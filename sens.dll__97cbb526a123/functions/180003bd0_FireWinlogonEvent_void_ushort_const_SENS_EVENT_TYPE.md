# FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)

- ea: `0x180003bd0`
- end: `0x180003df7`
- name: `?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003690`

## callees

- `0x180003bd0`
- `0x180003e00`
- `0x18000a27c`
- `0x18000a7a0`

## pseudocode

```c
__int64 __fastcall FireWinlogonEvent(__int64 a1, int a2, int a3)
{
  char *v4; // rdx
  char *v6; // r8
  char *v7; // r10
  _WORD *v9; // rax
  __int64 v10; // r11
  __int64 v11; // r8
  __int64 v12; // rcx
  _WORD *v13; // rdx
  __int64 v14; // r10
  _WORD *v15; // rcx
  __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // rcx
  _WORD *v19; // r9
  const wchar_t *v20; // r10
  _WORD *v21; // rcx
  _WORD *v22; // rcx
  _WORD *i; // rax
  _WORD *v24; // r9
  _WORD *v25; // rcx
  __int64 v27; // [rsp+58h] [rbp-430h]
  _QWORD v28[128]; // [rsp+60h] [rbp-428h] BYREF
  _BYTE v29[14]; // [rsp+462h] [rbp-26h] BYREF

  LOWORD(v28[0]) = 0;
  v4 = byte_18000D350;
  v6 = byte_18000D350;
  v7 = byte_18000D350;
  if ( *(_QWORD *)(a1 + 16) )
    v6 = *(char **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 24) )
    v7 = *(char **)(a1 + 24);
  if ( *(_QWORD *)(a1 + 32) )
    v4 = *(char **)(a1 + 32);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    LODWORD(v27) = *(_DWORD *)(a1 + 48);
    WPP_SF_SdDSSSDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v4,
      (_DWORD)v6,
      a2,
      *(_DWORD *)(a1 + 8),
      *(_DWORD *)(a1 + 12),
      (__int64)v6,
      (__int64)v7,
      (__int64)v4,
      *(_DWORD *)(a1 + 40),
      *(_DWORD *)(a1 + 44),
      v27,
      v28[0]);
  }
  v9 = *(_WORD **)(a1 + 24);
  v10 = 2147483646;
  v11 = 513;
  if ( v9 )
  {
    v12 = 2147483646;
    v13 = v28;
    v14 = 513;
    do
    {
      if ( !v12 )
        break;
      if ( !*v9 )
        break;
      *v13++ = *v9++;
      --v12;
      --v14;
    }
    while ( v14 );
    v15 = v13 - 1;
    if ( v14 )
      v15 = v13;
    v16 = 513;
    *v15 = 0;
    v17 = v28;
    while ( *v17 )
    {
      ++v17;
      if ( !--v16 )
        goto LABEL_26;
    }
    v18 = 2147483646;
    v19 = &v29[-2 * v16];
    v20 = L"\\";
    do
    {
      if ( !v18 )
        break;
      if ( !*v20 )
        break;
      *v19++ = *v20++;
      --v18;
      --v16;
    }
    while ( v16 );
    v21 = v19 - 1;
    if ( v16 )
      v21 = v19;
    *v21 = 0;
  }
LABEL_26:
  v22 = *(_WORD **)(a1 + 16);
  if ( v22 )
  {
    for ( i = v28; *i; ++i )
    {
      if ( !--v11 )
        return SensFireWinlogonEventHelper((const OLECHAR *)v28, *(_DWORD *)(a1 + 48), a3);
    }
    v24 = &v29[-2 * v11];
    do
    {
      if ( !v10 )
        break;
      if ( !*v22 )
        break;
      *v24++ = *v22++;
      --v10;
      --v11;
    }
    while ( v11 );
    v25 = v24 - 1;
    if ( v11 )
      v25 = v24;
    *v25 = 0;
  }
  return SensFireWinlogonEventHelper((const OLECHAR *)v28, *(_DWORD *)(a1 + 48), a3);
}

```

## disassembly

```asm
0x180003bd0  mov     [rsp+arg_18], rbx
0x180003bd5  push    rdi
0x180003bd6  sub     rsp, 480h
0x180003bdd  mov     rax, cs:__security_cookie
0x180003be4  xor     rax, rsp
0x180003be7  mov     [rsp+488h+var_18], rax
0x180003bef  xor     eax, eax
0x180003bf1  mov     r9, rdx
0x180003bf4  mov     [rsp+488h+var_428], ax
0x180003bf9  lea     rdx, byte_18000D350
0x180003c00  mov     rax, [rcx+10h]
0x180003c04  mov     edi, r8d
0x180003c07  test    rax, rax
0x180003c0a  mov     r8, rdx
0x180003c0d  mov     r10, rdx
0x180003c10  mov     rbx, rcx
0x180003c13  cmovnz  r8, rax
0x180003c17  mov     rax, [rcx+18h]
0x180003c1b  test    rax, rax
0x180003c1e  cmovnz  r10, rax
0x180003c22  mov     rax, [rcx+20h]
0x180003c26  test    rax, rax
0x180003c29  cmovnz  rdx, rax
0x180003c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c34  lea     rax, WPP_GLOBAL_Control
0x180003c3b  cmp     rcx, rax
0x180003c3e  jnz     loc_180003DA3
0x180003c44  mov     rax, [rbx+18h]
0x180003c48  mov     r11d, 7FFFFFFEh
0x180003c4e  mov     r8d, 201h
0x180003c54  test    rax, rax
0x180003c57  jz      loc_180003D07
0x180003c5d  mov     ecx, r11d
0x180003c60  lea     rdx, [rsp+488h+var_428]
0x180003c65  mov     r10d, r8d
0x180003c68  test    rcx, rcx
0x180003c6b  jz      short loc_180003C8C
0x180003c6d  movzx   r9d, word ptr [rax]
0x180003c71  test    r9w, r9w
0x180003c75  jz      short loc_180003C8C
0x180003c77  mov     [rdx], r9w
0x180003c7b  add     rax, 2
0x180003c7f  add     rdx, 2
0x180003c83  dec     rcx
0x180003c86  sub     r10, 1
0x180003c8a  jnz     short loc_180003C68
0x180003c8c  test    r10, r10
0x180003c8f  lea     rcx, [rdx-2]
0x180003c93  cmovnz  rcx, rdx
0x180003c97  xor     eax, eax
0x180003c99  mov     rdx, r8
0x180003c9c  mov     [rcx], ax
0x180003c9f  lea     rax, [rsp+488h+var_428]
0x180003ca4  cmp     word ptr [rax], 0
0x180003ca8  jz      short loc_180003CB6
0x180003caa  add     rax, 2
0x180003cae  sub     rdx, 1
0x180003cb2  jnz     short loc_180003CA4
0x180003cb4  jmp     short loc_180003D07
0x180003cb6  lea     rax, [rdx+rdx]
0x180003cba  mov     rcx, r11
0x180003cbd  lea     r9, [rsp+488h+var_26]
0x180003cc5  sub     r9, rax
0x180003cc8  lea     r10, asc_18000D354; "\\"
0x180003ccf  test    rdx, rdx
0x180003cd2  jz      short loc_180003CF7
0x180003cd4  test    rcx, rcx
0x180003cd7  jz      short loc_180003CF7
0x180003cd9  movzx   eax, word ptr [r10]
0x180003cdd  test    ax, ax
0x180003ce0  jz      short loc_180003CF7
0x180003ce2  mov     [r9], ax
0x180003ce6  add     r10, 2
0x180003cea  add     r9, 2
0x180003cee  dec     rcx
0x180003cf1  sub     rdx, 1
0x180003cf5  jnz     short loc_180003CD4
0x180003cf7  test    rdx, rdx
0x180003cfa  lea     rcx, [r9-2]
0x180003cfe  cmovnz  rcx, r9
0x180003d02  xor     eax, eax
0x180003d04  mov     [rcx], ax
0x180003d07  mov     rcx, [rbx+10h]
0x180003d0b  test    rcx, rcx
0x180003d0e  jz      short loc_180003D72
0x180003d10  lea     rax, [rsp+488h+var_428]
0x180003d15  cmp     word ptr [rax], 0
0x180003d19  jz      short loc_180003D27
0x180003d1b  add     rax, 2
0x180003d1f  sub     r8, 1
0x180003d23  jnz     short loc_180003D15
0x180003d25  jmp     short loc_180003D72
0x180003d27  lea     rax, [r8+r8]
0x180003d2b  lea     r9, [rsp+488h+var_26]
0x180003d33  sub     r9, rax
0x180003d36  test    r8, r8
0x180003d39  jz      short loc_180003D62
0x180003d3b  nop     dword ptr [rax+rax+00h]
0x180003d40  test    r11, r11
0x180003d43  jz      short loc_180003D62
0x180003d45  movzx   eax, word ptr [rcx]
0x180003d48  test    ax, ax
0x180003d4b  jz      short loc_180003D62
0x180003d4d  mov     [r9], ax
0x180003d51  add     rcx, 2
0x180003d55  add     r9, 2
0x180003d59  dec     r11
0x180003d5c  sub     r8, 1
0x180003d60  jnz     short loc_180003D40
0x180003d62  test    r8, r8
0x180003d65  lea     rcx, [r9-2]
0x180003d69  cmovnz  rcx, r9
0x180003d6d  xor     eax, eax
0x180003d6f  mov     [rcx], ax
0x180003d72  mov     edx, [rbx+30h]
0x180003d75  lea     rcx, [rsp+488h+var_428]
0x180003d7a  mov     r8d, edi
0x180003d7d  call    ?SensFireWinlogonEventHelper@@YAJPEBGKW4SENS_EVENT_TYPE@@@Z; SensFireWinlogonEventHelper(ushort const *,ulong,SENS_EVENT_TYPE)
0x180003d82  mov     rcx, [rsp+488h+var_18]
0x180003d8a  xor     rcx, rsp; StackCookie
0x180003d8d  call    __security_check_cookie
0x180003d92  mov     rbx, [rsp+488h+arg_18]
0x180003d9a  add     rsp, 480h
0x180003da1  pop     rdi
0x180003da2  retn
0x180003da3  test    byte ptr [rcx+1Ch], 1
0x180003da7  jz      loc_180003C44
0x180003dad  cmp     byte ptr [rcx+19h], 4
0x180003db1  jb      loc_180003C44
0x180003db7  mov     eax, [rbx+30h]
0x180003dba  mov     rcx, [rcx+10h]
0x180003dbe  mov     dword ptr [rsp+488h+var_430], eax
0x180003dc2  mov     eax, [rbx+2Ch]
0x180003dc5  mov     [rsp+488h+var_438], eax
0x180003dc9  mov     eax, [rbx+28h]
0x180003dcc  mov     [rsp+488h+var_440], eax
0x180003dd0  mov     eax, [rbx+0Ch]
0x180003dd3  mov     [rsp+488h+var_448], rdx
0x180003dd8  mov     [rsp+488h+var_450], r10
0x180003ddd  mov     [rsp+488h+var_458], r8
0x180003de2  mov     [rsp+488h+var_460], eax
0x180003de6  mov     eax, [rbx+8]
0x180003de9  mov     [rsp+488h+var_468], eax
0x180003ded  call    WPP_SF_SdDSSSDDD
0x180003df2  jmp     loc_180003C44
```
