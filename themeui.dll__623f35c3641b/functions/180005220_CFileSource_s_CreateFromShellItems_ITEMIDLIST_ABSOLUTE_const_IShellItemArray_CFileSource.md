# CFileSource::s_CreateFromShellItems(_ITEMIDLIST_ABSOLUTE const *,IShellItemArray *,CFileSource * *)

- ea: `0x180005220`
- end: `0x18000540a`
- name: `?s_CreateFromShellItems@CFileSource@@SAJPEFBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellItemArray@@PEAPEAV1@@Z`
- size: `490`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, struct IShellItemArray *, struct CFileSource **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800047ac`
- `0x18004949c`

## callees

- `0x180004c78`
- `0x1800051b8`
- `0x180005220`
- `0x180005410`
- `0x180019160`
- `0x180035ccc`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x1800052e8`
- `SHELL32!SHCreateItemFromIDList` at `0x1800052e8`
- `SHELL32!SHGetIDListFromObject` at `0x180005357`
- `SHELL32!SHGetIDListFromObject` at `0x180005357`
- `SHELL32!__imp_ILClone` at `0x180005287`
- `SHELL32!__imp_ILClone` at `0x180005287`
- `SHELL32!__imp_ILFree` at `0x180005379`
- `SHELL32!__imp_ILFree` at `0x180005379`

## pseudocode

```c
__int64 __fastcall CFileSource::s_CreateFromShellItems(
        LPCITEMIDLIST pidl,
        struct IShellItemArray *a2,
        struct CFileSource **a3)
{
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx
  LPITEMIDLIST v8; // rax
  struct IShellItemArrayVtbl *lpVtbl; // rax
  HRESULT Instance; // edi
  const ITEMIDLIST *v11; // rcx
  LPITEMIDLIST v12; // rsi
  unsigned int v13; // r14d
  struct IShellItemArrayVtbl *v14; // rax
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
        lpVtbl = a2->lpVtbl;
        cItemGrow = 0;
        Instance = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))lpVtbl->GetCount)(a2, &cItemGrow);
        if ( Instance >= 0 )
        {
          if ( !cItemGrow )
            goto LABEL_22;
          v11 = (const ITEMIDLIST *)*((_QWORD *)v7 + 1);
          ppv = 0;
          Instance = SHCreateItemFromIDList(v11, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( Instance >= 0 )
          {
            ppidl = 0;
            Instance = CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::s_CreateInstance(cItemGrow);
            if ( Instance >= 0 )
            {
              v12 = ppidl;
              v13 = 0;
              while ( v13 < cItemGrow )
              {
                v14 = a2->lpVtbl;
                punk = 0;
                Instance = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, IUnknown **))v14->GetItemAt)(
                             a2,
                             v13,
                             &punk);
                if ( Instance >= 0 )
                {
                  ppidl = 0;
                  Instance = SHGetIDListFromObject(punk, &ppidl);
                  if ( Instance >= 0 )
                  {
                    Instance = CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::AppendPtr(v12, ppidl);
                    if ( Instance < 0 )
                      ILFree(ppidl);
                  }
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
                ++v13;
                if ( Instance < 0 )
                  goto LABEL_20;
              }
              if ( *(_QWORD *)&v12->mkid.cb && **(int **)&v12->mkid.cb > 0 )
              {
                *((_QWORD *)v7 + 2) = v12;
                _InterlockedIncrement((volatile signed __int32 *)v12[2].mkid.abID);
              }
LABEL_20:
              CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(v12);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            if ( Instance >= 0 )
            {
LABEL_22:
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
0x180005220  mov     [rsp-28h+arg_0], rbx
0x180005225  mov     [rsp-28h+arg_8], rsi
0x18000522a  push    rbp
0x18000522b  push    rdi
0x18000522c  push    r12
0x18000522e  push    r14
0x180005230  push    r15
0x180005232  mov     rbp, rsp
0x180005235  sub     rsp, 30h
0x180005239  mov     r15, rdx
0x18000523c  mov     qword ptr [r8], 0
0x180005243  mov     rdi, rcx
0x180005246  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000524d  mov     ecx, 20h ; ' '; unsigned __int64
0x180005252  mov     r12, r8
0x180005255  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000525a  mov     rbx, rax
0x18000525d  test    rax, rax
0x180005260  jz      loc_1800053EC
0x180005266  mov     rcx, rdi; pidl
0x180005269  mov     dword ptr [rax], 1
0x18000526f  mov     qword ptr [rax+8], 0
0x180005277  mov     qword ptr [rax+10h], 0
0x18000527f  mov     qword ptr [rax+18h], 0
0x180005287  call    cs:__imp_ILClone
0x18000528d  mov     [rbx+8], rax
0x180005291  test    rax, rax
0x180005294  jz      loc_1800053DD
0x18000529a  test    r15, r15
0x18000529d  jz      loc_1800053D2
0x1800052a3  mov     rax, [r15]
0x1800052a6  lea     rdx, [rbp+cItemGrow]
0x1800052aa  mov     rcx, r15
0x1800052ad  mov     [rbp+cItemGrow], 0
0x1800052b4  mov     rax, [rax+38h]
0x1800052b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052bd  mov     edi, eax
0x1800052bf  test    eax, eax
0x1800052c1  js      loc_1800053E2
0x1800052c7  cmp     [rbp+cItemGrow], 0
0x1800052cb  jbe     loc_1800053C9
0x1800052d1  mov     rcx, [rbx+8]; pidl
0x1800052d5  lea     r8, [rbp+ppv]; ppv
0x1800052d9  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800052e0  mov     [rbp+ppv], 0
0x1800052e8  call    cs:__imp_SHCreateItemFromIDList
0x1800052ee  mov     edi, eax
0x1800052f0  test    eax, eax
0x1800052f2  js      loc_1800053E2
0x1800052f8  mov     ecx, [rbp+cItemGrow]; cItemGrow
0x1800052fb  lea     rdx, [rbp+ppidl]
0x1800052ff  mov     [rbp+ppidl], 0
0x180005307  call    ?s_CreateInstance@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@SAJKPEAPEAV1@@Z; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::s_CreateInstance(ulong,CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>> * *)
0x18000530c  mov     edi, eax
0x18000530e  test    eax, eax
0x180005310  js      loc_1800053B5
0x180005316  mov     rsi, [rbp+ppidl]
0x18000531a  xor     r14d, r14d
0x18000531d  cmp     r14d, [rbp+cItemGrow]
0x180005321  jnb     short loc_180005398
0x180005323  mov     rax, [r15]
0x180005326  lea     r8, [rbp+punk]
0x18000532a  mov     edx, r14d
0x18000532d  mov     [rbp+punk], 0
0x180005335  mov     rcx, r15
0x180005338  mov     rax, [rax+40h]
0x18000533c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005341  mov     edi, eax
0x180005343  test    eax, eax
0x180005345  js      short loc_18000538F
0x180005347  mov     rcx, [rbp+punk]; punk
0x18000534b  lea     rdx, [rbp+ppidl]; ppidl
0x18000534f  mov     [rbp+ppidl], 0
0x180005357  call    cs:__imp_SHGetIDListFromObject
0x18000535d  mov     edi, eax
0x18000535f  test    eax, eax
0x180005361  js      short loc_18000537F
0x180005363  mov     rdx, [rbp+ppidl]
0x180005367  mov     rcx, rsi
0x18000536a  call    ?AppendPtr@?$CDPA_Base@U_ITEMIDLIST_ABSOLUTE@@VCTContainer_PolicyCoTaskMem@@@@QEAAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAH@Z; CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::AppendPtr(_ITEMIDLIST_ABSOLUTE *,int *)
0x18000536f  mov     edi, eax
0x180005371  test    eax, eax
0x180005373  jns     short loc_18000537F
0x180005375  mov     rcx, [rbp+ppidl]; pidl
0x180005379  call    cs:__imp_ILFree
0x18000537f  mov     rcx, [rbp+punk]
0x180005383  mov     rax, [rcx]
0x180005386  mov     rax, [rax+10h]
0x18000538a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538f  inc     r14d
0x180005392  test    edi, edi
0x180005394  jns     short loc_18000531D
0x180005396  jmp     short loc_1800053AD
0x180005398  mov     rax, [rsi]
0x18000539b  test    rax, rax
0x18000539e  jz      short loc_1800053AD
0x1800053a0  cmp     dword ptr [rax], 0
0x1800053a3  jle     short loc_1800053AD
0x1800053a5  mov     [rbx+10h], rsi
0x1800053a9  lock inc dword ptr [rsi+8]
0x1800053ad  mov     rcx, rsi; lpMem
0x1800053b0  call    ?Release@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAKXZ; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(void)
0x1800053b5  mov     rcx, [rbp+ppv]
0x1800053b9  mov     rax, [rcx]
0x1800053bc  mov     rax, [rax+10h]
0x1800053c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c5  test    edi, edi
0x1800053c7  js      short loc_1800053E2
0x1800053c9  lock inc dword ptr [rbx]
0x1800053cc  mov     [r12], rbx
0x1800053d0  jmp     short loc_1800053E2
0x1800053d2  lock inc dword ptr [rbx]
0x1800053d5  mov     [r12], rbx
0x1800053d9  xor     edi, edi
0x1800053db  jmp     short loc_1800053E2
0x1800053dd  mov     edi, 8007000Eh
0x1800053e2  mov     rcx, rbx; this
0x1800053e5  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x1800053ea  jmp     short loc_1800053F1
0x1800053ec  mov     edi, 8007000Eh
0x1800053f1  mov     rbx, [rsp+30h+arg_0]
0x1800053f6  mov     eax, edi
0x1800053f8  mov     rsi, [rsp+30h+arg_8]
0x1800053fd  add     rsp, 30h
0x180005401  pop     r15
0x180005403  pop     r14
0x180005405  pop     r12
0x180005407  pop     rdi
0x180005408  pop     rbp
0x180005409  retn
```
