# StartIOProcessing(void *)

- ea: `0x1800310f0`
- end: `0x180031297`
- name: `?StartIOProcessing@@YAKPEAX@Z`
- size: `423`
- prototype: `__int64 __fastcall(PVOID Parameter, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000db9c`
- `0x180022b54`
- `0x180022b7c`
- `0x1800310f0`
- `0x180031b58`
- `0x180031ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311dd`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180031192`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180031192`

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
0x1800310f0  push    rbp
0x1800310f2  push    rbx
0x1800310f3  push    rsi
0x1800310f4  push    rdi
0x1800310f5  push    r12
0x1800310f7  push    r14
0x1800310f9  push    r15
0x1800310fb  mov     rbp, rsp
0x1800310fe  sub     rsp, 30h
0x180031102  mov     r14, [rcx+40h]
0x180031106  lea     r12, WPP_witness_GLOBAL_Control
0x18003110d  xor     ebx, ebx
0x18003110f  mov     rsi, rcx
0x180031112  mov     [rbp+Overlapped], rbx
0x180031116  mov     [rbp+NumberOfBytesTransferred], ebx
0x180031119  lea     r15d, [rbx+1]
0x18003111d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031124  mov     rax, r15
0x180031127  mov     [rbp+CompletionKey], rax
0x18003112b  mov     rdx, rax
0x18003112e  sub     rdx, r15
0x180031131  jz      short loc_18003117B
0x180031133  sub     rdx, r15
0x180031136  jz      short loc_180031165
0x180031138  cmp     rdx, r15
0x18003113b  jz      short loc_18003115C
0x18003113d  cmp     rcx, r12
0x180031140  jz      short loc_180031124
0x180031142  test    [rcx+1Ch], r15b
0x180031146  jz      short loc_180031124
0x180031148  cmp     byte ptr [rcx+19h], 3
0x18003114c  jb      short loc_180031124
0x18003114e  mov     rcx, [rcx+10h]
0x180031152  mov     r9, rax
0x180031155  call    WPP_SF_i
0x18003115a  jmp     short loc_18003111D
0x18003115c  lea     rdx, ?ProcessInterfaceList@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; ProcessInterfaceList(_TP_CALLBACK_INSTANCE *,void *)
0x180031163  jmp     short loc_18003116C
0x180031165  lea     rdx, ?ProcessWitnessNotifications@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *)
0x18003116c  mov     r8, [rbp+Overlapped]; void *
0x180031170  mov     rcx, [rsi+38h]; this
0x180031174  call    ?SubmitWork@CThreadPool@@QEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; CThreadPool::SubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x180031179  jmp     short loc_18003111D
0x18003117b  lea     r9, [rbp+Overlapped]; lpOverlapped
0x18003117f  mov     [rsp+30h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180031187  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x18003118b  mov     rcx, r14; CompletionPort
0x18003118e  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180031192  call    cs:__imp_GetQueuedCompletionStatus
0x180031198  mov     edi, eax
0x18003119a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800311a1  cmp     rcx, r12
0x1800311a4  jz      short loc_1800311D9
0x1800311a6  test    [rcx+1Ch], r15b
0x1800311aa  jz      short loc_1800311D9
0x1800311ac  cmp     byte ptr [rcx+19h], 3
0x1800311b0  jb      short loc_1800311D9
0x1800311b2  mov     eax, dword ptr [rbp+CompletionKey]
0x1800311b5  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x1800311bc  mov     r9, [rbp+Overlapped]
0x1800311c0  mov     edx, 0Ah
0x1800311c5  mov     rcx, [rcx+10h]
0x1800311c9  mov     [rsp+30h+dwMilliseconds], eax
0x1800311cd  call    WPP_SF_qd
0x1800311d2  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800311d9  test    edi, edi
0x1800311db  jnz     short loc_180031224
0x1800311dd  call    cs:__imp_GetLastError
0x1800311e3  mov     ebx, eax
0x1800311e5  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800311ec  cmp     rcx, r12
0x1800311ef  jz      loc_180031124
0x1800311f5  test    [rcx+1Ch], r15b
0x1800311f9  jz      loc_180031124
0x1800311ff  cmp     [rcx+19h], r15b
0x180031203  jb      loc_180031124
0x180031209  mov     rcx, [rcx+10h]
0x18003120d  lea     edx, [rdi+0Bh]
0x180031210  mov     r9d, eax
0x180031213  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18003121a  call    WPP_SF_d
0x18003121f  jmp     loc_18003111D
0x180031224  mov     rax, [rbp+CompletionKey]
0x180031228  cmp     rax, 4
0x18003122c  jnz     loc_18003112B
0x180031232  cmp     rcx, r12
0x180031235  jz      short loc_180031286
0x180031237  test    [rcx+1Ch], r15b
0x18003123b  jz      short loc_18003125D
0x18003123d  cmp     byte ptr [rcx+19h], 3
0x180031241  jb      short loc_18003125D
0x180031243  mov     rcx, [rcx+10h]
0x180031247  lea     edx, [rax+8]
0x18003124a  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180031251  call    WPP_SF_
0x180031256  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003125d  cmp     rcx, r12
0x180031260  jz      short loc_180031286
0x180031262  test    [rcx+1Ch], r15b
0x180031266  jz      short loc_180031286
0x180031268  cmp     byte ptr [rcx+19h], 3
0x18003126c  jb      short loc_180031286
0x18003126e  mov     rcx, [rcx+10h]
0x180031272  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180031279  mov     edx, 0Eh
0x18003127e  mov     r9d, ebx
0x180031281  call    WPP_SF_d
0x180031286  mov     eax, ebx
0x180031288  add     rsp, 30h
0x18003128c  pop     r15
0x18003128e  pop     r14
0x180031290  pop     r12
0x180031292  pop     rdi
0x180031293  pop     rsi
0x180031294  pop     rbx
0x180031295  pop     rbp
0x180031296  retn
```
