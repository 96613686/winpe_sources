# CFileSource::s_LoadPIDL(ICachedPrivateProfile *,ushort const *,ushort const *,bool,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *,bool *,int)

- ea: `0x180008e20`
- end: `0x1800090d1`
- name: `?s_LoadPIDL@CFileSource@@CAJPEAUICachedPrivateProfile@@PEBG1_NPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU3@PEA_NH@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct ICachedPrivateProfile *, const unsigned __int16 *, const unsigned __int16 *, bool, LPCITEMIDLIST pidl1, LPITEMIDLIST *ppidl, bool *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ae0`

## callees

- `0x1800089c0`
- `0x180008e20`
- `0x180030f64`
- `0x1800358c0`
- `0x180052974`
- `0x180060fac`
- `0x1800618d0`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180008f7b`
- `SHELL32!SHCreateItemFromParsingName` at `0x180008f7b`
- `SHELL32!SHGetIDListFromObject` at `0x18000906d`
- `SHELL32!SHGetIDListFromObject` at `0x18000908b`
- `SHELL32!SHGetIDListFromObject` at `0x18000906d`
- `SHELL32!SHGetIDListFromObject` at `0x18000908b`
- `SHELL32!__imp_ILCombine` at `0x180008fe9`
- `SHELL32!__imp_ILCombine` at `0x180008fe9`
- `SHELL32!__imp_ILFree` at `0x180008ff7`
- `SHELL32!__imp_ILFree` at `0x180008ff7`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180008fd5`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180008fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009002`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009002`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f53`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f53`

## pseudocode

```c
__int64 __fastcall CFileSource::s_LoadPIDL(
        struct ICachedPrivateProfile *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        LPCITEMIDLIST pidl1,
        LPITEMIDLIST *ppidl,
        bool *a7,
        int a8)
{
  HRESULT Error; // ebx
  __int64 v13; // rax
  struct IUnknown *v14; // rdx
  __int64 v15; // r8
  ITEMIDLIST *v17; // rax
  ITEMIDLIST *v18; // rcx
  LPCWSTR lpSrc; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp-B0h] BYREF
  IStream *pstm[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  unsigned __int16 v24[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-10h] BYREF

  v23 = 0;
  *ppidl = 0;
  *(_OWORD *)pstm = 0;
  if ( a7 )
    *a7 = 1;
  if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const unsigned __int16 *, const unsigned __int16 *, __int64, __int16, IStream **))(*(_QWORD *)a1 + 40LL))(
         a1,
         a2,
         a3,
         1,
         66,
         pstm) < 0 )
  {
    *ppidl = 0;
    if ( a7 )
      *a7 = 1;
    Error = StringCchPrintfW(v24, 0x40u, L"%s%s", a3, L"Path");
    if ( Error < 0 )
    {
      if ( !a7 )
        return (unsigned int)Error;
    }
    else
    {
      v13 = *(_QWORD *)a1;
      lpSrc = 0;
      Error = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const unsigned __int16 *, unsigned __int16 *, _QWORD, int, LPCWSTR *))(v13 + 48))(
                a1,
                a2,
                v24,
                0,
                1,
                &lpSrc);
      if ( Error >= 0 )
      {
        if ( a8 != 1
          || (LODWORD(ppv) = -1, SHMapUrlToZoneEx(lpSrc, v14, v15, (unsigned int *)&ppv), !(_DWORD)ppv)
          || CFileSource::s_IsUncPathAllowedForThumbnailImage() )
        {
          if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) > 0x104 )
          {
            Error = ResultFromKnownLastError();
          }
          else
          {
            ppv = 0;
            Error = SHCreateItemFromParsingName(Dst, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
            if ( Error >= 0 )
            {
              if ( a4 )
              {
                punk = 0;
                Error = GetFilteredShellItem((struct IShellItem *)ppv, (struct IShellItem **)&punk);
                if ( Error >= 0 )
                {
                  Error = SHGetIDListFromObject(punk, ppidl);
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
              }
              else
              {
                Error = SHGetIDListFromObject((IUnknown *)ppv, ppidl);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
        }
        CoTaskMemFree((LPVOID)lpSrc);
        return (unsigned int)Error;
      }
      if ( !a7 )
        return (unsigned int)Error;
    }
    *a7 = 0;
    return (unsigned int)Error;
  }
  lpSrc = 0;
  Error = ILLoadFromStreamEx(pstm[1], (LPITEMIDLIST *)&lpSrc);
  if ( Error >= 0 )
  {
    v17 = ILCombine(pidl1, (LPCITEMIDLIST)lpSrc);
    v18 = (ITEMIDLIST *)lpSrc;
    *ppidl = v17;
    ILFree(v18);
  }
  PropVariantClear((PROPVARIANT *)pstm);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180008e20  mov     [rsp-8+arg_18], rbx
0x180008e25  push    rbp
0x180008e26  push    rsi
0x180008e27  push    rdi
0x180008e28  push    r12
0x180008e2a  push    r13
0x180008e2c  push    r14
0x180008e2e  push    r15
0x180008e30  lea     rbp, [rsp-210h]
0x180008e38  sub     rsp, 310h
0x180008e3f  mov     rax, cs:__security_cookie
0x180008e46  xor     rax, rsp
0x180008e49  mov     [rbp+240h+var_40], rax
0x180008e50  mov     r14, [rbp+240h+ppidl]
0x180008e57  xor     eax, eax
0x180008e59  mov     rdi, [rbp+240h+arg_30]
0x180008e60  xorps   xmm0, xmm0
0x180008e63  mov     r12, [rbp+240h+pidl1]
0x180008e6a  movzx   r13d, r9b
0x180008e6e  mov     [rsp+340h+var_2D8], rax
0x180008e73  mov     rbx, r8
0x180008e76  mov     qword ptr [r14], 0
0x180008e7d  mov     r15, rdx
0x180008e80  mov     rsi, rcx
0x180008e83  movups  xmmword ptr [rsp+340h+pstm], xmm0
0x180008e88  test    rdi, rdi
0x180008e8b  jz      short loc_180008E90
0x180008e8d  mov     byte ptr [rdi], 1
0x180008e90  mov     rax, [rcx]
0x180008e93  mov     r9d, 1
0x180008e99  lea     rcx, [rsp+340h+pstm]
0x180008e9e  mov     [rsp+340h+var_318], rcx
0x180008ea3  mov     rcx, rsi
0x180008ea6  mov     word ptr [rsp+340h+var_320], 42h ; 'B'
0x180008ead  mov     rax, [rax+28h]
0x180008eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb6  test    eax, eax
0x180008eb8  jns     loc_180008FC2
0x180008ebe  xor     r12d, r12d
0x180008ec1  mov     [r14], r12
0x180008ec4  test    rdi, rdi
0x180008ec7  jnz     loc_18000900A
0x180008ecd  lea     rax, aPath; "Path"
0x180008ed4  mov     r9, rbx
0x180008ed7  lea     r8, aSS_0; "%s%s"
0x180008ede  mov     [rsp+340h+var_320], rax
0x180008ee3  mov     edx, 40h ; '@'; unsigned __int64
0x180008ee8  lea     rcx, [rsp+340h+var_2D0]; unsigned __int16 *
0x180008eed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008ef2  mov     ebx, eax
0x180008ef4  test    eax, eax
0x180008ef6  js      loc_1800090C0
0x180008efc  mov     rax, [rsi]
0x180008eff  lea     rcx, [rsp+340h+lpSrc]
0x180008f04  mov     [rsp+340h+var_318], rcx
0x180008f09  lea     r8, [rsp+340h+var_2D0]
0x180008f0e  xor     r9d, r9d
0x180008f11  mov     [rsp+340h+lpSrc], r12
0x180008f16  mov     rdx, r15
0x180008f19  mov     dword ptr [rsp+340h+var_320], 1
0x180008f21  mov     rax, [rax+30h]
0x180008f25  mov     rcx, rsi
0x180008f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2d  mov     ebx, eax
0x180008f2f  test    eax, eax
0x180008f31  js      loc_1800090B5
0x180008f37  cmp     [rbp+240h+arg_38], 1
0x180008f3e  jz      loc_180009012
0x180008f44  mov     rcx, [rsp+340h+lpSrc]; lpSrc
0x180008f49  lea     rdx, [rbp+240h+Dst]; lpDst
0x180008f4d  mov     r8d, 104h; nSize
0x180008f53  call    cs:__imp_ExpandEnvironmentStringsW
0x180008f59  cmp     eax, 104h
0x180008f5e  ja      loc_1800090A9
0x180008f64  lea     r9, [rsp+340h+ppv]; ppv
0x180008f69  mov     [rsp+340h+ppv], r12
0x180008f6e  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180008f75  xor     edx, edx; pbc
0x180008f77  lea     rcx, [rbp+240h+Dst]; pszPath
0x180008f7b  call    cs:__imp_SHCreateItemFromParsingName
0x180008f81  mov     ebx, eax
0x180008f83  test    eax, eax
0x180008f85  jns     loc_180009046
0x180008f8b  mov     rcx, [rsp+340h+lpSrc]; pv
0x180008f90  call    cs:__imp_CoTaskMemFree
0x180008f96  mov     eax, ebx
0x180008f98  mov     rcx, [rbp+240h+var_40]
0x180008f9f  xor     rcx, rsp; StackCookie
0x180008fa2  call    __security_check_cookie
0x180008fa7  mov     rbx, [rsp+340h+arg_18]
0x180008faf  add     rsp, 310h
0x180008fb6  pop     r15
0x180008fb8  pop     r14
0x180008fba  pop     r13
0x180008fbc  pop     r12
0x180008fbe  pop     rdi
0x180008fbf  pop     rsi
0x180008fc0  pop     rbp
0x180008fc1  retn
0x180008fc2  mov     rcx, [rsp+340h+pstm+8]; pstm
0x180008fc7  lea     rdx, [rsp+340h+lpSrc]; pidl
0x180008fcc  mov     [rsp+340h+lpSrc], 0
0x180008fd5  call    cs:__imp_ILLoadFromStreamEx
0x180008fdb  mov     ebx, eax
0x180008fdd  test    eax, eax
0x180008fdf  js      short loc_180008FFD
0x180008fe1  mov     rdx, [rsp+340h+lpSrc]; pidl2
0x180008fe6  mov     rcx, r12; pidl1
0x180008fe9  call    cs:__imp_ILCombine
0x180008fef  mov     rcx, [rsp+340h+lpSrc]; pidl
0x180008ff4  mov     [r14], rax
0x180008ff7  call    cs:__imp_ILFree
0x180008ffd  lea     rcx, [rsp+340h+pstm]; pvar
0x180009002  call    cs:__imp_PropVariantClear
0x180009008  jmp     short loc_180008F96
0x18000900a  mov     byte ptr [rdi], 1
0x18000900d  jmp     loc_180008ECD
0x180009012  mov     rcx, [rsp+340h+lpSrc]; unsigned __int16 *
0x180009017  lea     r9, [rsp+340h+ppv]; unsigned int *
0x18000901c  mov     dword ptr [rsp+340h+ppv], 0FFFFFFFFh
0x180009024  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x180009029  cmp     dword ptr [rsp+340h+ppv], r12d
0x18000902e  jz      loc_180008F44
0x180009034  call    ?s_IsUncPathAllowedForThumbnailImage@CFileSource@@SAHXZ; CFileSource::s_IsUncPathAllowedForThumbnailImage(void)
0x180009039  test    eax, eax
0x18000903b  jz      loc_180008F8B
0x180009041  jmp     loc_180008F44
0x180009046  mov     rcx, [rsp+340h+ppv]; struct IShellItem *
0x18000904b  test    r13b, r13b
0x18000904e  jz      short loc_180009088
0x180009050  lea     rdx, [rsp+340h+punk]; struct IShellItem **
0x180009055  mov     [rsp+340h+punk], r12
0x18000905a  call    ?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z; GetFilteredShellItem(IShellItem *,IShellItem * *)
0x18000905f  mov     ebx, eax
0x180009061  test    eax, eax
0x180009063  js      short loc_180009093
0x180009065  mov     rcx, [rsp+340h+punk]; punk
0x18000906a  mov     rdx, r14; ppidl
0x18000906d  call    cs:__imp_SHGetIDListFromObject
0x180009073  mov     rcx, [rsp+340h+punk]
0x180009078  mov     ebx, eax
0x18000907a  mov     rax, [rcx]
0x18000907d  mov     rax, [rax+10h]
0x180009081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009086  jmp     short loc_180009093
0x180009088  mov     rdx, r14; ppidl
0x18000908b  call    cs:__imp_SHGetIDListFromObject
0x180009091  mov     ebx, eax
0x180009093  mov     rcx, [rsp+340h+ppv]
0x180009098  mov     rax, [rcx]
0x18000909b  mov     rax, [rax+10h]
0x18000909f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a4  jmp     loc_180008F8B
0x1800090a9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800090ae  mov     ebx, eax
0x1800090b0  jmp     loc_180008F8B
0x1800090b5  test    rdi, rdi
0x1800090b8  jz      loc_180008F96
0x1800090be  jmp     short loc_1800090C9
0x1800090c0  test    rdi, rdi
0x1800090c3  jz      loc_180008F96
0x1800090c9  mov     [rdi], r12b
0x1800090cc  jmp     loc_180008F96
```
