# McTemplateU0zjzz_EventWriteTransfer

- ea: `0x180002cb0`
- end: `0x180002dbd`
- name: `McTemplateU0zjzz_EventWriteTransfer`
- size: `269`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x1800027d8`
- `0x180002dd0`
- `0x180003a20`
- `0x180004300`
- `0x1800080a4`
- `0x180008230`
- `0x1800084c0`
- `0x1800094a8`
- `0x18000a820`
- `0x18000aa60`
- `0x18000ac20`
- `0x18000aef0`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`

## callees

- `0x180002c5c`
- `0x180002cb0`
- `0x18001f980`

## pseudocode

```c
ULONG __fastcall McTemplateU0zjzz_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        __int64 a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v9; // r10d
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-29h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-19h]
  int v20; // [rsp+48h] [rbp-11h]
  int v21; // [rsp+4Ch] [rbp-Dh]
  __int64 v22; // [rsp+50h] [rbp-9h]
  __int64 v23; // [rsp+58h] [rbp-1h]
  const wchar_t *v24; // [rsp+60h] [rbp+7h]
  int v25; // [rsp+68h] [rbp+Fh]
  int v26; // [rsp+6Ch] [rbp+13h]
  const wchar_t *v27; // [rsp+70h] [rbp+17h]
  int v28; // [rsp+78h] [rbp+1Fh]
  int v29; // [rsp+7Ch] [rbp+23h]

  v6 = -1;
  v9 = 10;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v20 = v11;
  v12 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v21 = 0;
  v19 = a3;
  v22 = a4;
  v23 = 16;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v25 = v14;
  v26 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v24 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v9 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v28 = v9;
  v27 = v15;
  v29 = 0;
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 5u, &v18);
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp-8+arg_10], rbx
0x180002cb5  push    rbp
0x180002cb6  push    rsi
0x180002cb7  push    rdi
0x180002cb8  lea     rbp, [rsp-37h]
0x180002cbd  sub     rsp, 90h
0x180002cc4  mov     rax, cs:__security_cookie
0x180002ccb  xor     rax, rsp
0x180002cce  mov     [rbp+47h+var_20], rax
0x180002cd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002cd6  xor     edi, edi
0x180002cd8  mov     rbx, rdx
0x180002cdb  mov     r11, rcx
0x180002cde  mov     r10d, 0Ah
0x180002ce4  test    r8, r8
0x180002ce7  jz      short loc_180002CFF
0x180002ce9  mov     rcx, rax
0x180002cec  inc     rcx
0x180002cef  cmp     [r8+rcx*2], di
0x180002cf4  jnz     short loc_180002CEC
0x180002cf6  lea     ecx, ds:2[rcx*2]
0x180002cfd  jmp     short loc_180002D02
0x180002cff  mov     ecx, r10d
0x180002d02  test    r8, r8
0x180002d05  mov     [rbp+47h+var_58], ecx
0x180002d08  mov     rcx, [rbp+47h+arg_20]
0x180002d0c  lea     rsi, aNull; "NULL"
0x180002d13  cmovz   r8, rsi
0x180002d17  mov     [rbp+47h+var_54], edi
0x180002d1a  mov     [rbp+47h+var_60], r8
0x180002d1e  mov     [rbp+47h+var_50], r9
0x180002d22  mov     [rbp+47h+var_48], 10h
0x180002d2a  test    rcx, rcx
0x180002d2d  jz      short loc_180002D44
0x180002d2f  mov     rdx, rax
0x180002d32  inc     rdx
0x180002d35  cmp     [rcx+rdx*2], di
0x180002d39  jnz     short loc_180002D32
0x180002d3b  lea     edx, ds:2[rdx*2]
0x180002d42  jmp     short loc_180002D47
0x180002d44  mov     edx, r10d
0x180002d47  test    rcx, rcx
0x180002d4a  mov     [rbp+47h+var_38], edx
0x180002d4d  mov     [rbp+47h+var_34], edi
0x180002d50  cmovz   rcx, rsi
0x180002d54  mov     [rbp+47h+var_40], rcx
0x180002d58  mov     rcx, [rbp+47h+arg_28]
0x180002d5c  test    rcx, rcx
0x180002d5f  jz      short loc_180002D75
0x180002d61  inc     rax
0x180002d64  cmp     [rcx+rax*2], di
0x180002d68  jnz     short loc_180002D61
0x180002d6a  lea     r10d, ds:2[rax*2]
0x180002d72  test    rcx, rcx
0x180002d75  cmovz   rcx, rsi
0x180002d79  mov     [rbp+47h+var_28], r10d
0x180002d7d  mov     [rbp+47h+var_30], rcx
0x180002d81  lea     rax, [rbp+47h+var_70]
0x180002d85  mov     rcx, r11
0x180002d88  mov     [rbp+47h+var_24], edi
0x180002d8b  mov     r9d, 5
0x180002d91  mov     [rsp+0A0h+var_80], rax
0x180002d96  mov     rdx, rbx
0x180002d99  call    McGenEventWrite_EventWriteTransfer
0x180002d9e  mov     rcx, [rbp+47h+var_20]
0x180002da2  xor     rcx, rsp; StackCookie
0x180002da5  call    __security_check_cookie
0x180002daa  mov     rbx, [rsp+0A0h+arg_10]
0x180002db2  add     rsp, 90h
0x180002db9  pop     rdi
0x180002dba  pop     rsi
0x180002dbb  pop     rbp
0x180002dbc  retn
```
