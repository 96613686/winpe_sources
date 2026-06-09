# StartIOProcessing(void *)

- ea: `0x180033f30`
- end: `0x1800340e4`
- name: `?StartIOProcessing@@YAKPEAX@Z`
- size: `436`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000e888`
- `0x180024520`
- `0x180024550`
- `0x180033f30`
- `0x18003499c`
- `0x1800349e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034023`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180033fd2`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180033fd2`

## pseudocode

```c
__int64 __fastcall StartIOProcessing(PVOID Parameter, __int64 a2, __int64 a3)
{
  void *v3; // r14
  DWORD v4; // ebx
  PVOID *v6; // rcx
  unsigned __int64 v7; // rax
  void (*v8)(struct _TP_CALLBACK_INSTANCE *, void *); // rdx
  BOOL QueuedCompletionStatus; // edi
  DWORD LastError; // eax
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+48h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+80h] [rbp+50h] BYREF

  v3 = (void *)*((_QWORD *)Parameter + 8);
  v4 = 0;
  Overlapped = 0;
  NumberOfBytesTransferred = 0;
LABEL_2:
  v6 = (PVOID *)WPP_witness_GLOBAL_Control;
LABEL_3:
  v7 = 1;
  CompletionKey = 1;
  do
  {
    if ( v7 != 1 )
    {
      if ( v7 == 2 )
      {
        v8 = ProcessWitnessNotifications;
      }
      else
      {
        if ( v7 != 3 )
        {
          if ( v6 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 3u )
          {
            WPP_SF_i(v6[2], v7 - 2, a3, v7);
            goto LABEL_2;
          }
          goto LABEL_3;
        }
        v8 = ProcessInterfaceList;
      }
      CThreadPool::SubmitWork(*((CThreadPool **)Parameter + 7), v8, Overlapped);
      goto LABEL_2;
    }
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               v3,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               0xFFFFFFFF);
    v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        10,
        &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        Overlapped,
        CompletionKey);
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    if ( !QueuedCompletionStatus )
    {
      LastError = GetLastError();
      v4 = LastError;
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
          11,
          &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
          LastError);
        goto LABEL_2;
      }
      goto LABEL_3;
    }
    v7 = CompletionKey;
  }
  while ( CompletionKey != 4 );
  if ( v6 != &WPP_witness_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 3u )
    {
      WPP_SF_(v6[2], (unsigned int)(CompletionKey + 8), &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids);
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    if ( v6 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 3u )
      WPP_SF_d(v6[2], 14, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180033f30  push    rbp
0x180033f32  push    rbx
0x180033f33  push    rsi
0x180033f34  push    rdi
0x180033f35  push    r12
0x180033f37  push    r14
0x180033f39  push    r15
0x180033f3b  mov     rbp, rsp
0x180033f3e  sub     rsp, 30h
0x180033f42  mov     r14, [rcx+40h]
0x180033f46  lea     r12, WPP_witness_GLOBAL_Control
0x180033f4d  xor     ebx, ebx
0x180033f4f  mov     rsi, rcx
0x180033f52  mov     [rbp+Overlapped], rbx
0x180033f56  mov     [rbp+NumberOfBytesTransferred], ebx
0x180033f59  lea     r15d, [rbx+1]
0x180033f5d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180033f64  mov     rax, r15
0x180033f67  mov     [rbp+CompletionKey], rax
0x180033f6b  mov     rdx, rax
0x180033f6e  sub     rdx, r15
0x180033f71  jz      short loc_180033FBB
0x180033f73  sub     rdx, r15
0x180033f76  jz      short loc_180033FA5
0x180033f78  cmp     rdx, r15
0x180033f7b  jz      short loc_180033F9C
0x180033f7d  cmp     rcx, r12
0x180033f80  jz      short loc_180033F64
0x180033f82  test    [rcx+1Ch], r15b
0x180033f86  jz      short loc_180033F64
0x180033f88  cmp     byte ptr [rcx+19h], 3
0x180033f8c  jb      short loc_180033F64
0x180033f8e  mov     rcx, [rcx+10h]
0x180033f92  mov     r9, rax
0x180033f95  call    WPP_SF_i
0x180033f9a  jmp     short loc_180033F5D
0x180033f9c  lea     rdx, ?ProcessInterfaceList@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; ProcessInterfaceList(_TP_CALLBACK_INSTANCE *,void *)
0x180033fa3  jmp     short loc_180033FAC
0x180033fa5  lea     rdx, ?ProcessWitnessNotifications@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *)
0x180033fac  mov     r8, [rbp+Overlapped]; void *
0x180033fb0  mov     rcx, [rsi+38h]; this
0x180033fb4  call    ?SubmitWork@CThreadPool@@QEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; CThreadPool::SubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x180033fb9  jmp     short loc_180033F5D
0x180033fbb  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180033fbf  mov     [rsp+30h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180033fc7  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180033fcb  mov     rcx, r14; CompletionPort
0x180033fce  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180033fd2  call    cs:__imp_GetQueuedCompletionStatus
0x180033fd9  nop     dword ptr [rax+rax+00h]
0x180033fde  mov     edi, eax
0x180033fe0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180033fe7  cmp     rcx, r12
0x180033fea  jz      short loc_18003401F
0x180033fec  test    [rcx+1Ch], r15b
0x180033ff0  jz      short loc_18003401F
0x180033ff2  cmp     byte ptr [rcx+19h], 3
0x180033ff6  jb      short loc_18003401F
0x180033ff8  mov     eax, dword ptr [rbp+CompletionKey]
0x180033ffb  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180034002  mov     r9, [rbp+Overlapped]
0x180034006  mov     edx, 0Ah
0x18003400b  mov     rcx, [rcx+10h]
0x18003400f  mov     [rsp+30h+dwMilliseconds], eax
0x180034013  call    WPP_SF_qd
0x180034018  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003401f  test    edi, edi
0x180034021  jnz     short loc_180034070
0x180034023  call    cs:__imp_GetLastError
0x18003402a  nop     dword ptr [rax+rax+00h]
0x18003402f  mov     ebx, eax
0x180034031  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034038  cmp     rcx, r12
0x18003403b  jz      loc_180033F64
0x180034041  test    [rcx+1Ch], r15b
0x180034045  jz      loc_180033F64
0x18003404b  cmp     [rcx+19h], r15b
0x18003404f  jb      loc_180033F64
0x180034055  mov     rcx, [rcx+10h]
0x180034059  lea     edx, [rdi+0Bh]
0x18003405c  mov     r9d, eax
0x18003405f  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180034066  call    WPP_SF_d
0x18003406b  jmp     loc_180033F5D
0x180034070  mov     rax, [rbp+CompletionKey]
0x180034074  cmp     rax, 4
0x180034078  jnz     loc_180033F6B
0x18003407e  cmp     rcx, r12
0x180034081  jz      short loc_1800340D2
0x180034083  test    [rcx+1Ch], r15b
0x180034087  jz      short loc_1800340A9
0x180034089  cmp     byte ptr [rcx+19h], 3
0x18003408d  jb      short loc_1800340A9
0x18003408f  mov     rcx, [rcx+10h]
0x180034093  lea     edx, [rax+8]
0x180034096  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18003409d  call    WPP_SF_
0x1800340a2  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800340a9  cmp     rcx, r12
0x1800340ac  jz      short loc_1800340D2
0x1800340ae  test    [rcx+1Ch], r15b
0x1800340b2  jz      short loc_1800340D2
0x1800340b4  cmp     byte ptr [rcx+19h], 3
0x1800340b8  jb      short loc_1800340D2
0x1800340ba  mov     rcx, [rcx+10h]
0x1800340be  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x1800340c5  mov     edx, 0Eh
0x1800340ca  mov     r9d, ebx
0x1800340cd  call    WPP_SF_d
0x1800340d2  mov     eax, ebx
0x1800340d4  add     rsp, 30h
0x1800340d8  pop     r15
0x1800340da  pop     r14
0x1800340dc  pop     r12
0x1800340de  pop     rdi
0x1800340df  pop     rsi
0x1800340e0  pop     rbx
0x1800340e1  pop     rbp
0x1800340e2  retn
```
