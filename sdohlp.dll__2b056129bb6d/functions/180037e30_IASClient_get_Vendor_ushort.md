# IASClient::get_Vendor(ushort * *)

- ea: `0x180037e30`
- end: `0x18003828f`
- name: `?get_Vendor@IASClient@@UEAAJPEAPEAG@Z`
- size: `1119`
- prototype: `__int64 __fastcall(IASClient *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cd00`
- `0x18002ee50`
- `0x18002f240`
- `0x18002f7fc`
- `0x180037e30`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800380ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800380ca`

## string_xrefs

- `0x180037f69`: `IASSDOCreateItem(IASSERVICE) failed with 0x%x`
- `0x180037fd9`: `pItem->QI(IID_IIASService) failed with 0x%x`
- `0x180038040`: `pService->get_ClientVendorCollection failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASClient::get_Vendor(IASClient *this, unsigned __int16 **a2)
{
  int Property; // ebx
  int v6; // edx
  struct ISdo *v7; // rdx
  int v8; // eax
  char v9; // bl
  int v10; // edx
  char v11; // bl
  __int64 v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v16; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v15 = 0;
  v13 = 0;
  v12 = 0;
  v17 = 0;
  v16 = 0;
  Property = IASItem::GetProperty((IASClient *)((char *)this + 16), 0x403u, &v15);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_47;
    }
    WppDbgPrint("GetProperty(PROPERTY_CLIENT_NAS_MANUFACTURER) failed with 0x%x");
    v6 = 10;
    goto LABEL_8;
  }
  v7 = (struct ISdo *)*((_QWORD *)this + 15);
  if ( !v7 )
    v7 = (struct ISdo *)*((_QWORD *)this + 5);
  v8 = IASSDOCreateItem(
         1,
         v7,
         v7,
         *((struct ISdoMachine **)this + 6),
         *((struct ISdoDictionaryOld **)this + 7),
         (__int64)&v16);
  v9 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("IASSDOCreateItem(IASSERVICE) failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
      (unsigned int)"NPSSDO",
      v9);
  }
  Property = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IIASService, &v13);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_47;
    }
    WppDbgPrint("pItem->QI(IID_IIASService) failed with 0x%x");
    v6 = 12;
    goto LABEL_8;
  }
  ATL::CComPtrBase<IIASItem>::Release(&v16);
  Property = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 256LL))(v13, &v12);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_47;
    }
    WppDbgPrint("pService->get_ClientVendorCollection failed with 0x%x");
    v6 = 13;
    goto LABEL_8;
  }
  Property = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 80LL))(v12, &v17);
  if ( Property >= 0 )
  {
    while ( 1 )
    {
      Property = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 64LL))(v17, &v16);
      if ( Property )
        break;
      VariantInit(&pvarg);
      Property = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v16 + 56LL))(v16, 1024, &pvarg);
      if ( Property < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pItem->GetProperty(PROPERTY_NAS_VENDOR_ID) failed with 0x%x");
          v10 = 15;
LABEL_52:
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
            (unsigned int)"NPSSDO",
            Property);
        }
LABEL_53:
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        goto LABEL_47;
      }
      if ( v15 == pvarg.lVal )
      {
        Property = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v16 + 96LL))(v16, a2);
        if ( Property < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pItem->get_Name failed with 0x%x\n");
            v10 = 16;
            goto LABEL_52;
          }
          goto LABEL_53;
        }
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        goto LABEL_41;
      }
      ATL::CComPtrBase<IIASItem>::Release(&v16);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
    }
    if ( Property >= 0 )
    {
LABEL_41:
      if ( !*a2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          v11 = v15;
          WppDbgPrint("No matching vendor found from collection for %d");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
            (unsigned int)"NPSSDO",
            v11);
        }
        Property = -2147418113;
      }
      goto LABEL_47;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pEnum->GetNextItem failed with 0x%x");
      v6 = 17;
      goto LABEL_8;
    }
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pVendors->get_Enumerator returned 0x%x");
    v6 = 14;
LABEL_8:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
      (unsigned int)"NPSSDO",
      Property);
  }
LABEL_47:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180037e30  mov     [rsp-38h+arg_0], rbx
0x180037e35  push    rbp
0x180037e36  push    rsi
0x180037e37  push    rdi
0x180037e38  push    r12
0x180037e3a  push    r13
0x180037e3c  push    r14
0x180037e3e  push    r15
0x180037e40  mov     rbp, rsp
0x180037e43  sub     rsp, 60h
0x180037e47  xor     esi, esi
0x180037e49  mov     r13, rdx
0x180037e4c  mov     rdi, rcx
0x180037e4f  test    rdx, rdx
0x180037e52  jnz     short loc_180037E5E
0x180037e54  mov     eax, 80004003h
0x180037e59  jmp     loc_1800381E2
0x180037e5e  mov     [rdx], rsi
0x180037e61  lea     r8, [rbp+arg_8]; unsigned int *
0x180037e65  mov     edx, 403h; unsigned int
0x180037e6a  mov     [rbp+arg_8], esi
0x180037e6d  add     rcx, 10h; this
0x180037e71  mov     [rbp+var_28], rsi
0x180037e75  mov     [rbp+var_30], rsi
0x180037e79  mov     [rbp+arg_18], rsi
0x180037e7d  mov     [rbp+arg_10], rsi
0x180037e81  call    ?GetProperty@IASItem@@IEAAJKPEAK@Z; IASItem::GetProperty(ulong,ulong *)
0x180037e86  mov     ebx, eax
0x180037e88  test    eax, eax
0x180037e8a  jns     short loc_180037EF8
0x180037e8c  mov     rax, cs:WPP_GLOBAL_Control
0x180037e93  lea     r14, WPP_GLOBAL_Control
0x180037e9a  cmp     rax, r14
0x180037e9d  jz      loc_1800381BC
0x180037ea3  mov     dil, 2
0x180037ea6  cmp     [rax+19h], dil
0x180037eaa  jb      loc_1800381BC
0x180037eb0  mov     esi, 400h
0x180037eb5  test    [rax+1Ch], esi
0x180037eb8  jz      loc_1800381BC
0x180037ebe  mov     edx, ebx
0x180037ec0  lea     rcx, aGetpropertyPro_1; "GetProperty(PROPERTY_CLIENT_NAS_MANUFAC"...
0x180037ec7  call    WppDbgPrint
0x180037ecc  mov     edx, 0Ah
0x180037ed1  lea     r9, aNpssdo; "NPSSDO"
0x180037ed8  lea     r8, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x180037edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ee6  mov     dword ptr [rsp+60h+var_40], ebx
0x180037eea  mov     rcx, [rcx+10h]
0x180037eee  call    WPP_SF_sd
0x180037ef3  jmp     loc_1800381BC
0x180037ef8  mov     rdx, [rdi+78h]
0x180037efc  test    rdx, rdx
0x180037eff  setnz   al
0x180037f02  test    al, al
0x180037f04  jnz     short loc_180037F0A
0x180037f06  mov     rdx, [rdi+28h]
0x180037f0a  mov     r9, [rdi+30h]
0x180037f0e  lea     rax, [rbp+arg_10]
0x180037f12  mov     [rsp+60h+var_38], rax
0x180037f17  mov     r8, rdx
0x180037f1a  mov     rax, [rdi+38h]
0x180037f1e  mov     ecx, 1
0x180037f23  mov     [rsp+60h+var_40], rax
0x180037f28  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x180037f2d  lea     r15, aNpssdo; "NPSSDO"
0x180037f34  mov     ebx, eax
0x180037f36  lea     r12, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x180037f3d  mov     esi, 400h
0x180037f42  lea     r14, WPP_GLOBAL_Control
0x180037f49  mov     dil, 2
0x180037f4c  test    eax, eax
0x180037f4e  jns     short loc_180037F94
0x180037f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f57  cmp     rcx, r14
0x180037f5a  jz      short loc_180037F94
0x180037f5c  cmp     [rcx+19h], dil
0x180037f60  jb      short loc_180037F94
0x180037f62  test    [rcx+1Ch], esi
0x180037f65  jz      short loc_180037F94
0x180037f67  mov     edx, eax
0x180037f69  lea     rcx, aIassdocreateit; "IASSDOCreateItem(IASSERVICE) failed wit"...
0x180037f70  call    WppDbgPrint
0x180037f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f7c  mov     edx, 0Bh
0x180037f81  mov     r9, r15
0x180037f84  mov     dword ptr [rsp+60h+var_40], ebx
0x180037f88  mov     r8, r12
0x180037f8b  mov     rcx, [rcx+10h]
0x180037f8f  call    WPP_SF_sd
0x180037f94  mov     rcx, [rbp+arg_10]
0x180037f98  lea     r8, [rbp+var_28]
0x180037f9c  lea     rdx, IID_IIASService
0x180037fa3  mov     rax, [rcx]
0x180037fa6  mov     rax, [rax]
0x180037fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fae  mov     ebx, eax
0x180037fb0  test    eax, eax
0x180037fb2  jns     short loc_180037FF5
0x180037fb4  mov     rax, cs:WPP_GLOBAL_Control
0x180037fbb  cmp     rax, r14
0x180037fbe  jz      loc_1800381BC
0x180037fc4  cmp     [rax+19h], dil
0x180037fc8  jb      loc_1800381BC
0x180037fce  test    [rax+1Ch], esi
0x180037fd1  jz      loc_1800381BC
0x180037fd7  mov     edx, ebx
0x180037fd9  lea     rcx, aPitemQiIidIias_0; "pItem->QI(IID_IIASService) failed with "...
0x180037fe0  call    WppDbgPrint
0x180037fe5  mov     edx, 0Ch
0x180037fea  mov     r9, r15
0x180037fed  mov     r8, r12
0x180037ff0  jmp     loc_180037EDF
0x180037ff5  lea     rcx, [rbp+arg_10]
0x180037ff9  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180037ffe  mov     rcx, [rbp+var_28]
0x180038002  lea     rdx, [rbp+var_30]
0x180038006  mov     rax, [rcx]
0x180038009  mov     rax, [rax+100h]
0x180038010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038015  mov     ebx, eax
0x180038017  test    eax, eax
0x180038019  jns     short loc_180038053
0x18003801b  mov     rax, cs:WPP_GLOBAL_Control
0x180038022  cmp     rax, r14
0x180038025  jz      loc_1800381BC
0x18003802b  cmp     [rax+19h], dil
0x18003802f  jb      loc_1800381BC
0x180038035  test    [rax+1Ch], esi
0x180038038  jz      loc_1800381BC
0x18003803e  mov     edx, ebx
0x180038040  lea     rcx, aPserviceGetCli; "pService->get_ClientVendorCollection fa"...
0x180038047  call    WppDbgPrint
0x18003804c  mov     edx, 0Dh
0x180038051  jmp     short loc_180037FEA
0x180038053  mov     rcx, [rbp+var_30]
0x180038057  lea     rdx, [rbp+arg_18]
0x18003805b  mov     rax, [rcx]
0x18003805e  mov     rax, [rax+50h]
0x180038062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038067  mov     ebx, eax
0x180038069  test    eax, eax
0x18003806b  jns     short loc_1800380A8
0x18003806d  mov     rax, cs:WPP_GLOBAL_Control
0x180038074  cmp     rax, r14
0x180038077  jz      loc_1800381BC
0x18003807d  cmp     [rax+19h], dil
0x180038081  jb      loc_1800381BC
0x180038087  test    [rax+1Ch], esi
0x18003808a  jz      loc_1800381BC
0x180038090  mov     edx, ebx
0x180038092  lea     rcx, aPvendorsGetEnu; "pVendors->get_Enumerator returned 0x%x"
0x180038099  call    WppDbgPrint
0x18003809e  mov     edx, 0Eh
0x1800380a3  jmp     loc_180037FEA
0x1800380a8  mov     rcx, [rbp+arg_18]
0x1800380ac  lea     rdx, [rbp+arg_10]
0x1800380b0  mov     rax, [rcx]
0x1800380b3  mov     rax, [rax+40h]
0x1800380b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380bc  mov     ebx, eax
0x1800380be  test    eax, eax
0x1800380c0  jnz     loc_18003824C
0x1800380c6  lea     rcx, [rbp+pvarg]; pvarg
0x1800380ca  call    cs:__imp_VariantInit
0x1800380d0  mov     rcx, [rbp+arg_10]
0x1800380d4  lea     r8, [rbp+pvarg]
0x1800380d8  mov     edx, esi
0x1800380da  mov     rax, [rcx]
0x1800380dd  mov     rax, [rax+38h]
0x1800380e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380e6  mov     ebx, eax
0x1800380e8  test    eax, eax
0x1800380ea  js      loc_1800381FA
0x1800380f0  mov     eax, [rbp+arg_8]
0x1800380f3  cmp     eax, dword ptr [rbp+pvarg+8]
0x1800380f6  jz      short loc_18003810C
0x1800380f8  lea     rcx, [rbp+arg_10]
0x1800380fc  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180038101  lea     rcx, [rbp+pvarg]; this
0x180038105  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003810a  jmp     short loc_1800380A8
0x18003810c  mov     rcx, [rbp+arg_10]
0x180038110  mov     rdx, r13
0x180038113  mov     rax, [rcx]
0x180038116  mov     rax, [rax+60h]
0x18003811a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003811f  mov     ebx, eax
0x180038121  test    eax, eax
0x180038123  jns     short loc_180038160
0x180038125  mov     rax, cs:WPP_GLOBAL_Control
0x18003812c  cmp     rax, r14
0x18003812f  jz      loc_18003823E
0x180038135  cmp     [rax+19h], dil
0x180038139  jb      loc_18003823E
0x18003813f  test    [rax+1Ch], esi
0x180038142  jz      loc_18003823E
0x180038148  mov     edx, ebx
0x18003814a  lea     rcx, aPitemGetNameFa; "pItem->get_Name failed with 0x%x\n"
0x180038151  call    WppDbgPrint
0x180038156  mov     edx, 10h
0x18003815b  jmp     loc_180038224
0x180038160  lea     rcx, [rbp+pvarg]; this
0x180038164  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180038169  cmp     qword ptr [r13+0], 0
0x18003816e  jnz     short loc_1800381BC
0x180038170  mov     rax, cs:WPP_GLOBAL_Control
0x180038177  cmp     rax, r14
0x18003817a  jz      short loc_1800381B7
0x18003817c  cmp     [rax+19h], dil
0x180038180  jb      short loc_1800381B7
0x180038182  test    [rax+1Ch], esi
0x180038185  jz      short loc_1800381B7
0x180038187  mov     ebx, [rbp+arg_8]
0x18003818a  lea     rcx, aNoMatchingVend; "No matching vendor found from collectio"...
0x180038191  mov     edx, ebx
0x180038193  call    WppDbgPrint
0x180038198  mov     rcx, cs:WPP_GLOBAL_Control
0x18003819f  mov     edx, 12h
0x1800381a4  mov     r9, r15
0x1800381a7  mov     dword ptr [rsp+60h+var_40], ebx
0x1800381ab  mov     r8, r12
0x1800381ae  mov     rcx, [rcx+10h]
0x1800381b2  call    WPP_SF_sd
0x1800381b7  mov     ebx, 8000FFFFh
0x1800381bc  lea     rcx, [rbp+arg_10]
0x1800381c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800381c5  lea     rcx, [rbp+arg_18]
0x1800381c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800381ce  lea     rcx, [rbp+var_30]
0x1800381d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800381d7  lea     rcx, [rbp+var_28]
0x1800381db  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800381e0  mov     eax, ebx
0x1800381e2  mov     rbx, [rsp+60h+arg_0]
0x1800381ea  add     rsp, 60h
0x1800381ee  pop     r15
0x1800381f0  pop     r14
0x1800381f2  pop     r13
0x1800381f4  pop     r12
0x1800381f6  pop     rdi
0x1800381f7  pop     rsi
0x1800381f8  pop     rbp
0x1800381f9  retn
0x1800381fa  mov     rax, cs:WPP_GLOBAL_Control
0x180038201  cmp     rax, r14
0x180038204  jz      short loc_18003823E
0x180038206  cmp     [rax+19h], dil
0x18003820a  jb      short loc_18003823E
0x18003820c  test    [rax+1Ch], esi
0x18003820f  jz      short loc_18003823E
0x180038211  mov     edx, ebx
0x180038213  lea     rcx, aPitemGetproper; "pItem->GetProperty(PROPERTY_NAS_VENDOR_"...
0x18003821a  call    WppDbgPrint
0x18003821f  mov     edx, 0Fh
0x180038224  mov     rcx, cs:WPP_GLOBAL_Control
0x18003822b  mov     r9, r15
0x18003822e  mov     r8, r12
0x180038231  mov     dword ptr [rsp+60h+var_40], ebx
0x180038235  mov     rcx, [rcx+10h]
0x180038239  call    WPP_SF_sd
0x18003823e  lea     rcx, [rbp+pvarg]; this
0x180038242  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180038247  jmp     loc_1800381BC
0x18003824c  test    ebx, ebx
0x18003824e  jns     loc_180038169
0x180038254  mov     rax, cs:WPP_GLOBAL_Control
0x18003825b  cmp     rax, r14
0x18003825e  jz      loc_1800381BC
0x180038264  cmp     [rax+19h], dil
0x180038268  jb      loc_1800381BC
0x18003826e  test    [rax+1Ch], esi
0x180038271  jz      loc_1800381BC
0x180038277  mov     edx, ebx
0x180038279  lea     rcx, aPenumGetnextit_0; "pEnum->GetNextItem failed with 0x%x"
0x180038280  call    WppDbgPrint
0x180038285  mov     edx, 11h
0x18003828a  jmp     loc_180037FEA
```
