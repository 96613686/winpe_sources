# ReparseRelativeIDListInternal(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_GUID const &,IShellFolder *,ReparseRelativeIdListFlags,IBindCtx *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x1800b0ea0`
- end: `0x1800b16c1`
- name: `?ReparseRelativeIDListInternal@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@0W4ReparseRelativeIdListFlags@@PEAUIBindCtx@@PEAPEAU2@@Z`
- size: `2081`
- prototype: `int __high(struct IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, struct IShellFolder *, enum ReparseRelativeIdListFlags, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x1800b06a4`
- `0x1800b06e0`
- `0x1800b1a00`
- `0x18027b738`

## callees

- `0x18005bbf0`
- `0x18005d760`
- `0x1800625e0`
- `0x180064ad0`
- `0x180067680`
- `0x18008c740`
- `0x1800b0560`
- `0x1800b0ea0`
- `0x1800b16c8`
- `0x1802d17f8`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x1804a5d40`
- `0x18067d010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800b1126`
- `OLEAUT32!__imp_VariantClear` at `0x1800b1126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b140b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b141b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b160f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b140b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b141b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b160f`
- `SHCORE!__imp_StrRetToStrW` at `0x1800b1051`
- `SHCORE!__imp_StrRetToStrW` at `0x1800b1051`
- `PROPSYS!VariantToBuffer` at `0x1800b168b`
- `PROPSYS!VariantToBuffer` at `0x1800b168b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b12b4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b13cf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b158a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b12b4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b13cf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800b158a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ReparseRelativeIDListInternal(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, IShellFolder **),
        const ITEMIDLIST *a2,
        __int128 *a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, IUnknown **),
        char a5,
        IUnknown *a6,
        struct _ITEMIDLIST_RELATIVE **a7)
{
  __int128 *v8; // r12
  struct _ITEMIDLIST_RELATIVE **v10; // r15
  __int64 result; // rax
  HRESULT v12; // edi
  char v13; // si
  const struct _ITEMIDLIST_RELATIVE *v14; // r14
  IShellFolder *v15; // rbx
  ITEMIDLIST *v16; // rsi
  const ITEMIDLIST *v17; // rax
  USHORT cb; // cx
  const ITEMIDLIST *v19; // rbx
  IUnknown *v20; // rbx
  IShellFolder *v21; // rbx
  int v22; // eax
  __int64 v23; // rdx
  HRESULT v24; // eax
  CDummyUnknown *v25; // rax
  CDummyUnknown *v26; // rdi
  _WORD *v27; // rcx
  _WORD *v28; // rcx
  void *v29; // r12
  struct _ITEMIDLIST_RELATIVE *v30; // r15
  struct _ITEMIDLIST_RELATIVE *v31; // rdx
  int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // r14
  unsigned __int16 *v35; // rdx
  unsigned int v36; // edi
  __int64 v37; // rcx
  char *v38; // rax
  char *v39; // rsi
  IUnknown *v40; // rcx
  _WORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  const struct _ITEMIDLIST_RELATIVE *v44; // [rsp+48h] [rbp-B8h]
  __int128 Buf2; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  IShellFolder *psf; // [rsp+78h] [rbp-88h] BYREF
  IUnknown *ppunk; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ppsz; // [rsp+88h] [rbp-78h] BYREF
  IUnknown *v52[2]; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW pstr; // [rsp+C0h] [rbp-40h] BYREF

  v8 = a3;
  v10 = a7;
  *a7 = 0;
  psf = 0;
  result = (**a1)(a1, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &psf);
  if ( (int)result < 0 )
    return result;
  ppunk = 0;
  v12 = (**a4)(a4, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppunk);
  if ( v12 < 0 )
    goto LABEL_72;
  v13 = a5;
  Buf2 = *v8;
  while ( a2 && a2->mkid.cb )
  {
    if ( v12 < 0 )
      goto LABEL_87;
    v14 = (const struct _ITEMIDLIST_RELATIVE *)ILCloneFirst(a2);
    v44 = v14;
    if ( v14 )
    {
      ppsz = 0;
      punk = 0;
      v15 = psf;
      if ( psf )
      {
        if ( !*(_WORD *)v14 || (v41 = (_WORD *)((char *)v14 + *(unsigned __int16 *)v14)) == 0 || !*v41 )
        {
          v12 = ((__int64 (__fastcall *)(IShellFolder *, GUID *, IUnknown **))psf->lpVtbl->QueryInterface)(
                  psf,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &punk);
          goto LABEL_11;
        }
      }
      v16 = (ITEMIDLIST *)ILCloneParent(v14);
      if ( v16 )
      {
        v12 = SHBindToObject(v15, v16, 0, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&punk);
        CoTaskMemFree(v16);
        v13 = a5;
LABEL_11:
        if ( v12 >= 0 )
        {
          v17 = (const ITEMIDLIST *)v14;
          cb = *(_WORD *)v14;
          if ( *(_WORD *)v14 )
          {
            do
            {
              v19 = v17;
              v17 = (const ITEMIDLIST *)((char *)v17 + cb);
              cb = v17->mkid.cb;
            }
            while ( v17->mkid.cb );
          }
          else
          {
            v19 = (const ITEMIDLIST *)v14;
          }
          memset_0(&pstr, 0, 0x110u);
          v12 = ((__int64 (__fastcall *)(IUnknown *, const ITEMIDLIST *, __int64, struct _WIN32_FIND_DATAW *))punk->lpVtbl[3].Release)(
                  punk,
                  v19,
                  32769,
                  &pstr);
          if ( v12 >= 0 )
            v12 = StrRetToStrW((STRRET *)&pstr, v19, &ppsz);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          if ( v12 >= 0 )
          {
            v20 = a6;
            v52[0] = a6;
            if ( a6 )
            {
              ((void (__fastcall *)(IUnknown *))a6->lpVtbl->AddRef)(a6);
              v20 = v52[0];
            }
            if ( !v20 )
            {
              v21 = psf;
              punk = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              if ( ((int (__fastcall *)(IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const PROPERTYKEY *, VARIANTARG *))psf->lpVtbl[1].EnumObjects)(
                     psf,
                     v14,
                     &PKEY_ParsingBindContext,
                     &pvarg) >= 0 )
              {
                punk = 0;
                if ( pvarg.vt == 13 && pvarg.llVal || (v12 = -2147467262, pvarg.vt == 9) && pvarg.llVal )
                {
                  v22 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, IUnknown **))pvarg.llVal)(
                          pvarg.llVal,
                          &GUID_0000000e_0000_0000_c000_000000000046,
                          &punk);
                  goto LABEL_24;
                }
                goto LABEL_25;
              }
              if ( ((int (__fastcall *)(IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const PROPERTYKEY *, VARIANTARG *))v21->lpVtbl[1].EnumObjects)(
                     v21,
                     v14,
                     &PKEY_FindData,
                     &pvarg) >= 0 )
              {
                memset_0(&pstr, 0, sizeof(pstr));
                v12 = VariantToBuffer(&pvarg, &pstr, 0x250u);
                if ( v12 >= 0 )
                {
                  v22 = _CreateFileSysBindCtx(0, &pstr, (struct IBindCtx **)&punk);
LABEL_24:
                  v12 = v22;
                }
LABEL_25:
                VariantClear(&pvarg);
              }
              else
              {
                v12 = SHCreateOriginalItemBindCtx(v43, v21, v14);
              }
              if ( v12 >= 0 )
              {
                v24 = (v13 & 1) != 0
                    ? ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))punk->lpVtbl->QueryInterface)(
                        punk,
                        &GUID_0000000e_0000_0000_c000_000000000046,
                        v52)
                    : BindCtx_SetMode_2(punk, v23, v52);
                v12 = v24;
                ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                if ( v12 >= 0 )
                {
                  v20 = v52[0];
                  goto LABEL_31;
                }
              }
              goto LABEL_63;
            }
LABEL_31:
            if ( (v13 & 2) != 0 )
            {
              v12 = BindCtx_AddObjectParam_2(v20, L"ParseUseSourceItemAsDelegateItem");
              if ( v12 < 0 )
                goto LABEL_63;
              v20 = v52[0];
            }
            v25 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            *(_QWORD *)&pvarg.vt = v25;
            if ( v25 )
            {
              v26 = CDummyUnknown::CDummyUnknown(v25);
              if ( v26 )
              {
                ((void (__fastcall *)(IUnknown *, const unsigned __int16 *, CDummyUnknown *))v20->lpVtbl[3].QueryInterface)(
                  v20,
                  L"ValidateRegItems",
                  v26);
                if ( (int)--*((_DWORD *)v26 + 6) <= 0 )
                  operator delete(v26, (const struct std::nothrow_t *)0x40);
              }
            }
            if ( !a2->mkid.cb || (v27 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb)) == 0 || !*v27 )
            {
              if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
              {
                punk = 0;
                *(_OWORD *)&pvarg.vt = *v8;
                if ( (int)_CreatePropertyBagBindCtx<_GUID>(v52[0], v42, &pvarg, &punk) >= 0 )
                {
                  IUnknown_Set(v52, punk);
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
              }
            }
            Src = 0;
            v12 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, IUnknown *, LPWSTR, _QWORD, void **, _QWORD))ppunk->lpVtbl[1].QueryInterface)(
                    ppunk,
                    0,
                    v52[0],
                    ppsz,
                    0,
                    &Src,
                    0);
            if ( v12 >= 0 )
            {
              if ( a2->mkid.cb && (v28 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb)) != 0 && *v28 )
              {
                *(_QWORD *)&pvarg.vt = 0;
                v12 = ((__int64 (__fastcall *)(IUnknown *, void *, _QWORD, GUID *, VARIANTARG *))ppunk->lpVtbl[1].Release)(
                        ppunk,
                        Src,
                        0,
                        &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                        &pvarg);
                if ( v12 >= 0 )
                {
                  IUnknown_Set(&ppunk, *(IUnknown **)&pvarg.vt);
                  v29 = Src;
                  v30 = *v10;
                  if ( Src )
                  {
                    if ( !v30 )
                    {
                      *a7 = (struct _ITEMIDLIST_RELATIVE *)Src;
                      Src = 0;
                      goto LABEL_59;
                    }
                    v31 = v30;
                    v32 = 2;
                    do
                    {
                      v33 = *(unsigned __int16 *)v31;
                      if ( !(_WORD)v33 )
                        break;
                      v32 += v33;
                      v31 = (struct _ITEMIDLIST_RELATIVE *)((char *)v31 + v33);
                    }
                    while ( v31 );
                    v34 = (unsigned int)(v32 - 2);
                    v35 = (unsigned __int16 *)Src;
                    v36 = 2;
                    do
                    {
                      v37 = *v35;
                      if ( !(_WORD)v37 )
                        break;
                      v36 += v37;
                      v35 = (unsigned __int16 *)((char *)v35 + v37);
                    }
                    while ( v35 );
                    v38 = (char *)WINRT_IMPL_CoTaskMemAlloc(v36 + (unsigned int)v34);
                    v39 = v38;
                    if ( v38 )
                    {
                      memset_0(v38, 0, v36 + (unsigned int)v34);
                      memcpy_0(v39, v30, (unsigned int)v34);
                      memcpy_0(&v39[v34], v29, v36);
                    }
                    *a7 = (struct _ITEMIDLIST_RELATIVE *)v39;
                    v12 = 0;
                    if ( !v39 )
                      v12 = -2147024882;
                    CoTaskMemFree(v30);
                    CoTaskMemFree(v29);
                    Src = 0;
                    v14 = v44;
                    if ( v39 )
                    {
LABEL_59:
                      punk = 0;
                      v12 = ((__int64 (__fastcall *)(IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, _QWORD, GUID *, IUnknown **))psf->lpVtbl->BindToObject)(
                              psf,
                              v14,
                              0,
                              &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                              &punk);
                      if ( v12 >= 0 )
                      {
                        IUnknown_Set((IUnknown **)&psf, punk);
                        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                      }
                    }
                  }
                  else
                  {
                    Src = 0;
                    if ( v30 )
                      goto LABEL_59;
                    v12 = -2147024809;
                  }
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
                  v10 = a7;
                  v8 = a3;
                }
              }
              else
              {
                v12 = _ILCombineAndFree(*v10, (struct _ITEMIDLIST_RELATIVE *)Src, v10);
                Src = 0;
              }
              CoTaskMemFree(Src);
            }
LABEL_63:
            CoTaskMemFree(ppsz);
            v40 = v52[0];
            if ( v52[0] )
            {
              v52[0] = 0;
              ((void (__fastcall *)(IUnknown *))v40->lpVtbl->Release)(v40);
            }
          }
        }
      }
      else
      {
        v12 = -2147024882;
      }
      CoTaskMemFree(v14);
      v13 = a5;
      goto LABEL_66;
    }
    v12 = -2147024882;
LABEL_66:
    a2 = (const ITEMIDLIST *)((char *)a2 + a2->mkid.cb);
  }
  if ( v12 < 0 )
  {
LABEL_87:
    CoTaskMemFree(*v10);
    *v10 = 0;
    goto LABEL_71;
  }
  if ( !*v10 )
    v12 = -2147467259;
LABEL_71:
  ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
LABEL_72:
  ((void (__fastcall *)(IShellFolder *))psf->lpVtbl->Release)(psf);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b0ea0  push    rbp
0x1800b0ea2  push    rbx
0x1800b0ea3  push    rsi
0x1800b0ea4  push    rdi
0x1800b0ea5  push    r12
0x1800b0ea7  push    r13
0x1800b0ea9  push    r14
0x1800b0eab  push    r15
0x1800b0ead  lea     rbp, [rsp-228h]
0x1800b0eb5  sub     rsp, 328h
0x1800b0ebc  mov     rax, cs:__security_cookie
0x1800b0ec3  xor     rax, rsp
0x1800b0ec6  mov     [rbp+260h+var_50], rax
0x1800b0ecd  mov     rbx, r9
0x1800b0ed0  mov     r12, r8
0x1800b0ed3  mov     [rsp+360h+var_310], r8
0x1800b0ed8  mov     r13, rdx
0x1800b0edb  mov     r15, [rbp+260h+arg_30]
0x1800b0ee2  mov     [rsp+360h+var_320], r15
0x1800b0ee7  xor     r14d, r14d
0x1800b0eea  mov     [r15], r14
0x1800b0eed  mov     [rsp+360h+psf], r14
0x1800b0ef2  mov     rax, [rcx]
0x1800b0ef5  lea     r8, [rsp+360h+psf]
0x1800b0efa  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800b0f01  mov     rax, [rax]
0x1800b0f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f09  test    eax, eax
0x1800b0f0b  js      loc_1800B14A1
0x1800b0f11  mov     [rbp+260h+ppunk], r14
0x1800b0f15  mov     rax, [rbx]
0x1800b0f18  lea     r8, [rbp+260h+ppunk]
0x1800b0f1c  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800b0f23  mov     rcx, rbx
0x1800b0f26  mov     rax, [rax]
0x1800b0f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f2e  mov     edi, eax
0x1800b0f30  test    eax, eax
0x1800b0f32  js      loc_1800B148E
0x1800b0f38  mov     esi, dword ptr [rbp+260h+arg_20]
0x1800b0f3e  movups  xmm0, xmmword ptr [r12]
0x1800b0f43  movups  [rsp+360h+Buf2], xmm0
0x1800b0f48  mov     ebx, 8007000Eh
0x1800b0f4d  test    r13, r13
0x1800b0f50  jz      loc_1800B146C
0x1800b0f56  cmp     word ptr [r13+0], 0
0x1800b0f5c  jz      loc_1800B146C
0x1800b0f62  test    edi, edi
0x1800b0f64  js      loc_1800B160C
0x1800b0f6a  mov     rcx, r13; pidl
0x1800b0f6d  call    ILCloneFirst
0x1800b0f72  mov     r14, rax
0x1800b0f75  mov     [rsp+360h+var_318], rax
0x1800b0f7a  test    rax, rax
0x1800b0f7d  jz      loc_1800B1468
0x1800b0f83  xor     eax, eax
0x1800b0f85  mov     [rbp+260h+ppsz], rax
0x1800b0f89  mov     [rsp+360h+punk], rax
0x1800b0f8e  mov     rbx, [rsp+360h+psf]
0x1800b0f93  test    rbx, rbx
0x1800b0f96  jnz     loc_1800B14C5
0x1800b0f9c  mov     rcx, r14; Src
0x1800b0f9f  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x1800b0fa4  mov     rsi, rax
0x1800b0fa7  test    rax, rax
0x1800b0faa  jz      loc_1800B1500
0x1800b0fb0  lea     rax, [rsp+360h+punk]
0x1800b0fb5  mov     [rsp+360h+ppv], rax; ppv
0x1800b0fba  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800b0fc1  xor     r8d, r8d; pbc
0x1800b0fc4  mov     rdx, rsi; pidl
0x1800b0fc7  mov     rcx, rbx; psf
0x1800b0fca  call    SHBindToObject
0x1800b0fcf  mov     edi, eax
0x1800b0fd1  mov     rcx, rsi; pv
0x1800b0fd4  call    cs:__imp_CoTaskMemFree
0x1800b0fdb  nop     dword ptr [rax+rax+00h]
0x1800b0fe0  mov     esi, dword ptr [rbp+260h+arg_20]
0x1800b0fe6  test    edi, edi
0x1800b0fe8  js      loc_1800B1446
0x1800b0fee  mov     rax, r14
0x1800b0ff1  movzx   ecx, word ptr [r14]
0x1800b0ff5  test    cx, cx
0x1800b0ff8  jz      loc_1800B1639
0x1800b0ffe  xchg    ax, ax
0x1800b1000  mov     rbx, rax
0x1800b1003  movzx   ecx, cx
0x1800b1006  add     rax, rcx
0x1800b1009  movzx   ecx, word ptr [rax]
0x1800b100c  test    cx, cx
0x1800b100f  jnz     short loc_1800B1000
0x1800b1011  xor     edx, edx; Val
0x1800b1013  mov     r8d, 110h; Size
0x1800b1019  lea     rcx, [rbp+260h+pstr]; void *
0x1800b101d  call    memset_0
0x1800b1022  mov     rcx, [rsp+360h+punk]
0x1800b1027  mov     rax, [rcx]
0x1800b102a  lea     r9, [rbp+260h+pstr]
0x1800b102e  mov     r8d, 8001h
0x1800b1034  mov     rdx, rbx
0x1800b1037  mov     rax, [rax+58h]
0x1800b103b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1040  mov     edi, eax
0x1800b1042  test    eax, eax
0x1800b1044  js      short loc_1800B105F
0x1800b1046  lea     r8, [rbp+260h+ppsz]; ppsz
0x1800b104a  mov     rdx, rbx; pidl
0x1800b104d  lea     rcx, [rbp+260h+pstr]; pstr
0x1800b1051  call    cs:__imp_StrRetToStrW
0x1800b1058  nop     dword ptr [rax+rax+00h]
0x1800b105d  mov     edi, eax
0x1800b105f  mov     rcx, [rsp+360h+punk]
0x1800b1064  mov     rax, [rcx]
0x1800b1067  mov     rax, [rax+10h]
0x1800b106b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1070  test    edi, edi
0x1800b1072  js      loc_1800B1446
0x1800b1078  mov     rcx, [rbp+260h+arg_28]
0x1800b107f  mov     rbx, rcx
0x1800b1082  mov     [rbp+260h+var_2D0], rcx
0x1800b1086  test    rcx, rcx
0x1800b1089  jz      short loc_1800B109B
0x1800b108b  mov     rax, [rcx]
0x1800b108e  mov     rax, [rax+8]
0x1800b1092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1097  mov     rbx, [rbp+260h+var_2D0]
0x1800b109b  test    rbx, rbx
0x1800b109e  jnz     loc_1800B117E
0x1800b10a4  mov     rbx, [rsp+360h+psf]
0x1800b10a9  xor     edi, edi
0x1800b10ab  mov     [rsp+360h+punk], rdi
0x1800b10b0  xorps   xmm0, xmm0
0x1800b10b3  xor     eax, eax
0x1800b10b5  movups  xmmword ptr [rbp+260h+pvarg], xmm0
0x1800b10b9  mov     qword ptr [rbp+260h+pvarg+10h], rax
0x1800b10bd  mov     rax, [rbx]
0x1800b10c0  lea     r9, [rbp+260h+pvarg]
0x1800b10c4  lea     r8, PKEY_ParsingBindContext
0x1800b10cb  mov     rdx, r14
0x1800b10ce  mov     rcx, rbx
0x1800b10d1  mov     rax, [rax+88h]
0x1800b10d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b10dd  test    eax, eax
0x1800b10df  js      loc_1800B15AC
0x1800b10e5  mov     [rsp+360h+punk], rdi
0x1800b10ea  movzx   eax, word ptr [rbp+260h+pvarg]
0x1800b10ee  mov     ecx, 0Dh
0x1800b10f3  cmp     cx, ax
0x1800b10f6  mov     rcx, qword ptr [rbp+260h+pvarg+8]
0x1800b10fa  jnz     loc_1800B1641
0x1800b1100  test    rcx, rcx
0x1800b1103  jz      loc_1800B1641
0x1800b1109  mov     rax, [rcx]
0x1800b110c  lea     r8, [rsp+360h+punk]
0x1800b1111  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x1800b1118  mov     rax, [rax]
0x1800b111b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1120  mov     edi, eax
0x1800b1122  lea     rcx, [rbp+260h+pvarg]; pvarg
0x1800b1126  call    cs:__imp_VariantClear
0x1800b112d  nop     dword ptr [rax+rax+00h]
0x1800b1132  test    edi, edi
0x1800b1134  js      loc_1800B1417
0x1800b113a  mov     rcx, [rsp+360h+punk]
0x1800b113f  lea     r8, [rbp+260h+var_2D0]
0x1800b1143  test    sil, 1
0x1800b1147  jz      loc_1800B16B6
0x1800b114d  mov     rax, [rcx]
0x1800b1150  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x1800b1157  mov     rax, [rax]
0x1800b115a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b115f  mov     edi, eax
0x1800b1161  mov     rcx, [rsp+360h+punk]
0x1800b1166  mov     rax, [rcx]
0x1800b1169  mov     rax, [rax+10h]
0x1800b116d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1172  test    edi, edi
0x1800b1174  js      loc_1800B1417
0x1800b117a  mov     rbx, [rbp+260h+var_2D0]
0x1800b117e  test    sil, 2
0x1800b1182  jz      short loc_1800B11A1
0x1800b1184  lea     rdx, aParseusesource; "ParseUseSourceItemAsDelegateItem"
0x1800b118b  mov     rcx, rbx
0x1800b118e  call    BindCtx_AddObjectParam_2
0x1800b1193  mov     edi, eax
0x1800b1195  test    eax, eax
0x1800b1197  js      loc_1800B1417
0x1800b119d  mov     rbx, [rbp+260h+var_2D0]
0x1800b11a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b11a8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800b11ad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b11b2  mov     qword ptr [rbp+260h+pvarg], rax
0x1800b11b6  test    rax, rax
0x1800b11b9  jz      short loc_1800B11F1
0x1800b11bb  mov     rcx, rax; this
0x1800b11be  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x1800b11c3  mov     rdi, rax
0x1800b11c6  test    rax, rax
0x1800b11c9  jz      short loc_1800B11F1
0x1800b11cb  mov     rdx, [rbx]
0x1800b11ce  mov     rax, [rdx+48h]
0x1800b11d2  mov     r8, rdi
0x1800b11d5  lea     rdx, aValidateregite; "ValidateRegItems"
0x1800b11dc  mov     rcx, rbx
0x1800b11df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b11e4  dec     dword ptr [rdi+18h]
0x1800b11e7  cmp     dword ptr [rdi+18h], 0
0x1800b11eb  jle     loc_1800B150A
0x1800b11f1  movzx   eax, word ptr [r13+0]
0x1800b11f6  test    ax, ax
0x1800b11f9  jz      loc_1800B1538
0x1800b11ff  mov     ecx, eax
0x1800b1201  add     rcx, r13
0x1800b1204  jz      loc_1800B1538
0x1800b120a  cmp     word ptr [rcx], 0
0x1800b120e  jz      loc_1800B1538
0x1800b1214  xor     ebx, ebx
0x1800b1216  mov     [rsp+360h+Src], rbx
0x1800b121b  mov     rcx, [rbp+260h+ppunk]
0x1800b121f  mov     rax, [rcx]
0x1800b1222  mov     [rsp+360h+var_330], rbx
0x1800b1227  lea     rdx, [rsp+360h+Src]
0x1800b122c  mov     [rsp+360h+var_338], rdx
0x1800b1231  mov     [rsp+360h+ppv], rbx
0x1800b1236  mov     r9, [rbp+260h+ppsz]
0x1800b123a  mov     r8, [rbp+260h+var_2D0]
0x1800b123e  xor     edx, edx
0x1800b1240  mov     rax, [rax+18h]
0x1800b1244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1249  mov     edi, eax
0x1800b124b  test    eax, eax
0x1800b124d  js      loc_1800B1417
0x1800b1253  movzx   eax, word ptr [r13+0]
0x1800b1258  test    ax, ax
0x1800b125b  jz      loc_1800B151C
0x1800b1261  mov     ecx, eax
0x1800b1263  add     rcx, r13
0x1800b1266  jz      loc_1800B151C
0x1800b126c  cmp     word ptr [rcx], 0
0x1800b1270  jz      loc_1800B151C
0x1800b1276  mov     qword ptr [rbp+260h+pvarg], rbx
0x1800b127a  mov     rcx, [rbp+260h+ppunk]
0x1800b127e  mov     rax, [rcx]
0x1800b1281  lea     rdx, [rbp+260h+pvarg]
0x1800b1285  mov     [rsp+360h+ppv], rdx
0x1800b128a  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800b1291  xor     r8d, r8d
0x1800b1294  mov     rdx, [rsp+360h+Src]
0x1800b1299  mov     rax, [rax+28h]
0x1800b129d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b12a2  mov     edi, eax
0x1800b12a4  test    eax, eax
0x1800b12a6  js      loc_1800B1406
0x1800b12ac  mov     rdx, qword ptr [rbp+260h+pvarg]; punk
0x1800b12b0  lea     rcx, [rbp+260h+ppunk]; ppunk
0x1800b12b4  call    cs:__imp_IUnknown_Set
0x1800b12bb  nop     dword ptr [rax+rax+00h]
0x1800b12c0  mov     r12, [rsp+360h+Src]
0x1800b12c5  mov     r15, [r15]
0x1800b12c8  test    r12, r12
0x1800b12cb  jz      loc_1800B15F4
0x1800b12d1  test    r15, r15
0x1800b12d4  jz      loc_1800B1627
0x1800b12da  mov     rdx, r15
0x1800b12dd  mov     r8d, 2
0x1800b12e3  movzx   ecx, word ptr [rdx]
0x1800b12e6  test    cx, cx
0x1800b12e9  jz      short loc_1800B12F3
0x1800b12eb  add     r8d, ecx
0x1800b12ee  add     rdx, rcx
0x1800b12f1  jnz     short loc_1800B12E3
0x1800b12f3  lea     r14d, [r8-2]
0x1800b12f7  mov     rdx, r12
0x1800b12fa  mov     edi, 2
0x1800b12ff  nop
0x1800b1300  movzx   ecx, word ptr [rdx]
0x1800b1303  test    cx, cx
0x1800b1306  jz      short loc_1800B130F
0x1800b1308  add     edi, ecx
0x1800b130a  add     rdx, rcx
0x1800b130d  jnz     short loc_1800B1300
0x1800b130f  lea     eax, [rdi+r14]
0x1800b1313  mov     ebx, eax
0x1800b1315  mov     ecx, eax; cb
0x1800b1317  call    WINRT_IMPL_CoTaskMemAlloc
0x1800b131c  mov     rsi, rax
0x1800b131f  test    rax, rax
0x1800b1322  jz      short loc_1800B134E
0x1800b1324  mov     r8d, ebx; Size
0x1800b1327  xor     edx, edx; Val
0x1800b1329  mov     rcx, rax; void *
0x1800b132c  call    memset_0
0x1800b1331  mov     r8d, r14d; Size
0x1800b1334  mov     rdx, r15; Src
0x1800b1337  mov     rcx, rsi; void *
0x1800b133a  call    memcpy_0
0x1800b133f  mov     r8d, edi; Size
0x1800b1342  lea     rcx, [rsi+r14]; void *
0x1800b1346  mov     rdx, r12; Src
0x1800b1349  call    memcpy_0
  ... truncated ...
```
