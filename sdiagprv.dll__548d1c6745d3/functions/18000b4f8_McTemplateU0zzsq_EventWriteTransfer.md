# McTemplateU0zzsq_EventWriteTransfer

- ea: `0x18000b4f8`
- end: `0x18000b5f3`
- name: `McTemplateU0zzsq_EventWriteTransfer`
- size: `251`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, const char *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000b4f8`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzsq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const char *a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  bool v10; // zf
  __int64 v11; // rcx
  const char *v12; // rcx
  int v13; // eax
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-9h]
  int v17; // [rsp+48h] [rbp-1h]
  int v18; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v19; // [rsp+50h] [rbp+7h]
  int v20; // [rsp+58h] [rbp+Fh]
  int v21; // [rsp+5Ch] [rbp+13h]
  const char *v22; // [rsp+60h] [rbp+17h]
  int v23; // [rsp+68h] [rbp+1Fh]
  int v24; // [rsp+6Ch] [rbp+23h]
  char *v25; // [rsp+70h] [rbp+27h]
  __int64 v26; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v17 = v9;
  v18 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v16 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v7 = 2 * v11 + 2;
    v10 = a4 == 0;
  }
  v12 = a5;
  if ( v10 )
    a4 = L"NULL";
  v19 = a4;
  v20 = v7;
  v21 = 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v13 = v6 + 1;
  }
  else
  {
    v13 = 5;
  }
  v23 = v13;
  v24 = 0;
  v25 = &a6;
  v26 = 4;
  if ( !a5 )
    v12 = "NULL";
  v22 = v12;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v12,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_PARSE_RESPONSE_END,
           (__int64)a3,
           5u,
           &v15);
}

```

## disassembly

```asm
0x18000b4f8  push    rbp
0x18000b4fa  lea     rbp, [rsp-47h]
0x18000b4ff  sub     rsp, 90h
0x18000b506  mov     rax, cs:__security_cookie
0x18000b50d  xor     rax, rsp
0x18000b510  mov     [rbp+47h+var_10], rax
0x18000b514  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b518  xor     r10d, r10d
0x18000b51b  mov     edx, 0Ah
0x18000b520  test    r8, r8
0x18000b523  jz      short loc_18000B53B
0x18000b525  mov     rcx, rax
0x18000b528  inc     rcx
0x18000b52b  cmp     [r8+rcx*2], r10w
0x18000b530  jnz     short loc_18000B528
0x18000b532  lea     ecx, ds:2[rcx*2]
0x18000b539  jmp     short loc_18000B53D
0x18000b53b  mov     ecx, edx
0x18000b53d  test    r8, r8
0x18000b540  mov     [rbp+47h+var_48], ecx
0x18000b543  lea     r11, aNull_0; "NULL"
0x18000b54a  mov     [rbp+47h+var_44], r10d
0x18000b54e  cmovz   r8, r11
0x18000b552  mov     [rbp+47h+var_50], r8
0x18000b556  test    r9, r9
0x18000b559  jz      short loc_18000B572
0x18000b55b  mov     rcx, rax
0x18000b55e  inc     rcx
0x18000b561  cmp     [r9+rcx*2], r10w
0x18000b566  jnz     short loc_18000B55E
0x18000b568  lea     edx, ds:2[rcx*2]
0x18000b56f  test    r9, r9
0x18000b572  mov     rcx, [rbp+47h+arg_20]
0x18000b576  cmovz   r9, r11
0x18000b57a  mov     [rbp+47h+var_40], r9
0x18000b57e  mov     r9d, 5
0x18000b584  mov     [rbp+47h+var_38], edx
0x18000b587  mov     [rbp+47h+var_34], r10d
0x18000b58b  test    rcx, rcx
0x18000b58e  jz      short loc_18000B59D
0x18000b590  inc     rax
0x18000b593  cmp     [rcx+rax], r10b
0x18000b597  jnz     short loc_18000B590
0x18000b599  inc     eax
0x18000b59b  jmp     short loc_18000B5A0
0x18000b59d  mov     eax, r9d
0x18000b5a0  mov     [rbp+47h+var_28], eax
0x18000b5a3  lea     rdx, aNull; "NULL"
0x18000b5aa  lea     rax, [rbp+47h+arg_28]
0x18000b5ae  mov     [rbp+47h+var_24], r10d
0x18000b5b2  test    rcx, rcx
0x18000b5b5  mov     [rbp+47h+var_20], rax
0x18000b5b9  lea     rax, [rbp+47h+var_60]
0x18000b5bd  mov     [rbp+47h+var_18], 4
0x18000b5c5  cmovz   rcx, rdx
0x18000b5c9  mov     [rsp+90h+var_70], rax
0x18000b5ce  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_PARSE_RESPONSE_END
0x18000b5d5  mov     [rbp+47h+var_30], rcx
0x18000b5d9  call    McGenEventWrite_EventWriteTransfer
0x18000b5de  mov     rcx, [rbp+47h+var_10]
0x18000b5e2  xor     rcx, rsp; StackCookie
0x18000b5e5  call    __security_check_cookie
0x18000b5ea  add     rsp, 90h
0x18000b5f1  pop     rbp
0x18000b5f2  retn
```
