� ��cmake_minimum_required(VERSION 2.8)
#Ïðîâåðêà âåðñèè CMake.
    set(PROJECT_NAME TArrList)
#Ñîçäàåì îáû÷íóþ ëîêàëüíóþ ïåðåìåííóþ ñ èìåíåì ïðîåêòà
    project($
	    {
	    PROJECT_NAME}

)
#Íàçâàíèå ïðîåêòà
    set(Arrlist Arrlist)
    set(arrlistlib arrlistlib)
    set(arrlisttest arrlisttest)
    set(CMAKE_CONFIGURATION_TYPES "Debug;Release" CACHE STRING "Configs"
	FORCE)
#Ñîçäàåòñÿ ïåðåìåííàÿ CMAKE_CONFIGURATION_TYPES ñî çíà÷åíèåì "Debug;Release" è ìåòêîé/ðàçäåëîì Configs, ïåðåìåííàÿ ñîõðàíèåòñÿ â ñïåöèàëüíîì ôàéëå äîñòóïíîì èç âñåõ ôàéëîâ,
    if (NOT CMAKE_BUILD_TYPE)
#ïðîâåðêà èìåþùèõñÿ ó êîìïèëÿòîðà âàðèàíòîâ ñáîðêè
    set(CMAKE_BUILD_TYPE Release)
#Åñëè íåò òî óñòàíàâëèâàåì Release
	endif()
	include_directories($
			    {
			    CMAKE_CURRENT_SOURCE_DIR}
			    /arrlistlib)
    include_directories($
			{
			CMAKE_CURRENT_SOURCE_DIR}

			/gtest)
    add_subdirectory(Arrlist)
    add_subdirectory(arrlistlib)
    add_subdirectory(arrlisttest)
    add_subdirectory(gtest)
    file(GLOB hdrs "*.h*")
#Äîáàâëÿåì â ïåðåìåííóþ hdrs âñå ôàéëû ñ ðàñøèðåíèåì .h
    file(GLOB srcs "*.cpp")
#Äîáàâëÿåì â ïåðåìåííóþ srcs âñå ôàéëû ñ ðàñøèðåíèåì .h
