# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x180011aa8`
- end: `0x180011bd6`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `302`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010938`
- `0x18001114c`

## callees

- `0x18000247c`
- `0x180011aa8`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v7; // r10d
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-9h]
  int v20; // [rsp+48h] [rbp-1h]
  int v21; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v22; // [rsp+50h] [rbp+7h]
  int v23; // [rsp+58h] [rbp+Fh]
  int v24; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v25; // [rsp+60h] [rbp+17h]
  int v26; // [rsp+68h] [rbp+1Fh]
  int v27; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v28; // [rsp+70h] [rbp+27h]
  int v29; // [rsp+78h] [rbp+2Fh]
  int v30; // [rsp+7Ch] [rbp+33h]

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
  v20 = v9;
  v21 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v19 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v23 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 0;
  v22 = a4;
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
  v26 = v14;
  v27 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v25 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v29 = v7;
  v28 = v15;
  v30 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_SEARCH_RESULT,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x180011aa8  mov     [rsp-8+arg_0], rbx
0x180011aad  push    rbp
0x180011aae  lea     rbp, [rsp-47h]
0x180011ab3  sub     rsp, 90h
0x180011aba  mov     rax, cs:__security_cookie
0x180011ac1  xor     rax, rsp
0x180011ac4  mov     [rbp+47h+var_10], rax
0x180011ac8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011acc  xor     r11d, r11d
0x180011acf  mov     r10d, 0Ah
0x180011ad5  test    r8, r8
0x180011ad8  jz      short loc_180011AF0
0x180011ada  mov     rcx, rax
0x180011add  inc     rcx
0x180011ae0  cmp     [r8+rcx*2], r11w
0x180011ae5  jnz     short loc_180011ADD
0x180011ae7  lea     ecx, ds:2[rcx*2]
0x180011aee  jmp     short loc_180011AF3
0x180011af0  mov     ecx, r10d
0x180011af3  test    r8, r8
0x180011af6  mov     [rbp+47h+var_48], ecx
0x180011af9  lea     rbx, aNull_0; "NULL"
0x180011b00  mov     [rbp+47h+var_44], r11d
0x180011b04  cmovz   r8, rbx
0x180011b08  mov     [rbp+47h+var_50], r8
0x180011b0c  test    r9, r9
0x180011b0f  jz      short loc_180011B27
0x180011b11  mov     rcx, rax
0x180011b14  inc     rcx
0x180011b17  cmp     [r9+rcx*2], r11w
0x180011b1c  jnz     short loc_180011B14
0x180011b1e  lea     ecx, ds:2[rcx*2]
0x180011b25  jmp     short loc_180011B2A
0x180011b27  mov     ecx, r10d
0x180011b2a  test    r9, r9
0x180011b2d  mov     [rbp+47h+var_38], ecx
0x180011b30  mov     rcx, [rbp+47h+arg_20]
0x180011b34  cmovz   r9, rbx
0x180011b38  mov     [rbp+47h+var_34], r11d
0x180011b3c  mov     [rbp+47h+var_40], r9
0x180011b40  test    rcx, rcx
0x180011b43  jz      short loc_180011B5B
0x180011b45  mov     rdx, rax
0x180011b48  inc     rdx
0x180011b4b  cmp     [rcx+rdx*2], r11w
0x180011b50  jnz     short loc_180011B48
0x180011b52  lea     edx, ds:2[rdx*2]
0x180011b59  jmp     short loc_180011B5E
0x180011b5b  mov     edx, r10d
0x180011b5e  test    rcx, rcx
0x180011b61  mov     [rbp+47h+var_28], edx
0x180011b64  mov     [rbp+47h+var_24], r11d
0x180011b68  cmovz   rcx, rbx
0x180011b6c  mov     [rbp+47h+var_30], rcx
0x180011b70  mov     rcx, [rbp+47h+arg_28]
0x180011b74  test    rcx, rcx
0x180011b77  jz      short loc_180011B8E
0x180011b79  inc     rax
0x180011b7c  cmp     [rcx+rax*2], r11w
0x180011b81  jnz     short loc_180011B79
0x180011b83  lea     r10d, ds:2[rax*2]
0x180011b8b  test    rcx, rcx
0x180011b8e  cmovz   rcx, rbx
0x180011b92  mov     [rbp+47h+var_18], r10d
0x180011b96  lea     rax, [rbp+47h+var_60]
0x180011b9a  mov     [rbp+47h+var_20], rcx
0x180011b9e  mov     r9d, 5
0x180011ba4  mov     [rsp+90h+var_70], rax
0x180011ba9  lea     rdx, SDIAGPRV_EVENT_DEBUG_SEARCH_RESULT
0x180011bb0  mov     [rbp+47h+var_14], r11d
0x180011bb4  call    McGenEventWrite_EventWriteTransfer
0x180011bb9  mov     rcx, [rbp+47h+var_10]
0x180011bbd  xor     rcx, rsp; StackCookie
0x180011bc0  call    __security_check_cookie
0x180011bc5  mov     rbx, [rsp+90h+arg_0]
0x180011bcd  add     rsp, 90h
0x180011bd4  pop     rbp
0x180011bd5  retn
```
