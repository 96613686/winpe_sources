# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x180013814`
- end: `0x180013942`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010938`

## callees

- `0x1800137bc`
- `0x180013814`
- `0x180016c50`

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
           (const EVENT_DESCRIPTOR *)ProcessTerminationSelf,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x180013814  mov     [rsp-8+arg_0], rbx
0x180013819  push    rbp
0x18001381a  lea     rbp, [rsp-47h]
0x18001381f  sub     rsp, 90h
0x180013826  mov     rax, cs:__security_cookie
0x18001382d  xor     rax, rsp
0x180013830  mov     [rbp+47h+var_10], rax
0x180013834  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013838  xor     r11d, r11d
0x18001383b  mov     r10d, 0Ah
0x180013841  test    r8, r8
0x180013844  jz      short loc_18001385C
0x180013846  mov     rcx, rax
0x180013849  inc     rcx
0x18001384c  cmp     [r8+rcx*2], r11w
0x180013851  jnz     short loc_180013849
0x180013853  lea     ecx, ds:2[rcx*2]
0x18001385a  jmp     short loc_18001385F
0x18001385c  mov     ecx, r10d
0x18001385f  test    r8, r8
0x180013862  mov     [rbp+47h+var_48], ecx
0x180013865  lea     rbx, aNull; "NULL"
0x18001386c  mov     [rbp+47h+var_44], r11d
0x180013870  cmovz   r8, rbx
0x180013874  mov     [rbp+47h+var_50], r8
0x180013878  test    r9, r9
0x18001387b  jz      short loc_180013893
0x18001387d  mov     rcx, rax
0x180013880  inc     rcx
0x180013883  cmp     [r9+rcx*2], r11w
0x180013888  jnz     short loc_180013880
0x18001388a  lea     ecx, ds:2[rcx*2]
0x180013891  jmp     short loc_180013896
0x180013893  mov     ecx, r10d
0x180013896  test    r9, r9
0x180013899  mov     [rbp+47h+var_38], ecx
0x18001389c  mov     rcx, [rbp+47h+arg_20]
0x1800138a0  cmovz   r9, rbx
0x1800138a4  mov     [rbp+47h+var_34], r11d
0x1800138a8  mov     [rbp+47h+var_40], r9
0x1800138ac  test    rcx, rcx
0x1800138af  jz      short loc_1800138C7
0x1800138b1  mov     rdx, rax
0x1800138b4  inc     rdx
0x1800138b7  cmp     [rcx+rdx*2], r11w
0x1800138bc  jnz     short loc_1800138B4
0x1800138be  lea     edx, ds:2[rdx*2]
0x1800138c5  jmp     short loc_1800138CA
0x1800138c7  mov     edx, r10d
0x1800138ca  test    rcx, rcx
0x1800138cd  mov     [rbp+47h+var_28], edx
0x1800138d0  mov     [rbp+47h+var_24], r11d
0x1800138d4  cmovz   rcx, rbx
0x1800138d8  mov     [rbp+47h+var_30], rcx
0x1800138dc  mov     rcx, [rbp+47h+arg_28]
0x1800138e0  test    rcx, rcx
0x1800138e3  jz      short loc_1800138FA
0x1800138e5  inc     rax
0x1800138e8  cmp     [rcx+rax*2], r11w
0x1800138ed  jnz     short loc_1800138E5
0x1800138ef  lea     r10d, ds:2[rax*2]
0x1800138f7  test    rcx, rcx
0x1800138fa  cmovz   rcx, rbx
0x1800138fe  mov     [rbp+47h+var_18], r10d
0x180013902  lea     rax, [rbp+47h+var_60]
0x180013906  mov     [rbp+47h+var_20], rcx
0x18001390a  mov     r9d, 5
0x180013910  mov     [rsp+90h+var_70], rax
0x180013915  lea     rdx, ProcessTerminationSelf
0x18001391c  mov     [rbp+47h+var_14], r11d
0x180013920  call    McGenEventWrite_EventWriteTransfer
0x180013925  mov     rcx, [rbp+47h+var_10]
0x180013929  xor     rcx, rsp; StackCookie
0x18001392c  call    __security_check_cookie
0x180013931  mov     rbx, [rsp+90h+arg_0]
0x180013939  add     rsp, 90h
0x180013940  pop     rbp
0x180013941  retn
```
