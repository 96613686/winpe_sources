# CTpUtils::GetCommercialId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800426e0`
- end: `0x180042910`
- name: `?GetCommercialId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800222c4`

## callees

- `0x180008174`
- `0x180009b40`
- `0x180009bb4`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000c390`
- `0x18001f8c8`
- `0x1800426e0`
- `0x180042918`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042869`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800428f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042869`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800428f3`
- `ntdll!wcsnlen` at `0x180042821`
- `ntdll!wcsnlen` at `0x180042821`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004279e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800427fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004279e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800427fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042878`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004275c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004275c`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x18004288f`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x18004288f`

## string_xrefs

- `0x18004276e`: `CommercialId`
- `0x1800427e0`: `CommercialId`
- `0x18004289a`: `CommercialId`

## pseudocode

```c
__int64 __fastcall CTpUtils::GetCommercialId(__int64 a1)
{
  signed int String; // ebx
  HKEY *phkResult; // rax
  HKEY v4; // rbx
  LSTATUS ValueW; // eax
  _BYTE *v6; // rdx
  _BYTE *v7; // r8
  const WCHAR *LocalAllowTelemetryRegPath; // rax
  PVOID lpMem[2]; // [rsp+40h] [rbp-40h] BYREF
  char v11; // [rsp+50h] [rbp-30h] BYREF
  LPVOID v12; // [rsp+60h] [rbp-20h] BYREF
  _BYTE *v13; // [rsp+68h] [rbp-18h]
  char v14; // [rsp+70h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+20h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v12);
  pcbData = 0;
  hkey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpMem) )
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
    wcsnlen((const wchar_t *)lpMem[0], (unsigned __int64)pcbData >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpMem);
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
  if ( String < 0 || (v6 = v12, v7 = v13, v12 == v13) )
  {
    LocalAllowTelemetryRegPath = (const WCHAR *)TelGetLocalAllowTelemetryRegPath();
    String = UtilRegGetString(HKEY_LOCAL_MACHINE, LocalAllowTelemetryRegPath, L"CommercialId", (__int64)&v12, 1, 1);
    if ( String < 0 )
      goto LABEL_21;
    v7 = v13;
    v6 = v12;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, v6, (v7 - v6) >> 1);
LABEL_21:
  if ( v12 != &v14 )
    HeapFree(g_hWerheap, 0, v12);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800426e0  mov     [rsp-8+arg_0], rbx
0x1800426e5  mov     [rsp-8+arg_18], rdi
0x1800426ea  push    rbp
0x1800426eb  mov     rbp, rsp
0x1800426ee  sub     rsp, 80h
0x1800426f5  mov     rdi, rcx
0x1800426f8  lea     rcx, [rbp+var_20]; void *
0x1800426fc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180042701  lea     rcx, [rbp+lpMem]; void *
0x180042705  mov     [rbp+arg_8], 0
0x18004270c  mov     [rbp+hkey], 0
0x180042714  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180042719  lea     rdx, Src
0x180042720  lea     rcx, [rbp+lpMem]
0x180042724  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180042729  test    al, al
0x18004272b  jnz     short loc_180042737
0x18004272d  mov     ebx, 8007000Eh
0x180042732  jmp     loc_180042846
0x180042737  lea     rcx, [rbp+hkey]
0x18004273b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180042740  mov     r9d, 101h; samDesired
0x180042746  mov     [rsp+80h+phkResult], rax; phkResult
0x18004274b  xor     r8d, r8d; ulOptions
0x18004274e  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180042755  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004275c  call    cs:__imp_RegOpenKeyExW
0x180042762  test    eax, eax
0x180042764  jnz     loc_180042833
0x18004276a  mov     rbx, [rbp+hkey]
0x18004276e  lea     r8, aCommercialid_0; "CommercialId"
0x180042775  mov     [rbp+arg_8], eax
0x180042778  mov     r9d, 2; dwFlags
0x18004277e  lea     rax, [rbp+arg_8]
0x180042782  xor     edx, edx; lpSubKey
0x180042784  mov     [rsp+80h+pcbData], rax; pcbData
0x180042789  mov     rcx, rbx; hkey
0x18004278c  mov     [rsp+80h+pvData], 0; pvData
0x180042795  mov     [rsp+80h+phkResult], 0; pdwType
0x18004279e  call    cs:__imp_RegGetValueW
0x1800427a4  test    eax, eax
0x1800427a6  jnz     loc_180042833
0x1800427ac  mov     rcx, [rbp+lpMem]
0x1800427b0  mov     [rbp+var_38], rcx
0x1800427b4  mov     [rcx], ax
0x1800427b7  lea     rcx, [rbp+lpMem]
0x1800427bb  mov     edx, [rbp+arg_8]
0x1800427be  shr     rdx, 1
0x1800427c1  inc     rdx
0x1800427c4  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800427c9  test    al, al
0x1800427cb  jz      loc_18004272D
0x1800427d1  lea     rax, [rbp+arg_8]
0x1800427d5  mov     r9d, 2; dwFlags
0x1800427db  mov     [rsp+80h+pcbData], rax; pcbData
0x1800427e0  lea     r8, aCommercialid_0; "CommercialId"
0x1800427e7  mov     rax, [rbp+lpMem]
0x1800427eb  xor     edx, edx; lpSubKey
0x1800427ed  mov     [rsp+80h+pvData], rax; pvData
0x1800427f2  mov     rcx, rbx; hkey
0x1800427f5  mov     [rsp+80h+phkResult], 0; pdwType
0x1800427fe  call    cs:__imp_RegGetValueW
0x180042804  mov     ebx, eax
0x180042806  test    eax, eax
0x180042808  jz      short loc_180042817
0x18004280a  jle     short loc_180042846
0x18004280c  movzx   ebx, ax
0x18004280f  or      ebx, 80070000h
0x180042815  jmp     short loc_180042846
0x180042817  mov     edx, [rbp+arg_8]
0x18004281a  mov     rcx, [rbp+lpMem]; Source
0x18004281e  shr     rdx, 1; MaxCount
0x180042821  call    cs:__imp_wcsnlen
0x180042827  mov     rdx, rax
0x18004282a  lea     rcx, [rbp+lpMem]
0x18004282e  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180042833  mov     rcx, [rbp+lpMem]; lpSrc
0x180042837  lea     rdx, [rbp+var_20]
0x18004283b  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180042840  mov     ebx, eax
0x180042842  test    eax, eax
0x180042844  jz      short loc_180042853
0x180042846  mov     rcx, [rbp+var_20]
0x18004284a  xor     eax, eax
0x18004284c  mov     [rbp+var_18], rcx
0x180042850  mov     [rcx], ax
0x180042853  mov     r8, [rbp+lpMem]; lpMem
0x180042857  lea     rax, [rbp+var_30]
0x18004285b  cmp     r8, rax
0x18004285e  jz      short loc_18004286F
0x180042860  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180042867  xor     edx, edx; dwFlags
0x180042869  call    cs:__imp_HeapFree
0x18004286f  mov     rcx, [rbp+hkey]; hKey
0x180042873  test    rcx, rcx
0x180042876  jz      short loc_18004287E
0x180042878  call    cs:__imp_RegCloseKey
0x18004287e  test    ebx, ebx
0x180042880  js      short loc_18004288F
0x180042882  mov     rdx, [rbp+var_20]
0x180042886  mov     r8, [rbp+var_18]
0x18004288a  cmp     rdx, r8
0x18004288d  jnz     short loc_1800428CF
0x18004288f  call    cs:__imp_TelGetLocalAllowTelemetryRegPath
0x180042895  mov     byte ptr [rsp+80h+pcbData], 1; char
0x18004289a  lea     r8, aCommercialid_0; "CommercialId"
0x1800428a1  mov     rdx, rax; lpSubKey
0x1800428a4  mov     byte ptr [rsp+80h+pvData], 1; char
0x1800428a9  lea     rax, [rbp+var_20]
0x1800428ad  xor     r9d, r9d
0x1800428b0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800428b7  mov     [rsp+80h+phkResult], rax; __int64
0x1800428bc  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800428c1  mov     ebx, eax
0x1800428c3  test    eax, eax
0x1800428c5  js      short loc_1800428DD
0x1800428c7  mov     r8, [rbp+var_18]
0x1800428cb  mov     rdx, [rbp+var_20]
0x1800428cf  sub     r8, rdx
0x1800428d2  mov     rcx, rdi
0x1800428d5  sar     r8, 1
0x1800428d8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800428dd  mov     r8, [rbp+var_20]; lpMem
0x1800428e1  lea     rax, [rbp+var_10]
0x1800428e5  cmp     r8, rax
0x1800428e8  jz      short loc_1800428F9
0x1800428ea  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800428f1  xor     edx, edx; dwFlags
0x1800428f3  call    cs:__imp_HeapFree
0x1800428f9  lea     r11, [rsp+80h+var_s0]
0x180042901  mov     eax, ebx
0x180042903  mov     rbx, [r11+10h]
0x180042907  mov     rdi, [r11+28h]
0x18004290b  mov     rsp, r11
0x18004290e  pop     rbp
0x18004290f  retn
```
