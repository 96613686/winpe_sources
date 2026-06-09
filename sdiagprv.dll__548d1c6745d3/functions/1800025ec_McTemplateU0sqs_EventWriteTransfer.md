# McTemplateU0sqs_EventWriteTransfer

- ea: `0x1800025ec`
- end: `0x1800026ac`
- name: `McTemplateU0sqs_EventWriteTransfer`
- size: `192`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, int, const char *)`
- caller_count: `111`
- callee_count: `3`
- tags: ``

## callers

- `0x180002240`
- `0x180003930`
- `0x180003a30`
- `0x180003b50`
- `0x180003c30`
- `0x1800046b0`
- `0x180004a30`
- `0x180004f50`
- `0x180005040`
- `0x180005190`
- `0x180006a78`
- `0x180006cd0`
- `0x180006fa0`
- `0x1800078d8`
- `0x180007bc0`
- `0x180007e2c`
- `0x180008070`
- `0x180008220`
- `0x18000855c`
- `0x180008710`
- `0x1800087e0`
- `0x180008cdc`
- `0x180008f00`
- `0x180009728`
- `0x180009da0`
- `0x180009e60`
- `0x18000ac18`
- `0x18000b890`
- `0x18000b9f0`
- `0x18000c018`
- `0x18000c1d4`
- `0x18000c2a0`
- `0x18000c618`
- `0x18000cc30`
- `0x18000cee0`
- `0x18000d244`
- `0x18000d418`
- `0x18000d748`
- `0x18000daa0`
- `0x18000dc8c`
- `0x18000e1bc`
- `0x18000e3e8`
- `0x18000e7f4`
- `0x18000f0ec`
- `0x18000f654`
- `0x18000fac8`
- `0x18000fc2c`
- `0x18000fd98`
- `0x18000fe60`
- `0x180010938`

## callees

- `0x18000247c`
- `0x1800025ec`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqs_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4, const char *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const char *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  const char *v13; // [rsp+40h] [rbp-40h]
  int v14; // [rsp+48h] [rbp-38h]
  int v15; // [rsp+4Ch] [rbp-34h]
  int *v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+58h] [rbp-28h]
  const char *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A8h] [rbp+28h] BYREF

  v21 = a4;
  v5 = -1;
  v6 = 5;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  v14 = v8;
  v15 = 0;
  v16 = &v21;
  v9 = a5;
  if ( !a3 )
    a3 = "NULL";
  v13 = a3;
  v17 = 4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = v5 + 1;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = "NULL";
  v19 = v6;
  v20 = 0;
  v18 = v9;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v9,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_INVALIDARG,
           4,
           4u,
           &v12);
}

```

## disassembly

```asm
0x1800025ec  mov     [rsp-8+arg_18], r9d
0x1800025f1  push    rbp
0x1800025f2  mov     rbp, rsp
0x1800025f5  sub     rsp, 80h
0x1800025fc  mov     rax, cs:__security_cookie
0x180002603  xor     rax, rsp
0x180002606  mov     [rbp+var_10], rax
0x18000260a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000260e  xor     r9d, r9d
0x180002611  mov     edx, 5
0x180002616  test    r8, r8
0x180002619  jz      short loc_18000262B
0x18000261b  mov     rcx, rax
0x18000261e  inc     rcx
0x180002621  cmp     [r8+rcx], r9b
0x180002625  jnz     short loc_18000261E
0x180002627  inc     ecx
0x180002629  jmp     short loc_18000262D
0x18000262b  mov     ecx, edx
0x18000262d  test    r8, r8
0x180002630  mov     [rbp+var_38], ecx
0x180002633  lea     rcx, [rbp+arg_18]
0x180002637  mov     [rbp+var_34], r9d
0x18000263b  lea     r10, aNull; "NULL"
0x180002642  mov     [rbp+var_30], rcx
0x180002646  mov     rcx, [rbp+arg_20]
0x18000264a  cmovz   r8, r10
0x18000264e  mov     [rbp+var_40], r8
0x180002652  mov     r8d, 4
0x180002658  mov     [rbp+var_28], r8
0x18000265c  test    rcx, rcx
0x18000265f  jz      short loc_180002670
0x180002661  inc     rax
0x180002664  cmp     [rcx+rax], r9b
0x180002668  jnz     short loc_180002661
0x18000266a  lea     edx, [rax+1]
0x18000266d  test    rcx, rcx
0x180002670  cmovz   rcx, r10
0x180002674  mov     [rbp+var_18], edx
0x180002677  mov     [rbp+var_14], r9d
0x18000267b  lea     rax, [rbp+var_50]
0x18000267f  mov     r9d, r8d
0x180002682  mov     [rbp+var_20], rcx
0x180002686  lea     rdx, SDIAGPRV_EVENT_DEBUG_INVALIDARG
0x18000268d  mov     [rsp+80h+var_60], rax
0x180002692  call    McGenEventWrite_EventWriteTransfer
0x180002697  mov     rcx, [rbp+var_10]
0x18000269b  xor     rcx, rsp; StackCookie
0x18000269e  call    __security_check_cookie
0x1800026a3  add     rsp, 80h
0x1800026aa  pop     rbp
0x1800026ab  retn
```
