# Wsp::Facade::StorageVolume::GetMountPoint(void)

- ea: `0x180064af0`
- end: `0x180064c36`
- name: `?GetMountPoint@StorageVolume@Facade@Wsp@@UEAA?AV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x180002af4`
- `0x180003528`
- `0x180005fdc`
- `0x18000d624`
- `0x18000e14c`
- `0x180014c94`
- `0x1800257dc`
- `0x18004905c`
- `0x180064af0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bc2`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180064bb4`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180064bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Wsp::Facade::StorageVolume::GetMountPoint(__int64 a1, __int64 *a2)
{
  __int64 v3; // r8
  BOOL VolumePathNamesForVolumeNameW; // ebx
  char *v5; // rsi
  unsigned __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  const WCHAR *v9; // rax
  LPWCH v10; // rdx
  __int64 v12; // rax
  __int64 v13; // [rsp+28h] [rbp-18h] BYREF
  void *v14; // [rsp+30h] [rbp-10h]
  __int64 v15; // [rsp+38h] [rbp-8h]
  DWORD cchBufferLength; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF
  void *v18; // [rsp+78h] [rbp+38h] BYREF

  cchBufferLength = 261;
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v13);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 16LL))(v3, &v17);
  if ( v17 )
  {
    VolumePathNamesForVolumeNameW = 0;
    while ( 1 )
    {
      if ( VolumePathNamesForVolumeNameW )
      {
        v18 = operator new(0x20u);
        v12 = std::wstring::wstring(v18, v13);
        v18 = 0;
        *a2 = v12;
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v18);
        goto LABEL_13;
      }
      v5 = (char *)v14;
      v6 = ((__int64)v14 - v13) >> 1;
      if ( cchBufferLength < v6 )
        break;
      if ( cchBufferLength > v6 )
      {
        if ( cchBufferLength <= (unsigned __int64)((v15 - v13) >> 1) )
        {
          v8 = 2 * (cchBufferLength - v6);
          memset_0(v14, 0, v8);
          v7 = &v5[v8];
          goto LABEL_10;
        }
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&v13, cchBufferLength);
      }
LABEL_11:
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
      VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(v9, v10, cchBufferLength, &cchBufferLength);
      if ( GetLastError() != 234 )
        goto LABEL_12;
    }
    v7 = (char *)(v13 + 2LL * cchBufferLength);
LABEL_10:
    v14 = v7;
    goto LABEL_11;
  }
LABEL_12:
  *a2 = 0;
LABEL_13:
  std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v17);
  std::vector<unsigned short>::_Tidy(&v13);
  return a2;
}

```

## disassembly

```asm
0x180064af0  mov     [rsp-18h+arg_8], rbx
0x180064af5  push    rbp
0x180064af6  push    rsi
0x180064af7  push    rdi
0x180064af8  mov     rbp, rsp
0x180064afb  sub     rsp, 40h
0x180064aff  mov     rdi, rdx
0x180064b02  mov     r8, rcx
0x180064b05  mov     [rbp+cchBufferLength], 105h
0x180064b0c  lea     rcx, [rbp+var_18]
0x180064b10  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180064b15  nop
0x180064b16  mov     rax, [r8]
0x180064b19  lea     rdx, [rbp+arg_10]
0x180064b1d  mov     rcx, r8
0x180064b20  mov     rax, [rax+10h]
0x180064b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b29  nop
0x180064b2a  cmp     [rbp+arg_10], 0
0x180064b2f  jz      loc_180064BD9
0x180064b35  xor     ebx, ebx
0x180064b37  test    ebx, ebx
0x180064b39  jnz     loc_180064C04
0x180064b3f  mov     ebx, [rbp+cchBufferLength]
0x180064b42  mov     rsi, [rbp+var_10]
0x180064b46  mov     rcx, rsi
0x180064b49  mov     rdx, [rbp+var_18]
0x180064b4d  sub     rcx, rdx
0x180064b50  sar     rcx, 1
0x180064b53  cmp     rbx, rcx
0x180064b56  jnb     short loc_180064B5E
0x180064b58  lea     rax, [rdx+rbx*2]
0x180064b5c  jmp     short loc_180064B9C
0x180064b5e  jbe     short loc_180064BA0
0x180064b60  mov     rax, [rbp+var_8]
0x180064b64  sub     rax, rdx
0x180064b67  sar     rax, 1
0x180064b6a  cmp     rbx, rax
0x180064b6d  jbe     short loc_180064B81
0x180064b6f  mov     rdx, rbx
0x180064b72  lea     rcx, [rbp+var_18]
0x180064b76  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180064b7b  mov     rdx, [rbp+var_18]
0x180064b7f  jmp     short loc_180064BA0
0x180064b81  sub     rbx, rcx
0x180064b84  add     rbx, rbx
0x180064b87  mov     r8, rbx; Size
0x180064b8a  xor     edx, edx; Val
0x180064b8c  mov     rcx, rsi; void *
0x180064b8f  call    memset_0
0x180064b94  lea     rax, [rbx+rsi]
0x180064b98  mov     rdx, [rbp+var_18]
0x180064b9c  mov     [rbp+var_10], rax
0x180064ba0  mov     rcx, [rbp+arg_10]
0x180064ba4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064ba9  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x180064bad  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x180064bb1  mov     rcx, rax; lpszVolumeName
0x180064bb4  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180064bbb  nop     dword ptr [rax+rax+00h]
0x180064bc0  mov     ebx, eax
0x180064bc2  call    cs:__imp_GetLastError
0x180064bc9  nop     dword ptr [rax+rax+00h]
0x180064bce  cmp     eax, 0EAh
0x180064bd3  jz      loc_180064B37
0x180064bd9  mov     qword ptr [rdi], 0
0x180064be0  lea     rcx, [rbp+arg_10]
0x180064be4  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180064be9  nop
0x180064bea  lea     rcx, [rbp+var_18]
0x180064bee  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180064bf3  mov     rax, rdi
0x180064bf6  mov     rbx, [rsp+40h+arg_8]
0x180064bfb  add     rsp, 40h
0x180064bff  pop     rdi
0x180064c00  pop     rsi
0x180064c01  pop     rbp
0x180064c02  retn
0x180064c04  mov     ecx, 20h ; ' '; Size
0x180064c09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064c0e  mov     [rbp+arg_18], rax
0x180064c12  mov     rdx, [rbp+var_18]
0x180064c16  mov     rcx, rax
0x180064c19  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180064c1e  nop
0x180064c1f  mov     [rbp+arg_18], 0
0x180064c27  mov     [rdi], rax
0x180064c2a  lea     rcx, [rbp+arg_18]
0x180064c2e  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180064c33  jmp     short loc_180064BE0
```
