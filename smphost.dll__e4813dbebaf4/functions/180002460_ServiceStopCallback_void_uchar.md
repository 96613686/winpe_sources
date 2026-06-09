# ServiceStopCallback(void *,uchar)

- ea: `0x180002460`
- end: `0x1800025cb`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `363`
- prototype: `void __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001fec`

## callees

- `0x180001f3c`
- `0x180002460`
- `0x180002740`
- `0x180002770`
- `0x180002890`
- `0x180003010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002597`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002533`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002533`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800024e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800024e0`

## pseudocode

```c
void __fastcall ServiceStopCallback(void *a1, unsigned int a2)
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
  unsigned int v14; // edx
  _BYTE v15[16]; // [rsp+30h] [rbp-28h] BYREF

  ReportServiceStatus(3u, a2, 0);
  if ( (Microsoft_Windows_StorageManagement_WSP_HostEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, SMPHOST_SHUTDOWN_INITIATED, v3, 1, v15);
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
    McGenEventWrite_EventWriteTransfer(v12, SMPHOST_SHUTDOWN_COMPLETED, v6, 1, v15);
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
0x180002460  mov     [rsp+arg_0], rbx
0x180002465  mov     [rsp+arg_8], rsi
0x18000246a  push    rdi
0x18000246b  sub     rsp, 50h
0x18000246f  mov     rax, cs:__security_cookie
0x180002476  xor     rax, rsp
0x180002479  mov     [rsp+58h+var_18], rax
0x18000247e  xor     r8d, r8d; unsigned int
0x180002481  lea     ecx, [r8+3]; unsigned int
0x180002485  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x18000248a  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, 2
0x180002491  jz      short loc_1800024AF
0x180002493  lea     rax, [rsp+58h+var_28]
0x180002498  mov     r9d, 1
0x18000249e  lea     rdx, SMPHOST_SHUTDOWN_INITIATED
0x1800024a5  mov     [rsp+58h+var_38], rax
0x1800024aa  call    McGenEventWrite_EventWriteTransfer
0x1800024af  lea     rsi, ?g_HostedProviders@@3PAU_WSP_HOSTED_PROVIDER@@A; _WSP_HOSTED_PROVIDER near * g_HostedProviders
0x1800024b6  mov     rbx, rsi
0x1800024b9  mov     rax, [rbx+38h]
0x1800024bd  test    rax, rax
0x1800024c0  jz      short loc_1800024C7
0x1800024c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c7  add     rbx, 40h ; '@'
0x1800024cb  lea     rax, __native_dllmain_reason
0x1800024d2  cmp     rbx, rax
0x1800024d5  jnz     short loc_1800024B9
0x1800024d7  mov     rcx, cs:?g_WaitHandle@@3PEAXEA; WaitHandle
0x1800024de  xor     edx, edx; CompletionEvent
0x1800024e0  call    cs:__imp_UnregisterWaitEx
0x1800024e6  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hObject
0x1800024ed  call    cs:__imp_CloseHandle
0x1800024f3  mov     edi, 4
0x1800024f8  dec     edi
0x1800024fa  lea     rcx, [rsi+18h]
0x1800024fe  mov     ebx, edi
0x180002500  shl     rbx, 6
0x180002504  add     rcx, rbx
0x180002507  jz      short loc_18000251A
0x180002509  mov     rax, [rcx+10h]
0x18000250d  test    rax, rax
0x180002510  jz      short loc_18000251A
0x180002512  mov     rax, [rax]
0x180002515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251a  mov     rax, [rbx+rsi+30h]
0x18000251f  test    rax, rax
0x180002522  jz      short loc_180002529
0x180002524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002529  mov     rcx, [rbx+rsi+10h]; hLibModule
0x18000252e  test    rcx, rcx
0x180002531  jz      short loc_180002539
0x180002533  call    cs:__imp_FreeLibrary
0x180002539  test    edi, edi
0x18000253b  jnz     short loc_1800024F8
0x18000253d  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, 2
0x180002544  jz      short loc_180002560
0x180002546  lea     rax, [rsp+58h+var_28]
0x18000254b  lea     r9d, [rdi+1]
0x18000254f  mov     [rsp+58h+var_38], rax
0x180002554  lea     rdx, SMPHOST_SHUTDOWN_COMPLETED
0x18000255b  call    McGenEventWrite_EventWriteTransfer
0x180002560  mov     rax, cs:?g_Application@@3U_MI_Application@@A.ft; _MI_Application g_Application ...
0x180002567  test    rax, rax
0x18000256a  jz      short loc_18000257B
0x18000256c  mov     rax, [rax]
0x18000256f  lea     rcx, ?g_Application@@3U_MI_Application@@A; _MI_Application g_Application
0x180002576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257b  mov     rcx, cs:RegHandle; RegHandle
0x180002582  mov     cs:dword_180006048, 0
0x18000258c  mov     cs:RegHandle, 0
0x180002597  call    cs:__imp_EventUnregister
0x18000259d  call    McGenEventUnregister_EventUnregister
0x1800025a2  xor     r8d, r8d; unsigned int
0x1800025a5  lea     ecx, [r8+1]; unsigned int
0x1800025a9  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x1800025ae  mov     rcx, [rsp+58h+var_18]
0x1800025b3  xor     rcx, rsp; StackCookie
0x1800025b6  call    __security_check_cookie
0x1800025bb  mov     rbx, [rsp+58h+arg_0]
0x1800025c0  mov     rsi, [rsp+58h+arg_8]
0x1800025c5  add     rsp, 50h
0x1800025c9  pop     rdi
0x1800025ca  retn
```
