# CGlobalThumbsDBStore::_GetStorage(IShellItem2 *,CGlobalThumbsDBStore::STORAGEMODE,int,IStorage * *)

- ea: `0x180024cbc`
- end: `0x180024f5d`
- name: `?_GetStorage@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@W4STORAGEMODE@1@HPEAPEAUIStorage@@@Z`
- size: `673`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x1800249d0`
- `0x1800443fc`

## callees

- `0x18001f98c`
- `0x18001fe54`
- `0x180024cbc`
- `0x180025004`
- `0x18002a1bc`
- `0x180035830`
- `0x180044e30`
- `0x180044f14`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ddd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ddd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024d85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024d85`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024e6f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024e6f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180024d53`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180024d53`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180024d72`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180024d72`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180024dfb`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180024dfb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180024dac`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180024ef1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180024dac`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180024ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f2b`
- `ole32!StgCreateStorageEx` at `0x180024eaa`
- `ole32!StgCreateStorageEx` at `0x180024eaa`
- `ole32!StgOpenStorageEx` at `0x180024e4a`
- `ole32!StgOpenStorageEx` at `0x180024e4a`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::_GetStorage(
        __int64 a1,
        struct IShellItem2 *a2,
        unsigned int a3,
        int a4,
        IUnknown **ppunk)
{
  HRESULT Storage; // ebx
  struct IShellItem2 v9; // rax
  IUnknown **v10; // rdi
  int ShouldReopenStorage; // r12d
  int v12; // edi
  HRESULT v13; // eax
  IUnknown *v14; // rdx
  LPWSTR ppwsz; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR pszPath; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  Storage = -2147175932;
  *ppunk = 0;
  if ( *(_DWORD *)a1 )
  {
    if ( (unsigned int)CGlobalThumbsDBStore::CanCache((CGlobalThumbsDBStore *)a1, a2, 0) )
    {
      v9.lpVtbl = a2->lpVtbl;
      pszPath = 0;
      Storage = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, LPWSTR *))v9.lpVtbl->GetDisplayName)(
                  a2,
                  2147844096LL,
                  &pszPath);
      if ( Storage >= 0 )
      {
        if ( !PathRemoveFileSpecW(pszPath) || !PathCombineW(pszDest, pszPath, L"Thumbs.db") )
        {
          Storage = -2147418113;
          goto LABEL_29;
        }
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
        v10 = (IUnknown **)(a1 + 16);
        ShouldReopenStorage = CGlobalThumbsDBStore::_ShouldReopenStorage(a1, pszDest, a3);
        if ( ShouldReopenStorage )
        {
          Storage = 0;
          if ( *v10 )
            ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 16), 0);
        }
        else
        {
          IUnknown_Set(ppunk, *v10);
          Storage = *v10 == 0 ? 0x8004B204 : 0;
        }
        v12 = *(_DWORD *)(a1 + 36);
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
        if ( !ShouldReopenStorage )
          goto LABEL_29;
        ppwsz = 0;
        Storage = SHStrDupW(pszDest, &ppwsz);
        if ( Storage < 0 )
          goto LABEL_29;
        punk = 0;
        v13 = StgOpenStorageEx(
                ppwsz,
                a3 != 0 ? 4194322 : 4194368,
                0,
                0,
                0,
                0,
                &GUID_0000000b_0000_0000_c000_000000000046,
                (void **)&punk);
        Storage = v13;
        if ( v13 < 0 )
        {
          if ( v13 == -2147286775 )
          {
            DeleteFileW(ppwsz);
            Storage = -2147287038;
          }
          else if ( v13 != -2147287038 )
          {
            if ( a3 == 1 )
              v12 = 2;
            goto LABEL_27;
          }
          if ( a4 )
          {
            Storage = StgCreateStorageEx(
                        ppwsz,
                        0x400012u,
                        0,
                        0,
                        0,
                        0,
                        &GUID_0000000b_0000_0000_c000_000000000046,
                        (void **)&punk);
            v12 = ((Storage >> 31) & 1) + 1;
            if ( Storage < 0 )
              a3 = 0;
          }
          else
          {
            v12 = 0;
            a3 = 0;
          }
          if ( Storage < 0 )
          {
LABEL_27:
            v14 = punk;
            punk = 0;
            CGlobalThumbsDBStore::_Reset(a1, v14, ppwsz, a3, v12);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&punk);
LABEL_29:
            CoTaskMemFree(pszPath);
            return (unsigned int)Storage;
          }
        }
        else if ( a3 == 1 )
        {
          v12 = 1;
        }
        CGlobalThumbsDBStore::_SetAttribs(ppwsz);
        IUnknown_Set(ppunk, punk);
        goto LABEL_27;
      }
    }
  }
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x180024cbc  mov     [rsp-8+arg_10], rbx
0x180024cc1  push    rbp
0x180024cc2  push    rsi
0x180024cc3  push    rdi
0x180024cc4  push    r12
0x180024cc6  push    r13
0x180024cc8  push    r14
0x180024cca  push    r15
0x180024ccc  lea     rbp, [rsp-180h]
0x180024cd4  sub     rsp, 280h
0x180024cdb  mov     rax, cs:__security_cookie
0x180024ce2  xor     rax, rsp
0x180024ce5  mov     [rbp+1B0h+var_40], rax
0x180024cec  mov     r13, [rbp+1B0h+ppunk]
0x180024cf3  xor     r15d, r15d
0x180024cf6  mov     [rsp+2B0h+var_270], r9d
0x180024cfb  mov     esi, r8d
0x180024cfe  mov     rdi, rdx
0x180024d01  mov     r14, rcx
0x180024d04  mov     ebx, 8004B204h
0x180024d09  mov     [r13+0], r15
0x180024d0d  cmp     [rcx], r15d
0x180024d10  jz      loc_180024F31
0x180024d16  xor     r8d, r8d; bool *
0x180024d19  call    ?CanCache@CGlobalThumbsDBStore@@QEAAHPEAUIShellItem2@@PEA_N@Z; CGlobalThumbsDBStore::CanCache(IShellItem2 *,bool *)
0x180024d1e  test    eax, eax
0x180024d20  jz      loc_180024F31
0x180024d26  mov     rax, [rdi]
0x180024d29  lea     r8, [rsp+2B0h+pszPath]
0x180024d2e  mov     edx, 80058000h
0x180024d33  mov     [rsp+2B0h+pszPath], r15
0x180024d38  mov     rcx, rdi
0x180024d3b  mov     rax, [rax+28h]
0x180024d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d44  mov     ebx, eax
0x180024d46  test    eax, eax
0x180024d48  js      loc_180024F31
0x180024d4e  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x180024d53  call    cs:__imp_PathRemoveFileSpecW
0x180024d59  test    eax, eax
0x180024d5b  jz      loc_180024F21
0x180024d61  mov     rdx, [rsp+2B0h+pszPath]; pszDir
0x180024d66  lea     r8, pszFile; "Thumbs.db"
0x180024d6d  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x180024d72  call    cs:__imp_PathCombineW
0x180024d78  test    rax, rax
0x180024d7b  jz      loc_180024F21
0x180024d81  lea     rcx, [r14+8]; SRWLock
0x180024d85  call    cs:__imp_AcquireSRWLockExclusive
0x180024d8b  mov     r8d, esi
0x180024d8e  lea     rdx, [rsp+2B0h+pszDest]
0x180024d93  mov     rcx, r14
0x180024d96  call    ?_ShouldReopenStorage@CGlobalThumbsDBStore@@AEAAHPEBGW4STORAGEMODE@1@@Z; CGlobalThumbsDBStore::_ShouldReopenStorage(ushort const *,CGlobalThumbsDBStore::STORAGEMODE)
0x180024d9b  lea     rdi, [r14+10h]
0x180024d9f  mov     r12d, eax
0x180024da2  test    eax, eax
0x180024da4  jnz     short loc_180024DC4
0x180024da6  mov     rdx, [rdi]; punk
0x180024da9  mov     rcx, r13; ppunk
0x180024dac  call    cs:__imp_IUnknown_Set
0x180024db2  mov     rcx, [rdi]
0x180024db5  neg     rcx
0x180024db8  sbb     ebx, ebx
0x180024dba  not     ebx
0x180024dbc  and     ebx, 8004B204h
0x180024dc2  jmp     short loc_180024DD5
0x180024dc4  xor     ebx, ebx
0x180024dc6  cmp     [rdi], rbx
0x180024dc9  jz      short loc_180024DD5
0x180024dcb  xor     edx, edx; struct IUnknown *
0x180024dcd  mov     rcx, rdi; struct IUnknown **
0x180024dd0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180024dd5  mov     edi, [r14+24h]
0x180024dd9  lea     rcx, [r14+8]; SRWLock
0x180024ddd  call    cs:__imp_ReleaseSRWLockExclusive
0x180024de3  test    r12d, r12d
0x180024de6  jz      loc_180024F26
0x180024dec  lea     rdx, [rsp+2B0h+ppwsz]; ppwsz
0x180024df1  mov     [rsp+2B0h+ppwsz], r15
0x180024df6  lea     rcx, [rsp+2B0h+pszDest]; psz
0x180024dfb  call    cs:__imp_SHStrDupW
0x180024e01  mov     ebx, eax
0x180024e03  test    eax, eax
0x180024e05  js      loc_180024F26
0x180024e0b  mov     rcx, [rsp+2B0h+ppwsz]; pwcsName
0x180024e10  lea     r12, _GUID_0000000b_0000_0000_c000_000000000046
0x180024e17  mov     eax, esi
0x180024e19  mov     [rsp+2B0h+punk], r15
0x180024e1e  neg     eax
0x180024e20  lea     rax, [rsp+2B0h+punk]
0x180024e25  sbb     edx, edx
0x180024e27  mov     [rsp+2B0h+ppObjectOpen], rax; ppObjectOpen
0x180024e2c  and     edx, 0FFFFFFD2h
0x180024e2f  mov     [rsp+2B0h+riid], r12; riid
0x180024e34  add     edx, 400040h; grfMode
0x180024e3a  mov     [rsp+2B0h+pSecurityDescriptor], r15; pSecurityDescriptor
0x180024e3f  xor     r9d, r9d; grfAttrs
0x180024e42  mov     [rsp+2B0h+pStgOptions], r15; pStgOptions
0x180024e47  xor     r8d, r8d; stgfmt
0x180024e4a  call    cs:__imp_StgOpenStorageEx
0x180024e50  mov     ebx, eax
0x180024e52  test    eax, eax
0x180024e54  js      short loc_180024E63
0x180024e56  cmp     esi, 1
0x180024e59  jnz     loc_180024EDF
0x180024e5f  mov     edi, esi
0x180024e61  jmp     short loc_180024EDF
0x180024e63  cmp     eax, 80030109h
0x180024e68  jnz     short loc_180024EC4
0x180024e6a  mov     rcx, [rsp+2B0h+ppwsz]; lpFileName
0x180024e6f  call    cs:__imp_DeleteFileW
0x180024e75  mov     ebx, 80030002h
0x180024e7a  cmp     [rsp+2B0h+var_270], r15d
0x180024e7f  jz      short loc_180024ED5
0x180024e81  mov     rcx, [rsp+2B0h+ppwsz]; pwcsName
0x180024e86  lea     rax, [rsp+2B0h+punk]
0x180024e8b  mov     [rsp+2B0h+ppObjectOpen], rax; ppObjectOpen
0x180024e90  xor     r9d, r9d; grfAttrs
0x180024e93  mov     [rsp+2B0h+riid], r12; riid
0x180024e98  xor     r8d, r8d; stgfmt
0x180024e9b  mov     [rsp+2B0h+pSecurityDescriptor], r15; pSecurityDescriptor
0x180024ea0  mov     edx, 400012h; grfMode
0x180024ea5  mov     [rsp+2B0h+pStgOptions], r15; pStgOptions
0x180024eaa  call    cs:__imp_StgCreateStorageEx
0x180024eb0  mov     edi, eax
0x180024eb2  mov     ebx, eax
0x180024eb4  sar     edi, 1Fh
0x180024eb7  and     edi, 1
0x180024eba  inc     edi
0x180024ebc  test    eax, eax
0x180024ebe  cmovs   esi, r15d
0x180024ec2  jmp     short loc_180024EDB
0x180024ec4  cmp     eax, 80030002h
0x180024ec9  jz      short loc_180024E7A
0x180024ecb  cmp     esi, 1
0x180024ece  jnz     short loc_180024EF7
0x180024ed0  lea     edi, [rsi+1]
0x180024ed3  jmp     short loc_180024EF7
0x180024ed5  mov     edi, r15d
0x180024ed8  mov     esi, r15d
0x180024edb  test    ebx, ebx
0x180024edd  js      short loc_180024EF7
0x180024edf  mov     rcx, [rsp+2B0h+ppwsz]; unsigned __int16 *
0x180024ee4  call    ?_SetAttribs@CGlobalThumbsDBStore@@CAXPEBG@Z; CGlobalThumbsDBStore::_SetAttribs(ushort const *)
0x180024ee9  mov     rdx, [rsp+2B0h+punk]; punk
0x180024eee  mov     rcx, r13; ppunk
0x180024ef1  call    cs:__imp_IUnknown_Set
0x180024ef7  mov     rdx, [rsp+2B0h+punk]
0x180024efc  mov     r9d, esi
0x180024eff  mov     r8, [rsp+2B0h+ppwsz]
0x180024f04  mov     rcx, r14
0x180024f07  mov     [rsp+2B0h+punk], r15
0x180024f0c  mov     dword ptr [rsp+2B0h+pStgOptions], edi
0x180024f10  call    ?_Reset@CGlobalThumbsDBStore@@AEAAXPEAUIStorage@@PEAGW4STORAGEMODE@1@W4TRIBIT@@@Z; CGlobalThumbsDBStore::_Reset(IStorage *,ushort *,CGlobalThumbsDBStore::STORAGEMODE,TRIBIT)
0x180024f15  lea     rcx, [rsp+2B0h+punk]
0x180024f1a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024f1f  jmp     short loc_180024F26
0x180024f21  mov     ebx, 8000FFFFh
0x180024f26  mov     rcx, [rsp+2B0h+pszPath]; pv
0x180024f2b  call    cs:__imp_CoTaskMemFree
0x180024f31  mov     eax, ebx
0x180024f33  mov     rcx, [rbp+1B0h+var_40]
0x180024f3a  xor     rcx, rsp; StackCookie
0x180024f3d  call    __security_check_cookie
0x180024f42  mov     rbx, [rsp+2B0h+arg_10]
0x180024f4a  add     rsp, 280h
0x180024f51  pop     r15
0x180024f53  pop     r14
0x180024f55  pop     r13
0x180024f57  pop     r12
0x180024f59  pop     rdi
0x180024f5a  pop     rsi
0x180024f5b  pop     rbp
0x180024f5c  retn
```
