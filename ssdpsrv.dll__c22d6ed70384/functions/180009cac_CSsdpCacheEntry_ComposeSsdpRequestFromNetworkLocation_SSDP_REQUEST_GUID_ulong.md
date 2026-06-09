# CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)

- ea: `0x180009cac`
- end: `0x180009fc9`
- name: `?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z`
- size: `797`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *this, struct _SSDP_REQUEST *, struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800084e0`
- `0x1800099c8`

## callees

- `0x18000920c`
- `0x180009cac`
- `0x1800255a8`
- `0x18003528c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009dcb`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009e35`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009e9e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009dcb`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009e35`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180009e9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fa0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f1c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fa0`

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
0x180009cac  push    rbx
0x180009cae  push    rbp
0x180009caf  push    rsi
0x180009cb0  push    rdi
0x180009cb1  push    r14
0x180009cb3  push    r15
0x180009cb5  sub     rsp, 38h
0x180009cb9  mov     rbx, r8
0x180009cbc  mov     esi, r9d
0x180009cbf  mov     rdi, rdx
0x180009cc2  mov     rbp, rcx
0x180009cc5  mov     rcx, rbx; Buf1
0x180009cc8  lea     rdx, GUID_NULL; Buf2
0x180009ccf  mov     r8d, 10h; Size
0x180009cd5  call    memcmp_0
0x180009cda  xor     r10d, r10d
0x180009cdd  test    eax, eax
0x180009cdf  setz    r10b
0x180009ce3  test    r10d, r10d
0x180009ce6  jz      short loc_180009D23
0x180009ce8  movups  xmm0, xmmword ptr [rdi+20h]
0x180009cec  xor     r8d, r8d
0x180009cef  xor     edx, edx
0x180009cf1  movdqu  [rsp+68h+var_48], xmm0
0x180009cf7  cmp     edx, [rbp+68h]
0x180009cfa  jnb     short loc_180009D60
0x180009cfc  mov     ebx, edx
0x180009cfe  shl     rbx, 6
0x180009d02  add     rbx, [rbp+60h]
0x180009d06  mov     rax, [rbx+30h]
0x180009d0a  sub     rax, qword ptr [rsp+68h+var_48]
0x180009d0f  jnz     short loc_180009D1A
0x180009d11  mov     rax, [rbx+38h]
0x180009d15  sub     rax, qword ptr [rsp+68h+var_48+8]
0x180009d1a  test    rax, rax
0x180009d1d  jz      short loc_180009D62
0x180009d1f  inc     edx
0x180009d21  jmp     short loc_180009CF7
0x180009d23  movaps  xmm0, xmmword ptr [rbx]
0x180009d26  mov     r8d, 1
0x180009d2c  movdqa  [rsp+68h+var_48], xmm0
0x180009d32  xor     edx, edx
0x180009d34  cmp     edx, [rbp+68h]
0x180009d37  jnb     short loc_180009D60
0x180009d39  mov     ebx, edx
0x180009d3b  shl     rbx, 6
0x180009d3f  add     rbx, [rbp+60h]
0x180009d43  mov     rax, [rbx+30h]
0x180009d47  sub     rax, qword ptr [rsp+68h+var_48]
0x180009d4c  jnz     short loc_180009D57
0x180009d4e  mov     rax, [rbx+38h]
0x180009d52  sub     rax, qword ptr [rsp+68h+var_48+8]
0x180009d57  test    rax, rax
0x180009d5a  jz      short loc_180009D62
0x180009d5c  inc     edx
0x180009d5e  jmp     short loc_180009D34
0x180009d60  xor     ebx, ebx
0x180009d62  test    rbx, rbx
0x180009d65  jz      loc_180009FB7
0x180009d6b  cmp     qword ptr [rbx+rsi*8+10h], 0
0x180009d71  jz      short loc_180009D7A
0x180009d73  cmp     qword ptr [rbx+rsi*8], 0
0x180009d78  jnz     short loc_180009DBC
0x180009d7a  test    r8d, r8d
0x180009d7d  jnz     loc_180009FB7
0x180009d83  xor     eax, eax
0x180009d85  cmp     eax, [rbp+68h]
0x180009d88  jnb     loc_180009FB7
0x180009d8e  mov     rdx, [rbp+60h]
0x180009d92  lea     r8, [rsi+rax*8]
0x180009d96  mov     ecx, eax
0x180009d98  cmp     qword ptr [rdx+r8*8+10h], 0
0x180009d9e  jz      short loc_180009DA7
0x180009da0  cmp     qword ptr [rdx+r8*8], 0
0x180009da5  jnz     short loc_180009DAB
0x180009da7  inc     eax
0x180009da9  jmp     short loc_180009D85
0x180009dab  shl     rcx, 6
0x180009daf  lea     rbx, [rcx+rdx]
0x180009db3  test    rbx, rbx
0x180009db6  jz      loc_180009FB7
0x180009dbc  mov     rcx, [rdi+50h]
0x180009dc0  xor     r14d, r14d
0x180009dc3  mov     rdx, [rbx+rsi*8]
0x180009dc7  mov     rcx, [rcx+30h]
0x180009dcb  call    cs:__imp__o__stricmp
0x180009dd1  test    eax, eax
0x180009dd3  jz      short loc_180009E29
0x180009dd5  mov     rcx, [rbx+rsi*8]; char *
0x180009dd9  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180009dde  mov     r14, rax
0x180009de1  test    rax, rax
0x180009de4  jnz     short loc_180009E29
0x180009de6  mov     ebx, 8007000Eh
0x180009deb  mov     esi, ebx
0x180009ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180009df4  lea     rdi, WPP_GLOBAL_Control
0x180009dfb  cmp     rcx, rdi
0x180009dfe  jz      loc_180009FB3
0x180009e04  test    byte ptr [rcx+1Ch], 1
0x180009e08  jz      loc_180009F29
0x180009e0e  mov     rcx, [rcx+10h]
0x180009e12  lea     edx, [rax+32h]
0x180009e15  mov     r9d, ebx
0x180009e18  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009e1f  call    WPP_SF_d
0x180009e24  jmp     loc_180009F22
0x180009e29  mov     rcx, [rdi+50h]
0x180009e2d  mov     rdx, [rbx+rsi*8+10h]
0x180009e32  mov     rcx, [rcx]
0x180009e35  call    cs:__imp__o__stricmp
0x180009e3b  test    eax, eax
0x180009e3d  jz      short loc_180009E7E
0x180009e3f  mov     rcx, [rbx+rsi*8+10h]; char *
0x180009e44  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180009e49  mov     rbp, rax
0x180009e4c  test    rax, rax
0x180009e4f  jnz     short loc_180009E80
0x180009e51  mov     ebx, 8007000Eh
0x180009e56  mov     esi, ebx
0x180009e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e5f  lea     rdi, WPP_GLOBAL_Control
0x180009e66  cmp     rcx, rdi
0x180009e69  jz      loc_180009EFF
0x180009e6f  test    byte ptr [rcx+1Ch], 1
0x180009e73  jz      loc_180009EFF
0x180009e79  lea     edx, [rax+33h]
0x180009e7c  jmp     short loc_180009EE5
0x180009e7e  xor     ebp, ebp
0x180009e80  mov     rdx, [rbx+rsi*8+20h]
0x180009e85  xor     r15d, r15d
0x180009e88  test    rdx, rdx
0x180009e8b  jz      loc_180009F52
0x180009e91  mov     rcx, [rdi+30h]
0x180009e95  test    rcx, rcx
0x180009e98  jz      loc_180009F52
0x180009e9e  call    cs:__imp__o__stricmp
0x180009ea4  test    eax, eax
0x180009ea6  jz      loc_180009F52
0x180009eac  mov     rcx, [rbx+rsi*8+20h]; char *
0x180009eb1  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180009eb6  mov     r15, rax
0x180009eb9  test    rax, rax
0x180009ebc  jnz     loc_180009F52
0x180009ec2  mov     ebx, 8007000Eh
0x180009ec7  mov     esi, ebx
0x180009ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ed0  lea     rdi, WPP_GLOBAL_Control
0x180009ed7  cmp     rcx, rdi
0x180009eda  jz      short loc_180009EFF
0x180009edc  test    byte ptr [rcx+1Ch], 1
0x180009ee0  jz      short loc_180009EFF
0x180009ee2  lea     edx, [rax+34h]
0x180009ee5  mov     rcx, [rcx+10h]
0x180009ee9  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009ef0  mov     r9d, ebx
0x180009ef3  call    WPP_SF_d
0x180009ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eff  test    r14, r14
0x180009f02  jz      short loc_180009F14
0x180009f04  mov     rcx, r14; Block
0x180009f07  call    cs:__imp_free
0x180009f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f14  test    rbp, rbp
0x180009f17  jz      short loc_180009F29
0x180009f19  mov     rcx, rbp; Block
0x180009f1c  call    cs:__imp_free
0x180009f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f29  cmp     rcx, rdi
0x180009f2c  jz      loc_180009FB3
0x180009f32  test    byte ptr [rcx+1Ch], 1
0x180009f36  jz      short loc_180009FB3
0x180009f38  mov     rcx, [rcx+10h]
0x180009f3c  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009f43  mov     edx, 35h ; '5'
0x180009f48  mov     r9d, ebx
0x180009f4b  call    WPP_SF_d
0x180009f50  jmp     short loc_180009FB3
0x180009f52  xor     esi, esi
0x180009f54  test    r14, r14
0x180009f57  jz      short loc_180009F77
0x180009f59  mov     rcx, [rdi+50h]
0x180009f5d  mov     rcx, [rcx+30h]; Block
0x180009f61  call    cs:__imp_free
0x180009f67  mov     rax, [rdi+50h]
0x180009f6b  mov     [rax+30h], rsi
0x180009f6f  mov     rax, [rdi+50h]
0x180009f73  mov     [rax+30h], r14
0x180009f77  test    rbp, rbp
0x180009f7a  jz      short loc_180009F97
0x180009f7c  mov     rcx, [rdi+50h]
0x180009f80  mov     rcx, [rcx]; Block
0x180009f83  call    cs:__imp_free
0x180009f89  mov     rax, [rdi+50h]
0x180009f8d  mov     [rax], rsi
0x180009f90  mov     rax, [rdi+50h]
0x180009f94  mov     [rax], rbp
0x180009f97  test    r15, r15
0x180009f9a  jz      short loc_180009FAA
0x180009f9c  mov     rcx, [rdi+30h]; Block
0x180009fa0  call    cs:__imp_free
0x180009fa6  mov     [rdi+30h], r15
0x180009faa  movups  xmm0, xmmword ptr [rbx+30h]
0x180009fae  movdqu  xmmword ptr [rdi+20h], xmm0
0x180009fb3  mov     eax, esi
0x180009fb5  jmp     short loc_180009FBC
0x180009fb7  mov     eax, 80070057h
0x180009fbc  add     rsp, 38h
0x180009fc0  pop     r15
0x180009fc2  pop     r14
0x180009fc4  pop     rdi
0x180009fc5  pop     rsi
0x180009fc6  pop     rbp
0x180009fc7  pop     rbx
0x180009fc8  retn
```
