# ParseCacheControlHeader(_SSDP_REQUEST *)

- ea: `0x180018a40`
- end: `0x180018cb4`
- name: `?ParseCacheControlHeader@@YAHPEAU_SSDP_REQUEST@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004744`

## callees

- `0x180018a40`
- `0x180028000`
- `0x180035298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180018b5a`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180018b6b`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180018b5a`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180018b6b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180018a7b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180018a7b`

## pseudocode

```c
__int64 __fastcall ParseCacheControlHeader(struct _SSDP_REQUEST *a1)
{
  const char *v2; // rcx
  char *v4; // rax
  char v5; // dl
  _BYTE *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  _BYTE *v9; // r8
  unsigned __int8 *v10; // rbx
  unsigned __int8 v11; // dl
  unsigned __int8 *v13; // rax
  unsigned __int8 v14; // al
  unsigned __int8 *v15; // rsi
  __int64 v16; // rcx
  LPCSTR v17; // rcx
  __int64 v18; // rdx

  v2 = *(const char **)(*((_QWORD *)a1 + 10) + 72LL);
  if ( !v2 )
    return 1;
  v4 = strstr(v2, "max-age");
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
    return 1;
  }
  v5 = v4[7];
  v6 = v4 + 7;
  if ( !v5 )
    goto LABEL_38;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  v9 = &v6[v8 - 1];
  while ( v5 == 32 || v5 == 9 )
    v5 = *++v6;
  for ( ; v9 > v6; --v9 )
  {
    if ( *v9 != 32 && *v9 != 9 )
      break;
  }
  v9[1] = 0;
  if ( *v6 != 61 )
  {
LABEL_38:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      return 0;
    v18 = 48;
    goto LABEL_41;
  }
  v10 = v6 + 1;
  qmemcpy(*(void **)(*((_QWORD *)a1 + 10) + 72LL), "max-age=", 8);
  v11 = *v10;
  if ( *v10 )
  {
    while ( v10[++v7] != 0 )
      ;
    v13 = &v10[v7 - 1];
    while ( v11 == 32 || v11 == 9 )
      v11 = *++v10;
    for ( ; v13 > v10; --v13 )
    {
      if ( *v13 != 32 && *v13 != 9 )
        break;
    }
    v13[1] = 0;
    v14 = *v10;
  }
  else
  {
    v14 = 0;
  }
  v15 = v10;
  if ( (unsigned int)_o_isdigit(v14) )
  {
    do
      v16 = *++v10;
    while ( (unsigned int)_o_isdigit(v16) );
    if ( v10 != v15 )
    {
      memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 72LL) + 8LL), v15, v10 - v15);
      v10[*(_QWORD *)(*((_QWORD *)a1 + 10) + 72LL) - (_QWORD)v15 + 8] = 0;
      return 1;
    }
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    v18 = 49;
LABEL_41:
    WPP_SF_(*((_QWORD *)v17 + 2), v18, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180018a40  mov     [rsp+arg_0], rbx
0x180018a45  mov     [rsp+arg_8], rsi
0x180018a4a  push    rdi
0x180018a4b  sub     rsp, 20h
0x180018a4f  mov     rax, [rcx+50h]
0x180018a53  mov     rdi, rcx
0x180018a56  mov     rcx, [rax+48h]; Str
0x180018a5a  test    rcx, rcx
0x180018a5d  jnz     short loc_180018A74
0x180018a5f  mov     eax, 1
0x180018a64  mov     rbx, [rsp+28h+arg_0]
0x180018a69  mov     rsi, [rsp+28h+arg_8]
0x180018a6e  add     rsp, 20h
0x180018a72  pop     rdi
0x180018a73  retn
0x180018a74  lea     rdx, aMaxAge; "max-age"
0x180018a7b  call    cs:__imp_strstr
0x180018a81  test    rax, rax
0x180018a84  jz      loc_180018C26
0x180018a8a  movzx   edx, byte ptr [rax+7]
0x180018a8e  lea     rbx, [rax+7]
0x180018a92  test    dl, dl
0x180018a94  jz      loc_180018C61
0x180018a9a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018aa1  mov     rax, rcx
0x180018aa4  inc     rax
0x180018aa7  cmp     byte ptr [rbx+rax], 0
0x180018aab  jnz     short loc_180018AA4
0x180018aad  lea     r8, [rbx-1]
0x180018ab1  add     r8, rax
0x180018ab4  cmp     dl, 20h ; ' '
0x180018ab7  jz      loc_180018C0E
0x180018abd  cmp     dl, 9
0x180018ac0  jz      loc_180018C0E
0x180018ac6  cmp     r8, rbx
0x180018ac9  ja      loc_180018BD2
0x180018acf  mov     byte ptr [r8+1], 0
0x180018ad4  cmp     byte ptr [rbx], 3Dh ; '='
0x180018ad7  jnz     loc_180018C61
0x180018add  mov     rax, [rdi+50h]
0x180018ae1  inc     rbx
0x180018ae4  mov     rdx, [rax+48h]
0x180018ae8  mov     rax, qword ptr cs:aMaxAge; "max-age"
0x180018aef  mov     [rdx], eax
0x180018af1  movzx   eax, word ptr cs:aMaxAge+4; "age"
0x180018af8  mov     [rdx+4], ax
0x180018afc  movzx   eax, byte ptr cs:aMaxAge+6; "e"
0x180018b03  mov     [rdx+6], al
0x180018b06  mov     rax, [rdi+50h]
0x180018b0a  mov     rdx, [rax+48h]
0x180018b0e  mov     byte ptr [rdx+7], 3Dh ; '='
0x180018b12  movzx   edx, byte ptr [rbx]
0x180018b15  test    dl, dl
0x180018b17  jz      loc_180018C9C
0x180018b1d  nop     dword ptr [rax]
0x180018b20  cmp     byte ptr [rbx+rcx+1], 0
0x180018b25  lea     rcx, [rcx+1]
0x180018b29  jnz     short loc_180018B20
0x180018b2b  lea     rax, [rcx-1]
0x180018b2f  add     rax, rbx
0x180018b32  cmp     dl, 20h ; ' '
0x180018b35  jz      loc_180018C1A
0x180018b3b  cmp     dl, 9
0x180018b3e  jz      loc_180018C1A
0x180018b44  cmp     rax, rbx
0x180018b47  ja      loc_180018BF0
0x180018b4d  mov     byte ptr [rax+1], 0
0x180018b51  movzx   eax, byte ptr [rbx]
0x180018b54  movzx   ecx, al
0x180018b57  mov     rsi, rbx
0x180018b5a  call    cs:__imp__o_isdigit
0x180018b60  test    eax, eax
0x180018b62  jz      short loc_180018BA9
0x180018b64  movzx   ecx, byte ptr [rbx+1]
0x180018b68  inc     rbx
0x180018b6b  call    cs:__imp__o_isdigit
0x180018b71  test    eax, eax
0x180018b73  jnz     short loc_180018B64
0x180018b75  cmp     rbx, rsi
0x180018b78  jz      short loc_180018BA9
0x180018b7a  mov     rax, [rdi+50h]
0x180018b7e  mov     r8, rbx
0x180018b81  sub     r8, rsi; Size
0x180018b84  mov     rdx, rsi; Src
0x180018b87  mov     rcx, [rax+48h]
0x180018b8b  add     rcx, 8; void *
0x180018b8f  call    memcpy_0
0x180018b94  mov     rax, [rdi+50h]
0x180018b98  mov     rcx, [rax+48h]
0x180018b9c  sub     rcx, rsi
0x180018b9f  mov     byte ptr [rcx+rbx+8], 0
0x180018ba4  jmp     loc_180018A5F
0x180018ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bb0  lea     rax, WPP_GLOBAL_Control
0x180018bb7  cmp     rcx, rax
0x180018bba  jnz     loc_180018CA3
0x180018bc0  mov     rbx, [rsp+28h+arg_0]
0x180018bc5  xor     eax, eax
0x180018bc7  mov     rsi, [rsp+28h+arg_8]
0x180018bcc  add     rsp, 20h
0x180018bd0  pop     rdi
0x180018bd1  retn
0x180018bd2  movzx   eax, byte ptr [r8]
0x180018bd6  cmp     al, 20h ; ' '
0x180018bd8  jz      short loc_180018BE2
0x180018bda  cmp     al, 9
0x180018bdc  jnz     loc_180018ACF
0x180018be2  dec     r8
0x180018be5  cmp     r8, rbx
0x180018be8  ja      short loc_180018BD2
0x180018bea  jmp     loc_180018ACF
0x180018bf0  movzx   ecx, byte ptr [rax]
0x180018bf3  cmp     cl, 20h ; ' '
0x180018bf6  jz      short loc_180018C01
0x180018bf8  cmp     cl, 9
0x180018bfb  jnz     loc_180018B4D
0x180018c01  dec     rax
0x180018c04  cmp     rax, rbx
0x180018c07  ja      short loc_180018BF0
0x180018c09  jmp     loc_180018B4D
0x180018c0e  movzx   edx, byte ptr [rbx+1]
0x180018c12  inc     rbx
0x180018c15  jmp     loc_180018AB4
0x180018c1a  movzx   edx, byte ptr [rbx+1]
0x180018c1e  inc     rbx
0x180018c21  jmp     loc_180018B32
0x180018c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c2d  lea     rax, WPP_GLOBAL_Control
0x180018c34  cmp     rcx, rax
0x180018c37  jz      loc_180018A5F
0x180018c3d  test    byte ptr [rcx+1Ch], 1
0x180018c41  jz      loc_180018A5F
0x180018c47  mov     rcx, [rcx+10h]
0x180018c4b  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180018c52  mov     edx, 32h ; '2'
0x180018c57  call    WPP_SF_
0x180018c5c  jmp     loc_180018A5F
0x180018c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c68  lea     rax, WPP_GLOBAL_Control
0x180018c6f  cmp     rcx, rax
0x180018c72  jz      loc_180018BC0
0x180018c78  test    byte ptr [rcx+1Ch], 1
0x180018c7c  jz      loc_180018BC0
0x180018c82  mov     edx, 30h ; '0'
0x180018c87  mov     rcx, [rcx+10h]
0x180018c8b  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180018c92  call    WPP_SF_
0x180018c97  jmp     loc_180018BC0
0x180018c9c  xor     al, al
0x180018c9e  jmp     loc_180018B54
0x180018ca3  test    byte ptr [rcx+1Ch], 1
0x180018ca7  jz      loc_180018BC0
0x180018cad  mov     edx, 31h ; '1'
0x180018cb2  jmp     short loc_180018C87
```
