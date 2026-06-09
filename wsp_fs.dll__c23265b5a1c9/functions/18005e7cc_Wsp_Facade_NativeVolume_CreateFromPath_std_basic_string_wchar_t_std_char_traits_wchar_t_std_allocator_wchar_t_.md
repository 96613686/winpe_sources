# Wsp::Facade::NativeVolume::CreateFromPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18005e7cc`
- end: `0x18005e8ca`
- name: `?CreateFromPath@NativeVolume@Facade@Wsp@@SA?AV?$unique_ptr@VNativeVolume@Facade@Wsp@@U?$default_delete@VNativeVolume@Facade@Wsp@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18005aa20`

## callees

- `0x180002ad0`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000e14c`
- `0x180014c94`
- `0x180026588`
- `0x18005e694`
- `0x18005e7cc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005e832`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005e832`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005e85d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005e85d`

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
0x18005e7cc  mov     [rsp-8+arg_10], rbx
0x18005e7d1  mov     [rsp-8+arg_18], rdi
0x18005e7d6  push    rbp
0x18005e7d7  lea     rbp, [rsp-57h]
0x18005e7dc  sub     rsp, 90h
0x18005e7e3  mov     rax, cs:__security_cookie
0x18005e7ea  xor     rax, rsp
0x18005e7ed  mov     [rbp+57h+var_10], rax
0x18005e7f1  mov     rbx, rdx
0x18005e7f4  mov     rdi, rcx
0x18005e7f7  mov     [rbp+57h+var_38], rcx
0x18005e7fb  mov     edx, 105h
0x18005e800  lea     rcx, [rbp+57h+lpszVolumeMountPoint]
0x18005e804  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18005e809  nop
0x18005e80a  mov     edx, 105h
0x18005e80f  lea     rcx, [rbp+57h+lpszVolumeName]
0x18005e813  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18005e818  nop
0x18005e819  mov     rdx, [rbp+57h+lpszVolumeMountPoint]
0x18005e81d  mov     rcx, rbx
0x18005e820  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005e825  mov     r8, [rbp+57h+var_50]
0x18005e829  sub     r8, rdx
0x18005e82c  sar     r8, 1; cchBufferLength
0x18005e82f  mov     rcx, rax; lpszFileName
0x18005e832  call    cs:__imp_GetVolumePathNameW
0x18005e839  nop     dword ptr [rax+rax+00h]
0x18005e83e  test    eax, eax
0x18005e840  jnz     short loc_18005E84B
0x18005e842  mov     qword ptr [rdi], 0
0x18005e849  jmp     short loc_18005E892
0x18005e84b  mov     rdx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x18005e84f  mov     r8, [rbp+57h+var_68]
0x18005e853  sub     r8, rdx
0x18005e856  sar     r8, 1; cchBufferLength
0x18005e859  mov     rcx, [rbp+57h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x18005e85d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005e864  nop     dword ptr [rax+rax+00h]
0x18005e869  test    eax, eax
0x18005e86b  jz      short loc_18005E842
0x18005e86d  mov     rdx, [rbp+57h+lpszVolumeName]
0x18005e871  lea     rcx, [rbp+57h+var_30]
0x18005e875  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005e87a  nop
0x18005e87b  lea     rdx, [rbp+57h+var_30]
0x18005e87f  mov     rcx, rdi
0x18005e882  call    ?CreateFromName@NativeVolume@Facade@Wsp@@SA?AV?$unique_ptr@VNativeVolume@Facade@Wsp@@U?$default_delete@VNativeVolume@Facade@Wsp@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Wsp::Facade::NativeVolume::CreateFromName(std::wstring const &)
0x18005e887  nop
0x18005e888  lea     rcx, [rbp+57h+var_30]
0x18005e88c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e891  nop
0x18005e892  lea     rcx, [rbp+57h+lpszVolumeName]
0x18005e896  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005e89b  nop
0x18005e89c  lea     rcx, [rbp+57h+lpszVolumeMountPoint]
0x18005e8a0  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005e8a5  mov     rax, rdi
0x18005e8a8  mov     rcx, [rbp+57h+var_10]
0x18005e8ac  xor     rcx, rsp; StackCookie
0x18005e8af  call    __security_check_cookie
0x18005e8b4  lea     r11, [rsp+90h+var_s0]
0x18005e8bc  mov     rbx, [r11+20h]
0x18005e8c0  mov     rdi, [r11+28h]
0x18005e8c4  mov     rsp, r11
0x18005e8c7  pop     rbp
0x18005e8c8  retn
```
