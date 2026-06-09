# CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)

- ea: `0x18000b28c`
- end: `0x18000b5de`
- name: `?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z`
- size: `850`
- prototype: `int(CSsdpCacheEntry *__hidden this, struct _SSDP_REQUEST *, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009a84`
- `0x18000af80`

## callees

- `0x18000a844`
- `0x18000b28c`
- `0x1800271fc`
- `0x180037dcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b3ab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b41b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b48a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b3ab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b41b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000b48a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b4f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b514`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b563`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b58b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b5ae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b4f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b514`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b563`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b58b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b5ae`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(
        CSsdpCacheEntry *this,
        struct _SSDP_REQUEST *a2,
        struct _GUID *a3,
        unsigned int a4)
{
  __int64 v5; // rsi
  int v8; // r8d
  unsigned int v9; // edx
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int i; // edx
  __int64 v13; // rax
  __int64 j; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  char *v17; // r14
  unsigned int v18; // esi
  LPCSTR v19; // rcx
  char *v20; // rbp
  __int64 v21; // rdx
  __int64 v22; // rdx
  char *v23; // r15
  __int64 v24; // rcx
  __int128 v26; // [rsp+20h] [rbp-48h]
  __int128 v27; // [rsp+20h] [rbp-48h]

  v5 = a4;
  if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
  {
    v8 = 0;
    v9 = 0;
    v26 = *((_OWORD *)a2 + 2);
    while ( v9 < *((_DWORD *)this + 26) )
    {
      v10 = *((_QWORD *)this + 12) + ((unsigned __int64)v9 << 6);
      v11 = *(_QWORD *)(v10 + 48) - v26;
      if ( !v11 )
        v11 = *(_QWORD *)(v10 + 56) - *((_QWORD *)&v26 + 1);
      if ( !v11 )
        goto LABEL_15;
      ++v9;
    }
  }
  else
  {
    v8 = 1;
    v27 = (__int128)*a3;
    for ( i = 0; i < *((_DWORD *)this + 26); ++i )
    {
      v10 = *((_QWORD *)this + 12) + ((unsigned __int64)i << 6);
      v13 = *(_QWORD *)(v10 + 48) - v27;
      if ( !v13 )
        v13 = *(_QWORD *)(v10 + 56) - *((_QWORD *)&v27 + 1);
      if ( !v13 )
        goto LABEL_15;
    }
  }
  v10 = 0;
LABEL_15:
  if ( !v10 )
    return 2147942487LL;
  if ( *(_QWORD *)(v10 + 8 * v5 + 16) && *(_QWORD *)(v10 + 8 * v5) )
  {
LABEL_25:
    v17 = 0;
    if ( (unsigned int)_o__stricmp(*(_QWORD *)(*((_QWORD *)a2 + 10) + 48LL), *(_QWORD *)(v10 + 8 * v5)) )
    {
      v17 = SzaDupSza(*(const char **)(v10 + 8 * v5));
      if ( !v17 )
      {
        v18 = -2147024882;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
          return v18;
        if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        {
LABEL_49:
          if ( v19 != (LPCSTR)&WPP_GLOBAL_Control && (v19[28] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)v19 + 2), 53, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942414LL);
          return v18;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942414LL);
LABEL_48:
        v19 = WPP_GLOBAL_Control;
        goto LABEL_49;
      }
    }
    if ( (unsigned int)_o__stricmp(**((_QWORD **)a2 + 10), *(_QWORD *)(v10 + 8 * v5 + 16)) )
    {
      v20 = SzaDupSza(*(const char **)(v10 + 8 * v5 + 16));
      if ( !v20 )
      {
        v18 = -2147024882;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
          goto LABEL_44;
        v21 = 51;
LABEL_43:
        WPP_SF_d(*((_QWORD *)v19 + 2), v21, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942414LL);
        v19 = WPP_GLOBAL_Control;
LABEL_44:
        if ( v17 )
        {
          free(v17);
          v19 = WPP_GLOBAL_Control;
        }
        if ( !v20 )
          goto LABEL_49;
        free(v20);
        goto LABEL_48;
      }
    }
    else
    {
      v20 = 0;
    }
    v22 = *(_QWORD *)(v10 + 8 * v5 + 32);
    v23 = 0;
    if ( !v22
      || (v24 = *((_QWORD *)a2 + 6)) == 0
      || !(unsigned int)_o__stricmp(v24, v22)
      || (v23 = SzaDupSza(*(const char **)(v10 + 8 * v5 + 32))) != 0 )
    {
      v18 = 0;
      if ( v17 )
      {
        free(*(void **)(*((_QWORD *)a2 + 10) + 48LL));
        *(_QWORD *)(*((_QWORD *)a2 + 10) + 48LL) = 0;
        *(_QWORD *)(*((_QWORD *)a2 + 10) + 48LL) = v17;
      }
      if ( v20 )
      {
        free(**((void ***)a2 + 10));
        **((_QWORD **)a2 + 10) = 0;
        **((_QWORD **)a2 + 10) = v20;
      }
      if ( v23 )
      {
        free(*((void **)a2 + 6));
        *((_QWORD *)a2 + 6) = v23;
      }
      *((_OWORD *)a2 + 2) = *(_OWORD *)(v10 + 48);
      return v18;
    }
    v18 = -2147024882;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_44;
    v21 = 52;
    goto LABEL_43;
  }
  if ( !v8 )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 26); j = (unsigned int)(j + 1) )
    {
      v15 = *((_QWORD *)this + 12);
      v16 = v5 + 8 * j;
      if ( *(_QWORD *)(v15 + 8 * v16 + 16) && *(_QWORD *)(v15 + 8 * v16) )
      {
        v10 = ((unsigned __int64)(unsigned int)j << 6) + v15;
        if ( !v10 )
          return 2147942487LL;
        goto LABEL_25;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b28c  push    rbx
0x18000b28e  push    rbp
0x18000b28f  push    rsi
0x18000b290  push    rdi
0x18000b291  push    r14
0x18000b293  push    r15
0x18000b295  sub     rsp, 38h
0x18000b299  mov     rbx, r8
0x18000b29c  mov     esi, r9d
0x18000b29f  mov     rdi, rdx
0x18000b2a2  mov     rbp, rcx
0x18000b2a5  mov     rcx, rbx; Buf1
0x18000b2a8  lea     rdx, GUID_NULL; Buf2
0x18000b2af  mov     r8d, 10h; Size
0x18000b2b5  call    memcmp_0
0x18000b2ba  xor     r10d, r10d
0x18000b2bd  test    eax, eax
0x18000b2bf  setz    r10b
0x18000b2c3  test    r10d, r10d
0x18000b2c6  jz      short loc_18000B303
0x18000b2c8  movups  xmm0, xmmword ptr [rdi+20h]
0x18000b2cc  xor     r8d, r8d
0x18000b2cf  xor     edx, edx
0x18000b2d1  movdqu  [rsp+68h+var_48], xmm0
0x18000b2d7  cmp     edx, [rbp+68h]
0x18000b2da  jnb     short loc_18000B340
0x18000b2dc  mov     ebx, edx
0x18000b2de  shl     rbx, 6
0x18000b2e2  add     rbx, [rbp+60h]
0x18000b2e6  mov     rax, [rbx+30h]
0x18000b2ea  sub     rax, qword ptr [rsp+68h+var_48]
0x18000b2ef  jnz     short loc_18000B2FA
0x18000b2f1  mov     rax, [rbx+38h]
0x18000b2f5  sub     rax, qword ptr [rsp+68h+var_48+8]
0x18000b2fa  test    rax, rax
0x18000b2fd  jz      short loc_18000B342
0x18000b2ff  inc     edx
0x18000b301  jmp     short loc_18000B2D7
0x18000b303  movaps  xmm0, xmmword ptr [rbx]
0x18000b306  mov     r8d, 1
0x18000b30c  movdqa  [rsp+68h+var_48], xmm0
0x18000b312  xor     edx, edx
0x18000b314  cmp     edx, [rbp+68h]
0x18000b317  jnb     short loc_18000B340
0x18000b319  mov     ebx, edx
0x18000b31b  shl     rbx, 6
0x18000b31f  add     rbx, [rbp+60h]
0x18000b323  mov     rax, [rbx+30h]
0x18000b327  sub     rax, qword ptr [rsp+68h+var_48]
0x18000b32c  jnz     short loc_18000B337
0x18000b32e  mov     rax, [rbx+38h]
0x18000b332  sub     rax, qword ptr [rsp+68h+var_48+8]
0x18000b337  test    rax, rax
0x18000b33a  jz      short loc_18000B342
0x18000b33c  inc     edx
0x18000b33e  jmp     short loc_18000B314
0x18000b340  xor     ebx, ebx
0x18000b342  test    rbx, rbx
0x18000b345  jz      loc_18000B5CB
0x18000b34b  cmp     qword ptr [rbx+rsi*8+10h], 0
0x18000b351  jz      short loc_18000B35A
0x18000b353  cmp     qword ptr [rbx+rsi*8], 0
0x18000b358  jnz     short loc_18000B39C
0x18000b35a  test    r8d, r8d
0x18000b35d  jnz     loc_18000B5CB
0x18000b363  xor     eax, eax
0x18000b365  cmp     eax, [rbp+68h]
0x18000b368  jnb     loc_18000B5CB
0x18000b36e  mov     rdx, [rbp+60h]
0x18000b372  lea     r8, [rsi+rax*8]
0x18000b376  mov     ecx, eax
0x18000b378  cmp     qword ptr [rdx+r8*8+10h], 0
0x18000b37e  jz      short loc_18000B387
0x18000b380  cmp     qword ptr [rdx+r8*8], 0
0x18000b385  jnz     short loc_18000B38B
0x18000b387  inc     eax
0x18000b389  jmp     short loc_18000B365
0x18000b38b  shl     rcx, 6
0x18000b38f  lea     rbx, [rcx+rdx]
0x18000b393  test    rbx, rbx
0x18000b396  jz      loc_18000B5CB
0x18000b39c  mov     rcx, [rdi+50h]
0x18000b3a0  xor     r14d, r14d
0x18000b3a3  mov     rdx, [rbx+rsi*8]
0x18000b3a7  mov     rcx, [rcx+30h]
0x18000b3ab  call    cs:__imp__o__stricmp
0x18000b3b2  nop     dword ptr [rax+rax+00h]
0x18000b3b7  test    eax, eax
0x18000b3b9  jz      short loc_18000B40F
0x18000b3bb  mov     rcx, [rbx+rsi*8]; char *
0x18000b3bf  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000b3c4  mov     r14, rax
0x18000b3c7  test    rax, rax
0x18000b3ca  jnz     short loc_18000B40F
0x18000b3cc  mov     ebx, 8007000Eh
0x18000b3d1  mov     esi, ebx
0x18000b3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3da  lea     rdi, WPP_GLOBAL_Control
0x18000b3e1  cmp     rcx, rdi
0x18000b3e4  jz      loc_18000B5C7
0x18000b3ea  test    byte ptr [rcx+1Ch], 1
0x18000b3ee  jz      loc_18000B527
0x18000b3f4  mov     rcx, [rcx+10h]
0x18000b3f8  lea     edx, [rax+32h]
0x18000b3fb  mov     r9d, ebx
0x18000b3fe  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000b405  call    WPP_SF_d
0x18000b40a  jmp     loc_18000B520
0x18000b40f  mov     rcx, [rdi+50h]
0x18000b413  mov     rdx, [rbx+rsi*8+10h]
0x18000b418  mov     rcx, [rcx]
0x18000b41b  call    cs:__imp__o__stricmp
0x18000b422  nop     dword ptr [rax+rax+00h]
0x18000b427  test    eax, eax
0x18000b429  jz      short loc_18000B46A
0x18000b42b  mov     rcx, [rbx+rsi*8+10h]; char *
0x18000b430  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000b435  mov     rbp, rax
0x18000b438  test    rax, rax
0x18000b43b  jnz     short loc_18000B46C
0x18000b43d  mov     ebx, 8007000Eh
0x18000b442  mov     esi, ebx
0x18000b444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b44b  lea     rdi, WPP_GLOBAL_Control
0x18000b452  cmp     rcx, rdi
0x18000b455  jz      loc_18000B4F1
0x18000b45b  test    byte ptr [rcx+1Ch], 1
0x18000b45f  jz      loc_18000B4F1
0x18000b465  lea     edx, [rax+33h]
0x18000b468  jmp     short loc_18000B4D7
0x18000b46a  xor     ebp, ebp
0x18000b46c  mov     rdx, [rbx+rsi*8+20h]
0x18000b471  xor     r15d, r15d
0x18000b474  test    rdx, rdx
0x18000b477  jz      loc_18000B554
0x18000b47d  mov     rcx, [rdi+30h]
0x18000b481  test    rcx, rcx
0x18000b484  jz      loc_18000B554
0x18000b48a  call    cs:__imp__o__stricmp
0x18000b491  nop     dword ptr [rax+rax+00h]
0x18000b496  test    eax, eax
0x18000b498  jz      loc_18000B554
0x18000b49e  mov     rcx, [rbx+rsi*8+20h]; char *
0x18000b4a3  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000b4a8  mov     r15, rax
0x18000b4ab  test    rax, rax
0x18000b4ae  jnz     loc_18000B554
0x18000b4b4  mov     ebx, 8007000Eh
0x18000b4b9  mov     esi, ebx
0x18000b4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4c2  lea     rdi, WPP_GLOBAL_Control
0x18000b4c9  cmp     rcx, rdi
0x18000b4cc  jz      short loc_18000B4F1
0x18000b4ce  test    byte ptr [rcx+1Ch], 1
0x18000b4d2  jz      short loc_18000B4F1
0x18000b4d4  lea     edx, [rax+34h]
0x18000b4d7  mov     rcx, [rcx+10h]
0x18000b4db  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000b4e2  mov     r9d, ebx
0x18000b4e5  call    WPP_SF_d
0x18000b4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4f1  test    r14, r14
0x18000b4f4  jz      short loc_18000B50C
0x18000b4f6  mov     rcx, r14; Block
0x18000b4f9  call    cs:__imp_free
0x18000b500  nop     dword ptr [rax+rax+00h]
0x18000b505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b50c  test    rbp, rbp
0x18000b50f  jz      short loc_18000B527
0x18000b511  mov     rcx, rbp; Block
0x18000b514  call    cs:__imp_free
0x18000b51b  nop     dword ptr [rax+rax+00h]
0x18000b520  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b527  cmp     rcx, rdi
0x18000b52a  jz      loc_18000B5C7
0x18000b530  test    byte ptr [rcx+1Ch], 1
0x18000b534  jz      loc_18000B5C7
0x18000b53a  mov     rcx, [rcx+10h]
0x18000b53e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000b545  mov     edx, 35h ; '5'
0x18000b54a  mov     r9d, ebx
0x18000b54d  call    WPP_SF_d
0x18000b552  jmp     short loc_18000B5C7
0x18000b554  xor     esi, esi
0x18000b556  test    r14, r14
0x18000b559  jz      short loc_18000B57F
0x18000b55b  mov     rcx, [rdi+50h]
0x18000b55f  mov     rcx, [rcx+30h]; Block
0x18000b563  call    cs:__imp_free
0x18000b56a  nop     dword ptr [rax+rax+00h]
0x18000b56f  mov     rax, [rdi+50h]
0x18000b573  mov     [rax+30h], rsi
0x18000b577  mov     rax, [rdi+50h]
0x18000b57b  mov     [rax+30h], r14
0x18000b57f  test    rbp, rbp
0x18000b582  jz      short loc_18000B5A5
0x18000b584  mov     rcx, [rdi+50h]
0x18000b588  mov     rcx, [rcx]; Block
0x18000b58b  call    cs:__imp_free
0x18000b592  nop     dword ptr [rax+rax+00h]
0x18000b597  mov     rax, [rdi+50h]
0x18000b59b  mov     [rax], rsi
0x18000b59e  mov     rax, [rdi+50h]
0x18000b5a2  mov     [rax], rbp
0x18000b5a5  test    r15, r15
0x18000b5a8  jz      short loc_18000B5BE
0x18000b5aa  mov     rcx, [rdi+30h]; Block
0x18000b5ae  call    cs:__imp_free
0x18000b5b5  nop     dword ptr [rax+rax+00h]
0x18000b5ba  mov     [rdi+30h], r15
0x18000b5be  movups  xmm0, xmmword ptr [rbx+30h]
0x18000b5c2  movdqu  xmmword ptr [rdi+20h], xmm0
0x18000b5c7  mov     eax, esi
0x18000b5c9  jmp     short loc_18000B5D0
0x18000b5cb  mov     eax, 80070057h
0x18000b5d0  add     rsp, 38h
0x18000b5d4  pop     r15
0x18000b5d6  pop     r14
0x18000b5d8  pop     rdi
0x18000b5d9  pop     rsi
0x18000b5da  pop     rbp
0x18000b5db  pop     rbx
0x18000b5dc  retn
```
