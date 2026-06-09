# ServiceStopCallback(void *,uchar)

- ea: `0x1800024f0`
- end: `0x180002674`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `388`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002044`

## callees

- `0x180001f80`
- `0x1800024f0`
- `0x1800027e8`
- `0x180002820`
- `0x180002950`
- `0x180003010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002639`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002583`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800025cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800025cf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002570`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002570`

## pseudocode

```c
void __fastcall ServiceStopCallback(void *a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  struct _WSP_HOSTED_PROVIDER near **v4; // rbx
  void (*v5)(void); // rax
  __int64 v6; // r8
  int v7; // edi
  unsigned __int64 v8; // rbx
  _BYTE *v9; // rcx
  void (**v10)(void); // rax
  void (__fastcall *v11)(_BYTE *); // rax
  HMODULE v12; // rcx
  REGHANDLE v13; // rcx
  __int64 v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-28h] BYREF

  ReportServiceStatus(3u, a2, 0);
  if ( (Microsoft_Windows_StorageManagement_WSP_HostEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, (const EVENT_DESCRIPTOR *)SMPHOST_SHUTDOWN_INITIATED, v3, 1u, &v15);
  v4 = &g_HostedProviders;
  do
  {
    v5 = (void (*)(void))v4[7];
    if ( v5 )
      v5();
    v4 += 8;
  }
  while ( v4 != (struct _WSP_HOSTED_PROVIDER near **)&_native_dllmain_reason );
  UnregisterWaitEx(g_WaitHandle, 0);
  CloseHandle(g_ServiceStopEvent);
  v7 = 4;
  do
  {
    v8 = (unsigned __int64)(unsigned int)--v7 << 6;
    v9 = &algn_180006090[v8 + 8];
    if ( &algn_180006090[v8 + 8] )
    {
      v10 = (void (**)(void))*((_QWORD *)v9 + 2);
      if ( v10 )
        (*v10)();
    }
    v11 = *(void (__fastcall **)(_BYTE *))((char *)&g_HostedProviders + v8 + 48);
    if ( v11 )
      v11(v9);
    v12 = *(HMODULE *)((char *)&g_HostedProviders + v8 + 16);
    if ( v12 )
      FreeLibrary(v12);
  }
  while ( v7 );
  if ( (Microsoft_Windows_StorageManagement_WSP_HostEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v12, (const EVENT_DESCRIPTOR *)SMPHOST_SHUTDOWN_COMPLETED, v6, 1u, &v15);
  if ( g_Application.ft )
    ((void (__fastcall *)(MI_Application *))g_Application.ft->Close)(&g_Application);
  v13 = RegHandle;
  dword_180006048 = 0;
  RegHandle = 0;
  EventUnregister(v13);
  McGenEventUnregister_EventUnregister();
  ReportServiceStatus(1u, v14, 0);
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp+arg_0], rbx
0x1800024f5  mov     [rsp+arg_8], rsi
0x1800024fa  push    rdi
0x1800024fb  sub     rsp, 50h
0x1800024ff  mov     rax, cs:__security_cookie
0x180002506  xor     rax, rsp
0x180002509  mov     [rsp+58h+var_18], rax
0x18000250e  xor     r8d, r8d; unsigned int
0x180002511  lea     ecx, [r8+3]; unsigned int
0x180002515  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x18000251a  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, 2
0x180002521  jz      short loc_18000253F
0x180002523  lea     rax, [rsp+58h+var_28]
0x180002528  mov     r9d, 1
0x18000252e  lea     rdx, SMPHOST_SHUTDOWN_INITIATED
0x180002535  mov     [rsp+58h+var_38], rax
0x18000253a  call    McGenEventWrite_EventWriteTransfer
0x18000253f  lea     rsi, ?g_HostedProviders@@3PAU_WSP_HOSTED_PROVIDER@@A; _WSP_HOSTED_PROVIDER near * g_HostedProviders
0x180002546  mov     rbx, rsi
0x180002549  mov     rax, [rbx+38h]
0x18000254d  test    rax, rax
0x180002550  jz      short loc_180002557
0x180002552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002557  add     rbx, 40h ; '@'
0x18000255b  lea     rax, __native_dllmain_reason
0x180002562  cmp     rbx, rax
0x180002565  jnz     short loc_180002549
0x180002567  mov     rcx, cs:?g_WaitHandle@@3PEAXEA; WaitHandle
0x18000256e  xor     edx, edx; CompletionEvent
0x180002570  call    cs:__imp_UnregisterWaitEx
0x180002577  nop     dword ptr [rax+rax+00h]
0x18000257c  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hObject
0x180002583  call    cs:__imp_CloseHandle
0x18000258a  nop     dword ptr [rax+rax+00h]
0x18000258f  mov     edi, 4
0x180002594  dec     edi
0x180002596  lea     rcx, [rsi+18h]
0x18000259a  mov     ebx, edi
0x18000259c  shl     rbx, 6
0x1800025a0  add     rcx, rbx
0x1800025a3  jz      short loc_1800025B6
0x1800025a5  mov     rax, [rcx+10h]
0x1800025a9  test    rax, rax
0x1800025ac  jz      short loc_1800025B6
0x1800025ae  mov     rax, [rax]
0x1800025b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b6  mov     rax, [rbx+rsi+30h]
0x1800025bb  test    rax, rax
0x1800025be  jz      short loc_1800025C5
0x1800025c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c5  mov     rcx, [rbx+rsi+10h]; hLibModule
0x1800025ca  test    rcx, rcx
0x1800025cd  jz      short loc_1800025DB
0x1800025cf  call    cs:__imp_FreeLibrary
0x1800025d6  nop     dword ptr [rax+rax+00h]
0x1800025db  test    edi, edi
0x1800025dd  jnz     short loc_180002594
0x1800025df  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, 2
0x1800025e6  jz      short loc_180002602
0x1800025e8  lea     rax, [rsp+58h+var_28]
0x1800025ed  lea     r9d, [rdi+1]
0x1800025f1  mov     [rsp+58h+var_38], rax
0x1800025f6  lea     rdx, SMPHOST_SHUTDOWN_COMPLETED
0x1800025fd  call    McGenEventWrite_EventWriteTransfer
0x180002602  mov     rax, cs:?g_Application@@3U_MI_Application@@A.ft; _MI_Application g_Application ...
0x180002609  test    rax, rax
0x18000260c  jz      short loc_18000261D
0x18000260e  mov     rax, [rax]
0x180002611  lea     rcx, ?g_Application@@3U_MI_Application@@A; _MI_Application g_Application
0x180002618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261d  mov     rcx, cs:RegHandle; RegHandle
0x180002624  mov     cs:dword_180006048, 0
0x18000262e  mov     cs:RegHandle, 0
0x180002639  call    cs:__imp_EventUnregister
0x180002640  nop     dword ptr [rax+rax+00h]
0x180002645  call    McGenEventUnregister_EventUnregister
0x18000264a  xor     r8d, r8d; unsigned int
0x18000264d  lea     ecx, [r8+1]; unsigned int
0x180002651  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002656  mov     rcx, [rsp+58h+var_18]
0x18000265b  xor     rcx, rsp; StackCookie
0x18000265e  call    __security_check_cookie
0x180002663  mov     rbx, [rsp+58h+arg_0]
0x180002668  mov     rsi, [rsp+58h+arg_8]
0x18000266d  add     rsp, 50h
0x180002671  pop     rdi
0x180002672  retn
```
