# WPDLibConvertStringGUIDToGUID

- ea: `0x180007f68`
- end: `0x1800080da`
- name: `WPDLibConvertStringGUIDToGUID`
- size: `370`
- prototype: `__int64 __fastcall(_WORD *, _OWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001210`
- `0x180004f10`
- `0x180005420`

## callees

- `0x180007f68`
- `0x1800097d0`
- `0x180014224`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007fc8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180008000`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180008039`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007fc8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180008000`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180008039`

## pseudocode

```c
__int64 __fastcall WPDLibConvertStringGUIDToGUID(_WORD *a1, _OWORD *a2)
{
  bool v3; // zf
  _WORD *v4; // rbx
  const wchar_t *v5; // rcx
  _WORD *v6; // rbx
  const wchar_t *v7; // rcx
  _WORD *v8; // rbx
  const wchar_t *v9; // rcx
  _WORD *v10; // rbx
  unsigned int v11; // r8d
  __int16 v12; // cx
  _WORD *v13; // rdx
  char v14; // al
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r9
  char BinaryForAscii; // al
  unsigned int v20; // r8d
  __int64 v21; // rcx
  char v22; // r9
  __int16 v23; // ax
  __int64 result; // rax
  __int128 v25; // [rsp+20h] [rbp-28h]

  v3 = *a1 == 123;
  *((_QWORD *)&v25 + 1) = 0;
  if ( !v3 )
    return 0;
  v4 = a1 + 1;
  v5 = a1 + 1;
  while ( *v4 && *v4 != 45 )
    ++v4;
  if ( *v4 != 45 )
    return 0;
  *v4 = 0;
  v6 = v4 + 1;
  LODWORD(v25) = wcstoul(v5, 0, 16);
  v7 = v6;
  while ( *v6 && *v6 != 45 )
    ++v6;
  if ( *v6 != 45 )
    return 0;
  *v6 = 0;
  v8 = v6 + 1;
  WORD2(v25) = wcstoul(v7, 0, 16);
  v9 = v8;
  while ( *v8 && *v8 != 45 )
    ++v8;
  if ( *v8 != 45 )
    return 0;
  *v8 = 0;
  WORD3(v25) = wcstoul(v9, 0, 16);
  v10 = v8 + 1;
  v11 = 0;
  while ( 1 )
  {
    v23 = *v10;
    if ( !*v10 || v11 >= 8 )
      break;
    v12 = v23 == 45 ? v10[1] : *v10;
    v13 = v10 + 1;
    if ( v23 != 45 )
      v13 = v10;
    if ( v12 == 125 )
      break;
    if ( !*v13 )
      break;
    v14 = ((__int64 (*)(void))GetBinaryForAscii)();
    v17 = *(unsigned __int16 *)(v15 + 2);
    LOBYTE(v18) = v14;
    if ( !(_WORD)v17 )
      break;
    v10 = (_WORD *)(v15 + 4);
    BinaryForAscii = GetBinaryForAscii(v17, v15, v16, v18);
    v21 = v20;
    v11 = v20 + 1;
    *((_BYTE *)&v25 + v21 + 8) = (16 * v22) | BinaryForAscii;
  }
  result = 1;
  *a2 = v25;
  return result;
}

```

## disassembly

```asm
0x180007f68  mov     [rsp+arg_10], rbx
0x180007f6d  mov     [rsp+arg_18], rsi
0x180007f72  push    rdi
0x180007f73  sub     rsp, 40h
0x180007f77  mov     rax, cs:__security_cookie
0x180007f7e  xor     rax, rsp
0x180007f81  mov     [rsp+48h+var_18], rax
0x180007f86  xor     esi, esi
0x180007f88  mov     rdi, rdx
0x180007f8b  cmp     word ptr [rcx], 7Bh ; '{'
0x180007f8f  mov     qword ptr [rsp+48h+var_28+8], rsi
0x180007f94  jnz     loc_1800080BB
0x180007f9a  lea     rbx, [rcx+2]
0x180007f9e  mov     rcx, rbx; String
0x180007fa1  jmp     short loc_180007FAD
0x180007fa3  cmp     ax, 2Dh ; '-'
0x180007fa7  jz      short loc_180007FB5
0x180007fa9  add     rbx, 2
0x180007fad  movzx   eax, word ptr [rbx]
0x180007fb0  test    ax, ax
0x180007fb3  jnz     short loc_180007FA3
0x180007fb5  cmp     word ptr [rbx], 2Dh ; '-'
0x180007fb9  jnz     loc_1800080BB
0x180007fbf  xor     edx, edx; EndPtr
0x180007fc1  mov     [rbx], si
0x180007fc4  lea     r8d, [rdx+10h]; Radix
0x180007fc8  call    cs:__imp_wcstoul
0x180007fce  add     rbx, 2
0x180007fd2  mov     dword ptr [rsp+48h+var_28], eax
0x180007fd6  mov     rcx, rbx; String
0x180007fd9  jmp     short loc_180007FE5
0x180007fdb  cmp     ax, 2Dh ; '-'
0x180007fdf  jz      short loc_180007FED
0x180007fe1  add     rbx, 2
0x180007fe5  movzx   eax, word ptr [rbx]
0x180007fe8  test    ax, ax
0x180007feb  jnz     short loc_180007FDB
0x180007fed  cmp     word ptr [rbx], 2Dh ; '-'
0x180007ff1  jnz     loc_1800080BB
0x180007ff7  xor     edx, edx; EndPtr
0x180007ff9  mov     [rbx], si
0x180007ffc  lea     r8d, [rdx+10h]; Radix
0x180008000  call    cs:__imp_wcstoul
0x180008006  add     rbx, 2
0x18000800a  mov     word ptr [rsp+48h+var_28+4], ax
0x18000800f  mov     rcx, rbx; String
0x180008012  jmp     short loc_18000801E
0x180008014  cmp     ax, 2Dh ; '-'
0x180008018  jz      short loc_180008026
0x18000801a  add     rbx, 2
0x18000801e  movzx   eax, word ptr [rbx]
0x180008021  test    ax, ax
0x180008024  jnz     short loc_180008014
0x180008026  cmp     word ptr [rbx], 2Dh ; '-'
0x18000802a  jnz     loc_1800080BB
0x180008030  xor     edx, edx; EndPtr
0x180008032  mov     [rbx], si
0x180008035  lea     r8d, [rdx+10h]; Radix
0x180008039  call    cs:__imp_wcstoul
0x18000803f  mov     word ptr [rsp+48h+var_28+6], ax
0x180008044  add     rbx, 2
0x180008048  mov     r8d, esi
0x18000804b  jmp     short loc_1800080A3
0x18000804d  cmp     r8d, 8
0x180008051  jnb     short loc_1800080AB
0x180008053  cmp     ax, 2Dh ; '-'
0x180008057  jnz     short loc_18000805F
0x180008059  movzx   ecx, word ptr [rbx+2]
0x18000805d  jmp     short loc_180008062
0x18000805f  movzx   ecx, ax
0x180008062  lea     rdx, [rbx+2]
0x180008066  cmovnz  rdx, rbx
0x18000806a  cmp     cx, 7Dh ; '}'
0x18000806e  jz      short loc_1800080AB
0x180008070  movzx   ecx, word ptr [rdx]
0x180008073  test    cx, cx
0x180008076  jz      short loc_1800080AB
0x180008078  call    GetBinaryForAscii
0x18000807d  movzx   ecx, word ptr [rdx+2]
0x180008081  mov     r9b, al
0x180008084  test    cx, cx
0x180008087  jz      short loc_1800080AB
0x180008089  lea     rbx, [rdx+4]
0x18000808d  call    GetBinaryForAscii
0x180008092  mov     ecx, r8d
0x180008095  shl     r9b, 4
0x180008099  or      al, r9b
0x18000809c  inc     r8d
0x18000809f  mov     byte ptr [rsp+rcx+48h+var_28+8], al
0x1800080a3  movzx   eax, word ptr [rbx]
0x1800080a6  test    ax, ax
0x1800080a9  jnz     short loc_18000804D
0x1800080ab  movups  xmm0, [rsp+48h+var_28]
0x1800080b0  mov     eax, 1
0x1800080b5  movdqu  xmmword ptr [rdi], xmm0
0x1800080b9  jmp     short loc_1800080BD
0x1800080bb  xor     eax, eax
0x1800080bd  mov     rcx, [rsp+48h+var_18]
0x1800080c2  xor     rcx, rsp; StackCookie
0x1800080c5  call    __security_check_cookie
0x1800080ca  mov     rbx, [rsp+48h+arg_10]
0x1800080cf  mov     rsi, [rsp+48h+arg_18]
0x1800080d4  add     rsp, 40h
0x1800080d8  pop     rdi
0x1800080d9  retn
```
