# CThemePack::_AddFileToList(ushort const *,ushort const *,CThemePack::FILE_INFO * *)

- ea: `0x180067010`
- end: `0x180067354`
- name: `?_AddFileToList@CThemePack@@AEAAJPEBG0PEAPEAUFILE_INFO@1@@Z`
- size: `836`
- prototype: `int(CThemePack *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct CThemePack::FILE_INFO **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180066168`

## callees

- `0x1800089c0`
- `0x1800151e0`
- `0x180030f64`
- `0x1800358c0`
- `0x18003633c`
- `0x180052974`
- `0x180063548`
- `0x180063c40`
- `0x180065d88`
- `0x180065dc0`
- `0x180066fd0`
- `0x180067010`
- `0x1800677e8`
- `0x1800678b4`
- `0x180068aac`
- `0x180068c08`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18006708d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18006708d`
- `SHLWAPI!PathFindFileNameW` at `0x180067167`
- `SHLWAPI!PathFindFileNameW` at `0x180067167`
- `SHLWAPI!PathFindExtensionW` at `0x18006719f`
- `SHLWAPI!PathFindExtensionW` at `0x18006719f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180067106`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180067106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800670c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800670c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006731d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006731d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180067136`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180067136`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006718c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006718c`

## pseudocode

```c
__int64 __fastcall CThemePack::_AddFileToList(
        HDPA *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CThemePack::FILE_INFO **a4)
{
  int updated; // ebx
  unsigned int v7; // r12d
  struct IUnknown *v8; // rdx
  unsigned int v9; // r8d
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  __int64 v13; // rsi
  char *v14; // r14
  const WCHAR *v15; // rbp
  unsigned __int8 **v16; // r9
  __int64 v17; // r8
  HDPA *v18; // rbp
  int v19; // edx
  __int64 v20; // r9
  HDPA *v21; // rbp
  __int64 v22; // r8
  __int64 v23; // rcx
  PCWSTR v24; // rdx
  WCHAR *v25; // rax
  unsigned __int8 *v26; // r9
  int v27; // eax
  bool v28; // sf
  int v29; // eax
  HDPA *v30; // r12
  int *lpDestStr; // [rsp+20h] [rbp-B8h]
  unsigned int lpDestStra; // [rsp+20h] [rbp-B8h]
  unsigned int cchDest; // [rsp+28h] [rbp-B0h]
  unsigned __int8 *v34; // [rsp+30h] [rbp-A8h]
  unsigned int v35; // [rsp+38h] [rbp-A0h]
  unsigned int v36[2]; // [rsp+40h] [rbp-98h] BYREF
  HDPA *v37; // [rsp+48h] [rbp-90h]
  PCWSTR pszPathIn; // [rsp+50h] [rbp-88h] BYREF
  WCHAR *FileNameW; // [rsp+58h] [rbp-80h]
  __int128 FileInformation; // [rsp+60h] [rbp-78h] BYREF
  __int128 v41; // [rsp+70h] [rbp-68h]
  unsigned int v42; // [rsp+80h] [rbp-58h]

  v37 = this;
  *a4 = 0;
  pszPathIn = a3;
  if ( !(unsigned int)IsSystemResource(a2) || (unsigned int)VerifyResourceFile(a2, 0) )
  {
    v7 = 2;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned int)SHWindowsPolicy(POLID_EnableThemeFileRemoteResource) )
      {
        v36[0] = -1;
        SHMapUrlToZoneEx(a2, v8, v9, v36);
        if ( v36[0] > 2 )
          return 2147942405LL;
      }
    }
    v11 = (WCHAR *)CoTaskMemAlloc(0x420u);
    v12 = v11;
    if ( !v11 )
      return (unsigned int)-2147024882;
    memset_0(v11, 0, 0x420u);
    v13 = -1;
    v14 = (char *)(v12 + 4);
    updated = LCMapStringW(0x400u, 0x100u, a2, -1, v12 + 4, 260);
    if ( updated >= 0 )
    {
      v42 = 0;
      FileInformation = 0;
      v41 = 0;
      if ( GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation)
        || (updated = ResultFromKnownLastError(), updated >= 0) )
      {
        *(_QWORD *)v12 = v42 + ((unsigned __int64)HIDWORD(v41) << 32);
        FileNameW = PathFindFileNameW(v12 + 4);
        v15 = FileNameW;
        updated = PathCchCombine(v12 + 264, 0x104u, pszPathIn, FileNameW);
        if ( updated >= 0 )
        {
          *(_QWORD *)v36 = PathFindExtensionW(v15);
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)&v14[2 * v17] );
          v18 = v37;
          if ( (int)CByteHashTable::_GetValue(
                      (CByteHashTable *)(v37 + 1),
                      (const unsigned __int8 *)v12 + 8,
                      2 * (int)v17 + 2,
                      v16,
                      lpDestStr,
                      (unsigned __int8 *)a4,
                      8) >= 0 )
            return (unsigned int)updated;
          pszPathIn = v12;
          v20 = -1;
          do
            ++v20;
          while ( *(_WORD *)&v14[2 * v20] );
          updated = CByteHashTable::_AddUpdateItem(
                      (CByteHashTable *)(v18 + 1),
                      v19,
                      (const unsigned __int8 *)v12 + 8,
                      2 * (int)v20 + 2,
                      (const unsigned __int8 *)&pszPathIn,
                      cchDest,
                      v34,
                      v35);
          if ( updated >= 0 )
          {
            v21 = v18 + 6;
            if ( (int)CHashTable<int,unsigned short>::ContainsKey(v21, v12 + 264) < 0 )
            {
LABEL_23:
              v29 = CHashTable<int,unsigned short>::SetPtr(v21, v12 + 264);
              v30 = v37;
              updated = v29;
              if ( v29 >= 0 )
              {
                if ( DPA_InsertPtr(*v37, 0x7FFFFFFF, v12) != -1 )
                {
                  updated = 0;
                  *a4 = (struct CThemePack::FILE_INFO *)v12;
                  return (unsigned int)updated;
                }
                updated = -2147024882;
                CHashTable<int,unsigned short>::DeletePtr(v21, v12 + 264);
              }
            }
            else
            {
              v22 = *(_QWORD *)v36;
              v23 = (int)((__int64)(*(_QWORD *)v36 - (_QWORD)FileNameW) >> 1);
              v24 = (PCWSTR)(260 - v23);
              pszPathIn = (PCWSTR)(260 - v23);
              v25 = &v12[v23 + 264];
              FileNameW = v25;
              while ( 1 )
              {
                updated = StringCchPrintfW(v25, (unsigned __int64)v24, L" (%d)%s", v7, v22);
                if ( updated < 0 )
                  break;
                ++v7;
                v27 = CHashTable<int,unsigned short>::ContainsKey(v21, v12 + 264);
                v24 = pszPathIn;
                v28 = v27 < 0;
                v25 = FileNameW;
                v22 = *(_QWORD *)v36;
                if ( v28 )
                  goto LABEL_23;
              }
              v30 = v37;
            }
            do
              ++v13;
            while ( *(_WORD *)&v14[2 * v13] );
            CByteHashTable::_RemoveItem(
              (CByteHashTable *)(v30 + 1),
              (const unsigned __int8 *)v12 + 8,
              2 * v13 + 2,
              v26,
              lpDestStra);
            if ( updated >= 0 )
              return (unsigned int)updated;
          }
        }
      }
    }
    CoTaskMemFree(v12);
    *a4 = 0;
    return (unsigned int)updated;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180067010  push    rbx
0x180067012  push    rbp
0x180067013  push    rsi
0x180067014  push    rdi
0x180067015  push    r12
0x180067017  push    r13
0x180067019  push    r14
0x18006701b  push    r15
0x18006701d  sub     rsp, 98h
0x180067024  mov     rax, cs:__security_cookie
0x18006702b  xor     rax, rsp
0x18006702e  mov     [rsp+0D8h+var_50], rax
0x180067036  mov     [rsp+0D8h+var_90], rcx
0x18006703b  xor     r15d, r15d
0x18006703e  mov     rcx, rdx; unsigned __int16 *
0x180067041  mov     [r9], r15
0x180067044  mov     r13, r9
0x180067047  mov     [rsp+0D8h+pszPathIn], r8
0x18006704c  mov     rbp, rdx
0x18006704f  call    ?IsSystemResource@@YAHPEBG@Z; IsSystemResource(ushort const *)
0x180067054  test    eax, eax
0x180067056  jz      short loc_180067070
0x180067058  xor     edx, edx; int
0x18006705a  mov     rcx, rbp; unsigned __int16 *
0x18006705d  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180067062  test    eax, eax
0x180067064  jnz     short loc_180067070
0x180067066  mov     ebx, 80070057h
0x18006706b  jmp     loc_18006732E
0x180067070  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource> `wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl(void)'::`2'::impl
0x180067077  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(void)
0x18006707c  mov     r12d, 2
0x180067082  test    al, al
0x180067084  jz      short loc_1800670BD
0x180067086  lea     rcx, POLID_EnableThemeFileRemoteResource
0x18006708d  call    cs:__imp_SHWindowsPolicy
0x180067093  test    eax, eax
0x180067095  jnz     short loc_1800670BD
0x180067097  lea     r9, [rsp+0D8h+var_98]; unsigned int *
0x18006709c  mov     [rsp+0D8h+var_98], 0FFFFFFFFh
0x1800670a4  mov     rcx, rbp; unsigned __int16 *
0x1800670a7  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x1800670ac  cmp     [rsp+0D8h+var_98], r12d
0x1800670b1  jbe     short loc_1800670BD
0x1800670b3  mov     eax, 80070005h
0x1800670b8  jmp     loc_180067330
0x1800670bd  mov     ebx, 420h
0x1800670c2  mov     ecx, ebx; cb
0x1800670c4  call    cs:__imp_CoTaskMemAlloc
0x1800670ca  mov     rdi, rax
0x1800670cd  test    rax, rax
0x1800670d0  jz      loc_180067329
0x1800670d6  mov     r8d, ebx; Size
0x1800670d9  xor     edx, edx; Val
0x1800670db  mov     rcx, rax; void *
0x1800670de  call    memset_0
0x1800670e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800670e7  mov     [rsp+0D8h+cchDest], 104h; cchDest
0x1800670ef  lea     r14, [rdi+8]
0x1800670f3  mov     r9d, esi; cchSrc
0x1800670f6  mov     r8, rbp; lpSrcStr
0x1800670f9  mov     [rsp+0D8h+lpDestStr], r14; int *
0x1800670fe  mov     edx, 100h; dwMapFlags
0x180067103  lea     ecx, [rbx-20h]; Locale
0x180067106  call    cs:__imp_LCMapStringW
0x18006710c  mov     ebx, eax
0x18006710e  test    eax, eax
0x180067110  js      loc_18006731A
0x180067116  xorps   xmm0, xmm0
0x180067119  lea     r8, [rsp+0D8h+FileInformation]; lpFileInformation
0x18006711e  xor     eax, eax
0x180067120  xor     edx, edx; fInfoLevelId
0x180067122  mov     rcx, rbp; lpFileName
0x180067125  mov     [rsp+0D8h+var_58], eax
0x18006712c  movups  [rsp+0D8h+FileInformation], xmm0
0x180067131  movups  [rsp+0D8h+var_68], xmm0
0x180067136  call    cs:__imp_GetFileAttributesExW
0x18006713c  test    eax, eax
0x18006713e  jnz     short loc_18006714F
0x180067140  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067145  mov     ebx, eax
0x180067147  test    eax, eax
0x180067149  js      loc_18006731A
0x18006714f  mov     ecx, dword ptr [rsp+0D8h+var_68+0Ch]
0x180067153  mov     eax, [rsp+0D8h+var_58]
0x18006715a  shl     rcx, 20h
0x18006715e  add     rcx, rax
0x180067161  mov     [rdi], rcx
0x180067164  mov     rcx, r14; pszPath
0x180067167  call    cs:__imp_PathFindFileNameW
0x18006716d  mov     r8, [rsp+0D8h+pszPathIn]; pszPathIn
0x180067172  lea     r15, [rdi+210h]
0x180067179  mov     r9, rax; pszMore
0x18006717c  mov     [rsp+0D8h+var_80], rax
0x180067181  mov     rcx, r15; pszPathOut
0x180067184  mov     edx, 104h; cchPathOut
0x180067189  mov     rbp, rax
0x18006718c  call    cs:__imp_PathCchCombine
0x180067192  mov     ebx, eax
0x180067194  test    eax, eax
0x180067196  js      loc_180067317
0x18006719c  mov     rcx, rbp; pszPath
0x18006719f  call    cs:__imp_PathFindExtensionW
0x1800671a5  mov     qword ptr [rsp+0D8h+var_98], rax
0x1800671aa  mov     r8, rsi
0x1800671ad  xor     eax, eax
0x1800671af  inc     r8
0x1800671b2  cmp     [r14+r8*2], ax
0x1800671b7  jnz     short loc_1800671AF
0x1800671b9  mov     rbp, [rsp+0D8h+var_90]
0x1800671be  lea     r8d, ds:2[r8*2]; unsigned int
0x1800671c6  mov     dword ptr [rsp+0D8h+var_A8], 8; unsigned __int8 *
0x1800671ce  mov     rdx, r14; unsigned __int8 *
0x1800671d1  mov     qword ptr [rsp+0D8h+cchDest], r13; unsigned int
0x1800671d6  lea     rcx, [rbp+8]; this
0x1800671da  call    ?_GetValue@CByteHashTable@@AEBAJPEBEIPEAPEAEPEAHPEAEH@Z; CByteHashTable::_GetValue(uchar const *,uint,uchar * *,int *,uchar *,int)
0x1800671df  xor     ecx, ecx
0x1800671e1  test    eax, eax
0x1800671e3  jns     loc_18006732E
0x1800671e9  mov     [rsp+0D8h+pszPathIn], rdi
0x1800671ee  mov     r9, rsi
0x1800671f1  inc     r9
0x1800671f4  cmp     [r14+r9*2], cx
0x1800671f9  jnz     short loc_1800671F1
0x1800671fb  lea     rax, [rsp+0D8h+pszPathIn]
0x180067200  mov     r8, r14; unsigned __int8 *
0x180067203  lea     r9d, ds:2[r9*2]; unsigned int
0x18006720b  mov     [rsp+0D8h+lpDestStr], rax; unsigned __int8 *
0x180067210  lea     rcx, [rbp+8]; this
0x180067214  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x180067219  mov     ebx, eax
0x18006721b  test    eax, eax
0x18006721d  js      loc_180067317
0x180067223  mov     rdx, r15
0x180067226  add     rbp, 30h ; '0'
0x18006722a  mov     rcx, rbp
0x18006722d  call    ?ContainsKey@?$CHashTable@HG@@QEBAJPEBG@Z; CHashTable<int,ushort>::ContainsKey(ushort const *)
0x180067232  test    eax, eax
0x180067234  js      short loc_1800672A4
0x180067236  mov     r8, qword ptr [rsp+0D8h+var_98]
0x18006723b  mov     edx, 104h
0x180067240  mov     rax, r8
0x180067243  sub     rax, [rsp+0D8h+var_80]
0x180067248  sar     rax, 1
0x18006724b  movsxd  rcx, eax
0x18006724e  sub     rdx, rcx; unsigned __int64
0x180067251  mov     [rsp+0D8h+pszPathIn], rdx
0x180067256  lea     rax, [rcx+108h]
0x18006725d  lea     rax, [rdi+rax*2]
0x180067261  mov     [rsp+0D8h+var_80], rax
0x180067266  mov     [rsp+0D8h+lpDestStr], r8; unsigned int
0x18006726b  mov     r9d, r12d
0x18006726e  lea     r8, aDS; " (%d)%s"
0x180067275  mov     rcx, rax; unsigned __int16 *
0x180067278  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006727d  mov     ebx, eax
0x18006727f  test    eax, eax
0x180067281  js      short loc_1800672EA
0x180067283  mov     rdx, r15
0x180067286  mov     rcx, rbp
0x180067289  inc     r12d
0x18006728c  call    ?ContainsKey@?$CHashTable@HG@@QEBAJPEBG@Z; CHashTable<int,ushort>::ContainsKey(ushort const *)
0x180067291  mov     rdx, [rsp+0D8h+pszPathIn]
0x180067296  test    eax, eax
0x180067298  mov     rax, [rsp+0D8h+var_80]
0x18006729d  mov     r8, qword ptr [rsp+0D8h+var_98]
0x1800672a2  jns     short loc_180067266
0x1800672a4  mov     rdx, r15
0x1800672a7  mov     rcx, rbp
0x1800672aa  call    ?SetPtr@?$CHashTable@HG@@QEAAJPEBGPEAHPEAPEAH@Z; CHashTable<int,ushort>::SetPtr(ushort const *,int *,int * *)
0x1800672af  mov     r12, [rsp+0D8h+var_90]
0x1800672b4  mov     ebx, eax
0x1800672b6  test    eax, eax
0x1800672b8  js      short loc_1800672EF
0x1800672ba  mov     rcx, [r12]; hdpa
0x1800672be  mov     r8, rdi; p
0x1800672c1  mov     edx, 7FFFFFFFh; i
0x1800672c6  call    cs:__imp_DPA_InsertPtr
0x1800672cc  cmp     eax, esi
0x1800672ce  jz      short loc_1800672D8
0x1800672d0  xor     ebx, ebx
0x1800672d2  mov     [r13+0], rdi
0x1800672d6  jmp     short loc_18006732E
0x1800672d8  mov     rdx, r15
0x1800672db  mov     rcx, rbp
0x1800672de  mov     ebx, 8007000Eh
0x1800672e3  call    ?DeletePtr@?$CHashTable@HG@@QEAAJPEBGPEAPEAH@Z; CHashTable<int,ushort>::DeletePtr(ushort const *,int * *)
0x1800672e8  jmp     short loc_1800672EF
0x1800672ea  mov     r12, [rsp+0D8h+var_90]
0x1800672ef  xor     r15d, r15d
0x1800672f2  inc     rsi
0x1800672f5  cmp     [r14+rsi*2], r15w
0x1800672fa  jnz     short loc_1800672F2
0x1800672fc  lea     r8d, ds:2[rsi*2]; unsigned int
0x180067304  mov     rdx, r14; unsigned __int8 *
0x180067307  lea     rcx, [r12+8]; this
0x18006730c  call    ?_RemoveItem@CByteHashTable@@AEAAJPEBEIPEAEI@Z; CByteHashTable::_RemoveItem(uchar const *,uint,uchar *,uint)
0x180067311  test    ebx, ebx
0x180067313  jns     short loc_18006732E
0x180067315  jmp     short loc_18006731A
0x180067317  xor     r15d, r15d
0x18006731a  mov     rcx, rdi; pv
0x18006731d  call    cs:__imp_CoTaskMemFree
0x180067323  mov     [r13+0], r15
0x180067327  jmp     short loc_18006732E
0x180067329  mov     ebx, 8007000Eh
0x18006732e  mov     eax, ebx
0x180067330  mov     rcx, [rsp+0D8h+var_50]
0x180067338  xor     rcx, rsp; StackCookie
0x18006733b  call    __security_check_cookie
0x180067340  add     rsp, 98h
0x180067347  pop     r15
0x180067349  pop     r14
0x18006734b  pop     r13
0x18006734d  pop     r12
0x18006734f  pop     rdi
0x180067350  pop     rsi
0x180067351  pop     rbp
0x180067352  pop     rbx
0x180067353  retn
```
