#
# Copyright Soramitsu Co., Ltd. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0
#

add_library(sector_index
        impl/index_impl.cpp
        )

target_link_libraries(sector_index
        sector_file
        outcome
        uri_parser
        Boost::filesystem
        )

add_library(store
        impl/local_store.cpp
        impl/store_error.cpp
        )

target_link_libraries(store
        sector_index
        buffer
        rpc
        logger
        )
