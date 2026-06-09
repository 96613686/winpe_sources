# TmpTxActionDoPrePrepare

- ea: `0x14001eb30`
- end: `0x14001ebb1`
- name: `TmpTxActionDoPrePrepare`
- size: `129`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010140`
- `0x140010220`
- `0x1400106c0`
- `0x14001a2e0`

## callees

- `0x14000c320`
- `0x140010c70`
- `0x14001b658`
- `0x14001eb30`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoPrePrepare(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  int v6; // edi

  v3 = a1 + 200;
  *(_DWORD *)(a1 + 192) = 8;
  v5 = *(_QWORD *)(a1 + 200);
  if ( v5 == v3 || *(_QWORD *)(a1 + 240) && v5 == *(_QWORD *)(a1 + 208) || !*(_DWORD *)(a1 + 224) )
  {
    return (unsigned int)TmpTxActionDoPrePrepareComplete(a1);
  }
  else
  {
    v6 = TmpNotifyAllEnlistmentsTransaction(a1, 1u, a3, 266);
    if ( v6 < 0 )
      TmRollbackTransactionExt((PKTRANSACTION)a1, 0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001eb30  mov     [rsp+arg_0], rbx
0x14001eb35  push    rdi
0x14001eb36  sub     rsp, 30h
0x14001eb3a  lea     rax, [rcx+0C8h]
0x14001eb41  mov     dword ptr [rcx+0C0h], 8
0x14001eb4b  mov     rbx, rcx
0x14001eb4e  mov     rcx, [rax]
0x14001eb51  cmp     rcx, rax
0x14001eb54  jnz     short loc_14001EB70
0x14001eb56  xor     edx, edx
0x14001eb58  mov     rcx, rbx; int
0x14001eb5b  call    TmpTxActionDoPrePrepareComplete
0x14001eb60  mov     edi, eax
0x14001eb62  mov     rbx, [rsp+38h+arg_0]
0x14001eb67  mov     eax, edi
0x14001eb69  add     rsp, 30h
0x14001eb6d  pop     rdi
0x14001eb6e  retn
0x14001eb70  cmp     qword ptr [rbx+0F0h], 0
0x14001eb78  jz      short loc_14001EB83
0x14001eb7a  cmp     rcx, [rbx+0D0h]
0x14001eb81  jz      short loc_14001EB56
0x14001eb83  cmp     dword ptr [rbx+0E0h], 0
0x14001eb8a  jz      short loc_14001EB56
0x14001eb8c  mov     edx, 1
0x14001eb91  mov     r9d, 10Ah
0x14001eb97  mov     rcx, rbx
0x14001eb9a  call    TmpNotifyAllEnlistmentsTransaction
0x14001eb9f  mov     edi, eax
0x14001eba1  test    eax, eax
0x14001eba3  jns     short loc_14001EB62
0x14001eba5  xor     edx, edx; Wait
0x14001eba7  mov     rcx, rbx; Transaction
0x14001ebaa  call    TmRollbackTransactionExt
0x14001ebaf  jmp     short loc_14001EB62
```
