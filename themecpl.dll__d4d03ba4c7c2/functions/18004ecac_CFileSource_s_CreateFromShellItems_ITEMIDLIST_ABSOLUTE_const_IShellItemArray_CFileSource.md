# CFileSource::s_CreateFromShellItems(_ITEMIDLIST_ABSOLUTE const *,IShellItemArray *,CFileSource * *)

- ea: `0x18004ecac`
- end: `0x18004eedf`
- name: `?s_CreateFromShellItems@CFileSource@@SAJPEFBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellItemArray@@PEAPEAV1@@Z`
- size: `563`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, struct IShellItemArray *, struct CFileSource **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18004eb24`

## callees

- `0x18000268c`
- `0x180011734`
- `0x18003a5f8`
- `0x18004eae4`
- `0x18004ecac`
- `0x18004eee8`
- `0x180055074`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18004ed7a`
- `SHELL32!SHCreateItemFromIDList` at `0x18004ed7a`
- `SHELL32!SHGetIDListFromObject` at `0x18004edf3`
- `SHELL32!SHGetIDListFromObject` at `0x18004edf3`
- `SHELL32!__imp_ILClone` at `0x18004ed13`
- `SHELL32!__imp_ILClone` at `0x18004ed13`
- `SHELL32!__imp_ILFree` at `0x18004ee28`
- `SHELL32!__imp_ILFree` at `0x18004ee28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFileSource::s_CreateFromShellItems(
        LPCITEMIDLIST pidl,
        struct IShellItemArray *a2,
        struct CFileSource **a3)
{
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx
  LPITEMIDLIST v8; // rax
  HRESULT Instance; // edi
  unsigned int v10; // r14d
  LPITEMIDLIST v11; // rsi
  IUnknown *punk; // [rsp+20h] [rbp-10h] BYREF
  void *ppv; // [rsp+28h] [rbp-8h] BYREF
  int cItemGrow; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp+48h] BYREF

  *a3 = 0;
  v6 = (volatile signed __int32 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 1;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    v8 = ILClone(pidl);
    *((_QWORD *)v7 + 1) = v8;
    if ( v8 )
    {
      if ( a2 )
      {
        cItemGrow = 0;
        Instance = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))a2->lpVtbl->GetCount)(a2, &cItemGrow);
        if ( Instance >= 0 )
        {
          if ( !cItemGrow )
            goto LABEL_25;
          ppv = 0;
          Instance = SHCreateItemFromIDList(
                       *((LPCITEMIDLIST *)v7 + 1),
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &ppv);
          if ( Instance >= 0 )
          {
            ppidl = 0;
            Instance = CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::s_CreateInstance(cItemGrow);
            if ( Instance >= 0 )
            {
              v10 = 0;
              v11 = ppidl;
              while ( v10 < cItemGrow )
              {
                punk = 0;
                Instance = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, IUnknown **))a2->lpVtbl->GetItemAt)(
                             a2,
                             v10,
                             &punk);
                if ( Instance >= 0 )
                {
                  ppidl = 0;
                  Instance = SHGetIDListFromObject(punk, &ppidl);
                  if ( Instance >= 0 )
                  {
                    if ( DPA_InsertPtr(*(HDPA *)&v11->mkid.cb, 0x7FFFFFFF, ppidl) == -1 )
                    {
                      Instance = -2147024882;
                      ILFree(ppidl);
                    }
                    else
                    {
                      Instance = 0;
                    }
                  }
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
                ++v10;
                if ( Instance < 0 )
                  goto LABEL_21;
              }
              if ( *(_QWORD *)&v11->mkid.cb && **(int **)&v11->mkid.cb > 0 )
              {
                *((_QWORD *)v7 + 2) = v11;
                _InterlockedIncrement((volatile signed __int32 *)v11[2].mkid.abID);
              }
LABEL_21:
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11[2].mkid.abID, 0xFFFFFFFF) == 1 && v11 )
              {
                CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::~CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>(v11);
                operator delete(v11);
              }
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            if ( Instance >= 0 )
            {
LABEL_25:
              _InterlockedIncrement(v7);
              *a3 = (struct CFileSource *)v7;
            }
          }
        }
      }
      else
      {
        _InterlockedIncrement(v7);
        *a3 = (struct CFileSource *)v7;
        Instance = 0;
      }
    }
    else
    {
      Instance = -2147024882;
    }
    CFileSource::Release((CFileSource *)v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004ecac  mov     [rsp-28h+arg_0], rbx
0x18004ecb1  mov     [rsp-28h+arg_8], rsi
0x18004ecb6  push    rbp
0x18004ecb7  push    rdi
0x18004ecb8  push    r12
0x18004ecba  push    r14
0x18004ecbc  push    r15
0x18004ecbe  mov     rbp, rsp
0x18004ecc1  sub     rsp, 30h
0x18004ecc5  mov     r12, r8
0x18004ecc8  mov     r15, rdx
0x18004eccb  mov     rdi, rcx
0x18004ecce  mov     qword ptr [r8], 0
0x18004ecd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004ecdc  mov     ecx, 20h ; ' '; unsigned __int64
0x18004ece1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004ece6  mov     rbx, rax
0x18004ece9  test    rax, rax
0x18004ecec  jz      loc_18004EEC0
0x18004ecf2  mov     dword ptr [rax], 1
0x18004ecf8  mov     qword ptr [rax+8], 0
0x18004ed00  mov     qword ptr [rax+10h], 0
0x18004ed08  mov     qword ptr [rax+18h], 0
0x18004ed10  mov     rcx, rdi; pidl
0x18004ed13  call    cs:__imp_ILClone
0x18004ed1a  nop     dword ptr [rax+rax+00h]
0x18004ed1f  mov     [rbx+8], rax
0x18004ed23  test    rax, rax
0x18004ed26  jz      loc_18004EEB1
0x18004ed2c  test    r15, r15
0x18004ed2f  jz      loc_18004EEA6
0x18004ed35  mov     [rbp+cItemGrow], 0
0x18004ed3c  mov     rax, [r15]
0x18004ed3f  lea     rdx, [rbp+cItemGrow]
0x18004ed43  mov     rcx, r15
0x18004ed46  mov     rax, [rax+38h]
0x18004ed4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed4f  mov     edi, eax
0x18004ed51  test    eax, eax
0x18004ed53  js      loc_18004EEB6
0x18004ed59  cmp     [rbp+cItemGrow], 0
0x18004ed5d  jbe     loc_18004EE9D
0x18004ed63  mov     [rbp+ppv], 0
0x18004ed6b  lea     r8, [rbp+ppv]; ppv
0x18004ed6f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004ed76  mov     rcx, [rbx+8]; pidl
0x18004ed7a  call    cs:__imp_SHCreateItemFromIDList
0x18004ed81  nop     dword ptr [rax+rax+00h]
0x18004ed86  mov     edi, eax
0x18004ed88  test    eax, eax
0x18004ed8a  js      loc_18004EEB6
0x18004ed90  mov     [rbp+ppidl], 0
0x18004ed98  lea     rdx, [rbp+ppidl]
0x18004ed9c  mov     ecx, [rbp+cItemGrow]; cItemGrow
0x18004ed9f  call    ?s_CreateInstance@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@SAJKPEAPEAV1@@Z; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::s_CreateInstance(ulong,CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>> * *)
0x18004eda4  mov     edi, eax
0x18004eda6  test    eax, eax
0x18004eda8  js      loc_18004EE89
0x18004edae  xor     r14d, r14d
0x18004edb1  mov     rsi, [rbp+ppidl]
0x18004edb5  cmp     r14d, [rbp+cItemGrow]
0x18004edb9  jnb     loc_18004EE51
0x18004edbf  mov     [rbp+punk], 0
0x18004edc7  mov     rax, [r15]
0x18004edca  lea     r8, [rbp+punk]
0x18004edce  mov     edx, r14d
0x18004edd1  mov     rcx, r15
0x18004edd4  mov     rax, [rax+40h]
0x18004edd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eddd  mov     edi, eax
0x18004eddf  test    eax, eax
0x18004ede1  js      short loc_18004EE44
0x18004ede3  mov     [rbp+ppidl], 0
0x18004edeb  lea     rdx, [rbp+ppidl]; ppidl
0x18004edef  mov     rcx, [rbp+punk]; punk
0x18004edf3  call    cs:__imp_SHGetIDListFromObject
0x18004edfa  nop     dword ptr [rax+rax+00h]
0x18004edff  mov     edi, eax
0x18004ee01  test    eax, eax
0x18004ee03  js      short loc_18004EE34
0x18004ee05  mov     r8, [rbp+ppidl]; p
0x18004ee09  mov     edx, 7FFFFFFFh; i
0x18004ee0e  mov     rcx, [rsi]; hdpa
0x18004ee11  call    DPA_InsertPtr
0x18004ee16  cmp     eax, 0FFFFFFFFh
0x18004ee19  jz      short loc_18004EE1F
0x18004ee1b  xor     edi, edi
0x18004ee1d  jmp     short loc_18004EE34
0x18004ee1f  mov     edi, 8007000Eh
0x18004ee24  mov     rcx, [rbp+ppidl]; pidl
0x18004ee28  call    cs:__imp_ILFree
0x18004ee2f  nop     dword ptr [rax+rax+00h]
0x18004ee34  mov     rcx, [rbp+punk]
0x18004ee38  mov     rax, [rcx]
0x18004ee3b  mov     rax, [rax+10h]
0x18004ee3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee44  inc     r14d
0x18004ee47  test    edi, edi
0x18004ee49  jns     loc_18004EDB5
0x18004ee4f  jmp     short loc_18004EE66
0x18004ee51  mov     rax, [rsi]
0x18004ee54  test    rax, rax
0x18004ee57  jz      short loc_18004EE66
0x18004ee59  cmp     dword ptr [rax], 0
0x18004ee5c  jle     short loc_18004EE66
0x18004ee5e  mov     [rbx+10h], rsi
0x18004ee62  lock inc dword ptr [rsi+8]
0x18004ee66  or      eax, 0FFFFFFFFh
0x18004ee69  lock xadd [rsi+8], eax
0x18004ee6e  cmp     eax, 1
0x18004ee71  jnz     short loc_18004EE89
0x18004ee73  test    rsi, rsi
0x18004ee76  jz      short loc_18004EE89
0x18004ee78  mov     rcx, rsi
0x18004ee7b  call    ??1?$CDPA_Base@U_ITEMIDLIST_ABSOLUTE@@VCTContainer_PolicyCoTaskMem@@@@QEAA@XZ; CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::~CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>(void)
0x18004ee80  nop
0x18004ee81  mov     rcx, rsi; lpMem
0x18004ee84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004ee89  mov     rcx, [rbp+ppv]
0x18004ee8d  mov     rax, [rcx]
0x18004ee90  mov     rax, [rax+10h]
0x18004ee94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee99  test    edi, edi
0x18004ee9b  js      short loc_18004EEB6
0x18004ee9d  lock inc dword ptr [rbx]
0x18004eea0  mov     [r12], rbx
0x18004eea4  jmp     short loc_18004EEB6
0x18004eea6  lock inc dword ptr [rbx]
0x18004eea9  mov     [r12], rbx
0x18004eead  xor     edi, edi
0x18004eeaf  jmp     short loc_18004EEB6
0x18004eeb1  mov     edi, 8007000Eh
0x18004eeb6  mov     rcx, rbx; this
0x18004eeb9  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x18004eebe  jmp     short loc_18004EEC5
0x18004eec0  mov     edi, 8007000Eh
0x18004eec5  mov     eax, edi
0x18004eec7  mov     rbx, [rsp+30h+arg_0]
0x18004eecc  mov     rsi, [rsp+30h+arg_8]
0x18004eed1  add     rsp, 30h
0x18004eed5  pop     r15
0x18004eed7  pop     r14
0x18004eed9  pop     r12
0x18004eedb  pop     rdi
0x18004eedc  pop     rbp
0x18004eedd  retn
```
