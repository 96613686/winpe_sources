# TerminationStore::AddItem(TerminationItem)

- ea: `0x180019800`
- end: `0x180019ae1`
- name: `?AddItem@TerminationStore@@QEAAJUTerminationItem@@@Z`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800195f0`

## callees

- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180019800`
- `0x18001cb20`
- `0x1800201f0`
- `0x18003fb94`
- `0x180040814`
- `0x1800a0204`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001987d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001987d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019a5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800198fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001999c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800198fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001999c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800199e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800199e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198b4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180019938`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180019938`

## string_xrefs

- `0x180019853`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x180019951`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x180019a38`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

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
0x180019800  mov     [rsp-8+arg_0], rbx
0x180019805  mov     [rsp-8+arg_10], rsi
0x18001980a  push    rbp
0x18001980b  push    rdi
0x18001980c  push    r14
0x18001980e  lea     rbp, [rsp-47h]
0x180019813  sub     rsp, 90h
0x18001981a  xor     esi, esi
0x18001981c  lea     rcx, [rbp+57h+lpMem]; void *
0x180019820  mov     [rbp+57h+hKey], rsi
0x180019824  mov     rdi, rdx
0x180019827  mov     [rbp+57h+dwDisposition], esi
0x18001982a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001982f  mov     r9d, [rdi]
0x180019832  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\Windows E"...
0x180019839  lea     rdx, aLsU; "%ls\\%u"
0x180019840  lea     rcx, [rbp+57h+lpMem]
0x180019844  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180019849  mov     ebx, eax
0x18001984b  test    eax, eax
0x18001984d  jns     short loc_1800198A7
0x18001984f  mov     rcx, [rbp+5Fh]; this
0x180019853  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x18001985a  mov     r9d, eax; char *
0x18001985d  mov     edx, 188h; void *
0x180019862  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019867  mov     r8, [rbp+57h+lpMem]; lpMem
0x18001986b  lea     rax, [rbp+57h+var_20]
0x18001986f  cmp     r8, rax
0x180019872  jz      short loc_180019889
0x180019874  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001987b  xor     edx, edx; dwFlags
0x18001987d  call    cs:__imp_HeapFree
0x180019884  nop     dword ptr [rax+rax+00h]
0x180019889  mov     rcx, [rbp+57h+hKey]; hKey
0x18001988d  test    rcx, rcx
0x180019890  jz      loc_180019AC6
0x180019896  call    cs:__imp_RegCloseKey
0x18001989d  nop     dword ptr [rax+rax+00h]
0x1800198a2  jmp     loc_180019AC6
0x1800198a7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800198ab  mov     [rbp+57h+hKey], rsi
0x1800198af  test    rcx, rcx
0x1800198b2  jz      short loc_1800198C0
0x1800198b4  call    cs:__imp_RegCloseKey
0x1800198bb  nop     dword ptr [rax+rax+00h]
0x1800198c0  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x1800198c4  lea     rax, [rbp+57h+dwDisposition]
0x1800198c8  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x1800198cd  mov     r14, 0FFFFFFFF80000002h
0x1800198d4  lea     rax, [rbp+57h+hKey]
0x1800198d8  mov     ebx, 1
0x1800198dd  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800198e2  xor     r9d, r9d; lpClass
0x1800198e5  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800198ea  xor     r8d, r8d; Reserved
0x1800198ed  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x1800198f5  mov     rcx, r14; hKey
0x1800198f8  mov     [rsp+0A0h+dwOptions], ebx; unsigned int
0x1800198fc  call    cs:__imp_RegCreateKeyExW
0x180019903  nop     dword ptr [rax+rax+00h]
0x180019908  test    eax, eax
0x18001990a  jz      short loc_180019913
0x18001990c  mov     edx, 192h
0x180019911  jmp     short loc_18001994D
0x180019913  cmp     [rbp+57h+dwDisposition], 2
0x180019917  jnz     loc_1800199B3
0x18001991d  mov     r8d, [rdi]; unsigned int
0x180019920  mov     rdx, [rbp+57h+hKey]; HKEY
0x180019924  call    ?KeyIsValidItem@TerminationStore@@AEAA_NPEAUHKEY__@@K@Z; TerminationStore::KeyIsValidItem(HKEY__ *,ulong)
0x180019929  test    al, al
0x18001992b  jnz     loc_180019AB4
0x180019931  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x180019935  mov     rcx, r14; hKey
0x180019938  call    cs:__imp_RegDeleteKeyW
0x18001993f  nop     dword ptr [rax+rax+00h]
0x180019944  test    eax, eax
0x180019946  jz      short loc_180019967
0x180019948  mov     edx, 19Eh; void *
0x18001994d  mov     rcx, [rbp+5Fh]; this
0x180019951  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x180019958  mov     r9d, eax; char *
0x18001995b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019960  mov     ebx, eax
0x180019962  jmp     loc_180019AB4
0x180019967  lea     rcx, [rbp+57h+hKey]
0x18001996b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180019970  lea     rdx, [rbp+57h+dwDisposition]
0x180019974  xor     r9d, r9d; lpClass
0x180019977  mov     [rsp+0A0h+lpdwDisposition], rdx; lpdwDisposition
0x18001997c  xor     r8d, r8d; Reserved
0x18001997f  mov     rdx, [rbp+57h+lpMem]; lpSubKey
0x180019983  mov     rcx, r14; hKey
0x180019986  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18001998b  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180019990  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x180019998  mov     [rsp+0A0h+dwOptions], ebx; dwOptions
0x18001999c  call    cs:__imp_RegCreateKeyExW
0x1800199a3  nop     dword ptr [rax+rax+00h]
0x1800199a8  test    eax, eax
0x1800199aa  jz      short loc_1800199B3
0x1800199ac  mov     edx, 1A8h
0x1800199b1  jmp     short loc_18001994D
0x1800199b3  lea     rcx, [rdi+4]
0x1800199b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800199bb  inc     rax
0x1800199be  cmp     [rcx+rax*2], si
0x1800199c2  jnz     short loc_1800199BB
0x1800199c4  lea     eax, ds:2[rax*2]
0x1800199cb  mov     r9d, ebx; dwType
0x1800199ce  mov     [rsp+0A0h+samDesired], eax; cbData
0x1800199d2  lea     rdx, ValueName; "Terminator"
0x1800199d9  mov     qword ptr [rsp+0A0h+dwOptions], rcx; lpData
0x1800199de  xor     r8d, r8d; Reserved
0x1800199e1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800199e5  call    cs:__imp_RegSetValueExW
0x1800199ec  nop     dword ptr [rax+rax+00h]
0x1800199f1  test    eax, eax
0x1800199f3  jz      short loc_1800199FF
0x1800199f5  mov     edx, 1B0h
0x1800199fa  jmp     loc_18001994D
0x1800199ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180019a03  lea     rax, [rdi+84h]
0x180019a0a  mov     r9d, 4; dwType
0x180019a10  lea     rdx, aReason_0; "Reason"
0x180019a17  mov     [rsp+0A0h+samDesired], r9d; cbData
0x180019a1c  xor     r8d, r8d; Reserved
0x180019a1f  mov     qword ptr [rsp+0A0h+dwOptions], rax; unsigned int
0x180019a24  call    cs:__imp_RegSetValueExW
0x180019a2b  nop     dword ptr [rax+rax+00h]
0x180019a30  test    eax, eax
0x180019a32  jz      short loc_180019A53
0x180019a34  mov     rcx, [rbp+5Fh]; this
0x180019a38  lea     r8, aOnecoreWindows_8; "onecore\\windows\\feedback\\core\\commo"...
0x180019a3f  mov     r9d, eax; char *
0x180019a42  mov     edx, 1B7h; void *
0x180019a47  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019a4c  mov     ebx, eax
0x180019a4e  jmp     loc_180019867
0x180019a53  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019a57  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180019a5b  mov     qword ptr [rbp+57h+Data], rsi
0x180019a5f  call    cs:__imp_GetSystemTimeAsFileTime
0x180019a66  nop     dword ptr [rax+rax+00h]
0x180019a6b  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180019a6f  lea     rdx, aCreationtime; "CreationTime"
0x180019a76  mov     rcx, [rbp+57h+hKey]; hKey
0x180019a7a  mov     r9d, 0Bh; dwType
0x180019a80  mov     qword ptr [rbp+57h+Data], rax
0x180019a84  xor     r8d, r8d; Reserved
0x180019a87  lea     rax, [rbp+57h+Data]
0x180019a8b  mov     [rsp+0A0h+samDesired], 8; cbData
0x180019a93  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x180019a98  call    cs:__imp_RegSetValueExW
0x180019a9f  nop     dword ptr [rax+rax+00h]
0x180019aa4  test    eax, eax
0x180019aa6  jz      short loc_180019AB2
0x180019aa8  mov     edx, 1C5h
0x180019aad  jmp     loc_18001994D
0x180019ab2  mov     ebx, esi
0x180019ab4  lea     rcx, [rbp+57h+lpMem]; void *
0x180019ab8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180019abd  lea     rcx, [rbp+57h+hKey]
0x180019ac1  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180019ac6  lea     r11, [rsp+0A0h+var_10]
0x180019ace  mov     eax, ebx
0x180019ad0  mov     rbx, [r11+20h]
0x180019ad4  mov     rsi, [r11+30h]
0x180019ad8  mov     rsp, r11
0x180019adb  pop     r14
0x180019add  pop     rdi
0x180019ade  pop     rbp
0x180019adf  retn
```
