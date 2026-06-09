# IASService::GetAccountingLogs(_ITEMTYPE,IIASItem * *)

- ea: `0x18003233c`
- end: `0x1800325b8`
- name: `?GetAccountingLogs@IASService@@QEAAJW4_ITEMTYPE@@PEAPEAUIIASItem@@@Z`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033010`
- `0x1800336d0`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002844c`
- `0x18002cd00`
- `0x18002f14c`
- `0x18002f240`
- `0x18003233c`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180032429`
- `OLEAUT32!__imp_SysAllocString` at `0x180032429`
- `OLEAUT32!__imp_VariantInit` at `0x180032375`
- `OLEAUT32!__imp_VariantInit` at `0x180032375`

## string_xrefs

- `0x18003254b`: `IASSDOCreateItem(AcctType:%d) returned 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IASService::GetAccountingLogs(__int64 a1, int a2, __int64 a3)
{
  int SdoCollection; // ebx
  int v7; // edx
  const OLECHAR *v8; // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct ISdo **); // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  struct ISdo *v12; // [rsp+80h] [rbp+30h] BYREF
  struct ISdoCollection *v13; // [rsp+88h] [rbp+38h] BYREF

  v10 = 0;
  v13 = 0;
  v12 = 0;
  VariantInit(&pvarg);
  if ( !a3 )
  {
    SdoCollection = -2147467261;
    goto LABEL_26;
  }
  SdoCollection = GetSdoCollection(*(struct ISdo **)(a1 + 32), 0x405u, &v13);
  if ( SdoCollection >= 0 )
  {
    pvarg.vt = 8;
    v8 = L"Microsoft Accounting";
    if ( a2 != 7 )
      v8 = L"Microsoft Database Accounting";
    pvarg.llVal = (LONGLONG)SysAllocString(v8);
    SdoCollection = ((__int64 (__fastcall *)(struct ISdoCollection *, VARIANTARG *, _QWORD))v13->lpVtbl->Item)(
                      v13,
                      &pvarg,
                      &v10);
    if ( SdoCollection >= 0 )
    {
      SdoCollection = (**v10)(v10, &IID_ISdo, &v12);
      if ( SdoCollection >= 0 )
      {
        SdoCollection = IASSDOCreateItem(
                          a2,
                          v12,
                          *(struct ISdo **)(a1 + 40),
                          *(struct ISdoMachine **)(a1 + 48),
                          *(struct ISdoDictionaryOld **)(a1 + 56),
                          a3);
        if ( SdoCollection < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("IASSDOCreateItem(AcctType:%d) returned 0x%x");
          WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pDispAcct->QI(ISdo) failed with 0x%x");
        v7 = 18;
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pRequestHandlersColl->Item returned 0x%x");
      v7 = 17;
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetSdoCollection(PROPERTY_IAS_REQUESTHANDLERS_COLLECTION) returned 0x%x");
    v7 = 16;
LABEL_8:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
LABEL_26:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x18003233c  mov     [rsp-18h+arg_0], rbx
0x180032341  mov     [rsp-18h+arg_8], rsi
0x180032346  push    rbp
0x180032347  push    rdi
0x180032348  push    r14
0x18003234a  mov     rbp, rsp
0x18003234d  sub     rsp, 50h
0x180032351  mov     r14, r8
0x180032354  mov     esi, edx
0x180032356  mov     rdi, rcx
0x180032359  mov     [rbp+var_20], 0
0x180032361  mov     [rbp+arg_18], 0
0x180032369  mov     [rbp+arg_10], 0
0x180032371  lea     rcx, [rbp+pvarg]; pvarg
0x180032375  call    cs:__imp_VariantInit
0x18003237b  nop
0x18003237c  test    r14, r14
0x18003237f  jnz     short loc_18003238B
0x180032381  mov     ebx, 80004003h
0x180032386  jmp     loc_18003257C
0x18003238b  lea     r8, [rbp+arg_18]; struct ISdoCollection **
0x18003238f  mov     edx, 405h; unsigned int
0x180032394  mov     rcx, [rdi+20h]; struct ISdo *
0x180032398  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x18003239d  mov     ebx, eax
0x18003239f  test    eax, eax
0x1800323a1  jns     short loc_18003240B
0x1800323a3  lea     rax, WPP_GLOBAL_Control
0x1800323aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800323b1  cmp     rcx, rax
0x1800323b4  jz      loc_18003257C
0x1800323ba  cmp     byte ptr [rcx+19h], 2
0x1800323be  jb      loc_18003257C
0x1800323c4  test    dword ptr [rcx+1Ch], 400h
0x1800323cb  jz      loc_18003257C
0x1800323d1  mov     edx, ebx
0x1800323d3  lea     rcx, aGetsdocollecti_1; "GetSdoCollection(PROPERTY_IAS_REQUESTHA"...
0x1800323da  call    WppDbgPrint
0x1800323df  mov     edx, 10h
0x1800323e4  mov     dword ptr [rsp+50h+var_30], ebx
0x1800323e8  lea     r9, aNpssdo; "NPSSDO"
0x1800323ef  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800323f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800323fd  mov     rcx, [rcx+10h]
0x180032401  call    WPP_SF_sd
0x180032406  jmp     loc_18003257C
0x18003240b  mov     eax, 8
0x180032410  mov     word ptr [rbp+pvarg], ax
0x180032414  lea     rax, aMicrosoftDatab; "Microsoft Database Accounting"
0x18003241b  lea     rcx, aMicrosoftAccou; "Microsoft Accounting"
0x180032422  cmp     esi, 7
0x180032425  cmovnz  rcx, rax; psz
0x180032429  call    cs:__imp_SysAllocString
0x18003242f  mov     qword ptr [rbp+pvarg+8], rax
0x180032433  mov     rcx, [rbp+arg_18]
0x180032437  mov     rax, [rcx]
0x18003243a  lea     r8, [rbp+var_20]
0x18003243e  lea     rdx, [rbp+pvarg]
0x180032442  mov     rax, [rax+68h]
0x180032446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003244b  mov     ebx, eax
0x18003244d  test    eax, eax
0x18003244f  jns     short loc_180032497
0x180032451  lea     rax, WPP_GLOBAL_Control
0x180032458  mov     rcx, cs:WPP_GLOBAL_Control
0x18003245f  cmp     rcx, rax
0x180032462  jz      loc_18003257C
0x180032468  cmp     byte ptr [rcx+19h], 2
0x18003246c  jb      loc_18003257C
0x180032472  test    dword ptr [rcx+1Ch], 400h
0x180032479  jz      loc_18003257C
0x18003247f  mov     edx, ebx
0x180032481  lea     rcx, aPrequesthandle; "pRequestHandlersColl->Item returned 0x%"...
0x180032488  call    WppDbgPrint
0x18003248d  mov     edx, 11h
0x180032492  jmp     loc_1800323E4
0x180032497  mov     rcx, [rbp+var_20]
0x18003249b  mov     rax, [rcx]
0x18003249e  lea     r8, [rbp+arg_10]
0x1800324a2  lea     rdx, IID_ISdo
0x1800324a9  mov     rax, [rax]
0x1800324ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324b1  mov     ebx, eax
0x1800324b3  test    eax, eax
0x1800324b5  jns     short loc_1800324FD
0x1800324b7  lea     rax, WPP_GLOBAL_Control
0x1800324be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324c5  cmp     rcx, rax
0x1800324c8  jz      loc_18003257C
0x1800324ce  cmp     byte ptr [rcx+19h], 2
0x1800324d2  jb      loc_18003257C
0x1800324d8  test    dword ptr [rcx+1Ch], 400h
0x1800324df  jz      loc_18003257C
0x1800324e5  mov     edx, ebx
0x1800324e7  lea     rcx, aPdispacctQiIsd; "pDispAcct->QI(ISdo) failed with 0x%x"
0x1800324ee  call    WppDbgPrint
0x1800324f3  mov     edx, 12h
0x1800324f8  jmp     loc_1800323E4
0x1800324fd  mov     [rsp+50h+var_28], r14
0x180032502  mov     rax, [rdi+38h]
0x180032506  mov     [rsp+50h+var_30], rax
0x18003250b  mov     r9, [rdi+30h]
0x18003250f  mov     r8, [rdi+28h]
0x180032513  mov     rdx, [rbp+arg_10]
0x180032517  mov     ecx, esi
0x180032519  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x18003251e  mov     ebx, eax
0x180032520  test    eax, eax
0x180032522  jns     short loc_18003257C
0x180032524  lea     rax, WPP_GLOBAL_Control
0x18003252b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032532  cmp     rcx, rax
0x180032535  jz      short loc_18003257C
0x180032537  cmp     byte ptr [rcx+19h], 2
0x18003253b  jb      short loc_18003257C
0x18003253d  test    dword ptr [rcx+1Ch], 400h
0x180032544  jz      short loc_18003257C
0x180032546  mov     r8d, ebx
0x180032549  mov     edx, esi
0x18003254b  lea     rcx, aIassdocreateit_2; "IASSDOCreateItem(AcctType:%d) returned "...
0x180032552  call    WppDbgPrint
0x180032557  mov     edx, 13h
0x18003255c  mov     dword ptr [rsp+50h+var_28], ebx
0x180032560  mov     dword ptr [rsp+50h+var_30], esi
0x180032564  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x18003256b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032572  mov     rcx, [rcx+10h]
0x180032576  call    WPP_SF_sdD
0x18003257b  nop
0x18003257c  lea     rcx, [rbp+pvarg]; this
0x180032580  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180032585  nop
0x180032586  lea     rcx, [rbp+arg_10]
0x18003258a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003258f  nop
0x180032590  lea     rcx, [rbp+arg_18]
0x180032594  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032599  nop
0x18003259a  lea     rcx, [rbp+var_20]
0x18003259e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800325a3  mov     eax, ebx
0x1800325a5  mov     rbx, [rsp+50h+arg_0]
0x1800325aa  mov     rsi, [rsp+50h+arg_8]
0x1800325af  add     rsp, 50h
0x1800325b3  pop     r14
0x1800325b5  pop     rdi
0x1800325b6  pop     rbp
0x1800325b7  retn
```
