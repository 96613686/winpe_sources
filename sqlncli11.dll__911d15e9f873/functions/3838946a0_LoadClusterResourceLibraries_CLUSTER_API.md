# LoadClusterResourceLibraries(CLUSTER_API *)

- ea: `0x3838946a0`
- end: `0x3838948de`
- name: `?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z`
- size: `574`
- prototype: `unsigned int __fastcall(struct CLUSTER_API *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x383894630`

## callees

- `0x383846430`
- `0x383892180`
- `0x3838946a0`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x3838f5719`
- `KERNEL32!FreeLibrary` at `0x3838f572f`
- `KERNEL32!FreeLibrary` at `0x3838f5745`
- `KERNEL32!FreeLibrary` at `0x3838f5719`
- `KERNEL32!FreeLibrary` at `0x3838f572f`
- `KERNEL32!FreeLibrary` at `0x3838f5745`
- `KERNEL32!GetLastError` at `0x3838f5709`
- `KERNEL32!GetLastError` at `0x3838f5709`
- `KERNEL32!GetProcAddress` at `0x3838946fd`
- `KERNEL32!GetProcAddress` at `0x38389471a`
- `KERNEL32!GetProcAddress` at `0x383894737`
- `KERNEL32!GetProcAddress` at `0x383894754`
- `KERNEL32!GetProcAddress` at `0x383894771`
- `KERNEL32!GetProcAddress` at `0x38389478e`
- `KERNEL32!GetProcAddress` at `0x3838947ab`
- `KERNEL32!GetProcAddress` at `0x3838947c8`
- `KERNEL32!GetProcAddress` at `0x3838947e5`
- `KERNEL32!GetProcAddress` at `0x383894802`
- `KERNEL32!GetProcAddress` at `0x38389481f`
- `KERNEL32!GetProcAddress` at `0x38389483c`
- `KERNEL32!GetProcAddress` at `0x383894874`
- `KERNEL32!GetProcAddress` at `0x383894891`
- `KERNEL32!GetProcAddress` at `0x3838946fd`
- `KERNEL32!GetProcAddress` at `0x38389471a`
- `KERNEL32!GetProcAddress` at `0x383894737`
- `KERNEL32!GetProcAddress` at `0x383894754`
- `KERNEL32!GetProcAddress` at `0x383894771`
- `KERNEL32!GetProcAddress` at `0x38389478e`
- `KERNEL32!GetProcAddress` at `0x3838947ab`
- `KERNEL32!GetProcAddress` at `0x3838947c8`
- `KERNEL32!GetProcAddress` at `0x3838947e5`
- `KERNEL32!GetProcAddress` at `0x383894802`
- `KERNEL32!GetProcAddress` at `0x38389481f`
- `KERNEL32!GetProcAddress` at `0x38389483c`
- `KERNEL32!GetProcAddress` at `0x383894874`
- `KERNEL32!GetProcAddress` at `0x383894891`

## string_xrefs

- `0x3838946db`: `CLUSAPI.DLL`
- `0x3838946f3`: `OpenCluster`
- `0x38389472d`: `OpenClusterResource`
- `0x383894767`: `ClusterOpenEnum`
- `0x3838947be`: `ClusterResourceOpenEnum`
- `0x383894852`: `RESUTILS.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadClusterResourceLibraries(struct CLUSTER_API *a1)
{
  HMODULE v2; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  HMODULE v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  DWORD LastError; // esi
  HMODULE v21; // rcx
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-28h]
  __int64 v24; // [rsp+58h] [rbp+10h] BYREF

  v24 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48600[0] )
    bidScopeEnterA(&v24, off_383B48600[0], a1);
  v2 = SNILoadSystemLibA("CLUSAPI.DLL");
  v3 = v2;
  if ( !v2 )
    goto LABEL_28;
  ProcAddress = GetProcAddress(v2, "OpenCluster");
  *((_QWORD *)a1 + 1) = ProcAddress;
  if ( !ProcAddress )
    goto LABEL_28;
  v5 = GetProcAddress(v3, "CloseCluster");
  *((_QWORD *)a1 + 2) = v5;
  if ( !v5 )
    goto LABEL_28;
  v6 = GetProcAddress(v3, "OpenClusterResource");
  *((_QWORD *)a1 + 3) = v6;
  if ( !v6 )
    goto LABEL_28;
  v7 = GetProcAddress(v3, "CloseClusterResource");
  *((_QWORD *)a1 + 4) = v7;
  if ( !v7 )
    goto LABEL_28;
  v8 = GetProcAddress(v3, "ClusterOpenEnum");
  *((_QWORD *)a1 + 5) = v8;
  if ( !v8 )
    goto LABEL_28;
  v9 = GetProcAddress(v3, "ClusterEnum");
  *((_QWORD *)a1 + 6) = v9;
  if ( !v9 )
    goto LABEL_28;
  v10 = GetProcAddress(v3, "ClusterCloseEnum");
  *((_QWORD *)a1 + 7) = v10;
  if ( !v10 )
    goto LABEL_28;
  v11 = GetProcAddress(v3, "ClusterResourceOpenEnum");
  *((_QWORD *)a1 + 8) = v11;
  if ( !v11 )
    goto LABEL_28;
  v12 = GetProcAddress(v3, "ClusterResourceEnum");
  *((_QWORD *)a1 + 9) = v12;
  if ( !v12 )
    goto LABEL_28;
  v13 = GetProcAddress(v3, "ClusterResourceCloseEnum");
  *((_QWORD *)a1 + 10) = v13;
  if ( !v13 )
    goto LABEL_28;
  v14 = GetProcAddress(v3, "ClusterResourceControl");
  *((_QWORD *)a1 + 11) = v14;
  if ( !v14 )
    goto LABEL_28;
  v15 = GetProcAddress(v3, "GetClusterResourceState");
  *((_QWORD *)a1 + 12) = v15;
  if ( !v15 )
    goto LABEL_28;
  *(_QWORD *)a1 = v3;
  v16 = SNILoadSystemLibA("RESUTILS.DLL");
  v3 = v16;
  if ( v16
    && (v17 = GetProcAddress(v16, "ResUtilFindSzProperty"), (*((_QWORD *)a1 + 14) = v17) != 0)
    && (v18 = GetProcAddress(v3, "ResUtilResourceTypesEqual"), (*((_QWORD *)a1 + 15) = v18) != 0) )
  {
    *((_QWORD *)a1 + 13) = v3;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B462D8[0] )
      bidTraceA(off_383B43C58[0], 183296, off_383B462D8[0], 0, v23);
    if ( v24 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 0;
  }
  else
  {
LABEL_28:
    LastError = GetLastError();
    if ( *(_QWORD *)a1 )
    {
      FreeLibrary(*(HMODULE *)a1);
      *(_QWORD *)a1 = 0;
    }
    v21 = (HMODULE)*((_QWORD *)a1 + 13);
    if ( v21 )
    {
      FreeLibrary(v21);
      *((_QWORD *)a1 + 13) = 0;
    }
    if ( v3 )
      FreeLibrary(v3);
    if ( (bidGblFlags & 2) != 0 && off_383B462D0[0] )
    {
      v22 = SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B43C50[0], 212992, off_383B462D0[0], 7, v22);
    }
    SNISetLastError(7, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B462C8[0] )
      bidTraceA(off_383B43C48[0], 215040, off_383B462C8[0], LastError, v23);
    if ( v24 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return LastError;
  }
}

```

## disassembly

```asm
0x3838946a0  push    rdi
0x3838946a2  sub     rsp, 40h
0x3838946a6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x3838946af  mov     [rsp+48h+arg_0], rbx
0x3838946b4  mov     [rsp+48h+arg_10], rsi
0x3838946b9  mov     rdi, rcx
0x3838946bc  mov     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x3838946c5  mov     eax, cs:_bidGblFlags
0x3838946cb  and     eax, 20004h
0x3838946d0  cmp     eax, 20004h
0x3838946d5  jz      loc_3838F567A
0x3838946db  lea     rcx, aClusapiDll; "CLUSAPI.DLL"
0x3838946e2  call    SNILoadSystemLibA
0x3838946e7  mov     rbx, rax
0x3838946ea  test    rax, rax
0x3838946ed  jz      loc_3838F5709
0x3838946f3  lea     rdx, aOpencluster; "OpenCluster"
0x3838946fa  mov     rcx, rax; hModule
0x3838946fd  call    cs:__imp_GetProcAddress
0x383894703  mov     [rdi+8], rax
0x383894707  test    rax, rax
0x38389470a  jz      loc_3838F5709
0x383894710  lea     rdx, aClosecluster; "CloseCluster"
0x383894717  mov     rcx, rbx; hModule
0x38389471a  call    cs:__imp_GetProcAddress
0x383894720  mov     [rdi+10h], rax
0x383894724  test    rax, rax
0x383894727  jz      loc_3838F5709
0x38389472d  lea     rdx, aOpenclusterres; "OpenClusterResource"
0x383894734  mov     rcx, rbx; hModule
0x383894737  call    cs:__imp_GetProcAddress
0x38389473d  mov     [rdi+18h], rax
0x383894741  test    rax, rax
0x383894744  jz      loc_3838F5709
0x38389474a  lea     rdx, aCloseclusterre; "CloseClusterResource"
0x383894751  mov     rcx, rbx; hModule
0x383894754  call    cs:__imp_GetProcAddress
0x38389475a  mov     [rdi+20h], rax
0x38389475e  test    rax, rax
0x383894761  jz      loc_3838F5709
0x383894767  lea     rdx, aClusteropenenu; "ClusterOpenEnum"
0x38389476e  mov     rcx, rbx; hModule
0x383894771  call    cs:__imp_GetProcAddress
0x383894777  mov     [rdi+28h], rax
0x38389477b  test    rax, rax
0x38389477e  jz      loc_3838F5709
0x383894784  lea     rdx, aClusterenum; "ClusterEnum"
0x38389478b  mov     rcx, rbx; hModule
0x38389478e  call    cs:__imp_GetProcAddress
0x383894794  mov     [rdi+30h], rax
0x383894798  test    rax, rax
0x38389479b  jz      loc_3838F5709
0x3838947a1  lea     rdx, aClustercloseen; "ClusterCloseEnum"
0x3838947a8  mov     rcx, rbx; hModule
0x3838947ab  call    cs:__imp_GetProcAddress
0x3838947b1  mov     [rdi+38h], rax
0x3838947b5  test    rax, rax
0x3838947b8  jz      loc_3838F5709
0x3838947be  lea     rdx, aClusterresourc_2; "ClusterResourceOpenEnum"
0x3838947c5  mov     rcx, rbx; hModule
0x3838947c8  call    cs:__imp_GetProcAddress
0x3838947ce  mov     [rdi+40h], rax
0x3838947d2  test    rax, rax
0x3838947d5  jz      loc_3838F5709
0x3838947db  lea     rdx, aClusterresourc_1; "ClusterResourceEnum"
0x3838947e2  mov     rcx, rbx; hModule
0x3838947e5  call    cs:__imp_GetProcAddress
0x3838947eb  mov     [rdi+48h], rax
0x3838947ef  test    rax, rax
0x3838947f2  jz      loc_3838F5709
0x3838947f8  lea     rdx, aClusterresourc_0; "ClusterResourceCloseEnum"
0x3838947ff  mov     rcx, rbx; hModule
0x383894802  call    cs:__imp_GetProcAddress
0x383894808  mov     [rdi+50h], rax
0x38389480c  test    rax, rax
0x38389480f  jz      loc_3838F5709
0x383894815  lea     rdx, aClusterresourc; "ClusterResourceControl"
0x38389481c  mov     rcx, rbx; hModule
0x38389481f  call    cs:__imp_GetProcAddress
0x383894825  mov     [rdi+58h], rax
0x383894829  test    rax, rax
0x38389482c  jz      loc_3838F5709
0x383894832  lea     rdx, aGetclusterreso; "GetClusterResourceState"
0x383894839  mov     rcx, rbx; hModule
0x38389483c  call    cs:__imp_GetProcAddress
0x383894842  mov     [rdi+60h], rax
0x383894846  test    rax, rax
0x383894849  jz      loc_3838F5709
0x38389484f  mov     [rdi], rbx
0x383894852  lea     rcx, aResutilsDll; "RESUTILS.DLL"
0x383894859  call    SNILoadSystemLibA
0x38389485e  mov     rbx, rax
0x383894861  test    rax, rax
0x383894864  jz      loc_3838F5709
0x38389486a  lea     rdx, aResutilfindszp; "ResUtilFindSzProperty"
0x383894871  mov     rcx, rax; hModule
0x383894874  call    cs:__imp_GetProcAddress
0x38389487a  mov     [rdi+70h], rax
0x38389487e  test    rax, rax
0x383894881  jz      loc_3838F5709
0x383894887  lea     rdx, aResutilresourc; "ResUtilResourceTypesEqual"
0x38389488e  mov     rcx, rbx; hModule
0x383894891  call    cs:__imp_GetProcAddress
0x383894897  mov     [rdi+78h], rax
0x38389489b  test    rax, rax
0x38389489e  jz      loc_3838F5709
0x3838948a4  mov     [rdi+68h], rbx
0x3838948a8  mov     eax, cs:_bidGblFlags
0x3838948ae  and     eax, 20002h
0x3838948b3  cmp     eax, 20002h
0x3838948b8  jz      loc_3838F56A4
0x3838948be  cmp     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x3838948c4  jnz     loc_3838F56D5
0x3838948ca  xor     eax, eax
0x3838948cc  jmp     short $+2
0x3838948ce  mov     rbx, [rsp+48h+arg_0]
0x3838948d3  mov     rsi, [rsp+48h+arg_10]
0x3838948d8  add     rsp, 40h
0x3838948dc  pop     rdi
0x3838948dd  retn
0x3838f567a  mov     rax, cs:off_383B48600; "<LoadClusterResourceLibraries|API|SNI> "...
0x3838f5681  test    rax, rax
0x3838f5684  jz      loc_3838946DB
0x3838f568a  mov     r8, rcx
0x3838f568d  mov     rdx, cs:off_383B48600; "<LoadClusterResourceLibraries|API|SNI> "...
0x3838f5694  lea     rcx, [rsp+48h+arg_8]
0x3838f5699  call    _bidScopeEnterA
0x3838f569e  nop
0x3838f569f  jmp     loc_3838946DB
0x3838f56a4  mov     rax, cs:off_383B462D8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x3838f56ab  test    rax, rax
0x3838f56ae  jz      loc_3838948BE
0x3838f56b4  xor     r9d, r9d
0x3838f56b7  mov     r8, cs:off_383B462D8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x3838f56be  mov     edx, 2CC00h
0x3838f56c3  mov     rcx, cs:off_383B43C58; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f56ca  call    _bidTraceA
0x3838f56cf  nop
0x3838f56d0  jmp     loc_3838948BE
0x3838f56d5  test    byte ptr cs:_bidGblFlags, 4
0x3838f56dc  jz      loc_3838948CA
0x3838f56e2  mov     rcx, cs:_bidID
0x3838f56e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f56ed  jz      loc_3838948CA
0x3838f56f3  lea     r9, [rsp+48h+arg_8]
0x3838f56f8  xor     r8d, r8d
0x3838f56fb  xor     edx, edx
0x3838f56fd  call    cs:off_383B15058
0x3838f5703  nop
0x3838f5704  jmp     loc_3838948CA
0x3838f5709  call    cs:__imp_GetLastError
0x3838f570f  mov     esi, eax
0x3838f5711  mov     rcx, [rdi]; hLibModule
0x3838f5714  test    rcx, rcx
0x3838f5717  jz      short loc_3838F5726
0x3838f5719  call    cs:__imp_FreeLibrary
0x3838f571f  mov     qword ptr [rdi], 0
0x3838f5726  mov     rcx, [rdi+68h]; hLibModule
0x3838f572a  test    rcx, rcx
0x3838f572d  jz      short loc_3838F573D
0x3838f572f  call    cs:__imp_FreeLibrary
0x3838f5735  mov     qword ptr [rdi+68h], 0
0x3838f573d  test    rbx, rbx
0x3838f5740  jz      short loc_3838F574B
0x3838f5742  mov     rcx, rbx; hLibModule
0x3838f5745  call    cs:__imp_FreeLibrary
0x3838f574b  test    byte ptr cs:_bidGblFlags, 2
0x3838f5752  jz      short loc_3838F5790
0x3838f5754  mov     rax, cs:off_383B462D0; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x3838f575b  test    rax, rax
0x3838f575e  jz      short loc_3838F5790
0x3838f5760  mov     ecx, 0C3B4h; unsigned int
0x3838f5765  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838f576a  mov     [rsp+48h+var_20], esi
0x3838f576e  mov     [rsp+48h+var_28], eax
0x3838f5772  mov     r9d, 7
0x3838f5778  mov     r8, cs:off_383B462D0; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x3838f577f  mov     edx, 34000h
0x3838f5784  mov     rcx, cs:off_383B43C50; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f578b  call    _bidTraceA
0x3838f5790  mov     r8d, 0C3B4h
0x3838f5796  mov     edx, esi
0x3838f5798  mov     ecx, 7
0x3838f579d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838f57a2  mov     r11d, cs:_bidGblFlags
0x3838f57a9  and     r11d, 20002h
0x3838f57b0  cmp     r11d, 20002h
0x3838f57b7  jnz     short loc_3838F57E1
0x3838f57b9  mov     rax, cs:off_383B462C8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x3838f57c0  test    rax, rax
0x3838f57c3  jz      short loc_3838F57E1
0x3838f57c5  mov     r9d, esi
0x3838f57c8  mov     r8, cs:off_383B462C8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x3838f57cf  mov     edx, 34800h
0x3838f57d4  mov     rcx, cs:off_383B43C48; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f57db  call    _bidTraceA
0x3838f57e0  nop
0x3838f57e1  cmp     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x3838f57e7  jz      short loc_3838F580F
0x3838f57e9  test    byte ptr cs:_bidGblFlags, 4
0x3838f57f0  jz      short loc_3838F580F
0x3838f57f2  mov     rcx, cs:_bidID
0x3838f57f9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838f57fd  jz      short loc_3838F580F
0x3838f57ff  lea     r9, [rsp+48h+arg_8]
0x3838f5804  xor     r8d, r8d
0x3838f5807  xor     edx, edx
0x3838f5809  call    cs:off_383B15058
0x3838f580f  mov     eax, esi
0x3838f5811  jmp     loc_3838948CE
```
