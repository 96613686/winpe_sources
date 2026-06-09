# McTemplateU0zzzzzz_EventWriteTransfer

- ea: `0x180013948`
- end: `0x180013ad3`
- name: `McTemplateU0zzzzzz_EventWriteTransfer`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010938`

## callees

- `0x1800137bc`
- `0x180013948`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        const wchar_t *a8)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // edx
  __int64 v12; // rdx
  int v13; // edx
  const wchar_t *v14; // rdx
  __int64 v15; // r8
  int v16; // r8d
  const wchar_t *v17; // rdx
  __int64 v18; // r8
  int v19; // r8d
  const wchar_t *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  const wchar_t *v23; // rdx
  bool v24; // zf
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+30h] [rbp-49h] BYREF
  const wchar_t *v27; // [rsp+40h] [rbp-39h]
  int v28; // [rsp+48h] [rbp-31h]
  int v29; // [rsp+4Ch] [rbp-2Dh]
  const wchar_t *v30; // [rsp+50h] [rbp-29h]
  int v31; // [rsp+58h] [rbp-21h]
  int v32; // [rsp+5Ch] [rbp-1Dh]
  const wchar_t *v33; // [rsp+60h] [rbp-19h]
  int v34; // [rsp+68h] [rbp-11h]
  int v35; // [rsp+6Ch] [rbp-Dh]
  const wchar_t *v36; // [rsp+70h] [rbp-9h]
  int v37; // [rsp+78h] [rbp-1h]
  int v38; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v39; // [rsp+80h] [rbp+7h]
  int v40; // [rsp+88h] [rbp+Fh]
  int v41; // [rsp+8Ch] [rbp+13h]
  const wchar_t *v42; // [rsp+90h] [rbp+17h]
  int v43; // [rsp+98h] [rbp+1Fh]
  int v44; // [rsp+9Ch] [rbp+23h]

  v8 = -1;
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
  v28 = v11;
  v29 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v27 = a3;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v31 = v13;
  v14 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v32 = 0;
  v30 = a4;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v34 = v16;
  v35 = 0;
  if ( !a5 )
    v14 = L"NULL";
  v33 = v14;
  v17 = a6;
  if ( a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a6[v18] );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v19 = 10;
  }
  v37 = v19;
  v38 = 0;
  if ( !a6 )
    v17 = L"NULL";
  v36 = v17;
  v20 = a7;
  if ( a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a7[v21] );
    v22 = (unsigned int)(2 * v21 + 2);
  }
  else
  {
    v22 = 10;
  }
  v40 = v22;
  v41 = 0;
  if ( !a7 )
    v20 = L"NULL";
  v39 = v20;
  v23 = a8;
  v24 = a8 == 0;
  if ( a8 )
  {
    do
      ++v8;
    while ( a8[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v24 = a8 == 0;
  }
  if ( v24 )
    v23 = L"NULL";
  v43 = v9;
  v42 = v23;
  v44 = 0;
  return McGenEventWrite_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)ProcessTerminationCrossProcess, v22, 7u, &v26);
}

```

## disassembly

```asm
0x180013948  push    rbp
0x18001394a  lea     rbp, [rsp-37h]
0x18001394f  sub     rsp, 0B0h
0x180013956  mov     rax, cs:__security_cookie
0x18001395d  xor     rax, rsp
0x180013960  mov     [rbp+37h+var_10], rax
0x180013964  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013968  xor     r10d, r10d
0x18001396b  mov     ecx, 0Ah
0x180013970  test    r8, r8
0x180013973  jz      short loc_18001398B
0x180013975  mov     rdx, rax
0x180013978  inc     rdx
0x18001397b  cmp     [r8+rdx*2], r10w
0x180013980  jnz     short loc_180013978
0x180013982  lea     edx, ds:2[rdx*2]
0x180013989  jmp     short loc_18001398D
0x18001398b  mov     edx, ecx
0x18001398d  test    r8, r8
0x180013990  mov     [rbp+37h+var_68], edx
0x180013993  lea     r11, aNull; "NULL"
0x18001399a  mov     [rbp+37h+var_64], r10d
0x18001399e  cmovz   r8, r11
0x1800139a2  mov     [rbp+37h+var_70], r8
0x1800139a6  test    r9, r9
0x1800139a9  jz      short loc_1800139C1
0x1800139ab  mov     rdx, rax
0x1800139ae  inc     rdx
0x1800139b1  cmp     [r9+rdx*2], r10w
0x1800139b6  jnz     short loc_1800139AE
0x1800139b8  lea     edx, ds:2[rdx*2]
0x1800139bf  jmp     short loc_1800139C3
0x1800139c1  mov     edx, ecx
0x1800139c3  test    r9, r9
0x1800139c6  mov     [rbp+37h+var_58], edx
0x1800139c9  mov     rdx, [rbp+37h+arg_20]
0x1800139cd  cmovz   r9, r11
0x1800139d1  mov     [rbp+37h+var_54], r10d
0x1800139d5  mov     [rbp+37h+var_60], r9
0x1800139d9  test    rdx, rdx
0x1800139dc  jz      short loc_1800139F5
0x1800139de  mov     r8, rax
0x1800139e1  inc     r8
0x1800139e4  cmp     [rdx+r8*2], r10w
0x1800139e9  jnz     short loc_1800139E1
0x1800139eb  lea     r8d, ds:2[r8*2]
0x1800139f3  jmp     short loc_1800139F8
0x1800139f5  mov     r8d, ecx
0x1800139f8  test    rdx, rdx
0x1800139fb  mov     [rbp+37h+var_48], r8d
0x1800139ff  mov     [rbp+37h+var_44], r10d
0x180013a03  cmovz   rdx, r11
0x180013a07  mov     [rbp+37h+var_50], rdx
0x180013a0b  mov     rdx, [rbp+37h+arg_28]
0x180013a0f  test    rdx, rdx
0x180013a12  jz      short loc_180013A2B
0x180013a14  mov     r8, rax
0x180013a17  inc     r8
0x180013a1a  cmp     [rdx+r8*2], r10w
0x180013a1f  jnz     short loc_180013A17
0x180013a21  lea     r8d, ds:2[r8*2]
0x180013a29  jmp     short loc_180013A2E
0x180013a2b  mov     r8d, ecx
0x180013a2e  test    rdx, rdx
0x180013a31  mov     [rbp+37h+var_38], r8d
0x180013a35  mov     [rbp+37h+var_34], r10d
0x180013a39  cmovz   rdx, r11
0x180013a3d  mov     [rbp+37h+var_40], rdx
0x180013a41  mov     rdx, [rbp+37h+arg_30]
0x180013a45  test    rdx, rdx
0x180013a48  jz      short loc_180013A61
0x180013a4a  mov     r8, rax
0x180013a4d  inc     r8
0x180013a50  cmp     [rdx+r8*2], r10w
0x180013a55  jnz     short loc_180013A4D
0x180013a57  lea     r8d, ds:2[r8*2]
0x180013a5f  jmp     short loc_180013A64
0x180013a61  mov     r8d, ecx
0x180013a64  test    rdx, rdx
0x180013a67  mov     [rbp+37h+var_28], r8d
0x180013a6b  mov     [rbp+37h+var_24], r10d
0x180013a6f  cmovz   rdx, r11
0x180013a73  mov     [rbp+37h+var_30], rdx
0x180013a77  mov     rdx, [rbp+37h+arg_38]
0x180013a7b  test    rdx, rdx
0x180013a7e  jz      short loc_180013A94
0x180013a80  inc     rax
0x180013a83  cmp     [rdx+rax*2], r10w
0x180013a88  jnz     short loc_180013A80
0x180013a8a  lea     ecx, ds:2[rax*2]
0x180013a91  test    rdx, rdx
0x180013a94  cmovz   rdx, r11
0x180013a98  mov     [rbp+37h+var_18], ecx
0x180013a9b  mov     [rbp+37h+var_20], rdx
0x180013a9f  lea     rax, [rbp+37h+var_80]
0x180013aa3  lea     rdx, ProcessTerminationCrossProcess
0x180013aaa  mov     [rbp+37h+var_14], r10d
0x180013aae  mov     r9d, 7
0x180013ab4  mov     [rsp+0B0h+var_90], rax
0x180013ab9  call    McGenEventWrite_EventWriteTransfer
0x180013abe  mov     rcx, [rbp+37h+var_10]
0x180013ac2  xor     rcx, rsp; StackCookie
0x180013ac5  call    __security_check_cookie
0x180013aca  add     rsp, 0B0h
0x180013ad1  pop     rbp
0x180013ad2  retn
```
