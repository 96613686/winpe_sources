# IASClient::put_Vendor(ushort *)

- ea: `0x180038320`
- end: `0x180038723`
- name: `?put_Vendor@IASClient@@UEAAJPEAG@Z`
- size: `1027`
- prototype: `int(IASClient *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cd00`
- `0x18002cd74`
- `0x18002ee50`
- `0x18002f240`
- `0x18002faa0`
- `0x180038320`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180038571`
- `msvcrt!_wcsicmp` at `0x180038571`
- `OLEAUT32!__imp_SysFreeString` at `0x180038588`
- `OLEAUT32!__imp_SysFreeString` at `0x180038611`
- `OLEAUT32!__imp_SysFreeString` at `0x180038588`
- `OLEAUT32!__imp_SysFreeString` at `0x180038611`
- `OLEAUT32!__imp_VariantInit` at `0x180038594`
- `OLEAUT32!__imp_VariantInit` at `0x180038594`

## string_xrefs

- `0x1800383ca`: `IASSDOCreateItem(IASSERVICE) failed with 0x%x`
- `0x180038443`: `pItem->QI(IID_IIASService) failed with 0x%x`
- `0x1800384be`: `pService->get_ClientVendorCollection failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASClient::put_Vendor(IASClient *this, unsigned __int16 *a2)
{
  struct ISdo *v5; // rdx
  int v6; // eax
  char v7; // bl
  int v8; // ebx
  int v9; // edx
  int v10; // edx
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+98h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+48h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct ISdo *)*((_QWORD *)this + 15);
  v12 = 0;
  v11 = 0;
  v16 = 0;
  v14 = 0;
  if ( !v5 )
    v5 = (struct ISdo *)*((_QWORD *)this + 5);
  v6 = IASSDOCreateItem(
         1,
         v5,
         v5,
         *((struct ISdoMachine **)this + 6),
         *((struct ISdoDictionaryOld **)this + 7),
         (__int64)&v14);
  v7 = v6;
  if ( v6 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("IASSDOCreateItem(IASSERVICE) failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
      (unsigned int)"NPSSDO",
      v7);
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_IIASService, &v12);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_52;
    }
    WppDbgPrint("pItem->QI(IID_IIASService) failed with 0x%x");
    v9 = 20;
    goto LABEL_15;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 256LL))(v12, &v11);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_52;
    }
    WppDbgPrint("pService->get_ClientVendorCollection failed with 0x%x");
    v9 = 21;
    goto LABEL_15;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 80LL))(v11, &v16);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_52;
    }
    WppDbgPrint("pVendors->get_Enumerator returned 0x%x");
    v9 = 22;
    goto LABEL_15;
  }
  ATL::CComPtrBase<IIASItem>::Release(&v14);
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v14);
    if ( v8 )
      break;
    String1 = 0;
    (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v14 + 96LL))(v14, &String1);
    if ( !_wcsicmp(String1, a2) )
    {
      VariantInit(&pvarg);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v14 + 56LL))(v14, 1024, &pvarg);
      if ( v8 >= 0 )
      {
        v8 = IASItem::PutProperty((IASClient *)((char *)this + 16), 0x403u, pvarg.cyVal.Lo);
        if ( v8 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("IASItem::PutProperty() returned 0x%x");
          v10 = 24;
LABEL_35:
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
            (unsigned int)"NPSSDO",
            v8);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pItem->GetProperty(PROPERTY_NAS_VENDOR_ID) failed with 0x%x");
        v10 = 23;
        goto LABEL_35;
      }
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      SysFreeString(String1);
      goto LABEL_52;
    }
    ATL::CComPtrBase<IIASItem>::Release(&v14);
    SysFreeString(String1);
  }
  if ( v8 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("No matching vendor found from collection for %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)a2);
    }
    v8 = -2147418113;
    goto LABEL_52;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pEnum->GetNextItem failed with 0x%x");
    v9 = 25;
LABEL_15:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids,
      (unsigned int)"NPSSDO",
      v8);
  }
LABEL_52:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038320  mov     [rsp-28h+arg_0], rbx
0x180038325  push    rbp
0x180038326  push    rsi
0x180038327  push    rdi
0x180038328  push    r13
0x18003832a  push    r15
0x18003832c  mov     rbp, rsp
0x18003832f  sub     rsp, 60h
0x180038333  mov     rsi, rdx
0x180038336  mov     rdi, rcx
0x180038339  test    rdx, rdx
0x18003833c  jnz     short loc_180038348
0x18003833e  mov     eax, 80070057h
0x180038343  jmp     loc_18003870F
0x180038348  mov     rdx, [rcx+78h]
0x18003834c  test    rdx, rdx
0x18003834f  mov     [rbp+var_28], 0
0x180038357  mov     [rbp+var_30], 0
0x18003835f  setnz   al
0x180038362  mov     [rbp+arg_18], 0
0x18003836a  mov     [rbp+arg_8], 0
0x180038372  test    al, al
0x180038374  jnz     short loc_18003837A
0x180038376  mov     rdx, [rcx+28h]
0x18003837a  mov     r9, [rcx+30h]
0x18003837e  lea     rax, [rbp+arg_8]
0x180038382  mov     [rsp+60h+var_38], rax
0x180038387  mov     r8, rdx
0x18003838a  mov     rax, [rcx+38h]
0x18003838e  mov     ecx, 1
0x180038393  mov     [rsp+60h+var_40], rax
0x180038398  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x18003839d  lea     r13, WPP_GLOBAL_Control
0x1800383a4  mov     ebx, eax
0x1800383a6  mov     r15d, 400h
0x1800383ac  test    eax, eax
0x1800383ae  jns     short loc_1800383FD
0x1800383b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383b7  cmp     rcx, r13
0x1800383ba  jz      short loc_1800383FD
0x1800383bc  cmp     byte ptr [rcx+19h], 2
0x1800383c0  jb      short loc_1800383FD
0x1800383c2  test    [rcx+1Ch], r15d
0x1800383c6  jz      short loc_1800383FD
0x1800383c8  mov     edx, eax
0x1800383ca  lea     rcx, aIassdocreateit; "IASSDOCreateItem(IASSERVICE) failed wit"...
0x1800383d1  call    WppDbgPrint
0x1800383d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383dd  lea     r9, aNpssdo; "NPSSDO"
0x1800383e4  mov     edx, 13h
0x1800383e9  mov     dword ptr [rsp+60h+var_40], ebx
0x1800383ed  lea     r8, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x1800383f4  mov     rcx, [rcx+10h]
0x1800383f8  call    WPP_SF_sd
0x1800383fd  mov     rcx, [rbp+arg_8]
0x180038401  lea     r8, [rbp+var_28]
0x180038405  lea     rdx, IID_IIASService
0x18003840c  mov     rax, [rcx]
0x18003840f  mov     rax, [rax]
0x180038412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038417  mov     ebx, eax
0x180038419  test    eax, eax
0x18003841b  jns     short loc_18003847B
0x18003841d  mov     rax, cs:WPP_GLOBAL_Control
0x180038424  cmp     rax, r13
0x180038427  jz      loc_1800386E9
0x18003842d  cmp     byte ptr [rax+19h], 2
0x180038431  jb      loc_1800386E9
0x180038437  test    [rax+1Ch], r15d
0x18003843b  jz      loc_1800386E9
0x180038441  mov     edx, ebx
0x180038443  lea     rcx, aPitemQiIidIias_0; "pItem->QI(IID_IIASService) failed with "...
0x18003844a  call    WppDbgPrint
0x18003844f  mov     edx, 14h
0x180038454  mov     rcx, cs:WPP_GLOBAL_Control
0x18003845b  lea     r9, aNpssdo; "NPSSDO"
0x180038462  lea     r8, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x180038469  mov     dword ptr [rsp+60h+var_40], ebx
0x18003846d  mov     rcx, [rcx+10h]
0x180038471  call    WPP_SF_sd
0x180038476  jmp     loc_1800386E9
0x18003847b  mov     rcx, [rbp+var_28]
0x18003847f  lea     rdx, [rbp+var_30]
0x180038483  mov     rax, [rcx]
0x180038486  mov     rax, [rax+100h]
0x18003848d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038492  mov     ebx, eax
0x180038494  test    eax, eax
0x180038496  jns     short loc_1800384D1
0x180038498  mov     rax, cs:WPP_GLOBAL_Control
0x18003849f  cmp     rax, r13
0x1800384a2  jz      loc_1800386E9
0x1800384a8  cmp     byte ptr [rax+19h], 2
0x1800384ac  jb      loc_1800386E9
0x1800384b2  test    [rax+1Ch], r15d
0x1800384b6  jz      loc_1800386E9
0x1800384bc  mov     edx, ebx
0x1800384be  lea     rcx, aPserviceGetCli; "pService->get_ClientVendorCollection fa"...
0x1800384c5  call    WppDbgPrint
0x1800384ca  mov     edx, 15h
0x1800384cf  jmp     short loc_180038454
0x1800384d1  mov     rcx, [rbp+var_30]
0x1800384d5  lea     rdx, [rbp+arg_18]
0x1800384d9  mov     rax, [rcx]
0x1800384dc  mov     rax, [rax+50h]
0x1800384e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384e5  mov     ebx, eax
0x1800384e7  test    eax, eax
0x1800384e9  jns     short loc_180038527
0x1800384eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800384f2  cmp     rax, r13
0x1800384f5  jz      loc_1800386E9
0x1800384fb  cmp     byte ptr [rax+19h], 2
0x1800384ff  jb      loc_1800386E9
0x180038505  test    [rax+1Ch], r15d
0x180038509  jz      loc_1800386E9
0x18003850f  mov     edx, ebx
0x180038511  lea     rcx, aPvendorsGetEnu; "pVendors->get_Enumerator returned 0x%x"
0x180038518  call    WppDbgPrint
0x18003851d  mov     edx, 16h
0x180038522  jmp     loc_180038454
0x180038527  lea     rcx, [rbp+arg_8]
0x18003852b  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180038530  mov     rcx, [rbp+arg_18]
0x180038534  lea     rdx, [rbp+arg_8]
0x180038538  mov     rax, [rcx]
0x18003853b  mov     rax, [rax+40h]
0x18003853f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038544  mov     ebx, eax
0x180038546  test    eax, eax
0x180038548  jnz     loc_180038661
0x18003854e  mov     rcx, [rbp+arg_8]
0x180038552  lea     rdx, [rbp+String1]
0x180038556  mov     [rbp+String1], 0
0x18003855e  mov     rax, [rcx]
0x180038561  mov     rax, [rax+60h]
0x180038565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003856a  mov     rcx, [rbp+String1]; String1
0x18003856e  mov     rdx, rsi; String2
0x180038571  call    cs:__imp__wcsicmp
0x180038577  test    eax, eax
0x180038579  jz      short loc_180038590
0x18003857b  lea     rcx, [rbp+arg_8]
0x18003857f  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180038584  mov     rcx, [rbp+String1]; bstrString
0x180038588  call    cs:__imp_SysFreeString
0x18003858e  jmp     short loc_180038530
0x180038590  lea     rcx, [rbp+pvarg]; pvarg
0x180038594  call    cs:__imp_VariantInit
0x18003859a  mov     rcx, [rbp+arg_8]
0x18003859e  lea     r8, [rbp+pvarg]
0x1800385a2  mov     edx, r15d
0x1800385a5  mov     rax, [rcx]
0x1800385a8  mov     rax, [rax+38h]
0x1800385ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385b1  mov     ebx, eax
0x1800385b3  test    eax, eax
0x1800385b5  jns     short loc_18003861C
0x1800385b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800385be  cmp     rax, r13
0x1800385c1  jz      short loc_180038604
0x1800385c3  cmp     byte ptr [rax+19h], 2
0x1800385c7  jb      short loc_180038604
0x1800385c9  test    [rax+1Ch], r15d
0x1800385cd  jz      short loc_180038604
0x1800385cf  mov     edx, ebx
0x1800385d1  lea     rcx, aPitemGetproper; "pItem->GetProperty(PROPERTY_NAS_VENDOR_"...
0x1800385d8  call    WppDbgPrint
0x1800385dd  mov     edx, 17h
0x1800385e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385e9  lea     r9, aNpssdo; "NPSSDO"
0x1800385f0  lea     r8, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x1800385f7  mov     dword ptr [rsp+60h+var_40], ebx
0x1800385fb  mov     rcx, [rcx+10h]
0x1800385ff  call    WPP_SF_sd
0x180038604  lea     rcx, [rbp+pvarg]; this
0x180038608  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003860d  mov     rcx, [rbp+String1]; bstrString
0x180038611  call    cs:__imp_SysFreeString
0x180038617  jmp     loc_1800386E9
0x18003861c  mov     r8d, dword ptr [rbp+pvarg+8]; unsigned int
0x180038620  lea     rcx, [rdi+10h]; this
0x180038624  mov     edx, 403h; unsigned int
0x180038629  call    ?PutProperty@IASItem@@IEAAJKK@Z; IASItem::PutProperty(ulong,ulong)
0x18003862e  mov     ebx, eax
0x180038630  test    eax, eax
0x180038632  jns     short loc_180038604
0x180038634  mov     rax, cs:WPP_GLOBAL_Control
0x18003863b  cmp     rax, r13
0x18003863e  jz      short loc_180038604
0x180038640  cmp     byte ptr [rax+19h], 2
0x180038644  jb      short loc_180038604
0x180038646  test    [rax+1Ch], r15d
0x18003864a  jz      short loc_180038604
0x18003864c  mov     edx, ebx
0x18003864e  lea     rcx, aIasitemPutprop; "IASItem::PutProperty() returned 0x%x"
0x180038655  call    WppDbgPrint
0x18003865a  mov     edx, 18h
0x18003865f  jmp     short loc_1800385E2
0x180038661  test    ebx, ebx
0x180038663  jns     short loc_180038695
0x180038665  mov     rax, cs:WPP_GLOBAL_Control
0x18003866c  cmp     rax, r13
0x18003866f  jz      short loc_1800386E9
0x180038671  cmp     byte ptr [rax+19h], 2
0x180038675  jb      short loc_1800386E9
0x180038677  test    [rax+1Ch], r15d
0x18003867b  jz      short loc_1800386E9
0x18003867d  mov     edx, ebx
0x18003867f  lea     rcx, aPenumGetnextit_0; "pEnum->GetNextItem failed with 0x%x"
0x180038686  call    WppDbgPrint
0x18003868b  mov     edx, 19h
0x180038690  jmp     loc_180038454
0x180038695  mov     rax, cs:WPP_GLOBAL_Control
0x18003869c  cmp     rax, r13
0x18003869f  jz      short loc_1800386E4
0x1800386a1  cmp     byte ptr [rax+19h], 2
0x1800386a5  jb      short loc_1800386E4
0x1800386a7  test    [rax+1Ch], r15d
0x1800386ab  jz      short loc_1800386E4
0x1800386ad  mov     rdx, rsi
0x1800386b0  lea     rcx, aNoMatchingVend_0; "No matching vendor found from collectio"...
0x1800386b7  call    WppDbgPrint
0x1800386bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386c3  lea     r9, aNpssdo; "NPSSDO"
0x1800386ca  mov     edx, 1Ah
0x1800386cf  mov     [rsp+60h+var_40], rsi
0x1800386d4  lea     r8, WPP_d6e3168c2d5837c5b8fc702394a55b9f_Traceguids
0x1800386db  mov     rcx, [rcx+10h]
0x1800386df  call    WPP_SF_sS
0x1800386e4  mov     ebx, 8000FFFFh
0x1800386e9  lea     rcx, [rbp+arg_8]
0x1800386ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800386f2  lea     rcx, [rbp+arg_18]
0x1800386f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800386fb  lea     rcx, [rbp+var_30]
0x1800386ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038704  lea     rcx, [rbp+var_28]
0x180038708  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003870d  mov     eax, ebx
0x18003870f  mov     rbx, [rsp+60h+arg_0]
0x180038717  add     rsp, 60h
0x18003871b  pop     r15
0x18003871d  pop     r13
0x18003871f  pop     rdi
0x180038720  pop     rsi
0x180038721  pop     rbp
0x180038722  retn
```
