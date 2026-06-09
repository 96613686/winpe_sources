# CZipFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x180012de0`
- end: `0x1800130eb`
- name: `?GetUIObjectOf@CZipFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `779`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, IID *riid, unsigned int *, void **ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x18000d9b0`
- `0x18000ed94`
- `0x18000f5f0`
- `0x180012de0`
- `0x1800130f4`
- `0x180013178`
- `0x180013308`
- `0x180013904`
- `0x180036f50`
- `0x18003732c`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x180012f79`
- `SHELL32!SHCreateDataObject` at `0x180012f79`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180012eed`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180012eed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ffd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ffd`

## pseudocode

```c
__int64 __fastcall CZipFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        WCHAR *a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        IID *riid,
        unsigned int *a6,
        void **ppv)
{
  HRESULT IconW; // ebx
  CZipFolder *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  IDataObject *v16; // r14
  int v17; // eax
  WCHAR *v18; // rsi
  CObjectWithSite *v20; // rax
  IDataObject *v21; // rsi
  HRESULT v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  struct IDataObjectVtbl *lpVtbl; // rax
  IDataObject *v26; // rcx
  LPCITEMIDLIST v27; // rax
  const struct _ITEMIDLIST *v28; // rdx
  LPCWSTR pszFile[2]; // [rsp+30h] [rbp-28h] BYREF
  IDataObject *pdtInner; // [rsp+40h] [rbp-18h] BYREF

  pszFile[0] = a2;
  pdtInner = 0;
  *ppv = 0;
  IconW = CArchiveIDList::_ValidateItemArray(a3, a4, (const struct CArchiveIDList **)&pdtInner);
  if ( IconW < 0 )
    return (unsigned int)IconW;
  IconW = CZipFolder::BuildMainEnumerator((CZipFolder *)this, (HWND)a2);
  if ( IconW < 0 )
    return (unsigned int)IconW;
  v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v13 )
  {
    v20 = (CObjectWithSite *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = (IDataObject *)v20;
    if ( !v20 )
      return (unsigned int)-2147024882;
    CObjectWithSite::CObjectWithSite(v20);
    v21[2].lpVtbl = (struct IDataObjectVtbl *)&CArchiveItemContextMenu::`vftable'{for `IContextMenu'};
    v21->lpVtbl = (struct IDataObjectVtbl *)&CArchiveItemContextMenu::`vftable'{for `CObjectWithSite'};
    v21[6].lpVtbl = 0;
    v21[7].lpVtbl = 0;
    LODWORD(v21[3].lpVtbl) = 1;
    v21[4].lpVtbl = 0;
    v21[5].lpVtbl = 0;
    ZipInit();
    IconW = ((__int64 (__fastcall *)(IDataObject *, LPCWSTR, _QWORD, const struct _ITEMIDLIST **, LPCITEMIDLIST *))v21->lpVtbl->GetCanonicalFormatEtc)(
              v21,
              pszFile[0],
              a3,
              a4,
              this);
    if ( IconW >= 0 )
      IconW = ((__int64 (__fastcall *)(IDataObject *, IID *, void **))v21->lpVtbl->QueryInterface)(v21, riid, ppv);
    lpVtbl = v21->lpVtbl;
    v26 = v21;
LABEL_34:
    ((void (__fastcall *)(IDataObject *))lpVtbl->Release)(v26);
    return (unsigned int)IconW;
  }
  v14 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v14 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v14 )
  {
    pdtInner = 0;
    IconW = CArchiveItemDataObject_CreateFromIDArray((struct CZipFolder *)this, a3, a4, &pdtInner);
    if ( IconW < 0 )
      return (unsigned int)IconW;
    v22 = SHCreateDataObject(this[139], a3, a4, pdtInner, riid, ppv);
LABEL_35:
    v26 = pdtInner;
    IconW = v22;
    lpVtbl = pdtInner->lpVtbl;
    goto LABEL_34;
  }
  v15 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
    v15 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
  if ( v15 )
  {
    v23 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
      v23 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
    if ( v23 )
    {
      v24 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
        v24 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
      if ( !v24 )
        return (unsigned int)CZipFolder::_AssocCreate(v12, (const struct CArchiveIDList *)pdtInner, riid, ppv);
      return (unsigned int)-2147467263;
    }
    if ( ((__int64)pdtInner[4].lpVtbl & 0x10) == 0 )
      return (unsigned int)-2147467263;
    v27 = *this;
    v28 = *a4;
    pdtInner = 0;
    IconW = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, const struct _ITEMIDLIST *, _QWORD, GUID *, IDataObject **))((char *)&v27[13].mkid.cb + 1))(
              this,
              v28,
              0,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &pdtInner);
    if ( IconW < 0 )
      return (unsigned int)IconW;
    v22 = ((__int64 (__fastcall *)(IDataObject *, WCHAR *, IID *, void **))pdtInner->lpVtbl->EnumFormatEtc)(
            pdtInner,
            a2,
            riid,
            ppv);
    goto LABEL_35;
  }
  v16 = pdtInner;
  *(_OWORD *)pszFile = 0;
  v17 = CTempAlignedString::Set((CTempAlignedString *)pszFile, (const unsigned __int16 *)&pdtInner[11].lpVtbl + 2);
  v18 = (WCHAR *)pszFile[0];
  IconW = v17;
  if ( v17 >= 0 )
    IconW = SHCreateFileExtractIconW(pszFile[0], (__int64)v16[4].lpVtbl & 0xFFFFEFFF, riid, ppv);
  if ( v18 != pszFile[1] && v18 != &psz )
    LocalFree(v18);
  return (unsigned int)IconW;
}

```

## disassembly

```asm
0x180012de0  push    rbp
0x180012de2  push    rbx
0x180012de3  push    rsi
0x180012de4  push    rdi
0x180012de5  push    r12
0x180012de7  push    r13
0x180012de9  push    r14
0x180012deb  push    r15
0x180012ded  mov     rbp, rsp
0x180012df0  sub     rsp, 58h
0x180012df4  mov     rax, cs:__security_cookie
0x180012dfb  xor     rax, rsp
0x180012dfe  mov     [rbp+var_10], rax
0x180012e02  mov     r15, [rbp+ppv]
0x180012e06  mov     r13d, r8d
0x180012e09  mov     rdi, [rbp+riid]
0x180012e0d  lea     r8, [rbp+pdtInner]; struct CArchiveIDList **
0x180012e11  mov     rsi, rdx
0x180012e14  mov     [rbp+pszFile], rdx
0x180012e18  mov     r14, rcx
0x180012e1b  mov     [rbp+pdtInner], 0
0x180012e23  mov     rdx, r9; struct _ITEMIDLIST **
0x180012e26  mov     qword ptr [r15], 0
0x180012e2d  mov     ecx, r13d; unsigned int
0x180012e30  mov     r12, r9
0x180012e33  call    ?_ValidateItemArray@CArchiveIDList@@SAJIPEAPEFBU_ITEMIDLIST@@PEAPEBV1@@Z; CArchiveIDList::_ValidateItemArray(uint,_ITEMIDLIST const * *,CArchiveIDList const * *)
0x180012e38  mov     ebx, eax
0x180012e3a  test    eax, eax
0x180012e3c  js      loc_180012EFF
0x180012e42  mov     rdx, rsi; HWND
0x180012e45  mov     rcx, r14; this
0x180012e48  call    ?BuildMainEnumerator@CZipFolder@@QEAAJPEAUHWND__@@@Z; CZipFolder::BuildMainEnumerator(HWND__ *)
0x180012e4d  mov     ebx, eax
0x180012e4f  test    eax, eax
0x180012e51  js      loc_180012EFF
0x180012e57  mov     rax, [rdi]
0x180012e5a  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180012e61  jnz     short loc_180012E6E
0x180012e63  mov     rax, [rdi+8]
0x180012e67  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180012e6e  xor     ebx, ebx
0x180012e70  test    rax, rax
0x180012e73  jz      loc_180012F1E
0x180012e79  mov     rax, [rdi]
0x180012e7c  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180012e83  jnz     short loc_180012E90
0x180012e85  mov     rax, [rdi+8]
0x180012e89  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180012e90  test    rax, rax
0x180012e93  jz      loc_180012F42
0x180012e99  mov     rax, [rdi]
0x180012e9c  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180012ea3  jnz     short loc_180012EB0
0x180012ea5  mov     rax, [rdi+8]
0x180012ea9  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180012eb0  test    rax, rax
0x180012eb3  jnz     loc_180012F84
0x180012eb9  mov     r14, [rbp+pdtInner]
0x180012ebd  lea     rcx, [rbp+pszFile]; this
0x180012ec1  xorps   xmm0, xmm0
0x180012ec4  movdqu  xmmword ptr [rbp+pszFile], xmm0
0x180012ec9  lea     rdx, [r14+5Ch]; unsigned __int16 *
0x180012ecd  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x180012ed2  mov     rsi, [rbp+pszFile]
0x180012ed6  mov     ebx, eax
0x180012ed8  test    eax, eax
0x180012eda  js      short loc_180012EF5
0x180012edc  mov     edx, [r14+20h]
0x180012ee0  mov     r9, r15; ppv
0x180012ee3  btr     edx, 0Ch; dwFileAttributes
0x180012ee7  mov     r8, rdi; riid
0x180012eea  mov     rcx, rsi; pszFile
0x180012eed  call    cs:__imp_SHCreateFileExtractIconW
0x180012ef3  mov     ebx, eax
0x180012ef5  cmp     rsi, [rbp+pszFile+8]
0x180012ef9  jnz     loc_180012FEA
0x180012eff  mov     eax, ebx
0x180012f01  mov     rcx, [rbp+var_10]
0x180012f05  xor     rcx, rsp; StackCookie
0x180012f08  call    __security_check_cookie
0x180012f0d  add     rsp, 58h
0x180012f11  pop     r15
0x180012f13  pop     r14
0x180012f15  pop     r13
0x180012f17  pop     r12
0x180012f19  pop     rdi
0x180012f1a  pop     rsi
0x180012f1b  pop     rbx
0x180012f1c  pop     rbp
0x180012f1d  retn
0x180012f1e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012f25  mov     ecx, 40h ; '@'; unsigned __int64
0x180012f2a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012f2f  mov     rsi, rax
0x180012f32  test    rax, rax
0x180012f35  jnz     loc_180013008
0x180012f3b  mov     ebx, 8007000Eh
0x180012f40  jmp     short loc_180012EFF
0x180012f42  lea     r9, [rbp+pdtInner]; struct IDataObject **
0x180012f46  mov     [rbp+pdtInner], rbx
0x180012f4a  mov     r8, r12; struct _ITEMIDLIST **
0x180012f4d  mov     edx, r13d; unsigned int
0x180012f50  mov     rcx, r14; struct CZipFolder *
0x180012f53  call    ?CArchiveItemDataObject_CreateFromIDArray@@YAJPEAVCZipFolder@@IPEAPEFBU_ITEMIDLIST@@PEAPEAUIDataObject@@@Z; CArchiveItemDataObject_CreateFromIDArray(CZipFolder *,uint,_ITEMIDLIST const * *,IDataObject * *)
0x180012f58  mov     ebx, eax
0x180012f5a  test    eax, eax
0x180012f5c  js      short loc_180012EFF
0x180012f5e  mov     r9, [rbp+pdtInner]; pdtInner
0x180012f62  mov     r8, r12; apidl
0x180012f65  mov     rcx, [r14+458h]; pidlFolder
0x180012f6c  mov     edx, r13d; cidl
0x180012f6f  mov     [rsp+58h+var_30], r15; ppv
0x180012f74  mov     [rsp+58h+var_38], rdi; riid
0x180012f79  call    cs:__imp_SHCreateDataObject
0x180012f7f  jmp     loc_1800130AA
0x180012f84  mov     rax, [rdi]
0x180012f87  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180012f8e  jnz     short loc_180012F9B
0x180012f90  mov     rax, [rdi+8]
0x180012f94  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x180012f9b  test    rax, rax
0x180012f9e  jz      short loc_180012FD2
0x180012fa0  mov     rax, [rdi]
0x180012fa3  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180012faa  jnz     short loc_180012FB7
0x180012fac  mov     rax, [rdi+8]
0x180012fb0  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180012fb7  test    rax, rax
0x180012fba  jnz     short loc_180012FE0
0x180012fbc  mov     rdx, [rbp+pdtInner]; struct CArchiveIDList *
0x180012fc0  mov     r9, r15; void **
0x180012fc3  mov     r8, rdi; struct _GUID *
0x180012fc6  call    ?_AssocCreate@CZipFolder@@AEAAJPEBVCArchiveIDList@@AEBU_GUID@@PEAPEAX@Z; CZipFolder::_AssocCreate(CArchiveIDList const *,_GUID const &,void * *)
0x180012fcb  mov     ebx, eax
0x180012fcd  jmp     loc_180012EFF
0x180012fd2  mov     rax, [rbp+pdtInner]
0x180012fd6  test    byte ptr [rax+20h], 10h
0x180012fda  jnz     loc_1800130B5
0x180012fe0  mov     ebx, 80004001h
0x180012fe5  jmp     loc_180012EFF
0x180012fea  lea     rax, psz
0x180012ff1  cmp     rsi, rax
0x180012ff4  jz      loc_180012EFF
0x180012ffa  mov     rcx, rsi; hMem
0x180012ffd  call    cs:__imp_LocalFree
0x180013003  jmp     loc_180012EFF
0x180013008  mov     rcx, rsi; this
0x18001300b  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x180013010  lea     rax, ??_7CArchiveItemContextMenu@@6BIContextMenu@@@; const CArchiveItemContextMenu::`vftable'{for `IContextMenu'}
0x180013017  mov     [rsi+10h], rax
0x18001301b  lea     rcx, ??_7CArchiveItemContextMenu@@6BCObjectWithSite@@@; const CArchiveItemContextMenu::`vftable'{for `CObjectWithSite'}
0x180013022  mov     [rsi], rcx
0x180013025  mov     [rsi+30h], rbx
0x180013029  mov     [rsi+38h], rbx
0x18001302d  mov     dword ptr [rsi+18h], 1
0x180013034  mov     [rsi+20h], rbx
0x180013038  mov     [rsi+28h], rbx
0x18001303c  call    ?ZipInit@@YAXXZ; ZipInit(void)
0x180013041  mov     rax, [rsi]
0x180013044  mov     r9, r12
0x180013047  mov     rdx, [rbp+pszFile]
0x18001304b  mov     r8d, r13d
0x18001304e  mov     rcx, rsi
0x180013051  mov     [rsp+58h+var_38], r14
0x180013056  mov     rax, [rax+30h]
0x18001305a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001305f  mov     ebx, eax
0x180013061  test    eax, eax
0x180013063  jns     short loc_180013079
0x180013065  mov     rax, [rsi]
0x180013068  mov     rcx, rsi
0x18001306b  mov     rax, [rax+10h]
0x18001306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013074  jmp     loc_180012EFF
0x180013079  mov     rax, [rsi]
0x18001307c  mov     r8, r15
0x18001307f  mov     rdx, rdi
0x180013082  mov     rcx, rsi
0x180013085  mov     rax, [rax]
0x180013088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001308d  mov     ebx, eax
0x18001308f  jmp     short loc_180013065
0x180013091  mov     rcx, [rbp+pdtInner]
0x180013095  mov     r9, r15
0x180013098  mov     r8, rdi
0x18001309b  mov     rdx, rsi
0x18001309e  mov     rax, [rcx]
0x1800130a1  mov     rax, [rax+40h]
0x1800130a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130aa  mov     rcx, [rbp+pdtInner]
0x1800130ae  mov     ebx, eax
0x1800130b0  mov     rax, [rcx]
0x1800130b3  jmp     short loc_18001306B
0x1800130b5  mov     rax, [r14]
0x1800130b8  lea     rcx, [rbp+pdtInner]
0x1800130bc  mov     rdx, [r12]
0x1800130c0  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800130c7  mov     [rsp+58h+var_38], rcx
0x1800130cc  xor     r8d, r8d
0x1800130cf  mov     rcx, r14
0x1800130d2  mov     [rbp+pdtInner], rbx
0x1800130d6  mov     rax, [rax+28h]
0x1800130da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130df  mov     ebx, eax
0x1800130e1  test    eax, eax
0x1800130e3  js      loc_180012EFF
0x1800130e9  jmp     short loc_180013091
```
