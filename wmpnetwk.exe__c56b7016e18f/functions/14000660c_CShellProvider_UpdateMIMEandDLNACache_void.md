# CShellProvider::UpdateMIMEandDLNACache(void)

- ea: `0x14000660c`
- end: `0x140006d67`
- name: `?UpdateMIMEandDLNACache@CShellProvider@@AEAAXXZ`
- size: `1883`
- prototype: `void __fastcall(CShellProvider *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400786b0`

## callees

- `0x14000660c`
- `0x140007020`
- `0x140007098`
- `0x140007fc4`
- `0x140008550`
- `0x140015230`
- `0x140024688`
- `0x140025e00`
- `0x140025e58`
- `0x1400396dc`
- `0x140046c32`
- `0x1400476ac`
- `0x14007b6a8`
- `0x140086790`
- `0x14009ad10`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140006b1f`
- `KERNEL32!CompareStringW` at `0x140006b8d`
- `KERNEL32!CompareStringW` at `0x140006cac`
- `KERNEL32!CompareStringW` at `0x140006b1f`
- `KERNEL32!CompareStringW` at `0x140006b8d`
- `KERNEL32!CompareStringW` at `0x140006cac`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400069e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006aa5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006be1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400069e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006aa5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006be1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400067a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400067c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140006959`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400067a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400067c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140006959`
- `ole32!PropVariantClear` at `0x14000684c`
- `ole32!PropVariantClear` at `0x140006856`
- `ole32!PropVariantClear` at `0x14000684c`
- `ole32!PropVariantClear` at `0x140006856`

## string_xrefs

- `0x1400066a5`: `SELECT System.ItemType, System.ContentType, System.Kind, System.Media.ClassSecondaryID, System.Video.EncodingBitrate, System.Video.Compression, System.DRM.IsProtected FROM SystemIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CShellProvider::UpdateMIMEandDLNACache(CShellProvider *this)
{
  CShellProvider *v1; // r12
  char *v2; // rbx
  unsigned int ContainerIndexForObjectID; // eax
  int Container; // eax
  __int64 v5; // r9
  struct IHMEMediaContainer *v6; // rdi
  unsigned __int64 i; // r14
  __int64 v8; // rcx
  struct IPropertyStore *v9; // rbx
  __int64 v10; // rdx
  char *v11; // r13
  int v12; // esi
  __int64 v13; // r14
  unsigned __int64 v14; // r13
  __int64 v15; // r8
  volatile signed __int32 *v16; // rsi
  unsigned int *v17; // rdx
  __int64 v18; // r12
  unsigned __int64 v19; // rcx
  char *v20; // r15
  unsigned int *v21; // rax
  __int64 v22; // r8
  volatile signed __int32 *v23; // rdx
  WCHAR *v24; // r14
  __int64 v25; // rsi
  int v26; // eax
  __int64 v27; // rcx
  WCHAR v28; // ax
  char *v29; // r8
  const WCHAR *lpString2; // r13
  __int64 v31; // rsi
  __int64 v32; // r15
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r15
  __int64 v36; // rax
  __int64 v37; // rdx
  char v38; // cl
  char *v39; // rax
  signed __int64 v40; // r8
  int v41; // ecx
  int v42; // edx
  __int64 j; // rax
  char v44; // cl
  __int64 v45; // r15
  __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // [rsp+40h] [rbp-49h]
  __int64 v49; // [rsp+48h] [rbp-41h] BYREF
  PCNZWCH lpString1; // [rsp+50h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v52; // [rsp+68h] [rbp-21h]
  struct IPropertyStore *v53; // [rsp+70h] [rbp-19h] BYREF
  unsigned int *v54; // [rsp+78h] [rbp-11h]
  char *v55; // [rsp+80h] [rbp-9h]
  PROPVARIANT v56[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v57; // [rsp+98h] [rbp+Fh]
  unsigned int *v59; // [rsp+F8h] [rbp+6Fh] BYREF
  WCHAR *v60; // [rsp+100h] [rbp+77h] BYREF
  struct IHMEMediaContainer *v61; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = this;
  v61 = 0;
  v2 = (char *)this + 312;
  ContainerIndexForObjectID = FindContainerIndexForObjectID(L"0");
  if ( ContainerIndexForObjectID == -1
    || (Container = CHMEMediaContainerFactory::CreateContainer(
                      (const struct SHMEContainerDefinition *)&qword_1400BDF20[8
                                                                             * (unsigned __int64)ContainerIndexForObjectID],
                      (const struct CShellCommandFactory *)(v2 + 72),
                      (struct CGeneratedContainerFactory *)v2,
                      &v61),
        Container == -2147220635) )
  {
    Container = CGeneratedContainerFactory::FindContainer((CGeneratedContainerFactory *)v2, L"0", &v61);
  }
  v6 = v61;
  if ( Container < 0 )
    goto LABEL_30;
  v49 = 0;
  LOBYTE(v5) = 1;
  if ( (*(int (__fastcall **)(struct IHMEMediaContainer *, const wchar_t *, const WCHAR *, __int64, _BYTE, __int64 *))(*(_QWORD *)v61 + 128LL))(
         v61,
         L"SELECT System.ItemType, System.ContentType, System.Kind, System.Media.ClassSecondaryID, System.Video.EncodingBi"
          "trate, System.Video.Compression, System.DRM.IsProtected FROM SystemIndex",
         &Password,
         v5,
         0,
         &v49) < 0 )
  {
    v8 = v49;
    goto LABEL_28;
  }
  for ( i = 0; ; ++i )
  {
    v48 = i;
    v8 = v49;
    if ( i >= *(_QWORD *)(v49 + 72) )
      break;
    v9 = *(struct IPropertyStore **)(*(_QWORD *)(v49 + 64) + 8 * i);
    v53 = v9;
    ((void (__fastcall *)(struct IPropertyStore *))v9->lpVtbl->AddRef)(v9);
    *(_OWORD *)v56 = 0;
    v57 = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v9->lpVtbl->GetValue)(
           v9,
           &PKEY_ItemType,
           v56) >= 0 )
    {
      LODWORD(v59) = 0;
      if ( (int)CUpnpClassMapper::GetUpnpClassForItem(v9, v10, (enum CUpnpClassMapper::CdsItemClass *)&v59) >= 0 )
      {
        v11 = (char *)v56[1] + 2;
        v55 = (char *)v56[1] + 2;
        *(_OWORD *)pvar = 0;
        v52 = 0;
        if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v9->lpVtbl->GetValue)(
               v9,
               &PKEY_ContentType,
               pvar) < 0
          || LOWORD(pvar[0]) != 31 )
        {
          goto LABEL_23;
        }
        v12 = (int)v59;
        if ( (unsigned int)((_DWORD)v59 - 5) <= 2 && (unsigned int)_o__wcsnicmp(pvar[1], L"audio", 5)
          || (unsigned int)(v12 - 1) <= 3 && (unsigned int)_o__wcsnicmp(pvar[1], L"video", 5)
          || (unsigned int)(v12 - 8) <= 1 && (unsigned int)_o__wcsnicmp(pvar[1], L"image", 5) )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
          continue;
        }
        v60 = (WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        lpString1 = (PCNZWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v20 = (char *)pvar[1];
        v21 = (unsigned int *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v17 = v21 + 6;
        v54 = v21 + 6;
        v16 = (volatile signed __int32 *)(v21 + 6);
        v59 = v21 + 6;
        v15 = 0;
        if ( !v20 )
        {
LABEL_44:
          ATL::CSimpleStringT<unsigned short,0>::Empty(&v59);
          goto LABEL_45;
        }
        if ( (unsigned __int64)v20 < 0x10000 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
            &v59,
            (unsigned __int16)v20);
LABEL_45:
          v16 = (volatile signed __int32 *)v59;
LABEL_50:
          CShellPropertyThunk::GenerateDLNAProfileID(
            (__int64)v9,
            (__int64 *)&v59,
            0,
            (__int64 *)&v60,
            (__int64 *)&lpString1);
          v23 = v16 - 6;
          if ( _InterlockedExchangeAdd(v16 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
          v24 = v60;
          if ( !*((_DWORD *)v60 - 4) )
          {
            v25 = L"*" - v60;
            v26 = *((_DWORD *)v60 - 3) - 1;
            v27 = v26 | (unsigned int)(1 - *((_DWORD *)v60 - 2));
            if ( (v26 | (1 - *((_DWORD *)v60 - 2))) < 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v60, 1);
              v24 = v60;
            }
            if ( v25 )
            {
              if ( v24 )
              {
                v28 = asc_1400A28A0[0];
                goto LABEL_58;
              }
LABEL_59:
              *(_DWORD *)_o__errno(v27, v23, v22) = 22;
              invalid_parameter_noinfo();
            }
            else
            {
              if ( !v24 )
                goto LABEL_59;
              v28 = *v24;
LABEL_58:
              *v24 = v28;
            }
            if ( *((int *)v24 - 3) < 1 )
              goto LABEL_121;
            *((_DWORD *)v24 - 4) = 1;
            v24[1] = 0;
          }
          v29 = v11;
          lpString2 = lpString1;
          ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::SetAt(
            (char *)v1 + 888,
            lpString1,
            v29);
          v31 = 0;
          v32 = *((_QWORD *)v1 + 120);
          while ( v32 != *((_QWORD *)v1 + 125) )
          {
            if ( v31 )
              goto LABEL_69;
            v33 = CompareStringW(0x7Fu, 1u, lpString2, -1, *(PCNZWCH *)v32, -1) - 1;
            if ( v33 )
            {
              if ( v33 == 2 )
                v32 = *(_QWORD *)(v32 + 32);
              else
                v31 = v32;
            }
            else
            {
              v32 = *(_QWORD *)(v32 + 24);
            }
          }
          if ( !v31 )
          {
            v31 = 0;
            goto LABEL_16;
          }
          while ( 1 )
          {
LABEL_69:
            v34 = *((_QWORD *)v1 + 125);
            v35 = *(_QWORD *)(v31 + 24);
            if ( v35 == v34 )
            {
              v36 = *(_QWORD *)(v31 + 40);
              v37 = v31;
              while ( v36 != v34 )
              {
                if ( v37 != *(_QWORD *)(v36 + 24) )
                {
                  v38 = 0;
                  goto LABEL_79;
                }
                v37 = v36;
                v36 = *(_QWORD *)(v36 + 40);
              }
              v38 = 1;
LABEL_79:
              v35 = 0;
              if ( !v38 )
                v35 = v36;
            }
            else if ( v35 )
            {
              while ( *(_QWORD *)(v35 + 32) != v34 )
                v35 = *(_QWORD *)(v35 + 32);
            }
            else
            {
              v35 = 0;
            }
            if ( !v35 || CompareStringW(0x7Fu, 1u, lpString2, -1, *(PCNZWCH *)v35, -1) != 2 )
              break;
            v31 = v35;
          }
LABEL_16:
          while ( v31 )
          {
            v45 = v31;
            v46 = *((_QWORD *)v1 + 125);
            v47 = *(_QWORD *)(v31 + 32);
            if ( v47 == v46 )
            {
              for ( j = *(_QWORD *)(v31 + 40); j != v46; j = *(_QWORD *)(j + 40) )
              {
                if ( v31 != *(_QWORD *)(j + 32) )
                {
                  v44 = 0;
                  goto LABEL_101;
                }
                v31 = j;
              }
              v44 = 1;
LABEL_101:
              v31 = 0;
              if ( !v44 )
                v31 = j;
            }
            else
            {
              v31 = *(_QWORD *)(v31 + 32);
              if ( v47 )
              {
                while ( *(_QWORD *)(v31 + 24) != v46 )
                  v31 = *(_QWORD *)(v31 + 24);
              }
            }
            if ( !v31 || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)v31, -1, lpString2, -1) != 2 )
              v31 = 0;
            if ( !v24 )
              ATL::AtlThrowImpl(-2147467259);
            v39 = *(char **)(v45 + 8);
            v40 = (char *)v24 - v39;
            do
            {
              v41 = *(unsigned __int16 *)&v39[v40];
              v42 = *(unsigned __int16 *)v39 - v41;
              if ( v42 )
                break;
              v39 += 2;
            }
            while ( v41 );
            if ( !v42 )
              goto LABEL_18;
          }
          ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RBInsert(
            (char *)v1 + 960,
            lpString2,
            v24);
LABEL_18:
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpString2 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpString2 - 3) + 8LL))(*((_QWORD *)lpString2 - 3));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v24 - 3) + 8LL))(*((_QWORD *)v24 - 3));
          i = v48;
LABEL_23:
          PropVariantClear(pvar);
          goto LABEL_24;
        }
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v20[2 * v13] );
        if ( !(_DWORD)v13 )
          goto LABEL_44;
        v14 = v21[2];
        if ( (int)((v21[3] - v13) | (1 - v21[4])) < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v59, (unsigned int)v13);
          v16 = (volatile signed __int32 *)v59;
          v17 = v54;
        }
        v18 = 2LL * (int)v13;
        if ( v18 )
        {
          v19 = (v20 - (char *)v17) >> 1;
          if ( v19 <= v14 )
          {
            if ( !v16 )
              goto LABEL_46;
            v17 = (unsigned int *)((char *)v16 + 2 * v19);
            if ( !v17 )
              goto LABEL_46;
            memmove_0((void *)v16, v17, 2LL * (int)v13);
          }
          else
          {
            if ( v16 )
            {
              memcpy_0((void *)v16, v20, 2LL * (int)v13);
              goto LABEL_47;
            }
LABEL_46:
            *(_DWORD *)_o__errno(v19, v17, v15) = 22;
            invalid_parameter_noinfo();
          }
        }
LABEL_47:
        if ( (int)v13 < 0 || (int)v13 > *((_DWORD *)v16 - 3) )
LABEL_121:
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v16 - 4) = v13;
        *(_WORD *)((char *)v16 + v18) = 0;
        v1 = this;
        v11 = v55;
        goto LABEL_50;
      }
    }
LABEL_24:
    PropVariantClear(v56);
    if ( v9 )
      ((void (__fastcall *)(struct IPropertyStore *))v9->lpVtbl->Release)(v9);
  }
  *((_DWORD *)v1 + 212) = *((_DWORD *)v1 + 211);
LABEL_28:
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_30:
  if ( v6 )
    (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v6 + 16LL))(v6);
}

```

## disassembly

```asm
0x14000660c  mov     [rsp-8+arg_0], rcx
0x140006611  push    rbp
0x140006612  push    rbx
0x140006613  push    rsi
0x140006614  push    rdi
0x140006615  push    r12
0x140006617  push    r13
0x140006619  push    r14
0x14000661b  push    r15
0x14000661d  lea     rbp, [rsp-1Fh]
0x140006622  sub     rsp, 0A8h
0x140006629  mov     r12, rcx
0x14000662c  xor     r15d, r15d
0x14000662f  mov     [rbp+57h+arg_18], r15
0x140006633  lea     rbx, [rcx+138h]
0x14000663a  lea     rcx, a0; "0"
0x140006641  call    ?FindContainerIndexForObjectID@@YAKPEBG@Z; FindContainerIndexForObjectID(ushort const *)
0x140006646  cmp     eax, 0FFFFFFFFh
0x140006649  jz      loc_140006D00
0x14000664f  lea     rdx, [rbx+48h]; struct CShellCommandFactory *
0x140006653  mov     ecx, eax
0x140006655  shl     rcx, 6
0x140006659  lea     rax, qword_1400BDF20
0x140006660  add     rcx, rax; struct SHMEContainerDefinition *
0x140006663  lea     r9, [rbp+57h+arg_18]; struct IHMEMediaContainer **
0x140006667  mov     r8, rbx; struct CGeneratedContainerFactory *
0x14000666a  call    ?CreateContainer@CHMEMediaContainerFactory@@SAJPEBUSHMEContainerDefinition@@PEBVCShellCommandFactory@@PEAVCGeneratedContainerFactory@@PEAPEAUIHMEMediaContainer@@@Z; CHMEMediaContainerFactory::CreateContainer(SHMEContainerDefinition const *,CShellCommandFactory const *,CGeneratedContainerFactory *,IHMEMediaContainer * *)
0x14000666f  cmp     eax, 80040365h
0x140006674  jz      loc_140006D00
0x14000667a  mov     rdi, [rbp+57h+arg_18]
0x14000667e  test    eax, eax
0x140006680  js      loc_14000689C
0x140006686  mov     [rbp+57h+var_98], r15
0x14000668a  mov     rax, [rdi]
0x14000668d  lea     rcx, [rbp+57h+var_98]
0x140006691  mov     qword ptr [rsp+0E0h+cchCount2], rcx
0x140006696  mov     byte ptr [rsp+0E0h+lpString2], r15b
0x14000669b  mov     r9b, 1
0x14000669e  lea     r8, Password
0x1400066a5  lea     rdx, aSelectSystemIt_0; "SELECT System.ItemType, System.ContentT"...
0x1400066ac  mov     rcx, rdi
0x1400066af  mov     rax, [rax+80h]
0x1400066b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066bb  test    eax, eax
0x1400066bd  js      loc_140006D5D
0x1400066c3  mov     r14, r15
0x1400066c6  mov     [rbp+57h+var_A0], r14
0x1400066ca  mov     rcx, [rbp+57h+var_98]
0x1400066ce  cmp     r14, [rcx+48h]
0x1400066d2  jnb     loc_14000687A
0x1400066d8  mov     rbx, [rcx+40h]
0x1400066dc  mov     rbx, [rbx+r14*8]
0x1400066e0  mov     [rbp+57h+var_70], rbx
0x1400066e4  mov     rax, [rbx]
0x1400066e7  mov     rcx, rbx
0x1400066ea  mov     rax, [rax+8]
0x1400066ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066f3  xorps   xmm0, xmm0
0x1400066f6  xor     eax, eax
0x1400066f8  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1400066fc  mov     [rbp+57h+var_48], rax
0x140006700  mov     rax, [rbx]
0x140006703  lea     r8, [rbp+57h+var_58]
0x140006707  lea     rdx, PKEY_ItemType
0x14000670e  mov     rcx, rbx
0x140006711  mov     rax, [rax+28h]
0x140006715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000671a  test    eax, eax
0x14000671c  js      loc_140006852
0x140006722  mov     dword ptr [rbp+57h+arg_8], r15d
0x140006726  lea     r8, [rbp+57h+arg_8]; enum CUpnpClassMapper::CdsItemClass *
0x14000672a  mov     rcx, rbx; struct IPropertyStore *
0x14000672d  call    ?GetUpnpClassForItem@CUpnpClassMapper@@SAJPEAUIPropertyStore@@_NPEAW4CdsItemClass@1@@Z; CUpnpClassMapper::GetUpnpClassForItem(IPropertyStore *,bool,CUpnpClassMapper::CdsItemClass *)
0x140006732  test    eax, eax
0x140006734  js      loc_140006852
0x14000673a  mov     r13, [rbp+57h+var_58+8]
0x14000673e  add     r13, 2
0x140006742  mov     [rbp+57h+var_60], r13
0x140006746  xorps   xmm0, xmm0
0x140006749  xor     eax, eax
0x14000674b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x14000674f  mov     [rbp+57h+var_78], rax
0x140006753  mov     rax, [rbx]
0x140006756  lea     r8, [rbp+57h+pvar]
0x14000675a  lea     rdx, PKEY_ContentType
0x140006761  mov     rcx, rbx
0x140006764  mov     rax, [rax+28h]
0x140006768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000676d  test    eax, eax
0x14000676f  js      loc_140006848
0x140006775  mov     eax, 1Fh
0x14000677a  cmp     ax, word ptr [rbp+57h+pvar]
0x14000677e  jnz     loc_140006848
0x140006784  mov     esi, dword ptr [rbp+57h+arg_8]
0x140006787  lea     eax, [rsi-5]
0x14000678a  cmp     eax, 2
0x14000678d  ja      short loc_1400067AA
0x14000678f  mov     r8d, 5
0x140006795  lea     rdx, aAudio_1; "audio"
0x14000679c  mov     rcx, [rbp+57h+pvar+8]
0x1400067a0  call    cs:__imp__o__wcsnicmp
0x1400067a6  test    eax, eax
0x1400067a8  jnz     short loc_1400067D5
0x1400067aa  lea     eax, [rsi-1]
0x1400067ad  cmp     eax, 3
0x1400067b0  ja      loc_140006940
0x1400067b6  mov     r8d, 5
0x1400067bc  lea     rdx, aVideo_0; "video"
0x1400067c3  mov     rcx, [rbp+57h+pvar+8]
0x1400067c7  call    cs:__imp__o__wcsnicmp
0x1400067cd  test    eax, eax
0x1400067cf  jz      loc_140006940
0x1400067d5  lea     rcx, [rbp+57h+var_70]
0x1400067d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400067de  jmp     loc_140006872
0x1400067e3  xor     r15d, r15d
0x1400067e6  test    rsi, rsi
0x1400067e9  jnz     loc_140006CD6
0x1400067ef  mov     r8, r14
0x1400067f2  mov     rdx, r13
0x1400067f5  lea     rcx, [r12+3C0h]
0x1400067fd  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@IEAAPEAVCNode@12@PEBG0@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RBInsert(ushort const *,ushort const *)
0x140006802  nop
0x140006803  lea     rdx, [r13-18h]
0x140006807  or      eax, 0FFFFFFFFh
0x14000680a  lock xadd [rdx+10h], eax
0x14000680f  sub     eax, 1
0x140006812  jg      short loc_140006824
0x140006814  mov     rcx, [rdx]
0x140006817  mov     rax, [rcx]
0x14000681a  mov     rax, [rax+8]
0x14000681e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006823  nop
0x140006824  lea     rdx, [r14-18h]
0x140006828  or      eax, 0FFFFFFFFh
0x14000682b  lock xadd [rdx+10h], eax
0x140006830  sub     eax, 1
0x140006833  jg      short loc_140006844
0x140006835  mov     rcx, [rdx]
0x140006838  mov     rax, [rcx]
0x14000683b  mov     rax, [rax+8]
0x14000683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006844  mov     r14, [rbp+57h+var_A0]
0x140006848  lea     rcx, [rbp+57h+pvar]; pvar
0x14000684c  call    cs:__imp_PropVariantClear
0x140006852  lea     rcx, [rbp+57h+var_58]; pvar
0x140006856  call    cs:__imp_PropVariantClear
0x14000685c  nop
0x14000685d  test    rbx, rbx
0x140006860  jz      short loc_140006872
0x140006862  mov     rax, [rbx]
0x140006865  mov     rcx, rbx
0x140006868  mov     rax, [rax+10h]
0x14000686c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006871  nop
0x140006872  inc     r14
0x140006875  jmp     loc_1400066C6
0x14000687a  mov     eax, [r12+34Ch]
0x140006882  mov     [r12+350h], eax
0x14000688a  test    rcx, rcx
0x14000688d  jz      short loc_14000689C
0x14000688f  mov     rax, [rcx]
0x140006892  mov     rax, [rax+10h]
0x140006896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000689b  nop
0x14000689c  test    rdi, rdi
0x14000689f  jz      short loc_1400068B1
0x1400068a1  mov     rax, [rdi]
0x1400068a4  mov     rcx, rdi
0x1400068a7  mov     rax, [rax+10h]
0x1400068ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068b0  nop
0x1400068b1  add     rsp, 0A8h
0x1400068b8  pop     r15
0x1400068ba  pop     r14
0x1400068bc  pop     r13
0x1400068be  pop     r12
0x1400068c0  pop     rdi
0x1400068c1  pop     rsi
0x1400068c2  pop     rbx
0x1400068c3  pop     rbp
0x1400068c4  retn
0x1400068c5  inc     r14
0x1400068c8  cmp     [r15+r14*2], r8w
0x1400068cd  jnz     short loc_1400068C5
0x1400068cf  test    r14d, r14d
0x1400068d2  jz      loc_1400069D6
0x1400068d8  mov     r13d, [rdx-10h]
0x1400068dc  mov     ecx, 1
0x1400068e1  sub     ecx, [rax+10h]
0x1400068e4  mov     eax, [rax+0Ch]
0x1400068e7  sub     eax, r14d
0x1400068ea  or      ecx, eax
0x1400068ec  jge     short loc_140006902
0x1400068ee  mov     edx, r14d
0x1400068f1  lea     rcx, [rbp+57h+arg_8]
0x1400068f5  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400068fa  mov     rsi, [rbp+57h+arg_8]
0x1400068fe  mov     rdx, [rbp+57h+var_68]
0x140006902  movsxd  rax, r14d
0x140006905  lea     r12, [rax+rax]
0x140006909  test    r12, r12
0x14000690c  jz      loc_1400069F9
0x140006912  mov     rcx, r15
0x140006915  sub     rcx, rdx
0x140006918  sar     rcx, 1
0x14000691b  cmp     rcx, r13
0x14000691e  jbe     loc_140006BD9
0x140006924  test    rsi, rsi
0x140006927  jz      loc_1400069E8
0x14000692d  mov     r8, r12; Size
0x140006930  mov     rdx, r15; Src
0x140006933  mov     rcx, rsi; void *
0x140006936  call    memcpy_0
0x14000693b  jmp     loc_1400069F9
0x140006940  lea     eax, [rsi-8]
0x140006943  cmp     eax, 1
0x140006946  ja      short loc_140006967
0x140006948  mov     r8d, 5
0x14000694e  lea     rdx, String2; "image"
0x140006955  mov     rcx, [rbp+57h+pvar+8]
0x140006959  call    cs:__imp__o__wcsnicmp
0x14000695f  test    eax, eax
0x140006961  jnz     loc_1400067D5
0x140006967  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000696e  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006975  mov     rcx, rsi
0x140006978  mov     rax, [rax+18h]
0x14000697c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006981  add     rax, 18h
0x140006985  mov     [rbp+57h+arg_10], rax
0x140006989  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006990  mov     rcx, rsi
0x140006993  mov     rax, [rax+18h]
0x140006997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000699c  add     rax, 18h
0x1400069a0  mov     [rbp+57h+lpString1], rax
0x1400069a4  mov     r15, [rbp+57h+pvar+8]
0x1400069a8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400069af  mov     rcx, rsi
0x1400069b2  mov     rax, [rax+18h]
0x1400069b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069bb  lea     rdx, [rax+18h]
0x1400069bf  mov     [rbp+57h+var_68], rdx
0x1400069c3  mov     rsi, rdx
0x1400069c6  mov     [rbp+57h+arg_8], rdx
0x1400069ca  xor     r8d, r8d
0x1400069cd  test    r15, r15
0x1400069d0  jnz     loc_140006D18
0x1400069d6  lea     rcx, [rbp+57h+arg_8]
0x1400069da  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400069df  xor     r15d, r15d
0x1400069e2  mov     rsi, [rbp+57h+arg_8]
0x1400069e6  jmp     short loc_140006A20
0x1400069e8  call    cs:__imp__o__errno
0x1400069ee  mov     dword ptr [rax], 16h
0x1400069f4  call    _invalid_parameter_noinfo
0x1400069f9  xor     r15d, r15d
0x1400069fc  test    r14d, r14d
0x1400069ff  js      loc_140006D52
0x140006a05  cmp     r14d, [rsi-0Ch]
0x140006a09  jg      loc_140006D52
0x140006a0f  mov     [rsi-10h], r14d
0x140006a13  mov     [r12+rsi], r15w
0x140006a18  mov     r12, [rbp+57h+arg_0]
0x140006a1c  mov     r13, [rbp+57h+var_60]
0x140006a20  lea     rax, [rbp+57h+lpString1]
0x140006a24  mov     [rsp+0E0h+lpString2], rax
0x140006a29  lea     r9, [rbp+57h+arg_10]
0x140006a2d  xor     r8d, r8d
0x140006a30  lea     rdx, [rbp+57h+arg_8]
0x140006a34  mov     rcx, rbx
0x140006a37  call    ?GenerateDLNAProfileID@CShellPropertyThunk@@SAXPEAUIPropertyStore@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KAEAV34@2@Z; CShellPropertyThunk::GenerateDLNAProfileID(IPropertyStore *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140006a3c  nop
0x140006a3d  lea     rdx, [rsi-18h]
0x140006a41  or      eax, 0FFFFFFFFh
0x140006a44  lock xadd [rdx+10h], eax
0x140006a49  sub     eax, 1
0x140006a4c  jg      short loc_140006A5D
0x140006a4e  mov     rcx, [rdx]
0x140006a51  mov     rax, [rcx]
0x140006a54  mov     rax, [rax+8]
0x140006a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a5d  mov     r14, [rbp+57h+arg_10]
0x140006a61  cmp     [r14-10h], r15d
0x140006a65  jnz     short loc_140006ACE
0x140006a67  lea     rsi, asc_1400A28A0; "*"
0x140006a6e  sub     rsi, r14
0x140006a71  sar     rsi, 1
0x140006a74  mov     ecx, 1
0x140006a79  sub     ecx, [r14-8]
0x140006a7d  mov     eax, [r14-0Ch]
0x140006a81  dec     eax
0x140006a83  or      ecx, eax
0x140006a85  jl      loc_140006C2E
0x140006a8b  test    rsi, rsi
0x140006a8e  jz      loc_140006C10
0x140006a94  test    r14, r14
0x140006a97  jz      short loc_140006AA5
0x140006a99  mov     eax, dword ptr cs:asc_1400A28A0; "*"
  ... truncated ...
```
