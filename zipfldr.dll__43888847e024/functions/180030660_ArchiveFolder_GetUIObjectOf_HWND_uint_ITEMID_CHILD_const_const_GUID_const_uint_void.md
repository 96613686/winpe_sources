# ArchiveFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180030660`
- end: `0x180030a18`
- name: `?GetUIObjectOf@ArchiveFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `952`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, HWND, int, const struct _ITEMIDLIST_RELATIVE **, const struct _GUID *riid, unsigned int *, void **ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000f1c0`
- `0x18000f5f0`
- `0x180020708`
- `0x180030618`
- `0x180030660`
- `0x180030a3c`
- `0x180030a68`
- `0x180031e94`
- `0x180036f50`
- `0x180049530`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x1800309c3`
- `SHELL32!SHCreateDataObject` at `0x1800309c3`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x1800308f0`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x1800308f0`

## pseudocode

```c
__int64 __fastcall ArchiveFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        int a3,
        const struct _ITEMIDLIST_RELATIVE **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  const struct _GUID *v8; // rbx
  void **v9; // r14
  const struct ArchiveIdList *v11; // rsi
  UINT v12; // r10d
  LPCITEMIDLIST *v13; // r11
  unsigned int i; // r9d
  int v15; // r9d
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // edi
  HRESULT IconW; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  HRESULT v30; // eax
  unsigned int v31; // ebx
  int v32; // [rsp+20h] [rbp-68h]
  int v33; // [rsp+20h] [rbp-68h]
  int v34; // [rsp+20h] [rbp-68h]
  __int64 (__fastcall ***v35)(_QWORD, const struct _GUID *, void **); // [rsp+30h] [rbp-58h] BYREF
  LPCWSTR pszFile[2]; // [rsp+38h] [rbp-50h] BYREF
  int v37[2]; // [rsp+48h] [rbp-40h] BYREF
  int v38; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HWND v40; // [rsp+98h] [rbp+10h] BYREF

  v40 = a2;
  v38 = a3;
  *(_QWORD *)v37 = a4;
  v8 = riid;
  v9 = ppv;
  *ppv = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
      (const char *)0x80070057LL,
      v32);
    return 2147942487LL;
  }
  v11 = ArchiveIdList::FromPIDL(*a4);
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
      (const char *)0x80070057LL,
      v32);
    return 2147942487LL;
  }
  for ( i = 1; i < v12; i = v15 + 1 )
  {
    if ( !ArchiveIdList::FromPIDL((const struct _ITEMIDLIST_RELATIVE *)v13[i]) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
        (const char *)0x80070057LL,
        v32);
      return 2147942487LL;
    }
  }
  v16 = *(_QWORD *)&v8->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&v8->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v16 = *(_QWORD *)v8->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( v16 )
  {
    v21 = *(_QWORD *)&v8->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
    if ( *(_QWORD *)&v8->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
      v21 = *(_QWORD *)v8->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
    if ( v21 )
    {
      v26 = *(_QWORD *)&v8->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
      if ( *(_QWORD *)&v8->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
        v26 = *(_QWORD *)v8->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
      if ( v26 )
      {
        v29 = *(_QWORD *)&v8->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
        if ( *(_QWORD *)&v8->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
          v29 = *(_QWORD *)v8->Data4 - *(_QWORD *)IID_IDataObject.Data4;
        if ( v29 )
          return 2147500033LL;
        v30 = SHCreateDataObject(this[16], v12, v13, 0, v8, v9);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BF,
            (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
            (const char *)(unsigned int)v30,
            v34);
          return v31;
        }
      }
      else
      {
        v27 = ArchiveFolder::AssocCreate(v11, v8, v9);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BB,
            (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
            (const char *)(unsigned int)v27,
            v32);
          return v28;
        }
      }
    }
    else
    {
      if ( v12 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
          (const char *)0x80070057LL,
          v32);
        return 2147942487LL;
      }
      *(_OWORD *)pszFile = 0;
      v22 = CTempAlignedString::Set(
              (CTempAlignedString *)pszFile,
              (const unsigned __int16 *)v11 + *((unsigned __int16 *)v11 + 15) + 16);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
          (const char *)(unsigned int)v22,
          v32);
        CTempAlignedString::Clear((CTempAlignedString *)pszFile);
        return v23;
      }
      IconW = SHCreateFileExtractIconW(pszFile[0], *((_DWORD *)v11 + 1), v8, v9);
      v25 = IconW;
      if ( IconW < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
          (const char *)(unsigned int)IconW,
          v32);
        CTempAlignedString::Clear((CTempAlignedString *)pszFile);
        return v25;
      }
      CTempAlignedString::Clear((CTempAlignedString *)pszFile);
    }
    return 0;
  }
  v17 = ArchiveFolder::EnsureMainEnumerator((ArchiveFolder *)this);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
      (const char *)(unsigned int)v17,
      v32);
    return v18;
  }
  pszFile[0] = (LPCWSTR)this;
  winrt::make<ArchiveItemContextMenu,HWND__ * &,ArchiveFolder *,unsigned int &,_ITEMID_CHILD const __unaligned * const * &>(
    (unsigned int)&v35,
    (unsigned int)&v40,
    (unsigned int)pszFile,
    (unsigned int)&v38,
    (__int64)v37);
  v19 = (**v35)(v35, v8, v9);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( v35 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v35);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AB,
    (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
    (const char *)(unsigned int)v19,
    v33);
  if ( v35 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v35);
  return v20;
}

```

## disassembly

```asm
0x180030660  mov     [rsp+arg_8], rdx
0x180030665  push    rbx
0x180030666  push    rsi
0x180030667  push    rdi
0x180030668  push    r14
0x18003066a  push    r15
0x18003066c  sub     rsp, 60h
0x180030670  mov     rax, cs:__security_cookie
0x180030677  xor     rax, rsp
0x18003067a  mov     [rsp+88h+var_30], rax
0x18003067f  mov     r11, r9
0x180030682  mov     r10d, r8d
0x180030685  mov     r15, rcx
0x180030688  mov     [rsp+88h+var_38], r8d
0x18003068d  mov     qword ptr [rsp+88h+var_40], r9
0x180030692  mov     rbx, [rsp+88h+riid]
0x18003069a  mov     r14, [rsp+88h+ppv]
0x1800306a2  mov     qword ptr [r14], 0
0x1800306a9  test    r8d, r8d
0x1800306ac  jnz     short loc_1800306D6
0x1800306ae  mov     rcx, [rsp+88h]; this
0x1800306b6  mov     ebx, 80070057h
0x1800306bb  mov     r9d, ebx; char *
0x1800306be  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x1800306c5  mov     edx, 19Dh; void *
0x1800306ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800306cf  mov     eax, ebx
0x1800306d1  jmp     loc_1800309FE
0x1800306d6  mov     rcx, [r9]; struct _ITEMIDLIST_RELATIVE *
0x1800306d9  call    ?FromPIDL@ArchiveIdList@@SAPEFBU1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ArchiveIdList::FromPIDL(_ITEMIDLIST_RELATIVE const *)
0x1800306de  mov     rsi, rax
0x1800306e1  test    rax, rax
0x1800306e4  jnz     short loc_18003070E
0x1800306e6  mov     rcx, [rsp+88h]; this
0x1800306ee  mov     ebx, 80070057h
0x1800306f3  mov     r9d, ebx; char *
0x1800306f6  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x1800306fd  mov     edx, 1A1h; void *
0x180030702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030707  mov     eax, ebx
0x180030709  jmp     loc_1800309FE
0x18003070e  mov     r9d, 1
0x180030714  cmp     r9d, r10d
0x180030717  jnb     short loc_180030757
0x180030719  mov     ecx, r9d
0x18003071c  mov     rcx, [r11+rcx*8]; struct _ITEMIDLIST_RELATIVE *
0x180030720  call    ?FromPIDL@ArchiveIdList@@SAPEFBU1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ArchiveIdList::FromPIDL(_ITEMIDLIST_RELATIVE const *)
0x180030725  test    rax, rax
0x180030728  jnz     short loc_180030752
0x18003072a  mov     rcx, [rsp+88h]; this
0x180030732  mov     ebx, 80070057h
0x180030737  mov     r9d, ebx; char *
0x18003073a  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x180030741  mov     edx, 1A4h; void *
0x180030746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003074b  mov     eax, ebx
0x18003074d  jmp     loc_1800309FE
0x180030752  inc     r9d
0x180030755  jmp     short loc_180030714
0x180030757  mov     rax, [rbx]
0x18003075a  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180030761  jnz     short loc_18003076E
0x180030763  mov     rax, [rbx+8]
0x180030767  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18003076e  test    rax, rax
0x180030771  jnz     loc_180030841
0x180030777  mov     rcx, r15; this
0x18003077a  call    ?EnsureMainEnumerator@ArchiveFolder@@AEAAJXZ; ArchiveFolder::EnsureMainEnumerator(void)
0x18003077f  mov     edi, eax
0x180030781  test    eax, eax
0x180030783  jns     short loc_1800307A8
0x180030785  mov     rcx, [rsp+88h]; this
0x18003078d  mov     r9d, eax; char *
0x180030790  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x180030797  mov     edx, 1A9h; void *
0x18003079c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800307a1  mov     eax, edi
0x1800307a3  jmp     loc_1800309FE
0x1800307a8  mov     [rsp+88h+pszFile], r15
0x1800307ad  lea     rax, [rsp+88h+var_40]
0x1800307b2  mov     [rsp+88h+var_68], rax; int
0x1800307b7  lea     r9, [rsp+88h+var_38]
0x1800307bc  lea     r8, [rsp+88h+pszFile]
0x1800307c1  lea     rdx, [rsp+88h+arg_8]
0x1800307c9  lea     rcx, [rsp+88h+var_58]
0x1800307ce  call    ??$make@UArchiveItemContextMenu@@AEAPEAUHWND__@@PEAVArchiveFolder@@AEAIAEAPEBQEFBU_ITEMID_CHILD@@@winrt@@YA?A_PAEAPEAUHWND__@@$$QEAPEAVArchiveFolder@@AEAIAEAPEBQEFBU_ITEMID_CHILD@@@Z
0x1800307d3  nop
0x1800307d4  mov     rcx, [rsp+88h+var_58]
0x1800307d9  mov     rax, [rcx]
0x1800307dc  mov     r8, r14
0x1800307df  mov     rdx, rbx
0x1800307e2  mov     rax, [rax]
0x1800307e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307ea  mov     ebx, eax
0x1800307ec  test    eax, eax
0x1800307ee  jns     short loc_180030826
0x1800307f0  mov     rcx, [rsp+88h]; this
0x1800307f8  mov     r9d, eax; char *
0x1800307fb  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x180030802  mov     edx, 1ABh; void *
0x180030807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003080c  nop
0x18003080d  cmp     [rsp+88h+var_58], 0
0x180030813  jz      short loc_18003081F
0x180030815  lea     rcx, [rsp+88h+var_58]
0x18003081a  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18003081f  mov     eax, ebx
0x180030821  jmp     loc_1800309FE
0x180030826  cmp     [rsp+88h+var_58], 0
0x18003082c  jz      loc_1800309EF
0x180030832  lea     rcx, [rsp+88h+var_58]
0x180030837  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18003083c  jmp     loc_1800309EF
0x180030841  mov     rax, [rbx]
0x180030844  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x18003084b  jnz     short loc_180030858
0x18003084d  mov     rax, [rbx+8]
0x180030851  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180030858  test    rax, rax
0x18003085b  jnz     loc_180030939
0x180030861  cmp     r10d, 1
0x180030865  jz      short loc_18003088F
0x180030867  mov     rcx, [rsp+88h]; this
0x18003086f  mov     ebx, 80070057h
0x180030874  mov     r9d, ebx; char *
0x180030877  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18003087e  mov     edx, 1AFh; void *
0x180030883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030888  mov     eax, ebx
0x18003088a  jmp     loc_1800309FE
0x18003088f  xorps   xmm0, xmm0
0x180030892  movdqu  xmmword ptr [rsp+88h+pszFile], xmm0
0x180030898  movzx   eax, word ptr [rsi+1Eh]
0x18003089c  add     rax, 10h
0x1800308a0  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x1800308a4  lea     rcx, [rsp+88h+pszFile]; this
0x1800308a9  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x1800308ae  mov     edi, eax
0x1800308b0  test    eax, eax
0x1800308b2  jns     short loc_1800308E2
0x1800308b4  mov     rcx, [rsp+88h]; this
0x1800308bc  mov     r9d, eax; char *
0x1800308bf  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x1800308c6  mov     edx, 1B2h; void *
0x1800308cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800308d0  nop
0x1800308d1  lea     rcx, [rsp+88h+pszFile]; this
0x1800308d6  call    ?Clear@CTempAlignedString@@QEAAXXZ; CTempAlignedString::Clear(void)
0x1800308db  mov     eax, edi
0x1800308dd  jmp     loc_1800309FE
0x1800308e2  mov     r9, r14; ppv
0x1800308e5  mov     r8, rbx; riid
0x1800308e8  mov     edx, [rsi+4]; dwFileAttributes
0x1800308eb  mov     rcx, [rsp+88h+pszFile]; pszFile
0x1800308f0  call    cs:__imp_SHCreateFileExtractIconW
0x1800308f6  mov     ebx, eax
0x1800308f8  test    eax, eax
0x1800308fa  jns     short loc_18003092A
0x1800308fc  mov     rcx, [rsp+88h]; this
0x180030904  mov     r9d, eax; char *
0x180030907  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18003090e  mov     edx, 1B7h; void *
0x180030913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030918  nop
0x180030919  lea     rcx, [rsp+88h+pszFile]; this
0x18003091e  call    ?Clear@CTempAlignedString@@QEAAXXZ; CTempAlignedString::Clear(void)
0x180030923  mov     eax, ebx
0x180030925  jmp     loc_1800309FE
0x18003092a  lea     rcx, [rsp+88h+pszFile]; this
0x18003092f  call    ?Clear@CTempAlignedString@@QEAAXXZ; CTempAlignedString::Clear(void)
0x180030934  jmp     loc_1800309EF
0x180030939  mov     rax, [rbx]
0x18003093c  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180030943  jnz     short loc_180030950
0x180030945  mov     rax, [rbx+8]
0x180030949  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180030950  test    rax, rax
0x180030953  jnz     short loc_18003098D
0x180030955  mov     r8, r14; void **
0x180030958  mov     rdx, rbx; struct _GUID *
0x18003095b  mov     rcx, rsi; struct ArchiveIdList *
0x18003095e  call    ?AssocCreate@ArchiveFolder@@CAJPEFBUArchiveIdList@@AEBU_GUID@@PEAPEAX@Z; ArchiveFolder::AssocCreate(ArchiveIdList const *,_GUID const &,void * *)
0x180030963  mov     ebx, eax
0x180030965  test    eax, eax
0x180030967  jns     loc_1800309EF
0x18003096d  mov     rcx, [rsp+88h]; this
0x180030975  mov     r9d, eax; char *
0x180030978  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18003097f  mov     edx, 1BBh; void *
0x180030984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030989  mov     eax, ebx
0x18003098b  jmp     short loc_1800309FE
0x18003098d  mov     rax, [rbx]
0x180030990  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180030997  jnz     short loc_1800309A4
0x180030999  mov     rax, [rbx+8]
0x18003099d  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800309a4  test    rax, rax
0x1800309a7  jnz     short loc_1800309F3
0x1800309a9  mov     [rsp+88h+var_60], r14; ppv
0x1800309ae  mov     [rsp+88h+var_68], rbx; int
0x1800309b3  xor     r9d, r9d; pdtInner
0x1800309b6  mov     r8, r11; apidl
0x1800309b9  mov     edx, r10d; cidl
0x1800309bc  mov     rcx, [r15+80h]; pidlFolder
0x1800309c3  call    cs:__imp_SHCreateDataObject
0x1800309c9  mov     ebx, eax
0x1800309cb  test    eax, eax
0x1800309cd  jns     short loc_1800309EF
0x1800309cf  mov     rcx, [rsp+88h]; this
0x1800309d7  mov     r9d, eax; char *
0x1800309da  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x1800309e1  mov     edx, 1BFh; void *
0x1800309e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800309eb  mov     eax, ebx
0x1800309ed  jmp     short loc_1800309FE
0x1800309ef  xor     eax, eax
0x1800309f1  jmp     short loc_1800309FE
0x1800309f3  mov     eax, 80004001h
0x1800309f8  jmp     short loc_1800309FE
0x1800309fa  mov     eax, [rsp+88h+var_38]
0x1800309fe  mov     rcx, [rsp+88h+var_30]
0x180030a03  xor     rcx, rsp; StackCookie
0x180030a06  call    __security_check_cookie
0x180030a0b  add     rsp, 60h
0x180030a0f  pop     r15
0x180030a11  pop     r14
0x180030a13  pop     rdi
0x180030a14  pop     rsi
0x180030a15  pop     rbx
0x180030a16  retn
```
