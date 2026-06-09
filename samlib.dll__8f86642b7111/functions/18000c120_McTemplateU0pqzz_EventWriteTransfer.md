# McTemplateU0pqzz_EventWriteTransfer

- ea: `0x18000c120`
- end: `0x18000c209`
- name: `McTemplateU0pqzz_EventWriteTransfer`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eca0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c120`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // edx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+40h] [rbp-9h]
  __int64 v16; // [rsp+48h] [rbp-1h]
  int *v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  __int64 v25; // [rsp+B0h] [rbp+67h] BYREF
  int v26; // [rsp+B8h] [rbp+6Fh] BYREF

  v26 = a4;
  v25 = a3;
  v6 = a5;
  v15 = &v25;
  v16 = 8;
  v17 = &v26;
  v7 = -1;
  v18 = 4;
  v8 = 10;
  if ( a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a5[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v20 = v10;
  v21 = 0;
  if ( !a5 )
    v6 = L"NULL";
  v19 = v6;
  v11 = a6;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v24 = 0;
  v22 = v11;
  v23 = v8;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v11,
           (const EVENT_DESCRIPTOR *)SamGetDisplayEnumerationIndexEntry,
           v8,
           5u,
           &v14);
}

```

## disassembly

```asm
0x18000c120  mov     [rsp-8+arg_18], r9d
0x18000c125  mov     [rsp-8+arg_10], r8
0x18000c12a  push    rbp
0x18000c12b  lea     rbp, [rsp-47h]
0x18000c130  sub     rsp, 90h
0x18000c137  mov     rax, cs:__security_cookie
0x18000c13e  xor     rax, rsp
0x18000c141  mov     [rbp+47h+var_10], rax
0x18000c145  mov     rcx, [rbp+47h+arg_20]
0x18000c149  lea     rax, [rbp+47h+arg_10]
0x18000c14d  mov     [rbp+47h+var_50], rax
0x18000c151  xor     r9d, r9d
0x18000c154  lea     rax, [rbp+47h+arg_18]
0x18000c158  mov     [rbp+47h+var_48], 8
0x18000c160  mov     [rbp+47h+var_40], rax
0x18000c164  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c168  mov     [rbp+47h+var_38], 4
0x18000c170  lea     r8d, [r9+0Ah]
0x18000c174  test    rcx, rcx
0x18000c177  jz      short loc_18000C18F
0x18000c179  mov     rdx, rax
0x18000c17c  inc     rdx
0x18000c17f  cmp     [rcx+rdx*2], r9w
0x18000c184  jnz     short loc_18000C17C
0x18000c186  lea     edx, ds:2[rdx*2]
0x18000c18d  jmp     short loc_18000C192
0x18000c18f  mov     edx, r8d
0x18000c192  test    rcx, rcx
0x18000c195  mov     [rbp+47h+var_28], edx
0x18000c198  lea     r10, aNull_0; "NULL"
0x18000c19f  mov     [rbp+47h+var_24], r9d
0x18000c1a3  cmovz   rcx, r10
0x18000c1a7  mov     [rbp+47h+var_30], rcx
0x18000c1ab  mov     rcx, [rbp+47h+arg_28]
0x18000c1af  test    rcx, rcx
0x18000c1b2  jz      short loc_18000C1C9
0x18000c1b4  inc     rax
0x18000c1b7  cmp     [rcx+rax*2], r9w
0x18000c1bc  jnz     short loc_18000C1B4
0x18000c1be  lea     r8d, ds:2[rax*2]
0x18000c1c6  test    rcx, rcx
0x18000c1c9  cmovz   rcx, r10
0x18000c1cd  mov     [rbp+47h+var_14], r9d
0x18000c1d1  lea     rax, [rbp+47h+var_60]
0x18000c1d5  mov     [rbp+47h+var_20], rcx
0x18000c1d9  mov     r9d, 5
0x18000c1df  mov     [rsp+90h+var_70], rax
0x18000c1e4  lea     rdx, SamGetDisplayEnumerationIndexEntry
0x18000c1eb  mov     [rbp+47h+var_18], r8d
0x18000c1ef  call    McGenEventWrite_EventWriteTransfer
0x18000c1f4  mov     rcx, [rbp+47h+var_10]
0x18000c1f8  xor     rcx, rsp; StackCookie
0x18000c1fb  call    __security_check_cookie
0x18000c200  add     rsp, 90h
0x18000c207  pop     rbp
0x18000c208  retn
```
