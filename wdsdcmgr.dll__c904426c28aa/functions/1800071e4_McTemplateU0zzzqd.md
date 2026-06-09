# McTemplateU0zzzqd

- ea: `0x1800071e4`
- end: `0x180007308`
- name: `McTemplateU0zzzqd`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004dbc`
- `0x180004f98`

## callees

- `0x180007188`
- `0x1800071e4`
- `0x180015660`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzqd(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6,
        char a7)
{
  __int64 v7; // rcx
  int v9; // edx
  __int64 v10; // rax
  int v11; // r10d
  const wchar_t *v12; // r11
  const wchar_t *v13; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  const wchar_t *v16; // rax
  bool v17; // zf
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v20; // [rsp+40h] [rbp-21h]
  int v21; // [rsp+48h] [rbp-19h]
  int v22; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v23; // [rsp+50h] [rbp-11h]
  int v24; // [rsp+58h] [rbp-9h]
  int v25; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v26; // [rsp+60h] [rbp-1h]
  int v27; // [rsp+68h] [rbp+7h]
  int v28; // [rsp+6Ch] [rbp+Bh]
  char *v29; // [rsp+70h] [rbp+Fh]
  __int64 v30; // [rsp+78h] [rbp+17h]
  char *v31; // [rsp+80h] [rbp+1Fh]
  __int64 v32; // [rsp+88h] [rbp+27h]

  v7 = -1;
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
  v21 = v11;
  v12 = L"NULL";
  v22 = 0;
  v13 = L"NULL";
  if ( a3 )
    v13 = a3;
  v20 = v13;
  if ( a4 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a4[v14] );
    v15 = (unsigned int)(2 * v14 + 2);
  }
  else
  {
    v15 = 10;
  }
  v24 = v15;
  v16 = L"NULL";
  v25 = 0;
  if ( a4 )
    v16 = a4;
  v23 = v16;
  v17 = a5 == 0;
  if ( a5 )
  {
    do
      ++v7;
    while ( a5[v7] );
    v9 = 2 * v7 + 2;
    v17 = a5 == 0;
  }
  if ( !v17 )
    v12 = a5;
  v27 = v9;
  v26 = v12;
  v29 = &a6;
  v28 = 0;
  v31 = &a7;
  v30 = 4;
  v32 = 4;
  return McGenEventWrite(v7, a2, v15, 6u, &v19);
}

```

## disassembly

```asm
0x1800071e4  mov     [rsp-8+arg_0], rbx
0x1800071e9  mov     [rsp-8+arg_10], rdi
0x1800071ee  push    rbp
0x1800071ef  lea     rbp, [rsp-3Fh]
0x1800071f4  sub     rsp, 0A0h
0x1800071fb  mov     rax, cs:__security_cookie
0x180007202  xor     rax, rsp
0x180007205  mov     [rbp+3Fh+var_10], rax
0x180007209  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000720d  xor     edi, edi
0x18000720f  mov     rbx, rdx
0x180007212  mov     edx, 0Ah
0x180007217  test    r8, r8
0x18000721a  jz      short loc_180007233
0x18000721c  mov     rax, rcx
0x18000721f  inc     rax
0x180007222  cmp     [r8+rax*2], di
0x180007227  jnz     short loc_18000721F
0x180007229  lea     r10d, ds:2[rax*2]
0x180007231  jmp     short loc_180007236
0x180007233  mov     r10d, edx
0x180007236  test    r8, r8
0x180007239  mov     [rbp+3Fh+var_58], r10d
0x18000723d  lea     r11, aNull; "NULL"
0x180007244  mov     [rbp+3Fh+var_54], edi
0x180007247  mov     rax, r11
0x18000724a  cmovnz  rax, r8
0x18000724e  mov     [rbp+3Fh+var_60], rax
0x180007252  test    r9, r9
0x180007255  jz      short loc_18000726E
0x180007257  mov     rax, rcx
0x18000725a  inc     rax
0x18000725d  cmp     [r9+rax*2], di
0x180007262  jnz     short loc_18000725A
0x180007264  lea     r8d, ds:2[rax*2]
0x18000726c  jmp     short loc_180007271
0x18000726e  mov     r8d, edx
0x180007271  test    r9, r9
0x180007274  mov     [rbp+3Fh+var_48], r8d
0x180007278  mov     rax, r11
0x18000727b  mov     [rbp+3Fh+var_44], edi
0x18000727e  cmovnz  rax, r9
0x180007282  mov     [rbp+3Fh+var_50], rax
0x180007286  mov     rax, [rbp+3Fh+arg_20]
0x18000728a  test    rax, rax
0x18000728d  jz      short loc_1800072A2
0x18000728f  inc     rcx
0x180007292  cmp     [rax+rcx*2], di
0x180007296  jnz     short loc_18000728F
0x180007298  lea     edx, ds:2[rcx*2]
0x18000729f  test    rax, rax
0x1800072a2  cmovnz  r11, rax
0x1800072a6  mov     [rbp+3Fh+var_38], edx
0x1800072a9  lea     rax, [rbp+3Fh+arg_28]
0x1800072ad  mov     [rbp+3Fh+var_40], r11
0x1800072b1  mov     [rbp+3Fh+var_30], rax
0x1800072b5  mov     r9d, 6
0x1800072bb  lea     rax, [rbp+3Fh+arg_30]
0x1800072bf  mov     [rbp+3Fh+var_34], edi
0x1800072c2  mov     [rbp+3Fh+var_20], rax
0x1800072c6  mov     rdx, rbx
0x1800072c9  lea     rax, [rbp+3Fh+var_70]
0x1800072cd  mov     [rbp+3Fh+var_28], 4
0x1800072d5  mov     [rsp+0A0h+var_80], rax
0x1800072da  mov     [rbp+3Fh+var_18], 4
0x1800072e2  call    McGenEventWrite
0x1800072e7  mov     rcx, [rbp+3Fh+var_10]
0x1800072eb  xor     rcx, rsp; StackCookie
0x1800072ee  call    __security_check_cookie
0x1800072f3  lea     r11, [rsp+0A0h+var_s0]
0x1800072fb  mov     rbx, [r11+10h]
0x1800072ff  mov     rdi, [r11+20h]
0x180007303  mov     rsp, r11
0x180007306  pop     rbp
0x180007307  retn
```
