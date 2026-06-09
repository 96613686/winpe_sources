# HrCopySsdpMessage(_SSDP_MESSAGE_EX * *,_SSDP_MESSAGE_EX const *)

- ea: `0x18000d840`
- end: `0x18000dd5f`
- name: `?HrCopySsdpMessage@@YAJPEAPEAU_SSDP_MESSAGE_EX@@PEBU1@@Z`
- size: `1311`
- prototype: `__int64 __fastcall(struct _SSDP_MESSAGE_EX **, const struct _SSDP_MESSAGE_EX *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d564`

## callees

- `0x18000d840`
- `0x18000dd70`
- `0x1800200f4`
- `0x18003d4b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc84`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d871`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d94a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000da08`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000daf6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dcbe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d871`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d94a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000da08`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000daf6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dcbe`
- `SSDPAPI!FreeSsdpMessageEx` at `0x18000da86`
- `SSDPAPI!FreeSsdpMessageEx` at `0x18000da86`

## string_xrefs

- `0x18000dd3d`: `HrCopySsdpMessage`

## pseudocode

```c
__int64 __fastcall HrCopySsdpMessage(struct _SSDP_MESSAGE_EX **a1, const struct _SSDP_MESSAGE_EX *a2)
{
  char *v3; // rax
  char *v4; // r15
  const char *v5; // rcx
  unsigned int v6; // esi
  int v7; // r13d
  char *v8; // rcx
  const char *v9; // rcx
  const char *v10; // rcx
  const char *v11; // rcx
  _BYTE *v12; // rbx
  __int64 v13; // rbp
  __int64 v14; // r14
  void *v15; // r8
  __int64 v16; // rax
  bool v17; // zf
  unsigned int v18; // esi
  __int64 v19; // rdi
  _BYTE *v20; // rax
  __int64 v21; // rcx
  _BYTE *v22; // rdx
  _BYTE *v23; // rax
  const char *v24; // rcx
  _BYTE *v25; // rbx
  _BYTE *v26; // rbx
  void *v27; // rdx
  unsigned int v28; // esi
  __int64 v29; // rdi
  _BYTE *v30; // rax
  _BYTE *v31; // rcx
  _BYTE *v32; // rax
  void *v34; // r8
  __int64 v35; // rax
  unsigned int v36; // esi
  __int64 v37; // rdi
  _BYTE *v38; // rax
  __int64 v39; // rcx
  _BYTE *v40; // rdx
  _BYTE *v41; // rax
  char *v42; // rax
  __int64 v43; // rdi
  char *v44; // rax
  char *v45; // rax
  char *v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // r14
  char *v49; // rax

  v3 = (char *)malloc(0x78u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_44;
  v5 = (const char *)*((_QWORD *)a2 + 2);
  *((_QWORD *)v3 + 2) = 0;
  *(_OWORD *)(v3 + 88) = 0;
  *((_QWORD *)v3 + 13) = 0;
  v6 = 0;
  *((_DWORD *)v3 + 11) = *((_DWORD *)a2 + 11);
  *((_DWORD *)v3 + 10) = *((_DWORD *)a2 + 10);
  *((_QWORD *)v3 + 14) = 0;
  *(_OWORD *)(v3 + 56) = *(_OWORD *)((char *)a2 + 56);
  if ( v5 )
  {
    v7 = -2147024882;
    v8 = SzaDupSza(v5);
    if ( v8 )
      v7 = 0;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  *((_QWORD *)v4 + 2) = v8;
  v9 = (const char *)*((_QWORD *)a2 + 9);
  if ( v9 && v7 >= 0 )
  {
    v42 = SzaDupSza(v9);
    *((_QWORD *)v4 + 9) = v42;
    if ( !v42 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 9) = 0;
  }
  v10 = (const char *)*((_QWORD *)a2 + 10);
  if ( v10 && v7 >= 0 )
  {
    v44 = SzaDupSza(v10);
    *((_QWORD *)v4 + 10) = v44;
    if ( !v44 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 10) = 0;
  }
  v11 = (const char *)*((_QWORD *)a2 + 6);
  if ( v11 && v7 >= 0 )
  {
    v45 = SzaDupSza(v11);
    *((_QWORD *)v4 + 6) = v45;
    if ( !v45 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 6) = 0;
  }
  v12 = (_BYTE *)*((_QWORD *)a2 + 1);
  v13 = 2147483646;
  v14 = -1;
  if ( !v12 || v7 < 0 )
  {
    *((_QWORD *)v4 + 1) = 0;
    goto LABEL_25;
  }
  v15 = 0;
  v16 = -1;
  do
    v17 = v12[++v16] == 0;
  while ( !v17 );
  v18 = v16 + 1;
  if ( (_DWORD)v16 != -1 )
  {
    v19 = v18;
    v20 = malloc(v18);
    v15 = v20;
    if ( v20 )
    {
      if ( v18 > 0x7FFFFFFF )
      {
        *v20 = 0;
      }
      else
      {
        v21 = 2147483646;
        v22 = v20;
        do
        {
          if ( !v21 )
            break;
          if ( !*v12 )
            break;
          *v22++ = *v12++;
          --v21;
          --v19;
        }
        while ( v19 );
        v23 = v22 - 1;
        if ( v19 )
          v23 = v22;
        *v23 = 0;
        if ( v19 )
          goto LABEL_24;
      }
      free(v15);
      v6 = 0;
      *((_QWORD *)v4 + 1) = 0;
      goto LABEL_81;
    }
  }
LABEL_24:
  v6 = 0;
  *((_QWORD *)v4 + 1) = v15;
  if ( !v15 )
LABEL_81:
    v7 = -2147024882;
LABEL_25:
  v24 = (const char *)*((_QWORD *)a2 + 4);
  if ( v24 && v7 >= 0 )
  {
    v46 = SzaDupSza(v24);
    *((_QWORD *)v4 + 4) = v46;
    if ( !v46 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 4) = 0;
  }
  v25 = *(_BYTE **)a2;
  if ( !*(_QWORD *)a2 || v7 < 0 )
  {
    *(_QWORD *)v4 = 0;
    goto LABEL_29;
  }
  v34 = 0;
  v35 = -1;
  do
    v17 = v25[++v35] == 0;
  while ( !v17 );
  v36 = v35 + 1;
  if ( (_DWORD)v35 != -1 )
  {
    v37 = v36;
    v38 = malloc(v36);
    v34 = v38;
    if ( v38 )
    {
      if ( v36 > 0x7FFFFFFF )
      {
        *v38 = 0;
      }
      else
      {
        v39 = 2147483646;
        v40 = v38;
        do
        {
          if ( !v39 )
            break;
          if ( !*v25 )
            break;
          *v40++ = *v25++;
          --v39;
          --v37;
        }
        while ( v37 );
        v41 = v40 - 1;
        if ( v37 )
          v41 = v40;
        *v41 = 0;
        if ( v37 )
          goto LABEL_62;
      }
      free(v34);
      v6 = 0;
      *(_QWORD *)v4 = 0;
LABEL_87:
      v7 = -2147024882;
      goto LABEL_29;
    }
  }
LABEL_62:
  v6 = 0;
  *(_QWORD *)v4 = v34;
  if ( !v34 )
    goto LABEL_87;
LABEL_29:
  v26 = (_BYTE *)*((_QWORD *)a2 + 3);
  if ( !v26 || v7 < 0 )
  {
    *((_QWORD *)v4 + 3) = 0;
    if ( v7 < 0 )
      goto LABEL_46;
LABEL_68:
    v43 = *((unsigned int *)a2 + 26);
    if ( (_DWORD)v43 && *((_QWORD *)a2 + 14) )
    {
      *((_DWORD *)v4 + 26) = v43;
      v47 = malloc(8 * v43);
      *((_QWORD *)v4 + 14) = v47;
      v48 = v47;
      if ( !v47 )
        goto LABEL_44;
      memset_0(v47, 0, 8 * v43);
      while ( v6 < (unsigned int)v43 )
      {
        v49 = SzaDupSza(*(const char **)(8LL * v6 + *((_QWORD *)a2 + 14)));
        v48[v6] = v49;
        if ( !v49 )
          goto LABEL_44;
        ++v6;
      }
    }
    *a1 = (struct _SSDP_MESSAGE_EX *)v4;
    goto LABEL_47;
  }
  v27 = 0;
  do
    v17 = v26[++v14] == 0;
  while ( !v17 );
  v28 = v14 + 1;
  if ( (_DWORD)v14 != -1 )
  {
    v29 = v28;
    v30 = malloc(v28);
    v27 = v30;
    if ( v30 )
    {
      if ( v28 > 0x7FFFFFFF )
      {
        *v30 = 0;
      }
      else
      {
        v31 = v30;
        do
        {
          if ( !v13 )
            break;
          if ( !*v26 )
            break;
          *v31++ = *v26++;
          --v13;
          --v29;
        }
        while ( v29 );
        v32 = v31 - 1;
        if ( v29 )
          v32 = v31;
        *v32 = 0;
        if ( v29 )
          goto LABEL_43;
      }
      free(v27);
      *((_QWORD *)v4 + 3) = 0;
      goto LABEL_44;
    }
  }
LABEL_43:
  *((_QWORD *)v4 + 3) = v27;
  if ( v27 )
  {
    v6 = 0;
    goto LABEL_68;
  }
LABEL_44:
  v7 = -2147024882;
LABEL_46:
  FreeSsdpMessageEx(v4);
LABEL_47:
  if ( v7 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_46aece34ec5f3261a433300ce9b09bc3_Traceguids,
      (unsigned int)"HrCopySsdpMessage",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d840  mov     rax, rsp
0x18000d843  mov     [rax+8], rcx
0x18000d847  push    r13
0x18000d849  sub     rsp, 50h
0x18000d84d  mov     [rax+10h], rbx
0x18000d851  mov     ecx, 78h ; 'x'; Size
0x18000d856  mov     [rax+18h], rbp
0x18000d85a  mov     [rax+20h], rsi
0x18000d85e  mov     [rax-10h], rdi
0x18000d862  mov     [rax-18h], r12
0x18000d866  mov     r12, rdx
0x18000d869  mov     [rax-20h], r14
0x18000d86d  mov     [rax-28h], r15
0x18000d871  call    cs:__imp_malloc
0x18000d878  nop     dword ptr [rax+rax+00h]
0x18000d87d  mov     r15, rax
0x18000d880  test    rax, rax
0x18000d883  jz      loc_18000DA6E
0x18000d889  mov     rcx, [r12+10h]; char *
0x18000d88e  xor     eax, eax
0x18000d890  mov     [r15+10h], rax
0x18000d894  xorps   xmm0, xmm0
0x18000d897  movups  xmmword ptr [r15+58h], xmm0
0x18000d89c  mov     [r15+68h], rax
0x18000d8a0  xor     esi, esi
0x18000d8a2  mov     eax, [r12+2Ch]
0x18000d8a7  mov     [r15+2Ch], eax
0x18000d8ab  mov     eax, [r12+28h]
0x18000d8b0  mov     [r15+28h], eax
0x18000d8b4  mov     [r15+70h], rsi
0x18000d8b8  movups  xmm0, xmmword ptr [r12+38h]
0x18000d8be  movups  xmmword ptr [r15+38h], xmm0
0x18000d8c3  test    rcx, rcx
0x18000d8c6  jnz     loc_18000DBAD
0x18000d8cc  mov     r13d, esi
0x18000d8cf  mov     ecx, esi
0x18000d8d1  mov     [r15+10h], rcx
0x18000d8d5  mov     rcx, [r12+48h]; char *
0x18000d8da  test    rcx, rcx
0x18000d8dd  jnz     loc_18000DB64
0x18000d8e3  mov     [r15+48h], rsi
0x18000d8e7  mov     rcx, [r12+50h]; char *
0x18000d8ec  test    rcx, rcx
0x18000d8ef  jnz     loc_18000DBC7
0x18000d8f5  mov     [r15+50h], rsi
0x18000d8f9  mov     rcx, [r12+30h]; char *
0x18000d8fe  test    rcx, rcx
0x18000d901  jnz     loc_18000DBED
0x18000d907  mov     [r15+30h], rsi
0x18000d90b  mov     rbx, [r12+8]
0x18000d910  mov     ebp, 7FFFFFFEh
0x18000d915  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000d91c  test    rbx, rbx
0x18000d91f  jz      loc_18000DB8A
0x18000d925  test    r13d, r13d
0x18000d928  js      loc_18000DB8A
0x18000d92e  mov     r8, rsi
0x18000d931  mov     rax, r14
0x18000d934  cmp     [rbx+rax+1], sil
0x18000d939  lea     rax, [rax+1]
0x18000d93d  jnz     short loc_18000D934
0x18000d93f  lea     esi, [rax+1]
0x18000d942  test    esi, esi
0x18000d944  jz      short loc_18000D9A1
0x18000d946  mov     ecx, esi; Size
0x18000d948  mov     edi, esi
0x18000d94a  call    cs:__imp_malloc
0x18000d951  nop     dword ptr [rax+rax+00h]
0x18000d956  mov     r8, rax
0x18000d959  test    rax, rax
0x18000d95c  jz      short loc_18000D9A1
0x18000d95e  cmp     esi, 7FFFFFFFh
0x18000d964  ja      loc_18000DC13
0x18000d96a  mov     rcx, rbp
0x18000d96d  mov     rdx, rax
0x18000d970  test    rcx, rcx
0x18000d973  jz      short loc_18000D98D
0x18000d975  movzx   eax, byte ptr [rbx]
0x18000d978  test    al, al
0x18000d97a  jz      short loc_18000D98D
0x18000d97c  mov     [rdx], al
0x18000d97e  inc     rbx
0x18000d981  inc     rdx
0x18000d984  dec     rcx
0x18000d987  sub     rdi, 1
0x18000d98b  jnz     short loc_18000D970
0x18000d98d  test    rdi, rdi
0x18000d990  lea     rax, [rdx-1]
0x18000d994  cmovnz  rax, rdx
0x18000d998  mov     byte ptr [rax], 0
0x18000d99b  jz      loc_18000DC16
0x18000d9a1  xor     esi, esi
0x18000d9a3  mov     [r15+8], r8
0x18000d9a7  test    r8, r8
0x18000d9aa  jz      loc_18000DC2B
0x18000d9b0  mov     rcx, [r12+20h]; char *
0x18000d9b5  test    rcx, rcx
0x18000d9b8  jnz     loc_18000DC36
0x18000d9be  mov     [r15+20h], rsi
0x18000d9c2  mov     rbx, [r12]
0x18000d9c6  test    rbx, rbx
0x18000d9c9  jnz     loc_18000DAC9
0x18000d9cf  mov     [r15], rsi
0x18000d9d2  mov     rbx, [r12+18h]
0x18000d9d7  test    rbx, rbx
0x18000d9da  jz      loc_18000DA76
0x18000d9e0  test    r13d, r13d
0x18000d9e3  js      loc_18000DA76
0x18000d9e9  mov     rdx, rsi
0x18000d9ec  nop     dword ptr [rax+00h]
0x18000d9f0  cmp     byte ptr [rbx+r14+1], 0
0x18000d9f6  lea     r14, [r14+1]
0x18000d9fa  jnz     short loc_18000D9F0
0x18000d9fc  lea     esi, [r14+1]
0x18000da00  test    esi, esi
0x18000da02  jz      short loc_18000DA61
0x18000da04  mov     ecx, esi; Size
0x18000da06  mov     edi, esi
0x18000da08  call    cs:__imp_malloc
0x18000da0f  nop     dword ptr [rax+rax+00h]
0x18000da14  mov     rdx, rax
0x18000da17  test    rax, rax
0x18000da1a  jz      short loc_18000DA61
0x18000da1c  cmp     esi, 7FFFFFFFh
0x18000da22  ja      loc_18000DC7E
0x18000da28  mov     rcx, rax
0x18000da2b  nop     dword ptr [rax+rax+00h]
0x18000da30  test    rbp, rbp
0x18000da33  jz      short loc_18000DA4D
0x18000da35  movzx   eax, byte ptr [rbx]
0x18000da38  test    al, al
0x18000da3a  jz      short loc_18000DA4D
0x18000da3c  mov     [rcx], al
0x18000da3e  inc     rbx
0x18000da41  inc     rcx
0x18000da44  dec     rbp
0x18000da47  sub     rdi, 1
0x18000da4b  jnz     short loc_18000DA30
0x18000da4d  test    rdi, rdi
0x18000da50  lea     rax, [rcx-1]
0x18000da54  cmovnz  rax, rcx
0x18000da58  mov     byte ptr [rax], 0
0x18000da5b  jz      loc_18000DC81
0x18000da61  mov     [r15+18h], rdx
0x18000da65  test    rdx, rdx
0x18000da68  jnz     loc_18000DC9D
0x18000da6e  mov     r13d, 8007000Eh
0x18000da74  jmp     short loc_18000DA83
0x18000da76  mov     [r15+18h], rsi
0x18000da7a  test    r13d, r13d
0x18000da7d  jns     loc_18000DB93
0x18000da83  mov     rcx, r15
0x18000da86  call    cs:__imp_FreeSsdpMessageEx
0x18000da8d  nop     dword ptr [rax+rax+00h]
0x18000da92  mov     r15, [rsp+58h+var_28]
0x18000da97  mov     r14, [rsp+58h+var_20]
0x18000da9c  mov     r12, [rsp+58h+var_18]
0x18000daa1  mov     rdi, [rsp+58h+var_10]
0x18000daa6  mov     rsi, [rsp+58h+arg_18]
0x18000daab  mov     rbp, [rsp+58h+arg_10]
0x18000dab0  mov     rbx, [rsp+58h+arg_8]
0x18000dab5  test    r13d, r13d
0x18000dab8  jnz     loc_18000DD18
0x18000dabe  mov     eax, r13d
0x18000dac1  add     rsp, 50h
0x18000dac5  pop     r13
0x18000dac7  retn
0x18000dac9  test    r13d, r13d
0x18000dacc  js      loc_18000D9CF
0x18000dad2  mov     r8, rsi
0x18000dad5  mov     rax, r14
0x18000dad8  nop     dword ptr [rax+rax+00000000h]
0x18000dae0  cmp     byte ptr [rbx+rax+1], 0
0x18000dae5  lea     rax, [rax+1]
0x18000dae9  jnz     short loc_18000DAE0
0x18000daeb  lea     esi, [rax+1]
0x18000daee  test    esi, esi
0x18000daf0  jz      short loc_18000DB51
0x18000daf2  mov     ecx, esi; Size
0x18000daf4  mov     edi, esi
0x18000daf6  call    cs:__imp_malloc
0x18000dafd  nop     dword ptr [rax+rax+00h]
0x18000db02  mov     r8, rax
0x18000db05  test    rax, rax
0x18000db08  jz      short loc_18000DB51
0x18000db0a  cmp     esi, 7FFFFFFFh
0x18000db10  ja      loc_18000DC5C
0x18000db16  mov     rcx, rbp
0x18000db19  mov     rdx, rax
0x18000db1c  nop     dword ptr [rax+00h]
0x18000db20  test    rcx, rcx
0x18000db23  jz      short loc_18000DB3D
0x18000db25  movzx   eax, byte ptr [rbx]
0x18000db28  test    al, al
0x18000db2a  jz      short loc_18000DB3D
0x18000db2c  mov     [rdx], al
0x18000db2e  inc     rbx
0x18000db31  inc     rdx
0x18000db34  dec     rcx
0x18000db37  sub     rdi, 1
0x18000db3b  jnz     short loc_18000DB20
0x18000db3d  test    rdi, rdi
0x18000db40  lea     rax, [rdx-1]
0x18000db44  cmovnz  rax, rdx
0x18000db48  mov     byte ptr [rax], 0
0x18000db4b  jz      loc_18000DC5F
0x18000db51  xor     esi, esi
0x18000db53  mov     [r15], r8
0x18000db56  test    r8, r8
0x18000db59  jnz     loc_18000D9D2
0x18000db5f  jmp     loc_18000DC73
0x18000db64  test    r13d, r13d
0x18000db67  js      loc_18000D8E3
0x18000db6d  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000db72  mov     [r15+48h], rax
0x18000db76  test    rax, rax
0x18000db79  jnz     loc_18000D8E7
0x18000db7f  mov     r13d, 8007000Eh
0x18000db85  jmp     loc_18000D8E7
0x18000db8a  mov     [r15+8], rsi
0x18000db8e  jmp     loc_18000D9B0
0x18000db93  mov     edi, [r12+68h]
0x18000db98  test    edi, edi
0x18000db9a  jnz     loc_18000DCA4
0x18000dba0  mov     rax, [rsp+58h+arg_0]
0x18000dba5  mov     [rax], r15
0x18000dba8  jmp     loc_18000DA92
0x18000dbad  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000dbb2  test    rax, rax
0x18000dbb5  mov     r13d, 8007000Eh
0x18000dbbb  mov     rcx, rax
0x18000dbbe  cmovnz  r13d, esi
0x18000dbc2  jmp     loc_18000D8D1
0x18000dbc7  test    r13d, r13d
0x18000dbca  js      loc_18000D8F5
0x18000dbd0  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000dbd5  mov     [r15+50h], rax
0x18000dbd9  test    rax, rax
0x18000dbdc  jnz     loc_18000D8F9
0x18000dbe2  mov     r13d, 8007000Eh
0x18000dbe8  jmp     loc_18000D8F9
0x18000dbed  test    r13d, r13d
0x18000dbf0  js      loc_18000D907
0x18000dbf6  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000dbfb  mov     [r15+30h], rax
0x18000dbff  test    rax, rax
0x18000dc02  jnz     loc_18000D90B
0x18000dc08  mov     r13d, 8007000Eh
0x18000dc0e  jmp     loc_18000D90B
0x18000dc13  mov     byte ptr [rax], 0
0x18000dc16  mov     rcx, r8; Block
0x18000dc19  call    cs:__imp_free
0x18000dc20  nop     dword ptr [rax+rax+00h]
0x18000dc25  xor     esi, esi
0x18000dc27  mov     [r15+8], rsi
0x18000dc2b  mov     r13d, 8007000Eh
0x18000dc31  jmp     loc_18000D9B0
0x18000dc36  test    r13d, r13d
0x18000dc39  js      loc_18000D9BE
0x18000dc3f  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000dc44  mov     [r15+20h], rax
0x18000dc48  test    rax, rax
0x18000dc4b  jnz     loc_18000D9C2
0x18000dc51  mov     r13d, 8007000Eh
0x18000dc57  jmp     loc_18000D9C2
0x18000dc5c  mov     byte ptr [rax], 0
0x18000dc5f  mov     rcx, r8; Block
0x18000dc62  call    cs:__imp_free
0x18000dc69  nop     dword ptr [rax+rax+00h]
0x18000dc6e  xor     esi, esi
0x18000dc70  mov     [r15], rsi
0x18000dc73  mov     r13d, 8007000Eh
0x18000dc79  jmp     loc_18000D9D2
0x18000dc7e  mov     byte ptr [rax], 0
0x18000dc81  mov     rcx, rdx; Block
0x18000dc84  call    cs:__imp_free
0x18000dc8b  nop     dword ptr [rax+rax+00h]
0x18000dc90  mov     qword ptr [r15+18h], 0
0x18000dc98  jmp     loc_18000DA6E
0x18000dc9d  xor     esi, esi
0x18000dc9f  jmp     loc_18000DB93
0x18000dca4  cmp     qword ptr [r12+70h], 0
0x18000dcaa  jz      loc_18000DBA0
0x18000dcb0  mov     rbx, rdi
0x18000dcb3  mov     [r15+68h], edi
0x18000dcb7  shl     rbx, 3
0x18000dcbb  mov     rcx, rbx; Size
0x18000dcbe  call    cs:__imp_malloc
0x18000dcc5  nop     dword ptr [rax+rax+00h]
0x18000dcca  mov     [r15+70h], rax
0x18000dcce  mov     r14, rax
0x18000dcd1  test    rax, rax
0x18000dcd4  jz      loc_18000DA6E
0x18000dcda  mov     r8, rbx; Size
0x18000dcdd  xor     edx, edx; Val
0x18000dcdf  mov     rcx, rax; void *
0x18000dce2  call    memset_0
0x18000dce7  cmp     esi, edi
0x18000dce9  jnb     loc_18000DBA0
0x18000dcef  mov     rcx, [r12+70h]
  ... truncated ...
```
