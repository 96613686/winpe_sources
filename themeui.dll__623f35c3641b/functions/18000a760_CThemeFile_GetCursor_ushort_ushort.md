# CThemeFile::GetCursor(ushort *,ushort * *)

- ea: `0x18000a760`
- end: `0x18000a994`
- name: `?GetCursor@CThemeFile@@UEAAJPEAGPEAPEAG@Z`
- size: `564`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000a760`
- `0x18000a9a0`
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

- `SHLWAPI!PathIsRelativeW` at `0x18000a91e`
- `SHLWAPI!PathIsRelativeW` at `0x18000a91e`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000a8e9`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18000a8e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a81d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a81d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a973`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a801`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a801`

## pseudocode

```c
__int64 __fastcall CThemeFile::GetCursor(CThemeFile *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  const unsigned __int16 **v3; // r15
  OLECHAR *v6; // rdi
  HRESULT CachedProfile; // ebx
  unsigned __int16 *v9; // rax
  int v10; // eax
  struct ICachedPrivateProfile *v11; // r14
  unsigned int v12; // edx
  struct IUnknown *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  HRESULT v16; // eax
  struct ICachedPrivateProfile *v17; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszSource; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v19; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[264]; // [rsp+270h] [rbp+170h] BYREF

  v3 = (const unsigned __int16 **)((char *)this - 16);
  *a3 = 0;
  v19 = 0;
  v17 = 0;
  v6 = 0;
  CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)((char *)this - 16), 1, &v17);
  if ( CachedProfile < 0 )
    return (unsigned int)CachedProfile;
  pszSource = 0;
  v10 = StringCchPrintfW(v21, 0x104u, L"%s.MUI", a2);
  v11 = v17;
  if ( v10 >= 0
    && (*(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v17 + 48LL))(
         v17,
         L"Control Panel\\Cursors",
         v21,
         0,
         1,
         &pszSource) >= 0
    || (CachedProfile = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v11 + 48LL))(
                          v11,
                          L"Control Panel\\Cursors",
                          a2,
                          0,
                          1,
                          &pszSource),
        CachedProfile >= 0) )
  {
    memset_0(pszOutBuf, 0, 0x208u);
    CachedProfile = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
    if ( CachedProfile < 0 )
      goto LABEL_20;
    CachedProfile = ExpandResourceDir(pszOutBuf, v12);
    if ( CachedProfile < 0 )
      goto LABEL_20;
    CachedProfile = ExpandThemeTokens(v3[6], pszOutBuf);
    if ( CachedProfile < 0 )
      goto LABEL_20;
    if ( !PathIsRelativeW(pszOutBuf) )
    {
      LODWORD(v17) = 0;
      SHMapUrlToZoneEx(pszOutBuf, v13, v15, (unsigned int *)&v17);
      if ( pszOutBuf[0] && (_DWORD)v17 && !CFileSource::s_IsUncPathAllowedForThumbnailImage() )
      {
        pszOutBuf[0] = 0;
      }
      else if ( (unsigned int)ConfirmFile(pszOutBuf) == 3 )
      {
        CachedProfile = -2147024894;
        goto LABEL_20;
      }
    }
    v16 = _AllocString<CTCoAllocPolicy>(v14, v13, pszOutBuf, &v19);
    v6 = v19;
    CachedProfile = v16;
LABEL_20:
    CoTaskMemFree((LPVOID)pszSource);
  }
  (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( CachedProfile >= 0 )
  {
    CachedProfile = 0;
    v9 = SysAllocString(v6);
    *a3 = v9;
    if ( v6 && !v9 )
      CachedProfile = -2147024882;
    CoTaskMemFree(v6);
  }
  return (unsigned int)CachedProfile;
}

```

## disassembly

```asm
0x18000a760  push    rbp
0x18000a762  push    rbx
0x18000a763  push    rsi
0x18000a764  push    rdi
0x18000a765  push    r12
0x18000a767  push    r13
0x18000a769  push    r15
0x18000a76b  lea     rbp, [rsp-390h]
0x18000a773  sub     rsp, 490h
0x18000a77a  mov     rax, cs:__security_cookie
0x18000a781  xor     rax, rsp
0x18000a784  mov     [rbp+3C0h+var_40], rax
0x18000a78b  xor     r13d, r13d
0x18000a78e  lea     r15, [rcx-10h]
0x18000a792  mov     [r8], r13
0x18000a795  mov     rsi, r8
0x18000a798  mov     r12, rdx
0x18000a79b  mov     [rsp+4C0h+var_470], r13
0x18000a7a0  lea     r8, [rsp+4C0h+var_480]; struct ICachedPrivateProfile **
0x18000a7a5  mov     [rsp+4C0h+var_480], r13
0x18000a7aa  mov     dl, 1; bool
0x18000a7ac  mov     rcx, r15; this
0x18000a7af  mov     edi, r13d
0x18000a7b2  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x18000a7b7  mov     ebx, eax
0x18000a7b9  test    eax, eax
0x18000a7bb  jns     short loc_18000A825
0x18000a7bd  mov     eax, ebx
0x18000a7bf  mov     rcx, [rbp+3C0h+var_40]
0x18000a7c6  xor     rcx, rsp; StackCookie
0x18000a7c9  call    __security_check_cookie
0x18000a7ce  add     rsp, 490h
0x18000a7d5  pop     r15
0x18000a7d7  pop     r13
0x18000a7d9  pop     r12
0x18000a7db  pop     rdi
0x18000a7dc  pop     rsi
0x18000a7dd  pop     rbx
0x18000a7de  pop     rbp
0x18000a7df  retn
0x18000a7e0  mov     rax, [r14]
0x18000a7e3  mov     rcx, r14
0x18000a7e6  mov     rax, [rax+10h]
0x18000a7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7ef  mov     r14, [rsp+4C0h+arg_18]
0x18000a7f7  test    ebx, ebx
0x18000a7f9  js      short loc_18000A7BD
0x18000a7fb  mov     rcx, rdi; psz
0x18000a7fe  mov     ebx, r13d
0x18000a801  call    cs:__imp_SysAllocString
0x18000a807  mov     [rsi], rax
0x18000a80a  test    rdi, rdi
0x18000a80d  jz      short loc_18000A81A
0x18000a80f  test    rax, rax
0x18000a812  mov     ecx, 8007000Eh
0x18000a817  cmovz   ebx, ecx
0x18000a81a  mov     rcx, rdi; pv
0x18000a81d  call    cs:__imp_CoTaskMemFree
0x18000a823  jmp     short loc_18000A7BD
0x18000a825  mov     r9, r12
0x18000a828  mov     [rsp+4C0h+arg_18], r14
0x18000a830  lea     r8, aSMui; "%s.MUI"
0x18000a837  mov     [rsp+4C0h+pszSource], r13
0x18000a83c  mov     edx, 104h; unsigned __int64
0x18000a841  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x18000a848  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a84d  mov     r14, [rsp+4C0h+var_480]
0x18000a852  test    eax, eax
0x18000a854  js      short loc_18000A88C
0x18000a856  mov     rax, [r14]
0x18000a859  lea     rcx, [rsp+4C0h+pszSource]
0x18000a85e  mov     [rsp+4C0h+var_498], rcx
0x18000a863  lea     r8, [rbp+3C0h+var_250]
0x18000a86a  xor     r9d, r9d
0x18000a86d  mov     [rsp+4C0h+var_4A0], 1
0x18000a875  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18000a87c  mov     rcx, r14
0x18000a87f  mov     rax, [rax+30h]
0x18000a883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a888  test    eax, eax
0x18000a88a  jns     short loc_18000A8C4
0x18000a88c  mov     rax, [r14]
0x18000a88f  lea     rcx, [rsp+4C0h+pszSource]
0x18000a894  mov     [rsp+4C0h+var_498], rcx
0x18000a899  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x18000a8a0  xor     r9d, r9d
0x18000a8a3  mov     [rsp+4C0h+var_4A0], 1
0x18000a8ab  mov     r8, r12
0x18000a8ae  mov     rcx, r14
0x18000a8b1  mov     rax, [rax+30h]
0x18000a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ba  mov     ebx, eax
0x18000a8bc  test    eax, eax
0x18000a8be  js      loc_18000A7E0
0x18000a8c4  xor     edx, edx; Val
0x18000a8c6  lea     rcx, [rsp+4C0h+pszOutBuf]; void *
0x18000a8cb  mov     r8d, 208h; Size
0x18000a8d1  call    memset_0
0x18000a8d6  mov     rcx, [rsp+4C0h+pszSource]; pszSource
0x18000a8db  lea     rdx, [rsp+4C0h+pszOutBuf]; pszOutBuf
0x18000a8e0  xor     r9d, r9d; ppvReserved
0x18000a8e3  mov     r8d, 104h; cchOutBuf
0x18000a8e9  call    cs:__imp_SHLoadIndirectString
0x18000a8ef  mov     ebx, eax
0x18000a8f1  test    eax, eax
0x18000a8f3  js      short loc_18000A96E
0x18000a8f5  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x18000a8fa  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x18000a8ff  mov     ebx, eax
0x18000a901  test    eax, eax
0x18000a903  js      short loc_18000A96E
0x18000a905  mov     rcx, [r15+30h]; unsigned __int16 *
0x18000a909  lea     rdx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x18000a90e  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x18000a913  mov     ebx, eax
0x18000a915  test    eax, eax
0x18000a917  js      short loc_18000A96E
0x18000a919  lea     rcx, [rsp+4C0h+pszOutBuf]; pszPath
0x18000a91e  call    cs:__imp_PathIsRelativeW
0x18000a924  test    eax, eax
0x18000a926  jnz     short loc_18000A958
0x18000a928  lea     r9, [rsp+4C0h+var_480]; unsigned int *
0x18000a92d  mov     dword ptr [rsp+4C0h+var_480], r13d
0x18000a932  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x18000a937  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x18000a93c  cmp     [rsp+4C0h+pszOutBuf], di
0x18000a941  jz      short loc_18000A97E
0x18000a943  cmp     dword ptr [rsp+4C0h+var_480], edi
0x18000a947  jz      short loc_18000A97E
0x18000a949  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x18000a94e  test    eax, eax
0x18000a950  jnz     short loc_18000A97E
0x18000a952  mov     [rsp+4C0h+pszOutBuf], r13w
0x18000a958  lea     r9, [rsp+4C0h+var_470]
0x18000a95d  lea     r8, [rsp+4C0h+pszOutBuf]
0x18000a962  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000a967  mov     rdi, [rsp+4C0h+var_470]
0x18000a96c  mov     ebx, eax
0x18000a96e  mov     rcx, [rsp+4C0h+pszSource]; pv
0x18000a973  call    cs:__imp_CoTaskMemFree
0x18000a979  jmp     loc_18000A7E0
0x18000a97e  lea     rcx, [rsp+4C0h+pszOutBuf]; unsigned __int16 *
0x18000a983  call    ?ConfirmFile@@YAHPEAGH@Z; ConfirmFile(ushort *,int)
0x18000a988  cmp     eax, 3
0x18000a98b  jnz     short loc_18000A958
0x18000a98d  mov     ebx, 80070002h
0x18000a992  jmp     short loc_18000A96E
```
