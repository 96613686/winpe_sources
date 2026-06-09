# TmpTxActionDoRollback

- ea: `0x140011ab4`
- end: `0x140011c6c`
- name: `TmpTxActionDoRollback`
- size: `440`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400108c0`
- `0x140010c70`
- `0x140011ab4`
- `0x1400161c0`
- `0x140020250`

## callees

- `0x1400013d0`
- `0x140001fec`
- `0x14000c140`
- `0x140011300`
- `0x140011ab4`
- `0x14001b658`
- `0x14001f3e8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140011b52`
- `ntoskrnl!KeSetEvent` at `0x140011b52`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoRollback(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebp
  __int64 v5; // r8
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  unsigned int v8; // eax

  v3 = 0;
  if ( (unsigned int)(*(_DWORD *)(a1 + 192) - 3) <= 1 && (*(_DWORD *)(a1 + 196) & 0x800000) != 0 )
    v3 = TmpLogTransaction(a1, 4, 0);
  *(_QWORD *)(a1 + 320) = KeGetCurrentThread();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 3), a1 + 176, a3, a1, a1 + 176);
  *(_DWORD *)(a1 + 192) = 6;
  *(_DWORD *)(a1 + 504) = 3;
  KeSetEvent((PRKEVENT)a1, 0, 0);
  if ( *(_QWORD *)(a1 + 240) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_sqq_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 3));
    v3 = TmpNotifyEnlistment(*(PVOID *)(a1 + 240), 269);
  }
  v6 = *(_QWORD *)(a1 + 200);
  if ( v6 != a1 + 200 && (!*(_QWORD *)(a1 + 240) || v6 != *(_QWORD *)(a1 + 208)) )
    v3 = TmpNotifyAllEnlistmentsTransaction(a1, 8, v5, 269);
  if ( (*(_DWORD *)(a1 + 196) & 0x100) != 0 && (*(_DWORD *)(a1 + 196) & 0x400) != 0 )
  {
    v7 = *(_QWORD **)(a1 + 256);
    while ( v7 != (_QWORD *)(a1 + 256) )
    {
      v8 = TmpTxActionDoRollback(v7 - 32);
      v7 = (_QWORD *)*v7;
      v3 = v8;
    }
  }
  *(_DWORD *)(a1 + 192) = 9;
  TmpFinalizeTransaction((PVOID)a1);
  return v3;
}

```

## disassembly

```asm
0x140011ab4  push    rbx
0x140011ab6  push    rbp
0x140011ab7  push    rsi
0x140011ab8  push    rdi
0x140011ab9  sub     rsp, 48h
0x140011abd  mov     eax, [rcx+0C0h]
0x140011ac3  xor     ebp, ebp
0x140011ac5  sub     eax, 3
0x140011ac8  mov     rbx, rcx
0x140011acb  cmp     eax, 1
0x140011ace  ja      short loc_140011AE9
0x140011ad0  mov     eax, [rcx+0C4h]
0x140011ad6  bt      eax, 17h
0x140011ada  jnb     short loc_140011AE9
0x140011adc  xor     r8d, r8d
0x140011adf  lea     edx, [rbp+4]
0x140011ae2  call    TmpLogTransaction
0x140011ae7  mov     ebp, eax
0x140011ae9  mov     rcx, gs:188h
0x140011af2  mov     [rbx+140h], rcx
0x140011af9  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b00  lea     rsi, WPP_GLOBAL_Control
0x140011b07  cmp     rcx, rsi
0x140011b0a  jz      short loc_140011B36
0x140011b0c  mov     edx, [rcx+2Ch]
0x140011b0f  test    dl, 4
0x140011b12  jz      short loc_140011B36
0x140011b14  mov     eax, [rbx+0D8h]
0x140011b1a  lea     rdx, [rbx+0B0h]
0x140011b21  mov     rcx, [rcx+18h]
0x140011b25  mov     r9, rbx
0x140011b28  mov     dword ptr [rsp+68h+var_40], eax
0x140011b2c  mov     qword ptr [rsp+68h+var_48], rdx
0x140011b31  call    WPP_SF_q_guid_d
0x140011b36  xor     r8d, r8d; Wait
0x140011b39  mov     dword ptr [rbx+0C0h], 6
0x140011b43  xor     edx, edx; Increment
0x140011b45  mov     dword ptr [rbx+1F8h], 3
0x140011b4f  mov     rcx, rbx; Event
0x140011b52  call    cs:__imp_KeSetEvent
0x140011b59  nop     dword ptr [rax+rax+00h]
0x140011b5e  cmp     qword ptr [rbx+0F0h], 0
0x140011b66  jz      short loc_140011BDB
0x140011b68  mov     edi, [rbx+0C4h]
0x140011b6e  shr     edi, 6
0x140011b71  not     dil
0x140011b74  and     dil, 1
0x140011b78  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b7f  cmp     rcx, rsi
0x140011b82  jz      short loc_140011BB9
0x140011b84  mov     eax, [rcx+2Ch]
0x140011b87  test    al, 4
0x140011b89  jz      short loc_140011BB9
0x140011b8b  mov     rcx, [rcx+18h]
0x140011b8f  lea     rdx, [rbx+0B0h]
0x140011b96  movzx   eax, dil
0x140011b9a  mov     [rsp+68h+var_30], eax
0x140011b9e  mov     rax, [rbx+0F0h]
0x140011ba5  mov     [rsp+68h+var_38], rdx
0x140011baa  mov     [rsp+68h+var_40], rbx
0x140011baf  mov     qword ptr [rsp+68h+var_48], rax
0x140011bb4  call    WPP_SF_sqq_guid_d
0x140011bb9  mov     rcx, [rbx+0F0h]; Object
0x140011bc0  mov     r9b, 1
0x140011bc3  mov     r8d, 8
0x140011bc9  mov     [rsp+68h+var_48], 10Dh; int
0x140011bd1  mov     dl, dil
0x140011bd4  call    TmpNotifyEnlistment
0x140011bd9  mov     ebp, eax
0x140011bdb  lea     rax, [rbx+0C8h]
0x140011be2  mov     rcx, [rax]
0x140011be5  cmp     rcx, rax
0x140011be8  jz      short loc_140011C12
0x140011bea  cmp     qword ptr [rbx+0F0h], 0
0x140011bf2  jz      short loc_140011BFD
0x140011bf4  cmp     rcx, [rbx+0D0h]
0x140011bfb  jz      short loc_140011C12
0x140011bfd  mov     edx, 8
0x140011c02  mov     r9d, 10Dh
0x140011c08  mov     rcx, rbx
0x140011c0b  call    TmpNotifyAllEnlistmentsTransaction
0x140011c10  mov     ebp, eax
0x140011c12  mov     eax, [rbx+0C4h]
0x140011c18  bt      eax, 8
0x140011c1c  jnb     short loc_140011C4E
0x140011c1e  mov     eax, [rbx+0C4h]
0x140011c24  bt      eax, 0Ah
0x140011c28  jnb     short loc_140011C4E
0x140011c2a  lea     rsi, [rbx+100h]
0x140011c31  mov     rdi, [rsi]
0x140011c34  jmp     short loc_140011C49
0x140011c36  lea     rcx, [rdi-100h]
0x140011c3d  xor     edx, edx
0x140011c3f  call    TmpTxActionDoRollback
0x140011c44  mov     rdi, [rdi]
0x140011c47  mov     ebp, eax
0x140011c49  cmp     rdi, rsi
0x140011c4c  jnz     short loc_140011C36
0x140011c4e  mov     rcx, rbx; Object
0x140011c51  mov     dword ptr [rbx+0C0h], 9
0x140011c5b  call    TmpFinalizeTransaction
0x140011c60  mov     eax, ebp
0x140011c62  add     rsp, 48h
0x140011c66  pop     rdi
0x140011c67  pop     rsi
0x140011c68  pop     rbp
0x140011c69  pop     rbx
0x140011c6a  retn
```
