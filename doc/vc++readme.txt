Windows
-------

Prerequisites

BOOST_TRUNK environmental variable set to the path to a current Boost trunk checkout.
Example:

  setx BOOST_TRUNK=c:\boost\trunk

Boost libraries available in %BOOST_TRUNK%\stage\lib. Example:
 
  cd %BOOST_TRUNK%
  .\bootstrap
  .\b2 --with-system --with-chrono --with-timer link=shared stage

path environmental variable set to include %BOOST_TRUNK%\stage\lib. Example:
 
  path %path%;%BOOST_TRUNK%\stage\lib

The provided Visual Studio solution (endian/test/msvc2012/endian.sln) has these Property
setups:

C/C++|General|Additional Include Directories: prefix ..\..\..\..\endian\include;$(BOOST_TRUNK);
C/C++|Preprocessor: prefix BOOST_ALL_DYN_LINK; 
Linker|General|Additional Library Directories: $(BOOST_TRUNK)\stage\lib

IMPORTANT: If Preprocessor macros are supplied via a common property page,
<inherit from parent or project defaults> must be set for each project!
------------------------------------------------------------------------------------------
Copyright Beman Dawes, 2013
Distributed under the Boost Software License, Version 1.0.
See http://www.boost.org/LICENSE_1_0.txt
