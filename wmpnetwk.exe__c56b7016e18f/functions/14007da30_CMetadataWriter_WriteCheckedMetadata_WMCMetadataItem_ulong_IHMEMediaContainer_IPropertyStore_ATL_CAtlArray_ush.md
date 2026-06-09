# CMetadataWriter::WriteCheckedMetadata(_WMCMetadataItem *,ulong,IHMEMediaContainer *,IPropertyStore *,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> const &,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> const &,IPropertyStore *)

- ea: `0x14007da30`
- end: `0x14007dd4b`
- name: `?WriteCheckedMetadata@CMetadataWriter@@IEAAJPEAU_WMCMetadataItem@@KPEAUIHMEMediaContainer@@PEAUIPropertyStore@@AEBV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@32@Z`
- size: `795`
- prototype: `__int64 __fastcall(WCHAR *, __int64, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14007df94`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x1400276c0`
- `0x140027e30`
- `0x14002defc`
- `0x140039480`
- `0x14007da30`
- `0x14007dd54`
- `0x14009e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14007db62`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14007db78`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14007db62`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14007db78`
- `ole32!PropVariantClear` at `0x14007dcfe`
- `ole32!PropVariantClear` at `0x14007dd12`
- `ole32!PropVariantClear` at `0x14007dcfe`
- `ole32!PropVariantClear` at `0x14007dd12`
- `ole32!CoTaskMemFree` at `0x14007dd08`
- `ole32!CoTaskMemFree` at `0x14007dd08`
- `PROPSYS!PropVariantToStringAlloc` at `0x14007dc0b`
- `PROPSYS!PropVariantToStringAlloc` at `0x14007dc0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMetadataWriter::WriteCheckedMetadata(
        WCHAR *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  HRESULT inited; // ebx
  unsigned int v11; // esi
  __int64 i; // r14
  __int64 AtomForElement; // r10
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  int v20; // eax
  __int64 (__fastcall *v21)(__int64, __int64, _QWORD); // rbx
  unsigned int v22; // eax
  int ValueForProperty; // eax
  char *v24; // r8
  PWSTR v25; // rcx
  int v26; // eax
  int v27; // edx
  signed __int64 v28; // r8
  int v29; // eax
  int v30; // edx
  const unsigned __int16 **v31; // rax
  int v32; // eax
  int v33; // eax
  char v35[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v36; // [rsp+38h] [rbp-48h] BYREF
  __int64 v37; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT propvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h]
  struct tagPROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF
  PWSTR ppszOut; // [rsp+B0h] [rbp+30h] BYREF
  int v42; // [rsp+C0h] [rbp+40h] BYREF

  v42 = a3;
  ppszOut = a1;
  inited = 0;
  v11 = 0;
  for ( i = a6; (unsigned __int64)v11 < *(_QWORD *)(i + 8); ++v11 )
  {
    AtomForElement = (int)CdsValues::GetAtomForElement(*(unsigned int *)(a2 + 8LL * v11));
    if ( !qword_1400BC4B8[10 * AtomForElement] )
    {
      inited = -2147220634;
      continue;
    }
    if ( (_DWORD)AtomForElement == 32 )
    {
      v14 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                        a7,
                        v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        v35,
        *v14);
      v15 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                        i,
                        v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &a6,
        *v15);
      inited = CMetadataWriter::WriteDate(v16, a5, &a6, v35, a4, a8);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a6);
      v17 = (__int64 *)v35;
    }
    else
    {
      if ( (_DWORD)AtomForElement != 66 )
      {
        *(_OWORD *)propvar = 0;
        v39 = 0;
        ValueForProperty = CShellPropertyThunk::GetValueForProperty((unsigned int)AtomForElement, a5, 0, a4, propvar);
        inited = ValueForProperty;
        if ( ValueForProperty == -2147023728 )
        {
          LOWORD(propvar[0]) = 0;
LABEL_16:
          ppszOut = 0;
          inited = PropVariantToStringAlloc(propvar, &ppszOut);
          if ( inited >= 0 )
          {
            v24 = *(char **)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                              i,
                              v11);
            v25 = ppszOut;
            if ( *(_DWORD *)(a2 + 8LL * v11) == 51 )
            {
              v26 = *(unsigned __int16 *)v24;
              v27 = 48 - v26;
              if ( v26 == 48 )
                v27 = -*((unsigned __int16 *)v24 + 1);
              if ( !v27 && !*ppszOut )
                goto LABEL_26;
            }
            v28 = v24 - (char *)ppszOut;
            do
            {
              v29 = *(PWSTR)((char *)v25 + v28);
              v30 = *v25 - v29;
              if ( v30 )
                break;
              ++v25;
            }
            while ( v29 );
            if ( !v30 )
            {
LABEL_26:
              memset(&pvar, 0, sizeof(pvar));
              v31 = (const unsigned __int16 **)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                                                 a7,
                                                 v11);
              inited = InitPropVariantFromString(*v31, &pvar);
              if ( inited >= 0 )
              {
                v32 = CdsValues::GetAtomForElement(*(unsigned int *)(a2 + 8LL * v11));
                v33 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey * near *, struct tagPROPVARIANT *))(*(_QWORD *)a8 + 48LL))(
                        a8,
                        (&CShellProvider::s_EditableWMPAtomByCdsValue)[v32],
                        &pvar);
                inited = v33;
                if ( v33 < 0 )
                {
                  if ( v33 == -2147024809 || (inited = -2147220631, v33 == -2147316576) )
                    inited = -2147220633;
                }
              }
              PropVariantClear((PROPVARIANT *)&pvar);
            }
          }
          CoTaskMemFree(ppszOut);
        }
        else if ( ValueForProperty >= 0 )
        {
          goto LABEL_16;
        }
        PropVariantClear(propvar);
        continue;
      }
      v18 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                        a7,
                        v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v37,
        *v18);
      v19 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                        i,
                        v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v36,
        *v19);
      v42 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)a4 + 104LL))(a4, a5, &v42) >= 0
        && (v20 = _o__wtoi(v36), v20 == v42) )
      {
        v21 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a4 + 112LL);
        v22 = _o__wtoi(v37);
        inited = v21(a4, a5, v22);
        if ( inited < 0 )
          inited = -2147220631;
      }
      else
      {
        inited = -2147220634;
      }
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v36);
      v17 = &v37;
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v17);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14007da30  mov     rax, rsp
0x14007da33  mov     [rax+10h], rbx
0x14007da37  mov     [rax+20h], rsi
0x14007da3b  mov     [rax+18h], r8d
0x14007da3f  mov     [rax+8], rcx
0x14007da43  push    rbp
0x14007da44  push    rdi
0x14007da45  push    r13
0x14007da47  push    r14
0x14007da49  push    r15
0x14007da4b  mov     rbp, rsp
0x14007da4e  sub     rsp, 80h
0x14007da55  mov     r15, r9
0x14007da58  mov     r13, rdx
0x14007da5b  xor     eax, eax
0x14007da5d  mov     ebx, eax
0x14007da5f  mov     esi, eax
0x14007da61  mov     r14, [rbp+arg_28]
0x14007da65  cmp     [r14+8], rax
0x14007da69  jbe     loc_14007DD2D
0x14007da6f  mov     edi, esi
0x14007da71  mov     ecx, [r13+rdi*8+0]
0x14007da76  call    ?GetAtomForElement@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@@Z; CdsValues::GetAtomForElement(CDS_ELEMENT_VALUE)
0x14007da7b  movsxd  r10, eax
0x14007da7e  lea     rcx, [r10+r10*4]
0x14007da82  add     rcx, rcx
0x14007da85  xor     ebx, ebx
0x14007da87  lea     rax, __ImageBase
0x14007da8e  cmp     rva qword_1400BC4B8[rax+rcx*8], rbx
0x14007da96  jz      loc_14007DD1A
0x14007da9c  cmp     r10d, 20h ; ' '
0x14007daa0  jnz     short loc_14007DB05
0x14007daa2  mov     edx, edi
0x14007daa4  mov     rcx, [rbp+arg_30]
0x14007daa8  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007daad  mov     rdx, [rax]
0x14007dab0  lea     rcx, [rbp+var_50]
0x14007dab4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007dab9  nop
0x14007daba  mov     edx, edi
0x14007dabc  mov     rcx, r14
0x14007dabf  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007dac4  mov     rdx, [rax]
0x14007dac7  lea     rcx, [rbp+arg_28]
0x14007dacb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007dad0  nop
0x14007dad1  mov     rax, [rbp+arg_38]
0x14007dad5  mov     [rsp+80h+var_58], rax
0x14007dada  mov     [rsp+80h+var_60], r15
0x14007dadf  lea     r9, [rbp+var_50]
0x14007dae3  lea     r8, [rbp+arg_28]
0x14007dae7  mov     rdx, [rbp+arg_20]
0x14007daeb  call    ?WriteDate@CMetadataWriter@@IEAAJPEAUIPropertyStore@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@1PEAUIHMEMediaContainer@@0@Z; CMetadataWriter::WriteDate(IPropertyStore *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IHMEMediaContainer *,IPropertyStore *)
0x14007daf0  mov     ebx, eax
0x14007daf2  lea     rcx, [rbp+arg_28]
0x14007daf6  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007dafb  nop
0x14007dafc  lea     rcx, [rbp+var_50]
0x14007db00  jmp     loc_14007DBB0
0x14007db05  cmp     r10d, 42h ; 'B'
0x14007db09  jnz     loc_14007DBBA
0x14007db0f  mov     rdx, rdi
0x14007db12  mov     rcx, [rbp+arg_30]
0x14007db16  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007db1b  mov     rdx, [rax]
0x14007db1e  lea     rcx, [rbp+var_40]
0x14007db22  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007db27  nop
0x14007db28  mov     rdx, rdi
0x14007db2b  mov     rcx, r14
0x14007db2e  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007db33  mov     rdx, [rax]
0x14007db36  lea     rcx, [rbp+var_48]
0x14007db3a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14007db3f  nop
0x14007db40  mov     [rbp+arg_10], ebx
0x14007db43  mov     rax, [r15]
0x14007db46  lea     r8, [rbp+arg_10]
0x14007db4a  mov     rdx, [rbp+arg_20]
0x14007db4e  mov     rcx, r15
0x14007db51  mov     rax, [rax+68h]
0x14007db55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007db5a  test    eax, eax
0x14007db5c  js      short loc_14007DB9D
0x14007db5e  mov     rcx, [rbp+var_48]
0x14007db62  call    cs:__imp__o__wtoi
0x14007db68  cmp     eax, [rbp+arg_10]
0x14007db6b  jnz     short loc_14007DB9D
0x14007db6d  mov     rax, [r15]
0x14007db70  mov     rbx, [rax+70h]
0x14007db74  mov     rcx, [rbp+var_40]
0x14007db78  call    cs:__imp__o__wtoi
0x14007db7e  mov     r8d, eax
0x14007db81  mov     rdx, [rbp+arg_20]
0x14007db85  mov     rcx, r15
0x14007db88  mov     rax, rbx
0x14007db8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007db90  mov     ebx, eax
0x14007db92  test    eax, eax
0x14007db94  jns     short loc_14007DBA2
0x14007db96  mov     ebx, 80040369h
0x14007db9b  jmp     short loc_14007DBA2
0x14007db9d  mov     ebx, 80040366h
0x14007dba2  lea     rcx, [rbp+var_48]
0x14007dba6  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007dbab  nop
0x14007dbac  lea     rcx, [rbp+var_40]
0x14007dbb0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007dbb5  jmp     loc_14007DD1F
0x14007dbba  xorps   xmm0, xmm0
0x14007dbbd  xor     eax, eax
0x14007dbbf  movups  xmmword ptr [rbp+propvar], xmm0
0x14007dbc3  mov     [rbp+var_28], rax
0x14007dbc7  lea     rax, [rbp+propvar]
0x14007dbcb  mov     [rsp+80h+var_60], rax
0x14007dbd0  mov     r9, r15
0x14007dbd3  xor     r8d, r8d
0x14007dbd6  mov     rdx, [rbp+arg_20]
0x14007dbda  mov     ecx, r10d
0x14007dbdd  call    ?GetValueForProperty@CShellPropertyThunk@@SAJW4Value@CdsValue@@PEAUIPropertyStore@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z; CShellPropertyThunk::GetValueForProperty(CdsValue::Value,IPropertyStore *,long,IHMEMediaContainer *,tagPROPVARIANT *)
0x14007dbe2  mov     ebx, eax
0x14007dbe4  cmp     eax, 80070490h
0x14007dbe9  jnz     short loc_14007DBF3
0x14007dbeb  xor     eax, eax
0x14007dbed  mov     word ptr [rbp+propvar], ax
0x14007dbf1  jmp     short loc_14007DBFB
0x14007dbf3  test    eax, eax
0x14007dbf5  js      loc_14007DD0E
0x14007dbfb  mov     [rbp+ppszOut], 0
0x14007dc03  lea     rdx, [rbp+ppszOut]; ppszOut
0x14007dc07  lea     rcx, [rbp+propvar]; propvar
0x14007dc0b  call    cs:__imp_PropVariantToStringAlloc
0x14007dc11  mov     ebx, eax
0x14007dc13  test    eax, eax
0x14007dc15  js      loc_14007DD04
0x14007dc1b  mov     rdx, rdi
0x14007dc1e  mov     rcx, r14
0x14007dc21  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007dc26  mov     r8, [rax]
0x14007dc29  mov     rcx, [rbp+ppszOut]
0x14007dc2d  cmp     dword ptr [r13+rdi*8+0], 33h ; '3'
0x14007dc33  jnz     short loc_14007DC5F
0x14007dc35  mov     edx, 30h ; '0'
0x14007dc3a  movzx   eax, word ptr [r8]
0x14007dc3e  sub     edx, eax
0x14007dc40  jnz     short loc_14007DC52
0x14007dc42  xor     r9d, r9d
0x14007dc45  movzx   edx, r9w
0x14007dc49  movzx   eax, word ptr [r8+2]
0x14007dc4e  sub     edx, eax
0x14007dc50  jmp     short loc_14007DC55
0x14007dc52  xor     r9d, r9d
0x14007dc55  test    edx, edx
0x14007dc57  jnz     short loc_14007DC5F
0x14007dc59  cmp     [rcx], r9w
0x14007dc5d  jz      short loc_14007DC7E
0x14007dc5f  sub     r8, rcx
0x14007dc62  movzx   edx, word ptr [rcx]
0x14007dc65  movzx   eax, word ptr [rcx+r8]
0x14007dc6a  sub     edx, eax
0x14007dc6c  jnz     short loc_14007DC76
0x14007dc6e  add     rcx, 2
0x14007dc72  test    eax, eax
0x14007dc74  jnz     short loc_14007DC62
0x14007dc76  test    edx, edx
0x14007dc78  jnz     loc_14007DD04
0x14007dc7e  xorps   xmm0, xmm0
0x14007dc81  xor     eax, eax
0x14007dc83  movups  xmmword ptr [rbp+pvar], xmm0
0x14007dc87  mov     [rbp+var_10], rax
0x14007dc8b  mov     rdx, rdi
0x14007dc8e  mov     rcx, [rbp+arg_30]
0x14007dc92  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14007dc97  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x14007dc9b  mov     rcx, [rax]; Src
0x14007dc9e  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x14007dca3  mov     ebx, eax
0x14007dca5  test    eax, eax
0x14007dca7  js      short loc_14007DCFA
0x14007dca9  mov     ecx, [r13+rdi*8+0]
0x14007dcae  call    ?GetAtomForElement@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@@Z; CdsValues::GetAtomForElement(CDS_ELEMENT_VALUE)
0x14007dcb3  mov     r9, [rbp+arg_38]
0x14007dcb7  mov     rcx, [r9]
0x14007dcba  movsxd  rdx, eax
0x14007dcbd  mov     rax, [rcx+30h]
0x14007dcc1  lea     r8, [rbp+pvar]
0x14007dcc5  lea     rcx, __ImageBase
0x14007dccc  mov     rdx, rva ?s_EditableWMPAtomByCdsValue@CShellProvider@@2PAPEBU_tagpropertykey@@A[rcx+rdx*8]; _tagpropertykey const * near * CShellProvider::s_EditableWMPAtomByCdsValue ...
0x14007dcd4  mov     rcx, r9
0x14007dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007dcdc  mov     ebx, eax
0x14007dcde  test    eax, eax
0x14007dce0  jns     short loc_14007DCFA
0x14007dce2  cmp     eax, 80070057h
0x14007dce7  jz      short loc_14007DCF5
0x14007dce9  cmp     eax, 80028CA0h
0x14007dcee  mov     ebx, 80040369h
0x14007dcf3  jnz     short loc_14007DCFA
0x14007dcf5  mov     ebx, 80040367h
0x14007dcfa  lea     rcx, [rbp+pvar]; pvar
0x14007dcfe  call    cs:__imp_PropVariantClear
0x14007dd04  mov     rcx, [rbp+ppszOut]; pv
0x14007dd08  call    cs:__imp_CoTaskMemFree
0x14007dd0e  lea     rcx, [rbp+propvar]; pvar
0x14007dd12  call    cs:__imp_PropVariantClear
0x14007dd18  jmp     short loc_14007DD1F
0x14007dd1a  mov     ebx, 80040366h
0x14007dd1f  inc     esi
0x14007dd21  mov     eax, esi
0x14007dd23  cmp     rax, [r14+8]
0x14007dd27  jb      loc_14007DA6F
0x14007dd2d  mov     eax, ebx
0x14007dd2f  lea     r11, [rsp+80h+var_s0]
0x14007dd37  mov     rbx, [r11+38h]
0x14007dd3b  mov     rsi, [r11+48h]
0x14007dd3f  mov     rsp, r11
0x14007dd42  pop     r15
0x14007dd44  pop     r14
0x14007dd46  pop     r13
0x14007dd48  pop     rdi
0x14007dd49  pop     rbp
0x14007dd4a  retn
```
