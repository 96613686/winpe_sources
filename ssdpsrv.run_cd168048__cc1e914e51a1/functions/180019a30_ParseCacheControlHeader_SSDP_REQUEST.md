# ParseCacheControlHeader(_SSDP_REQUEST *)

- ea: `0x180019a30`
- end: `0x180019cc4`
- name: `?ParseCacheControlHeader@@YAHPEAU_SSDP_REQUEST@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000307c`

## callees

- `0x180019a30`
- `0x180029df0`
- `0x180037dd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180019b5a`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180019b71`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180019b5a`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180019b71`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180019a6c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180019a6c`

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
0x180019a30  mov     [rsp+arg_0], rbx
0x180019a35  mov     [rsp+arg_8], rsi
0x180019a3a  push    rdi
0x180019a3b  sub     rsp, 20h
0x180019a3f  mov     rax, [rcx+50h]
0x180019a43  mov     rdi, rcx
0x180019a46  mov     rcx, [rax+48h]; Str
0x180019a4a  test    rcx, rcx
0x180019a4d  jnz     short loc_180019A65
0x180019a4f  mov     eax, 1
0x180019a54  mov     rbx, [rsp+28h+arg_0]
0x180019a59  mov     rsi, [rsp+28h+arg_8]
0x180019a5e  add     rsp, 20h
0x180019a62  pop     rdi
0x180019a63  retn
0x180019a65  lea     rdx, aMaxAge; "max-age"
0x180019a6c  call    cs:__imp_strstr
0x180019a73  nop     dword ptr [rax+rax+00h]
0x180019a78  test    rax, rax
0x180019a7b  jz      loc_180019C36
0x180019a81  movzx   edx, byte ptr [rax+7]
0x180019a85  lea     rbx, [rax+7]
0x180019a89  test    dl, dl
0x180019a8b  jz      loc_180019C71
0x180019a91  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019a98  mov     rax, rcx
0x180019a9b  nop     dword ptr [rax+rax+00h]
0x180019aa0  inc     rax
0x180019aa3  cmp     byte ptr [rbx+rax], 0
0x180019aa7  jnz     short loc_180019AA0
0x180019aa9  lea     r8, [rbx-1]
0x180019aad  add     r8, rax
0x180019ab0  cmp     dl, 20h ; ' '
0x180019ab3  jz      loc_180019C1E
0x180019ab9  cmp     dl, 9
0x180019abc  jz      loc_180019C1E
0x180019ac2  cmp     r8, rbx
0x180019ac5  ja      loc_180019BE0
0x180019acb  mov     byte ptr [r8+1], 0
0x180019ad0  cmp     byte ptr [rbx], 3Dh ; '='
0x180019ad3  jnz     loc_180019C71
0x180019ad9  mov     rax, [rdi+50h]
0x180019add  inc     rbx
0x180019ae0  mov     rdx, [rax+48h]
0x180019ae4  mov     rax, qword ptr cs:aMaxAge; "max-age"
0x180019aeb  mov     [rdx], eax
0x180019aed  movzx   eax, word ptr cs:aMaxAge+4; "age"
0x180019af4  mov     [rdx+4], ax
0x180019af8  movzx   eax, byte ptr cs:aMaxAge+6; "e"
0x180019aff  mov     [rdx+6], al
0x180019b02  mov     rax, [rdi+50h]
0x180019b06  mov     rdx, [rax+48h]
0x180019b0a  mov     byte ptr [rdx+7], 3Dh ; '='
0x180019b0e  movzx   edx, byte ptr [rbx]
0x180019b11  test    dl, dl
0x180019b13  jz      loc_180019CAC
0x180019b19  nop     dword ptr [rax+00000000h]
0x180019b20  cmp     byte ptr [rbx+rcx+1], 0
0x180019b25  lea     rcx, [rcx+1]
0x180019b29  jnz     short loc_180019B20
0x180019b2b  lea     rax, [rcx-1]
0x180019b2f  add     rax, rbx
0x180019b32  cmp     dl, 20h ; ' '
0x180019b35  jz      loc_180019C2A
0x180019b3b  cmp     dl, 9
0x180019b3e  jz      loc_180019C2A
0x180019b44  cmp     rax, rbx
0x180019b47  ja      loc_180019C00
0x180019b4d  mov     byte ptr [rax+1], 0
0x180019b51  movzx   eax, byte ptr [rbx]
0x180019b54  movzx   ecx, al
0x180019b57  mov     rsi, rbx
0x180019b5a  call    cs:__imp__o_isdigit
0x180019b61  nop     dword ptr [rax+rax+00h]
0x180019b66  test    eax, eax
0x180019b68  jz      short loc_180019BB5
0x180019b6a  movzx   ecx, byte ptr [rbx+1]
0x180019b6e  inc     rbx
0x180019b71  call    cs:__imp__o_isdigit
0x180019b78  nop     dword ptr [rax+rax+00h]
0x180019b7d  test    eax, eax
0x180019b7f  jnz     short loc_180019B6A
0x180019b81  cmp     rbx, rsi
0x180019b84  jz      short loc_180019BB5
0x180019b86  mov     rax, [rdi+50h]
0x180019b8a  mov     r8, rbx
0x180019b8d  sub     r8, rsi; Size
0x180019b90  mov     rdx, rsi; Src
0x180019b93  mov     rcx, [rax+48h]
0x180019b97  add     rcx, 8; void *
0x180019b9b  call    memcpy_0
0x180019ba0  mov     rax, [rdi+50h]
0x180019ba4  mov     rcx, [rax+48h]
0x180019ba8  sub     rcx, rsi
0x180019bab  mov     byte ptr [rcx+rbx+8], 0
0x180019bb0  jmp     loc_180019A4F
0x180019bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bbc  lea     rax, WPP_GLOBAL_Control
0x180019bc3  cmp     rcx, rax
0x180019bc6  jnz     loc_180019CB3
0x180019bcc  mov     rbx, [rsp+28h+arg_0]
0x180019bd1  xor     eax, eax
0x180019bd3  mov     rsi, [rsp+28h+arg_8]
0x180019bd8  add     rsp, 20h
0x180019bdc  pop     rdi
0x180019bdd  retn
0x180019be0  movzx   eax, byte ptr [r8]
0x180019be4  cmp     al, 20h ; ' '
0x180019be6  jz      short loc_180019BF0
0x180019be8  cmp     al, 9
0x180019bea  jnz     loc_180019ACB
0x180019bf0  dec     r8
0x180019bf3  cmp     r8, rbx
0x180019bf6  ja      short loc_180019BE0
0x180019bf8  jmp     loc_180019ACB
0x180019c00  movzx   ecx, byte ptr [rax]
0x180019c03  cmp     cl, 20h ; ' '
0x180019c06  jz      short loc_180019C11
0x180019c08  cmp     cl, 9
0x180019c0b  jnz     loc_180019B4D
0x180019c11  dec     rax
0x180019c14  cmp     rax, rbx
0x180019c17  ja      short loc_180019C00
0x180019c19  jmp     loc_180019B4D
0x180019c1e  movzx   edx, byte ptr [rbx+1]
0x180019c22  inc     rbx
0x180019c25  jmp     loc_180019AB0
0x180019c2a  movzx   edx, byte ptr [rbx+1]
0x180019c2e  inc     rbx
0x180019c31  jmp     loc_180019B32
0x180019c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c3d  lea     rax, WPP_GLOBAL_Control
0x180019c44  cmp     rcx, rax
0x180019c47  jz      loc_180019A4F
0x180019c4d  test    byte ptr [rcx+1Ch], 1
0x180019c51  jz      loc_180019A4F
0x180019c57  mov     rcx, [rcx+10h]
0x180019c5b  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180019c62  mov     edx, 32h ; '2'
0x180019c67  call    WPP_SF_
0x180019c6c  jmp     loc_180019A4F
0x180019c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c78  lea     rax, WPP_GLOBAL_Control
0x180019c7f  cmp     rcx, rax
0x180019c82  jz      loc_180019BCC
0x180019c88  test    byte ptr [rcx+1Ch], 1
0x180019c8c  jz      loc_180019BCC
0x180019c92  mov     edx, 30h ; '0'
0x180019c97  mov     rcx, [rcx+10h]
0x180019c9b  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180019ca2  call    WPP_SF_
0x180019ca7  jmp     loc_180019BCC
0x180019cac  xor     al, al
0x180019cae  jmp     loc_180019B54
0x180019cb3  test    byte ptr [rcx+1Ch], 1
0x180019cb7  jz      loc_180019BCC
0x180019cbd  mov     edx, 31h ; '1'
0x180019cc2  jmp     short loc_180019C97
```
