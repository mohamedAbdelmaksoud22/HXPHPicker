platform :ios, '10.0'

install! 'cocoapods', disable_input_output_paths: true
inhibit_all_warnings!

use_frameworks!

target 'Example' do
  
  # 包含所有功能，网络图片使用的是 'Kingfisher', '~> 6.0'
  pod 'HXPHPicker/Full', :path => './'
  
  # 不带网络图片功能
  # pod 'HXPHPicker', :path => './'
  
  # 只有选择功能
  # pod 'HXPHPicker/Picker', :path => './'
  
  # 只有编辑功能
  # pod 'HXPHPicker/Editor', :path => './'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.name == 'Pods-Example'
#      Pod::UI.puts "'target':#{target}"
      target.build_configurations.each do |config|
        config.build_settings['MACH_O_TYPE'] = 'mh_dylib'
      end
    end
  end
end
