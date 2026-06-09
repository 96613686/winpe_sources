# VmsVrssInitializeRssQueue

- ea: `0x1401b108c`
- end: `0x1401b123f`
- name: `VmsVrssInitializeRssQueue`
- size: `435`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1401ad104`

## callees

- `0x14005555c`
- `0x140078270`
- `0x1401b108c`
- `0x1401b1320`
- `0x1401b1394`
- `0x1401b1854`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1401b10cf`
- `ntoskrnl!InitializeSListHead` at `0x1401b10e2`
- `ntoskrnl!InitializeSListHead` at `0x1401b10cf`
- `ntoskrnl!InitializeSListHead` at `0x1401b10e2`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b1194`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b11bf`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b1194`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b11bf`
- `ntoskrnl!KeInitializeDpc` at `0x1401b1169`
- `ntoskrnl!KeInitializeDpc` at `0x1401b1169`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x1401b1138`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x1401b1138`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b10bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b10bc`

## pseudocode

```c
__int64 __fastcall VmsVrssInitializeRssQueue(char *StartContext)
{
  union _SLIST_HEADER *v1; // rdi
  int NblGroupPool; // ebx

  v1 = (union _SLIST_HEADER *)(StartContext + 576);
  *((_DWORD *)StartContext + 206) = 0;
  *((_QWORD *)StartContext + 102) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)StartContext + 114);
  InitializeSListHead(v1 + 14);
  InitializeSListHead(v1 + 22);
  v1[20].Region = (unsigned __int64)&v1[20];
  v1[20].Alignment = (unsigned __int64)&v1[20];
  v1[16].Region = (unsigned __int64)&v1[16];
  v1[16].Alignment = (unsigned __int64)&v1[16];
  LODWORD(v1[24].Alignment) = 0;
  *((_DWORD *)&v1[21].HeaderX64 + 2) = 0;
  LODWORD(v1[17].Alignment) = 0;
  *((_DWORD *)&v1[13].HeaderX64 + 2) = *((_DWORD *)StartContext + 1);
  *((_DWORD *)&v1[15].HeaderX64 + 3) = KeGetProcessorIndexFromNumber((PPROCESSOR_NUMBER)StartContext + 1);
  NblGroupPool = VmsVrssAllocateNblGroupPool(v1);
  if ( NblGroupPool >= 0 )
  {
    KeInitializeDpc((PRKDPC)v1, (PKDEFERRED_ROUTINE)VmsVrssDpc, StartContext);
    VmsVrssPvtConfigureDpc((PRKDPC)v1);
    KeInitializeThreadedDpc((PRKDPC)StartContext + 11, VmsVrssStandardThreadedDpc, StartContext);
    VmsVrssPvtConfigureDpc((PRKDPC)StartContext + 11);
    KeInitializeThreadedDpc((PRKDPC)StartContext + 10, VmsVrssExclusiveThreadedDpc, StartContext);
    VmsVrssPvtConfigureDpc((PRKDPC)StartContext + 10);
    NblGroupPool = VmsVrssPvtCreateWorkerThread((struct _KEVENT *)StartContext);
    if ( NblGroupPool >= 0 )
      return 0;
    VmsExecutionMode &= 0xFFFFFFF0;
  }
  WPP_RECORDER_SF_ddqd(
    VmsVrssIfrLog,
    *((unsigned __int16 *)StartContext + 2),
    3,
    22,
    (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
    *((_WORD *)StartContext + 2),
    StartContext[6],
    (char)v1,
    NblGroupPool);
  VmsVrssUninitializeRssQueue(v1);
  return (unsigned int)NblGroupPool;
}

```

## disassembly

```asm
0x1401b108c  push    rbx
0x1401b108e  push    rsi
0x1401b108f  push    rdi
0x1401b1090  push    r14
0x1401b1092  sub     rsp, 58h
0x1401b1096  lea     rdi, [rcx+240h]
0x1401b109d  mov     rsi, rcx
0x1401b10a0  lea     rcx, [rdi+150h]; SpinLock
0x1401b10a7  mov     dword ptr [rdi+0F8h], 0
0x1401b10b1  mov     qword ptr [rdi+0F0h], 0
0x1401b10bc  call    cs:__imp_KeInitializeSpinLock
0x1401b10c3  nop     dword ptr [rax+rax+00h]
0x1401b10c8  lea     rcx, [rdi+0E0h]; SListHead
0x1401b10cf  call    cs:__imp_InitializeSListHead
0x1401b10d6  nop     dword ptr [rax+rax+00h]
0x1401b10db  lea     rcx, [rdi+160h]; SListHead
0x1401b10e2  call    cs:__imp_InitializeSListHead
0x1401b10e9  nop     dword ptr [rax+rax+00h]
0x1401b10ee  lea     rax, [rdi+140h]
0x1401b10f5  mov     [rax+8], rax
0x1401b10f9  lea     r14, [rsi+4]
0x1401b10fd  mov     [rax], rax
0x1401b1100  mov     rcx, r14; ProcNumber
0x1401b1103  lea     rax, [rdi+100h]
0x1401b110a  mov     [rax+8], rax
0x1401b110e  mov     [rax], rax
0x1401b1111  mov     dword ptr [rdi+180h], 0
0x1401b111b  mov     dword ptr [rdi+158h], 0
0x1401b1125  mov     dword ptr [rdi+110h], 0
0x1401b112f  mov     eax, [r14]
0x1401b1132  mov     [rdi+0D8h], eax
0x1401b1138  call    cs:__imp_KeGetProcessorIndexFromNumber
0x1401b113f  nop     dword ptr [rax+rax+00h]
0x1401b1144  mov     rcx, rdi
0x1401b1147  mov     [rdi+0FCh], eax
0x1401b114d  call    VmsVrssAllocateNblGroupPool
0x1401b1152  mov     ebx, eax
0x1401b1154  test    eax, eax
0x1401b1156  js      loc_1401B11EB
0x1401b115c  mov     r8, rsi; DeferredContext
0x1401b115f  lea     rdx, VmsVrssDpc; DeferredRoutine
0x1401b1166  mov     rcx, rdi; Dpc
0x1401b1169  call    cs:__imp_KeInitializeDpc
0x1401b1170  nop     dword ptr [rax+rax+00h]
0x1401b1175  mov     rdx, rsi
0x1401b1178  mov     rcx, rdi; Dpc
0x1401b117b  call    VmsVrssPvtConfigureDpc
0x1401b1180  lea     rbx, [rsi+2C0h]
0x1401b1187  mov     r8, rsi; DeferredContext
0x1401b118a  mov     rcx, rbx; Dpc
0x1401b118d  lea     rdx, VmsVrssStandardThreadedDpc; DeferredRoutine
0x1401b1194  call    cs:__imp_KeInitializeThreadedDpc
0x1401b119b  nop     dword ptr [rax+rax+00h]
0x1401b11a0  mov     rdx, rsi
0x1401b11a3  mov     rcx, rbx; Dpc
0x1401b11a6  call    VmsVrssPvtConfigureDpc
0x1401b11ab  lea     rbx, [rsi+280h]
0x1401b11b2  mov     r8, rsi; DeferredContext
0x1401b11b5  mov     rcx, rbx; Dpc
0x1401b11b8  lea     rdx, VmsVrssExclusiveThreadedDpc; DeferredRoutine
0x1401b11bf  call    cs:__imp_KeInitializeThreadedDpc
0x1401b11c6  nop     dword ptr [rax+rax+00h]
0x1401b11cb  mov     rdx, rsi
0x1401b11ce  mov     rcx, rbx; Dpc
0x1401b11d1  call    VmsVrssPvtConfigureDpc
0x1401b11d6  mov     rcx, rsi; StartContext
0x1401b11d9  call    VmsVrssPvtCreateWorkerThread
0x1401b11de  mov     ebx, eax
0x1401b11e0  test    eax, eax
0x1401b11e2  jns     short loc_1401B123B
0x1401b11e4  and     cs:VmsExecutionMode, 0FFFFFFF0h
0x1401b11eb  movzx   eax, byte ptr [rsi+6]
0x1401b11ef  mov     r9d, 16h
0x1401b11f5  movzx   edx, word ptr [r14]
0x1401b11f9  mov     rcx, cs:VmsVrssIfrLog
0x1401b1200  mov     [rsp+78h+var_38], ebx
0x1401b1204  mov     [rsp+78h+var_40], rdi
0x1401b1209  lea     r8d, [r9-13h]
0x1401b120d  mov     [rsp+78h+var_48], eax
0x1401b1211  lea     rax, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1218  mov     [rsp+78h+var_50], edx
0x1401b121c  mov     [rsp+78h+var_58], rax
0x1401b1221  call    WPP_RECORDER_SF_ddqd
0x1401b1226  mov     rcx, rdi
0x1401b1229  call    VmsVrssUninitializeRssQueue
0x1401b122e  mov     eax, ebx
0x1401b1230  add     rsp, 58h
0x1401b1234  pop     r14
0x1401b1236  pop     rdi
0x1401b1237  pop     rsi
0x1401b1238  pop     rbx
0x1401b1239  retn
0x1401b123b  xor     ebx, ebx
0x1401b123d  jmp     short loc_1401B122E
```
