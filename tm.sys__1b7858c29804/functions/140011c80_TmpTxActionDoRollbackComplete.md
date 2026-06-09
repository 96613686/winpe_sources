# TmpTxActionDoRollbackComplete

- ea: `0x140011c80`
- end: `0x140011d41`
- name: `TmpTxActionDoRollbackComplete`
- size: `193`
- prototype: `__int64 __fastcall(PRKEVENT Event)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000117c`
- `0x140011300`
- `0x140011c80`
- `0x14001b658`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140011ced`
- `ntoskrnl!KeSetEvent` at `0x140011ced`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoRollbackComplete(PRKEVENT Event, __int64 a2, int a3)
{
  unsigned int v3; // edi
  __int64 v5; // r8
  void *v6; // rcx

  v3 = 0;
  if ( Event[8].Header.LockNV == 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_q_guid_(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, a3, (_DWORD)Event, (__int64)&Event[7].Header.WaitListHead);
    Event[8].Header.LockNV = 6;
    Event[21].Header.LockNV = 3;
    KeSetEvent(Event, 0, 0);
    TmpNotifyAllEnlistmentsTransaction(Event, 8, v5, 269);
    v6 = *(void **)&Event[10].Header.Lock;
    if ( v6 )
      return (unsigned int)TmpNotifyEnlistment(v6, 263);
  }
  return v3;
}

```

## disassembly

```asm
0x140011c80  mov     [rsp+arg_0], rbx
0x140011c85  push    rdi
0x140011c86  sub     rsp, 40h
0x140011c8a  xor     edi, edi
0x140011c8c  mov     rbx, rcx
0x140011c8f  cmp     dword ptr [rcx+0C0h], 7
0x140011c96  jnz     loc_140011D33
0x140011c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ca3  lea     rax, WPP_GLOBAL_Control
0x140011caa  cmp     rcx, rax
0x140011cad  jz      short loc_140011CD1
0x140011caf  mov     eax, [rcx+2Ch]
0x140011cb2  test    al, 4
0x140011cb4  jz      short loc_140011CD1
0x140011cb6  mov     rcx, [rcx+18h]
0x140011cba  lea     rax, [rbx+0B0h]
0x140011cc1  lea     edx, [rdi+14h]
0x140011cc4  mov     qword ptr [rsp+48h+var_28], rax
0x140011cc9  mov     r9, rbx
0x140011ccc  call    WPP_SF_q_guid_
0x140011cd1  xor     r8d, r8d; Wait
0x140011cd4  mov     dword ptr [rbx+0C0h], 6
0x140011cde  xor     edx, edx; Increment
0x140011ce0  mov     dword ptr [rbx+1F8h], 3
0x140011cea  mov     rcx, rbx; Event
0x140011ced  call    cs:__imp_KeSetEvent
0x140011cf4  nop     dword ptr [rax+rax+00h]
0x140011cf9  mov     edx, 8
0x140011cfe  mov     r9d, 10Dh
0x140011d04  mov     rcx, rbx
0x140011d07  call    TmpNotifyAllEnlistmentsTransaction
0x140011d0c  mov     rcx, [rbx+0F0h]; Object
0x140011d13  test    rcx, rcx
0x140011d16  jz      short loc_140011D33
0x140011d18  mov     r9b, 1
0x140011d1b  mov     [rsp+48h+var_28], 107h; int
0x140011d23  mov     dl, r9b
0x140011d26  mov     r8d, 80h
0x140011d2c  call    TmpNotifyEnlistment
0x140011d31  mov     edi, eax
0x140011d33  mov     rbx, [rsp+48h+arg_0]
0x140011d38  mov     eax, edi
0x140011d3a  add     rsp, 40h
0x140011d3e  pop     rdi
0x140011d3f  retn
```
