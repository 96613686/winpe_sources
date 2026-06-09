# TmpTxActionDoCommitComplete

- ea: `0x14000c010`
- end: `0x14000c137`
- name: `TmpTxActionDoCommitComplete`
- size: `295`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020dd4`

## callees

- `0x14000117c`
- `0x14000c010`
- `0x14000c140`
- `0x140011300`
- `0x14001b658`
- `0x14001f3e8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c0a6`
- `ntoskrnl!KeSetEvent` at `0x14000c10b`
- `ntoskrnl!KeSetEvent` at `0x14000c0a6`
- `ntoskrnl!KeSetEvent` at `0x14000c10b`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoCommitComplete(struct _KEVENT *Object, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  void *v5; // rcx

  v3 = 0;
  if ( Object[8].Header.LockNV == 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_q_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        17,
        a3,
        (_DWORD)Object,
        (__int64)&Object[7].Header.WaitListHead);
    Object[8].Header.LockNV = 5;
    Object[21].Header.LockNV = 2;
    TmpNotifyAllEnlistmentsTransaction(Object, 4, a3, 261);
  }
  else if ( (Object[8].Header.SignalState & 0x800000) != 0 )
  {
    TmpLogTransaction((__int64)Object, 4, 0);
  }
  KeSetEvent(Object, 0, 0);
  v5 = *(void **)&Object[10].Header.Lock;
  if ( v5 )
    v3 = TmpNotifyEnlistment(v5, 260);
  if ( (HIDWORD(Object[3].Header.WaitListHead.Blink[12].Flink) & 0x20000) != 0
    && (struct _KEVENT *)Object[3].Header.WaitListHead.Blink == Object
    && _InterlockedExchangeAdd(&TmpTransactionsCommittedActive, 0xFFFFFFFF) == 1 )
  {
    KeSetEvent(&TmpTransactionFreezeCompleteEvent, 0, 0);
  }
  Object[8].Header.LockNV = 9;
  TmpFinalizeTransaction(Object);
  return v3;
}

```

## disassembly

```asm
0x14000c010  mov     [rsp+arg_0], rbx
0x14000c015  push    rdi
0x14000c016  sub     rsp, 40h
0x14000c01a  xor     edi, edi
0x14000c01c  mov     rbx, rcx
0x14000c01f  cmp     dword ptr [rcx+0C0h], 7
0x14000c026  jnz     short loc_14000C086
0x14000c028  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c02f  lea     rax, WPP_GLOBAL_Control
0x14000c036  cmp     rcx, rax
0x14000c039  jz      short loc_14000C05D
0x14000c03b  mov     eax, [rcx+2Ch]
0x14000c03e  test    al, 4
0x14000c040  jz      short loc_14000C05D
0x14000c042  mov     rcx, [rcx+18h]
0x14000c046  lea     rax, [rbx+0B0h]
0x14000c04d  lea     edx, [rdi+11h]
0x14000c050  mov     qword ptr [rsp+48h+var_28], rax
0x14000c055  mov     r9, rbx
0x14000c058  call    WPP_SF_q_guid_
0x14000c05d  mov     edx, 4
0x14000c062  mov     dword ptr [rbx+0C0h], 5
0x14000c06c  mov     r9d, 105h
0x14000c072  mov     dword ptr [rbx+1F8h], 2
0x14000c07c  mov     rcx, rbx
0x14000c07f  call    TmpNotifyAllEnlistmentsTransaction
0x14000c084  jmp     short loc_14000C09E
0x14000c086  mov     eax, [rcx+0C4h]
0x14000c08c  bt      eax, 17h
0x14000c090  jnb     short loc_14000C09E
0x14000c092  xor     r8d, r8d
0x14000c095  lea     edx, [r8+4]
0x14000c099  call    TmpLogTransaction
0x14000c09e  xor     r8d, r8d; Wait
0x14000c0a1  xor     edx, edx; Increment
0x14000c0a3  mov     rcx, rbx; Event
0x14000c0a6  call    cs:__imp_KeSetEvent
0x14000c0ad  nop     dword ptr [rax+rax+00h]
0x14000c0b2  mov     rcx, [rbx+0F0h]; Object
0x14000c0b9  test    rcx, rcx
0x14000c0bc  jz      short loc_14000C0D9
0x14000c0be  mov     r9b, 1
0x14000c0c1  mov     [rsp+48h+var_28], 104h; int
0x14000c0c9  mov     dl, r9b
0x14000c0cc  mov     r8d, 40h ; '@'
0x14000c0d2  call    TmpNotifyEnlistment
0x14000c0d7  mov     edi, eax
0x14000c0d9  mov     rcx, [rbx+58h]
0x14000c0dd  mov     edx, [rcx+0C4h]
0x14000c0e3  bt      edx, 11h
0x14000c0e7  jnb     short loc_14000C117
0x14000c0e9  cmp     [rbx+58h], rbx
0x14000c0ed  jnz     short loc_14000C117
0x14000c0ef  or      ecx, 0FFFFFFFFh
0x14000c0f2  lock xadd cs:TmpTransactionsCommittedActive, ecx
0x14000c0fa  cmp     ecx, 1
0x14000c0fd  jnz     short loc_14000C117
0x14000c0ff  xor     r8d, r8d; Wait
0x14000c102  lea     rcx, TmpTransactionFreezeCompleteEvent; Event
0x14000c109  xor     edx, edx; Increment
0x14000c10b  call    cs:__imp_KeSetEvent
0x14000c112  nop     dword ptr [rax+rax+00h]
0x14000c117  mov     rcx, rbx; Object
0x14000c11a  mov     dword ptr [rbx+0C0h], 9
0x14000c124  call    TmpFinalizeTransaction
0x14000c129  mov     rbx, [rsp+48h+arg_0]
0x14000c12e  mov     eax, edi
0x14000c130  add     rsp, 40h
0x14000c134  pop     rdi
0x14000c135  retn
```
