# TmpTraceTransactionBlockedFreeze

- ea: `0x14000f6e8`
- end: `0x14000f824`
- name: `TmpTraceTransactionBlockedFreeze`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011228`

## callees

- `0x1400024e0`
- `0x14000f6e8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000f7f3`
- `ntoskrnl!EtwWrite` at `0x14000f7f3`

## pseudocode

```c
NTSTATUS __fastcall TmpTraceTransactionBlockedFreeze(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 *v3; // rdi
  __int64 *i; // rbx
  __int64 v5; // rdx
  int v6; // ecx
  int v7; // ecx
  _WORD v8[8]; // [rsp+30h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-39h] BYREF
  _WORD *v10; // [rsp+50h] [rbp-29h]
  __int64 v11; // [rsp+58h] [rbp-21h]
  __int64 v12; // [rsp+60h] [rbp-19h]
  int v13; // [rsp+68h] [rbp-11h]
  int v14; // [rsp+6Ch] [rbp-Dh]
  __int64 v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  _WORD *v17; // [rsp+80h] [rbp+7h]
  __int64 v18; // [rsp+88h] [rbp+Fh]
  __int64 v19; // [rsp+90h] [rbp+17h]
  int v20; // [rsp+98h] [rbp+1Fh]
  int v21; // [rsp+9Ch] [rbp+23h]

  result = 0;
  v8[0] = 0;
  if ( TmpEtwHandle )
  {
    v3 = (__int64 *)(a1 + 200);
    for ( i = *(__int64 **)(a1 + 200); i != v3; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 12) == 261 )
      {
        v5 = i[4];
        v6 = *(unsigned __int16 *)(a1 + 304);
        UserData.Ptr = a1 + 176;
        v13 = v6;
        v8[0] = (unsigned __int16)v6 >> 1;
        v10 = v8;
        v12 = *(_QWORD *)(a1 + 312);
        v15 = v5 + 136;
        *(_QWORD *)&UserData.Size = 16;
        v11 = 2;
        v14 = 0;
        v16 = 16;
        v8[0] = *(_WORD *)(v5 + 368) >> 1;
        v17 = v8;
        v18 = 2;
        v7 = *(unsigned __int16 *)(v5 + 368);
        v19 = *(_QWORD *)(v5 + 376);
        v20 = v7;
        v21 = 0;
        result = EtwWrite(TmpEtwHandle, &KTM_ETW_EVENT_TRANSACTION_BLOCKED_FREEZE, 0, 6u, &UserData);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f6e8  push    rbp
0x14000f6ea  push    rbx
0x14000f6eb  push    rsi
0x14000f6ec  push    rdi
0x14000f6ed  lea     rbp, [rsp-3Fh]
0x14000f6f2  sub     rsp, 0B8h
0x14000f6f9  mov     rax, cs:__security_cookie
0x14000f700  xor     rax, rsp
0x14000f703  mov     [rbp+57h+var_30], rax
0x14000f707  xor     eax, eax
0x14000f709  mov     rsi, rcx
0x14000f70c  cmp     cs:TmpEtwHandle, rax
0x14000f713  mov     [rbp+57h+var_A0], ax
0x14000f717  jz      loc_14000F80B
0x14000f71d  lea     rdi, [rcx+0C8h]
0x14000f724  mov     rbx, [rdi]
0x14000f727  jmp     loc_14000F802
0x14000f72c  cmp     dword ptr [rbx+30h], 105h
0x14000f733  jnz     loc_14000F7FF
0x14000f739  mov     rdx, [rbx+20h]
0x14000f73d  lea     rax, [rsi+0B0h]
0x14000f744  movzx   ecx, word ptr [rsi+130h]
0x14000f74b  mov     r9d, 6; UserDataCount
0x14000f751  mov     [rbp+57h+var_90.Ptr], rax
0x14000f755  xor     r8d, r8d; ActivityId
0x14000f758  movzx   eax, cx
0x14000f75b  mov     [rbp+57h+var_68], ecx
0x14000f75e  shr     ax, 1
0x14000f761  mov     [rbp+57h+var_A0], ax
0x14000f765  lea     rax, [rbp+57h+var_A0]
0x14000f769  mov     [rbp+57h+var_80], rax
0x14000f76d  mov     rax, [rsi+138h]
0x14000f774  mov     [rbp+57h+var_70], rax
0x14000f778  lea     rax, [rdx+88h]
0x14000f77f  mov     [rbp+57h+var_60], rax
0x14000f783  mov     qword ptr [rbp+57h+var_90.Size], 10h
0x14000f78b  mov     [rbp+57h+var_78], 2
0x14000f793  mov     [rbp+57h+var_64], 0
0x14000f79a  mov     [rbp+57h+var_58], 10h
0x14000f7a2  movzx   eax, word ptr [rdx+170h]
0x14000f7a9  shr     ax, 1
0x14000f7ac  mov     [rbp+57h+var_A0], ax
0x14000f7b0  lea     rax, [rbp+57h+var_A0]
0x14000f7b4  mov     [rbp+57h+var_50], rax
0x14000f7b8  mov     [rbp+57h+var_48], 2
0x14000f7c0  mov     rax, [rdx+178h]
0x14000f7c7  movzx   ecx, word ptr [rdx+170h]
0x14000f7ce  lea     rdx, KTM_ETW_EVENT_TRANSACTION_BLOCKED_FREEZE; EventDescriptor
0x14000f7d5  mov     [rbp+57h+var_40], rax
0x14000f7d9  lea     rax, [rbp+57h+var_90]
0x14000f7dd  mov     [rbp+57h+var_38], ecx
0x14000f7e0  mov     rcx, cs:TmpEtwHandle; RegHandle
0x14000f7e7  mov     [rsp+0D0h+UserData], rax; UserData
0x14000f7ec  mov     [rbp+57h+var_34], 0
0x14000f7f3  call    cs:__imp_EtwWrite
0x14000f7fa  nop     dword ptr [rax+rax+00h]
0x14000f7ff  mov     rbx, [rbx]
0x14000f802  cmp     rbx, rdi
0x14000f805  jnz     loc_14000F72C
0x14000f80b  mov     rcx, [rbp+57h+var_30]
0x14000f80f  xor     rcx, rsp; StackCookie
0x14000f812  call    __security_check_cookie
0x14000f817  add     rsp, 0B8h
0x14000f81e  pop     rdi
0x14000f81f  pop     rsi
0x14000f820  pop     rbx
0x14000f821  pop     rbp
0x14000f822  retn
```
