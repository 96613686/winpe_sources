# McTemplateU0pzqz_EventWriteTransfer

- ea: `0x18000c39c`
- end: `0x18000c478`
- name: `McTemplateU0pzqz_EventWriteTransfer`
- size: `220`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d330`
- `0x18000d630`
- `0x18000dde0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c39c`

## pseudocode

```c
ULONG __fastcall McTemplateU0pzqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+40h] [rbp-9h]
  __int64 v16; // [rsp+48h] [rbp-1h]
  const wchar_t *v17; // [rsp+50h] [rbp+7h]
  int v18; // [rsp+58h] [rbp+Fh]
  int v19; // [rsp+5Ch] [rbp+13h]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  __int64 v25; // [rsp+B0h] [rbp+67h] BYREF

  v25 = a3;
  v16 = 8;
  v15 = &v25;
  v6 = -1;
  v8 = 10;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v18 = v10;
  v19 = 0;
  v20 = &a5;
  v11 = a6;
  if ( !a4 )
    a4 = L"NULL";
  v21 = 4;
  v17 = a4;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v8 = 2 * v6 + 2;
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v23 = v8;
  v22 = v11;
  v24 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v11, a2, (__int64)a2, 5u, &v14);
}

```

## disassembly

```asm
0x18000c39c  mov     [rsp-8+arg_10], r8
0x18000c3a1  push    rbp
0x18000c3a2  lea     rbp, [rsp-47h]
0x18000c3a7  sub     rsp, 90h
0x18000c3ae  mov     rax, cs:__security_cookie
0x18000c3b5  xor     rax, rsp
0x18000c3b8  mov     [rbp+47h+var_10], rax
0x18000c3bc  lea     rax, [rbp+47h+arg_10]
0x18000c3c0  mov     [rbp+47h+var_48], 8
0x18000c3c8  xor     r10d, r10d
0x18000c3cb  mov     [rbp+47h+var_50], rax
0x18000c3cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c3d3  mov     r8, rdx
0x18000c3d6  lea     edx, [r10+0Ah]
0x18000c3da  test    r9, r9
0x18000c3dd  jz      short loc_18000C3F5
0x18000c3df  mov     rcx, rax
0x18000c3e2  inc     rcx
0x18000c3e5  cmp     [r9+rcx*2], r10w
0x18000c3ea  jnz     short loc_18000C3E2
0x18000c3ec  lea     ecx, ds:2[rcx*2]
0x18000c3f3  jmp     short loc_18000C3F7
0x18000c3f5  mov     ecx, edx
0x18000c3f7  mov     [rbp+47h+var_38], ecx
0x18000c3fa  lea     r11, aNull_0; "NULL"
0x18000c401  lea     rcx, [rbp+47h+arg_20]
0x18000c405  mov     [rbp+47h+var_34], r10d
0x18000c409  test    r9, r9
0x18000c40c  mov     [rbp+47h+var_30], rcx
0x18000c410  mov     rcx, [rbp+47h+arg_28]
0x18000c414  cmovz   r9, r11
0x18000c418  mov     [rbp+47h+var_28], 4
0x18000c420  mov     [rbp+47h+var_40], r9
0x18000c424  test    rcx, rcx
0x18000c427  jz      short loc_18000C43D
0x18000c429  inc     rax
0x18000c42c  cmp     [rcx+rax*2], r10w
0x18000c431  jnz     short loc_18000C429
0x18000c433  lea     edx, ds:2[rax*2]
0x18000c43a  test    rcx, rcx
0x18000c43d  cmovz   rcx, r11
0x18000c441  mov     [rbp+47h+var_18], edx
0x18000c444  lea     rax, [rbp+47h+var_60]
0x18000c448  mov     [rbp+47h+var_20], rcx
0x18000c44c  mov     rdx, r8
0x18000c44f  mov     [rsp+90h+var_70], rax
0x18000c454  mov     r9d, 5
0x18000c45a  mov     [rbp+47h+var_14], r10d
0x18000c45e  call    McGenEventWrite_EventWriteTransfer
0x18000c463  mov     rcx, [rbp+47h+var_10]
0x18000c467  xor     rcx, rsp; StackCookie
0x18000c46a  call    __security_check_cookie
0x18000c46f  add     rsp, 90h
0x18000c476  pop     rbp
0x18000c477  retn
```
