# MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)

- ea: `0x18000e4c4`
- end: `0x18000e591`
- name: `?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z`
- size: `205`
- prototype: `__int64 __fastcall(MULTI_WORK_QUEUE *this, struct MULTI_WORK_DISPATCH *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008730`
- `0x18000b324`
- `0x18000c3a4`
- `0x18000c860`
- `0x18000e1a0`

## callees

- `0x18000e4c4`
- `0x18000e598`
- `0x18000e6d8`
- `0x180010010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000e580`
- `iisutil!PuDbgPrintError` at `0x18000e580`

## string_xrefs

- `0x18000e575`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_queue.cxx`

## pseudocode

```c
__int64 __fastcall MULTI_WORK_QUEUE::GetAndQueueWorkItem(
        MULTI_WORK_QUEUE *this,
        struct MULTI_WORK_DISPATCH *a2,
        __int64 a3)
{
  int BlankWorkItem; // ebx
  struct MULTI_WORK_ITEM *v7; // rbx
  __int64 v8; // rcx
  struct MULTI_WORK_ITEM *v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  BlankWorkItem = MULTI_WORK_QUEUE::GetBlankWorkItem(this, &v10);
  if ( BlankWorkItem >= 0 )
  {
    v7 = v10;
    v8 = *((_QWORD *)v10 + 3);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *((_QWORD *)v7 + 3) = a2;
    (**(void (__fastcall ***)(struct MULTI_WORK_DISPATCH *))a2)(a2);
    *((_QWORD *)v7 + 2) = a3;
    BlankWorkItem = MULTI_WORK_QUEUE::QueueWorkItem(this, v7);
    if ( BlankWorkItem < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
        387,
        "MULTI_WORK_QUEUE::GetAndQueueWorkItem",
        BlankWorkItem,
        "Could not queue work item\n");
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
      368,
      "MULTI_WORK_QUEUE::GetAndQueueWorkItem",
      BlankWorkItem,
      "Could not get a blank work item\n");
  }
  return (unsigned int)BlankWorkItem;
}

```

## disassembly

```asm
0x18000e4c4  push    rbx
0x18000e4c6  push    rbp
0x18000e4c7  push    rsi
0x18000e4c8  push    rdi
0x18000e4c9  sub     rsp, 38h
0x18000e4cd  mov     rsi, rdx
0x18000e4d0  mov     [rsp+58h+arg_18], 0
0x18000e4d9  lea     rdx, [rsp+58h+arg_18]; struct MULTI_WORK_ITEM **
0x18000e4de  mov     rbp, r8
0x18000e4e1  mov     rdi, rcx
0x18000e4e4  call    ?GetBlankWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAPEAVMULTI_WORK_ITEM@@@Z; MULTI_WORK_QUEUE::GetBlankWorkItem(MULTI_WORK_ITEM * *)
0x18000e4e9  mov     ebx, eax
0x18000e4eb  test    eax, eax
0x18000e4ed  jns     short loc_18000E50B
0x18000e4ef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e4f6  jz      loc_18000E586
0x18000e4fc  lea     rax, aCouldNotGetABl; "Could not get a blank work item\n"
0x18000e503  mov     r8d, 170h
0x18000e509  jmp     short loc_18000E562
0x18000e50b  mov     rbx, [rsp+58h+arg_18]
0x18000e510  mov     rcx, [rbx+18h]
0x18000e514  test    rcx, rcx
0x18000e517  jz      short loc_18000E525
0x18000e519  mov     rax, [rcx]
0x18000e51c  mov     rax, [rax+8]
0x18000e520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e525  mov     [rbx+18h], rsi
0x18000e529  mov     rcx, rsi
0x18000e52c  mov     rax, [rsi]
0x18000e52f  mov     rax, [rax]
0x18000e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e537  mov     rdx, rbx; struct MULTI_WORK_ITEM *
0x18000e53a  mov     [rbx+10h], rbp
0x18000e53e  mov     rcx, rdi; this
0x18000e541  call    ?QueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_ITEM@@@Z; MULTI_WORK_QUEUE::QueueWorkItem(MULTI_WORK_ITEM *)
0x18000e546  mov     ebx, eax
0x18000e548  test    eax, eax
0x18000e54a  jns     short loc_18000E586
0x18000e54c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e553  jz      short loc_18000E586
0x18000e555  lea     rax, aCouldNotQueueW; "Could not queue work item\n"
0x18000e55c  mov     r8d, 183h
0x18000e562  mov     rcx, cs:g_pDebug
0x18000e569  lea     r9, aMultiWorkQueue; "MULTI_WORK_QUEUE::GetAndQueueWorkItem"
0x18000e570  mov     [rsp+58h+var_30], rax
0x18000e575  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e57c  mov     [rsp+58h+var_38], ebx
0x18000e580  call    cs:__imp_PuDbgPrintError
0x18000e586  mov     eax, ebx
0x18000e588  add     rsp, 38h
0x18000e58c  pop     rdi
0x18000e58d  pop     rsi
0x18000e58e  pop     rbp
0x18000e58f  pop     rbx
0x18000e590  retn
```
