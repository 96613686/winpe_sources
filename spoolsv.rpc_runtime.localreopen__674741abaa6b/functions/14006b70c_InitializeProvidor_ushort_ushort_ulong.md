# InitializeProvidor(ushort *,ushort *,ulong *)

- ea: `0x14006b70c`
- end: `0x14006b9fa`
- name: `?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z`
- size: `750`
- prototype: `struct _PROVIDOR *__fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140063c38`
- `0x14006b5a4`
- `0x14006bb40`

## callees

- `0x140004790`
- `0x14000b4b0`
- `0x14000bca0`
- `0x14000ef30`
- `0x14000f600`
- `0x140015378`
- `0x1400161d0`
- `0x14004ddd0`
- `0x14005be70`
- `0x14005c00c`
- `0x14005e898`
- `0x14006b70c`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b743`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b75d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b7ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b743`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b75d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006b7ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006b8e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006b8e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006b9d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006b9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006b812`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006b83e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006b812`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14006b83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006b950`
- `KERNEL32!FreeLibrary` at `0x14006b9b1`
- `KERNEL32!FreeLibrary` at `0x14006b9b1`
- `KERNEL32!LoadLibraryExW` at `0x14006b829`
- `KERNEL32!LoadLibraryExW` at `0x14006b829`

## string_xrefs

- `0x14006b753`: `win32spl.dll`
- `0x14006b862`: `LoadLibrary for '%ws' failed.  Error %d.`
- `0x14006b739`: `localspl.dll`

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
    if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v8 + 8), off_140096B20[i]) )
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
0x14006b70c  push    rbx
0x14006b70e  push    rbp
0x14006b70f  push    rsi
0x14006b710  push    rdi
0x14006b711  push    r12
0x14006b713  push    r13
0x14006b715  push    r14
0x14006b717  push    r15
0x14006b719  sub     rsp, 88h
0x14006b720  mov     r12, r8
0x14006b723  mov     r13, rdx
0x14006b726  mov     rsi, rcx
0x14006b729  xor     r15d, r15d
0x14006b72c  xor     ebp, ebp
0x14006b72e  xor     edi, edi
0x14006b730  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14006b735  test    eax, eax
0x14006b737  jz      short loc_14006B78B
0x14006b739  lea     rdx, szLocalSplDll; "localspl.dll"
0x14006b740  mov     rcx, rsi
0x14006b743  call    cs:__imp__o__wcsicmp
0x14006b74a  nop     dword ptr [rax+rax+00h]
0x14006b74f  test    eax, eax
0x14006b751  jz      short loc_14006B78B
0x14006b753  lea     rdx, szWin32spl; "win32spl.dll"
0x14006b75a  mov     rcx, rsi
0x14006b75d  call    cs:__imp__o__wcsicmp
0x14006b764  nop     dword ptr [rax+rax+00h]
0x14006b769  test    eax, eax
0x14006b76b  jz      short loc_14006B78B
0x14006b76d  mov     r8, rsi
0x14006b770  lea     rdx, aRejectingLoadO; "Rejecting load of '%ws' as Windows Prot"...
0x14006b777  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006b77e  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006b783  lea     ebx, [rbp+32h]
0x14006b786  jmp     loc_14006B98D
0x14006b78b  call    RevertToPrinterSelf
0x14006b790  mov     r14, rax
0x14006b793  test    rax, rax
0x14006b796  jnz     short loc_14006B7AB
0x14006b798  call    cs:__imp_GetLastError
0x14006b79f  nop     dword ptr [rax+rax+00h]
0x14006b7a4  mov     ebx, eax
0x14006b7a6  jmp     loc_14006B98D
0x14006b7ab  mov     ecx, 388h; dwBytes
0x14006b7b0  call    DllAllocSplMem
0x14006b7b5  mov     rdi, rax
0x14006b7b8  test    rax, rax
0x14006b7bb  jz      loc_14006B950
0x14006b7c1  mov     rcx, rsi; Src
0x14006b7c4  call    AllocSplStr
0x14006b7c9  mov     [rdi+8], rax
0x14006b7cd  test    rax, rax
0x14006b7d0  jz      loc_14006B950
0x14006b7d6  xor     ebx, ebx
0x14006b7d8  cmp     ebx, 3
0x14006b7db  jnb     short loc_14006B80D
0x14006b7dd  mov     rcx, [rdi+8]
0x14006b7e1  lea     rax, off_140096B20; "localspl.dll"
0x14006b7e8  movsxd  rdx, ebx
0x14006b7eb  mov     rdx, [rax+rdx*8]
0x14006b7ef  call    cs:__imp__o__wcsicmp
0x14006b7f6  nop     dword ptr [rax+rax+00h]
0x14006b7fb  test    eax, eax
0x14006b7fd  jz      short loc_14006B803
0x14006b7ff  inc     ebx
0x14006b801  jmp     short loc_14006B7D8
0x14006b803  mov     dword ptr [rdi+380h], 1
0x14006b80d  mov     ecx, 8001h; uMode
0x14006b812  call    cs:__imp_SetErrorMode
0x14006b819  nop     dword ptr [rax+rax+00h]
0x14006b81e  xor     edx, edx; hFile
0x14006b820  mov     rcx, rsi; lpLibFileName
0x14006b823  mov     ebx, eax
0x14006b825  lea     r8d, [rdx+8]; dwFlags
0x14006b829  call    cs:__imp_LoadLibraryExW
0x14006b830  nop     dword ptr [rax+rax+00h]
0x14006b835  mov     ecx, ebx; uMode
0x14006b837  mov     [rdi+10h], rax
0x14006b83b  mov     rbp, rax
0x14006b83e  call    cs:__imp_SetErrorMode
0x14006b845  nop     dword ptr [rax+rax+00h]
0x14006b84a  test    rbp, rbp
0x14006b84d  jnz     loc_14006B8D7
0x14006b853  call    cs:__imp_GetLastError
0x14006b85a  nop     dword ptr [rax+rax+00h]
0x14006b85f  mov     r8, rsi
0x14006b862  lea     rdx, aLoadlibraryFor; "LoadLibrary for '%ws' failed.  Error %d"...
0x14006b869  mov     r9d, eax
0x14006b86c  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006b873  mov     ebx, eax
0x14006b875  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006b87a  lea     eax, [rbp+4]
0x14006b87d  mov     [rsp+0C8h+var_98], 73h ; 's'
0x14006b885  xor     r10d, r10d
0x14006b888  mov     [rsp+0C8h+var_90], rax
0x14006b88d  mov     rdx, rsi; unsigned __int16 *
0x14006b890  mov     [rsp+0C8h+var_88], r10d
0x14006b895  lea     rcx, [rsp+0C8h+var_68]; this
0x14006b89a  mov     [rsp+0C8h+var_78], rax
0x14006b89f  mov     [rsp+0C8h+var_70], r10d
0x14006b8a4  mov     [rsp+0C8h+var_80], ebx
0x14006b8a8  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x14006b8ad  lea     r9, [rsp+0C8h+var_98]
0x14006b8b2  mov     [rsp+0C8h+var_A8], r10
0x14006b8b7  lea     r8, [rsp+0C8h+var_80]
0x14006b8bc  mov     rdx, rax; struct SplLogType *
0x14006b8bf  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x14006b8c6  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x14006b8cb  lea     rcx, MSG_ROUTER_PROVIDER_LOAD_FAILED
0x14006b8d2  jmp     loc_14006B97B
0x14006b8d7  lea     rdx, aInitializeprin; "InitializePrintProvidor"
0x14006b8de  mov     rcx, rbp; hModule
0x14006b8e1  call    cs:__imp_GetProcAddress
0x14006b8e8  nop     dword ptr [rax+rax+00h]
0x14006b8ed  mov     [rdi+18h], rax
0x14006b8f1  test    rax, rax
0x14006b8f4  jnz     short loc_14006B906
0x14006b8f6  call    cs:__imp_GetLastError
0x14006b8fd  nop     dword ptr [rax+rax+00h]
0x14006b902  mov     ebx, eax
0x14006b904  jmp     short loc_14006B985
0x14006b906  lea     rcx, [rdi+20h]
0x14006b90a  mov     r8, r13
0x14006b90d  mov     edx, 360h
0x14006b912  xor     ebx, ebx
0x14006b914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b919  mov     r15d, eax
0x14006b91c  test    eax, eax
0x14006b91e  jnz     short loc_14006B985
0x14006b920  call    cs:__imp_GetLastError
0x14006b927  nop     dword ptr [rax+rax+00h]
0x14006b92c  mov     r8, rsi
0x14006b92f  lea     rdx, aFailedForProvi; "Failed for provider '%ws'.  Error %d."
0x14006b936  mov     r9d, eax
0x14006b939  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006b940  mov     ebx, eax
0x14006b942  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006b947  lea     rcx, MSG_ROUTER_PROVIDER_INIT_FAILED
0x14006b94e  jmp     short loc_14006B97B
0x14006b950  call    cs:__imp_GetLastError
0x14006b957  nop     dword ptr [rax+rax+00h]
0x14006b95c  mov     r8, rsi
0x14006b95f  lea     rdx, aCanTAllocateMe; "Can't allocate memory for '%ws'."
0x14006b966  lea     rcx, aInitializeprov; "InitializeProvidor"
0x14006b96d  mov     ebx, eax
0x14006b96f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006b974  lea     rcx, MSG_ROUTER_PROVIDER_ALLOC_FAILED; struct _EVENT_DESCRIPTOR *
0x14006b97b  mov     r8, rsi; unsigned __int16 *
0x14006b97e  mov     edx, ebx; unsigned int
0x14006b980  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006b985  mov     rcx, r14; hToken
0x14006b988  call    ImpersonatePrinterClient
0x14006b98d  test    r12, r12
0x14006b990  jz      short loc_14006B996
0x14006b992  mov     [r12], ebx
0x14006b996  test    r15d, r15d
0x14006b999  jz      short loc_14006B9A9
0x14006b99b  lea     rcx, [rdi+20h]; struct _PRINTPROVIDOR *
0x14006b99f  call    ?FixupOldProvidor@@YAXPEAU_PRINTPROVIDOR@@@Z; FixupOldProvidor(_PRINTPROVIDOR *)
0x14006b9a4  mov     rax, rdi
0x14006b9a7  jmp     short loc_14006B9E5
0x14006b9a9  test    rbp, rbp
0x14006b9ac  jz      short loc_14006B9BD
0x14006b9ae  mov     rcx, rbp; hLibModule
0x14006b9b1  call    cs:__imp_FreeLibrary
0x14006b9b8  nop     dword ptr [rax+rax+00h]
0x14006b9bd  test    rdi, rdi
0x14006b9c0  jz      short loc_14006B9E3
0x14006b9c2  mov     rcx, [rdi+8]
0x14006b9c6  call    DllFreeSplStr
0x14006b9cb  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006b9d2  mov     r8, rdi; lpMem
0x14006b9d5  xor     edx, edx; dwFlags
0x14006b9d7  call    cs:__imp_HeapFree
0x14006b9de  nop     dword ptr [rax+rax+00h]
0x14006b9e3  xor     eax, eax
0x14006b9e5  add     rsp, 88h
0x14006b9ec  pop     r15
0x14006b9ee  pop     r14
0x14006b9f0  pop     r13
0x14006b9f2  pop     r12
0x14006b9f4  pop     rdi
0x14006b9f5  pop     rsi
0x14006b9f6  pop     rbp
0x14006b9f7  pop     rbx
0x14006b9f8  retn
```
