# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x1800208ec`
- end: `0x180020a1b`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e334`

## callees

- `0x180020808`
- `0x1800208ec`
- `0x1800319f0`

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
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_Configuration,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x1800208ec  mov     [rsp-8+arg_0], rbx
0x1800208f1  push    rbp
0x1800208f2  lea     rbp, [rsp-47h]
0x1800208f7  sub     rsp, 90h
0x1800208fe  mov     rax, cs:__security_cookie
0x180020905  xor     rax, rsp
0x180020908  mov     [rbp+47h+var_10], rax
0x18002090c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020910  xor     r11d, r11d
0x180020913  mov     r10d, 0Ah
0x180020919  test    r8, r8
0x18002091c  jz      short loc_180020934
0x18002091e  mov     rcx, rax
0x180020921  inc     rcx
0x180020924  cmp     [r8+rcx*2], r11w
0x180020929  jnz     short loc_180020921
0x18002092b  lea     ecx, ds:2[rcx*2]
0x180020932  jmp     short loc_180020937
0x180020934  mov     ecx, r10d
0x180020937  test    r8, r8
0x18002093a  mov     [rbp+47h+var_48], ecx
0x18002093d  lea     rbx, aNull; "NULL"
0x180020944  mov     [rbp+47h+var_44], r11d
0x180020948  cmovz   r8, rbx
0x18002094c  mov     [rbp+47h+var_50], r8
0x180020950  test    r9, r9
0x180020953  jz      short loc_18002096B
0x180020955  mov     rcx, rax
0x180020958  inc     rcx
0x18002095b  cmp     [r9+rcx*2], r11w
0x180020960  jnz     short loc_180020958
0x180020962  lea     ecx, ds:2[rcx*2]
0x180020969  jmp     short loc_18002096E
0x18002096b  mov     ecx, r10d
0x18002096e  test    r9, r9
0x180020971  mov     [rbp+47h+var_38], ecx
0x180020974  mov     rcx, [rbp+47h+arg_20]
0x180020978  cmovz   r9, rbx
0x18002097c  mov     [rbp+47h+var_34], r11d
0x180020980  mov     [rbp+47h+var_40], r9
0x180020984  test    rcx, rcx
0x180020987  jz      short loc_18002099F
0x180020989  mov     rdx, rax
0x18002098c  inc     rdx
0x18002098f  cmp     [rcx+rdx*2], r11w
0x180020994  jnz     short loc_18002098C
0x180020996  lea     edx, ds:2[rdx*2]
0x18002099d  jmp     short loc_1800209A2
0x18002099f  mov     edx, r10d
0x1800209a2  test    rcx, rcx
0x1800209a5  mov     [rbp+47h+var_28], edx
0x1800209a8  mov     [rbp+47h+var_24], r11d
0x1800209ac  cmovz   rcx, rbx
0x1800209b0  mov     [rbp+47h+var_30], rcx
0x1800209b4  mov     rcx, [rbp+47h+arg_28]
0x1800209b8  test    rcx, rcx
0x1800209bb  jz      short loc_1800209D2
0x1800209bd  inc     rax
0x1800209c0  cmp     [rcx+rax*2], r11w
0x1800209c5  jnz     short loc_1800209BD
0x1800209c7  lea     r10d, ds:2[rax*2]
0x1800209cf  test    rcx, rcx
0x1800209d2  cmovz   rcx, rbx
0x1800209d6  mov     [rbp+47h+var_18], r10d
0x1800209da  lea     rax, [rbp+47h+var_60]
0x1800209de  mov     [rbp+47h+var_20], rcx
0x1800209e2  mov     r9d, 5
0x1800209e8  mov     [rsp+90h+var_70], rax
0x1800209ed  lea     rdx, TraceMerge_NGEN_Configuration
0x1800209f4  mov     [rbp+47h+var_14], r11d
0x1800209f8  call    McGenEventWrite_EventWriteTransfer
0x1800209fd  mov     rcx, [rbp+47h+var_10]
0x180020a01  xor     rcx, rsp; StackCookie
0x180020a04  call    __security_check_cookie
0x180020a09  mov     rbx, [rsp+90h+arg_0]
0x180020a11  add     rsp, 90h
0x180020a18  pop     rbp
0x180020a19  retn
```
