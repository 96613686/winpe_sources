# CDistinctHMEMediaContainer::CreateSubcontainers(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> const &,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140083e00`
- end: `0x1400842e9`
- name: `?CreateSubcontainers@CDistinctHMEMediaContainer@@IEAAJAEBV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@3@@Z`
- size: `1257`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400850a0`

## callees

- `0x140006d70`
- `0x140009364`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c920`
- `0x140018df0`
- `0x140022d30`
- `0x140023bdc`
- `0x140024688`
- `0x14002c410`
- `0x14002c4a0`
- `0x14003d898`
- `0x14003ddb0`
- `0x1400406f4`
- `0x140045f20`
- `0x140061f34`
- `0x140081fcc`
- `0x140082048`
- `0x14008328c`
- `0x140083e00`
- `0x140087438`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1400842ad`
- `ole32!PropVariantClear` at `0x1400842ad`
- `ole32!CoTaskMemFree` at `0x140084279`
- `ole32!CoTaskMemFree` at `0x140084283`
- `ole32!CoTaskMemFree` at `0x140084279`
- `ole32!CoTaskMemFree` at `0x140084283`
- `PROPSYS!PropVariantToStringAlloc` at `0x14008400e`
- `PROPSYS!PropVariantToStringAlloc` at `0x14008400e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDistinctHMEMediaContainer::CreateSubcontainers(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  HRESULT StackContainer; // ebx
  unsigned __int64 i; // r9
  char *v7; // rcx
  char *v8; // r8
  int v9; // edx
  int v10; // eax
  unsigned __int64 j; // r12
  __int64 **v12; // rax
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int128 *v15; // rdx
  __int64 v16; // r14
  __int64 v17; // rsi
  int v18; // edi
  int v19; // ebx
  char *v20; // rax
  __int128 *v21; // rax
  unsigned int v22; // eax
  char *HMEUnknownString; // rax
  const unsigned __int16 *v24; // rbx
  struct IPropertyStore **v25; // rax
  unsigned __int16 *v26; // rbx
  __int64 v27; // r8
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // r14
  __int64 v31; // rsi
  int v32; // edi
  int v33; // ebx
  char *v34; // rax
  unsigned __int16 *v36; // [rsp+50h] [rbp-89h] BYREF
  __int64 v37; // [rsp+58h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-79h] BYREF
  __int64 v39; // [rsp+68h] [rbp-71h] BYREF
  __int64 v40; // [rsp+70h] [rbp-69h] BYREF
  wchar_t **v41; // [rsp+78h] [rbp-61h]
  PWSTR ppszOut; // [rsp+80h] [rbp-59h] BYREF
  void *v43; // [rsp+88h] [rbp-51h] BYREF
  void *v44; // [rsp+90h] [rbp-49h] BYREF
  __int64 v45; // [rsp+98h] [rbp-41h] BYREF
  void *v46; // [rsp+A0h] [rbp-39h] BYREF
  void *v47; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD *v50; // [rsp+C0h] [rbp-19h]
  PROPVARIANT propvar[2]; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-1h]
  __int128 v53; // [rsp+E0h] [rbp+7h] BYREF
  int v54; // [rsp+F0h] [rbp+17h]

  v50 = a3;
  StackContainer = 0;
  v41 = 0;
  for ( i = 0; i < 4; ++i )
  {
    v7 = *(char **)(a1[2] + 40LL);
    v8 = (char *)((char *)off_1400BEE20[4 * i] - v7);
    do
    {
      v9 = *(unsigned __int16 *)&v8[(_QWORD)v7];
      v10 = *(unsigned __int16 *)v7 - v9;
      if ( v10 )
        break;
      v7 += 2;
    }
    while ( v9 );
    if ( !v10 )
    {
      v41 = &off_1400BEE20[4 * i];
      break;
    }
  }
  for ( j = 0; j < a2[1]; ++j )
  {
    if ( StackContainer < 0 )
      break;
    *(_OWORD *)propvar = 0;
    v52 = 0;
    v12 = (__int64 **)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                        a2,
                        j);
    v13 = *v12;
    v14 = **v12;
    v15 = *(__int128 **)(a1[2] + 48LL);
    v53 = *v15;
    v54 = *((_DWORD *)v15 + 4);
    StackContainer = (*(__int64 (__fastcall **)(__int64 *, __int128 *, PROPVARIANT *))(v14 + 40))(v13, &v53, propvar);
    if ( StackContainer >= 0 )
    {
      v39 = 0;
      if ( LOWORD(propvar[0]) == 1 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v40);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
          &v40,
          L"%s IS NULL",
          *(_QWORD *)(a1[2] + 40LL));
        v16 = a1[4];
        v17 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
        v18 = *(_DWORD *)(a1[2] + 32LL);
        v19 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
        v20 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v44,
          v20);
        v21 = *(__int128 **)(a1[2] + 48LL);
        v53 = *v21;
        v54 = *((_DWORD *)v21 + 4);
        v22 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
        HMEUnknownString = (char *)CHMEUnknownStringUtil::GetHMEUnknownString(v22, &v53);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v43,
          HMEUnknownString);
        StackContainer = CGeneratedContainerFactory::CreateStackContainer(
                           v16,
                           (unsigned int)&v43,
                           (unsigned int)&v44,
                           v19,
                           v18,
                           v17,
                           (__int64)&v40,
                           (__int64)v41,
                           (__int64)&v39);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v43);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v44);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v40);
      }
      else
      {
        ppszOut = 0;
        StackContainer = PropVariantToStringAlloc(propvar, &ppszOut);
        if ( StackContainer >= 0 )
        {
          pv = 0;
          v24 = *(const unsigned __int16 **)(a1[2] + 40LL);
          v25 = (struct IPropertyStore **)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                                            a2,
                                            j);
          StackContainer = GetDistinctValueFromItem(*v25, v24, (unsigned __int16 **)&pv);
          if ( StackContainer >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v37);
            if ( CShellPropertyThunk::IsPropertyNumeric(*(const unsigned __int16 **)(a1[2] + 40LL)) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                &v37,
                L"%s = %s",
                *(_QWORD *)(a1[2] + 40LL),
                pv);
            }
            else
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                (void **)&v36,
                (char *)pv);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                &v36,
                L"'",
                L"''");
              if ( CShellPropertyThunk::IsPropertyMultiValued(*(const unsigned __int16 **)(a1[2] + 40LL)) )
              {
                v26 = v36;
                if ( ContainsInvalidContainsCharacters(v36) )
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                    &v37,
                    L"%s LIKE '%%%s%%'",
                    *(_QWORD *)(a1[2] + 40LL),
                    v26);
                }
                else
                {
                  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                       &v36,
                                       32,
                                       0) != -1
                    || (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                       &v36,
                                       44,
                                       v27) != -1 )
                  {
                    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                      &v36,
                      L"\"",
                      L"\"\"");
                    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                      &v45,
                      "\"");
                    v28 = ATL::operator+(&v49, L"\"", &v36);
                    v29 = (_QWORD *)ATL::operator+(&v48, v28, &v45);
                    ATL::CSimpleStringT<unsigned short,0>::operator=(&v36, v29);
                    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v48);
                    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v49);
                    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v45);
                    v26 = v36;
                  }
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                    &v37,
                    L"CONTAINS(%s, '%s')",
                    *(_QWORD *)(a1[2] + 40LL),
                    v26);
                }
              }
              else
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                  &v37,
                  L"%s = '%s'",
                  *(_QWORD *)(a1[2] + 40LL),
                  v36);
              }
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v36);
            }
            v30 = a1[4];
            v31 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
            v32 = *(_DWORD *)(a1[2] + 32LL);
            v33 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
            v34 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v47,
              v34);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v46,
              (char *)ppszOut);
            StackContainer = CGeneratedContainerFactory::CreateStackContainer(
                               v30,
                               (unsigned int)&v46,
                               (unsigned int)&v47,
                               v33,
                               v32,
                               v31,
                               (__int64)&v37,
                               (__int64)v41,
                               (__int64)&v39);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v46);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v47);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v37);
          }
          CoTaskMemFree(pv);
        }
        CoTaskMemFree(ppszOut);
      }
      if ( StackContainer >= 0 )
        ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
          v50,
          v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    }
    PropVariantClear(propvar);
  }
  return (unsigned int)StackContainer;
}

```

## disassembly

```asm
0x140083e00  mov     [rsp-8+arg_18], rbx
0x140083e05  push    rbp
0x140083e06  push    rsi
0x140083e07  push    rdi
0x140083e08  push    r12
0x140083e0a  push    r13
0x140083e0c  push    r14
0x140083e0e  push    r15
0x140083e10  lea     rbp, [rsp-27h]
0x140083e15  sub     rsp, 100h
0x140083e1c  mov     rax, cs:__security_cookie
0x140083e23  xor     rax, rsp
0x140083e26  mov     [rbp+57h+var_38], rax
0x140083e2a  mov     [rbp+57h+var_70], r8
0x140083e2e  mov     r13, rdx
0x140083e31  mov     r15, rcx
0x140083e34  xor     ebx, ebx
0x140083e36  mov     [rbp+57h+var_B8], rbx
0x140083e3a  xor     r9d, r9d
0x140083e3d  lea     edi, [rbx+1]
0x140083e40  cmp     r9, 4
0x140083e44  jnb     short loc_140083E86
0x140083e46  mov     r10, r9
0x140083e49  shl     r10, 5
0x140083e4d  lea     rcx, off_1400BEE20; "System.Music.Artist"
0x140083e54  add     r10, rcx
0x140083e57  mov     rax, [r15+10h]
0x140083e5b  mov     rcx, [rax+28h]
0x140083e5f  mov     r8, [r10]
0x140083e62  sub     r8, rcx
0x140083e65  movzx   eax, word ptr [rcx]
0x140083e68  movzx   edx, word ptr [rcx+r8]
0x140083e6d  sub     eax, edx
0x140083e6f  jnz     short loc_140083E79
0x140083e71  add     rcx, 2
0x140083e75  test    edx, edx
0x140083e77  jnz     short loc_140083E65
0x140083e79  test    eax, eax
0x140083e7b  jz      short loc_140083E82
0x140083e7d  add     r9, rdi
0x140083e80  jmp     short loc_140083E40
0x140083e82  mov     [rbp+57h+var_B8], r10
0x140083e86  xor     r12d, r12d
0x140083e89  cmp     [r13+8], rbx
0x140083e8d  jbe     loc_1400842C0
0x140083e93  test    ebx, ebx
0x140083e95  js      loc_1400842C0
0x140083e9b  xorps   xmm0, xmm0
0x140083e9e  xor     eax, eax
0x140083ea0  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x140083ea4  mov     [rbp+57h+var_58], rax
0x140083ea8  mov     rdx, r12
0x140083eab  mov     rcx, r13
0x140083eae  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140083eb3  mov     rcx, [rax]
0x140083eb6  mov     rax, [rcx]
0x140083eb9  mov     rdx, [r15+10h]
0x140083ebd  mov     rdx, [rdx+30h]
0x140083ec1  movups  xmm0, xmmword ptr [rdx]
0x140083ec4  movups  [rbp+57h+var_50], xmm0
0x140083ec8  mov     edx, [rdx+10h]
0x140083ecb  mov     [rbp+57h+var_40], edx
0x140083ece  lea     r8, [rbp+57h+propvar]
0x140083ed2  lea     rdx, [rbp+57h+var_50]
0x140083ed6  mov     rax, [rax+28h]
0x140083eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083edf  mov     ebx, eax
0x140083ee1  test    eax, eax
0x140083ee3  js      loc_1400842A9
0x140083ee9  mov     [rbp+57h+var_C8], 0
0x140083ef1  cmp     di, word ptr [rbp+57h+propvar]
0x140083ef5  jnz     loc_140083FFE
0x140083efb  lea     rcx, [rbp+57h+var_C0]
0x140083eff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140083f04  nop
0x140083f05  mov     r8, [r15+10h]
0x140083f09  mov     r8, [r8+28h]
0x140083f0d  lea     rdx, aSIsNull; "%s IS NULL"
0x140083f14  lea     rcx, [rbp+57h+var_C0]
0x140083f18  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140083f1d  mov     r14, [r15+20h]
0x140083f21  mov     rax, [r15]
0x140083f24  mov     rcx, r15
0x140083f27  mov     rax, [rax+60h]
0x140083f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083f30  mov     rsi, rax
0x140083f33  mov     rcx, [r15+10h]
0x140083f37  mov     edi, [rcx+20h]
0x140083f3a  mov     rcx, [r15]
0x140083f3d  mov     rax, [rcx+50h]
0x140083f41  mov     rcx, r15
0x140083f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083f49  mov     ebx, eax
0x140083f4b  mov     rcx, [r15]
0x140083f4e  mov     rax, [rcx+38h]
0x140083f52  mov     rcx, r15
0x140083f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083f5a  mov     rdx, rax
0x140083f5d  lea     rcx, [rbp+57h+var_A0]
0x140083f61  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140083f66  nop
0x140083f67  mov     rcx, [r15+10h]
0x140083f6b  mov     rax, [rcx+30h]
0x140083f6f  movups  xmm0, xmmword ptr [rax]
0x140083f72  movups  [rbp+57h+var_50], xmm0
0x140083f76  mov     eax, [rax+10h]
0x140083f79  mov     [rbp+57h+var_40], eax
0x140083f7c  mov     rax, [r15]
0x140083f7f  mov     rcx, r15
0x140083f82  mov     rax, [rax+50h]
0x140083f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083f8b  lea     rdx, [rbp+57h+var_50]
0x140083f8f  mov     ecx, eax
0x140083f91  call    ?GetHMEUnknownString@CHMEUnknownStringUtil@@SAPEBGW4MediaCacheSchema@@AEBU_tagpropertykey@@@Z; CHMEUnknownStringUtil::GetHMEUnknownString(MediaCacheSchema,_tagpropertykey const &)
0x140083f96  mov     rdx, rax
0x140083f99  lea     rcx, [rbp+57h+var_A8]
0x140083f9d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140083fa2  nop
0x140083fa3  lea     rax, [rbp+57h+var_C8]
0x140083fa7  mov     [rsp+130h+var_F0], rax
0x140083fac  mov     rax, [rbp+57h+var_B8]
0x140083fb0  mov     [rsp+130h+var_F8], rax
0x140083fb5  lea     rax, [rbp+57h+var_C0]
0x140083fb9  mov     [rsp+130h+var_100], rax
0x140083fbe  mov     [rsp+130h+var_108], rsi
0x140083fc3  mov     [rsp+130h+var_110], edi
0x140083fc7  mov     r9d, ebx
0x140083fca  lea     r8, [rbp+57h+var_A0]
0x140083fce  lea     rdx, [rbp+57h+var_A8]
0x140083fd2  mov     rcx, r14
0x140083fd5  call    ?CreateStackContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEBUSHMEDistinctSubcontainerDefinition@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateStackContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,SHMEDistinctSubcontainerDefinition const *,IHMEMediaContainer * *)
0x140083fda  mov     ebx, eax
0x140083fdc  lea     rcx, [rbp+57h+var_A8]
0x140083fe0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083fe5  nop
0x140083fe6  lea     rcx, [rbp+57h+var_A0]
0x140083fea  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083fef  nop
0x140083ff0  lea     rcx, [rbp+57h+var_C0]
0x140083ff4  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083ff9  jmp     loc_140084289
0x140083ffe  mov     [rbp+57h+ppszOut], 0
0x140084006  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x14008400a  lea     rcx, [rbp+57h+propvar]; propvar
0x14008400e  call    cs:__imp_PropVariantToStringAlloc
0x140084014  mov     ebx, eax
0x140084016  test    eax, eax
0x140084018  js      loc_14008427F
0x14008401e  mov     [rbp+57h+pv], 0
0x140084026  mov     rax, [r15+10h]
0x14008402a  mov     rbx, [rax+28h]
0x14008402e  mov     rdx, r12
0x140084031  mov     rcx, r13
0x140084034  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140084039  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x14008403d  mov     rdx, rbx; unsigned __int16 *
0x140084040  mov     rcx, [rax]; struct IPropertyStore *
0x140084043  call    ?GetDistinctValueFromItem@@YAJPEAUIPropertyStore@@PEBGPEAPEAG@Z; GetDistinctValueFromItem(IPropertyStore *,ushort const *,ushort * *)
0x140084048  mov     ebx, eax
0x14008404a  test    eax, eax
0x14008404c  js      loc_140084275
0x140084052  lea     rcx, [rsp+130h+var_D8]
0x140084057  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14008405c  nop
0x14008405d  mov     rcx, [r15+10h]
0x140084061  mov     rcx, [rcx+28h]; unsigned __int16 *
0x140084065  call    ?IsPropertyNumeric@CShellPropertyThunk@@SA_NPEBG@Z; CShellPropertyThunk::IsPropertyNumeric(ushort const *)
0x14008406a  test    al, al
0x14008406c  jnz     loc_1400841A8
0x140084072  mov     rdx, [rbp+57h+pv]
0x140084076  lea     rcx, [rsp+130h+var_E0]
0x14008407b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084080  nop
0x140084081  lea     r8, asc_1400A5BFC; "''"
0x140084088  lea     rdx, asc_1400A5BF8; "'"
0x14008408f  lea     rcx, [rsp+130h+var_E0]
0x140084094  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort const *,ushort const *)
0x140084099  mov     rcx, [r15+10h]
0x14008409d  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1400840a1  call    ?IsPropertyMultiValued@CShellPropertyThunk@@SA_NPEBG@Z; CShellPropertyThunk::IsPropertyMultiValued(ushort const *)
0x1400840a6  test    al, al
0x1400840a8  jz      loc_14008417D
0x1400840ae  mov     rbx, [rsp+130h+var_E0]
0x1400840b3  mov     rcx, rbx; unsigned __int16 *
0x1400840b6  call    ?ContainsInvalidContainsCharacters@@YA_NPEBG@Z; ContainsInvalidContainsCharacters(ushort const *)
0x1400840bb  test    al, al
0x1400840bd  jz      short loc_1400840CE
0x1400840bf  mov     r9, rbx
0x1400840c2  lea     rdx, aSLikeS; "%s LIKE '%%%s%%'"
0x1400840c9  jmp     loc_140084189
0x1400840ce  mov     edx, 20h ; ' '
0x1400840d3  xor     r8d, r8d
0x1400840d6  lea     rcx, [rsp+130h+var_E0]
0x1400840db  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Find(ushort,int)
0x1400840e0  cmp     eax, 0FFFFFFFFh
0x1400840e3  jnz     short loc_1400840F7
0x1400840e5  lea     edx, [rax+2Dh]
0x1400840e8  lea     rcx, [rsp+130h+var_E0]
0x1400840ed  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Find(ushort,int)
0x1400840f2  cmp     eax, 0FFFFFFFFh
0x1400840f5  jz      short loc_140084171
0x1400840f7  lea     r8, asc_1400AAB3C; "\"\""
0x1400840fe  lea     rdx, asc_1400A3A6C; "\""
0x140084105  lea     rcx, [rsp+130h+var_E0]
0x14008410a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort const *,ushort const *)
0x14008410f  lea     rdx, asc_1400AE1AC; "\""
0x140084116  lea     rcx, [rbp+57h+var_98]
0x14008411a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14008411f  lea     r8, [rsp+130h+var_E0]
0x140084124  lea     rdx, asc_1400A3A6C; "\""
0x14008412b  lea     rcx, [rbp+57h+var_78]
0x14008412f  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140084134  lea     r8, [rbp+57h+var_98]
0x140084138  mov     rdx, rax
0x14008413b  lea     rcx, [rbp+57h+var_80]
0x14008413f  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140084144  mov     rdx, rax
0x140084147  lea     rcx, [rsp+130h+var_E0]
0x14008414c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140084151  lea     rcx, [rbp+57h+var_80]
0x140084155  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008415a  lea     rcx, [rbp+57h+var_78]
0x14008415e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084163  lea     rcx, [rbp+57h+var_98]
0x140084167  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008416c  mov     rbx, [rsp+130h+var_E0]
0x140084171  mov     r9, rbx
0x140084174  lea     rdx, aContainsSS; "CONTAINS(%s, '%s')"
0x14008417b  jmp     short loc_140084189
0x14008417d  mov     r9, [rsp+130h+var_E0]
0x140084182  lea     rdx, aSS_0; "%s = '%s'"
0x140084189  mov     r8, [r15+10h]
0x14008418d  mov     r8, [r8+28h]
0x140084191  lea     rcx, [rsp+130h+var_D8]
0x140084196  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14008419b  nop
0x14008419c  lea     rcx, [rsp+130h+var_E0]
0x1400841a1  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400841a6  jmp     short loc_1400841C5
0x1400841a8  mov     r8, [r15+10h]
0x1400841ac  mov     r9, [rbp+57h+pv]
0x1400841b0  mov     r8, [r8+28h]
0x1400841b4  lea     rdx, aSS; "%s = %s"
0x1400841bb  lea     rcx, [rsp+130h+var_D8]
0x1400841c0  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x1400841c5  mov     r14, [r15+20h]
0x1400841c9  mov     rax, [r15]
0x1400841cc  mov     rcx, r15
0x1400841cf  mov     rax, [rax+60h]
0x1400841d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400841d8  mov     rsi, rax
0x1400841db  mov     rcx, [r15+10h]
0x1400841df  mov     edi, [rcx+20h]
0x1400841e2  mov     rcx, [r15]
0x1400841e5  mov     rax, [rcx+50h]
0x1400841e9  mov     rcx, r15
0x1400841ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400841f1  mov     ebx, eax
0x1400841f3  mov     rcx, [r15]
0x1400841f6  mov     rax, [rcx+38h]
0x1400841fa  mov     rcx, r15
0x1400841fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084202  mov     rdx, rax
0x140084205  lea     rcx, [rbp+57h+var_88]
0x140084209  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008420e  nop
0x14008420f  mov     rdx, [rbp+57h+ppszOut]
0x140084213  lea     rcx, [rbp+57h+var_90]
0x140084217  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008421c  nop
0x14008421d  lea     rax, [rbp+57h+var_C8]
0x140084221  mov     [rsp+130h+var_F0], rax
0x140084226  mov     rax, [rbp+57h+var_B8]
0x14008422a  mov     [rsp+130h+var_F8], rax
0x14008422f  lea     rax, [rsp+130h+var_D8]
0x140084234  mov     [rsp+130h+var_100], rax
0x140084239  mov     [rsp+130h+var_108], rsi
0x14008423e  mov     [rsp+130h+var_110], edi
0x140084242  mov     r9d, ebx
0x140084245  lea     r8, [rbp+57h+var_88]
0x140084249  lea     rdx, [rbp+57h+var_90]
0x14008424d  mov     rcx, r14
0x140084250  call    ?CreateStackContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEBUSHMEDistinctSubcontainerDefinition@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateStackContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,SHMEDistinctSubcontainerDefinition const *,IHMEMediaContainer * *)
0x140084255  mov     ebx, eax
0x140084257  lea     rcx, [rbp+57h+var_90]
0x14008425b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084260  nop
0x140084261  lea     rcx, [rbp+57h+var_88]
0x140084265  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008426a  nop
0x14008426b  lea     rcx, [rsp+130h+var_D8]
0x140084270  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084275  mov     rcx, [rbp+57h+pv]; pv
0x140084279  call    cs:__imp_CoTaskMemFree
0x14008427f  mov     rcx, [rbp+57h+ppszOut]; pv
0x140084283  call    cs:__imp_CoTaskMemFree
0x140084289  test    ebx, ebx
0x14008428b  js      short loc_14008429B
0x14008428d  mov     rdx, [rbp+57h+var_C8]
0x140084291  mov     rcx, [rbp+57h+var_70]
  ... truncated ...
```
