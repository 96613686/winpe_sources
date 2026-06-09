# I_RpcAsyncSetHandle

- ea: `0x180066200`
- end: `0x180066418`
- name: `I_RpcAsyncSetHandle`
- size: `536`
- prototype: `RPC_STATUS __stdcall(PRPC_MESSAGE Message, PRPC_ASYNC_STATE pAsync)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cc0`
- `0x180002130`
- `0x180065660`
- `0x1800d1860`
- `0x1800d1df0`

## callees

- `0x18000adb0`
- `0x180023a40`
- `0x1800258b4`
- `0x180066200`
- `0x180066718`
- `0x18006cff0`
- `0x1800a72e0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180066389`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180066389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006637b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006637b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066282`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066282`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006626e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006626e`

## pseudocode

```c
RPC_STATUS __stdcall I_RpcAsyncSetHandle(PRPC_MESSAGE Message, PRPC_ASYNC_STATE pAsync)
{
  _DWORD *Handle; // rdi
  RPC_STATUS v5; // ebp
  RPC_STATUS result; // eax
  GENERIC_OBJECT *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  RPC_STATUS v10; // ebx
  int v11; // eax
  RPC_WSTR v12; // rsi
  char *v13; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  int v16; // ecx
  RPC_WSTR StringBinding; // [rsp+50h] [rbp+8h] BYREF
  RPC_WSTR Protseq; // [rsp+60h] [rbp+18h] BYREF

  Handle = Message->Handle;
  StringBinding = 0;
  Protseq = 0;
  if ( !Handle || Handle[2] != -1985229329 || (Handle[3] & 0x20306C) == 0 )
    return 1702;
  if ( pAsync->NotificationType != RpcNotificationTypeHwnd || (Handle[3] & 0x1024) == 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)Handle + 80LL))(Handle);
    if ( !v5 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)pAsync->Reserved);
      pAsync->RuntimeInfo = Handle;
      ReleaseSRWLockExclusive((PSRWLOCK)pAsync->Reserved);
    }
    return v5;
  }
  v7 = (GENERIC_OBJECT *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)Handle + 272LL))(Handle);
  if ( !RpcHasBeenInitialized )
  {
    result = PerformRpcInitialization();
    if ( result )
      return result;
  }
  if ( GENERIC_OBJECT::InvalidHandle(v7, 3350616) )
    return 1702;
  v9 = *(_QWORD *)v7;
  if ( (*((_DWORD *)v7 + 3) & 0x130010) != 0 )
    result = (*(__int64 (__fastcall **)(__int64, RPC_WSTR *))(v9 + 176))(v8, &StringBinding);
  else
    result = (*(__int64 (__fastcall **)(__int64, RPC_WSTR *))(v9 + 368))(v8, &StringBinding);
  if ( !result )
  {
    v10 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( RpcHasBeenInitialized || !(unsigned int)PerformRpcInitialization() )
    {
      FreeWrapper(StringBinding);
      StringBinding = 0;
    }
    if ( v10 )
    {
      return v10;
    }
    else
    {
      v11 = ShouldSkipLogging(3u);
      v12 = Protseq;
      if ( !v11 && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
      {
        v13 = (char *)Message->RpcInterfaceInformation + 4;
        CurrentProcessId = GetCurrentProcessId();
        CommandLineW = (unsigned int)GetCommandLineW();
        McTemplateU0zdzj_EtwEventWriteTransfer(
          v16,
          (unsigned int)RPC_EVENTLOG_ASYNC_HWND_USE_ERR,
          CommandLineW,
          CurrentProcessId,
          (__int64)v12,
          (__int64)v13);
      }
      if ( RpcHasBeenInitialized || !(unsigned int)PerformRpcInitialization() )
        FreeWrapper(v12);
      return 1764;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180066200  mov     rax, rsp
0x180066203  mov     [rax+10h], rbx
0x180066207  mov     [rax+20h], rbp
0x18006620b  push    rsi
0x18006620c  push    rdi
0x18006620d  push    r14
0x18006620f  sub     rsp, 30h
0x180066213  mov     rdi, [rcx]
0x180066216  mov     rsi, rdx
0x180066219  mov     qword ptr [rax+8], 0
0x180066221  mov     r14, rcx
0x180066224  mov     qword ptr [rax+18h], 0
0x18006622c  test    rdi, rdi
0x18006622f  jz      loc_1800663CC
0x180066235  cmp     dword ptr [rdi+8], 89ABCDEFh
0x18006623c  jnz     loc_1800663CC
0x180066242  test    dword ptr [rdi+0Ch], 20306Ch
0x180066249  jz      loc_1800663CC
0x18006624f  cmp     dword ptr [rdx+2Ch], 4
0x180066253  jz      short loc_1800662A4
0x180066255  mov     rax, [rdi]
0x180066258  mov     rcx, rdi
0x18006625b  mov     rax, [rax+50h]
0x18006625f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066264  mov     ebp, eax
0x180066266  test    eax, eax
0x180066268  jnz     short loc_18006628E
0x18006626a  lea     rcx, [rsi+50h]; SRWLock
0x18006626e  call    cs:__imp_AcquireSRWLockExclusive
0x180066275  nop     dword ptr [rax+rax+00h]
0x18006627a  lea     rcx, [rsi+50h]; SRWLock
0x18006627e  mov     [rsi+20h], rdi
0x180066282  call    cs:__imp_ReleaseSRWLockExclusive
0x180066289  nop     dword ptr [rax+rax+00h]
0x18006628e  mov     eax, ebp
0x180066290  mov     rbx, [rsp+48h+arg_8]
0x180066295  mov     rbp, [rsp+48h+arg_18]
0x18006629a  add     rsp, 30h
0x18006629e  pop     r14
0x1800662a0  pop     rdi
0x1800662a1  pop     rsi
0x1800662a2  retn
0x1800662a4  test    dword ptr [rdi+0Ch], 1024h
0x1800662ab  jz      short loc_180066255
0x1800662ad  mov     rax, [rdi]
0x1800662b0  mov     rcx, rdi
0x1800662b3  mov     rax, [rax+110h]
0x1800662ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662bf  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x1800662c6  mov     rbx, rax
0x1800662c9  jz      loc_1800663F3
0x1800662cf  mov     edx, 332058h; int
0x1800662d4  mov     rcx, rbx; this
0x1800662d7  call    ?InvalidHandle@GENERIC_OBJECT@@QEAAIH@Z; GENERIC_OBJECT::InvalidHandle(int)
0x1800662dc  test    eax, eax
0x1800662de  jnz     loc_1800663CC
0x1800662e4  test    dword ptr [rbx+0Ch], 130010h
0x1800662eb  lea     rdx, [rsp+48h+StringBinding]
0x1800662f0  mov     rax, [rbx]
0x1800662f3  jnz     loc_180066405
0x1800662f9  mov     rax, [rax+170h]
0x180066300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066305  test    eax, eax
0x180066307  jnz     short loc_180066290
0x180066309  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x18006630e  lea     r8, [rsp+48h+Protseq]; Protseq
0x180066313  mov     [rsp+48h+NetworkOptions], 0; NetworkOptions
0x18006631c  xor     r9d, r9d; NetworkAddr
0x18006631f  xor     edx, edx; ObjUuid
0x180066321  mov     [rsp+48h+Endpoint], 0; Endpoint
0x18006632a  call    RpcStringBindingParseW
0x18006632f  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x180066336  mov     ebx, eax
0x180066338  jz      loc_1800663D6
0x18006633e  mov     rcx, [rsp+48h+StringBinding]; lpMem
0x180066343  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180066348  mov     [rsp+48h+StringBinding], 0
0x180066351  test    ebx, ebx
0x180066353  jnz     loc_180066411
0x180066359  lea     ecx, [rbx+3]; unsigned int
0x18006635c  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x180066361  mov     rsi, [rsp+48h+Protseq]
0x180066366  test    eax, eax
0x180066368  jnz     short loc_1800663B1
0x18006636a  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x180066371  jz      short loc_1800663B1
0x180066373  mov     rbx, [r14+28h]
0x180066377  add     rbx, 4
0x18006637b  call    cs:__imp_GetCurrentProcessId
0x180066382  nop     dword ptr [rax+rax+00h]
0x180066387  mov     edi, eax
0x180066389  call    cs:__imp_GetCommandLineW
0x180066390  nop     dword ptr [rax+rax+00h]
0x180066395  mov     [rsp+48h+NetworkOptions], rbx
0x18006639a  lea     rdx, RPC_EVENTLOG_ASYNC_HWND_USE_ERR
0x1800663a1  mov     r8, rax
0x1800663a4  mov     [rsp+48h+Endpoint], rsi
0x1800663a9  mov     r9d, edi
0x1800663ac  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800663b1  cmp     cs:?RpcHasBeenInitialized@@3HA, 0; int RpcHasBeenInitialized
0x1800663b8  jz      short loc_1800663E8
0x1800663ba  mov     rcx, rsi; lpMem
0x1800663bd  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800663c2  mov     eax, 6E4h
0x1800663c7  jmp     loc_180066290
0x1800663cc  mov     eax, 6A6h
0x1800663d1  jmp     loc_180066290
0x1800663d6  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x1800663db  test    eax, eax
0x1800663dd  jnz     loc_180066351
0x1800663e3  jmp     loc_18006633E
0x1800663e8  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x1800663ed  test    eax, eax
0x1800663ef  jnz     short loc_1800663C2
0x1800663f1  jmp     short loc_1800663BA
0x1800663f3  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x1800663f8  test    eax, eax
0x1800663fa  jnz     loc_180066290
0x180066400  jmp     loc_1800662CF
0x180066405  mov     rax, [rax+0B0h]
0x18006640c  jmp     loc_180066300
0x180066411  mov     eax, ebx
0x180066413  jmp     loc_180066290
```
