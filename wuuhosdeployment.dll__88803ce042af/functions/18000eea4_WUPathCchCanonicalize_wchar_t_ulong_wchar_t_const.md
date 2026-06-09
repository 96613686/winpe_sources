# WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)

- ea: `0x18000eea4`
- end: `0x18000f1d7`
- name: `?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z`
- size: `819`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18000f27c`

## callees

- `0x180003950`
- `0x180005f64`
- `0x180009c1c`
- `0x18000a6d0`
- `0x18000ee4c`
- `0x18000eea4`
- `0x18000f590`
- `0x1800446b8`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000f054`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000f094`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000f054`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000f094`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000efac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000efac`

## string_xrefs

- `0x18000f1c4`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

## pseudocode

```c
__int64 __fastcall WUPathCchCanonicalize(wchar_t *a1, unsigned int a2, const wchar_t *a3)
{
  unsigned __int64 v3; // r13
  wchar_t *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // edi
  int v10; // eax
  unsigned __int64 v11; // r9
  const wchar_t *i; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // r12
  wchar_t *v15; // rsi
  wchar_t *v16; // r15
  unsigned int IsUNCW; // edi
  wchar_t *v18; // rbp
  __int64 v19; // rax
  __int64 v20; // rbp
  wchar_t *v21; // r15
  wchar_t *v22; // rax
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned __int64 *v27; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v28; // [rsp+28h] [rbp-60h]
  unsigned int v29; // [rsp+30h] [rbp-58h]
  unsigned int v30; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = a2;
  v6 = 0;
  if ( !a1 )
  {
    v7 = 63;
LABEL_11:
    v9 = -2147024809;
    goto LABEL_74;
  }
  if ( !a2 )
  {
    v7 = 64;
    goto LABEL_11;
  }
  if ( !a3 )
  {
    v7 = 65;
    goto LABEL_11;
  }
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( a2 < (int)v8 + 1 )
  {
    v7 = 66;
    goto LABEL_11;
  }
  if ( !*a3 )
  {
    *a1 = 0;
    v9 = 0;
    goto LABEL_76;
  }
  v6 = (wchar_t *)SafeSusAllocArray(a2, 2u);
  v9 = v6 == 0 ? 0x8007000E : 0;
  if ( !v6 )
  {
    v7 = 78;
    goto LABEL_74;
  }
  v10 = StringCchCopyExW(v6, v3, a3, 0, 0, 0x1100u);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v7 = 80;
    goto LABEL_75;
  }
  for ( i = v6; ; i = v13 )
  {
    v13 = wcschr(i, 0x2Fu);
    if ( !v13 )
      break;
    *v13 = 92;
  }
  *a1 = 0;
  v14 = &a1[v3 - 1];
  v15 = v6;
  v16 = a1;
  IsUNCW = PathIsUNCW(a3);
  v30 = IsUNCW;
  if ( !*v6 )
  {
LABEL_65:
    WUNearRootFixupsW(a1, (unsigned int)v3, IsUNCW);
    v9 = 0;
    goto LABEL_66;
  }
  v9 = 0;
  while ( v16 < v14 )
  {
    *v16 = 0;
    v18 = wcschr(v15, 0x5Cu);
    if ( !v18 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v15[v19] );
      v18 = &v15[v19];
    }
    v20 = v18 - v15;
    if ( (_DWORD)v20 )
    {
      switch ( (_DWORD)v20 )
      {
        case 1:
          if ( *v15 == 46 )
          {
            if ( v15[1] )
            {
              v15 += 2;
              goto LABEL_63;
            }
            ++v15;
            if ( v16 <= a1 || PathIsRootW(a1) )
              goto LABEL_63;
            --v16;
            goto LABEL_62;
          }
          break;
        case 2:
          if ( *v15 == 46 && v15[1] == 46 )
          {
            if ( PathIsRootW(a1) )
            {
              if ( v15[2] == 92 )
                ++v15;
              v9 = 0;
            }
            else
            {
              v9 = 0;
              v21 = v16 - 1;
              v22 = 0;
              if ( v21 > a1 )
              {
                v23 = a1;
                if ( !v21 )
                {
                  v24 = -1;
                  do
                    ++v24;
                  while ( a1[v24] );
                  v21 = &a1[v24];
                }
                if ( a1 < v21 )
                {
                  do
                  {
                    if ( *v23 == 92 )
                      v22 = v23;
                    ++v23;
                  }
                  while ( v23 < v21 );
                }
              }
              v16 = a1;
              if ( v22 )
                v16 = v22;
            }
            v15 += 2;
            goto LABEL_62;
          }
          break;
        case 0xFFFFFFFF:
          WUNearRootFixupsW(a1, (unsigned int)v3, v30);
          goto LABEL_76;
      }
    }
    else if ( *v15 == 92 )
    {
      if ( v16 + 1 > v14 )
      {
        v7 = 129;
        goto LABEL_73;
      }
      *v16 = v20 + 92;
      ++v15;
      ++v16;
      goto LABEL_63;
    }
    v9 = StringCchCopyNExW(v16, (unsigned int)(v14 - v16) + 1, v15, (unsigned int)(v20 + 1), (wchar_t **)v27, v28, v29);
    if ( (v9 & 0x80000000) != 0 )
    {
      v7 = 197;
      goto LABEL_74;
    }
    v25 = 2LL * (unsigned int)v20;
    v16 = (wchar_t *)((char *)v16 + v25);
    v15 = (wchar_t *)((char *)v15 + v25);
    v9 = 0;
LABEL_62:
    if ( v16 > v14 )
    {
      v7 = 209;
      goto LABEL_73;
    }
LABEL_63:
    *v16 = 0;
    if ( !*v15 )
    {
      IsUNCW = v30;
      goto LABEL_65;
    }
  }
  v7 = 106;
LABEL_73:
  a1[(unsigned int)(v3 - 1)] = 0;
  v9 = -2147024774;
LABEL_74:
  v11 = v9;
LABEL_75:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
    (const char *)v11,
    (int)v27);
LABEL_76:
  if ( v6 )
LABEL_66:
    CSusBaseAllocTag<942762101>::operator delete(v6);
  return v9;
}

```

## disassembly

```asm
0x18000eea4  mov     [rsp+arg_18], rbx
0x18000eea9  push    rbp
0x18000eeaa  push    rsi
0x18000eeab  push    rdi
0x18000eeac  push    r12
0x18000eeae  push    r13
0x18000eeb0  push    r14
0x18000eeb2  push    r15
0x18000eeb4  sub     rsp, 50h
0x18000eeb8  xor     esi, esi
0x18000eeba  mov     r13d, edx
0x18000eebd  mov     rbp, r8
0x18000eec0  mov     r14, rcx
0x18000eec3  mov     ebx, esi
0x18000eec5  test    rcx, rcx
0x18000eec8  jnz     short loc_18000EECF
0x18000eeca  lea     edx, [rcx+3Fh]
0x18000eecd  jmp     short loc_18000EEFE
0x18000eecf  test    edx, edx
0x18000eed1  jnz     short loc_18000EEDA
0x18000eed3  mov     edx, 40h ; '@'
0x18000eed8  jmp     short loc_18000EEFE
0x18000eeda  test    rbp, rbp
0x18000eedd  jnz     short loc_18000EEE4
0x18000eedf  lea     edx, [rbp+41h]
0x18000eee2  jmp     short loc_18000EEFE
0x18000eee4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eee8  inc     rax
0x18000eeeb  cmp     [r8+rax*2], si
0x18000eef0  jnz     short loc_18000EEE8
0x18000eef2  inc     eax
0x18000eef4  cmp     r13d, eax
0x18000eef7  jnb     short loc_18000EF08
0x18000eef9  mov     edx, 42h ; 'B'
0x18000eefe  mov     edi, 80070057h
0x18000ef03  jmp     loc_18000F1B9
0x18000ef08  cmp     [r8], si
0x18000ef0c  jnz     short loc_18000EF18
0x18000ef0e  mov     [rcx], si
0x18000ef11  mov     edi, esi
0x18000ef13  jmp     loc_18000F1D0
0x18000ef18  mov     edx, 2; unsigned __int64
0x18000ef1d  mov     rcx, r13; unsigned __int64
0x18000ef20  mov     r12, r13
0x18000ef23  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000ef28  mov     rbx, rax
0x18000ef2b  neg     rax
0x18000ef2e  sbb     edi, edi
0x18000ef30  not     edi
0x18000ef32  and     edi, 8007000Eh
0x18000ef38  test    rbx, rbx
0x18000ef3b  jnz     short loc_18000EF45
0x18000ef3d  lea     edx, [rbx+4Eh]
0x18000ef40  jmp     loc_18000F1B9
0x18000ef45  mov     dword ptr [rsp+88h+var_60], 1100h; unsigned int
0x18000ef4d  xor     r9d, r9d; wchar_t **
0x18000ef50  mov     r8, rbp; wchar_t *
0x18000ef53  mov     [rsp+88h+var_68], rsi; unsigned __int64 *
0x18000ef58  mov     rdx, r13; unsigned __int64
0x18000ef5b  mov     rcx, rbx; pszDest
0x18000ef5e  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000ef63  mov     edi, eax
0x18000ef65  test    eax, eax
0x18000ef67  jns     short loc_18000EF76
0x18000ef69  mov     r9d, eax
0x18000ef6c  mov     edx, 50h ; 'P'
0x18000ef71  jmp     loc_18000F1BC
0x18000ef76  mov     edi, 2Fh ; '/'
0x18000ef7b  mov     rcx, rbx
0x18000ef7e  jmp     short loc_18000EF88
0x18000ef80  mov     word ptr [rax], 5Ch ; '\'
0x18000ef85  mov     rcx, rax; Str
0x18000ef88  mov     edx, edi; Ch
0x18000ef8a  call    wcschr
0x18000ef8f  test    rax, rax
0x18000ef92  jnz     short loc_18000EF80
0x18000ef94  xor     ecx, ecx
0x18000ef96  lea     r12, [r12-1]
0x18000ef9b  mov     [r14], cx
0x18000ef9f  lea     r12, [r14+r12*2]
0x18000efa3  mov     rcx, rbp; pszPath
0x18000efa6  mov     rsi, rbx
0x18000efa9  mov     r15, r14
0x18000efac  call    cs:__imp_PathIsUNCW
0x18000efb2  mov     edi, eax
0x18000efb4  mov     [rsp+88h+var_48], eax
0x18000efb8  xor     eax, eax
0x18000efba  cmp     [rbx], ax
0x18000efbd  jz      loc_18000F14B
0x18000efc3  xor     edi, edi
0x18000efc5  cmp     r15, r12
0x18000efc8  jnb     loc_18000F1A6
0x18000efce  mov     edx, 5Ch ; '\'; Ch
0x18000efd3  mov     [r15], di
0x18000efd7  mov     rcx, rsi; Str
0x18000efda  call    wcschr
0x18000efdf  mov     rbp, rax
0x18000efe2  test    rax, rax
0x18000efe5  jnz     short loc_18000EFF8
0x18000efe7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efeb  inc     rax
0x18000efee  cmp     [rsi+rax*2], di
0x18000eff2  jnz     short loc_18000EFEB
0x18000eff4  lea     rbp, [rsi+rax*2]
0x18000eff8  sub     rbp, rsi
0x18000effb  sar     rbp, 1
0x18000effe  lea     eax, [rbp+1]
0x18000f001  cmp     eax, 1
0x18000f004  jnz     short loc_18000F02F
0x18000f006  lea     ecx, [rax+5Bh]
0x18000f009  cmp     [rsi], cx
0x18000f00c  jnz     loc_18000F109
0x18000f012  lea     rax, [r15+2]
0x18000f016  cmp     rax, r12
0x18000f019  ja      loc_18000F17F
0x18000f01f  mov     [r15], cx
0x18000f023  add     rsi, 2
0x18000f027  mov     r15, rax
0x18000f02a  jmp     loc_18000F13A
0x18000f02f  cmp     eax, 2
0x18000f032  jnz     short loc_18000F074
0x18000f034  cmp     word ptr [rsi], 2Eh ; '.'
0x18000f038  jnz     loc_18000F109
0x18000f03e  cmp     [rsi+2], di
0x18000f042  jnz     short loc_18000F06B
0x18000f044  add     rsi, 2
0x18000f048  cmp     r15, r14
0x18000f04b  jbe     loc_18000F13A
0x18000f051  mov     rcx, r14; pszPath
0x18000f054  call    cs:__imp_PathIsRootW
0x18000f05a  test    eax, eax
0x18000f05c  jnz     loc_18000F13A
0x18000f062  sub     r15, 2
0x18000f066  jmp     loc_18000F135
0x18000f06b  add     rsi, 4
0x18000f06f  jmp     loc_18000F13A
0x18000f074  cmp     eax, 3
0x18000f077  jnz     loc_18000F100
0x18000f07d  cmp     word ptr [rsi], 2Eh ; '.'
0x18000f081  jnz     loc_18000F109
0x18000f087  lea     rdi, [rsi+2]
0x18000f08b  cmp     word ptr [rdi], 2Eh ; '.'
0x18000f08f  jnz     short loc_18000F109
0x18000f091  mov     rcx, r14; pszPath
0x18000f094  call    cs:__imp_PathIsRootW
0x18000f09a  test    eax, eax
0x18000f09c  jnz     short loc_18000F0EB
0x18000f09e  xor     edi, edi
0x18000f0a0  add     r15, 0FFFFFFFFFFFFFFFEh
0x18000f0a4  mov     eax, edi
0x18000f0a6  cmp     r15, r14
0x18000f0a9  jbe     short loc_18000F0DF
0x18000f0ab  mov     rcx, r14
0x18000f0ae  test    r15, r15
0x18000f0b1  jnz     short loc_18000F0C5
0x18000f0b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f0b7  inc     rdx
0x18000f0ba  cmp     [r14+rdx*2], di
0x18000f0bf  jnz     short loc_18000F0B7
0x18000f0c1  lea     r15, [r14+rdx*2]
0x18000f0c5  cmp     r14, r15
0x18000f0c8  jnb     short loc_18000F0DF
0x18000f0ca  mov     edx, 5Ch ; '\'
0x18000f0cf  cmp     [rcx], dx
0x18000f0d2  cmovz   rax, rcx
0x18000f0d6  add     rcx, 2
0x18000f0da  cmp     rcx, r15
0x18000f0dd  jb      short loc_18000F0CF
0x18000f0df  test    rax, rax
0x18000f0e2  mov     r15, r14
0x18000f0e5  cmovnz  r15, rax
0x18000f0e9  jmp     short loc_18000F0FA
0x18000f0eb  mov     eax, 5Ch ; '\'
0x18000f0f0  cmp     [rsi+4], ax
0x18000f0f4  cmovz   rsi, rdi
0x18000f0f8  xor     edi, edi
0x18000f0fa  add     rsi, 4
0x18000f0fe  jmp     short loc_18000F135
0x18000f100  cmp     eax, 1
0x18000f103  jb      loc_18000F194
0x18000f109  mov     rdx, r12
0x18000f10c  mov     r9d, eax; unsigned __int64
0x18000f10f  sub     rdx, r15
0x18000f112  mov     r8, rsi; wchar_t *
0x18000f115  sar     rdx, 1
0x18000f118  mov     rcx, r15; wchar_t *
0x18000f11b  inc     edx; unsigned __int64
0x18000f11d  call    ?StringCchCopyNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCopyNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x18000f122  mov     edi, eax
0x18000f124  test    eax, eax
0x18000f126  js      short loc_18000F18D
0x18000f128  mov     eax, ebp
0x18000f12a  add     rax, rax
0x18000f12d  add     r15, rax
0x18000f130  add     rsi, rax
0x18000f133  xor     edi, edi
0x18000f135  cmp     r15, r12
0x18000f138  ja      short loc_18000F186
0x18000f13a  mov     [r15], di
0x18000f13e  cmp     [rsi], di
0x18000f141  jnz     loc_18000EFC5
0x18000f147  mov     edi, [rsp+88h+var_48]
0x18000f14b  mov     r8d, edi
0x18000f14e  mov     edx, r13d
0x18000f151  mov     rcx, r14
0x18000f154  call    WUNearRootFixupsW
0x18000f159  xor     eax, eax
0x18000f15b  mov     edi, eax
0x18000f15d  mov     rcx, rbx; lpMem
0x18000f160  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18000f165  mov     rbx, [rsp+88h+arg_18]
0x18000f16d  mov     eax, edi
0x18000f16f  add     rsp, 50h
0x18000f173  pop     r15
0x18000f175  pop     r14
0x18000f177  pop     r13
0x18000f179  pop     r12
0x18000f17b  pop     rdi
0x18000f17c  pop     rsi
0x18000f17d  pop     rbp
0x18000f17e  retn
0x18000f17f  mov     edx, 81h
0x18000f184  jmp     short loc_18000F1AB
0x18000f186  mov     edx, 0D1h
0x18000f18b  jmp     short loc_18000F1AB
0x18000f18d  mov     edx, 0C5h
0x18000f192  jmp     short loc_18000F1B9
0x18000f194  mov     r8d, [rsp+88h+var_48]
0x18000f199  mov     edx, r13d
0x18000f19c  mov     rcx, r14
0x18000f19f  call    WUNearRootFixupsW
0x18000f1a4  jmp     short loc_18000F1D0
0x18000f1a6  mov     edx, 6Ah ; 'j'; void *
0x18000f1ab  lea     eax, [r13-1]
0x18000f1af  mov     [r14+rax*2], di
0x18000f1b4  mov     edi, 8007007Ah
0x18000f1b9  mov     r9d, edi; char *
0x18000f1bc  mov     rcx, [rsp+88h]; this
0x18000f1c4  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000f1cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f1d0  test    rbx, rbx
0x18000f1d3  jz      short loc_18000F165
0x18000f1d5  jmp     short loc_18000F15D
```
