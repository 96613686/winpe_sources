# VmsVrssInitializeRssQueue

- ea: `0x1401b10fc`
- end: `0x1401b12af`
- name: `VmsVrssInitializeRssQueue`
- size: `435`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1401ad174`

## callees

- `0x14005555c`
- `0x140078270`
- `0x1401b10fc`
- `0x1401b1390`
- `0x1401b1404`
- `0x1401b18c4`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1401b113f`
- `ntoskrnl!InitializeSListHead` at `0x1401b1152`
- `ntoskrnl!InitializeSListHead` at `0x1401b113f`
- `ntoskrnl!InitializeSListHead` at `0x1401b1152`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b1204`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b122f`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b1204`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x1401b122f`
- `ntoskrnl!KeInitializeDpc` at `0x1401b11d9`
- `ntoskrnl!KeInitializeDpc` at `0x1401b11d9`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x1401b11a8`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x1401b11a8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b112c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b112c`

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
0x1401b10fc  push    rbx
0x1401b10fe  push    rsi
0x1401b10ff  push    rdi
0x1401b1100  push    r14
0x1401b1102  sub     rsp, 58h
0x1401b1106  lea     rdi, [rcx+240h]
0x1401b110d  mov     rsi, rcx
0x1401b1110  lea     rcx, [rdi+150h]; SpinLock
0x1401b1117  mov     dword ptr [rdi+0F8h], 0
0x1401b1121  mov     qword ptr [rdi+0F0h], 0
0x1401b112c  call    cs:__imp_KeInitializeSpinLock
0x1401b1133  nop     dword ptr [rax+rax+00h]
0x1401b1138  lea     rcx, [rdi+0E0h]; SListHead
0x1401b113f  call    cs:__imp_InitializeSListHead
0x1401b1146  nop     dword ptr [rax+rax+00h]
0x1401b114b  lea     rcx, [rdi+160h]; SListHead
0x1401b1152  call    cs:__imp_InitializeSListHead
0x1401b1159  nop     dword ptr [rax+rax+00h]
0x1401b115e  lea     rax, [rdi+140h]
0x1401b1165  mov     [rax+8], rax
0x1401b1169  lea     r14, [rsi+4]
0x1401b116d  mov     [rax], rax
0x1401b1170  mov     rcx, r14; ProcNumber
0x1401b1173  lea     rax, [rdi+100h]
0x1401b117a  mov     [rax+8], rax
0x1401b117e  mov     [rax], rax
0x1401b1181  mov     dword ptr [rdi+180h], 0
0x1401b118b  mov     dword ptr [rdi+158h], 0
0x1401b1195  mov     dword ptr [rdi+110h], 0
0x1401b119f  mov     eax, [r14]
0x1401b11a2  mov     [rdi+0D8h], eax
0x1401b11a8  call    cs:__imp_KeGetProcessorIndexFromNumber
0x1401b11af  nop     dword ptr [rax+rax+00h]
0x1401b11b4  mov     rcx, rdi
0x1401b11b7  mov     [rdi+0FCh], eax
0x1401b11bd  call    VmsVrssAllocateNblGroupPool
0x1401b11c2  mov     ebx, eax
0x1401b11c4  test    eax, eax
0x1401b11c6  js      loc_1401B125B
0x1401b11cc  mov     r8, rsi; DeferredContext
0x1401b11cf  lea     rdx, VmsVrssDpc; DeferredRoutine
0x1401b11d6  mov     rcx, rdi; Dpc
0x1401b11d9  call    cs:__imp_KeInitializeDpc
0x1401b11e0  nop     dword ptr [rax+rax+00h]
0x1401b11e5  mov     rdx, rsi
0x1401b11e8  mov     rcx, rdi; Dpc
0x1401b11eb  call    VmsVrssPvtConfigureDpc
0x1401b11f0  lea     rbx, [rsi+2C0h]
0x1401b11f7  mov     r8, rsi; DeferredContext
0x1401b11fa  mov     rcx, rbx; Dpc
0x1401b11fd  lea     rdx, VmsVrssStandardThreadedDpc; DeferredRoutine
0x1401b1204  call    cs:__imp_KeInitializeThreadedDpc
0x1401b120b  nop     dword ptr [rax+rax+00h]
0x1401b1210  mov     rdx, rsi
0x1401b1213  mov     rcx, rbx; Dpc
0x1401b1216  call    VmsVrssPvtConfigureDpc
0x1401b121b  lea     rbx, [rsi+280h]
0x1401b1222  mov     r8, rsi; DeferredContext
0x1401b1225  mov     rcx, rbx; Dpc
0x1401b1228  lea     rdx, VmsVrssExclusiveThreadedDpc; DeferredRoutine
0x1401b122f  call    cs:__imp_KeInitializeThreadedDpc
0x1401b1236  nop     dword ptr [rax+rax+00h]
0x1401b123b  mov     rdx, rsi
0x1401b123e  mov     rcx, rbx; Dpc
0x1401b1241  call    VmsVrssPvtConfigureDpc
0x1401b1246  mov     rcx, rsi; StartContext
0x1401b1249  call    VmsVrssPvtCreateWorkerThread
0x1401b124e  mov     ebx, eax
0x1401b1250  test    eax, eax
0x1401b1252  jns     short loc_1401B12AB
0x1401b1254  and     cs:VmsExecutionMode, 0FFFFFFF0h
0x1401b125b  movzx   eax, byte ptr [rsi+6]
0x1401b125f  mov     r9d, 16h
0x1401b1265  movzx   edx, word ptr [r14]
0x1401b1269  mov     rcx, cs:VmsVrssIfrLog
0x1401b1270  mov     [rsp+78h+var_38], ebx
0x1401b1274  mov     [rsp+78h+var_40], rdi
0x1401b1279  lea     r8d, [r9-13h]
0x1401b127d  mov     [rsp+78h+var_48], eax
0x1401b1281  lea     rax, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1288  mov     [rsp+78h+var_50], edx
0x1401b128c  mov     [rsp+78h+var_58], rax
0x1401b1291  call    WPP_RECORDER_SF_ddqd
0x1401b1296  mov     rcx, rdi
0x1401b1299  call    VmsVrssUninitializeRssQueue
0x1401b129e  mov     eax, ebx
0x1401b12a0  add     rsp, 58h
0x1401b12a4  pop     r14
0x1401b12a6  pop     rdi
0x1401b12a7  pop     rsi
0x1401b12a8  pop     rbx
0x1401b12a9  retn
0x1401b12ab  xor     ebx, ebx
0x1401b12ad  jmp     short loc_1401B129E
```
