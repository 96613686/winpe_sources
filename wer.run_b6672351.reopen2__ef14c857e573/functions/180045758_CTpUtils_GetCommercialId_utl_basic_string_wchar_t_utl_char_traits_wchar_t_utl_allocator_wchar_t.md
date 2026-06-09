# CTpUtils::GetCommercialId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180045758`
- end: `0x1800459b9`
- name: `?GetCommercialId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022e44`

## callees

- `0x180008e38`
- `0x18000add4`
- `0x18000ae48`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000da00`
- `0x1800201f0`
- `0x180045758`
- `0x1800459c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045995`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045995`
- `ntdll!wcsnlen` at `0x1800458ab`
- `ntdll!wcsnlen` at `0x1800458ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004581c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045882`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004581c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004590e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004590e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800457d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800457d4`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x18004592b`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x18004592b`

## string_xrefs

- `0x1800457ec`: `CommercialId`
- `0x180045864`: `CommercialId`
- `0x18004593c`: `CommercialId`

## pseudocode

```c
__int64 __fastcall CTpUtils::GetCommercialId(void *a1)
{
  signed int String; // ebx
  HKEY *phkResult; // rax
  HKEY v4; // rbx
  LSTATUS ValueW; // eax
  size_t v6; // rax
  void *v7; // rdx
  const WCHAR *LocalAllowTelemetryRegPath; // rax
  PVOID lpMem[2]; // [rsp+40h] [rbp-40h] BYREF
  char v11; // [rsp+50h] [rbp-30h] BYREF
  LPVOID v12; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v13; // [rsp+68h] [rbp-18h]
  char v14; // [rsp+70h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+20h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v12);
  pcbData = 0;
  hkey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpMem,
                           (void *)&Src) )
    goto LABEL_2;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\DataCollection",
         0,
         0x101u,
         phkResult)
    || (v4 = hkey, pcbData = 0, RegGetValueW(hkey, 0, L"CommercialId", 2u, 0, 0, &pcbData)) )
  {
LABEL_10:
    String = UtilExpandEnvironmentStrings((LPCWSTR)lpMem[0]);
    if ( !String )
      goto LABEL_12;
    goto LABEL_11;
  }
  lpMem[1] = lpMem[0];
  *(_WORD *)lpMem[0] = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          lpMem,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v4, 0, L"CommercialId", 2u, 0, lpMem[0], &pcbData);
    String = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        String = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_11;
    }
    v6 = wcsnlen((const wchar_t *)lpMem[0], (unsigned __int64)pcbData >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpMem, v6);
    goto LABEL_10;
  }
LABEL_2:
  String = -2147024882;
LABEL_11:
  v13 = v12;
  *(_WORD *)v12 = 0;
LABEL_12:
  if ( lpMem[0] != &v11 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( hkey )
    RegCloseKey(hkey);
  if ( String < 0 || (v7 = v12, v12 == v13) )
  {
    LocalAllowTelemetryRegPath = (const WCHAR *)TelGetLocalAllowTelemetryRegPath();
    String = UtilRegGetString(HKEY_LOCAL_MACHINE, LocalAllowTelemetryRegPath, L"CommercialId", (__int64)&v12, 1, 1);
    if ( String < 0 )
      goto LABEL_21;
    v7 = v12;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, v7);
LABEL_21:
  if ( v12 != &v14 )
    HeapFree(g_hWerheap, 0, v12);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180045758  mov     [rsp-8+arg_0], rbx
0x18004575d  mov     [rsp-8+arg_18], rdi
0x180045762  push    rbp
0x180045763  mov     rbp, rsp
0x180045766  sub     rsp, 80h
0x18004576d  mov     rdi, rcx
0x180045770  lea     rcx, [rbp+var_20]; void *
0x180045774  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180045779  lea     rcx, [rbp+lpMem]; void *
0x18004577d  mov     [rbp+arg_8], 0
0x180045784  mov     [rbp+hkey], 0
0x18004578c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180045791  lea     rdx, Src
0x180045798  lea     rcx, [rbp+lpMem]
0x18004579c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800457a1  test    al, al
0x1800457a3  jnz     short loc_1800457AF
0x1800457a5  mov     ebx, 8007000Eh
0x1800457aa  jmp     loc_1800458D6
0x1800457af  lea     rcx, [rbp+hkey]
0x1800457b3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800457b8  mov     r9d, 101h; samDesired
0x1800457be  mov     [rsp+80h+phkResult], rax; phkResult
0x1800457c3  xor     r8d, r8d; ulOptions
0x1800457c6  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800457cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800457d4  call    cs:__imp_RegOpenKeyExW
0x1800457db  nop     dword ptr [rax+rax+00h]
0x1800457e0  test    eax, eax
0x1800457e2  jnz     loc_1800458C3
0x1800457e8  mov     rbx, [rbp+hkey]
0x1800457ec  lea     r8, aCommercialid_0; "CommercialId"
0x1800457f3  mov     [rbp+arg_8], eax
0x1800457f6  mov     r9d, 2; dwFlags
0x1800457fc  lea     rax, [rbp+arg_8]
0x180045800  xor     edx, edx; lpSubKey
0x180045802  mov     [rsp+80h+pcbData], rax; pcbData
0x180045807  mov     rcx, rbx; hkey
0x18004580a  mov     [rsp+80h+pvData], 0; pvData
0x180045813  mov     [rsp+80h+phkResult], 0; pdwType
0x18004581c  call    cs:__imp_RegGetValueW
0x180045823  nop     dword ptr [rax+rax+00h]
0x180045828  test    eax, eax
0x18004582a  jnz     loc_1800458C3
0x180045830  mov     rcx, [rbp+lpMem]
0x180045834  mov     [rbp+var_38], rcx
0x180045838  mov     [rcx], ax
0x18004583b  lea     rcx, [rbp+lpMem]
0x18004583f  mov     edx, [rbp+arg_8]
0x180045842  shr     rdx, 1
0x180045845  inc     rdx
0x180045848  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18004584d  test    al, al
0x18004584f  jz      loc_1800457A5
0x180045855  lea     rax, [rbp+arg_8]
0x180045859  mov     r9d, 2; dwFlags
0x18004585f  mov     [rsp+80h+pcbData], rax; pcbData
0x180045864  lea     r8, aCommercialid_0; "CommercialId"
0x18004586b  mov     rax, [rbp+lpMem]
0x18004586f  xor     edx, edx; lpSubKey
0x180045871  mov     [rsp+80h+pvData], rax; pvData
0x180045876  mov     rcx, rbx; hkey
0x180045879  mov     [rsp+80h+phkResult], 0; pdwType
0x180045882  call    cs:__imp_RegGetValueW
0x180045889  nop     dword ptr [rax+rax+00h]
0x18004588e  mov     ebx, eax
0x180045890  test    eax, eax
0x180045892  jz      short loc_1800458A1
0x180045894  jle     short loc_1800458D6
0x180045896  movzx   ebx, ax
0x180045899  or      ebx, 80070000h
0x18004589f  jmp     short loc_1800458D6
0x1800458a1  mov     edx, [rbp+arg_8]
0x1800458a4  mov     rcx, [rbp+lpMem]; Source
0x1800458a8  shr     rdx, 1; MaxCount
0x1800458ab  call    cs:__imp_wcsnlen
0x1800458b2  nop     dword ptr [rax+rax+00h]
0x1800458b7  mov     rdx, rax
0x1800458ba  lea     rcx, [rbp+lpMem]
0x1800458be  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x1800458c3  mov     rcx, [rbp+lpMem]; lpSrc
0x1800458c7  lea     rdx, [rbp+var_20]
0x1800458cb  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800458d0  mov     ebx, eax
0x1800458d2  test    eax, eax
0x1800458d4  jz      short loc_1800458E3
0x1800458d6  mov     rcx, [rbp+var_20]
0x1800458da  xor     eax, eax
0x1800458dc  mov     [rbp+var_18], rcx
0x1800458e0  mov     [rcx], ax
0x1800458e3  mov     r8, [rbp+lpMem]; lpMem
0x1800458e7  lea     rax, [rbp+var_30]
0x1800458eb  cmp     r8, rax
0x1800458ee  jz      short loc_180045905
0x1800458f0  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800458f7  xor     edx, edx; dwFlags
0x1800458f9  call    cs:__imp_HeapFree
0x180045900  nop     dword ptr [rax+rax+00h]
0x180045905  mov     rcx, [rbp+hkey]; hKey
0x180045909  test    rcx, rcx
0x18004590c  jz      short loc_18004591A
0x18004590e  call    cs:__imp_RegCloseKey
0x180045915  nop     dword ptr [rax+rax+00h]
0x18004591a  test    ebx, ebx
0x18004591c  js      short loc_18004592B
0x18004591e  mov     rdx, [rbp+var_20]
0x180045922  mov     r8, [rbp+var_18]
0x180045926  cmp     rdx, r8
0x180045929  jnz     short loc_180045971
0x18004592b  call    cs:__imp_TelGetLocalAllowTelemetryRegPath
0x180045932  nop     dword ptr [rax+rax+00h]
0x180045937  mov     byte ptr [rsp+80h+pcbData], 1; char
0x18004593c  lea     r8, aCommercialid_0; "CommercialId"
0x180045943  mov     rdx, rax; lpSubKey
0x180045946  mov     byte ptr [rsp+80h+pvData], 1; char
0x18004594b  lea     rax, [rbp+var_20]
0x18004594f  xor     r9d, r9d
0x180045952  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180045959  mov     [rsp+80h+phkResult], rax; __int64
0x18004595e  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180045963  mov     ebx, eax
0x180045965  test    eax, eax
0x180045967  js      short loc_18004597F
0x180045969  mov     r8, [rbp+var_18]
0x18004596d  mov     rdx, [rbp+var_20]
0x180045971  sub     r8, rdx
0x180045974  mov     rcx, rdi
0x180045977  sar     r8, 1
0x18004597a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18004597f  mov     r8, [rbp+var_20]; lpMem
0x180045983  lea     rax, [rbp+var_10]
0x180045987  cmp     r8, rax
0x18004598a  jz      short loc_1800459A1
0x18004598c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180045993  xor     edx, edx; dwFlags
0x180045995  call    cs:__imp_HeapFree
0x18004599c  nop     dword ptr [rax+rax+00h]
0x1800459a1  lea     r11, [rsp+80h+var_s0]
0x1800459a9  mov     eax, ebx
0x1800459ab  mov     rbx, [r11+10h]
0x1800459af  mov     rdi, [r11+28h]
0x1800459b3  mov     rsp, r11
0x1800459b6  pop     rbp
0x1800459b7  retn
```
