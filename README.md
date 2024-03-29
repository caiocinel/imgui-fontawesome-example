
## ImGui + FontAwesome Example

- Icon header provided by [IconFontCppHeaders](https://github.com/juliettef/IconFontCppHeaders)
- Font binary generated using ImGui [binary_to_compressed_c](https://github.com/ocornut/imgui/blob/master/misc/fonts/binary_to_compressed_c.cpp "binary_to_compressed_c.cpp")
- Built using ImGui DirectX11 Example

### How to Update Font Files
1. Download from webfonts [FontAwesome .tff file](https://github.com/FortAwesome/Font-Awesome/"webfonts") 
2. Download (or generate) updated headers from [IconFontCppHeaders](https://github.com/juliettef/IconFontCppHeaders)
3. Convert .tff file to byte array
4. Replace template example files

### How to convert .tff to header file
1. Download [binary_to_compressed_c](https://github.com/ocornut/imgui/blob/master/misc/fonts/binary_to_compressed_c.cpp "binary_to_compressed_c.cpp") and compile following file comments (or use precompiled version from release)
2. Run generated executable *with fonts in same folder that executable* using following parameters: ```binary_to_compressed_c.exe fa-solid-900.ttf FontAwesome > fa.h```
3. Finished

### Additional Information
1. You can use brands icons following the same steps but using Brands fonts
2. To use multiple icon sizes you'll need add create multiple versions in memory like:
 ```
 io.Fonts->AddFontFromMemoryCompressedTTF(FA_compressed_data, FA_compressed_size, 12.0f, &icons_config, icons_ranges);
 io.Fonts->AddFontFromMemoryCompressedTTF(FA_compressed_data, FA_compressed_size, 20.0f, &icons_config, icons_ranges);
 ```
 3. If a quotation mark is displayed instead of the icon, probably the Icon header and Font Awesome version are not the same
    

#### Performance Implications:
I had some issues with performance degradation when using custom icons in a extreme low-end hardware (in a application with a HUGE iterations per second)

#### See more detaills about implementation in main.cpp
