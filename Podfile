platform :ios, '8.0'

use_frameworks!
inhibit_all_warnings!

target 'GEOSwift' do
  pod 'geos'
end

target 'GEOSwiftTests' do
  pod 'geos'
end

# Workaround for Cocoapods issue #7606
post_install do |installer|
  installer.pods_project.build_configurations.each do |config|
    config.build_settings.delete('CODE_SIGNING_ALLOWED')
    config.build_settings.delete('CODE_SIGNING_REQUIRED')
  end

  installer.pods_project.targets.each do |target|  
	target.build_configurations.each do |config|  
	  if target.name == 'geos'  
	    # change libstdc++ to libc++
		  config.build_settings['CLANG_CXX_LIBRARY'] = 'libc++'  
	  end  
	end  
  end  
end

