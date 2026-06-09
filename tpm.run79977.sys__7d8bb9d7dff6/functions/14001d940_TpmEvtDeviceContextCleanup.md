# TpmEvtDeviceContextCleanup

- ea: `0x14001d940`
- end: `0x14001dace`
- name: `TpmEvtDeviceContextCleanup`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, service_task`

## callees

- `0x140008f6c`
- `0x14000e568`
- `0x14001c300`
- `0x14001d0a0`
- `0x14001d0e0`
- `0x14001d940`
- `0x140021918`
- `0x140039780`
- `0x140039b40`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001d9e8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001d9e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d9d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d9d7`

## pseudocode

```c
void __fastcall TpmEvtDeviceContextCleanup(__int64 a1)
{
  __int64 v2; // rax
  TpmDevice *v3; // rsi
  TpmScheduler *v4; // rbx
  TpmStack *v5; // rax
  TpmTaskTrigger *v6; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids, a1);
  if ( qword_140047DB8
    && qword_140047DB8 == (*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
                            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                            a1,
                            off_140047040) )
  {
    RtlInitUnicodeString(&DestinationString, L"\\??\\TPM");
    IoDeleteSymbolicLink(&DestinationString);
    v2 = (*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           a1,
           off_140047040);
    v3 = (TpmDevice *)v2;
    qword_140047DB8 = 0;
    if ( TpmTransportType::m_Version == 1 )
    {
      v4 = (TpmScheduler *)(v2 + 888);
      TpmScheduler::Cancel((TpmScheduler *)(v2 + 888), 0, 0);
      TpmScheduler::Stop(v4, 0);
    }
    TpmDevice::~TpmDevice(v3);
    memset(v3, 0, 0x4B0u);
  }
  v5 = (TpmStack *)(*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
                     WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                     a1,
                     off_140047018);
  if ( v5 )
    TpmStack::~TpmStack(v5);
  v6 = g_TpmTaskTrigger;
  if ( g_TpmTaskTrigger )
  {
    TpmTaskTrigger::~TpmTaskTrigger(g_TpmTaskTrigger);
    TpmFree(v6);
    g_TpmTaskTrigger = 0;
  }
}

```

## disassembly

```asm
0x14001d940  mov     [rsp+arg_0], rbx
0x14001d945  mov     [rsp+arg_8], rsi
0x14001d94a  push    rdi
0x14001d94b  sub     rsp, 30h
0x14001d94f  xorps   xmm0, xmm0
0x14001d952  mov     rdi, rcx
0x14001d955  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14001d95a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001d961  lea     rax, WPP_GLOBAL_Control
0x14001d968  cmp     rcx, rax
0x14001d96b  jz      short loc_14001D98C
0x14001d96d  mov     eax, [rcx+2Ch]
0x14001d970  test    al, 8
0x14001d972  jz      short loc_14001D98C
0x14001d974  mov     rcx, [rcx+18h]
0x14001d978  lea     r8, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids
0x14001d97f  mov     edx, 10h
0x14001d984  mov     r9, rdi
0x14001d987  call    WPP_SF_q
0x14001d98c  cmp     cs:qword_140047DB8, 0
0x14001d994  jz      loc_14001DA65
0x14001d99a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001d9a1  mov     rdx, rdi
0x14001d9a4  mov     r8, cs:off_140047040
0x14001d9ab  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001d9b2  mov     rax, [rax+650h]
0x14001d9b9  call    _guard_dispatch_icall
0x14001d9be  cmp     cs:qword_140047DB8, rax
0x14001d9c5  jnz     loc_14001DA65
0x14001d9cb  lea     rdx, aTpm; "\\??\\TPM"
0x14001d9d2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14001d9d7  call    cs:__imp_RtlInitUnicodeString
0x14001d9de  nop     dword ptr [rax+rax+00h]
0x14001d9e3  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x14001d9e8  call    cs:__imp_IoDeleteSymbolicLink
0x14001d9ef  nop     dword ptr [rax+rax+00h]
0x14001d9f4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001d9fb  mov     rdx, rdi
0x14001d9fe  mov     r8, cs:off_140047040
0x14001da05  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001da0c  mov     rax, [rax+650h]
0x14001da13  call    _guard_dispatch_icall
0x14001da18  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 1; TpmTransportType::VERSION TpmTransportType::m_Version
0x14001da1f  mov     rsi, rax
0x14001da22  mov     cs:qword_140047DB8, 0
0x14001da2d  jnz     short loc_14001DA4D
0x14001da2f  lea     rbx, [rax+378h]
0x14001da36  xor     r8d, r8d; bool
0x14001da39  mov     rcx, rbx; this
0x14001da3c  xor     edx, edx; struct TpmContext *
0x14001da3e  call    ?Cancel@TpmScheduler@@QEAAXPEAVTpmContext@@_N@Z; TpmScheduler::Cancel(TpmContext *,bool)
0x14001da43  xor     edx, edx; int
0x14001da45  mov     rcx, rbx; this
0x14001da48  call    ?Stop@TpmScheduler@@QEAAXH@Z; TpmScheduler::Stop(int)
0x14001da4d  mov     rcx, rsi; this
0x14001da50  call    ??1TpmDevice@@QEAA@XZ; TpmDevice::~TpmDevice(void)
0x14001da55  xor     edx, edx; Val
0x14001da57  mov     r8d, 4B0h; Size
0x14001da5d  mov     rcx, rsi; void *
0x14001da60  call    memset
0x14001da65  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001da6c  mov     rdx, rdi
0x14001da6f  mov     r8, cs:off_140047018
0x14001da76  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001da7d  mov     rax, [rax+650h]
0x14001da84  call    _guard_dispatch_icall
0x14001da89  test    rax, rax
0x14001da8c  jz      short loc_14001DA96
0x14001da8e  mov     rcx, rax; this
0x14001da91  call    ??1TpmStack@@AEAA@XZ; TpmStack::~TpmStack(void)
0x14001da96  mov     rbx, cs:g_TpmTaskTrigger
0x14001da9d  test    rbx, rbx
0x14001daa0  jz      short loc_14001DABD
0x14001daa2  mov     rcx, rbx; this
0x14001daa5  call    ??1TpmTaskTrigger@@QEAA@XZ; TpmTaskTrigger::~TpmTaskTrigger(void)
0x14001daaa  mov     rcx, rbx; void *
0x14001daad  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14001dab2  mov     cs:g_TpmTaskTrigger, 0
0x14001dabd  mov     rbx, [rsp+38h+arg_0]
0x14001dac2  mov     rsi, [rsp+38h+arg_8]
0x14001dac7  add     rsp, 30h
0x14001dacb  pop     rdi
0x14001dacc  retn
```
