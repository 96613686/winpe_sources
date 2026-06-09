# Wsp::Facade::NativeVolume::FindDriveLetterAndMountPoint(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18005d8c4`
- end: `0x18005da2e`
- name: `?FindDriveLetterAndMountPoint@NativeVolume@Facade@Wsp@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18005de0c`

## callees

- `0x180003498`
- `0x18000d2bc`
- `0x18000dd74`
- `0x18001072c`
- `0x180014630`
- `0x180024ae8`
- `0x18005d8c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d972`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18005d96a`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18005d96a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Wsp::Facade::NativeVolume::FindDriveLetterAndMountPoint(__int64 a1, __int64 a2)
{
  BOOL VolumePathNamesForVolumeNameW; // ebx
  char *v5; // rdi
  unsigned __int64 v6; // rcx
  WCHAR *v7; // rax
  size_t v8; // rbx
  const WCHAR *v9; // rax
  unsigned __int64 i; // rdi
  LPWCH lpszVolumePathNames; // [rsp+20h] [rbp-20h] BYREF
  void *v13; // [rsp+28h] [rbp-18h]
  __int64 v14; // [rsp+30h] [rbp-10h]
  DWORD cchBufferLength; // [rsp+70h] [rbp+30h] BYREF

  cchBufferLength = 261;
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&lpszVolumePathNames);
  VolumePathNamesForVolumeNameW = 0;
  while ( !VolumePathNamesForVolumeNameW )
  {
    v5 = (char *)v13;
    v6 = ((_BYTE *)v13 - (_BYTE *)lpszVolumePathNames) >> 1;
    if ( cchBufferLength < v6 )
    {
      v7 = &lpszVolumePathNames[cchBufferLength];
LABEL_9:
      v13 = v7;
      goto LABEL_10;
    }
    if ( cchBufferLength > v6 )
    {
      if ( cchBufferLength <= (unsigned __int64)((v14 - (__int64)lpszVolumePathNames) >> 1) )
      {
        v8 = 2 * (cchBufferLength - v6);
        memset_0(v13, 0, v8);
        v7 = (WCHAR *)&v5[v8];
        goto LABEL_9;
      }
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpszVolumePathNames, cchBufferLength);
    }
LABEL_10:
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                      v9,
                                      lpszVolumePathNames,
                                      cchBufferLength,
                                      &cchBufferLength);
    if ( GetLastError() != 234 )
      return std::vector<unsigned short>::_Tidy(&lpszVolumePathNames);
  }
  for ( i = 0; i < ((_BYTE *)v13 - (_BYTE *)lpszVolumePathNames) >> 1; i += *(_QWORD *)(a1 + 88) + 1LL )
  {
    std::wstring::assign(a1 + 72);
    if ( (*(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72) >= 0x41u
       && *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72) <= 0x5Au
       || *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72) >= 0x61u
       && *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72) <= 0x7Au)
      && *(_WORD *)(std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72) + 2) == 58 )
    {
      *(_WORD *)(a1 + 172) = *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72);
      return std::vector<unsigned short>::_Tidy(&lpszVolumePathNames);
    }
  }
  return std::vector<unsigned short>::_Tidy(&lpszVolumePathNames);
}

```

## disassembly

```asm
0x18005d8c4  mov     [rsp-18h+arg_0], rbx
0x18005d8c9  mov     [rsp-18h+arg_8], rsi
0x18005d8ce  push    rbp
0x18005d8cf  push    rdi
0x18005d8d0  push    r14
0x18005d8d2  mov     rbp, rsp
0x18005d8d5  sub     rsp, 40h
0x18005d8d9  mov     r14, rdx
0x18005d8dc  mov     rsi, rcx
0x18005d8df  mov     [rbp+cchBufferLength], 105h
0x18005d8e6  lea     rcx, [rbp+lpszVolumePathNames]
0x18005d8ea  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18005d8ef  nop
0x18005d8f0  xor     ebx, ebx
0x18005d8f2  test    ebx, ebx
0x18005d8f4  jnz     loc_18005D988
0x18005d8fa  mov     ebx, [rbp+cchBufferLength]
0x18005d8fd  mov     rdx, [rbp+lpszVolumePathNames]
0x18005d901  mov     rdi, [rbp+var_18]
0x18005d905  mov     rcx, rdi
0x18005d908  sub     rcx, rdx
0x18005d90b  sar     rcx, 1
0x18005d90e  cmp     rbx, rcx
0x18005d911  jnb     short loc_18005D919
0x18005d913  lea     rax, [rdx+rbx*2]
0x18005d917  jmp     short loc_18005D94F
0x18005d919  jbe     short loc_18005D953
0x18005d91b  mov     rax, [rbp+var_10]
0x18005d91f  sub     rax, rdx
0x18005d922  sar     rax, 1
0x18005d925  cmp     rbx, rax
0x18005d928  jbe     short loc_18005D938
0x18005d92a  mov     rdx, rbx
0x18005d92d  lea     rcx, [rbp+lpszVolumePathNames]
0x18005d931  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005d936  jmp     short loc_18005D953
0x18005d938  sub     rbx, rcx
0x18005d93b  add     rbx, rbx
0x18005d93e  mov     r8, rbx; Size
0x18005d941  xor     edx, edx; Val
0x18005d943  mov     rcx, rdi; void *
0x18005d946  call    memset_0
0x18005d94b  lea     rax, [rbx+rdi]
0x18005d94f  mov     [rbp+var_18], rax
0x18005d953  mov     rcx, r14
0x18005d956  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d95b  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x18005d95f  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x18005d963  mov     rdx, [rbp+lpszVolumePathNames]; lpszVolumePathNames
0x18005d967  mov     rcx, rax; lpszVolumeName
0x18005d96a  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18005d970  mov     ebx, eax
0x18005d972  call    cs:__imp_GetLastError
0x18005d978  cmp     eax, 0EAh
0x18005d97d  jz      loc_18005D8F2
0x18005d983  jmp     loc_18005DA12
0x18005d988  xor     edi, edi
0x18005d98a  mov     rcx, [rbp+lpszVolumePathNames]
0x18005d98e  mov     rax, [rbp+var_18]
0x18005d992  sub     rax, rcx
0x18005d995  sar     rax, 1
0x18005d998  cmp     rdi, rax
0x18005d99b  jnb     short loc_18005DA12
0x18005d99d  lea     rbx, [rsi+48h]
0x18005d9a1  lea     rdx, [rcx+rdi*2]
0x18005d9a5  mov     rcx, rbx
0x18005d9a8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18005d9ad  mov     rcx, rbx
0x18005d9b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d9b5  cmp     word ptr [rax], 41h ; 'A'
0x18005d9b9  jb      short loc_18005D9C9
0x18005d9bb  mov     rcx, rbx
0x18005d9be  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d9c3  cmp     word ptr [rax], 5Ah ; 'Z'
0x18005d9c7  jbe     short loc_18005D9E5
0x18005d9c9  mov     rcx, rbx
0x18005d9cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d9d1  cmp     word ptr [rax], 61h ; 'a'
0x18005d9d5  jb      short loc_18005D9F4
0x18005d9d7  mov     rcx, rbx
0x18005d9da  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d9df  cmp     word ptr [rax], 7Ah ; 'z'
0x18005d9e3  ja      short loc_18005D9F4
0x18005d9e5  mov     rcx, rbx
0x18005d9e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005d9ed  cmp     word ptr [rax+2], 3Ah ; ':'
0x18005d9f2  jz      short loc_18005DA00
0x18005d9f4  mov     rax, [rsi+58h]
0x18005d9f8  inc     rax
0x18005d9fb  add     rdi, rax
0x18005d9fe  jmp     short loc_18005D98A
0x18005da00  mov     rcx, rbx
0x18005da03  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005da08  movzx   ecx, word ptr [rax]
0x18005da0b  mov     [rsi+0ACh], cx
0x18005da12  lea     rcx, [rbp+lpszVolumePathNames]
0x18005da16  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005da1b  mov     rbx, [rsp+40h+arg_0]
0x18005da20  mov     rsi, [rsp+40h+arg_8]
0x18005da25  add     rsp, 40h
0x18005da29  pop     r14
0x18005da2b  pop     rdi
0x18005da2c  pop     rbp
0x18005da2d  retn
```
