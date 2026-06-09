# TmpTraceTransactionManagerNotAdvancingTail

- ea: `0x140001bf4`
- end: `0x140001cf4`
- name: `TmpTraceTransactionManagerNotAdvancingTail`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015314`

## callees

- `0x140001bf4`
- `0x1400024e0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140001cd2`
- `ntoskrnl!EtwWrite` at `0x140001cd2`

## pseudocode

```c
NTSTATUS __fastcall TmpTraceTransactionManagerNotAdvancingTail(__int64 a1, __int64 a2)
{
  int v3; // r8d
  int v4; // edx
  NTSTATUS result; // eax
  __int16 v6; // [rsp+30h] [rbp-29h] BYREF
  __int16 v7; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-19h] BYREF
  __int16 *v9; // [rsp+50h] [rbp-9h]
  __int64 v10; // [rsp+58h] [rbp-1h]
  __int64 v11; // [rsp+60h] [rbp+7h]
  int v12; // [rsp+68h] [rbp+Fh]
  int v13; // [rsp+6Ch] [rbp+13h]
  __int64 v14; // [rsp+70h] [rbp+17h]
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  __int16 *v16; // [rsp+80h] [rbp+27h]
  __int64 v17; // [rsp+88h] [rbp+2Fh]
  __int64 v18; // [rsp+90h] [rbp+37h]
  int v19; // [rsp+98h] [rbp+3Fh]
  int v20; // [rsp+9Ch] [rbp+43h]

  if ( TmpEtwHandle )
  {
    v3 = *(unsigned __int16 *)(a1 + 136);
    UserData.Ptr = a1 + 112;
    v6 = (unsigned __int16)v3 >> 1;
    v9 = &v6;
    v4 = *(unsigned __int16 *)(a2 + 304);
    v11 = *(_QWORD *)(a1 + 144);
    v14 = a2 + 176;
    v7 = (unsigned __int16)v4 >> 1;
    v16 = &v7;
    v18 = *(_QWORD *)(a2 + 312);
    v12 = v3;
    v19 = v4;
    *(_QWORD *)&UserData.Size = 16;
    v10 = 2;
    v13 = 0;
    v15 = 16;
    v17 = 2;
    v20 = 0;
    return EtwWrite(TmpEtwHandle, &KTM_ETW_EVENT_TRANSACTIONMANAGER_NOT_ADVANCING_TAIL, 0, 6u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140001bf4  push    rbp
0x140001bf6  lea     rbp, [rsp-57h]
0x140001bfb  sub     rsp, 0B0h
0x140001c02  mov     rax, cs:__security_cookie
0x140001c09  xor     rax, rsp
0x140001c0c  mov     [rbp+57h+var_10], rax
0x140001c10  mov     r9, rdx
0x140001c13  mov     rdx, rcx
0x140001c16  mov     rcx, cs:TmpEtwHandle; RegHandle
0x140001c1d  test    rcx, rcx
0x140001c20  jz      loc_140001CDE
0x140001c26  movzx   r8d, word ptr [rdx+88h]
0x140001c2e  lea     rax, [rdx+70h]
0x140001c32  mov     [rbp+57h+var_70.Ptr], rax
0x140001c36  movzx   eax, r8w
0x140001c3a  shr     ax, 1
0x140001c3d  mov     [rbp+57h+var_80], ax
0x140001c41  lea     rax, [rbp+57h+var_80]
0x140001c45  mov     [rbp+57h+var_60], rax
0x140001c49  mov     rax, [rdx+90h]
0x140001c50  movzx   edx, word ptr [r9+130h]
0x140001c58  mov     [rbp+57h+var_50], rax
0x140001c5c  lea     rax, [r9+0B0h]
0x140001c63  mov     [rbp+57h+var_40], rax
0x140001c67  movzx   eax, dx
0x140001c6a  shr     ax, 1
0x140001c6d  mov     [rbp+57h+var_7C], ax
0x140001c71  lea     rax, [rbp+57h+var_7C]
0x140001c75  mov     [rbp+57h+var_30], rax
0x140001c79  mov     rax, [r9+138h]
0x140001c80  mov     r9d, 6; UserDataCount
0x140001c86  mov     [rbp+57h+var_20], rax
0x140001c8a  lea     rax, [rbp+57h+var_70]
0x140001c8e  mov     [rbp+57h+var_48], r8d
0x140001c92  xor     r8d, r8d; ActivityId
0x140001c95  mov     [rbp+57h+var_18], edx
0x140001c98  lea     rdx, KTM_ETW_EVENT_TRANSACTIONMANAGER_NOT_ADVANCING_TAIL; EventDescriptor
0x140001c9f  mov     [rsp+0B0h+UserData], rax; UserData
0x140001ca4  mov     qword ptr [rbp+57h+var_70.Size], 10h
0x140001cac  mov     [rbp+57h+var_58], 2
0x140001cb4  mov     [rbp+57h+var_44], 0
0x140001cbb  mov     [rbp+57h+var_38], 10h
0x140001cc3  mov     [rbp+57h+var_28], 2
0x140001ccb  mov     [rbp+57h+var_14], 0
0x140001cd2  call    cs:__imp_EtwWrite
0x140001cd9  nop     dword ptr [rax+rax+00h]
0x140001cde  mov     rcx, [rbp+57h+var_10]
0x140001ce2  xor     rcx, rsp; StackCookie
0x140001ce5  call    __security_check_cookie
0x140001cea  add     rsp, 0B0h
0x140001cf1  pop     rbp
0x140001cf2  retn
```
