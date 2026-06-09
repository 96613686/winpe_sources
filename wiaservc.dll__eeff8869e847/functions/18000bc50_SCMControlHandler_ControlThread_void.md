# SCMControlHandler::ControlThread(void *)

- ea: `0x18000bc50`
- end: `0x18000c02c`
- name: `?ControlThread@SCMControlHandler@@KAKPEAX@Z`
- size: `988`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000de60`

## callees

- `0x18000ab74`
- `0x18000ac34`
- `0x18000bc50`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18001e55c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000be5d`
- `KERNEL32!LeaveCriticalSection` at `0x18000bf11`
- `KERNEL32!LeaveCriticalSection` at `0x18000be5d`
- `KERNEL32!LeaveCriticalSection` at `0x18000bf11`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bd07`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bd07`

## string_xrefs

- `0x18000bcb1`: `Requests queue empty, control thread entering sleep...`
- `0x18000bcd7`: `Requests queue empty, control thread entering sleep...`
- `0x18000bd19`: `Resuming control thread...`
- `0x18000bd3b`: `Resuming control thread...`
- `0x18000bec0`: `Request processing complete`
- `0x18000bee6`: `Request processing complete`
- `0x18000bf1a`: `Service control thread finished returning 0x%08X`
- `0x18000bf43`: `Service control thread finished returning 0x%08X`
- `0x18000be68`: `Terminating control thread`
- `0x18000be8a`: `Terminating control thread`
- `0x18000bc74`: `SCMControlHandler::ControlThread`
- `0x18000bf64`: `SCMControlHandler::ControlThread`
- `0x18000bf58`: `Incorrect parameter, control thread terminated`
- `0x18000bf81`: `Incorrect parameter, control thread terminated`

## pseudocode

```c
__int64 __fastcall SCMControlHandler::ControlThread(HANDLE *Parameter)
{
  struct SCMControlQueue::ControlRequest *v2; // rax
  SCMControlQueue::ControlRequest *v3; // rsi
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r15
  int v15; // r12d
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // edx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  int v29; // r9d
  char *v31; // rbx
  void *v32; // rdx
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rcx
  char *v36; // rbx
  void *v37; // rdx
  char *v38; // rbx
  void *v39; // rdx
  char *v40; // rbx
  void *v41; // rdx
  void **v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  HANDLE Handles[11]; // [rsp+30h] [rbp-58h] BYREF

  if ( !Parameter )
  {
    v38 = (char *)WiaTrace_TraceLog("Incorrect parameter, control thread terminated");
    WriteDbgTraceErrorWI("SCMControlHandler::ControlThread", v38);
    WiaTrcLib::Free((WiaTrcLib *)v38, v39);
    v26 = (void **)WiaTrace_Trace("Incorrect parameter, control thread terminated");
    v29 = 1;
    goto LABEL_13;
  }
  Handles[0] = Parameter[26];
  Handles[1] = Parameter[27];
  while ( 1 )
  {
    while ( 1 )
    {
      v2 = SCMControlQueue::Pop((SCMControlQueue *)(Parameter + 17));
      v3 = v2;
      if ( v2 )
        break;
      if ( !Parameter[25] )
      {
        v45 = (char *)WiaTrace_TraceLog("Queue empty, no control request to process");
        WriteDbgTraceErrorWI("SCMControlHandler::ControlThread", v45);
        WiaTrcLib::Free((WiaTrcLib *)v45, v46);
        v47 = (void **)WiaTrace_Trace("Queue empty, no control request to process");
        WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"SCMControlHandler::ControlThread", 1, v47);
        goto LABEL_16;
      }
      v4 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                     0,
                     0,
                     "Requests queue empty, control thread entering sleep...");
      WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v4);
      WiaTrcLib::Free((WiaTrcLib *)v4, v5);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0,
                         0,
                         "Requests queue empty, control thread entering sleep...");
      WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"SCMControlHandler::ControlThread", 4, lpMem);
      if ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
      {
        v24 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Terminating control thread");
        WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v24);
        WiaTrcLib::Free((WiaTrcLib *)v24, v25);
        v26 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Terminating control thread");
        goto LABEL_12;
      }
      v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Resuming control thread...");
      WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      v11 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Resuming control thread...");
      WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"SCMControlHandler::ControlThread", 4, v11);
    }
    v14 = *((_QWORD *)v2 + 2);
    v15 = CRIT_SECT::Lock((CRIT_SECT *)(v14 + 48));
    if ( !*(_QWORD *)(v14 + 40) )
    {
      v40 = (char *)WiaTrace_TraceLog("There is no handler to process control %u, event type %u");
      WriteDbgTraceErrorWI("SCMControlHandler::ControlThread", v40);
      WiaTrcLib::Free((WiaTrcLib *)v40, v41);
      v42 = (void **)WiaTrace_Trace(
                       "There is no handler to process control %u, event type %u",
                       *(_DWORD *)v3,
                       *((_DWORD *)v3 + 1));
      WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"SCMControlHandler::ControlThread", 1, v42);
      goto LABEL_9;
    }
    v16 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "Processing control request (control: %u, event type: %u)...",
                    *(_DWORD *)v3,
                    *((_DWORD *)v3 + 1));
    WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "Processing control request (control: %u, event type: %u)...",
                     *(_DWORD *)v3,
                     *((_DWORD *)v3 + 1));
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"SCMControlHandler::ControlThread", 4, v18);
    v21 = *(_QWORD *)(v14 + 40) + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)(v14 + 40) + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v14 + 40) + 8LL))(
      *(_QWORD *)(v14 + 40),
      0xFFFFFFFFLL,
      *(unsigned int *)v3,
      *((unsigned int *)v3 + 1),
      *((_QWORD *)v3 + 1));
    v22 = *(_QWORD *)(v14 + 40) + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)(v14 + 40) + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( !Parameter[25] )
      break;
LABEL_9:
    SCMControlQueue::ControlRequest::`scalar deleting destructor'(v3, v23);
    if ( v15 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 48));
  }
  v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Request processing complete");
  WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v31);
  WiaTrcLib::Free((WiaTrcLib *)v31, v32);
  v33 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Request processing complete");
  WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"SCMControlHandler::ControlThread", 4, v33);
  if ( v15 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 48));
LABEL_16:
  v36 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Service control thread finished returning 0x%08X", 0);
  WriteDbgTraceInfoWI("SCMControlHandler::ControlThread", v36);
  WiaTrcLib::Free((WiaTrcLib *)v36, v37);
  v26 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Service control thread finished returning 0x%08X", 0);
LABEL_12:
  v29 = 4;
LABEL_13:
  WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"SCMControlHandler::ControlThread", v29, v26);
  return 0;
}

```

## disassembly

```asm
0x18000bc50  push    rbx
0x18000bc52  push    rbp
0x18000bc53  push    rsi
0x18000bc54  push    rdi
0x18000bc55  push    r12
0x18000bc57  push    r13
0x18000bc59  push    r14
0x18000bc5b  push    r15
0x18000bc5d  sub     rsp, 48h
0x18000bc61  mov     rbp, rcx
0x18000bc64  test    rcx, rcx
0x18000bc67  jz      loc_18000BF58
0x18000bc6d  mov     rax, [rcx+0D0h]
0x18000bc74  lea     rdi, aScmcontrolhand_3; "SCMControlHandler::ControlThread"
0x18000bc7b  mov     [rsp+88h+Handles], rax
0x18000bc80  mov     rax, [rcx+0D8h]
0x18000bc87  mov     [rsp+88h+var_50], rax
0x18000bc8c  lea     rcx, [rbp+88h]; this
0x18000bc93  call    ?Pop@SCMControlQueue@@QEAAPEAUControlRequest@1@XZ; SCMControlQueue::Pop(void)
0x18000bc98  mov     rsi, rax
0x18000bc9b  test    rax, rax
0x18000bc9e  jnz     loc_18000BD61
0x18000bca4  cmp     [rbp+0C8h], rax
0x18000bcab  jz      loc_18000BFE6
0x18000bcb1  lea     r8, aRequestsQueueE; "Requests queue empty, control thread en"...
0x18000bcb8  xor     edx, edx
0x18000bcba  xor     ecx, ecx
0x18000bcbc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bcc1  mov     rdx, rax; char *
0x18000bcc4  mov     rcx, rdi; char *
0x18000bcc7  mov     rbx, rax
0x18000bcca  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bccf  mov     rcx, rbx; this
0x18000bcd2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bcd7  lea     r8, aRequestsQueueE; "Requests queue empty, control thread en"...
0x18000bcde  xor     edx, edx
0x18000bce0  xor     ecx, ecx
0x18000bce2  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bce7  lea     r9d, [rsi+4]; int
0x18000bceb  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bcf0  mov     r8, rdi; int
0x18000bcf3  call    WiaTrace_ProcessTrace_Ex
0x18000bcf8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000bcfc  lea     rdx, [rsp+88h+Handles]; lpHandles
0x18000bd01  xor     r8d, r8d; bWaitAll
0x18000bd04  lea     ecx, [rsi+2]; nCount
0x18000bd07  call    cs:__imp_WaitForMultipleObjects
0x18000bd0d  xor     edx, edx
0x18000bd0f  xor     ecx, ecx
0x18000bd11  test    eax, eax
0x18000bd13  jz      loc_18000BE68
0x18000bd19  lea     r8, aResumingContro; "Resuming control thread..."
0x18000bd20  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bd25  mov     rdx, rax; char *
0x18000bd28  mov     rcx, rdi; char *
0x18000bd2b  mov     rbx, rax
0x18000bd2e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bd33  mov     rcx, rbx; this
0x18000bd36  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bd3b  lea     r8, aResumingContro; "Resuming control thread..."
0x18000bd42  xor     edx, edx
0x18000bd44  xor     ecx, ecx
0x18000bd46  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bd4b  lea     r9d, [rsi+4]; int
0x18000bd4f  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bd54  mov     r8, rdi; int
0x18000bd57  call    WiaTrace_ProcessTrace_Ex
0x18000bd5c  jmp     loc_18000BC8C
0x18000bd61  mov     r15, [rax+10h]
0x18000bd65  lea     r14, [r15+30h]
0x18000bd69  mov     rcx, r14; this
0x18000bd6c  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18000bd71  cmp     qword ptr [r15+28h], 0
0x18000bd76  mov     r12d, eax
0x18000bd79  mov     r8d, [rsi+4]
0x18000bd7d  jz      loc_18000BF98
0x18000bd83  mov     r9d, [rsi]
0x18000bd86  xor     edx, edx
0x18000bd88  mov     dword ptr [rsp+88h+lpMem], r8d
0x18000bd8d  xor     ecx, ecx
0x18000bd8f  lea     r8, aProcessingCont; "Processing control request (control: %u"...
0x18000bd96  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bd9b  mov     rdx, rax; char *
0x18000bd9e  mov     rcx, rdi; char *
0x18000bda1  mov     rbx, rax
0x18000bda4  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bda9  mov     rcx, rbx; this
0x18000bdac  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bdb1  mov     eax, [rsi+4]
0x18000bdb4  lea     r8, aProcessingCont; "Processing control request (control: %u"...
0x18000bdbb  mov     r9d, [rsi]
0x18000bdbe  xor     edx, edx
0x18000bdc0  xor     ecx, ecx
0x18000bdc2  mov     dword ptr [rsp+88h+lpMem], eax
0x18000bdc6  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bdcb  mov     r9d, 4; int
0x18000bdd1  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bdd6  mov     r8, rdi; int
0x18000bdd9  call    WiaTrace_ProcessTrace_Ex
0x18000bdde  mov     rdx, [r15+28h]
0x18000bde2  mov     rax, [rdx+8]
0x18000bde6  add     rdx, 8
0x18000bdea  movsxd  rcx, dword ptr [rax+4]
0x18000bdee  add     rcx, rdx
0x18000bdf1  mov     rax, [rcx]
0x18000bdf4  mov     rax, [rax+8]
0x18000bdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdfd  mov     rdx, [rsi+8]
0x18000be01  mov     rcx, [r15+28h]
0x18000be05  mov     r9d, [rsi+4]
0x18000be09  mov     r8d, [rsi]
0x18000be0c  mov     [rsp+88h+lpMem], rdx
0x18000be11  or      edx, 0FFFFFFFFh
0x18000be14  mov     rax, [rcx]
0x18000be17  mov     rax, [rax+8]
0x18000be1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be20  mov     rdx, [r15+28h]
0x18000be24  mov     rax, [rdx+8]
0x18000be28  add     rdx, 8
0x18000be2c  movsxd  rcx, dword ptr [rax+4]
0x18000be30  add     rcx, rdx
0x18000be33  mov     rax, [rcx]
0x18000be36  mov     rax, [rax+10h]
0x18000be3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3f  cmp     qword ptr [rbp+0C8h], 0
0x18000be47  jz      short loc_18000BEC0
0x18000be49  mov     rcx, rsi; this
0x18000be4c  call    ??_GControlRequest@SCMControlQueue@@QEAAPEAXI@Z; SCMControlQueue::ControlRequest::`scalar deleting destructor'(uint)
0x18000be51  test    r12d, r12d
0x18000be54  jz      loc_18000BC8C
0x18000be5a  mov     rcx, r14; lpCriticalSection
0x18000be5d  call    cs:__imp_LeaveCriticalSection
0x18000be63  jmp     loc_18000BC8C
0x18000be68  lea     r8, aTerminatingCon; "Terminating control thread"
0x18000be6f  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000be74  mov     rdx, rax; char *
0x18000be77  mov     rcx, rdi; char *
0x18000be7a  mov     rbx, rax
0x18000be7d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000be82  mov     rcx, rbx; this
0x18000be85  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000be8a  lea     r8, aTerminatingCon; "Terminating control thread"
0x18000be91  xor     edx, edx
0x18000be93  xor     ecx, ecx
0x18000be95  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000be9a  mov     r9d, 4; int
0x18000bea0  mov     r8, rdi; int
0x18000bea3  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bea8  call    WiaTrace_ProcessTrace_Ex
0x18000bead  xor     eax, eax
0x18000beaf  add     rsp, 48h
0x18000beb3  pop     r15
0x18000beb5  pop     r14
0x18000beb7  pop     r13
0x18000beb9  pop     r12
0x18000bebb  pop     rdi
0x18000bebc  pop     rsi
0x18000bebd  pop     rbp
0x18000bebe  pop     rbx
0x18000bebf  retn
0x18000bec0  lea     r8, aRequestProcess; "Request processing complete"
0x18000bec7  xor     edx, edx
0x18000bec9  xor     ecx, ecx
0x18000becb  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bed0  mov     rdx, rax; char *
0x18000bed3  mov     rcx, rdi; char *
0x18000bed6  mov     rbx, rax
0x18000bed9  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bede  mov     rcx, rbx; this
0x18000bee1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bee6  lea     r8, aRequestProcess; "Request processing complete"
0x18000beed  xor     edx, edx
0x18000beef  xor     ecx, ecx
0x18000bef1  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bef6  mov     r9d, 4; int
0x18000befc  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bf01  mov     r8, rdi; int
0x18000bf04  call    WiaTrace_ProcessTrace_Ex
0x18000bf09  test    r12d, r12d
0x18000bf0c  jz      short loc_18000BF17
0x18000bf0e  mov     rcx, r14; lpCriticalSection
0x18000bf11  call    cs:__imp_LeaveCriticalSection
0x18000bf17  xor     r9d, r9d
0x18000bf1a  lea     r8, aServiceControl_1; "Service control thread finished returni"...
0x18000bf21  xor     edx, edx
0x18000bf23  xor     ecx, ecx
0x18000bf25  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bf2a  mov     rdx, rax; char *
0x18000bf2d  mov     rcx, rdi; char *
0x18000bf30  mov     rbx, rax
0x18000bf33  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bf38  mov     rcx, rbx; this
0x18000bf3b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bf40  xor     r9d, r9d
0x18000bf43  lea     r8, aServiceControl_1; "Service control thread finished returni"...
0x18000bf4a  xor     edx, edx
0x18000bf4c  xor     ecx, ecx
0x18000bf4e  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bf53  jmp     loc_18000BE9A
0x18000bf58  lea     rcx, aIncorrectParam; "Incorrect parameter, control thread ter"...
0x18000bf5f  call    WiaTrace_TraceLog
0x18000bf64  lea     rdi, aScmcontrolhand_3; "SCMControlHandler::ControlThread"
0x18000bf6b  mov     rdx, rax; char *
0x18000bf6e  mov     rcx, rdi; char *
0x18000bf71  mov     rbx, rax
0x18000bf74  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000bf79  mov     rcx, rbx; this
0x18000bf7c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bf81  lea     rcx, aIncorrectParam; "Incorrect parameter, control thread ter"...
0x18000bf88  call    WiaTrace_Trace
0x18000bf8d  mov     r9d, 1
0x18000bf93  jmp     loc_18000BEA0
0x18000bf98  mov     edx, [rsi]
0x18000bf9a  lea     rcx, aThereIsNoHandl; "There is no handler to process control "...
0x18000bfa1  call    WiaTrace_TraceLog
0x18000bfa6  mov     rdx, rax; char *
0x18000bfa9  mov     rcx, rdi; char *
0x18000bfac  mov     rbx, rax
0x18000bfaf  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000bfb4  mov     rcx, rbx; this
0x18000bfb7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bfbc  mov     r8d, [rsi+4]
0x18000bfc0  lea     rcx, aThereIsNoHandl; "There is no handler to process control "...
0x18000bfc7  mov     edx, [rsi]
0x18000bfc9  call    WiaTrace_Trace
0x18000bfce  mov     r9d, 1; int
0x18000bfd4  mov     [rsp+88h+lpMem], rax; lpMem
0x18000bfd9  mov     r8, rdi; int
0x18000bfdc  call    WiaTrace_ProcessTrace_Ex
0x18000bfe1  jmp     loc_18000BE49
0x18000bfe6  lea     rcx, aQueueEmptyNoCo; "Queue empty, no control request to proc"...
0x18000bfed  call    WiaTrace_TraceLog
0x18000bff2  mov     rdx, rax; char *
0x18000bff5  mov     rcx, rdi; char *
0x18000bff8  mov     rbx, rax
0x18000bffb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000c000  mov     rcx, rbx; this
0x18000c003  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c008  lea     rcx, aQueueEmptyNoCo; "Queue empty, no control request to proc"...
0x18000c00f  call    WiaTrace_Trace
0x18000c014  mov     r9d, 1; int
0x18000c01a  mov     [rsp+88h+lpMem], rax; lpMem
0x18000c01f  mov     r8, rdi; int
0x18000c022  call    WiaTrace_ProcessTrace_Ex
0x18000c027  jmp     loc_18000BF17
```
