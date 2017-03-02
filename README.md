# Raven Code Style

This project includes two files for ensuring code compliance with common Raven style conventions: 

* .clang_format
    configuration file used by clang to clean up whitespace errors

* cpplint_raven.py

The repo contains an auto formatting script for the [ROS C++ Style Guidelines](http://wiki.ros.org/CppStyleGuide).

> **Note: this style is in beta format, please submit suggestions or fixes!**

## Setup

 * Install **clang_format**:

   ``sudo apt-get install -y clang-format-3.6``

 * Then symlink or copy in the root of your catkin workspace the file ``.clang_format``, located in this repo. You can save this file from [this link](https://raw.githubusercontent.com/davetcoleman/roscpp_code_format/master/.clang-format). For example, place it on your computer here:

   ``~/catkin_ws/.clang_format``

 * If you are interested in improving this configuration file, we recommend you checkout the git repo and symlink, e.g.:

   ``ln -s ~/roscpp_code_format/.clang-format ~/catkin_ws/.clang-format``

 * Now any file inside your catkin workspace will be formatted with the ROS style guidelines described in this config file

## Usage

You can run **clang_format** in several ways:

### Command Line

Format single file:

    clang-format-3.6 -i -style=file MY_ROS_NODE.cpp

Format entire directory recursively including subfolders:

    find . -name '*.h' -or -name '*.hpp' -or -name '*.cpp' | xargs clang-format-3.6 -i -style=file $1

The style guide and automated checker are based on those developed by Google 
-- see message below.

This is automated checker to make sure a C++ file follows Google's C++ style
guide (https://google.github.io/styleguide/cppguide.html). As it
heavily relies on regular expressions, cpplint.py won't catch all violations of
the style guide and will very occasionally report a false positive. There is a
list of things we currently don't handle very well at the top of cpplint.py,
and we welcome patches to improve it.

The linting tool takes a list of files as input. For full usage instructions,
please see the output of:

  ./cpplint.py --help

Unit tests are provided in cpplint_unittest.py. This file can safely be ignored
by end users who have downloaded this package and only want to run the lint
tool.

---

cpplint.py and its corresponding unit tests are Copyright (C) 2009 Google Inc.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

   * Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
   * Redistributions in binary form must reproduce the above
copyright notice, this list of conditions and the following disclaimer
in the documentation and/or other materials provided with the
distribution.
   * Neither the name of Google Inc. nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.