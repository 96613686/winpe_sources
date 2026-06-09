# TmpForwardCommitTransaction

- ea: `0x1400110f4`
- end: `0x140011222`
- name: `TmpForwardCommitTransaction`
- size: `302`
- prototype: `__int64 __fastcall(PKTRANSACTION Transaction)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010330`
- `0x14001a2e0`
- `0x14001ab8c`

## callees

- `0x14000cbcc`
- `0x140010c70`
- `0x1400110f4`
- `0x140011300`
- `0x14001b338`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400111fd`
- `ntoskrnl!KeReleaseMutex` at `0x140021df5`
- `ntoskrnl!KeReleaseMutex` at `0x1400111fd`
- `ntoskrnl!KeReleaseMutex` at `0x140021df5`

## pseudocode

```c
__int64 __fastcall TmpForwardCommitTransaction(_DWORD *Transaction)
{
  unsigned int v2; // ebx
  char v3; // r15
  _DWORD *v4; // r8
  _QWORD *v5; // r14
  _QWORD *v6; // rsi
  __int64 v7; // rax

  v2 = -1072103405;
  v3 = 0;
  TmpAcquireTransactionMutex(Transaction);
  if ( (Transaction[49] & 0x2000) != 0 )
    goto LABEL_16;
  if ( Transaction[48] != 1 )
    goto LABEL_15;
  v4 = Transaction;
  if ( (Transaction[49] & 0x100) == 0 )
    v4 = (_DWORD *)*((_QWORD *)Transaction + 34);
  if ( (v4[49] & 0x100) != 0 && (v4[49] & 0x400) != 0 && (unsigned __int8)TmpPromotionsIncomplete(v4) )
  {
    _InterlockedOr(v4 + 49, 0x4000u);
    v2 = 259;
    goto LABEL_17;
  }
  v5 = v4 + 64;
  v6 = v4 + 64;
  do
  {
    v7 = *(v6 - 2);
    if ( v7 && (*(_DWORD *)(v7 + 176) & 0x4000000) != 0 )
    {
      v3 = 1;
      v2 = TmpNotifyEnlistment((PVOID)*(v6 - 2), 262);
    }
    v6 = (_QWORD *)*v6;
  }
  while ( v6 != v5 );
  if ( !v3 )
  {
LABEL_15:
    TmRollbackTransactionExt((PKTRANSACTION)Transaction, 0);
LABEL_16:
    v2 = -1072103405;
  }
LABEL_17:
  KeReleaseMutex((PRKMUTEX)(*((_QWORD *)Transaction + 11) + 32LL), 0);
  return v2;
}

```

## disassembly

```asm
0x1400110f4  mov     [rsp+arg_8], rbx
0x1400110f9  mov     [rsp+arg_10], rsi
0x1400110fe  mov     [rsp+arg_0], rcx
0x140011103  push    rdi
0x140011104  push    r14
0x140011106  push    r15
0x140011108  sub     rsp, 50h
0x14001110c  mov     rdi, rcx
0x14001110f  mov     ebx, 0C0190013h
0x140011114  xor     r15b, r15b
0x140011117  call    TmpAcquireTransactionMutex
0x14001111c  nop
0x14001111d  mov     eax, [rdi+0C4h]
0x140011123  bt      eax, 0Dh
0x140011127  jb      loc_1400111EA
0x14001112d  cmp     dword ptr [rdi+0C0h], 1
0x140011134  jnz     loc_1400111E0
0x14001113a  mov     eax, [rdi+0C4h]
0x140011140  bt      eax, 8
0x140011144  mov     r8, rdi
0x140011147  jb      short loc_140011150
0x140011149  mov     r8, [rdi+110h]
0x140011150  mov     eax, [r8+0C4h]
0x140011157  bt      eax, 8
0x14001115b  jnb     short loc_140011189
0x14001115d  mov     eax, [r8+0C4h]
0x140011164  bt      eax, 0Ah
0x140011168  jnb     short loc_140011189
0x14001116a  mov     rcx, r8
0x14001116d  call    TmpPromotionsIncomplete
0x140011172  test    al, al
0x140011174  jz      short loc_140011189
0x140011176  lock or dword ptr [r8+0C4h], 4000h
0x140011182  mov     ebx, 103h
0x140011187  jmp     short loc_1400111EF
0x140011189  lea     r14, [r8+100h]
0x140011190  mov     rsi, r14
0x140011193  mov     rax, [rsi-10h]
0x140011197  test    rax, rax
0x14001119a  jz      short loc_1400111D3
0x14001119c  mov     eax, [rax+0B0h]
0x1400111a2  bt      eax, 1Ah
0x1400111a6  jnb     short loc_1400111D3
0x1400111a8  mov     r15b, 1
0x1400111ab  mov     [rsp+68h+var_28], r15b
0x1400111b0  mov     [rsp+68h+var_48], 106h; int
0x1400111b8  mov     r9b, r15b
0x1400111bb  mov     r8d, 4000000h
0x1400111c1  mov     dl, r15b
0x1400111c4  mov     rcx, [rsi-10h]; Object
0x1400111c8  call    TmpNotifyEnlistment
0x1400111cd  mov     ebx, eax
0x1400111cf  mov     [rsp+68h+var_24], eax
0x1400111d3  mov     rsi, [rsi]
0x1400111d6  cmp     rsi, r14
0x1400111d9  jnz     short loc_140011193
0x1400111db  test    r15b, r15b
0x1400111de  jnz     short loc_1400111F3
0x1400111e0  xor     edx, edx; Wait
0x1400111e2  mov     rcx, rdi; Transaction
0x1400111e5  call    TmRollbackTransactionExt
0x1400111ea  mov     ebx, 0C0190013h
0x1400111ef  mov     [rsp+68h+var_24], ebx
0x1400111f3  mov     rcx, [rdi+58h]
0x1400111f7  add     rcx, 20h ; ' '; Mutex
0x1400111fb  xor     edx, edx; Wait
0x1400111fd  call    cs:__imp_KeReleaseMutex
0x140011204  nop     dword ptr [rax+rax+00h]
0x140011209  mov     eax, ebx
0x14001120b  lea     r11, [rsp+68h+var_18]
0x140011210  mov     rbx, [r11+28h]
0x140011214  mov     rsi, [r11+30h]
0x140011218  mov     rsp, r11
0x14001121b  pop     r15
0x14001121d  pop     r14
0x14001121f  pop     rdi
0x140011220  retn
0x140021dde  push    rbp
0x140021de0  sub     rsp, 40h
0x140021de4  mov     rbp, rdx
0x140021de7  mov     rax, [rbp+70h]
0x140021deb  mov     rcx, [rax+58h]
0x140021def  add     rcx, 20h ; ' '; Mutex
0x140021df3  xor     edx, edx; Wait
0x140021df5  call    cs:__imp_KeReleaseMutex
0x140021dfc  nop     dword ptr [rax+rax+00h]
0x140021e01  nop
0x140021e02  add     rsp, 40h
0x140021e06  pop     rbp
0x140021e07  retn
```
