# CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18000b78c`
- end: `0x18000b9c5`
- name: `?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z`
- size: `569`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005d10`
- `0x180005ea0`
- `0x18000b6c0`
- `0x180016dd0`
- `0x1800519e0`
- `0x180051cf0`
- `0x180052590`
- `0x180053060`
- `0x180053200`

## callees

- `0x1800089c0`
- `0x18000a9a0`
- `0x18000ab10`
- `0x18000b78c`
- `0x18000d490`
- `0x18000dd60`
- `0x18000e780`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180060fac`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18000b922`
- `SHLWAPI!PathIsRelativeW` at `0x18000b922`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000b8b2`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000b8b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b96e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b96e`

## pseudocode

```c
__int64 __fastcall CThemeFile::_getThemeSetting(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned __int16 **a5)
{
  HRESULT CachedProfile; // ebx
  int v10; // eax
  struct ICachedPrivateProfile *v11; // r15
  const WCHAR *v12; // r14
  struct IUnknown *v13; // rdx
  __int64 v14; // rcx
  _WORD *v15; // rsi
  WCHAR *v16; // rax
  int v17; // edi
  __int64 v18; // r8
  struct ICachedPrivateProfile *v20; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszSource; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[264]; // [rsp+260h] [rbp+160h] BYREF

  v20 = 0;
  *a5 = 0;
  CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)this, 1, &v20);
  if ( CachedProfile >= 0 )
  {
    pszSource = 0;
    v10 = StringCchPrintfW(v23, 0x104u, L"%s.MUI", a3);
    v11 = v20;
    if ( v10 < 0
      || (CachedProfile = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const unsigned __int16 *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v20 + 48LL))(
                            v20,
                            a2,
                            v23,
                            0,
                            1,
                            &pszSource),
          CachedProfile < 0) )
    {
      CachedProfile = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v11 + 48LL))(
                        v11,
                        a2,
                        a3,
                        0,
                        1,
                        &pszSource);
      if ( CachedProfile < 0 )
        goto LABEL_24;
    }
    v12 = pszSource;
    memset_0(pszOutBuf, 0, 0x208u);
    if ( (a4 & 1) != 0 )
    {
      v15 = 0;
      CachedProfile = SHLoadIndirectString(v12, pszOutBuf, 0x104u, 0);
      if ( CachedProfile >= 0 )
      {
        CachedProfile = ExpandResourceDir(pszOutBuf, (unsigned int)v13);
        if ( CachedProfile >= 0 )
        {
          CachedProfile = ExpandThemeTokens(this[6], pszOutBuf);
          v16 = pszOutBuf;
          if ( CachedProfile < 0 )
            v16 = 0;
          v15 = v16;
        }
      }
      v17 = a4 & 2;
    }
    else
    {
      v17 = a4 & 2;
      if ( v17 )
        CachedProfile = StringCchCopyW(pszOutBuf, 0x104u, pszSource);
      v15 = v12;
    }
    if ( CachedProfile >= 0 )
    {
      if ( v17 && !PathIsRelativeW(pszOutBuf) )
      {
        LODWORD(v20) = 0;
        SHMapUrlToZoneEx(pszOutBuf, v13, v18, (unsigned int *)&v20);
        if ( pszOutBuf[0] && (_DWORD)v20 && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
        {
          *v15 = 0;
        }
        else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
        {
          CachedProfile = -2147024894;
          goto LABEL_23;
        }
      }
      CachedProfile = _AllocString<CTCoAllocPolicy>(v14, v13, v15, a5);
    }
LABEL_23:
    CoTaskMemFree((LPVOID)pszSource);
LABEL_24:
    (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)CachedProfile;
}

```

## disassembly

```asm
0x18000b78c  mov     [rsp-8+arg_18], rbx
0x18000b791  push    rbp
0x18000b792  push    rsi
0x18000b793  push    rdi
0x18000b794  push    r12
0x18000b796  push    r13
0x18000b798  push    r14
0x18000b79a  push    r15
0x18000b79c  lea     rbp, [rsp-380h]
0x18000b7a4  sub     rsp, 480h
0x18000b7ab  mov     rax, cs:__security_cookie
0x18000b7b2  xor     rax, rsp
0x18000b7b5  mov     [rbp+3B0h+var_40], rax
0x18000b7bc  mov     r12, [rbp+3B0h+arg_20]
0x18000b7c3  mov     rsi, r8
0x18000b7c6  mov     r14, rdx
0x18000b7c9  lea     r8, [rsp+4B0h+var_470]; struct ICachedPrivateProfile **
0x18000b7ce  xor     r15d, r15d
0x18000b7d1  mov     dl, 1; bool
0x18000b7d3  mov     edi, r9d
0x18000b7d6  mov     [rsp+4B0h+var_470], r15
0x18000b7db  mov     [r12], r15
0x18000b7df  mov     r13, rcx
0x18000b7e2  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x18000b7e7  mov     ebx, eax
0x18000b7e9  test    eax, eax
0x18000b7eb  js      loc_18000B983
0x18000b7f1  mov     r9, rsi
0x18000b7f4  mov     [rsp+4B0h+pszSource], r15
0x18000b7f9  lea     r8, aSMui; "%s.MUI"
0x18000b800  mov     edx, 104h; unsigned __int64
0x18000b805  lea     rcx, [rbp+3B0h+var_250]; unsigned __int16 *
0x18000b80c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b811  mov     r15, [rsp+4B0h+var_470]
0x18000b816  test    eax, eax
0x18000b818  js      short loc_18000B84E
0x18000b81a  mov     rax, [r15]
0x18000b81d  lea     rcx, [rsp+4B0h+pszSource]
0x18000b822  mov     [rsp+4B0h+var_488], rcx
0x18000b827  lea     r8, [rbp+3B0h+var_250]
0x18000b82e  xor     r9d, r9d
0x18000b831  mov     [rsp+4B0h+var_490], 1
0x18000b839  mov     rdx, r14
0x18000b83c  mov     rcx, r15
0x18000b83f  mov     rax, [rax+30h]
0x18000b843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b848  mov     ebx, eax
0x18000b84a  test    eax, eax
0x18000b84c  jns     short loc_18000B882
0x18000b84e  mov     rax, [r15]
0x18000b851  lea     rcx, [rsp+4B0h+pszSource]
0x18000b856  mov     [rsp+4B0h+var_488], rcx
0x18000b85b  xor     r9d, r9d
0x18000b85e  mov     r8, rsi
0x18000b861  mov     [rsp+4B0h+var_490], 1
0x18000b869  mov     rdx, r14
0x18000b86c  mov     rcx, r15
0x18000b86f  mov     rax, [rax+30h]
0x18000b873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b878  mov     ebx, eax
0x18000b87a  test    eax, eax
0x18000b87c  js      loc_18000B974
0x18000b882  mov     r14, [rsp+4B0h+pszSource]
0x18000b887  lea     rcx, [rsp+4B0h+pszOutBuf]; void *
0x18000b88c  xor     edx, edx; Val
0x18000b88e  mov     r8d, 208h; Size
0x18000b894  call    memset_0
0x18000b899  test    dil, 1
0x18000b89d  jz      short loc_18000B8F4
0x18000b89f  xor     r9d, r9d; ppvReserved
0x18000b8a2  lea     rdx, [rsp+4B0h+pszOutBuf]; pszOutBuf
0x18000b8a7  mov     r8d, 104h; cchOutBuf
0x18000b8ad  mov     rcx, r14; pszSource
0x18000b8b0  xor     esi, esi
0x18000b8b2  call    cs:__imp_SHLoadIndirectString
0x18000b8b8  xor     r14d, r14d
0x18000b8bb  mov     ebx, eax
0x18000b8bd  test    eax, eax
0x18000b8bf  js      short loc_18000B8EF
0x18000b8c1  lea     rcx, [rsp+4B0h+pszOutBuf]; unsigned __int16 *
0x18000b8c6  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x18000b8cb  mov     ebx, eax
0x18000b8cd  test    eax, eax
0x18000b8cf  js      short loc_18000B8EF
0x18000b8d1  mov     rcx, [r13+30h]; unsigned __int16 *
0x18000b8d5  lea     rdx, [rsp+4B0h+pszOutBuf]; unsigned __int16 *
0x18000b8da  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x18000b8df  mov     ebx, eax
0x18000b8e1  lea     rax, [rsp+4B0h+pszOutBuf]
0x18000b8e6  test    ebx, ebx
0x18000b8e8  cmovs   rax, rsi
0x18000b8ec  mov     rsi, rax
0x18000b8ef  and     edi, 2
0x18000b8f2  jmp     short loc_18000B915
0x18000b8f4  and     edi, 2
0x18000b8f7  jz      short loc_18000B90F
0x18000b8f9  mov     r8, [rsp+4B0h+pszSource]; unsigned __int16 *
0x18000b8fe  lea     rcx, [rsp+4B0h+pszOutBuf]; unsigned __int16 *
0x18000b903  mov     edx, 104h; unsigned __int64
0x18000b908  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b90d  mov     ebx, eax
0x18000b90f  mov     rsi, r14
0x18000b912  xor     r14d, r14d
0x18000b915  test    ebx, ebx
0x18000b917  js      short loc_18000B969
0x18000b919  test    edi, edi
0x18000b91b  jz      short loc_18000B95C
0x18000b91d  lea     rcx, [rsp+4B0h+pszOutBuf]; pszPath
0x18000b922  call    cs:__imp_PathIsRelativeW
0x18000b928  test    eax, eax
0x18000b92a  jnz     short loc_18000B95C
0x18000b92c  lea     r9, [rsp+4B0h+var_470]; unsigned int *
0x18000b931  mov     dword ptr [rsp+4B0h+var_470], r14d
0x18000b936  lea     rcx, [rsp+4B0h+pszOutBuf]; unsigned __int16 *
0x18000b93b  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x18000b940  cmp     [rsp+4B0h+pszOutBuf], r14w
0x18000b946  jz      short loc_18000B9AF
0x18000b948  cmp     dword ptr [rsp+4B0h+var_470], r14d
0x18000b94d  jz      short loc_18000B9AF
0x18000b94f  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x18000b954  test    eax, eax
0x18000b956  jnz     short loc_18000B9AF
0x18000b958  mov     [rsi], r14w
0x18000b95c  mov     r9, r12
0x18000b95f  mov     r8, rsi
0x18000b962  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000b967  mov     ebx, eax
0x18000b969  mov     rcx, [rsp+4B0h+pszSource]; pv
0x18000b96e  call    cs:__imp_CoTaskMemFree
0x18000b974  mov     rax, [r15]
0x18000b977  mov     rcx, r15
0x18000b97a  mov     rax, [rax+10h]
0x18000b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b983  mov     eax, ebx
0x18000b985  mov     rcx, [rbp+3B0h+var_40]
0x18000b98c  xor     rcx, rsp; StackCookie
0x18000b98f  call    __security_check_cookie
0x18000b994  mov     rbx, [rsp+4B0h+arg_18]
0x18000b99c  add     rsp, 480h
0x18000b9a3  pop     r15
0x18000b9a5  pop     r14
0x18000b9a7  pop     r13
0x18000b9a9  pop     r12
0x18000b9ab  pop     rdi
0x18000b9ac  pop     rsi
0x18000b9ad  pop     rbp
0x18000b9ae  retn
0x18000b9af  lea     rcx, [rsp+4B0h+pszOutBuf]; unsigned __int16 *
0x18000b9b4  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x18000b9b9  cmp     eax, 3
0x18000b9bc  jnz     short loc_18000B95C
0x18000b9be  mov     ebx, 80070002h
0x18000b9c3  jmp     short loc_18000B969
```
