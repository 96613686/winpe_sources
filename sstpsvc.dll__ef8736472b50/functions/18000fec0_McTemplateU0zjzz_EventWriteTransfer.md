# McTemplateU0zjzz_EventWriteTransfer

- ea: `0x18000fec0`
- end: `0x18000ffce`
- name: `McTemplateU0zjzz_EventWriteTransfer`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008c14`
- `0x18000fec0`
- `0x18001d210`

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
0x18000fec0  mov     [rsp-8+arg_10], rbx
0x18000fec5  push    rbp
0x18000fec6  push    rsi
0x18000fec7  push    rdi
0x18000fec8  lea     rbp, [rsp-37h]
0x18000fecd  sub     rsp, 90h
0x18000fed4  mov     rax, cs:__security_cookie
0x18000fedb  xor     rax, rsp
0x18000fede  mov     [rbp+47h+var_20], rax
0x18000fee2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fee6  xor     edi, edi
0x18000fee8  mov     rbx, rdx
0x18000feeb  mov     r11, rcx
0x18000feee  mov     r10d, 0Ah
0x18000fef4  test    r8, r8
0x18000fef7  jz      short loc_18000FF0F
0x18000fef9  mov     rcx, rax
0x18000fefc  inc     rcx
0x18000feff  cmp     [r8+rcx*2], di
0x18000ff04  jnz     short loc_18000FEFC
0x18000ff06  lea     ecx, ds:2[rcx*2]
0x18000ff0d  jmp     short loc_18000FF12
0x18000ff0f  mov     ecx, r10d
0x18000ff12  test    r8, r8
0x18000ff15  mov     [rbp+47h+var_58], ecx
0x18000ff18  mov     rcx, [rbp+47h+arg_20]
0x18000ff1c  lea     rsi, aNull; "NULL"
0x18000ff23  cmovz   r8, rsi
0x18000ff27  mov     [rbp+47h+var_54], edi
0x18000ff2a  mov     [rbp+47h+var_60], r8
0x18000ff2e  mov     [rbp+47h+var_50], r9
0x18000ff32  mov     [rbp+47h+var_48], 10h
0x18000ff3a  test    rcx, rcx
0x18000ff3d  jz      short loc_18000FF54
0x18000ff3f  mov     rdx, rax
0x18000ff42  inc     rdx
0x18000ff45  cmp     [rcx+rdx*2], di
0x18000ff49  jnz     short loc_18000FF42
0x18000ff4b  lea     edx, ds:2[rdx*2]
0x18000ff52  jmp     short loc_18000FF57
0x18000ff54  mov     edx, r10d
0x18000ff57  test    rcx, rcx
0x18000ff5a  mov     [rbp+47h+var_38], edx
0x18000ff5d  mov     [rbp+47h+var_34], edi
0x18000ff60  cmovz   rcx, rsi
0x18000ff64  mov     [rbp+47h+var_40], rcx
0x18000ff68  mov     rcx, [rbp+47h+arg_28]
0x18000ff6c  test    rcx, rcx
0x18000ff6f  jz      short loc_18000FF85
0x18000ff71  inc     rax
0x18000ff74  cmp     [rcx+rax*2], di
0x18000ff78  jnz     short loc_18000FF71
0x18000ff7a  lea     r10d, ds:2[rax*2]
0x18000ff82  test    rcx, rcx
0x18000ff85  cmovz   rcx, rsi
0x18000ff89  mov     [rbp+47h+var_28], r10d
0x18000ff8d  mov     [rbp+47h+var_30], rcx
0x18000ff91  lea     rax, [rbp+47h+var_70]
0x18000ff95  mov     rcx, r11
0x18000ff98  mov     [rbp+47h+var_24], edi
0x18000ff9b  mov     r9d, 5
0x18000ffa1  mov     [rsp+0A0h+var_80], rax
0x18000ffa6  mov     rdx, rbx
0x18000ffa9  call    McGenEventWrite_EventWriteTransfer
0x18000ffae  mov     rcx, [rbp+47h+var_20]
0x18000ffb2  xor     rcx, rsp; StackCookie
0x18000ffb5  call    __security_check_cookie
0x18000ffba  mov     rbx, [rsp+0A0h+arg_10]
0x18000ffc2  add     rsp, 90h
0x18000ffc9  pop     rdi
0x18000ffca  pop     rsi
0x18000ffcb  pop     rbp
0x18000ffcc  retn
```
