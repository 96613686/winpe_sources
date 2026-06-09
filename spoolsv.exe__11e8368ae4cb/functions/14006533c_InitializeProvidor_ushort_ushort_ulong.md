# InitializeProvidor(ushort *,ushort *,ulong *)

- ea: `0x14006533c`
- end: `0x1400655d1`
- name: `?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z`
- size: `661`
- prototype: `struct _PROVIDOR *__fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14005dfe4`
- `0x1400651d4`
- `0x140065710`

## callees

- `0x1400041c0`
- `0x14000a620`
- `0x14000ad50`
- `0x14000dd20`
- `0x14000e590`
- `0x1400140cc`
- `0x140014eb0`
- `0x140049660`
- `0x14005698c`
- `0x140056b18`
- `0x1400590f0`
- `0x14006533c`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140065373`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140065387`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006540d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140065373`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140065387`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006540d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400654dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400654dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400655b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400655b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006542a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006544a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006542a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006544a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400653bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400654ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006553a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400653bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400654ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006553a`
- `KERNEL32!FreeLibrary` at `0x140065595`
- `KERNEL32!FreeLibrary` at `0x140065595`
- `KERNEL32!LoadLibraryExW` at `0x14006543b`
- `KERNEL32!LoadLibraryExW` at `0x14006543b`

## string_xrefs

- `0x14006537d`: `win32spl.dll`
- `0x14006545e`: `LoadLibrary for '%ws' failed.  Error %d.`
- `0x140065369`: `localspl.dll`

## pseudocode

```c
struct _PROVIDOR *__fastcall InitializeProvidor(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3)
{
  int v6; // r15d
  HMODULE v7; // rbp
  __int64 v8; // rdi
  __int64 LastError; // rbx
  HANDLE v10; // r14
  __int64 v11; // rax
  unsigned int i; // ebx
  UINT v13; // ebx
  HMODULE Library; // rax
  struct SplLogType *v15; // rax
  __int64 v16; // r10
  const struct _EVENT_DESCRIPTOR *v17; // rcx
  FARPROC ProcAddress; // rax
  int v20; // [rsp+30h] [rbp-98h] BYREF
  __int64 v21; // [rsp+38h] [rbp-90h]
  int v22; // [rsp+40h] [rbp-88h]
  int v23; // [rsp+48h] [rbp-80h] BYREF
  __int64 v24; // [rsp+50h] [rbp-78h]
  int v25; // [rsp+58h] [rbp-70h]
  _BYTE v26[104]; // [rsp+60h] [rbp-68h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled()
    && (unsigned int)_o__wcsicmp(a1, L"localspl.dll")
    && (unsigned int)_o__wcsicmp(a1, L"win32spl.dll") )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeProvidor",
      L"Rejecting load of '%ws' as Windows Protected Print mode is enabled.",
      a1);
    LODWORD(LastError) = 50;
    goto LABEL_23;
  }
  v10 = RevertToPrinterSelf();
  if ( !v10 )
  {
    LODWORD(LastError) = GetLastError();
    goto LABEL_23;
  }
  v8 = DllAllocSplMem(0x388u);
  if ( !v8 || (v11 = AllocSplStr(a1), (*(_QWORD *)(v8 + 8) = v11) == 0) )
  {
    LODWORD(LastError) = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError("InitializeProvidor", L"Can't allocate memory for '%ws'.", a1);
    v17 = &MSG_ROUTER_PROVIDER_ALLOC_FAILED;
    goto LABEL_21;
  }
  for ( i = 0; i < 3; ++i )
  {
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v8 + 8), off_14008FB20[i]) )
    {
      *(_DWORD *)(v8 + 896) = 1;
      break;
    }
  }
  v13 = SetErrorMode(0x8001u);
  Library = LoadLibraryExW(a1, 0, 8u);
  *(_QWORD *)(v8 + 16) = Library;
  v7 = Library;
  SetErrorMode(v13);
  if ( !v7 )
  {
    LastError = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeProvidor",
      L"LoadLibrary for '%ws' failed.  Error %d.",
      a1,
      LastError);
    v20 = 115;
    v21 = 4;
    v22 = 0;
    v24 = 4;
    v25 = 0;
    v23 = LastError;
    v15 = SplLogType::SplLogType((SplLogType *)v26, a1);
    SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v15, &v23, &v20, v16);
    v17 = (const struct _EVENT_DESCRIPTOR *)MSG_ROUTER_PROVIDER_LOAD_FAILED;
LABEL_21:
    SplLogRouterEvent(v17, LastError, a1);
    goto LABEL_22;
  }
  ProcAddress = GetProcAddress(v7, "InitializePrintProvidor");
  *(_QWORD *)(v8 + 24) = ProcAddress;
  if ( ProcAddress )
  {
    LODWORD(LastError) = 0;
    v6 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int16 *))ProcAddress)(v8 + 32, 864, a2);
    if ( !v6 )
    {
      LastError = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "InitializeProvidor",
        L"Failed for provider '%ws'.  Error %d.",
        a1,
        LastError);
      v17 = (const struct _EVENT_DESCRIPTOR *)MSG_ROUTER_PROVIDER_INIT_FAILED;
      goto LABEL_21;
    }
  }
  else
  {
    LODWORD(LastError) = GetLastError();
  }
LABEL_22:
  ImpersonatePrinterClient(v10);
LABEL_23:
  if ( a3 )
    *a3 = LastError;
  if ( v6 )
  {
    FixupOldProvidor((struct _PRINTPROVIDOR *)(v8 + 32));
    return (struct _PROVIDOR *)v8;
  }
  else
  {
    if ( v7 )
      FreeLibrary(v7);
    if ( v8 )
    {
      DllFreeSplStr(*(_QWORD *)(v8 + 8));
      HeapFree(g_hSpoolssHeap, 0, (LPVOID)v8);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14006533c  push    rbx
0x14006533e  push    rbp
0x14006533f  push    rsi
0x140065340  push    rdi
0x140065341  push    r12
0x140065343  push    r13
0x140065345  push    r14
0x140065347  push    r15
0x140065349  sub     rsp, 88h
0x140065350  mov     r12, r8
0x140065353  mov     r13, rdx
0x140065356  mov     rsi, rcx
0x140065359  xor     r15d, r15d
0x14006535c  xor     ebp, ebp
0x14006535e  xor     edi, edi
0x140065360  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140065365  test    eax, eax
0x140065367  jz      short loc_1400653AF
0x140065369  lea     rdx, szLocalSplDll; "localspl.dll"
0x140065370  mov     rcx, rsi
0x140065373  call    cs:__imp__o__wcsicmp
0x140065379  test    eax, eax
0x14006537b  jz      short loc_1400653AF
0x14006537d  lea     rdx, szWin32spl; "win32spl.dll"
0x140065384  mov     rcx, rsi
0x140065387  call    cs:__imp__o__wcsicmp
0x14006538d  test    eax, eax
0x14006538f  jz      short loc_1400653AF
0x140065391  mov     r8, rsi
0x140065394  lea     rdx, aRejectingLoadO; "Rejecting load of '%ws' as Windows Prot"...
0x14006539b  lea     rcx, aInitializeprov; "InitializeProvidor"
0x1400653a2  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400653a7  lea     ebx, [rbp+32h]
0x1400653aa  jmp     loc_140065571
0x1400653af  call    RevertToPrinterSelf
0x1400653b4  mov     r14, rax
0x1400653b7  test    rax, rax
0x1400653ba  jnz     short loc_1400653C9
0x1400653bc  call    cs:__imp_GetLastError
0x1400653c2  mov     ebx, eax
0x1400653c4  jmp     loc_140065571
0x1400653c9  mov     ecx, 388h; dwBytes
0x1400653ce  call    DllAllocSplMem
0x1400653d3  mov     rdi, rax
0x1400653d6  test    rax, rax
0x1400653d9  jz      loc_14006553A
0x1400653df  mov     rcx, rsi; Src
0x1400653e2  call    AllocSplStr
0x1400653e7  mov     [rdi+8], rax
0x1400653eb  test    rax, rax
0x1400653ee  jz      loc_14006553A
0x1400653f4  xor     ebx, ebx
0x1400653f6  cmp     ebx, 3
0x1400653f9  jnb     short loc_140065425
0x1400653fb  mov     rcx, [rdi+8]
0x1400653ff  lea     rax, off_14008FB20; "localspl.dll"
0x140065406  movsxd  rdx, ebx
0x140065409  mov     rdx, [rax+rdx*8]
0x14006540d  call    cs:__imp__o__wcsicmp
0x140065413  test    eax, eax
0x140065415  jz      short loc_14006541B
0x140065417  inc     ebx
0x140065419  jmp     short loc_1400653F6
0x14006541b  mov     dword ptr [rdi+380h], 1
0x140065425  mov     ecx, 8001h; uMode
0x14006542a  call    cs:__imp_SetErrorMode
0x140065430  xor     edx, edx; hFile
0x140065432  mov     rcx, rsi; lpLibFileName
0x140065435  mov     ebx, eax
0x140065437  lea     r8d, [rdx+8]; dwFlags
0x14006543b  call    cs:__imp_LoadLibraryExW
0x140065441  mov     ecx, ebx; uMode
0x140065443  mov     [rdi+10h], rax
0x140065447  mov     rbp, rax
0x14006544a  call    cs:__imp_SetErrorMode
0x140065450  test    rbp, rbp
0x140065453  jnz     short loc_1400654D3
0x140065455  call    cs:__imp_GetLastError
0x14006545b  mov     r8, rsi
0x14006545e  lea     rdx, aLoadlibraryFor; "LoadLibrary for '%ws' failed.  Error %d"...
0x140065465  mov     r9d, eax
0x140065468  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006546f  mov     ebx, eax
0x140065471  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065476  lea     eax, [rbp+4]
0x140065479  mov     [rsp+0C8h+var_98], 73h ; 's'
0x140065481  xor     r10d, r10d
0x140065484  mov     [rsp+0C8h+var_90], rax
0x140065489  mov     rdx, rsi; unsigned __int16 *
0x14006548c  mov     [rsp+0C8h+var_88], r10d
0x140065491  lea     rcx, [rsp+0C8h+var_68]; this
0x140065496  mov     [rsp+0C8h+var_78], rax
0x14006549b  mov     [rsp+0C8h+var_70], r10d
0x1400654a0  mov     [rsp+0C8h+var_80], ebx
0x1400654a4  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1400654a9  lea     r9, [rsp+0C8h+var_98]
0x1400654ae  mov     [rsp+0C8h+var_A8], r10
0x1400654b3  lea     r8, [rsp+0C8h+var_80]
0x1400654b8  mov     rdx, rax; struct SplLogType *
0x1400654bb  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x1400654c2  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1400654c7  lea     rcx, MSG_ROUTER_PROVIDER_LOAD_FAILED
0x1400654ce  jmp     loc_14006555F
0x1400654d3  lea     rdx, aInitializeprin; "InitializePrintProvidor"
0x1400654da  mov     rcx, rbp; hModule
0x1400654dd  call    cs:__imp_GetProcAddress
0x1400654e3  mov     [rdi+18h], rax
0x1400654e7  test    rax, rax
0x1400654ea  jnz     short loc_1400654F6
0x1400654ec  call    cs:__imp_GetLastError
0x1400654f2  mov     ebx, eax
0x1400654f4  jmp     short loc_140065569
0x1400654f6  lea     rcx, [rdi+20h]
0x1400654fa  mov     r8, r13
0x1400654fd  mov     edx, 360h
0x140065502  xor     ebx, ebx
0x140065504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065509  mov     r15d, eax
0x14006550c  test    eax, eax
0x14006550e  jnz     short loc_140065569
0x140065510  call    cs:__imp_GetLastError
0x140065516  mov     r8, rsi
0x140065519  lea     rdx, aFailedForProvi; "Failed for provider '%ws'.  Error %d."
0x140065520  mov     r9d, eax
0x140065523  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006552a  mov     ebx, eax
0x14006552c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065531  lea     rcx, MSG_ROUTER_PROVIDER_INIT_FAILED
0x140065538  jmp     short loc_14006555F
0x14006553a  call    cs:__imp_GetLastError
0x140065540  mov     r8, rsi
0x140065543  lea     rdx, aCanTAllocateMe; "Can't allocate memory for '%ws'."
0x14006554a  lea     rcx, aInitializeprov; "InitializeProvidor"
0x140065551  mov     ebx, eax
0x140065553  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065558  lea     rcx, MSG_ROUTER_PROVIDER_ALLOC_FAILED; struct _EVENT_DESCRIPTOR *
0x14006555f  mov     r8, rsi; unsigned __int16 *
0x140065562  mov     edx, ebx; unsigned int
0x140065564  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x140065569  mov     rcx, r14; hToken
0x14006556c  call    ImpersonatePrinterClient
0x140065571  test    r12, r12
0x140065574  jz      short loc_14006557A
0x140065576  mov     [r12], ebx
0x14006557a  test    r15d, r15d
0x14006557d  jz      short loc_14006558D
0x14006557f  lea     rcx, [rdi+20h]; struct _PRINTPROVIDOR *
0x140065583  call    ?FixupOldProvidor@@YAXPEAU_PRINTPROVIDOR@@@Z; FixupOldProvidor(_PRINTPROVIDOR *)
0x140065588  mov     rax, rdi
0x14006558b  jmp     short loc_1400655BD
0x14006558d  test    rbp, rbp
0x140065590  jz      short loc_14006559B
0x140065592  mov     rcx, rbp; hLibModule
0x140065595  call    cs:__imp_FreeLibrary
0x14006559b  test    rdi, rdi
0x14006559e  jz      short loc_1400655BB
0x1400655a0  mov     rcx, [rdi+8]
0x1400655a4  call    DllFreeSplStr
0x1400655a9  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400655b0  mov     r8, rdi; lpMem
0x1400655b3  xor     edx, edx; dwFlags
0x1400655b5  call    cs:__imp_HeapFree
0x1400655bb  xor     eax, eax
0x1400655bd  add     rsp, 88h
0x1400655c4  pop     r15
0x1400655c6  pop     r14
0x1400655c8  pop     r13
0x1400655ca  pop     r12
0x1400655cc  pop     rdi
0x1400655cd  pop     rsi
0x1400655ce  pop     rbp
0x1400655cf  pop     rbx
0x1400655d0  retn
```
