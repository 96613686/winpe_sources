# TmRollbackTransactionExt

- ea: `0x140010c70`
- end: `0x140010e25`
- name: `TmRollbackTransactionExt`
- size: `437`
- prototype: `NTSTATUS __stdcall(PKTRANSACTION Transaction, BOOLEAN Wait)`
- caller_count: `13`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c3c4`
- `0x14000c480`
- `0x140010c70`
- `0x1400110f4`
- `0x140011740`
- `0x140015fa0`
- `0x140016ea0`
- `0x140019460`
- `0x14001ab8c`
- `0x14001dbb0`
- `0x14001eb30`
- `0x14001f380`
- `0x140020dd4`

## callees

- `0x14000117c`
- `0x14000c140`
- `0x140010c70`
- `0x140011ab4`
- `0x140011d48`
- `0x14001b338`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140010cdd`
- `ntoskrnl!KeReleaseMutex` at `0x140010df0`
- `ntoskrnl!KeReleaseMutex` at `0x140021d8c`
- `ntoskrnl!KeReleaseMutex` at `0x140010cdd`
- `ntoskrnl!KeReleaseMutex` at `0x140010df0`
- `ntoskrnl!KeReleaseMutex` at `0x140021d8c`
- `ntoskrnl!KeSetEvent` at `0x140010d8a`
- `ntoskrnl!KeSetEvent` at `0x140010d8a`
- `ntoskrnl!DbgPrintEx` at `0x140010c98`
- `ntoskrnl!DbgPrintEx` at `0x140010c98`

## string_xrefs

- `0x140010c87`: `KTM:  TmRollbackTransactionExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmRollbackTransactionExt(PKTRANSACTION Transaction, BOOLEAN Wait)
{
  int v4; // r8d
  char v5; // si
  struct _KTRANSACTION *v6; // rbx
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // ecx
  int v12; // eax

  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmRollbackTransactionExt for tx %lx\n", (_DWORD)Transaction);
  TmpAcquireTransactionMutex(Transaction);
  v5 = 1;
  if ( (*((_DWORD *)Transaction + 49) & 0x400) != 0 && (*((_DWORD *)Transaction + 49) & 0x100) == 0 )
  {
    v6 = (struct _KTRANSACTION *)*((_QWORD *)Transaction + 34);
    KeReleaseMutex((PRKMUTEX)(*((_QWORD *)Transaction + 11) + 32LL), 0);
    v5 = 0;
    v7 = TmRollbackTransactionExt(v6, 0);
LABEL_4:
    v8 = v7;
    goto LABEL_22;
  }
  v9 = *((_DWORD *)Transaction + 48);
  if ( v9 <= 0xB && (v10 = 2310, _bittest(&v10, v9)) || v9 == 3 && (*((_DWORD *)Transaction + 49) & 2) != 0 )
  {
    if ( *((_QWORD *)Transaction + 64) )
    {
      v7 = TmpTxActionDoRollback(Transaction);
      goto LABEL_4;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_q_guid_(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, v4, (_DWORD)Transaction, (__int64)Transaction + 176);
    *((_DWORD *)Transaction + 48) = 9;
    *((_DWORD *)Transaction + 126) = 3;
    KeSetEvent((PRKEVENT)Transaction, 0, 0);
    TmpFinalizeTransaction(Transaction);
    goto LABEL_21;
  }
  v11 = *((_DWORD *)Transaction + 48);
  if ( v11 == 6 || (v12 = *((_DWORD *)Transaction + 126), v12 == 3) )
  {
LABEL_21:
    v8 = 0;
    goto LABEL_22;
  }
  if ( v11 == 5 || v12 == 2 )
    v8 = -1072103402;
  else
    v8 = -1072103405;
LABEL_22:
  if ( v5 )
    KeReleaseMutex((PRKMUTEX)(*((_QWORD *)Transaction + 11) + 32LL), 0);
  if ( v8 == 259 && Wait )
    return TmpWaitForTransactionOutcome(Transaction, 3);
  return v8;
}

```

## disassembly

```asm
0x140010c70  mov     [rsp+arg_0], rcx
0x140010c75  push    rbx
0x140010c76  push    rsi
0x140010c77  push    rdi
0x140010c78  push    r14
0x140010c7a  sub     rsp, 48h
0x140010c7e  mov     r14b, dl
0x140010c81  mov     rdi, rcx
0x140010c84  mov     r9, rcx
0x140010c87  lea     r8, aKtmTmrollbackt; "KTM:  TmRollbackTransactionExt for tx %"...
0x140010c8e  mov     edx, 80000020h; Level
0x140010c93  mov     ecx, 6Ch ; 'l'; ComponentId
0x140010c98  call    cs:__imp_DbgPrintEx
0x140010c9f  nop     dword ptr [rax+rax+00h]
0x140010ca4  mov     rcx, rdi
0x140010ca7  call    TmpAcquireTransactionMutex
0x140010cac  mov     sil, 1
0x140010caf  mov     [rsp+68h+var_38], sil
0x140010cb4  mov     eax, [rdi+0C4h]
0x140010cba  bt      eax, 0Ah
0x140010cbe  jnb     short loc_140010D06
0x140010cc0  mov     eax, [rdi+0C4h]
0x140010cc6  bt      eax, 8
0x140010cca  jb      short loc_140010D06
0x140010ccc  mov     rbx, [rdi+110h]
0x140010cd3  mov     rcx, [rdi+58h]
0x140010cd7  add     rcx, 20h ; ' '; Mutex
0x140010cdb  xor     edx, edx; Wait
0x140010cdd  call    cs:__imp_KeReleaseMutex
0x140010ce4  nop     dword ptr [rax+rax+00h]
0x140010ce9  xor     sil, sil
0x140010cec  mov     [rsp+68h+var_38], sil
0x140010cf1  xor     edx, edx; Wait
0x140010cf3  mov     rcx, rbx; Transaction
0x140010cf6  call    TmRollbackTransactionExt
0x140010cfb  mov     ebx, eax
0x140010cfd  mov     [rsp+68h+var_34], eax
0x140010d01  jmp     loc_140010DE1
0x140010d06  mov     eax, [rdi+0C0h]
0x140010d0c  mov     edx, 0Bh
0x140010d11  cmp     eax, edx
0x140010d13  ja      short loc_140010D1F
0x140010d15  mov     ecx, 906h
0x140010d1a  bt      ecx, eax
0x140010d1d  jb      short loc_140010D32
0x140010d1f  cmp     eax, 3
0x140010d22  jnz     loc_140010DAD
0x140010d28  mov     eax, [rdi+0C4h]
0x140010d2e  test    al, 2
0x140010d30  jz      short loc_140010DAD
0x140010d32  cmp     qword ptr [rdi+200h], 0
0x140010d3a  jnz     short loc_140010DA0
0x140010d3c  lea     rax, WPP_GLOBAL_Control
0x140010d43  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d4a  cmp     rcx, rax
0x140010d4d  jz      short loc_140010D6E
0x140010d4f  mov     eax, [rcx+2Ch]
0x140010d52  test    al, 4
0x140010d54  jz      short loc_140010D6E
0x140010d56  lea     rax, [rdi+0B0h]
0x140010d5d  mov     [rsp+68h+var_48], rax
0x140010d62  mov     r9, rdi
0x140010d65  mov     rcx, [rcx+18h]
0x140010d69  call    WPP_SF_q_guid_
0x140010d6e  mov     dword ptr [rdi+0C0h], 9
0x140010d78  mov     dword ptr [rdi+1F8h], 3
0x140010d82  xor     r8d, r8d; Wait
0x140010d85  xor     edx, edx; Increment
0x140010d87  mov     rcx, rdi; Event
0x140010d8a  call    cs:__imp_KeSetEvent
0x140010d91  nop     dword ptr [rax+rax+00h]
0x140010d96  mov     rcx, rdi; Object
0x140010d99  call    TmpFinalizeTransaction
0x140010d9e  jmp     short loc_140010DDB
0x140010da0  mov     rcx, rdi
0x140010da3  call    TmpTxActionDoRollback
0x140010da8  jmp     loc_140010CFB
0x140010dad  mov     ecx, [rdi+0C0h]
0x140010db3  cmp     ecx, 6
0x140010db6  jz      short loc_140010DDB
0x140010db8  mov     eax, [rdi+1F8h]
0x140010dbe  cmp     eax, 3
0x140010dc1  jz      short loc_140010DDB
0x140010dc3  cmp     ecx, 5
0x140010dc6  jz      short loc_140010DD4
0x140010dc8  cmp     eax, 2
0x140010dcb  jz      short loc_140010DD4
0x140010dcd  mov     ebx, 0C0190013h
0x140010dd2  jmp     short loc_140010DDD
0x140010dd4  mov     ebx, 0C0190016h
0x140010dd9  jmp     short loc_140010DDD
0x140010ddb  xor     ebx, ebx
0x140010ddd  mov     [rsp+68h+var_34], ebx
0x140010de1  test    sil, sil
0x140010de4  jz      short loc_140010DFC
0x140010de6  mov     rcx, [rdi+58h]
0x140010dea  add     rcx, 20h ; ' '; Mutex
0x140010dee  xor     edx, edx; Wait
0x140010df0  call    cs:__imp_KeReleaseMutex
0x140010df7  nop     dword ptr [rax+rax+00h]
0x140010dfc  cmp     ebx, 103h
0x140010e02  jnz     short loc_140010E18
0x140010e04  test    r14b, r14b
0x140010e07  jz      short loc_140010E18
0x140010e09  mov     edx, 3
0x140010e0e  mov     rcx, rdi
0x140010e11  call    TmpWaitForTransactionOutcome
0x140010e16  mov     ebx, eax
0x140010e18  mov     eax, ebx
0x140010e1a  add     rsp, 48h
0x140010e1e  pop     r14
0x140010e20  pop     rdi
0x140010e21  pop     rsi
0x140010e22  pop     rbx
0x140010e23  retn
0x140021d6f  push    rbp
0x140021d71  sub     rsp, 30h
0x140021d75  mov     rbp, rdx
0x140021d78  cmp     byte ptr [rbp+30h], 0
0x140021d7c  jz      short loc_140021D9C
0x140021d7e  mov     rax, [rbp+70h]
0x140021d82  mov     rcx, [rax+58h]
0x140021d86  add     rcx, 20h ; ' '; Mutex
0x140021d8a  xor     edx, edx; Wait
0x140021d8c  call    cs:__imp_KeReleaseMutex
0x140021d93  nop     dword ptr [rax+rax+00h]
0x140021d98  mov     byte ptr [rbp+30h], 0
0x140021d9c  add     rsp, 30h
0x140021da0  pop     rbp
0x140021da1  retn
```
