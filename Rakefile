# -*- coding: utf-8 -*-
$:.unshift("/Library/RubyMotion/lib")
require 'motion/project/template/osx'

begin
  require 'bundler'
  Bundler.require

  require 'ib'
rescue LoadError
end

Motion::Project::App.setup do |app|
  # Use `rake config' to see complete project settings.
  app.name = 'GyaimMotion'
  app.icon = 'Gyaim.png'
  app.identifier = "com.pitecan.inputmethod.GyaimMotion"
  app.frameworks << 'InputMethodKit'

  # 順番がある場合 foo の方が先、とか
  # http://www.rubymotion.com/developers/guides/manuals/cocoa/project-management/
  # app.files_dependencies 'app/bar.rb' => 'app/foo.rb'

  #app.info_plist['CFBundleURLTypes'] = [
  #  { 'CFBundleURLName' => 'com.mycompany.x-videoplayer',
  #    'CFBundleURLSchemes' => ['x-videoplayer'] }
  #]
  app.info_plist['tsInputMethodCharacterRepertoireKey'] = [
    "Hira", "Latn"
  ]
  app.info_plist['InputMethodConnectionName'] = "Gyaim_Connection"
  app.info_plist['InputMethodServerControllerClass'] = "GyaimController"
  app.info_plist['InputMethodServerDelegateClass'] = "GyaimController"
  app.info_plist['LSBackgroundOnoly'] = true
  app.info_plist['NSMainNibFile'] = "MainMenu"
  app.info_plist['tsInputMethodIconFileKey'] = "icon.tiff"

  app.info_plist['ComponentInputModeDict'] = {
    'tsInputModeListKey' => {
      'com.apple.inputmethod.Japanese' => {
        "TISInputSourceID" => "com.pitecan.inputmethod.Gyaim.Japanese",
        "TISIntendedLanguage" => "ja",
        "tsInputModeScriptKey" => "smJapanese",
        "tsInputModePrimaryInScriptKey" => true
      }
    },
    "tsVisibleInputModeOrderedArrayKey" => [
      "com.apple.inputmethod.Japanese"
    ]
  }

end
