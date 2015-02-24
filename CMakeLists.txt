cmake_minimum_required(VERSION 2.8)

project(FreeSurferSampleAtlas)

configure_file(${FreeSurferSampleAtlas_SOURCE_DIR}/FreeSurferSampleAtlas.config.in  ${FreeSurferSampleAtlas_BINARY_DIR}/FreeSurferSampleAtlas.config @ONLY)

# These are used to customize the FreeSurferSampleAtlas.mrml file
set(ATLAS_NAME FreeSurferSampleAtlas)
set(ATLAS_VOLUME ${FreeSurferSampleAtlas_SOURCE_DIR}/Atlas/brain.nrrd)
set(ATLAS_VOLUME_NAME ${ATLAS_NAME}Volume)
set(ATLAS_COLOR_TABLE ${FreeSurferSampleAtlas_SOURCE_DIR}/Atlas/FreeSurferColors.ctbl)
set(ATLAS_COLOR_TABLE_NAME ${ATLAS_NAME}Colors)
set(ATLAS_LABELS ${FreeSurferSampleAtlas_SOURCE_DIR}/Atlas/aseg.nrrd)
set(ATLAS_LABELS_NAME ${ATLAS_NAME}Labels)
set(MRML_FILENAME ${FreeSurferSampleAtlas_SOURCE_DIR}/Atlas/${ATLAS_NAME}.mrml.in)

configure_file(${FreeSurferSampleAtlas_SOURCE_DIR}/Atlas/FreeSurferSampleAtlas.mrml.in  ${FreeSurferSampleAtlas_BINARY_DIR}/FreeSurferSampleAtlas.mrml @ONLY)
