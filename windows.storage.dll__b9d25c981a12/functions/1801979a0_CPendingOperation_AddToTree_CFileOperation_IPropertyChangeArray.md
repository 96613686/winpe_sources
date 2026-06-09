# CPendingOperation::AddToTree(CFileOperation *,IPropertyChangeArray *)

- ea: `0x1801979a0`
- end: `0x180197e6e`
- name: `?AddToTree@CPendingOperation@@UEAAJPEAVCFileOperation@@PEAUIPropertyChangeArray@@@Z`
- size: `1230`
- prototype: `int(CPendingOperation *__hidden this, struct CFileOperation *, struct IPropertyChangeArray *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1801183a0`
- `0x180133f50`
- `0x180135090`
- `0x180194e30`
- `0x1801979a0`
- `0x180197ea0`
- `0x180198104`
- `0x180198240`
- `0x180198380`
- `0x18019848c`
- `0x1801989b4`
- `0x180198fe8`
- `0x18019ae60`
- `0x18019aef0`
- `0x18019f788`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180197e28`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180197e28`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180197d86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180197d86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180197d97`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180197d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180197e58`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180197ce5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180197cf9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180197ce5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180197cf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPendingOperation::AddToTree(
        CPendingOperation *this,
        struct CFileOperation *a2,
        struct IPropertyChangeArray *a3)
{
  int v5; // r13d
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int FileName; // ebx
  WCHAR *v10; // rsi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, void **); // rcx
  CRecursiveFolderOperation *v12; // rax
  CRecursiveFolderOperation *v13; // rbx
  CRecursiveFolderOperation *v14; // rsi
  CRecursiveFolderOperation *v16; // rax
  CRecursiveFolderOperation *v17; // r14
  const unsigned __int16 *ExtensionW; // rax
  CUndoRoot *v19; // rax
  CUndoRoot *v20; // rbx
  CUndoRoot *v21; // rax
  CUndoRoot *v22; // r12
  HRESULT v23; // ebx
  void **v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertyChangeArray *v26; // [rsp+58h] [rbp-A8h]
  LPCWSTR v27; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  void *ppv[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPath[256]; // [rsp+90h] [rbp-70h] BYREF

  v26 = a3;
  v5 = 0;
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    LODWORD(v27) = 0;
    v7 = 4259840;
    if ( *((_DWORD *)this + 2) != 3 )
      v7 = 0x400000;
    v8 = v7;
    LODWORD(v8) = v7 | 0x20000000;
    (*(void (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v6 + 48LL))(v6, v8, &v27);
    if ( (v7 & (unsigned int)v27) == 0 && ((unsigned int)v27 & 0x20000000) != 0 )
    {
      v5 = 1;
    }
    else if ( ((unsigned int)v27 & 0x20400000) == 0x20400000 )
    {
      v5 = 2;
    }
  }
  FileName = 0;
  v10 = (WCHAR *)((char *)this + 32);
  if ( *((_DWORD *)this + 2) == 4 && (*((_DWORD *)a2 + 21) & 0x200000) != 0 )
  {
    FileName = StringCchCopyW(pszPath, 0xFFu, (const unsigned __int16 *)this + 16);
    if ( FileName < 0 )
      return (unsigned int)FileName;
    v27 = 0;
    FileName = IShellItem_GetFileName(*((struct IShellItem **)this + 2), (unsigned __int16 **)&v27);
    if ( FileName < 0 )
      return (unsigned int)FileName;
    PathRemoveExtensionW(pszPath);
    ExtensionW = PathFindExtensionW(v27);
    FileName = StringCchCatW(pszPath, 0xFFu, ExtensionW);
    CoTaskMemFree((LPVOID)v27);
    if ( FileName < 0 )
      return (unsigned int)FileName;
    v10 = pszPath;
  }
  pv = 0;
  if ( (int)GetFileSystemOrPlaceholderPath(*((struct IShellItem **)this + 2), (unsigned __int16 **)&pv) >= 0 )
  {
    FileName = CCopyTree::DiskCheck((struct CFileOperation *)((char *)a2 + 320), (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
  }
  if ( FileName >= 0 )
  {
    v29 = 0;
    if ( (int)IShellItem_GetFileName(*((struct IShellItem **)this + 2), &v29) >= 0 )
    {
      v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 2);
      v27 = 0;
      v30 = 0;
      ppv[0] = 0;
      FileName = (**v11)(v11, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, ppv);
      if ( FileName >= 0 )
      {
        v25 = 0;
        FileName = (*(__int64 (__fastcall **)(void *, _QWORD, __int64 *, LPCWSTR *))(*(_QWORD *)ppv[0] + 32LL))(
                     ppv[0],
                     0,
                     &v25,
                     &v27);
        if ( FileName >= 0 )
        {
          FileName = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
                       v25,
                       &GUID_000214e6_0000_0000_c000_000000000046,
                       &v30);
          if ( FileName < 0 )
          {
            CoTaskMemFree((LPVOID)v27);
            v27 = 0;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      }
      if ( FileName >= 0 )
      {
        v12 = (CRecursiveFolderOperation *)operator new(0x1C8u, (const struct std::nothrow_t *)&std::nothrow);
        v13 = v12;
        ppv[0] = v12;
        if ( v12
          && (memset_0(v12, 0, 0x1C8u), v16 = CRecursiveFolderOperation::CRecursiveFolderOperation(v13),
                                        (v17 = v16) != 0) )
        {
          IUnknown_Set((IUnknown **)v16 + 6, *((IUnknown **)this + 2));
          IUnknown_Set((IUnknown **)v17 + 7, *((IUnknown **)this + 3));
          CBaseOperation::SetNewName(v17, (const unsigned __int16 *)((unsigned __int64)v10 & -(__int64)(*v10 != 0)));
          *((_DWORD *)v17 + 18) = 0;
          v14 = 0;
          ppv[0] = 0;
          if ( (*((_DWORD *)a2 + 21) & 0x2000) != 0
            || (v24 = ppv,
                FileName = _TryAddConnected(
                             a2,
                             *((unsigned int *)this + 2),
                             *((_QWORD *)this + 2),
                             *((_QWORD *)this + 3),
                             v29),
                v14 = (CRecursiveFolderOperation *)ppv[0],
                FileName >= 0) )
          {
            ppv[0] = 0;
            if ( (*((_DWORD *)a2 + 21) & 0x20000000) != 0 )
            {
              v19 = (CUndoRoot *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
              v20 = v19;
              if ( !v19
                || (memset_0(v19, 0, 0xB0u), v21 = CUndoRoot::CUndoRoot(v20), (v22 = v21) == 0)
                || (*((_DWORD *)v21 + 11) &= ~2u,
                    v23 = QISearch(
                            v21,
                            &`CUndoRoot::QueryInterface'::`2'::qit,
                            &GUID_738f9802_d41f_4264_a81c_8024c0904e6b,
                            ppv),
                    CUndoRoot::Release(v22),
                    v23 < 0) )
              {
                CFileOperation::DisableUndoAndClearStack(a2);
              }
            }
            LODWORD(v24) = v5;
            FileName = CRecursiveFolderOperation::InitCopyRoot(
                         v17,
                         a2,
                         *((unsigned int *)this + 2),
                         v26,
                         *((_QWORD *)this + 132),
                         v14,
                         v27,
                         v24,
                         ppv[0]);
            if ( FileName >= 0 )
              FileName = CFileOperation::AppendRootToNormalList(a2, v17);
            if ( ppv[0] )
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
          }
          if ( v14 )
            CRecursiveFolderOperation::Release(v14);
          CRecursiveFolderOperation::Release(v17);
        }
        else
        {
          FileName = -2147024888;
        }
        CoTaskMemFree((LPVOID)v27);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      CoTaskMemFree(v29);
    }
  }
  return (unsigned int)FileName;
}

```

## disassembly

```asm
0x1801979a0  mov     [rsp-8+arg_18], rbx
0x1801979a5  push    rbp
0x1801979a6  push    rsi
0x1801979a7  push    rdi
0x1801979a8  push    r12
0x1801979aa  push    r13
0x1801979ac  push    r14
0x1801979ae  push    r15
0x1801979b0  lea     rbp, [rsp-1A0h]
0x1801979b8  sub     rsp, 2A0h
0x1801979bf  mov     rax, cs:__security_cookie
0x1801979c6  xor     rax, rsp
0x1801979c9  mov     [rbp+1D0h+var_40], rax
0x1801979d0  mov     [rsp+2D0h+var_278], r8
0x1801979d5  mov     r15, rdx
0x1801979d8  mov     rdi, rcx
0x1801979db  mov     r12d, 1
0x1801979e1  xor     r14d, r14d
0x1801979e4  mov     r13d, r14d
0x1801979e7  mov     rcx, [rcx+10h]
0x1801979eb  test    rcx, rcx
0x1801979ee  jz      short loc_180197A47
0x1801979f0  mov     dword ptr [rsp+2D0h+var_270], r14d
0x1801979f5  mov     ebx, 410000h
0x1801979fa  mov     eax, 400000h
0x1801979ff  cmp     dword ptr [rdi+8], 3
0x180197a03  cmovnz  ebx, eax
0x180197a06  mov     rax, [rcx]
0x180197a09  mov     edx, ebx
0x180197a0b  bts     edx, 1Dh
0x180197a0f  lea     r8, [rsp+2D0h+var_270]
0x180197a14  mov     rax, [rax+30h]
0x180197a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197a1d  mov     edx, dword ptr [rsp+2D0h+var_270]
0x180197a21  test    edx, ebx
0x180197a23  setz    cl
0x180197a26  bt      edx, 1Dh
0x180197a2a  setb    al
0x180197a2d  test    al, cl
0x180197a2f  jnz     loc_180197CAB
0x180197a35  mov     ecx, 20400000h
0x180197a3a  and     edx, ecx
0x180197a3c  lea     eax, [r12+1]
0x180197a41  cmp     edx, ecx
0x180197a43  cmovz   r13d, eax
0x180197a47  mov     ebx, r14d
0x180197a4a  lea     rsi, [rdi+20h]
0x180197a4e  cmp     dword ptr [rdi+8], 4
0x180197a52  jz      loc_180197D3A
0x180197a58  mov     [rsp+2D0h+pv], r14
0x180197a5d  lea     rdx, [rsp+2D0h+pv]; unsigned __int16 **
0x180197a62  mov     rcx, [rdi+10h]; struct IShellItem *
0x180197a66  call    ?GetFileSystemOrPlaceholderPath@@YAJPEAUIShellItem@@PEAPEAG@Z; GetFileSystemOrPlaceholderPath(IShellItem *,ushort * *)
0x180197a6b  test    eax, eax
0x180197a6d  js      short loc_180197A93
0x180197a6f  lea     rcx, [r15+140h]; this
0x180197a76  mov     rdx, [rsp+2D0h+pv]; unsigned __int16 *
0x180197a7b  call    ?DiskCheck@CCopyTree@@QEAAJPEBG@Z; CCopyTree::DiskCheck(ushort const *)
0x180197a80  mov     ebx, eax
0x180197a82  mov     rcx, [rsp+2D0h+pv]; pv
0x180197a87  call    cs:__imp_CoTaskMemFree
0x180197a8e  nop     dword ptr [rax+rax+00h]
0x180197a93  test    ebx, ebx
0x180197a95  js      loc_180197C7E
0x180197a9b  mov     [rsp+2D0h+var_260], r14
0x180197aa0  lea     rdx, [rsp+2D0h+var_260]; unsigned __int16 **
0x180197aa5  mov     rcx, [rdi+10h]; struct IShellItem *
0x180197aa9  call    ?IShellItem_GetFileName@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetFileName(IShellItem *,ushort * *)
0x180197aae  test    eax, eax
0x180197ab0  js      loc_180197C7E
0x180197ab6  mov     rcx, [rdi+10h]
0x180197aba  mov     [rsp+2D0h+var_270], r14
0x180197abf  mov     [rsp+2D0h+var_258], r14
0x180197ac4  mov     [rbp+1D0h+ppv], r14
0x180197ac8  mov     rax, [rcx]
0x180197acb  lea     r8, [rbp+1D0h+ppv]
0x180197acf  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180197ad6  mov     rax, [rax]
0x180197ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197ade  mov     ebx, eax
0x180197ae0  test    eax, eax
0x180197ae2  js      short loc_180197B52
0x180197ae4  mov     [rsp+2D0h+var_280], r14
0x180197ae9  mov     rcx, [rbp+1D0h+ppv]
0x180197aed  mov     rax, [rcx]
0x180197af0  lea     r9, [rsp+2D0h+var_270]
0x180197af5  lea     r8, [rsp+2D0h+var_280]
0x180197afa  xor     edx, edx
0x180197afc  mov     rax, [rax+20h]
0x180197b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197b05  mov     ebx, eax
0x180197b07  test    eax, eax
0x180197b09  js      short loc_180197B42
0x180197b0b  mov     rcx, [rsp+2D0h+var_280]
0x180197b10  mov     rax, [rcx]
0x180197b13  lea     r8, [rsp+2D0h+var_258]
0x180197b18  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180197b1f  mov     rax, [rax]
0x180197b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197b27  mov     ebx, eax
0x180197b29  test    eax, eax
0x180197b2b  js      loc_180197E53
0x180197b31  mov     rcx, [rsp+2D0h+var_280]
0x180197b36  mov     rax, [rcx]
0x180197b39  mov     rax, [rax+10h]
0x180197b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197b42  mov     rcx, [rbp+1D0h+ppv]
0x180197b46  mov     rax, [rcx]
0x180197b49  mov     rax, [rax+10h]
0x180197b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197b52  test    ebx, ebx
0x180197b54  js      loc_180197C6D
0x180197b5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180197b61  mov     ecx, 1C8h; unsigned __int64
0x180197b66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180197b6b  mov     rbx, rax
0x180197b6e  mov     [rbp+1D0h+ppv], rax
0x180197b72  test    rax, rax
0x180197b75  jnz     loc_180197CB9
0x180197b7b  mov     ebx, 80070008h
0x180197b80  jmp     loc_180197C4B
0x180197b85  lea     rax, [rbp+1D0h+ppv]
0x180197b89  mov     [rsp+2D0h+var_298], rax
0x180197b8e  mov     dword ptr [rsp+2D0h+var_2A0], r12d
0x180197b93  mov     rax, [rsp+2D0h+var_260]
0x180197b98  mov     [rsp+2D0h+var_2B0], rax
0x180197b9d  mov     r9, [rdi+18h]
0x180197ba1  mov     r8, [rdi+10h]
0x180197ba5  mov     edx, [rdi+8]
0x180197ba8  mov     rcx, r15
0x180197bab  call    ?_TryAddConnected@@YAJPEAVCFileOperation@@IPEAUIShellItem@@1PEBGW4OFM_FLAGS@@KPEAPEAVCRecursiveFolderOperation@@@Z; _TryAddConnected(CFileOperation *,uint,IShellItem *,IShellItem *,ushort const *,OFM_FLAGS,ulong,CRecursiveFolderOperation * *)
0x180197bb0  mov     ebx, eax
0x180197bb2  mov     rsi, [rbp+1D0h+ppv]
0x180197bb6  test    eax, eax
0x180197bb8  js      short loc_180197C36
0x180197bba  mov     [rbp+1D0h+ppv], 0
0x180197bc2  test    dword ptr [r15+54h], 20000000h
0x180197bca  jnz     loc_180197DD5
0x180197bd0  mov     rax, [rbp+1D0h+ppv]
0x180197bd4  mov     rdx, [rsp+2D0h+var_270]
0x180197bd9  mov     [rsp+2D0h+var_290], rax
0x180197bde  mov     dword ptr [rsp+2D0h+var_298], r13d
0x180197be3  mov     [rsp+2D0h+var_2A0], rdx
0x180197be8  mov     [rsp+2D0h+var_2A8], rsi
0x180197bed  mov     rax, [rdi+420h]
0x180197bf4  mov     [rsp+2D0h+var_2B0], rax
0x180197bf9  mov     r9, [rsp+2D0h+var_278]
0x180197bfe  mov     r8d, [rdi+8]
0x180197c02  mov     rdx, r15
0x180197c05  mov     rcx, r14
0x180197c08  call    ?InitCopyRoot@CRecursiveFolderOperation@@QEAAJPEAVCFileOperation@@KPEAUIPropertyChangeArray@@PEAUIFileOperationProgressSink@@PEAV1@PEFBU_ITEMID_CHILD@@W4OPERATION_NODE_FLAGS@@PEAUIUndoRoot@@@Z; CRecursiveFolderOperation::InitCopyRoot(CFileOperation *,ulong,IPropertyChangeArray *,IFileOperationProgressSink *,CRecursiveFolderOperation *,_ITEMID_CHILD const *,OPERATION_NODE_FLAGS,IUndoRoot *)
0x180197c0d  mov     ebx, eax
0x180197c0f  test    eax, eax
0x180197c11  js      short loc_180197C20
0x180197c13  mov     rdx, r14; struct CRecursiveFolderOperation *
0x180197c16  mov     rcx, r15; this
0x180197c19  call    ?AppendRootToNormalList@CFileOperation@@QEAAJPEAVCRecursiveFolderOperation@@@Z; CFileOperation::AppendRootToNormalList(CRecursiveFolderOperation *)
0x180197c1e  mov     ebx, eax
0x180197c20  mov     rcx, [rbp+1D0h+ppv]
0x180197c24  test    rcx, rcx
0x180197c27  jz      short loc_180197C36
0x180197c29  mov     rax, [rcx]
0x180197c2c  mov     rax, [rax+10h]
0x180197c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197c35  nop
0x180197c36  test    rsi, rsi
0x180197c39  jz      short loc_180197C43
0x180197c3b  mov     rcx, rsi; this
0x180197c3e  call    ?Release@CRecursiveFolderOperation@@UEAAKXZ; CRecursiveFolderOperation::Release(void)
0x180197c43  mov     rcx, r14; this
0x180197c46  call    ?Release@CRecursiveFolderOperation@@UEAAKXZ; CRecursiveFolderOperation::Release(void)
0x180197c4b  mov     rcx, [rsp+2D0h+var_270]; pv
0x180197c50  call    cs:__imp_CoTaskMemFree
0x180197c57  nop     dword ptr [rax+rax+00h]
0x180197c5c  mov     rcx, [rsp+2D0h+var_258]
0x180197c61  mov     rax, [rcx]
0x180197c64  mov     rax, [rax+10h]
0x180197c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197c6d  mov     rcx, [rsp+2D0h+var_260]; pv
0x180197c72  call    cs:__imp_CoTaskMemFree
0x180197c79  nop     dword ptr [rax+rax+00h]
0x180197c7e  mov     eax, ebx
0x180197c80  mov     rcx, [rbp+1D0h+var_40]
0x180197c87  xor     rcx, rsp; StackCookie
0x180197c8a  call    __security_check_cookie
0x180197c8f  mov     rbx, [rsp+2D0h+arg_18]
0x180197c97  add     rsp, 2A0h
0x180197c9e  pop     r15
0x180197ca0  pop     r14
0x180197ca2  pop     r13
0x180197ca4  pop     r12
0x180197ca6  pop     rdi
0x180197ca7  pop     rsi
0x180197ca8  pop     rbp
0x180197ca9  retn
0x180197cab  mov     r13d, r12d
0x180197cae  mov     r12d, 2
0x180197cb4  jmp     loc_180197A47
0x180197cb9  xor     edx, edx; Val
0x180197cbb  mov     r8d, 1C8h; Size
0x180197cc1  mov     rcx, rbx; void *
0x180197cc4  call    memset_0
0x180197cc9  mov     rcx, rbx; this
0x180197ccc  call    ??0CRecursiveFolderOperation@@QEAA@XZ; CRecursiveFolderOperation::CRecursiveFolderOperation(void)
0x180197cd1  mov     r14, rax
0x180197cd4  test    rax, rax
0x180197cd7  jz      loc_180197B7B
0x180197cdd  lea     rcx, [rax+30h]; ppunk
0x180197ce1  mov     rdx, [rdi+10h]; punk
0x180197ce5  call    cs:__imp_IUnknown_Set
0x180197cec  nop     dword ptr [rax+rax+00h]
0x180197cf1  lea     rcx, [r14+38h]; ppunk
0x180197cf5  mov     rdx, [rdi+18h]; punk
0x180197cf9  call    cs:__imp_IUnknown_Set
0x180197d00  nop     dword ptr [rax+rax+00h]
0x180197d05  movzx   ecx, word ptr [rsi]
0x180197d08  neg     cx
0x180197d0b  sbb     rdx, rdx
0x180197d0e  and     rdx, rsi; unsigned __int16 *
0x180197d11  mov     rcx, r14; this
0x180197d14  call    ?SetNewName@CBaseOperation@@QEAAJPEBG@Z; CBaseOperation::SetNewName(ushort const *)
0x180197d19  mov     dword ptr [r14+48h], 0
0x180197d21  xor     esi, esi
0x180197d23  mov     [rbp+1D0h+ppv], rsi
0x180197d27  test    dword ptr [r15+54h], 2000h
0x180197d2f  jz      loc_180197B85
0x180197d35  jmp     loc_180197BBA
0x180197d3a  test    dword ptr [r15+54h], 200000h
0x180197d42  jz      loc_180197A58
0x180197d48  mov     r8, rsi; unsigned __int16 *
0x180197d4b  mov     esi, 0FFh
0x180197d50  mov     edx, esi; unsigned __int64
0x180197d52  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x180197d56  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180197d5b  mov     ebx, eax
0x180197d5d  test    eax, eax
0x180197d5f  js      loc_180197C7E
0x180197d65  mov     [rsp+2D0h+var_270], r14
0x180197d6a  lea     rdx, [rsp+2D0h+var_270]; unsigned __int16 **
0x180197d6f  mov     rcx, [rdi+10h]; struct IShellItem *
0x180197d73  call    ?IShellItem_GetFileName@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetFileName(IShellItem *,ushort * *)
0x180197d78  mov     ebx, eax
0x180197d7a  test    eax, eax
0x180197d7c  js      loc_180197C7E
0x180197d82  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x180197d86  call    cs:__imp_PathRemoveExtensionW
0x180197d8d  nop     dword ptr [rax+rax+00h]
0x180197d92  mov     rcx, [rsp+2D0h+var_270]; pszPath
0x180197d97  call    cs:__imp_PathFindExtensionW
0x180197d9e  nop     dword ptr [rax+rax+00h]
0x180197da3  mov     r8, rax; unsigned __int16 *
0x180197da6  mov     edx, esi; unsigned __int64
0x180197da8  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x180197dac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180197db1  mov     ebx, eax
0x180197db3  mov     rcx, [rsp+2D0h+var_270]; pv
0x180197db8  call    cs:__imp_CoTaskMemFree
0x180197dbf  nop     dword ptr [rax+rax+00h]
0x180197dc4  test    ebx, ebx
0x180197dc6  js      loc_180197C7E
0x180197dcc  lea     rsi, [rbp+1D0h+pszPath]
0x180197dd0  jmp     loc_180197A58
0x180197dd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180197ddc  mov     r12d, 0B0h
0x180197de2  mov     ecx, r12d; unsigned __int64
0x180197de5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180197dea  mov     rbx, rax
0x180197ded  test    rax, rax
0x180197df0  jz      short loc_180197E46
0x180197df2  mov     r8d, r12d; Size
0x180197df5  xor     edx, edx; Val
0x180197df7  mov     rcx, rax; void *
0x180197dfa  call    memset_0
0x180197dff  mov     rcx, rbx; this
0x180197e02  call    ??0CUndoRoot@@QEAA@XZ; CUndoRoot::CUndoRoot(void)
0x180197e07  mov     r12, rax
0x180197e0a  test    rax, rax
0x180197e0d  jz      short loc_180197E46
0x180197e0f  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x180197e13  lea     r9, [rbp+1D0h+ppv]; ppv
0x180197e17  lea     r8, _GUID_738f9802_d41f_4264_a81c_8024c0904e6b; riid
0x180197e1e  lea     rdx, ?qit@?1??QueryInterface@CUndoRoot@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180197e25  mov     rcx, rax; that
0x180197e28  call    cs:__imp_QISearch
0x180197e2f  nop     dword ptr [rax+rax+00h]
0x180197e34  mov     ebx, eax
0x180197e36  mov     rcx, r12; this
0x180197e39  call    ?Release@CUndoRoot@@UEAAKXZ; CUndoRoot::Release(void)
0x180197e3e  test    ebx, ebx
0x180197e40  jns     loc_180197BD0
0x180197e46  mov     rcx, r15; this
0x180197e49  call    ?DisableUndoAndClearStack@CFileOperation@@QEAAXXZ; CFileOperation::DisableUndoAndClearStack(void)
0x180197e4e  jmp     loc_180197BD0
0x180197e53  mov     rcx, [rsp+2D0h+var_270]; pv
0x180197e58  call    cs:__imp_CoTaskMemFree
0x180197e5f  nop     dword ptr [rax+rax+00h]
0x180197e64  mov     [rsp+2D0h+var_270], r14
0x180197e69  jmp     loc_180197B31
```
