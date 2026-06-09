# GetLocalComputerDnsName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18002fa38`
- end: `0x18002faca`
- name: `?GetLocalComputerDnsName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003278`
- `0x180023210`
- `0x180026e90`
- `0x180043878`
- `0x18005e4e4`
- `0x180060194`
- `0x18009d1bc`

## callees

- `0x18002de9c`
- `0x18002fa38`
- `0x18008cde4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002fa60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002faa8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002fa60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002faa8`

## pseudocode

```c
char __fastcall GetLocalComputerDnsName(LPWSTR *a1)
{
  DWORD LastError; // eax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 120;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(a1, 120) )
    return 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, *a1, &nSize) )
  {
LABEL_3:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(a1, nSize);
    return 1;
  }
  LastError = GetLastError();
  if ( LastError != 234 )
    goto LABEL_8;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(a1, nSize) )
    return 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, *a1, &nSize) )
    goto LABEL_3;
  LastError = GetLastError();
LABEL_8:
  if ( !LastError )
    goto LABEL_3;
  return GetLocalComputerNetBIOSName(a1);
}

```

## disassembly

```asm
0x18002fa38  push    rbx
0x18002fa3a  sub     rsp, 20h
0x18002fa3e  mov     edx, 78h ; 'x'
0x18002fa43  mov     rbx, rcx
0x18002fa46  mov     [rsp+28h+nSize], edx
0x18002fa4a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18002fa4f  test    al, al
0x18002fa51  jz      short loc_18002FAC6
0x18002fa53  mov     rdx, [rbx]; lpBuffer
0x18002fa56  lea     r8, [rsp+28h+nSize]; nSize
0x18002fa5b  mov     ecx, 3; NameType
0x18002fa60  call    cs:__imp_GetComputerNameExW
0x18002fa66  test    eax, eax
0x18002fa68  jz      short loc_18002FA7E
0x18002fa6a  mov     edx, [rsp+28h+nSize]
0x18002fa6e  mov     rcx, rbx
0x18002fa71  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18002fa76  mov     al, 1
0x18002fa78  add     rsp, 20h
0x18002fa7c  pop     rbx
0x18002fa7d  retn
0x18002fa7e  call    cs:__imp_GetLastError
0x18002fa84  cmp     eax, 0EAh
0x18002fa89  jnz     short loc_18002FAB8
0x18002fa8b  mov     edx, [rsp+28h+nSize]
0x18002fa8f  mov     rcx, rbx
0x18002fa92  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18002fa97  test    al, al
0x18002fa99  jz      short loc_18002FAC6
0x18002fa9b  mov     rdx, [rbx]; lpBuffer
0x18002fa9e  lea     r8, [rsp+28h+nSize]; nSize
0x18002faa3  mov     ecx, 3; NameType
0x18002faa8  call    cs:__imp_GetComputerNameExW
0x18002faae  test    eax, eax
0x18002fab0  jnz     short loc_18002FA6A
0x18002fab2  call    cs:__imp_GetLastError
0x18002fab8  test    eax, eax
0x18002faba  jz      short loc_18002FA6A
0x18002fabc  mov     rcx, rbx
0x18002fabf  call    ?GetLocalComputerNetBIOSName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; GetLocalComputerNetBIOSName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18002fac4  jmp     short loc_18002FA78
0x18002fac6  xor     al, al
0x18002fac8  jmp     short loc_18002FA78
```
