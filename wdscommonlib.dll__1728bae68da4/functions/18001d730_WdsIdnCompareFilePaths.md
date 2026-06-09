# WdsIdnCompareFilePaths

- ea: `0x18001d730`
- end: `0x18001da9b`
- name: `WdsIdnCompareFilePaths`
- size: `875`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800172b0`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001d730`
- `0x180025a80`
- `0x180025c20`
- `0x180025ce0`
- `0x18002a950`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d9b8`
- `msvcrt!_wcsicmp` at `0x18001d9b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da16`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da52`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da66`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da16`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da52`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001da66`
- `SHLWAPI!PathIsUNCW` at `0x18001d7b3`
- `SHLWAPI!PathIsUNCW` at `0x18001d7cb`
- `SHLWAPI!PathIsUNCW` at `0x18001d7b3`
- `SHLWAPI!PathIsUNCW` at `0x18001d7cb`

## pseudocode

```c
__int64 __fastcall WdsIdnCompareFilePaths(LPCWSTR pszPath, const WCHAR *a2, int *a3)
{
  unsigned int v3; // ebx
  WCHAR *v4; // rsi
  WCHAR *v5; // rdi
  void *v6; // r14
  void *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // eax
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rcx
  LPCWSTR v32; // [rsp+38h] [rbp-59h] BYREF
  LPCWSTR lpUnicodeCharStr; // [rsp+40h] [rbp-51h] BYREF
  void *v34; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 *v35; // [rsp+50h] [rbp-41h]
  unsigned __int16 *v36; // [rsp+58h] [rbp-39h]
  unsigned __int16 *v37[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v38; // [rsp+70h] [rbp-21h]
  int v39; // [rsp+78h] [rbp-19h]
  unsigned __int16 *v40[2]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v41; // [rsp+90h] [rbp-1h]
  int v42; // [rsp+98h] [rbp+7h]
  void *v46; // [rsp+110h] [rbp+7Fh] BYREF

  v41 = 0;
  v3 = 0;
  v38 = 0;
  *(_OWORD *)v40 = 0;
  lpUnicodeCharStr = 0;
  v42 = 4;
  v4 = 0;
  v39 = 4;
  v5 = 0;
  v32 = 0;
  *(_OWORD *)v37 = 0;
  v35 = 0;
  v36 = 0;
  v6 = 0;
  v7 = 0;
  v46 = 0;
  v34 = 0;
  if ( !PathIsUNCW(pszPath) || !PathIsUNCW(a2) )
  {
    v29 = a2;
    v30 = pszPath;
    goto LABEL_24;
  }
  v3 = CTokenString::Initialize(v40, pszPath, L"\\", 0);
  if ( (unsigned int)ElValidateWin32_8(v3, v8, v9, 4942) )
    goto LABEL_37;
  v3 = CTokenString::Initialize(v37, a2, L"\\", 0);
  if ( (unsigned int)ElValidateWin32_8(v3, v10, v11, 4945) )
    goto LABEL_37;
  v3 = CTokenString::GetAt((CTokenString *)v40, 1u, (unsigned __int16 **)&lpUnicodeCharStr);
  if ( (unsigned int)ElValidateWin32_8(v3, v12, v13, 4951) )
  {
    v4 = (WCHAR *)lpUnicodeCharStr;
  }
  else
  {
    v3 = CTokenString::GetAt((CTokenString *)v37, 1u, (unsigned __int16 **)&v32);
    v16 = ElValidateWin32_8(v3, v14, v15, 4954);
    v4 = (WCHAR *)lpUnicodeCharStr;
    if ( v16 )
    {
      v5 = (WCHAR *)v32;
    }
    else
    {
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( lpUnicodeCharStr[v18] );
      v19 = WcsDup(&pszPath[v18 + 3]);
      v5 = (WCHAR *)v32;
      v35 = v19;
      if ( !v19 )
        goto LABEL_10;
      do
        ++v17;
      while ( v32[v17] );
      v36 = WcsDup(&a2[v17 + 3]);
      if ( v36 )
      {
        v3 = WdsIdnToAscii(1u, v4);
        if ( (unsigned int)ElValidateWin32_8(v3, v20, v21, 4973) )
          goto LABEL_25;
        v3 = WdsIdnToAscii(1u, v5);
        if ( (unsigned int)ElValidateWin32_8(v3, v22, v23, 4978) )
          goto LABEL_25;
        v3 = ConcatenatePaths(0, v35, &v46);
        if ( (unsigned int)ElValidateWin32_8(v3, v24, v25, 4987) )
        {
          v6 = v46;
        }
        else
        {
          v3 = ConcatenatePaths(0, v36, &v34);
          v28 = ElValidateWin32_8(v3, v26, v27, 4992);
          v7 = v34;
          v6 = v46;
          if ( !v28 )
          {
            v29 = (const wchar_t *)v34;
            v30 = (const wchar_t *)v46;
LABEL_24:
            *a3 = _wcsicmp(v30, v29);
          }
        }
      }
      else
      {
LABEL_10:
        v3 = 8;
      }
    }
  }
LABEL_25:
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  if ( v35 )
    operator delete(v35);
  if ( v36 )
    operator delete(v36);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
LABEL_37:
  CTokenString::Shutdown((CTokenString *)v37);
  CTokenString::Shutdown((CTokenString *)v40);
  return v3;
}

```

## disassembly

```asm
0x18001d730  mov     rax, rsp
0x18001d733  mov     [rax+18h], r8
0x18001d737  mov     [rax+10h], rdx
0x18001d73b  mov     [rax+8], rcx
0x18001d73f  push    rbp
0x18001d740  push    rbx
0x18001d741  push    rsi
0x18001d742  push    rdi
0x18001d743  push    r12
0x18001d745  push    r13
0x18001d747  push    r14
0x18001d749  push    r15
0x18001d74b  lea     rbp, [rax-5Fh]
0x18001d74f  sub     rsp, 0A8h
0x18001d756  xor     r8d, r8d
0x18001d759  mov     rax, rcx
0x18001d75c  xorps   xmm0, xmm0
0x18001d75f  mov     [rbp+57h+var_58], r8
0x18001d763  mov     ebx, r8d
0x18001d766  mov     [rbp+57h+var_78], r8
0x18001d76a  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18001d76f  lea     ecx, [r8+4]
0x18001d773  mov     [rbp+57h+lpUnicodeCharStr], r8
0x18001d777  mov     [rbp+57h+var_50], ecx
0x18001d77a  mov     esi, r8d
0x18001d77d  mov     [rbp+57h+var_70], ecx
0x18001d780  mov     edi, r8d
0x18001d783  mov     rcx, rax; pszPath
0x18001d786  mov     [rbp+57h+var_B0], r8
0x18001d78a  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18001d78f  mov     [rbp+57h+var_98], r8
0x18001d793  mov     r12d, r8d
0x18001d796  mov     [rbp+57h+var_90], r8
0x18001d79a  mov     r15d, r8d
0x18001d79d  mov     [rbp+57h+var_B8], r8
0x18001d7a1  mov     r14d, r8d
0x18001d7a4  mov     [rbp+57h+var_C0], r8
0x18001d7a8  mov     r13d, r8d
0x18001d7ab  mov     [rbp+57h+arg_18], r8
0x18001d7af  mov     [rbp+57h+var_A0], r8
0x18001d7b3  call    cs:__imp_PathIsUNCW
0x18001d7ba  nop     dword ptr [rax+rax+00h]
0x18001d7bf  test    eax, eax
0x18001d7c1  jz      loc_18001D9B0
0x18001d7c7  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18001d7cb  call    cs:__imp_PathIsUNCW
0x18001d7d2  nop     dword ptr [rax+rax+00h]
0x18001d7d7  test    eax, eax
0x18001d7d9  jz      loc_18001D9B0
0x18001d7df  mov     rdx, [rbp+57h+String1]; unsigned __int16 *
0x18001d7e3  lea     r8, SubBlock; "\\"
0x18001d7ea  xor     r9d, r9d; unsigned int
0x18001d7ed  lea     rcx, [rbp+57h+var_68]; this
0x18001d7f1  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001d7f6  mov     r9d, 134Eh
0x18001d7fc  mov     ecx, eax
0x18001d7fe  mov     ebx, eax
0x18001d800  call    ElValidateWin32_8
0x18001d805  test    eax, eax
0x18001d807  jnz     loc_18001DA72
0x18001d80d  mov     rdx, [rbp+57h+pszPath]; unsigned __int16 *
0x18001d811  lea     r8, SubBlock; "\\"
0x18001d818  xor     r9d, r9d; unsigned int
0x18001d81b  lea     rcx, [rbp+57h+var_88]; this
0x18001d81f  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001d824  mov     r9d, 1351h
0x18001d82a  mov     ecx, eax
0x18001d82c  mov     ebx, eax
0x18001d82e  call    ElValidateWin32_8
0x18001d833  test    eax, eax
0x18001d835  jnz     loc_18001DA72
0x18001d83b  lea     r8, [rbp+57h+lpUnicodeCharStr]; unsigned __int16 **
0x18001d83f  lea     edx, [rax+1]; unsigned int
0x18001d842  lea     rcx, [rbp+57h+var_68]; this
0x18001d846  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001d84b  mov     r9d, 1357h
0x18001d851  mov     ecx, eax
0x18001d853  mov     ebx, eax
0x18001d855  call    ElValidateWin32_8
0x18001d85a  test    eax, eax
0x18001d85c  jnz     loc_18001D9AA
0x18001d862  lea     r8, [rbp+57h+var_B0]; unsigned __int16 **
0x18001d866  lea     edx, [rax+1]; unsigned int
0x18001d869  lea     rcx, [rbp+57h+var_88]; this
0x18001d86d  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001d872  mov     r9d, 135Ah
0x18001d878  mov     ecx, eax
0x18001d87a  mov     ebx, eax
0x18001d87c  call    ElValidateWin32_8
0x18001d881  mov     rsi, [rbp+57h+lpUnicodeCharStr]
0x18001d885  test    eax, eax
0x18001d887  jnz     loc_18001D9A4
0x18001d88d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001d891  mov     rax, rbx
0x18001d894  inc     rax
0x18001d897  cmp     [rsi+rax*2], di
0x18001d89b  jnz     short loc_18001D894
0x18001d89d  mov     rcx, [rbp+57h+String1]
0x18001d8a1  lea     rcx, [rcx+rax*2]
0x18001d8a5  add     rcx, 6; Src
0x18001d8a9  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18001d8ae  mov     rdi, [rbp+57h+var_B0]
0x18001d8b2  mov     [rbp+57h+var_98], rax
0x18001d8b6  test    rax, rax
0x18001d8b9  jnz     short loc_18001D8C5
0x18001d8bb  mov     ebx, 8
0x18001d8c0  jmp     loc_18001D9CA
0x18001d8c5  xor     eax, eax
0x18001d8c7  inc     rbx
0x18001d8ca  cmp     [rdi+rbx*2], ax
0x18001d8ce  jnz     short loc_18001D8C7
0x18001d8d0  mov     rcx, [rbp+57h+pszPath]
0x18001d8d4  add     rcx, 6
0x18001d8d8  lea     rcx, [rcx+rbx*2]; Src
0x18001d8dc  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18001d8e1  mov     [rbp+57h+var_90], rax
0x18001d8e5  test    rax, rax
0x18001d8e8  jz      short loc_18001D8BB
0x18001d8ea  lea     r8, [rbp+57h+var_B8]
0x18001d8ee  mov     rdx, rsi; lpUnicodeCharStr
0x18001d8f1  mov     ecx, 1; dwFlags
0x18001d8f6  call    WdsIdnToAscii
0x18001d8fb  mov     r9d, 136Dh
0x18001d901  mov     ecx, eax
0x18001d903  mov     ebx, eax
0x18001d905  call    ElValidateWin32_8
0x18001d90a  test    eax, eax
0x18001d90c  jnz     loc_18001D99E
0x18001d912  lea     r8, [rbp+57h+var_C0]
0x18001d916  mov     rdx, rdi; lpUnicodeCharStr
0x18001d919  lea     ecx, [rax+1]; dwFlags
0x18001d91c  call    WdsIdnToAscii
0x18001d921  mov     r9d, 1372h
0x18001d927  mov     ecx, eax
0x18001d929  mov     ebx, eax
0x18001d92b  call    ElValidateWin32_8
0x18001d930  mov     r12, [rbp+57h+var_B8]
0x18001d934  test    eax, eax
0x18001d936  jnz     short loc_18001D998
0x18001d938  mov     rdx, [rbp+57h+var_98]
0x18001d93c  lea     r8, [rbp+57h+arg_18]
0x18001d940  mov     rcx, r12
0x18001d943  call    ConcatenatePaths
0x18001d948  mov     r9d, 137Bh
0x18001d94e  mov     ecx, eax
0x18001d950  mov     ebx, eax
0x18001d952  call    ElValidateWin32_8
0x18001d957  mov     r15, [rbp+57h+var_C0]
0x18001d95b  test    eax, eax
0x18001d95d  jnz     short loc_18001D992
0x18001d95f  mov     rdx, [rbp+57h+var_90]
0x18001d963  lea     r8, [rbp+57h+var_A0]
0x18001d967  mov     rcx, r15
0x18001d96a  call    ConcatenatePaths
0x18001d96f  mov     r9d, 1380h
0x18001d975  mov     ecx, eax
0x18001d977  mov     ebx, eax
0x18001d979  call    ElValidateWin32_8
0x18001d97e  mov     r13, [rbp+57h+var_A0]
0x18001d982  mov     r14, [rbp+57h+arg_18]
0x18001d986  test    eax, eax
0x18001d988  jnz     short loc_18001D9CA
0x18001d98a  mov     rdx, r13
0x18001d98d  mov     rcx, r14
0x18001d990  jmp     short loc_18001D9B8
0x18001d992  mov     r14, [rbp+57h+arg_18]
0x18001d996  jmp     short loc_18001D9CA
0x18001d998  mov     r15, [rbp+57h+var_C0]
0x18001d99c  jmp     short loc_18001D9CA
0x18001d99e  mov     r12, [rbp+57h+var_B8]
0x18001d9a2  jmp     short loc_18001D9CA
0x18001d9a4  mov     rdi, [rbp+57h+var_B0]
0x18001d9a8  jmp     short loc_18001D9CA
0x18001d9aa  mov     rsi, [rbp+57h+lpUnicodeCharStr]
0x18001d9ae  jmp     short loc_18001D9CA
0x18001d9b0  mov     rdx, [rbp+57h+pszPath]; String2
0x18001d9b4  mov     rcx, [rbp+57h+String1]; String1
0x18001d9b8  call    cs:__imp__wcsicmp
0x18001d9bf  nop     dword ptr [rax+rax+00h]
0x18001d9c4  mov     rcx, [rbp+57h+arg_10]
0x18001d9c8  mov     [rcx], eax
0x18001d9ca  test    rsi, rsi
0x18001d9cd  jz      short loc_18001D9DE
0x18001d9cf  mov     rcx, rsi
0x18001d9d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d9d9  nop     dword ptr [rax+rax+00h]
0x18001d9de  test    rdi, rdi
0x18001d9e1  jz      short loc_18001D9F2
0x18001d9e3  mov     rcx, rdi
0x18001d9e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d9ed  nop     dword ptr [rax+rax+00h]
0x18001d9f2  mov     rax, [rbp+57h+var_98]
0x18001d9f6  test    rax, rax
0x18001d9f9  jz      short loc_18001DA0A
0x18001d9fb  mov     rcx, rax
0x18001d9fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da05  nop     dword ptr [rax+rax+00h]
0x18001da0a  mov     rax, [rbp+57h+var_90]
0x18001da0e  test    rax, rax
0x18001da11  jz      short loc_18001DA22
0x18001da13  mov     rcx, rax
0x18001da16  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da1d  nop     dword ptr [rax+rax+00h]
0x18001da22  test    r12, r12
0x18001da25  jz      short loc_18001DA36
0x18001da27  mov     rcx, r12
0x18001da2a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da31  nop     dword ptr [rax+rax+00h]
0x18001da36  test    r15, r15
0x18001da39  jz      short loc_18001DA4A
0x18001da3b  mov     rcx, r15
0x18001da3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da45  nop     dword ptr [rax+rax+00h]
0x18001da4a  test    r14, r14
0x18001da4d  jz      short loc_18001DA5E
0x18001da4f  mov     rcx, r14
0x18001da52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da59  nop     dword ptr [rax+rax+00h]
0x18001da5e  test    r13, r13
0x18001da61  jz      short loc_18001DA72
0x18001da63  mov     rcx, r13
0x18001da66  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001da6d  nop     dword ptr [rax+rax+00h]
0x18001da72  lea     rcx, [rbp+57h+var_88]; this
0x18001da76  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001da7b  lea     rcx, [rbp+57h+var_68]; this
0x18001da7f  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001da84  mov     eax, ebx
0x18001da86  add     rsp, 0A8h
0x18001da8d  pop     r15
0x18001da8f  pop     r14
0x18001da91  pop     r13
0x18001da93  pop     r12
0x18001da95  pop     rdi
0x18001da96  pop     rsi
0x18001da97  pop     rbx
0x18001da98  pop     rbp
0x18001da99  retn
```
