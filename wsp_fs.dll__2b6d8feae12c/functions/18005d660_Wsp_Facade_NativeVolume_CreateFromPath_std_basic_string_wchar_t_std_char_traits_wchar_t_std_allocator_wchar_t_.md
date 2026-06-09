# Wsp::Facade::NativeVolume::CreateFromPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18005d660`
- end: `0x18005d751`
- name: `?CreateFromPath@NativeVolume@Facade@Wsp@@SA?AV?$unique_ptr@VNativeVolume@Facade@Wsp@@U?$default_delete@VNativeVolume@Facade@Wsp@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180059920`

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180014630`
- `0x180025888`
- `0x18005d52c`
- `0x18005d660`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005d6c6`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005d6c6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005d6eb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005d6eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const WCHAR *__fastcall Wsp::Facade::NativeVolume::CreateFromPath(const WCHAR *a1, __int64 a2)
{
  const WCHAR *v4; // rax
  LPWSTR v5; // rdx
  LPWSTR lpszVolumeName[3]; // [rsp+20h] [rbp-19h] BYREF
  LPCWSTR lpszVolumeMountPoint[5]; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp+27h] BYREF

  lpszVolumeMountPoint[4] = a1;
  std::vector<wchar_t>::vector<wchar_t>(lpszVolumeMountPoint, 261);
  std::vector<wchar_t>::vector<wchar_t>(lpszVolumeName, 261);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  if ( GetVolumePathNameW(v4, v5, lpszVolumeMountPoint[1] - v5)
    && GetVolumeNameForVolumeMountPointW(
         lpszVolumeMountPoint[0],
         lpszVolumeName[0],
         lpszVolumeName[1] - lpszVolumeName[0]) )
  {
    std::wstring::wstring(v9, lpszVolumeName[0]);
    Wsp::Facade::NativeVolume::CreateFromName(a1, v9);
    std::wstring::_Tidy_deallocate(v9);
  }
  else
  {
    *(_QWORD *)a1 = 0;
  }
  std::vector<unsigned short>::_Tidy(lpszVolumeName);
  std::vector<unsigned short>::_Tidy(lpszVolumeMountPoint);
  return a1;
}

```

## disassembly

```asm
0x18005d660  mov     [rsp-8+arg_10], rbx
0x18005d665  mov     [rsp-8+arg_18], rdi
0x18005d66a  push    rbp
0x18005d66b  lea     rbp, [rsp-57h]
0x18005d670  sub     rsp, 90h
0x18005d677  mov     rax, cs:__security_cookie
0x18005d67e  xor     rax, rsp
0x18005d681  mov     [rbp+57h+var_10], rax
0x18005d685  mov     rbx, rdx
0x18005d688  mov     rdi, rcx
0x18005d68b  mov     [rbp+57h+var_38], rcx
0x18005d68f  mov     edx, 105h
0x18005d694  lea     rcx, [rbp+57h+lpszVolumeMountPoint]
0x18005d698  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18005d69d  nop
0x18005d69e  mov     edx, 105h
0x18005d6a3  lea     rcx, [rbp+57h+lpszVolumeName]
0x18005d6a7  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18005d6ac  nop
0x18005d6ad  mov     rdx, [rbp+57h+lpszVolumeMountPoint]
0x18005d6b1  mov     rcx, rbx
0x18005d6b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d6b9  mov     r8, [rbp+57h+var_50]
0x18005d6bd  sub     r8, rdx
0x18005d6c0  sar     r8, 1; cchBufferLength
0x18005d6c3  mov     rcx, rax; lpszFileName
0x18005d6c6  call    cs:__imp_GetVolumePathNameW
0x18005d6cc  test    eax, eax
0x18005d6ce  jnz     short loc_18005D6D9
0x18005d6d0  mov     qword ptr [rdi], 0
0x18005d6d7  jmp     short loc_18005D71A
0x18005d6d9  mov     rdx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x18005d6dd  mov     r8, [rbp+57h+var_68]
0x18005d6e1  sub     r8, rdx
0x18005d6e4  sar     r8, 1; cchBufferLength
0x18005d6e7  mov     rcx, [rbp+57h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x18005d6eb  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005d6f1  test    eax, eax
0x18005d6f3  jz      short loc_18005D6D0
0x18005d6f5  mov     rdx, [rbp+57h+lpszVolumeName]
0x18005d6f9  lea     rcx, [rbp+57h+var_30]
0x18005d6fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005d702  nop
0x18005d703  lea     rdx, [rbp+57h+var_30]
0x18005d707  mov     rcx, rdi
0x18005d70a  call    ?CreateFromName@NativeVolume@Facade@Wsp@@SA?AV?$unique_ptr@VNativeVolume@Facade@Wsp@@U?$default_delete@VNativeVolume@Facade@Wsp@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Wsp::Facade::NativeVolume::CreateFromName(std::wstring const &)
0x18005d70f  nop
0x18005d710  lea     rcx, [rbp+57h+var_30]
0x18005d714  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d719  nop
0x18005d71a  lea     rcx, [rbp+57h+lpszVolumeName]
0x18005d71e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005d723  nop
0x18005d724  lea     rcx, [rbp+57h+lpszVolumeMountPoint]
0x18005d728  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005d72d  mov     rax, rdi
0x18005d730  mov     rcx, [rbp+57h+var_10]
0x18005d734  xor     rcx, rsp; StackCookie
0x18005d737  call    __security_check_cookie
0x18005d73c  lea     r11, [rsp+90h+var_s0]
0x18005d744  mov     rbx, [r11+20h]
0x18005d748  mov     rdi, [r11+28h]
0x18005d74c  mov     rsp, r11
0x18005d74f  pop     rbp
0x18005d750  retn
```
