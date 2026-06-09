# TerminationStore::AddItem(TerminationItem)

- ea: `0x180015e48`
- end: `0x1800160ec`
- name: `?AddItem@TerminationStore@@QEAAJUTerminationItem@@@Z`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015c40`

## callees

- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x180015e48`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18003db78`
- `0x18003e864`
- `0x18009b968`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ec5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ec5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016077`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016077`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015f32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015fc6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015f32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015fc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016009`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016042`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800160aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016009`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016042`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800160aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ef0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ef0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180015f68`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180015f68`

## string_xrefs

- `0x180015e9b`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x180015f7b`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x180016050`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
__int64 __fastcall TerminationStore::AddItem(__int64 a1, unsigned int *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  TerminationStore *v6; // rcx
  __int64 v7; // rdx
  HKEY *phkResult; // rax
  __int64 v9; // rax
  unsigned int v10; // eax
  int dwOptions; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp+Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp+1Fh] BYREF
  LPVOID lpMem[2]; // [rsp+70h] [rbp+27h] BYREF
  char v20; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  hKey = 0;
  dwDisposition = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpMem,
         L"%ls\\%u",
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\TermReason",
         *a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hKey = 0;
    v4 = 1;
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem[0], 0, 0, 1u, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( v5 )
    {
      v7 = 402;
LABEL_13:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
             (const char *)v5,
             dwOptionsa);
      goto LABEL_25;
    }
    if ( dwDisposition == 2 )
    {
      if ( TerminationStore::KeyIsValidItem(v6, hKey, *a2) )
      {
LABEL_25:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        return v4;
      }
      v5 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem[0]);
      if ( v5 )
      {
        v7 = 414;
        goto LABEL_13;
      }
      phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem[0], 0, 0, 1u, 0xF003Fu, 0, phkResult, &dwDisposition);
      if ( v5 )
      {
        v7 = 424;
        goto LABEL_13;
      }
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)a2 + v9 + 2) );
    v5 = RegSetValueExW(hKey, L"Terminator", 0, 1u, (const BYTE *)a2 + 4, 2 * v9 + 2);
    if ( v5 )
    {
      v7 = 432;
    }
    else
    {
      v10 = RegSetValueExW(hKey, L"Reason", 0, 4u, (const BYTE *)a2 + 132, 4u);
      if ( v10 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1B7,
               (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
               (const char *)v10,
               dwOptionsb);
        goto LABEL_3;
      }
      SystemTimeAsFileTime = 0;
      *(_QWORD *)Data = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *(struct _FILETIME *)Data = SystemTimeAsFileTime;
      v5 = RegSetValueExW(hKey, L"CreationTime", 0, 0xBu, Data, 8u);
      if ( !v5 )
      {
        v4 = 0;
        goto LABEL_25;
      }
      v7 = 453;
    }
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x188,
    (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
    (const char *)(unsigned int)v3,
    dwOptions);
LABEL_3:
  if ( lpMem[0] != &v20 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180015e48  mov     [rsp-8+arg_0], rbx
0x180015e4d  mov     [rsp-8+arg_10], rsi
0x180015e52  push    rbp
0x180015e53  push    rdi
0x180015e54  push    r14
0x180015e56  lea     rbp, [rsp-47h]
0x180015e5b  sub     rsp, 90h
0x180015e62  xor     esi, esi
0x180015e64  lea     rcx, [rbp+57h+lpMem]; void *
0x180015e68  mov     [rbp+57h+hKey], rsi
0x180015e6c  mov     rdi, rdx
0x180015e6f  mov     [rbp+57h+dwDisposition], esi
0x180015e72  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180015e77  mov     r9d, [rdi]
0x180015e7a  lea     r8, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\Windows E"...
0x180015e81  lea     rdx, aLsU; "%ls\\%u"
0x180015e88  lea     rcx, [rbp+57h+lpMem]
0x180015e8c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180015e91  mov     ebx, eax
0x180015e93  test    eax, eax
0x180015e95  jns     short loc_180015EE3
0x180015e97  mov     rcx, [rbp+5Fh]; this
0x180015e9b  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x180015ea2  mov     r9d, eax; char *
0x180015ea5  mov     edx, 188h; void *
0x180015eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015eaf  mov     r8, [rbp+57h+lpMem]; lpMem
0x180015eb3  lea     rax, [rbp+57h+var_20]
0x180015eb7  cmp     r8, rax
0x180015eba  jz      short loc_180015ECB
0x180015ebc  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180015ec3  xor     edx, edx; dwFlags
0x180015ec5  call    cs:__imp_HeapFree
0x180015ecb  mov     rcx, [rbp+57h+hKey]; hKey
0x180015ecf  test    rcx, rcx
0x180015ed2  jz      loc_1800160D2
0x180015ed8  call    cs:__imp_RegCloseKey
0x180015ede  jmp     loc_1800160D2
0x180015ee3  mov     rcx, [rbp+57h+hKey]; hKey
0x180015ee7  mov     [rbp+57h+hKey], rsi
0x180015eeb  test    rcx, rcx
0x180015eee  jz      short loc_180015EF6
0x180015ef0  call    cs:__imp_RegCloseKey
0x180015ef6  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x180015efa  lea     rax, [rbp+57h+dwDisposition]
0x180015efe  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x180015f03  mov     r14, 0FFFFFFFF80000002h
0x180015f0a  lea     rax, [rbp+57h+hKey]
0x180015f0e  mov     ebx, 1
0x180015f13  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180015f18  xor     r9d, r9d; lpClass
0x180015f1b  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180015f20  xor     r8d, r8d; Reserved
0x180015f23  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x180015f2b  mov     rcx, r14; hKey
0x180015f2e  mov     [rsp+0A0h+dwOptions], ebx; unsigned int
0x180015f32  call    cs:__imp_RegCreateKeyExW
0x180015f38  test    eax, eax
0x180015f3a  jz      short loc_180015F43
0x180015f3c  mov     edx, 192h
0x180015f41  jmp     short loc_180015F77
0x180015f43  cmp     [rbp+57h+dwDisposition], 2
0x180015f47  jnz     loc_180015FD7
0x180015f4d  mov     r8d, [rdi]; unsigned int
0x180015f50  mov     rdx, [rbp+57h+hKey]; HKEY
0x180015f54  call    ?KeyIsValidItem@TerminationStore@@AEAA_NPEAUHKEY__@@K@Z; TerminationStore::KeyIsValidItem(HKEY__ *,ulong)
0x180015f59  test    al, al
0x180015f5b  jnz     loc_1800160C0
0x180015f61  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x180015f65  mov     rcx, r14; hKey
0x180015f68  call    cs:__imp_RegDeleteKeyW
0x180015f6e  test    eax, eax
0x180015f70  jz      short loc_180015F91
0x180015f72  mov     edx, 19Eh; void *
0x180015f77  mov     rcx, [rbp+5Fh]; this
0x180015f7b  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x180015f82  mov     r9d, eax; char *
0x180015f85  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015f8a  mov     ebx, eax
0x180015f8c  jmp     loc_1800160C0
0x180015f91  lea     rcx, [rbp+57h+hKey]
0x180015f95  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180015f9a  lea     rdx, [rbp+57h+dwDisposition]
0x180015f9e  xor     r9d, r9d; lpClass
0x180015fa1  mov     [rsp+0A0h+lpdwDisposition], rdx; lpdwDisposition
0x180015fa6  xor     r8d, r8d; Reserved
0x180015fa9  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x180015fad  mov     rcx, r14; hKey
0x180015fb0  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180015fb5  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180015fba  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x180015fc2  mov     [rsp+0A0h+dwOptions], ebx; dwOptions
0x180015fc6  call    cs:__imp_RegCreateKeyExW
0x180015fcc  test    eax, eax
0x180015fce  jz      short loc_180015FD7
0x180015fd0  mov     edx, 1A8h
0x180015fd5  jmp     short loc_180015F77
0x180015fd7  lea     rcx, [rdi+4]
0x180015fdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015fdf  inc     rax
0x180015fe2  cmp     [rcx+rax*2], si
0x180015fe6  jnz     short loc_180015FDF
0x180015fe8  lea     eax, ds:2[rax*2]
0x180015fef  mov     r9d, ebx; dwType
0x180015ff2  mov     [rsp+0A0h+samDesired], eax; cbData
0x180015ff6  lea     rdx, ValueName; "Terminator"
0x180015ffd  mov     qword ptr [rsp+0A0h+dwOptions], rcx; lpData
0x180016002  xor     r8d, r8d; Reserved
0x180016005  mov     rcx, [rbp+57h+hKey]; hKey
0x180016009  call    cs:__imp_RegSetValueExW
0x18001600f  test    eax, eax
0x180016011  jz      short loc_18001601D
0x180016013  mov     edx, 1B0h
0x180016018  jmp     loc_180015F77
0x18001601d  mov     rcx, [rbp+57h+hKey]; hKey
0x180016021  lea     rax, [rdi+84h]
0x180016028  mov     r9d, 4; dwType
0x18001602e  lea     rdx, aReason_0; "Reason"
0x180016035  mov     [rsp+0A0h+samDesired], r9d; cbData
0x18001603a  xor     r8d, r8d; Reserved
0x18001603d  mov     qword ptr [rsp+0A0h+dwOptions], rax; unsigned int
0x180016042  call    cs:__imp_RegSetValueExW
0x180016048  test    eax, eax
0x18001604a  jz      short loc_18001606B
0x18001604c  mov     rcx, [rbp+5Fh]; this
0x180016050  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x180016057  mov     r9d, eax; char *
0x18001605a  mov     edx, 1B7h; void *
0x18001605f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016064  mov     ebx, eax
0x180016066  jmp     loc_180015EAF
0x18001606b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001606f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180016073  mov     qword ptr [rbp+57h+Data], rsi
0x180016077  call    cs:__imp_GetSystemTimeAsFileTime
0x18001607d  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180016081  lea     rdx, aCreationtime; "CreationTime"
0x180016088  mov     rcx, [rbp+57h+hKey]; hKey
0x18001608c  mov     r9d, 0Bh; dwType
0x180016092  mov     qword ptr [rbp+57h+Data], rax
0x180016096  xor     r8d, r8d; Reserved
0x180016099  lea     rax, [rbp+57h+Data]
0x18001609d  mov     [rsp+0A0h+samDesired], 8; cbData
0x1800160a5  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x1800160aa  call    cs:__imp_RegSetValueExW
0x1800160b0  test    eax, eax
0x1800160b2  jz      short loc_1800160BE
0x1800160b4  mov     edx, 1C5h
0x1800160b9  jmp     loc_180015F77
0x1800160be  mov     ebx, esi
0x1800160c0  lea     rcx, [rbp+57h+lpMem]; void *
0x1800160c4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800160c9  lea     rcx, [rbp+57h+hKey]
0x1800160cd  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800160d2  lea     r11, [rsp+0A0h+var_10]
0x1800160da  mov     eax, ebx
0x1800160dc  mov     rbx, [r11+20h]
0x1800160e0  mov     rsi, [r11+30h]
0x1800160e4  mov     rsp, r11
0x1800160e7  pop     r14
0x1800160e9  pop     rdi
0x1800160ea  pop     rbp
0x1800160eb  retn
```
