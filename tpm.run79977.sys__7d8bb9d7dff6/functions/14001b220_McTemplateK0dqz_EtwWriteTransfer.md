# McTemplateK0dqz_EtwWriteTransfer

- ea: `0x14001b220`
- end: `0x14001b2c4`
- name: `McTemplateK0dqz_EtwWriteTransfer`
- size: `164`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400116fc`
- `0x140016628`
- `0x1400171d0`

## callees

- `0x140014ac4`
- `0x14001b220`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dqz_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-50h] BYREF
  int *v11; // [rsp+40h] [rbp-40h]
  __int64 v12; // [rsp+48h] [rbp-38h]
  char *v13; // [rsp+50h] [rbp-30h]
  __int64 v14; // [rsp+58h] [rbp-28h]
  const wchar_t *v15; // [rsp+60h] [rbp-20h]
  int v16; // [rsp+68h] [rbp-18h]
  int v17; // [rsp+6Ch] [rbp-14h]
  int v18; // [rsp+A8h] [rbp+28h] BYREF

  v18 = a4;
  v6 = a6;
  v11 = &v18;
  v12 = 4;
  v14 = 4;
  v13 = &a5;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v17 = 0;
  if ( !a6 )
    v6 = L"NULL";
  v15 = v6;
  return McGenEventWrite_EtwWriteTransfer((__int64)v6, a2, (__int64)L"NULL", 4u, &v10);
}

```

## disassembly

```asm
0x14001b220  mov     [rsp-8+arg_18], r9d
0x14001b225  push    rbp
0x14001b226  mov     rbp, rsp
0x14001b229  sub     rsp, 80h
0x14001b230  mov     rax, cs:__security_cookie
0x14001b237  xor     rax, rsp
0x14001b23a  mov     [rbp+var_10], rax
0x14001b23e  mov     rcx, [rbp+arg_28]
0x14001b242  lea     rax, [rbp+arg_18]
0x14001b246  mov     r10d, 4
0x14001b24c  mov     [rbp+var_40], rax
0x14001b250  xor     r9d, r9d
0x14001b253  mov     [rbp+var_38], r10
0x14001b257  mov     [rbp+var_28], r10
0x14001b25b  lea     rax, [rbp+arg_20]
0x14001b25f  mov     [rbp+var_30], rax
0x14001b263  test    rcx, rcx
0x14001b266  jz      short loc_14001B27F
0x14001b268  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b26c  inc     rax
0x14001b26f  cmp     [rcx+rax*2], r9w
0x14001b274  jnz     short loc_14001B26C
0x14001b276  lea     eax, ds:2[rax*2]
0x14001b27d  jmp     short loc_14001B284
0x14001b27f  mov     eax, 0Ah
0x14001b284  test    rcx, rcx
0x14001b287  mov     [rbp+var_18], eax
0x14001b28a  lea     r8, aNull_0; "NULL"
0x14001b291  mov     [rbp+var_14], r9d
0x14001b295  cmovz   rcx, r8
0x14001b299  lea     rax, [rbp+var_50]
0x14001b29d  mov     r9d, r10d
0x14001b2a0  mov     [rbp+var_20], rcx
0x14001b2a4  mov     [rsp+80h+var_60], rax
0x14001b2a9  call    McGenEventWrite_EtwWriteTransfer
0x14001b2ae  mov     rcx, [rbp+var_10]
0x14001b2b2  xor     rcx, rsp; StackCookie
0x14001b2b5  call    __security_check_cookie
0x14001b2ba  add     rsp, 80h
0x14001b2c1  pop     rbp
0x14001b2c2  retn
```
