# Wsp::Facade::StorageVolume::GetMountPoint(void)

- ea: `0x180063860`
- end: `0x180063999`
- name: `?GetMountPoint@StorageVolume@Facade@Wsp@@UEAA?AV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x180002a94`
- `0x180003498`
- `0x180005e68`
- `0x18000d2bc`
- `0x18000dd74`
- `0x180014630`
- `0x180024ae8`
- `0x180047e98`
- `0x180063860`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006392c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006392c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180063924`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180063924`

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
0x180063860  mov     [rsp-18h+arg_8], rbx
0x180063865  push    rbp
0x180063866  push    rsi
0x180063867  push    rdi
0x180063868  mov     rbp, rsp
0x18006386b  sub     rsp, 40h
0x18006386f  mov     rdi, rdx
0x180063872  mov     r8, rcx
0x180063875  mov     [rbp+cchBufferLength], 105h
0x18006387c  lea     rcx, [rbp+var_18]
0x180063880  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180063885  nop
0x180063886  mov     rax, [r8]
0x180063889  lea     rdx, [rbp+arg_10]
0x18006388d  mov     rcx, r8
0x180063890  mov     rax, [rax+10h]
0x180063894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063899  nop
0x18006389a  cmp     [rbp+arg_10], 0
0x18006389f  jz      loc_18006393D
0x1800638a5  xor     ebx, ebx
0x1800638a7  test    ebx, ebx
0x1800638a9  jnz     loc_180063967
0x1800638af  mov     ebx, [rbp+cchBufferLength]
0x1800638b2  mov     rsi, [rbp+var_10]
0x1800638b6  mov     rcx, rsi
0x1800638b9  mov     rdx, [rbp+var_18]
0x1800638bd  sub     rcx, rdx
0x1800638c0  sar     rcx, 1
0x1800638c3  cmp     rbx, rcx
0x1800638c6  jnb     short loc_1800638CE
0x1800638c8  lea     rax, [rdx+rbx*2]
0x1800638cc  jmp     short loc_18006390C
0x1800638ce  jbe     short loc_180063910
0x1800638d0  mov     rax, [rbp+var_8]
0x1800638d4  sub     rax, rdx
0x1800638d7  sar     rax, 1
0x1800638da  cmp     rbx, rax
0x1800638dd  jbe     short loc_1800638F1
0x1800638df  mov     rdx, rbx
0x1800638e2  lea     rcx, [rbp+var_18]
0x1800638e6  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800638eb  mov     rdx, [rbp+var_18]
0x1800638ef  jmp     short loc_180063910
0x1800638f1  sub     rbx, rcx
0x1800638f4  add     rbx, rbx
0x1800638f7  mov     r8, rbx; Size
0x1800638fa  xor     edx, edx; Val
0x1800638fc  mov     rcx, rsi; void *
0x1800638ff  call    memset_0
0x180063904  lea     rax, [rbx+rsi]
0x180063908  mov     rdx, [rbp+var_18]
0x18006390c  mov     [rbp+var_10], rax
0x180063910  mov     rcx, [rbp+arg_10]
0x180063914  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180063919  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x18006391d  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x180063921  mov     rcx, rax; lpszVolumeName
0x180063924  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18006392a  mov     ebx, eax
0x18006392c  call    cs:__imp_GetLastError
0x180063932  cmp     eax, 0EAh
0x180063937  jz      loc_1800638A7
0x18006393d  mov     qword ptr [rdi], 0
0x180063944  lea     rcx, [rbp+arg_10]
0x180063948  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18006394d  nop
0x18006394e  lea     rcx, [rbp+var_18]
0x180063952  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180063957  mov     rax, rdi
0x18006395a  mov     rbx, [rsp+40h+arg_8]
0x18006395f  add     rsp, 40h
0x180063963  pop     rdi
0x180063964  pop     rsi
0x180063965  pop     rbp
0x180063966  retn
0x180063967  mov     ecx, 20h ; ' '; Size
0x18006396c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063971  mov     [rbp+arg_18], rax
0x180063975  mov     rdx, [rbp+var_18]
0x180063979  mov     rcx, rax
0x18006397c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063981  nop
0x180063982  mov     [rbp+arg_18], 0
0x18006398a  mov     [rdi], rax
0x18006398d  lea     rcx, [rbp+arg_18]
0x180063991  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180063996  jmp     short loc_180063944
```
