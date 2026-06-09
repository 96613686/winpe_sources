# CGeneratedStackContainer::CreateSubcontainers(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> const &,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140084568`
- end: `0x1400849b5`
- name: `?CreateSubcontainers@CGeneratedStackContainer@@IEAAJAEBV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@3@@Z`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x140085ae0`

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
- `0x140061f34`
- `0x140081fcc`
- `0x14008328c`
- `0x140084568`
- `0x140087438`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x140084985`
- `ole32!PropVariantClear` at `0x140084985`
- `ole32!CoTaskMemFree` at `0x140084951`
- `ole32!CoTaskMemFree` at `0x14008495b`
- `ole32!CoTaskMemFree` at `0x140084951`
- `ole32!CoTaskMemFree` at `0x14008495b`
- `PROPSYS!PropVariantToStringAlloc` at `0x140084713`
- `PROPSYS!PropVariantToStringAlloc` at `0x140084713`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CGeneratedStackContainer::CreateSubcontainers(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  HRESULT StackContainer; // ebx
  unsigned __int64 i; // r13
  _QWORD *v7; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  int v10; // esi
  int v11; // edi
  char *v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // eax
  char *HMEUnknownString; // rax
  const unsigned __int16 *v16; // rbx
  struct IPropertyStore **v17; // rax
  unsigned __int16 *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r14
  __int64 v23; // rsi
  int v24; // edi
  int v25; // ebx
  char *v26; // rax
  __int64 v28; // [rsp+58h] [rbp-59h] BYREF
  __int64 v29; // [rsp+60h] [rbp-51h] BYREF
  __int64 v30; // [rsp+68h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-41h] BYREF
  PWSTR ppszOut; // [rsp+78h] [rbp-39h] BYREF
  void *v33; // [rsp+80h] [rbp-31h] BYREF
  void *v34; // [rsp+88h] [rbp-29h] BYREF
  __int64 v35; // [rsp+90h] [rbp-21h] BYREF
  void *v36; // [rsp+98h] [rbp-19h] BYREF
  void *v37; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-1h] BYREF
  PROPVARIANT propvar[2]; // [rsp+B8h] [rbp+7h] BYREF
  __int64 v41; // [rsp+C8h] [rbp+17h]
  unsigned __int16 *v44; // [rsp+130h] [rbp+7Fh] BYREF

  v3 = a2;
  StackContainer = 0;
  for ( i = 0; i < v3[1]; ++i )
  {
    if ( StackContainer < 0 )
      break;
    *(_OWORD *)propvar = 0;
    v41 = 0;
    v7 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                     v3,
                     i);
    StackContainer = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)*v7 + 40LL))(
                       *v7,
                       *(_QWORD *)(a1[8] + 16LL),
                       propvar);
    if ( StackContainer >= 0 )
    {
      v29 = 0;
      if ( LOWORD(propvar[0]) == 1 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v30);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
          &v30,
          L"%s AND %s IS NULL",
          a1[7],
          *(_QWORD *)(a1[8] + 8LL));
        v8 = a1[9];
        v9 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
        v10 = *(_DWORD *)(a1[8] + 24LL);
        v11 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
        v12 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v34,
          v12);
        v13 = *(_QWORD *)(a1[8] + 16LL);
        v14 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
        HMEUnknownString = (char *)CHMEUnknownStringUtil::GetHMEUnknownString(v14, v13);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v33,
          HMEUnknownString);
        StackContainer = CGeneratedContainerFactory::CreateStackContainer(
                           v8,
                           (unsigned int)&v33,
                           (unsigned int)&v34,
                           v11,
                           v10,
                           v9,
                           (__int64)&v30,
                           0,
                           (__int64)&v29);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v33);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v34);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v30);
        v3 = a2;
      }
      else
      {
        ppszOut = 0;
        StackContainer = PropVariantToStringAlloc(propvar, &ppszOut);
        if ( StackContainer >= 0 )
        {
          pv = 0;
          v16 = *(const unsigned __int16 **)(a1[8] + 8LL);
          v17 = (struct IPropertyStore **)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                                            v3,
                                            i);
          StackContainer = GetDistinctValueFromItem(*v17, v16, (unsigned __int16 **)&pv);
          if ( StackContainer >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              (void **)&v44,
              (char *)pv);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
              &v44,
              L"'",
              L"''");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v28);
            if ( CShellPropertyThunk::IsPropertyMultiValued(*(const unsigned __int16 **)(a1[8] + 8LL)) )
            {
              v18 = v44;
              if ( ContainsInvalidContainsCharacters(v44) )
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                  &v28,
                  L"%s AND %s LIKE '%%%s%%'",
                  a1[7],
                  *(_QWORD *)(a1[8] + 8LL),
                  v18);
              }
              else
              {
                if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                     &v44,
                                     32,
                                     0) != -1
                  || (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                     &v44,
                                     44,
                                     v19) != -1 )
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Replace(
                    &v44,
                    L"\"",
                    L"\"\"");
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                    &v35,
                    "\"");
                  v20 = ATL::operator+(&v39, L"\"", &v44);
                  v21 = (_QWORD *)ATL::operator+(&v38, v20, &v35);
                  ATL::CSimpleStringT<unsigned short,0>::operator=(&v44, v21);
                  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v38);
                  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v39);
                  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v35);
                  v18 = v44;
                }
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                  &v28,
                  L"%s AND CONTAINS(%s, '%s')",
                  a1[7],
                  *(_QWORD *)(a1[8] + 8LL),
                  v18);
              }
            }
            else
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                &v28,
                L"%s AND %s = '%s'",
                a1[7],
                *(_QWORD *)(a1[8] + 8LL),
                v44);
            }
            v22 = a1[9];
            v23 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
            v24 = *(_DWORD *)(a1[8] + 24LL);
            v25 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
            v26 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v37,
              v26);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v36,
              (char *)ppszOut);
            StackContainer = CGeneratedContainerFactory::CreateStackContainer(
                               v22,
                               (unsigned int)&v36,
                               (unsigned int)&v37,
                               v25,
                               v24,
                               v23,
                               (__int64)&v28,
                               0,
                               (__int64)&v29);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v36);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v37);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v28);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v44);
          }
          CoTaskMemFree(pv);
        }
        CoTaskMemFree(ppszOut);
      }
      if ( StackContainer >= 0 )
        ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
          a3,
          v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    }
    PropVariantClear(propvar);
  }
  return (unsigned int)StackContainer;
}

```

## disassembly

```asm
0x140084568  mov     rax, rsp
0x14008456b  mov     [rax+8], rbx
0x14008456f  mov     [rax+18h], r8
0x140084573  mov     [rax+10h], rdx
0x140084577  push    rbp
0x140084578  push    rsi
0x140084579  push    rdi
0x14008457a  push    r12
0x14008457c  push    r13
0x14008457e  push    r14
0x140084580  push    r15
0x140084582  lea     rbp, [rax-5Fh]
0x140084586  sub     rsp, 0D0h
0x14008458d  mov     r15, rdx
0x140084590  mov     r12, rcx
0x140084593  xor     ebx, ebx
0x140084595  xor     r13d, r13d
0x140084598  cmp     [rdx+8], rbx
0x14008459c  jbe     loc_140084998
0x1400845a2  lea     edi, [rbx+1]
0x1400845a5  test    ebx, ebx
0x1400845a7  js      loc_140084998
0x1400845ad  xorps   xmm0, xmm0
0x1400845b0  xor     eax, eax
0x1400845b2  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x1400845b6  mov     [rbp+57h+var_40], rax
0x1400845ba  mov     rdx, r13
0x1400845bd  mov     rcx, r15
0x1400845c0  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x1400845c5  mov     rcx, [rax]
0x1400845c8  mov     rax, [rcx]
0x1400845cb  mov     rdx, [r12+40h]
0x1400845d0  lea     r8, [rbp+57h+propvar]
0x1400845d4  mov     rdx, [rdx+10h]
0x1400845d8  mov     rax, [rax+28h]
0x1400845dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400845e1  mov     ebx, eax
0x1400845e3  test    eax, eax
0x1400845e5  js      loc_140084981
0x1400845eb  mov     [rbp+57h+var_A8], 0
0x1400845f3  cmp     di, word ptr [rbp+57h+propvar]
0x1400845f7  jnz     loc_140084703
0x1400845fd  lea     rcx, [rbp+57h+var_A0]
0x140084601  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140084606  nop
0x140084607  mov     r9, [r12+40h]
0x14008460c  mov     r9, [r9+8]
0x140084610  mov     r8, [r12+38h]
0x140084615  lea     rdx, aSAndSIsNull; "%s AND %s IS NULL"
0x14008461c  lea     rcx, [rbp+57h+var_A0]
0x140084620  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140084625  mov     r15, [r12+48h]
0x14008462a  mov     rax, [r12]
0x14008462e  mov     rcx, r12
0x140084631  mov     rax, [rax+60h]
0x140084635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008463a  mov     r14, rax
0x14008463d  mov     rcx, [r12+40h]
0x140084642  mov     esi, [rcx+18h]
0x140084645  mov     rcx, [r12]
0x140084649  mov     rax, [rcx+50h]
0x14008464d  mov     rcx, r12
0x140084650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084655  mov     edi, eax
0x140084657  mov     rcx, [r12]
0x14008465b  mov     rax, [rcx+38h]
0x14008465f  mov     rcx, r12
0x140084662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084667  mov     rdx, rax
0x14008466a  lea     rcx, [rbp+57h+var_80]
0x14008466e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084673  nop
0x140084674  mov     rcx, [r12+40h]
0x140084679  mov     rbx, [rcx+10h]
0x14008467d  mov     rcx, [r12]
0x140084681  mov     rax, [rcx+50h]
0x140084685  mov     rcx, r12
0x140084688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008468d  mov     rdx, rbx
0x140084690  mov     ecx, eax
0x140084692  call    ?GetHMEUnknownString@CHMEUnknownStringUtil@@SAPEBGW4MediaCacheSchema@@AEBU_tagpropertykey@@@Z; CHMEUnknownStringUtil::GetHMEUnknownString(MediaCacheSchema,_tagpropertykey const &)
0x140084697  mov     rdx, rax
0x14008469a  lea     rcx, [rbp+57h+var_88]
0x14008469e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400846a3  nop
0x1400846a4  lea     rax, [rbp+57h+var_A8]
0x1400846a8  mov     [rsp+40h], rax
0x1400846ad  mov     [rsp+100h+var_C8], 0
0x1400846b6  lea     rax, [rbp+57h+var_A0]
0x1400846ba  mov     [rsp+100h+var_D0], rax
0x1400846bf  mov     [rsp+100h+var_D8], r14
0x1400846c4  mov     dword ptr [rsp+100h+var_E0], esi
0x1400846c8  mov     r9d, edi
0x1400846cb  lea     r8, [rbp+57h+var_80]
0x1400846cf  lea     rdx, [rbp+57h+var_88]
0x1400846d3  mov     rcx, r15
0x1400846d6  call    ?CreateStackContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEBUSHMEDistinctSubcontainerDefinition@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateStackContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,SHMEDistinctSubcontainerDefinition const *,IHMEMediaContainer * *)
0x1400846db  mov     ebx, eax
0x1400846dd  lea     rcx, [rbp+57h+var_88]
0x1400846e1  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400846e6  nop
0x1400846e7  lea     rcx, [rbp+57h+var_80]
0x1400846eb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400846f0  nop
0x1400846f1  lea     rcx, [rbp+57h+var_A0]
0x1400846f5  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400846fa  mov     r15, [rbp+57h+arg_8]
0x1400846fe  jmp     loc_140084961
0x140084703  mov     [rbp+57h+ppszOut], 0
0x14008470b  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x14008470f  lea     rcx, [rbp+57h+propvar]; propvar
0x140084713  call    cs:__imp_PropVariantToStringAlloc
0x140084719  mov     ebx, eax
0x14008471b  test    eax, eax
0x14008471d  js      loc_140084957
0x140084723  mov     [rbp+57h+pv], 0
0x14008472b  mov     rax, [r12+40h]
0x140084730  mov     rbx, [rax+8]
0x140084734  mov     rdx, r13
0x140084737  mov     rcx, r15
0x14008473a  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x14008473f  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x140084743  mov     rdx, rbx; unsigned __int16 *
0x140084746  mov     rcx, [rax]; struct IPropertyStore *
0x140084749  call    ?GetDistinctValueFromItem@@YAJPEAUIPropertyStore@@PEBGPEAPEAG@Z; GetDistinctValueFromItem(IPropertyStore *,ushort const *,ushort * *)
0x14008474e  mov     ebx, eax
0x140084750  test    eax, eax
0x140084752  js      loc_14008494D
0x140084758  mov     rdx, [rbp+57h+pv]
0x14008475c  lea     rcx, [rbp+57h+arg_18]
0x140084760  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084765  nop
0x140084766  lea     r8, asc_1400A5BFC; "''"
0x14008476d  lea     rdx, asc_1400A5BF8; "'"
0x140084774  lea     rcx, [rbp+57h+arg_18]
0x140084778  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort const *,ushort const *)
0x14008477d  lea     rcx, [rbp+57h+var_B0]
0x140084781  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140084786  nop
0x140084787  mov     rcx, [r12+40h]
0x14008478c  mov     rcx, [rcx+8]; unsigned __int16 *
0x140084790  call    ?IsPropertyMultiValued@CShellPropertyThunk@@SA_NPEBG@Z; CShellPropertyThunk::IsPropertyMultiValued(ushort const *)
0x140084795  test    al, al
0x140084797  jz      loc_140084869
0x14008479d  mov     rbx, [rbp+57h+arg_18]
0x1400847a1  mov     rcx, rbx; unsigned __int16 *
0x1400847a4  call    ?ContainsInvalidContainsCharacters@@YA_NPEBG@Z; ContainsInvalidContainsCharacters(ushort const *)
0x1400847a9  test    al, al
0x1400847ab  jz      short loc_1400847BE
0x1400847ad  mov     [rsp+100h+var_E0], rbx
0x1400847b2  lea     rdx, aSAndSLikeS; "%s AND %s LIKE '%%%s%%'"
0x1400847b9  jmp     loc_140084879
0x1400847be  mov     edx, 20h ; ' '
0x1400847c3  xor     r8d, r8d
0x1400847c6  lea     rcx, [rbp+57h+arg_18]
0x1400847ca  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Find(ushort,int)
0x1400847cf  cmp     eax, 0FFFFFFFFh
0x1400847d2  jnz     short loc_1400847E5
0x1400847d4  lea     edx, [rax+2Dh]
0x1400847d7  lea     rcx, [rbp+57h+arg_18]
0x1400847db  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Find(ushort,int)
0x1400847e0  cmp     eax, 0FFFFFFFFh
0x1400847e3  jz      short loc_14008485B
0x1400847e5  lea     r8, asc_1400AAB3C; "\"\""
0x1400847ec  lea     rdx, asc_1400A3A6C; "\""
0x1400847f3  lea     rcx, [rbp+57h+arg_18]
0x1400847f7  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Replace(ushort const *,ushort const *)
0x1400847fc  lea     rdx, asc_1400AE1AC; "\""
0x140084803  lea     rcx, [rbp+57h+var_78]
0x140084807  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14008480c  lea     r8, [rbp+57h+arg_18]
0x140084810  lea     rdx, asc_1400A3A6C; "\""
0x140084817  lea     rcx, [rbp+57h+var_58]
0x14008481b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140084820  lea     r8, [rbp+57h+var_78]
0x140084824  mov     rdx, rax
0x140084827  lea     rcx, [rbp+57h+var_60]
0x14008482b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140084830  mov     rdx, rax
0x140084833  lea     rcx, [rbp+57h+arg_18]
0x140084837  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14008483c  lea     rcx, [rbp+57h+var_60]
0x140084840  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084845  lea     rcx, [rbp+57h+var_58]
0x140084849  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008484e  lea     rcx, [rbp+57h+var_78]
0x140084852  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084857  mov     rbx, [rbp+57h+arg_18]
0x14008485b  mov     [rsp+100h+var_E0], rbx
0x140084860  lea     rdx, aSAndContainsSS; "%s AND CONTAINS(%s, '%s')"
0x140084867  jmp     short loc_140084879
0x140084869  mov     rax, [rbp+57h+arg_18]
0x14008486d  mov     [rsp+100h+var_E0], rax
0x140084872  lea     rdx, aSAndSS; "%s AND %s = '%s'"
0x140084879  mov     r9, [r12+40h]
0x14008487e  mov     r9, [r9+8]
0x140084882  mov     r8, [r12+38h]
0x140084887  lea     rcx, [rbp+57h+var_B0]
0x14008488b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140084890  mov     r14, [r12+48h]
0x140084895  mov     rax, [r12]
0x140084899  mov     rcx, r12
0x14008489c  mov     rax, [rax+60h]
0x1400848a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400848a5  mov     rsi, rax
0x1400848a8  mov     rcx, [r12+40h]
0x1400848ad  mov     edi, [rcx+18h]
0x1400848b0  mov     rcx, [r12]
0x1400848b4  mov     rax, [rcx+50h]
0x1400848b8  mov     rcx, r12
0x1400848bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400848c0  mov     ebx, eax
0x1400848c2  mov     rcx, [r12]
0x1400848c6  mov     rax, [rcx+38h]
0x1400848ca  mov     rcx, r12
0x1400848cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400848d2  mov     rdx, rax
0x1400848d5  lea     rcx, [rbp+57h+var_68]
0x1400848d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400848de  nop
0x1400848df  mov     rdx, [rbp+57h+ppszOut]
0x1400848e3  lea     rcx, [rbp+57h+var_70]
0x1400848e7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400848ec  nop
0x1400848ed  lea     rax, [rbp+57h+var_A8]
0x1400848f1  mov     [rsp+40h], rax
0x1400848f6  mov     [rsp+100h+var_C8], 0
0x1400848ff  lea     rax, [rbp+57h+var_B0]
0x140084903  mov     [rsp+100h+var_D0], rax
0x140084908  mov     [rsp+100h+var_D8], rsi
0x14008490d  mov     dword ptr [rsp+100h+var_E0], edi
0x140084911  mov     r9d, ebx
0x140084914  lea     r8, [rbp+57h+var_68]
0x140084918  lea     rdx, [rbp+57h+var_70]
0x14008491c  mov     rcx, r14
0x14008491f  call    ?CreateStackContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEBUSHMEDistinctSubcontainerDefinition@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateStackContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,SHMEDistinctSubcontainerDefinition const *,IHMEMediaContainer * *)
0x140084924  mov     ebx, eax
0x140084926  lea     rcx, [rbp+57h+var_70]
0x14008492a  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008492f  nop
0x140084930  lea     rcx, [rbp+57h+var_68]
0x140084934  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084939  nop
0x14008493a  lea     rcx, [rbp+57h+var_B0]
0x14008493e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084943  nop
0x140084944  lea     rcx, [rbp+57h+arg_18]
0x140084948  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14008494d  mov     rcx, [rbp+57h+pv]; pv
0x140084951  call    cs:__imp_CoTaskMemFree
0x140084957  mov     rcx, [rbp+57h+ppszOut]; pv
0x14008495b  call    cs:__imp_CoTaskMemFree
0x140084961  test    ebx, ebx
0x140084963  js      short loc_140084973
0x140084965  mov     rdx, [rbp+57h+var_A8]
0x140084969  mov     rcx, [rbp+57h+arg_10]
0x14008496d  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x140084972  nop
0x140084973  lea     rcx, [rbp+57h+var_A8]
0x140084977  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008497c  mov     edi, 1
0x140084981  lea     rcx, [rbp+57h+propvar]; pvar
0x140084985  call    cs:__imp_PropVariantClear
0x14008498b  add     r13, rdi
0x14008498e  cmp     r13, [r15+8]
0x140084992  jb      loc_1400845A5
0x140084998  mov     eax, ebx
0x14008499a  mov     rbx, [rsp+100h+arg_0]
0x1400849a2  add     rsp, 0D0h
0x1400849a9  pop     r15
0x1400849ab  pop     r14
0x1400849ad  pop     r13
0x1400849af  pop     r12
0x1400849b1  pop     rdi
0x1400849b2  pop     rsi
0x1400849b3  pop     rbp
0x1400849b4  retn
```
