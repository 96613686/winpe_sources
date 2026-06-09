# CExtensionList::_InitializeWithFilterAndSortOptions(CCoSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>> &,ICondition *,SORTCOLUMN *,uint,uint,IObjectArray *)

- ea: `0x18007e8f8`
- end: `0x18007ed68`
- name: `?_InitializeWithFilterAndSortOptions@CExtensionList@@AEAAJAEAV?$CCoSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@PEAUICondition@@PEAUSORTCOLUMN@@IIPEAUIObjectArray@@@Z`
- size: `1136`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HSTRING)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180079f60`

## callees

- `0x180003d24`
- `0x180013c80`
- `0x180016694`
- `0x180020e10`
- `0x180022fb4`
- `0x180025bb4`
- `0x180026ee0`
- `0x18002e4a1`
- `0x1800366a0`
- `0x18004b430`
- `0x180075240`
- `0x180077108`
- `0x1800772b0`
- `0x180077690`
- `0x180077740`
- `0x18007a4d4`
- `0x18007dae8`
- `0x18007e8f8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ebb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ebb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ead1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ec5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ece1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ead1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ec5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ece1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExtensionList::_InitializeWithFilterAndSortOptions(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        HSTRING a7)
{
  unsigned __int64 v10; // rbx
  int ExtensionIdFromExtensionItem; // edi
  HSTRING v12; // r15
  unsigned int v13; // esi
  __int64 (__fastcall *v14)(HSTRING, _QWORD, GUID *, struct IExtensionListItem **); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  const WCHAR *v18; // rbx
  unsigned __int64 v19; // rcx
  const WCHAR **v20; // rdx
  unsigned int v21; // edx
  void *v22; // rcx
  unsigned __int64 i; // rsi
  HSTRING v24; // rdi
  __int64 (__fastcall *v25)(HSTRING, GUID *, struct IExtensionListItem **); // rbx
  struct CONDITIONEVALPROPS *v26; // r8
  int DoesItemMatchCondition; // eax
  int v28; // edx
  __int64 v29; // rdx
  __int64 v30; // r15
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  unsigned __int64 v33; // rcx
  LPVOID *v34; // rsi
  unsigned int v35; // edx
  void *v36; // rcx
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rbx
  __int64 v39; // r8
  char v41[8]; // [rsp+30h] [rbp-A1h] BYREF
  HSTRING string; // [rsp+38h] [rbp-99h] BYREF
  struct IExtensionListItem *v43; // [rsp+40h] [rbp-91h] BYREF
  PCWSTR v44; // [rsp+48h] [rbp-89h] BYREF
  __int64 v45; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-79h]
  LPVOID pv; // [rsp+60h] [rbp-71h] BYREF
  __int64 v48; // [rsp+68h] [rbp-69h]
  __int64 v49; // [rsp+70h] [rbp-61h] BYREF
  int v50; // [rsp+78h] [rbp-59h]
  _QWORD v51[4]; // [rsp+80h] [rbp-51h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-31h]
  __int128 v53; // [rsp+B0h] [rbp-21h]
  __int64 v54; // [rsp+C0h] [rbp-11h]

  v10 = 0;
  ExtensionIdFromExtensionItem = 0;
  v41[0] = 0;
  v45 = 0;
  v46 = 0;
  pv = 0;
  v48 = 0;
  v12 = a7;
  if ( a7 )
  {
    LODWORD(a7) = 0;
    ExtensionIdFromExtensionItem = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v12 + 24LL))(v12, &a7);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v13 = 0;
      while ( 1 )
      {
        if ( v13 >= (unsigned int)a7 )
        {
          ExtensionIdFromExtensionItem = 0;
          if ( v46 > 1 )
          {
            pv = 0;
            string = 0;
            ExtensionIdFromExtensionItem = ULongLongMult(v46 >> 1, 8u, (unsigned __int64 *)&string);
            if ( ExtensionIdFromExtensionItem >= 0 )
              ExtensionIdFromExtensionItem = CTCoAllocPolicy::Realloc(v22, v21, 0, (unsigned __int64)string, &pv);
            if ( ExtensionIdFromExtensionItem >= 0 )
            {
              CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_MergeSort<CExtensionList::PWSTRCompare>(
                &v45,
                v41,
                0,
                v46);
              CoTaskMemFree(pv);
              pv = 0;
            }
          }
          goto LABEL_25;
        }
        v43 = 0;
        v14 = *(__int64 (__fastcall **)(HSTRING, _QWORD, GUID *, struct IExtensionListItem **))(*(_QWORD *)v12 + 32LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        ExtensionIdFromExtensionItem = v14(v12, v13, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v43);
        v10 = 0;
        if ( ExtensionIdFromExtensionItem >= 0 )
          break;
LABEL_18:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        ++v13;
        if ( ExtensionIdFromExtensionItem < 0 )
          goto LABEL_43;
      }
      string = 0;
      ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(v43, (struct Windows::Internal::String *)&string);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_17:
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_18;
      }
      v44 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      ExtensionIdFromExtensionItem = _AllocString<CTCoAllocPolicy>(v17, v16, StringRawBuffer, &v44);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_16:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v44);
        goto LABEL_17;
      }
      ExtensionIdFromExtensionItem = 0;
      v18 = v44;
      v19 = v46;
      if ( v46 == v48 )
      {
        ExtensionIdFromExtensionItem = CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(
                                         &v45,
                                         v46 + 1);
        if ( ExtensionIdFromExtensionItem < 0 )
        {
LABEL_13:
          if ( ExtensionIdFromExtensionItem >= 0 )
            v18 = 0;
          v44 = v18;
          v10 = 0;
          goto LABEL_16;
        }
        v19 = v46;
      }
      v46 = v19 + 1;
      v20 = (const WCHAR **)(v45 - 8 + 8 * (v19 + 1));
      if ( v20 )
        *v20 = v18;
      goto LABEL_13;
    }
  }
LABEL_25:
  for ( i = 0; ExtensionIdFromExtensionItem >= 0 && i < a2[1]; ++i )
  {
    string = 0;
    ExtensionIdFromExtensionItem = Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(
                                     *a2 + 8 * i,
                                     &string);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v43 = 0;
      v24 = string;
      v25 = *(__int64 (__fastcall **)(HSTRING, GUID *, struct IExtensionListItem **))(*(_QWORD *)string + 24LL);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v43);
      ExtensionIdFromExtensionItem = v25(v24, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v43);
      v10 = 0;
      if ( ExtensionIdFromExtensionItem >= 0 )
      {
        if ( !a3 )
          goto LABEL_33;
        LODWORD(a7) = 0;
        v51[2] = 0;
        v53 = 0;
        v54 = 0;
        v51[0] = v43;
        v51[1] = a3;
        v51[3] = 0;
        v52 = 0;
        DoesItemMatchCondition = GrepDoesItemMatchCondition((const struct CONDITIONEVALINFO *)v51, (int *)&a7, v26);
        v28 = (int)a7;
        if ( DoesItemMatchCondition < 0 )
          v28 = 0;
        if ( v28 )
        {
LABEL_33:
          a7 = 0;
          ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(
                                           *(struct IExtensionListItem **)(*a2 + 8 * i),
                                           (struct Windows::Internal::String *)&a7);
          if ( ExtensionIdFromExtensionItem >= 0 )
          {
            v44 = WindowsGetStringRawBuffer(a7, 0);
            if ( (int)CTSimpleFixedArray<unsigned short *,CSimpleArrayStandardCompareHelper<unsigned short *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(
                        &v45,
                        v29,
                        &v44,
                        &v49) < 0 )
            {
              v30 = *a2;
              ExtensionIdFromExtensionItem = 0;
              v31 = *(_QWORD *)(a1 + 40);
              if ( v31 != *(_QWORD *)(a1 + 56)
                || (ExtensionIdFromExtensionItem = CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(
                                                     a1 + 32,
                                                     v31 + 1),
                    ExtensionIdFromExtensionItem >= 0) )
              {
                v32 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * (*(_QWORD *)(a1 + 40))++);
                if ( v32 )
                {
                  *v32 = *(_QWORD *)(v30 + 8 * i);
                  Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef();
                }
              }
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&a7);
        }
      }
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v43);
    }
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&string);
  }
LABEL_43:
  if ( v46 )
  {
    do
      CoTaskMemFree(*(LPVOID *)(v45 + 8 * v10++));
    while ( v10 < v46 );
  }
  if ( ExtensionIdFromExtensionItem >= 0 )
  {
    if ( a5 && (v49 = a4, v50 = a5, ExtensionIdFromExtensionItem = 0, v33 = *(_QWORD *)(a1 + 40), v33 > 1) )
    {
      v34 = (LPVOID *)(a1 + 48);
      *(_QWORD *)(a1 + 48) = 0;
      a7 = 0;
      ExtensionIdFromExtensionItem = ULongLongMult(v33 >> 1, 8u, (unsigned __int64 *)&a7);
      if ( ExtensionIdFromExtensionItem >= 0 )
        ExtensionIdFromExtensionItem = CTCoAllocPolicy::Realloc(v36, v35, 0, (unsigned __int64)a7, (void **)(a1 + 48));
      if ( ExtensionIdFromExtensionItem >= 0 )
      {
        CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(
          a1 + 32,
          &v49,
          0,
          *(_QWORD *)(a1 + 40));
        CoTaskMemFree(*v34);
        *v34 = 0;
        goto LABEL_52;
      }
    }
    else
    {
LABEL_52:
      while ( 1 )
      {
        v37 = *(_QWORD *)(a1 + 40);
        if ( v37 <= a6 )
          break;
        v38 = v37 - 1;
        if ( !v37 )
        {
          ExtensionIdFromExtensionItem = -2147316575;
          break;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(*(_QWORD *)(a1 + 32) + 8 * v38);
        v39 = *(_QWORD *)(a1 + 40);
        if ( v38 != v39 - 1 )
          memmove_0(
            (void *)(*(_QWORD *)(a1 + 32) + 8 * v38),
            (const void *)(*(_QWORD *)(a1 + 32) + 8 * v38 + 8),
            8 * (v39 - v38) - 8);
        --*(_QWORD *)(a1 + 40);
        ExtensionIdFromExtensionItem = 0;
      }
    }
  }
  CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(&v45);
  return (unsigned int)ExtensionIdFromExtensionItem;
}

```

## disassembly

```asm
0x18007e8f8  mov     [rsp-8+arg_18], r9
0x18007e8fd  push    rbp
0x18007e8fe  push    rbx
0x18007e8ff  push    rsi
0x18007e900  push    rdi
0x18007e901  push    r12
0x18007e903  push    r13
0x18007e905  push    r14
0x18007e907  push    r15
0x18007e909  lea     rbp, [rsp-7]
0x18007e90e  sub     rsp, 0D8h
0x18007e915  mov     r13, r8
0x18007e918  mov     r12, rdx
0x18007e91b  mov     r14, rcx
0x18007e91e  xor     ebx, ebx
0x18007e920  mov     edi, ebx
0x18007e922  mov     [rsp+110h+var_E0], bl
0x18007e926  mov     [rsp+110h+var_C0], rbx
0x18007e92b  mov     [rbp+3Fh+var_B8], rbx
0x18007e92f  mov     [rbp+3Fh+pv], rbx
0x18007e933  mov     [rbp+3Fh+var_A8], rbx
0x18007e937  mov     r15, [rbp+3Fh+arg_30]
0x18007e93b  test    r15, r15
0x18007e93e  jz      loc_18007EADB
0x18007e944  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18007e947  mov     rax, [r15]
0x18007e94a  lea     rdx, [rbp+3Fh+arg_30]
0x18007e94e  mov     rcx, r15
0x18007e951  mov     rax, [rax+18h]
0x18007e955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e95a  mov     edi, eax
0x18007e95c  test    eax, eax
0x18007e95e  js      loc_18007EADB
0x18007e964  mov     esi, ebx
0x18007e966  cmp     esi, dword ptr [rbp+3Fh+arg_30]
0x18007e969  jnb     loc_18007EA6E
0x18007e96f  mov     [rsp+110h+var_D0], rbx
0x18007e974  mov     rax, [r15]
0x18007e977  mov     rbx, [rax+20h]
0x18007e97b  lea     rcx, [rsp+110h+var_D0]
0x18007e980  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e985  lea     r9, [rsp+110h+var_D0]
0x18007e98a  lea     r8, _GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4
0x18007e991  mov     edx, esi
0x18007e993  mov     rcx, r15
0x18007e996  mov     rax, rbx
0x18007e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e99e  mov     edi, eax
0x18007e9a0  xor     ebx, ebx
0x18007e9a2  test    eax, eax
0x18007e9a4  js      loc_18007EA55
0x18007e9aa  mov     [rsp+110h+string], rbx
0x18007e9af  lea     rdx, [rsp+110h+string]; struct Windows::Internal::String *
0x18007e9b4  mov     rcx, [rsp+110h+var_D0]; struct IExtensionListItem *
0x18007e9b9  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18007e9be  mov     edi, eax
0x18007e9c0  test    eax, eax
0x18007e9c2  js      loc_18007EA4B
0x18007e9c8  mov     [rsp+110h+var_C8], rbx
0x18007e9cd  xor     edx, edx; length
0x18007e9cf  mov     rcx, [rsp+110h+string]; string
0x18007e9d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18007e9da  lea     r9, [rsp+110h+var_C8]
0x18007e9df  mov     r8, rax
0x18007e9e2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18007e9e7  mov     edi, eax
0x18007e9e9  test    eax, eax
0x18007e9eb  js      short loc_18007EA41
0x18007e9ed  mov     edi, ebx
0x18007e9ef  mov     rbx, [rsp+110h+var_C8]
0x18007e9f4  mov     rcx, [rbp+3Fh+var_B8]
0x18007e9f8  cmp     rcx, [rbp+3Fh+var_A8]
0x18007e9fc  jnz     short loc_18007EA16
0x18007e9fe  lea     rdx, [rcx+1]
0x18007ea02  lea     rcx, [rsp+110h+var_C0]
0x18007ea07  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIRunningShareEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIRunningShareEntry@@@@@@QEAAJ_K0@Z; CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007ea0c  mov     edi, eax
0x18007ea0e  test    eax, eax
0x18007ea10  js      short loc_18007EA32
0x18007ea12  mov     rcx, [rbp+3Fh+var_B8]
0x18007ea16  inc     rcx
0x18007ea19  mov     [rbp+3Fh+var_B8], rcx
0x18007ea1d  mov     rdx, [rsp+110h+var_C0]
0x18007ea22  add     rdx, 0FFFFFFFFFFFFFFF8h
0x18007ea26  lea     rdx, [rdx+rcx*8]
0x18007ea2a  test    rdx, rdx
0x18007ea2d  jz      short loc_18007EA32
0x18007ea2f  mov     [rdx], rbx
0x18007ea32  xor     eax, eax
0x18007ea34  test    edi, edi
0x18007ea36  cmovns  rbx, rax
0x18007ea3a  mov     [rsp+110h+var_C8], rbx
0x18007ea3f  xor     ebx, ebx
0x18007ea41  lea     rcx, [rsp+110h+var_C8]
0x18007ea46  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18007ea4b  lea     rcx, [rsp+110h+string]; this
0x18007ea50  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007ea55  lea     rcx, [rsp+110h+var_D0]
0x18007ea5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ea5f  inc     esi
0x18007ea61  test    edi, edi
0x18007ea63  jns     loc_18007E966
0x18007ea69  jmp     loc_18007EC49
0x18007ea6e  mov     edi, ebx
0x18007ea70  mov     rcx, [rbp+3Fh+var_B8]
0x18007ea74  cmp     rcx, 1
0x18007ea78  jbe     short loc_18007EADB
0x18007ea7a  mov     [rbp+3Fh+pv], rbx
0x18007ea7e  mov     [rsp+110h+string], rbx
0x18007ea83  shr     rcx, 1; unsigned __int64
0x18007ea86  lea     r8, [rsp+110h+string]; unsigned __int64 *
0x18007ea8b  mov     edx, 8; unsigned __int64
0x18007ea90  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007ea95  mov     edi, eax
0x18007ea97  test    eax, eax
0x18007ea99  js      short loc_18007EAB3
0x18007ea9b  lea     rax, [rbp+3Fh+pv]
0x18007ea9f  mov     [rsp+110h+var_F0], rax; void **
0x18007eaa4  mov     r9, [rsp+110h+string]; unsigned __int64
0x18007eaa9  xor     r8d, r8d; void *
0x18007eaac  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18007eab1  mov     edi, eax
0x18007eab3  test    edi, edi
0x18007eab5  js      short loc_18007EADB
0x18007eab7  mov     r9, [rbp+3Fh+var_B8]
0x18007eabb  xor     r8d, r8d
0x18007eabe  lea     rdx, [rsp+110h+var_E0]
0x18007eac3  lea     rcx, [rsp+110h+var_C0]
0x18007eac8  call    ??$_MergeSort@VPWSTRCompare@CExtensionList@@@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXAEBVPWSTRCompare@CExtensionList@@_K1@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_MergeSort<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,unsigned __int64,unsigned __int64)
0x18007eacd  mov     rcx, [rbp+3Fh+pv]; pv
0x18007ead1  call    cs:__imp_CoTaskMemFree
0x18007ead7  mov     [rbp+3Fh+pv], rbx
0x18007eadb  mov     rsi, rbx
0x18007eade  jmp     loc_18007EC41
0x18007eae3  cmp     rsi, [r12+8]
0x18007eae8  jnb     loc_18007EC49
0x18007eaee  mov     [rsp+110h+string], rbx
0x18007eaf3  mov     rax, [r12]
0x18007eaf7  lea     rcx, [rax+rsi*8]
0x18007eafb  lea     rdx, [rsp+110h+string]
0x18007eb00  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x18007eb05  mov     edi, eax
0x18007eb07  test    eax, eax
0x18007eb09  js      loc_18007EC34
0x18007eb0f  mov     [rsp+110h+var_D0], rbx
0x18007eb14  mov     rdi, [rsp+110h+string]
0x18007eb19  mov     rax, [rdi]
0x18007eb1c  mov     rbx, [rax+18h]
0x18007eb20  lea     rcx, [rsp+110h+var_D0]
0x18007eb25  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007eb2a  lea     r8, [rsp+110h+var_D0]
0x18007eb2f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18007eb36  mov     rcx, rdi
0x18007eb39  mov     rax, rbx
0x18007eb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb41  mov     edi, eax
0x18007eb43  xor     ebx, ebx
0x18007eb45  test    eax, eax
0x18007eb47  js      loc_18007EC2A
0x18007eb4d  test    r13, r13
0x18007eb50  jz      short loc_18007EB98
0x18007eb52  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18007eb55  mov     [rbp+3Fh+var_80], rbx
0x18007eb59  xorps   xmm0, xmm0
0x18007eb5c  movdqa  [rbp+3Fh+var_60], xmm0
0x18007eb61  mov     [rbp+3Fh+var_50], rbx
0x18007eb65  mov     rax, [rsp+110h+var_D0]
0x18007eb6a  mov     [rbp+3Fh+var_90], rax
0x18007eb6e  mov     [rbp+3Fh+var_88], r13
0x18007eb72  mov     [rbp+3Fh+var_78], rbx
0x18007eb76  movdqa  [rbp+3Fh+var_70], xmm0
0x18007eb7b  lea     rdx, [rbp+3Fh+arg_30]; int *
0x18007eb7f  lea     rcx, [rbp+3Fh+var_90]; struct CONDITIONEVALINFO *
0x18007eb83  call    ?GrepDoesItemMatchCondition@@YAJPEBUCONDITIONEVALINFO@@PEAHPEAUCONDITIONEVALPROPS@@@Z; GrepDoesItemMatchCondition(CONDITIONEVALINFO const *,int *,CONDITIONEVALPROPS *)
0x18007eb88  mov     edx, dword ptr [rbp+3Fh+arg_30]
0x18007eb8b  test    eax, eax
0x18007eb8d  cmovs   edx, ebx
0x18007eb90  test    edx, edx
0x18007eb92  jz      loc_18007EC2A
0x18007eb98  mov     [rbp+3Fh+arg_30], rbx
0x18007eb9c  mov     rcx, [r12]
0x18007eba0  lea     rdx, [rbp+3Fh+arg_30]; struct Windows::Internal::String *
0x18007eba4  mov     rcx, [rcx+rsi*8]; struct IExtensionListItem *
0x18007eba8  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18007ebad  mov     edi, eax
0x18007ebaf  test    eax, eax
0x18007ebb1  js      short loc_18007EC21
0x18007ebb3  xor     edx, edx; length
0x18007ebb5  mov     rcx, [rbp+3Fh+arg_30]; string
0x18007ebb9  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ebbf  mov     [rsp+110h+var_C8], rax
0x18007ebc4  lea     r9, [rbp+3Fh+var_A0]
0x18007ebc8  lea     r8, [rsp+110h+var_C8]
0x18007ebcd  lea     rcx, [rsp+110h+var_C0]
0x18007ebd2  call    ??$BinarySearchEx@VPWSTRCompare@CExtensionList@@@?$CTSimpleFixedArray@PEAGV?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEBAJAEBVPWSTRCompare@CExtensionList@@AEBQEAGPEA_K@Z; CTSimpleFixedArray<ushort *,CSimpleArrayStandardCompareHelper<ushort *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,ushort * const &,unsigned __int64 *)
0x18007ebd7  test    eax, eax
0x18007ebd9  jns     short loc_18007EC21
0x18007ebdb  mov     r15, [r12]
0x18007ebdf  xor     edi, edi
0x18007ebe1  mov     rdx, [r14+28h]
0x18007ebe5  cmp     rdx, [r14+38h]
0x18007ebe9  jnz     short loc_18007EBFD
0x18007ebeb  inc     rdx
0x18007ebee  lea     rcx, [r14+20h]
0x18007ebf2  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIRunningShareEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIRunningShareEntry@@@@@@QEAAJ_K0@Z; CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007ebf7  mov     edi, eax
0x18007ebf9  test    eax, eax
0x18007ebfb  js      short loc_18007EC21
0x18007ebfd  inc     qword ptr [r14+28h]
0x18007ec01  mov     rcx, [r14+28h]
0x18007ec05  mov     rax, [r14+20h]
0x18007ec09  dec     rcx
0x18007ec0c  lea     rcx, [rax+rcx*8]
0x18007ec10  test    rcx, rcx
0x18007ec13  jz      short loc_18007EC21
0x18007ec15  mov     rax, [r15+rsi*8]
0x18007ec19  mov     [rcx], rax
0x18007ec1c  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18007ec21  lea     rcx, [rbp+3Fh+arg_30]; this
0x18007ec25  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007ec2a  lea     rcx, [rsp+110h+var_D0]
0x18007ec2f  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007ec34  lea     rcx, [rsp+110h+string]
0x18007ec39  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007ec3e  inc     rsi
0x18007ec41  test    edi, edi
0x18007ec43  jns     loc_18007EAE3
0x18007ec49  xor     r15d, r15d
0x18007ec4c  cmp     [rbp+3Fh+var_B8], r15
0x18007ec50  jbe     short loc_18007EC6A
0x18007ec52  mov     rcx, [rsp+110h+var_C0]
0x18007ec57  mov     rcx, [rcx+rbx*8]; pv
0x18007ec5b  call    cs:__imp_CoTaskMemFree
0x18007ec61  inc     rbx
0x18007ec64  cmp     rbx, [rbp+3Fh+var_B8]
0x18007ec68  jb      short loc_18007EC52
0x18007ec6a  test    edi, edi
0x18007ec6c  js      loc_18007ED47
0x18007ec72  mov     eax, [rbp+3Fh+arg_20]
0x18007ec75  test    eax, eax
0x18007ec77  jz      short loc_18007ECEE
0x18007ec79  mov     rcx, [rbp+3Fh+arg_18]
0x18007ec7d  mov     [rbp+3Fh+var_A0], rcx
0x18007ec81  mov     [rbp+3Fh+var_98], eax
0x18007ec84  mov     edi, r15d
0x18007ec87  mov     rcx, [r14+28h]
0x18007ec8b  cmp     rcx, 1
0x18007ec8f  jbe     short loc_18007ECEA
0x18007ec91  lea     rsi, [r14+30h]
0x18007ec95  mov     [rsi], r15
0x18007ec98  mov     [rbp+3Fh+arg_30], r15
0x18007ec9c  shr     rcx, 1; unsigned __int64
0x18007ec9f  lea     r8, [rbp+3Fh+arg_30]; unsigned __int64 *
0x18007eca3  mov     edx, 8; unsigned __int64
0x18007eca8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007ecad  mov     edi, eax
0x18007ecaf  test    eax, eax
0x18007ecb1  js      short loc_18007ECC6
0x18007ecb3  mov     [rsp+110h+var_F0], rsi; void **
0x18007ecb8  mov     r9, [rbp+3Fh+arg_30]; unsigned __int64
0x18007ecbc  xor     r8d, r8d; void *
0x18007ecbf  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18007ecc4  mov     edi, eax
0x18007ecc6  test    edi, edi
0x18007ecc8  js      short loc_18007ED47
0x18007ecca  mov     r9, [r14+28h]
0x18007ecce  xor     r8d, r8d
0x18007ecd1  lea     rdx, [rbp+3Fh+var_A0]
0x18007ecd5  lea     rcx, [r14+20h]
0x18007ecd9  call    ??$_MergeSort@VExtensionCompare@CExtensionList@@@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXAEBVExtensionCompare@CExtensionList@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(CExtensionList::ExtensionCompare const &,unsigned __int64,unsigned __int64)
0x18007ecde  mov     rcx, [rsi]; pv
0x18007ece1  call    cs:__imp_CoTaskMemFree
0x18007ece7  mov     [rsi], r15
0x18007ecea  test    edi, edi
0x18007ecec  js      short loc_18007ED47
0x18007ecee  mov     esi, [rbp+3Fh+arg_28]
0x18007ecf1  mov     rax, [r14+28h]
0x18007ecf5  cmp     rax, rsi
0x18007ecf8  jbe     short loc_18007ED47
0x18007ecfa  lea     rbx, [rax-1]
0x18007ecfe  cmp     rbx, rax
0x18007ed01  jnb     short loc_18007ED42
0x18007ed03  mov     rax, [r14+20h]
0x18007ed07  lea     rcx, [rax+rbx*8]
0x18007ed0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed10  mov     r8, [r14+28h]
0x18007ed14  lea     rax, [r8-1]
0x18007ed18  cmp     rbx, rax
0x18007ed1b  jz      short loc_18007ED39
0x18007ed1d  mov     rax, [r14+20h]
0x18007ed21  lea     rcx, [rax+rbx*8]; void *
0x18007ed25  sub     r8, rbx
0x18007ed28  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x18007ed30  lea     rdx, [rcx+8]; Src
0x18007ed34  call    memmove_0
0x18007ed39  dec     qword ptr [r14+28h]
0x18007ed3d  mov     edi, r15d
0x18007ed40  jmp     short loc_18007ECF1
0x18007ed42  mov     edi, 80028CA1h
0x18007ed47  lea     rcx, [rsp+110h+var_C0]
  ... truncated ...
```
