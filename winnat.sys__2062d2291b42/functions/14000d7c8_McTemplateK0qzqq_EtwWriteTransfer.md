# McTemplateK0qzqq_EtwWriteTransfer

- ea: `0x14000d7c8`
- end: `0x14000d890`
- name: `McTemplateK0qzqq_EtwWriteTransfer`
- size: `200`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x140014dcc`
- `0x140030b2c`
- `0x1400311f4`
- `0x1400319dc`
- `0x140033444`
- `0x140033518`
- `0x1400335e8`
- `0x140033730`
- `0x1400338a0`
- `0x140033968`
- `0x140033a78`
- `0x140034078`
- `0x140036078`
- `0x140036580`

## callees

- `0x1400095bc`
- `0x14000d7c8`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qzqq_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char a7)
{
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-21h] BYREF
  int *v13; // [rsp+40h] [rbp-11h]
  __int64 v14; // [rsp+48h] [rbp-9h]
  const wchar_t *v15; // [rsp+50h] [rbp-1h]
  int v16; // [rsp+58h] [rbp+7h]
  int v17; // [rsp+5Ch] [rbp+Bh]
  char *v18; // [rsp+60h] [rbp+Fh]
  __int64 v19; // [rsp+68h] [rbp+17h]
  char *v20; // [rsp+70h] [rbp+1Fh]
  __int64 v21; // [rsp+78h] [rbp+27h]
  int v22; // [rsp+B8h] [rbp+67h] BYREF

  v22 = a4;
  v14 = 4;
  v8 = a5;
  v13 = &v22;
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
  v16 = v10;
  v17 = 0;
  v19 = 4;
  if ( !a5 )
    v8 = L"NULL";
  v18 = &a6;
  v15 = v8;
  v20 = &a7;
  v21 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNATM_GENERAL_ERROR, (__int64)a1, 5u, &v12);
}

```

## disassembly

```asm
0x14000d7c8  mov     [rsp-8+arg_18], r9d
0x14000d7cd  push    rbp
0x14000d7ce  lea     rbp, [rsp-3Fh]
0x14000d7d3  sub     rsp, 90h
0x14000d7da  mov     rax, cs:__security_cookie
0x14000d7e1  xor     rax, rsp
0x14000d7e4  mov     [rbp+3Fh+var_10], rax
0x14000d7e8  mov     r8, rcx
0x14000d7eb  mov     [rbp+3Fh+var_48], 4
0x14000d7f3  mov     rcx, [rbp+3Fh+arg_20]
0x14000d7f7  lea     rax, [rbp+3Fh+arg_18]
0x14000d7fb  xor     r9d, r9d
0x14000d7fe  mov     [rbp+3Fh+var_50], rax
0x14000d802  test    rcx, rcx
0x14000d805  jz      short loc_14000D81E
0x14000d807  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d80b  inc     rax
0x14000d80e  cmp     [rcx+rax*2], r9w
0x14000d813  jnz     short loc_14000D80B
0x14000d815  lea     eax, ds:2[rax*2]
0x14000d81c  jmp     short loc_14000D823
0x14000d81e  mov     eax, 0Ah
0x14000d823  mov     [rbp+3Fh+var_38], eax
0x14000d826  lea     rdx, aNull; "NULL"
0x14000d82d  test    rcx, rcx
0x14000d830  mov     [rbp+3Fh+var_34], r9d
0x14000d834  lea     rax, [rbp+3Fh+arg_28]
0x14000d838  mov     [rbp+3Fh+var_28], 4
0x14000d840  cmovz   rcx, rdx
0x14000d844  mov     [rbp+3Fh+var_30], rax
0x14000d848  lea     rax, [rbp+3Fh+arg_30]
0x14000d84c  mov     [rbp+3Fh+var_40], rcx
0x14000d850  mov     [rbp+3Fh+var_20], rax
0x14000d854  lea     rdx, WINNATM_GENERAL_ERROR
0x14000d85b  lea     rax, [rbp+3Fh+var_60]
0x14000d85f  mov     [rbp+3Fh+var_18], 4
0x14000d867  mov     r9d, 5
0x14000d86d  mov     [rsp+90h+var_70], rax
0x14000d872  mov     rcx, r8
0x14000d875  call    McGenEventWrite_EtwWriteTransfer
0x14000d87a  mov     rcx, [rbp+3Fh+var_10]
0x14000d87e  xor     rcx, rsp; StackCookie
0x14000d881  call    __security_check_cookie
0x14000d886  add     rsp, 90h
0x14000d88d  pop     rbp
0x14000d88e  retn
```
