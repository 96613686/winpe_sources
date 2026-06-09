# TmpTraceTransactionRollbackLogError

- ea: `0x14000f944`
- end: `0x14000fa01`
- name: `TmpTraceTransactionRollbackLogError`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c480`
- `0x140020dd4`

## callees

- `0x1400024e0`
- `0x14000f944`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000f9df`
- `ntoskrnl!EtwWrite` at `0x14000f9df`

## pseudocode

```c
NTSTATUS __fastcall TmpTraceTransactionRollbackLogError(__int64 a1, int a2)
{
  int v2; // edx
  NTSTATUS result; // eax
  __int16 v4; // [rsp+30h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int16 *v6; // [rsp+50h] [rbp+17h]
  __int64 v7; // [rsp+58h] [rbp+1Fh]
  __int64 v8; // [rsp+60h] [rbp+27h]
  int v9; // [rsp+68h] [rbp+2Fh]
  int v10; // [rsp+6Ch] [rbp+33h]
  int *v11; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]
  int v13; // [rsp+A8h] [rbp+6Fh] BYREF

  v13 = a2;
  if ( TmpEtwHandle )
  {
    v2 = *(unsigned __int16 *)(a1 + 304);
    UserData.Ptr = a1 + 176;
    v9 = v2;
    v4 = (unsigned __int16)v2 >> 1;
    v6 = &v4;
    v8 = *(_QWORD *)(a1 + 312);
    v11 = &v13;
    *(_QWORD *)&UserData.Size = 16;
    v7 = 2;
    v10 = 0;
    v12 = 4;
    return EtwWrite(TmpEtwHandle, &KTM_ETW_EVENT_TRANSACTION_ROLLBACK_LOG_ERROR, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x14000f944  mov     [rsp-8+arg_8], edx
0x14000f948  push    rbp
0x14000f949  lea     rbp, [rsp-57h]
0x14000f94e  sub     rsp, 90h
0x14000f955  mov     rax, cs:__security_cookie
0x14000f95c  xor     rax, rsp
0x14000f95f  mov     [rbp+57h+var_10], rax
0x14000f963  mov     r8, rcx
0x14000f966  xor     r10d, r10d
0x14000f969  mov     rcx, cs:TmpEtwHandle; RegHandle
0x14000f970  test    rcx, rcx
0x14000f973  jz      short loc_14000F9EB
0x14000f975  movzx   edx, word ptr [r8+130h]
0x14000f97d  lea     rax, [r8+0B0h]
0x14000f984  mov     [rbp+57h+var_50.Ptr], rax
0x14000f988  lea     r9d, [r10+4]; UserDataCount
0x14000f98c  movzx   eax, dx
0x14000f98f  mov     [rbp+57h+var_28], edx
0x14000f992  shr     ax, 1
0x14000f995  lea     rdx, KTM_ETW_EVENT_TRANSACTION_ROLLBACK_LOG_ERROR; EventDescriptor
0x14000f99c  mov     [rbp+57h+var_60], ax
0x14000f9a0  lea     rax, [rbp+57h+var_60]
0x14000f9a4  mov     [rbp+57h+var_40], rax
0x14000f9a8  mov     rax, [r8+138h]
0x14000f9af  xor     r8d, r8d; ActivityId
0x14000f9b2  mov     [rbp+57h+var_30], rax
0x14000f9b6  lea     rax, [rbp+57h+arg_8]
0x14000f9ba  mov     [rbp+57h+var_20], rax
0x14000f9be  lea     rax, [rbp+57h+var_50]
0x14000f9c2  mov     [rsp+90h+UserData], rax; UserData
0x14000f9c7  mov     qword ptr [rbp+57h+var_50.Size], 10h
0x14000f9cf  mov     [rbp+57h+var_38], 2
0x14000f9d7  mov     [rbp+57h+var_24], r10d
0x14000f9db  mov     [rbp+57h+var_18], r9
0x14000f9df  call    cs:__imp_EtwWrite
0x14000f9e6  nop     dword ptr [rax+rax+00h]
0x14000f9eb  mov     rcx, [rbp+57h+var_10]
0x14000f9ef  xor     rcx, rsp; StackCookie
0x14000f9f2  call    __security_check_cookie
0x14000f9f7  add     rsp, 90h
0x14000f9fe  pop     rbp
0x14000f9ff  retn
```
