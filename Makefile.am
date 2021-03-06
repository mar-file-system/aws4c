#Copyright (c) 2015, Los Alamos National Security, LLC
#All rights reserved.
#
#Copyright 2015.  Los Alamos National Security, LLC. This software was produced
#under U.S. Government contract DE-AC52-06NA25396 for Los Alamos National
#Laboratory (LANL), which is operated by Los Alamos National Security, LLC for
#the U.S. Department of Energy. The U.S. Government has rights to use, reproduce,
#and distribute this software.  NEITHER THE GOVERNMENT NOR LOS ALAMOS NATIONAL
#SECURITY, LLC MAKES ANY WARRANTY, EXPRESS OR IMPLIED, OR ASSUMES ANY LIABILITY
#FOR THE USE OF THIS SOFTWARE.  If software is modified to produce derivative
#works, such modified software should be clearly marked, so as not to confuse it
#with the version available from LANL.
# 
#Additionally, redistribution and use in source and binary forms, with or without
#modification, are permitted provided that the following conditions are met:
#1. Redistributions of source code must retain the above copyright notice, this
#list of conditions and the following disclaimer.
#
#2. Redistributions in binary form must reproduce the above copyright notice,
#this list of conditions and the following disclaimer in the documentation
#and/or other materials provided with the distribution.
#3. Neither the name of Los Alamos National Security, LLC, Los Alamos National
#Laboratory, LANL, the U.S. Government, nor the names of its contributors may be
#used to endorse or promote products derived from this software without specific
#prior written permission.
#
#THIS SOFTWARE IS PROVIDED BY LOS ALAMOS NATIONAL SECURITY, LLC AND CONTRIBUTORS
#"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
#THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
#ARE DISCLAIMED. IN NO EVENT SHALL LOS ALAMOS NATIONAL SECURITY, LLC OR
#CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY,
#OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
#SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
#INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT,
#STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY
#OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
#
#-----
#NOTE:
#-----
#Although these files reside in a seperate repository, they fall under the MarFS copyright and license.
#
#MarFS is released under the BSD license.
#
#MarFS was reviewed and released by LANL under Los Alamos Computer Code identifier:
#LA-CC-15-039.
#
#MarFS uses libaws4c for Amazon S3 object communication. The original version
#is at https://aws.amazon.com/code/Amazon-S3/2601 and under the LGPL license.
#LANL added functionality to the original work. The original work plus
#LANL contributions is found at https://github.com/jti-lanl/aws4c.
#
#GNU licenses can be found at http://www.gnu.org/licenses/.

AUTOMAKE_OPTIONS = foreign

# automake requires '=' before '+=', even for these built-in vars
AM_CPPFLAGS =
AM_CFLAGS   =
AM_LDFLAGS  =


include_HEADERS = aws4c.h aws4c_extra.h


lib_LIBRARIES = libaws4c.a libaws4c_extra.a
libaws4c_a_SOURCES = aws4c.c
libaws4c_a_CFLAGS  = @AWSXML_CFLAGS@
libaws4c_extra_a_SOURCES = aws4c_extra.c
libaws4c_extra_a_CFLAGS  = @AWSXML_CFLAGS@


# ---
bin_PROGRAMS = 
# ---
bin_SCRIPTS = 
# ---
check_PROGRAMS = s3_delete s3_get s3_put sqs_example

s3_delete_SOURCES = s3_delete.c
s3_delete_LDADD   = libaws4c.a libaws4c_extra.a
s3_delete_LDFLAGS = -laws4c -laws4c_extra -lcrypto `curl-config --libs`

s3_get_SOURCES = s3_get.c
s3_get_LDADD   = libaws4c.a libaws4c_extra.a
s3_get_LDFLAGS = -laws4c -laws4c_extra -lcrypto `curl-config --libs`

s3_put_SOURCES = s3_put.c
s3_put_LDADD   = libaws4c.a libaws4c_extra.a
s3_put_LDFLAGS = -laws4c -laws4c_extra -lcrypto `curl-config --libs`

sqs_example_SOURCES = sqs_example.c
sqs_example_LDADD   = libaws4c.a libaws4c_extra.a
sqs_example_LDFLAGS = -laws4c -laws4c_extra -lcrypto `curl-config --libs`

check_PROGRAMS += test_aws
test_aws_SOURCES = test_aws.c
test_aws_CFLAGS  = @AWSXML_CFLAGS@
test_aws_LDADD   = libaws4c.a libaws4c_extra.a
test_aws_LDFLAGS = -laws4c -laws4c_extra -lcrypto `curl-config --libs` @AWSXML_LIBS@

TESTS = 

