# Copyright (C) 2014 eperi GmbH. All Rights Reserved.
# 
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; version 2 of the License.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301 USA

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/sql
                    ${PCRE_INCLUDES}
                    ${CMAKE_SOURCE_DIR}/include
#                    ${CMAKE_SOURCE_DIR}/include/mysql
                    ${CMAKE_SOURCE_DIR}/unittest/mytap
                    ${CMAKE_SOURCE_DIR}/extra/yassl/include
                    ${CMAKE_SOURCE_DIR}/storage/perfschema/unittest
                    ${CMAKE_SOURCE_DIR}/storage/perfschema
                    ${CMAKE_SOURCE_DIR}/storage/xtradb/include
                    )

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -D SINGLETON_TEST_DATA=\\\"${CMAKE_SOURCE_DIR}/unittest/eperi\\\" ")

MY_ADD_TESTS(eperi_aes 
  EXT "cc"
	LINK_LIBRARIES mysys_ssl)
	

if (WIN32) 

else()

MY_ADD_TESTS(
 pageenc
  EXT "cc" 
  LINK_LIBRARIES mysys_ssl xtradb perfschema mysys  sql mysql)

MY_ADD_TESTS(EperiKeySingleton
	EXT "cc" 
	LINK_LIBRARIES xtradb pcre mysys_ssl)
  
  
MY_ADD_TESTS(eperi)

endif()


file(COPY
	${CMAKE_CURRENT_LIST_DIR}/keys.txt
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xaa
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xab
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xac
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xad
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xae
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/xaf
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/keys.enc
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/compressed
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/compressed_full
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/compressed_6bytes_av
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/secret
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/secret.enc
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/long_secret
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/long_secret.enc
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/secret256
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/secret256.enc
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compressedaa
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compressedab
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compressedac
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)	
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compressedad
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_dynamicaa
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_dynamicab
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_dynamicac
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)	
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_dynamicad
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_redundantaa
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_redundantab
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_redundantac
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)	
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_redundantad
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compactaa
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compactab
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compactac
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)	
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compactad
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
file(COPY
	${CMAKE_CURRENT_LIST_DIR}/row_format_compactad_encrypted
	DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/)
		