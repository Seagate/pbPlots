# pbPlots Wrapper Build Configuration
# Delegates to appropriate language subfolder(s) based on build_variant option

project('pbPlots', 'cpp', version: '1.0.0', default_options: ['cpp_std=c++11', 'default_library=static'])

build_variant = get_option('build_variant')

if build_variant == 'cpp' or build_variant == 'both'
    subdir('Cpp')
endif

if build_variant == 'c' or build_variant == 'both'
    subdir('C')
endif
