# ReparseRelativeIDListInternal(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_GUID const &,IShellFolder *,ReparseRelativeIdListFlags,IBindCtx *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x18004ee30`
- end: `0x18004f612`
- name: `?ReparseRelativeIDListInternal@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@0W4ReparseRelativeIdListFlags@@PEAUIBindCtx@@PEAPEAU2@@Z`
- size: `2018`
- prototype: `int __high(struct IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, struct IShellFolder *, enum ReparseRelativeIdListFlags, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18004e674`
- `0x18004e6b0`
- `0x18004f930`
- `0x18026d92c`

## callees

- `0x18004e540`
- `0x18004ee30`
- `0x18004f618`
- `0x180055a88`
- `0x180055fb0`
- `0x1800d0990`
- `0x1800d2dc0`
- `0x1800d5920`
- `0x1800dfcf0`
- `0x1802c2754`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x180493200`
- `0x18065a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004f0b0`
- `OLEAUT32!__imp_VariantClear` at `0x18004f5fc`
- `OLEAUT32!__imp_VariantClear` at `0x18004f0b0`
- `OLEAUT32!__imp_VariantClear` at `0x18004f5fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f2e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f2f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f2e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f2f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f564`
- `SHCORE!__imp_StrRetToStrW` at `0x18004efe1`
- `SHCORE!__imp_StrRetToStrW` at `0x18004efe1`
- `PROPSYS!VariantToBuffer` at `0x18004f5da`
- `PROPSYS!VariantToBuffer` at `0x18004f5da`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f238`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f343`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f4e5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f238`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f343`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18004f4e5`

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
  __int64 v22; // rdx
  HRESULT v23; // eax
  CDummyUnknown *v24; // rax
  CDummyUnknown *v25; // rdi
  _WORD *v26; // rcx
  _WORD *v27; // rcx
  void *v28; // r12
  struct _ITEMIDLIST_RELATIVE *v29; // r15
  struct _ITEMIDLIST_RELATIVE *v30; // rdx
  int v31; // r8d
  __int64 v32; // rcx
  __int64 v33; // r14
  unsigned __int16 *v34; // rdx
  unsigned int v35; // edi
  __int64 v36; // rcx
  char *v37; // rax
  char *v38; // rsi
  IUnknown *v39; // rcx
  _WORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  const struct _ITEMIDLIST_RELATIVE *v43; // [rsp+48h] [rbp-B8h]
  __int128 Buf2; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  IShellFolder *psf; // [rsp+78h] [rbp-88h] BYREF
  IUnknown *ppunk; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ppsz; // [rsp+88h] [rbp-78h] BYREF
  IUnknown *v51[2]; // [rsp+90h] [rbp-70h] BYREF
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
    goto LABEL_71;
  v13 = a5;
  Buf2 = *v8;
  while ( a2 && a2->mkid.cb )
  {
    if ( v12 < 0 )
      goto LABEL_86;
    v14 = (const struct _ITEMIDLIST_RELATIVE *)ILCloneFirst(a2);
    v43 = v14;
    if ( v14 )
    {
      ppsz = 0;
      punk = 0;
      v15 = psf;
      if ( psf )
      {
        if ( !*(_WORD *)v14 || (v40 = (_WORD *)((char *)v14 + *(unsigned __int16 *)v14)) == 0 || !*v40 )
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
            v51[0] = a6;
            if ( a6 )
            {
              ((void (__fastcall *)(IUnknown *))a6->lpVtbl->AddRef)(a6);
              v20 = v51[0];
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
                  v12 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, IUnknown **))pvarg.llVal)(
                          pvarg.llVal,
                          &GUID_0000000e_0000_0000_c000_000000000046,
                          &punk);
                goto LABEL_24;
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
                  v12 = _CreateFileSysBindCtx(0, &pstr, (struct IBindCtx **)&punk);
LABEL_24:
                VariantClear(&pvarg);
              }
              else
              {
                v12 = SHCreateOriginalItemBindCtx(v42, v21, v14);
              }
              if ( v12 >= 0 )
              {
                v23 = (v13 & 1) != 0
                    ? ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))punk->lpVtbl->QueryInterface)(
                        punk,
                        &GUID_0000000e_0000_0000_c000_000000000046,
                        v51)
                    : BindCtx_SetMode_1(punk, v22, v51);
                v12 = v23;
                ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                if ( v12 >= 0 )
                {
                  v20 = v51[0];
                  goto LABEL_30;
                }
              }
              goto LABEL_62;
            }
LABEL_30:
            if ( (v13 & 2) != 0 )
            {
              v12 = BindCtx_AddObjectParam(v20, L"ParseUseSourceItemAsDelegateItem");
              if ( v12 < 0 )
                goto LABEL_62;
              v20 = v51[0];
            }
            v24 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            *(_QWORD *)&pvarg.vt = v24;
            if ( v24 )
            {
              v25 = CDummyUnknown::CDummyUnknown(v24);
              if ( v25 )
              {
                ((void (__fastcall *)(IUnknown *, const unsigned __int16 *, CDummyUnknown *))v20->lpVtbl[3].QueryInterface)(
                  v20,
                  L"ValidateRegItems",
                  v25);
                if ( (int)--*((_DWORD *)v25 + 6) <= 0 )
                  operator delete(v25, (const struct std::nothrow_t *)0x40);
              }
            }
            if ( !a2->mkid.cb || (v26 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb)) == 0 || !*v26 )
            {
              if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
              {
                punk = 0;
                *(_OWORD *)&pvarg.vt = *v8;
                if ( (int)_CreatePropertyBagBindCtx<_GUID>(v51[0], v41, &pvarg, &punk) >= 0 )
                {
                  IUnknown_Set(v51, punk);
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
              }
            }
            Src = 0;
            v12 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, IUnknown *, LPWSTR, _QWORD, void **, _QWORD))ppunk->lpVtbl[1].QueryInterface)(
                    ppunk,
                    0,
                    v51[0],
                    ppsz,
                    0,
                    &Src,
                    0);
            if ( v12 >= 0 )
            {
              if ( a2->mkid.cb && (v27 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb)) != 0 && *v27 )
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
                  v28 = Src;
                  v29 = *v10;
                  if ( Src )
                  {
                    if ( !v29 )
                    {
                      *a7 = (struct _ITEMIDLIST_RELATIVE *)Src;
                      Src = 0;
                      goto LABEL_58;
                    }
                    v30 = v29;
                    v31 = 2;
                    do
                    {
                      v32 = *(unsigned __int16 *)v30;
                      if ( !(_WORD)v32 )
                        break;
                      v31 += v32;
                      v30 = (struct _ITEMIDLIST_RELATIVE *)((char *)v30 + v32);
                    }
                    while ( v30 );
                    v33 = (unsigned int)(v31 - 2);
                    v34 = (unsigned __int16 *)Src;
                    v35 = 2;
                    do
                    {
                      v36 = *v34;
                      if ( !(_WORD)v36 )
                        break;
                      v35 += v36;
                      v34 = (unsigned __int16 *)((char *)v34 + v36);
                    }
                    while ( v34 );
                    v37 = (char *)WINRT_IMPL_CoTaskMemAlloc(v35 + (unsigned int)v33);
                    v38 = v37;
                    if ( v37 )
                    {
                      memset_0(v37, 0, v35 + (unsigned int)v33);
                      memcpy_0(v38, v29, (unsigned int)v33);
                      memcpy_0(&v38[v33], v28, v35);
                    }
                    *a7 = (struct _ITEMIDLIST_RELATIVE *)v38;
                    v12 = 0;
                    if ( !v38 )
                      v12 = -2147024882;
                    CoTaskMemFree(v29);
                    CoTaskMemFree(v28);
                    Src = 0;
                    v14 = v43;
                    if ( v38 )
                    {
LABEL_58:
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
                    if ( v29 )
                      goto LABEL_58;
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
LABEL_62:
            CoTaskMemFree(ppsz);
            v39 = v51[0];
            if ( v51[0] )
            {
              v51[0] = 0;
              ((void (__fastcall *)(IUnknown *))v39->lpVtbl->Release)(v39);
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
      goto LABEL_65;
    }
    v12 = -2147024882;
LABEL_65:
    a2 = (const ITEMIDLIST *)((char *)a2 + a2->mkid.cb);
  }
  if ( v12 < 0 )
  {
LABEL_86:
    CoTaskMemFree(*v10);
    *v10 = 0;
    goto LABEL_70;
  }
  if ( !*v10 )
    v12 = -2147467259;
LABEL_70:
  ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
LABEL_71:
  ((void (__fastcall *)(IShellFolder *))psf->lpVtbl->Release)(psf);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004ee30  push    rbp
0x18004ee32  push    rbx
0x18004ee33  push    rsi
0x18004ee34  push    rdi
0x18004ee35  push    r12
0x18004ee37  push    r13
0x18004ee39  push    r14
0x18004ee3b  push    r15
0x18004ee3d  lea     rbp, [rsp-228h]
0x18004ee45  sub     rsp, 328h
0x18004ee4c  mov     rax, cs:__security_cookie
0x18004ee53  xor     rax, rsp
0x18004ee56  mov     [rbp+260h+var_50], rax
0x18004ee5d  mov     rbx, r9
0x18004ee60  mov     r12, r8
0x18004ee63  mov     [rsp+360h+var_310], r8
0x18004ee68  mov     r13, rdx
0x18004ee6b  mov     r15, [rbp+260h+arg_30]
0x18004ee72  mov     [rsp+360h+var_320], r15
0x18004ee77  xor     r14d, r14d
0x18004ee7a  mov     [r15], r14
0x18004ee7d  mov     [rsp+360h+psf], r14
0x18004ee82  mov     rax, [rcx]
0x18004ee85  lea     r8, [rsp+360h+psf]
0x18004ee8a  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18004ee91  mov     rax, [rax]
0x18004ee94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee99  test    eax, eax
0x18004ee9b  js      loc_18004F3FD
0x18004eea1  mov     [rbp+260h+ppunk], r14
0x18004eea5  mov     rax, [rbx]
0x18004eea8  lea     r8, [rbp+260h+ppunk]
0x18004eeac  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18004eeb3  mov     rcx, rbx
0x18004eeb6  mov     rax, [rax]
0x18004eeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eebe  mov     edi, eax
0x18004eec0  test    eax, eax
0x18004eec2  js      loc_18004F3EA
0x18004eec8  mov     esi, dword ptr [rbp+260h+arg_20]
0x18004eece  movups  xmm0, xmmword ptr [r12]
0x18004eed3  movups  [rsp+360h+Buf2], xmm0
0x18004eed8  mov     ebx, 8007000Eh
0x18004eedd  test    r13, r13
0x18004eee0  jz      loc_18004F3C8
0x18004eee6  cmp     word ptr [r13+0], 0
0x18004eeec  jz      loc_18004F3C8
0x18004eef2  test    edi, edi
0x18004eef4  js      loc_18004F561
0x18004eefa  mov     rcx, r13; pidl
0x18004eefd  call    ILCloneFirst
0x18004ef02  mov     r14, rax
0x18004ef05  mov     [rsp+360h+var_318], rax
0x18004ef0a  test    rax, rax
0x18004ef0d  jz      loc_18004F3C4
0x18004ef13  xor     eax, eax
0x18004ef15  mov     [rbp+260h+ppsz], rax
0x18004ef19  mov     [rsp+360h+punk], rax
0x18004ef1e  mov     rbx, [rsp+360h+psf]
0x18004ef23  test    rbx, rbx
0x18004ef26  jnz     loc_18004F420
0x18004ef2c  mov     rcx, r14; Src
0x18004ef2f  call    ?ILCloneParent@@YAPEAU_ITEMIDLIST_RELATIVE@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST_RELATIVE const *)
0x18004ef34  mov     rsi, rax
0x18004ef37  test    rax, rax
0x18004ef3a  jz      loc_18004F45B
0x18004ef40  lea     rax, [rsp+360h+punk]
0x18004ef45  mov     [rsp+360h+ppv], rax; ppv
0x18004ef4a  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18004ef51  xor     r8d, r8d; pbc
0x18004ef54  mov     rdx, rsi; pidl
0x18004ef57  mov     rcx, rbx; psf
0x18004ef5a  call    SHBindToObject
0x18004ef5f  mov     edi, eax
0x18004ef61  mov     rcx, rsi; pv
0x18004ef64  call    cs:__imp_CoTaskMemFree
0x18004ef6a  mov     esi, dword ptr [rbp+260h+arg_20]
0x18004ef70  test    edi, edi
0x18004ef72  js      loc_18004F3A8
0x18004ef78  mov     rax, r14
0x18004ef7b  movzx   ecx, word ptr [r14]
0x18004ef7f  test    cx, cx
0x18004ef82  jz      loc_18004F588
0x18004ef88  nop     dword ptr [rax+rax+00000000h]
0x18004ef90  mov     rbx, rax
0x18004ef93  movzx   ecx, cx
0x18004ef96  add     rax, rcx
0x18004ef99  movzx   ecx, word ptr [rax]
0x18004ef9c  test    cx, cx
0x18004ef9f  jnz     short loc_18004EF90
0x18004efa1  xor     edx, edx; Val
0x18004efa3  mov     r8d, 110h; Size
0x18004efa9  lea     rcx, [rbp+260h+pstr]; void *
0x18004efad  call    memset_0
0x18004efb2  mov     rcx, [rsp+360h+punk]
0x18004efb7  mov     rax, [rcx]
0x18004efba  lea     r9, [rbp+260h+pstr]
0x18004efbe  mov     r8d, 8001h
0x18004efc4  mov     rdx, rbx
0x18004efc7  mov     rax, [rax+58h]
0x18004efcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efd0  mov     edi, eax
0x18004efd2  test    eax, eax
0x18004efd4  js      short loc_18004EFE9
0x18004efd6  lea     r8, [rbp+260h+ppsz]; ppsz
0x18004efda  mov     rdx, rbx; pidl
0x18004efdd  lea     rcx, [rbp+260h+pstr]; pstr
0x18004efe1  call    cs:__imp_StrRetToStrW
0x18004efe7  mov     edi, eax
0x18004efe9  mov     rcx, [rsp+360h+punk]
0x18004efee  mov     rax, [rcx]
0x18004eff1  mov     rax, [rax+10h]
0x18004eff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004effa  test    edi, edi
0x18004effc  js      loc_18004F3A8
0x18004f002  mov     rcx, [rbp+260h+arg_28]
0x18004f009  mov     rbx, rcx
0x18004f00c  mov     [rbp+260h+var_2D0], rcx
0x18004f010  test    rcx, rcx
0x18004f013  jz      short loc_18004F025
0x18004f015  mov     rax, [rcx]
0x18004f018  mov     rax, [rax+8]
0x18004f01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f021  mov     rbx, [rbp+260h+var_2D0]
0x18004f025  test    rbx, rbx
0x18004f028  jnz     loc_18004F102
0x18004f02e  mov     rbx, [rsp+360h+psf]
0x18004f033  xor     edi, edi
0x18004f035  mov     [rsp+360h+punk], rdi
0x18004f03a  xorps   xmm0, xmm0
0x18004f03d  xor     eax, eax
0x18004f03f  movups  xmmword ptr [rbp+260h+pvarg], xmm0
0x18004f043  mov     qword ptr [rbp+260h+pvarg+10h], rax
0x18004f047  mov     rax, [rbx]
0x18004f04a  lea     r9, [rbp+260h+pvarg]
0x18004f04e  lea     r8, PKEY_ParsingBindContext
0x18004f055  mov     rdx, r14
0x18004f058  mov     rcx, rbx
0x18004f05b  mov     rax, [rax+88h]
0x18004f062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f067  test    eax, eax
0x18004f069  js      loc_18004F501
0x18004f06f  mov     [rsp+360h+punk], rdi
0x18004f074  movzx   eax, word ptr [rbp+260h+pvarg]
0x18004f078  mov     ecx, 0Dh
0x18004f07d  cmp     cx, ax
0x18004f080  mov     rcx, qword ptr [rbp+260h+pvarg+8]
0x18004f084  jnz     loc_18004F590
0x18004f08a  test    rcx, rcx
0x18004f08d  jz      loc_18004F590
0x18004f093  mov     rax, [rcx]
0x18004f096  lea     r8, [rsp+360h+punk]
0x18004f09b  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x18004f0a2  mov     rax, [rax]
0x18004f0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0aa  mov     edi, eax
0x18004f0ac  lea     rcx, [rbp+260h+pvarg]; pvarg
0x18004f0b0  call    cs:__imp_VariantClear
0x18004f0b6  test    edi, edi
0x18004f0b8  js      loc_18004F37F
0x18004f0be  mov     rcx, [rsp+360h+punk]
0x18004f0c3  lea     r8, [rbp+260h+var_2D0]
0x18004f0c7  test    sil, 1
0x18004f0cb  jz      loc_18004F607
0x18004f0d1  mov     rax, [rcx]
0x18004f0d4  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x18004f0db  mov     rax, [rax]
0x18004f0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0e3  mov     edi, eax
0x18004f0e5  mov     rcx, [rsp+360h+punk]
0x18004f0ea  mov     rax, [rcx]
0x18004f0ed  mov     rax, [rax+10h]
0x18004f0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0f6  test    edi, edi
0x18004f0f8  js      loc_18004F37F
0x18004f0fe  mov     rbx, [rbp+260h+var_2D0]
0x18004f102  test    sil, 2
0x18004f106  jz      short loc_18004F125
0x18004f108  lea     rdx, aParseusesource; "ParseUseSourceItemAsDelegateItem"
0x18004f10f  mov     rcx, rbx
0x18004f112  call    BindCtx_AddObjectParam
0x18004f117  mov     edi, eax
0x18004f119  test    eax, eax
0x18004f11b  js      loc_18004F37F
0x18004f121  mov     rbx, [rbp+260h+var_2D0]
0x18004f125  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f12c  mov     ecx, 40h ; '@'; unsigned __int64
0x18004f131  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f136  mov     qword ptr [rbp+260h+pvarg], rax
0x18004f13a  test    rax, rax
0x18004f13d  jz      short loc_18004F175
0x18004f13f  mov     rcx, rax; this
0x18004f142  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x18004f147  mov     rdi, rax
0x18004f14a  test    rax, rax
0x18004f14d  jz      short loc_18004F175
0x18004f14f  mov     rdx, [rbx]
0x18004f152  mov     rax, [rdx+48h]
0x18004f156  mov     r8, rdi
0x18004f159  lea     rdx, aValidateregite; "ValidateRegItems"
0x18004f160  mov     rcx, rbx
0x18004f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f168  dec     dword ptr [rdi+18h]
0x18004f16b  cmp     dword ptr [rdi+18h], 0
0x18004f16f  jle     loc_18004F465
0x18004f175  movzx   eax, word ptr [r13+0]
0x18004f17a  test    ax, ax
0x18004f17d  jz      loc_18004F493
0x18004f183  mov     ecx, eax
0x18004f185  add     rcx, r13
0x18004f188  jz      loc_18004F493
0x18004f18e  cmp     word ptr [rcx], 0
0x18004f192  jz      loc_18004F493
0x18004f198  xor     ebx, ebx
0x18004f19a  mov     [rsp+360h+Src], rbx
0x18004f19f  mov     rcx, [rbp+260h+ppunk]
0x18004f1a3  mov     rax, [rcx]
0x18004f1a6  mov     [rsp+360h+var_330], rbx
0x18004f1ab  lea     rdx, [rsp+360h+Src]
0x18004f1b0  mov     [rsp+360h+var_338], rdx
0x18004f1b5  mov     [rsp+360h+ppv], rbx
0x18004f1ba  mov     r9, [rbp+260h+ppsz]
0x18004f1be  mov     r8, [rbp+260h+var_2D0]
0x18004f1c2  xor     edx, edx
0x18004f1c4  mov     rax, [rax+18h]
0x18004f1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1cd  mov     edi, eax
0x18004f1cf  test    eax, eax
0x18004f1d1  js      loc_18004F37F
0x18004f1d7  movzx   eax, word ptr [r13+0]
0x18004f1dc  test    ax, ax
0x18004f1df  jz      loc_18004F477
0x18004f1e5  mov     ecx, eax
0x18004f1e7  add     rcx, r13
0x18004f1ea  jz      loc_18004F477
0x18004f1f0  cmp     word ptr [rcx], 0
0x18004f1f4  jz      loc_18004F477
0x18004f1fa  mov     qword ptr [rbp+260h+pvarg], rbx
0x18004f1fe  mov     rcx, [rbp+260h+ppunk]
0x18004f202  mov     rax, [rcx]
0x18004f205  lea     rdx, [rbp+260h+pvarg]
0x18004f209  mov     [rsp+360h+ppv], rdx
0x18004f20e  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18004f215  xor     r8d, r8d
0x18004f218  mov     rdx, [rsp+360h+Src]
0x18004f21d  mov     rax, [rax+28h]
0x18004f221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f226  mov     edi, eax
0x18004f228  test    eax, eax
0x18004f22a  js      loc_18004F374
0x18004f230  mov     rdx, qword ptr [rbp+260h+pvarg]; punk
0x18004f234  lea     rcx, [rbp+260h+ppunk]; ppunk
0x18004f238  call    cs:__imp_IUnknown_Set
0x18004f23e  mov     r12, [rsp+360h+Src]
0x18004f243  mov     r15, [r15]
0x18004f246  test    r12, r12
0x18004f249  jz      loc_18004F549
0x18004f24f  test    r15, r15
0x18004f252  jz      loc_18004F576
0x18004f258  mov     rdx, r15
0x18004f25b  mov     r8d, 2
0x18004f261  movzx   ecx, word ptr [rdx]
0x18004f264  test    cx, cx
0x18004f267  jz      short loc_18004F271
0x18004f269  add     r8d, ecx
0x18004f26c  add     rdx, rcx
0x18004f26f  jnz     short loc_18004F261
0x18004f271  lea     r14d, [r8-2]
0x18004f275  mov     rdx, r12
0x18004f278  mov     edi, 2
0x18004f27d  nop     dword ptr [rax]
0x18004f280  movzx   ecx, word ptr [rdx]
0x18004f283  test    cx, cx
0x18004f286  jz      short loc_18004F28F
0x18004f288  add     edi, ecx
0x18004f28a  add     rdx, rcx
0x18004f28d  jnz     short loc_18004F280
0x18004f28f  lea     eax, [rdi+r14]
0x18004f293  mov     ebx, eax
0x18004f295  mov     ecx, eax; cb
0x18004f297  call    WINRT_IMPL_CoTaskMemAlloc
0x18004f29c  mov     rsi, rax
0x18004f29f  test    rax, rax
0x18004f2a2  jz      short loc_18004F2CE
0x18004f2a4  mov     r8d, ebx; Size
0x18004f2a7  xor     edx, edx; Val
0x18004f2a9  mov     rcx, rax; void *
0x18004f2ac  call    memset_0
0x18004f2b1  mov     r8d, r14d; Size
0x18004f2b4  mov     rdx, r15; Src
0x18004f2b7  mov     rcx, rsi; void *
0x18004f2ba  call    memcpy_0
0x18004f2bf  mov     r8d, edi; Size
0x18004f2c2  lea     rcx, [rsi+r14]; void *
0x18004f2c6  mov     rdx, r12; Src
0x18004f2c9  call    memcpy_0
0x18004f2ce  mov     rax, [rsp+360h+var_320]
0x18004f2d3  mov     [rax], rsi
0x18004f2d6  xor     ebx, ebx
0x18004f2d8  mov     edi, ebx
  ... truncated ...
```
