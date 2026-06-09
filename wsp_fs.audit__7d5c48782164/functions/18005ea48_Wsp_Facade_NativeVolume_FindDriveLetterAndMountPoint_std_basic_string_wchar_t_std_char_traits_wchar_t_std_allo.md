# Wsp::Facade::NativeVolume::FindDriveLetterAndMountPoint(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18005ea48`
- end: `0x18005ebbf`
- name: `?FindDriveLetterAndMountPoint@NativeVolume@Facade@Wsp@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18005efa0`

## callees

- `0x180003528`
- `0x18000d624`
- `0x18000e14c`
- `0x180010b90`
- `0x180014c94`
- `0x1800257dc`
- `0x18005ea48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eafc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eafc`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18005eaee`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18005eaee`

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
    std::wstring::assign(a1 + 72, &lpszVolumePathNames[i]);
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
0x18005ea48  mov     [rsp-18h+arg_0], rbx
0x18005ea4d  mov     [rsp-18h+arg_8], rsi
0x18005ea52  push    rbp
0x18005ea53  push    rdi
0x18005ea54  push    r14
0x18005ea56  mov     rbp, rsp
0x18005ea59  sub     rsp, 40h
0x18005ea5d  mov     r14, rdx
0x18005ea60  mov     rsi, rcx
0x18005ea63  mov     [rbp+cchBufferLength], 105h
0x18005ea6a  lea     rcx, [rbp+lpszVolumePathNames]
0x18005ea6e  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18005ea73  nop
0x18005ea74  xor     ebx, ebx
0x18005ea76  test    ebx, ebx
0x18005ea78  jnz     loc_18005EB18
0x18005ea7e  mov     ebx, [rbp+cchBufferLength]
0x18005ea81  mov     rdx, [rbp+lpszVolumePathNames]
0x18005ea85  mov     rdi, [rbp+var_18]
0x18005ea89  mov     rcx, rdi
0x18005ea8c  sub     rcx, rdx
0x18005ea8f  sar     rcx, 1
0x18005ea92  cmp     rbx, rcx
0x18005ea95  jnb     short loc_18005EA9D
0x18005ea97  lea     rax, [rdx+rbx*2]
0x18005ea9b  jmp     short loc_18005EAD3
0x18005ea9d  jbe     short loc_18005EAD7
0x18005ea9f  mov     rax, [rbp+var_10]
0x18005eaa3  sub     rax, rdx
0x18005eaa6  sar     rax, 1
0x18005eaa9  cmp     rbx, rax
0x18005eaac  jbe     short loc_18005EABC
0x18005eaae  mov     rdx, rbx
0x18005eab1  lea     rcx, [rbp+lpszVolumePathNames]
0x18005eab5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005eaba  jmp     short loc_18005EAD7
0x18005eabc  sub     rbx, rcx
0x18005eabf  add     rbx, rbx
0x18005eac2  mov     r8, rbx; Size
0x18005eac5  xor     edx, edx; Val
0x18005eac7  mov     rcx, rdi; void *
0x18005eaca  call    memset_0
0x18005eacf  lea     rax, [rbx+rdi]
0x18005ead3  mov     [rbp+var_18], rax
0x18005ead7  mov     rcx, r14
0x18005eada  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eadf  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x18005eae3  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x18005eae7  mov     rdx, [rbp+lpszVolumePathNames]; lpszVolumePathNames
0x18005eaeb  mov     rcx, rax; lpszVolumeName
0x18005eaee  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18005eaf5  nop     dword ptr [rax+rax+00h]
0x18005eafa  mov     ebx, eax
0x18005eafc  call    cs:__imp_GetLastError
0x18005eb03  nop     dword ptr [rax+rax+00h]
0x18005eb08  cmp     eax, 0EAh
0x18005eb0d  jz      loc_18005EA76
0x18005eb13  jmp     loc_18005EBA2
0x18005eb18  xor     edi, edi
0x18005eb1a  mov     rcx, [rbp+lpszVolumePathNames]
0x18005eb1e  mov     rax, [rbp+var_18]
0x18005eb22  sub     rax, rcx
0x18005eb25  sar     rax, 1
0x18005eb28  cmp     rdi, rax
0x18005eb2b  jnb     short loc_18005EBA2
0x18005eb2d  lea     rbx, [rsi+48h]
0x18005eb31  lea     rdx, [rcx+rdi*2]
0x18005eb35  mov     rcx, rbx
0x18005eb38  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18005eb3d  mov     rcx, rbx
0x18005eb40  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb45  cmp     word ptr [rax], 41h ; 'A'
0x18005eb49  jb      short loc_18005EB59
0x18005eb4b  mov     rcx, rbx
0x18005eb4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb53  cmp     word ptr [rax], 5Ah ; 'Z'
0x18005eb57  jbe     short loc_18005EB75
0x18005eb59  mov     rcx, rbx
0x18005eb5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb61  cmp     word ptr [rax], 61h ; 'a'
0x18005eb65  jb      short loc_18005EB84
0x18005eb67  mov     rcx, rbx
0x18005eb6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb6f  cmp     word ptr [rax], 7Ah ; 'z'
0x18005eb73  ja      short loc_18005EB84
0x18005eb75  mov     rcx, rbx
0x18005eb78  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb7d  cmp     word ptr [rax+2], 3Ah ; ':'
0x18005eb82  jz      short loc_18005EB90
0x18005eb84  mov     rax, [rsi+58h]
0x18005eb88  inc     rax
0x18005eb8b  add     rdi, rax
0x18005eb8e  jmp     short loc_18005EB1A
0x18005eb90  mov     rcx, rbx
0x18005eb93  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005eb98  movzx   ecx, word ptr [rax]
0x18005eb9b  mov     [rsi+0ACh], cx
0x18005eba2  lea     rcx, [rbp+lpszVolumePathNames]
0x18005eba6  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005ebab  mov     rbx, [rsp+40h+arg_0]
0x18005ebb0  mov     rsi, [rsp+40h+arg_8]
0x18005ebb5  add     rsp, 40h
0x18005ebb9  pop     r14
0x18005ebbb  pop     rdi
0x18005ebbc  pop     rbp
0x18005ebbd  retn
```
