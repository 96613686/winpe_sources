# IASServerGroup::InternalRemove(void)

- ea: `0x180037180`
- end: `0x180037797`
- name: `?InternalRemove@IASServerGroup@@UEAAJXZ`
- size: `1559`
- prototype: `__int64 __fastcall(IASServerGroup *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cca4`
- `0x18002cd00`
- `0x18002ee50`
- `0x18002f240`
- `0x180037180`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003746b`
- `msvcrt!_wcsicmp` at `0x18003746b`
- `OLEAUT32!__imp_VariantInit` at `0x180037428`
- `OLEAUT32!__imp_VariantInit` at `0x180037428`

## string_xrefs

- `0x18003720b`: `IASSDOCreateItem(IASSERVICE) failed with 0x%x`
- `0x1800372e7`: `pService->get_CRPolicies failed with 0x%x`
- `0x1800374f0`: `Cannot remove server group -- referenced by CRP attribute`

## pseudocode

```c
__int64 __fastcall IASServerGroup::InternalRemove(IASServerGroup *this)
{
  struct ISdoMachine *v1; // r9
  struct ISdo *v3; // r8
  struct ISdoDictionaryOld *v4; // rax
  int v5; // ebx
  int v6; // edx
  __int64 v8; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  int v14; // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+98h] [rbp+28h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v1 = (struct ISdoMachine *)*((_QWORD *)this + 5);
  v3 = (struct ISdo *)*((_QWORD *)this + 4);
  v4 = (struct ISdoDictionaryOld *)*((_QWORD *)this + 6);
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v5 = IASSDOCreateItem(1, v3, v3, v1, v4, (__int64)&v9);
  if ( v5 >= 0 )
  {
    v5 = (**v9)(v9, &IID_IIASItem, &v12);
    if ( v5 >= 0 )
    {
      ATL::CComPtrBase<IIASItem>::Release(&v9);
      if ( *((_DWORD *)this + 28) == 5 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 232LL))(v12, &v11);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 80LL))(v11, &v10);
          if ( v5 >= 0 )
          {
            while ( 2 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v10 + 64LL))(
                     v10,
                     &v9);
              if ( v5 )
              {
                if ( v5 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                {
                  WppDbgPrint("pEnum->GetNextItem failed with 0x%x");
                  v6 = 22;
                  goto LABEL_68;
                }
              }
              else
              {
                v16 = 0;
                v5 = (**v9)(v9, &IID_IIASPolicy, &v16);
                if ( v5 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  {
                    WppDbgPrint("pItem->QI(IID_IIASPolicy) failed with 0x%x");
                    WPP_SF_sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      16,
                      (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                      (unsigned int)"NPSSDO",
                      v5);
                  }
                }
                else
                {
                  ATL::CComPtrBase<IIASItem>::Release(&v9);
                  v15 = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 184LL))(v16, &v15);
                  if ( v5 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                    {
                      WppDbgPrint("pPolicy->get_ProfileAttributesCollection failed with 0x%x");
                      WPP_SF_sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        17,
                        (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                        (unsigned int)"NPSSDO",
                        v5);
                    }
                  }
                  else
                  {
                    v8 = 0;
                    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 80LL))(v15, &v8);
                    if ( v5 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                      {
                        WppDbgPrint("pAttribs->get_Enumerator failed with 0x%x");
                        WPP_SF_sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          18,
                          (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                          (unsigned int)"NPSSDO",
                          v5);
                      }
                    }
                    else
                    {
                      v17 = 0;
                      while ( 1 )
                      {
                        v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v17);
                        if ( v5 )
                          break;
                        v14 = 0;
                        VariantInit(&pvarg);
                        v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, VARIANTARG *))(*(_QWORD *)v15 + 104LL))(
                               v15,
                               v17,
                               &v14,
                               &pvarg);
                        if ( v5 < 0 )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                          {
                            WppDbgPrint("pAttribs->GetAttributeValue failed with 0x%x");
                            WPP_SF_sd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              19,
                              (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                              (unsigned int)"NPSSDO",
                              v5);
                          }
                          goto LABEL_42;
                        }
                        if ( ((v14 - 4137) & 0xFFFFFFFD) == 0 && !_wcsicmp(*((const wchar_t **)this + 2), pvarg.bstrVal) )
                        {
                          v5 = -2130837503;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                          {
                            WppDbgPrint("Cannot remove server group -- referenced by CRP attribute");
                            WPP_SF_s(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              20,
                              &WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                              "NPSSDO");
                          }
LABEL_42:
                          _variant_t::~_variant_t((_variant_t *)&pvarg);
                          goto LABEL_43;
                        }
                        ATL::CComPtrBase<IIASItem>::Release(&v17);
                        _variant_t::~_variant_t((_variant_t *)&pvarg);
                      }
                      if ( v5 >= 0 )
                      {
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
                        continue;
                      }
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                      {
                        WppDbgPrint("pEnum->GetNextItem failed with 0x%x");
                        WPP_SF_sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          21,
                          (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
                          (unsigned int)"NPSSDO",
                          v5);
                      }
LABEL_43:
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
                    }
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
                  }
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
              }
              break;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pPolicyColl->get_Enumerator failed with 0x%x");
            v6 = 15;
            goto LABEL_68;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pService->get_CRPolicies failed with 0x%x");
          v6 = 14;
          goto LABEL_68;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pItem->QI(IID_IIASItem) failed with 0x%x");
      v6 = 13;
      goto LABEL_68;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("IASSDOCreateItem(IASSERVICE) failed with 0x%x");
    v6 = 12;
LABEL_68:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids,
      (unsigned int)"NPSSDO",
      v5);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180037180  push    rbp
0x180037182  push    rbx
0x180037183  push    rdi
0x180037184  mov     rbp, rsp
0x180037187  sub     rsp, 70h
0x18003718b  mov     rdx, [rcx+20h]
0x18003718f  lea     rax, [rbp+var_38]
0x180037193  mov     r9, [rcx+28h]
0x180037197  mov     rdi, rcx
0x18003719a  mov     [rsp+70h+var_48], rax
0x18003719f  mov     r8, rdx
0x1800371a2  mov     rax, [rcx+30h]
0x1800371a6  mov     ecx, 1
0x1800371ab  mov     [rsp+70h+var_50], rax
0x1800371b0  mov     [rbp+var_20], 0
0x1800371b8  mov     [rbp+var_28], 0
0x1800371c0  mov     [rbp+var_30], 0
0x1800371c8  mov     [rbp+var_38], 0
0x1800371d0  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x1800371d5  mov     ebx, eax
0x1800371d7  test    eax, eax
0x1800371d9  jns     short loc_180037221
0x1800371db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371e2  lea     rax, WPP_GLOBAL_Control
0x1800371e9  cmp     rcx, rax
0x1800371ec  jz      loc_180037769
0x1800371f2  cmp     byte ptr [rcx+19h], 2
0x1800371f6  jb      loc_180037769
0x1800371fc  test    dword ptr [rcx+1Ch], 400h
0x180037203  jz      loc_180037769
0x180037209  mov     edx, ebx
0x18003720b  lea     rcx, aIassdocreateit; "IASSDOCreateItem(IASSERVICE) failed wit"...
0x180037212  call    WppDbgPrint
0x180037217  mov     edx, 0Ch
0x18003721c  jmp     loc_180037747
0x180037221  mov     rcx, [rbp+var_38]
0x180037225  lea     r8, [rbp+var_20]
0x180037229  lea     rdx, IID_IIASItem
0x180037230  mov     rax, [rcx]
0x180037233  mov     rax, [rax]
0x180037236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003723b  mov     ebx, eax
0x18003723d  test    eax, eax
0x18003723f  jns     short loc_180037287
0x180037241  mov     rcx, cs:WPP_GLOBAL_Control
0x180037248  lea     rax, WPP_GLOBAL_Control
0x18003724f  cmp     rcx, rax
0x180037252  jz      loc_180037769
0x180037258  cmp     byte ptr [rcx+19h], 2
0x18003725c  jb      loc_180037769
0x180037262  test    dword ptr [rcx+1Ch], 400h
0x180037269  jz      loc_180037769
0x18003726f  mov     edx, ebx
0x180037271  lea     rcx, aPitemQiIidIias_1; "pItem->QI(IID_IIASItem) failed with 0x%"...
0x180037278  call    WppDbgPrint
0x18003727d  mov     edx, 0Dh
0x180037282  jmp     loc_180037747
0x180037287  lea     rcx, [rbp+var_38]
0x18003728b  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x180037290  cmp     dword ptr [rdi+70h], 5
0x180037294  jnz     loc_180037769
0x18003729a  mov     rcx, [rbp+var_20]
0x18003729e  lea     rdx, [rbp+var_28]
0x1800372a2  mov     rax, [rcx]
0x1800372a5  mov     rax, [rax+0E8h]
0x1800372ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372b1  mov     ebx, eax
0x1800372b3  test    eax, eax
0x1800372b5  jns     short loc_1800372FD
0x1800372b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372be  lea     rax, WPP_GLOBAL_Control
0x1800372c5  cmp     rcx, rax
0x1800372c8  jz      loc_180037769
0x1800372ce  cmp     byte ptr [rcx+19h], 2
0x1800372d2  jb      loc_180037769
0x1800372d8  test    dword ptr [rcx+1Ch], 400h
0x1800372df  jz      loc_180037769
0x1800372e5  mov     edx, ebx
0x1800372e7  lea     rcx, aPserviceGetCrp; "pService->get_CRPolicies failed with 0x"...
0x1800372ee  call    WppDbgPrint
0x1800372f3  mov     edx, 0Eh
0x1800372f8  jmp     loc_180037747
0x1800372fd  mov     rcx, [rbp+var_28]
0x180037301  lea     rdx, [rbp+var_30]
0x180037305  mov     rax, [rcx]
0x180037308  mov     rax, [rax+50h]
0x18003730c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037311  mov     ebx, eax
0x180037313  test    eax, eax
0x180037315  jns     short loc_18003735D
0x180037317  mov     rcx, cs:WPP_GLOBAL_Control
0x18003731e  lea     rax, WPP_GLOBAL_Control
0x180037325  cmp     rcx, rax
0x180037328  jz      loc_180037769
0x18003732e  cmp     byte ptr [rcx+19h], 2
0x180037332  jb      loc_180037769
0x180037338  test    dword ptr [rcx+1Ch], 400h
0x18003733f  jz      loc_180037769
0x180037345  mov     edx, ebx
0x180037347  lea     rcx, aPpolicycollGet; "pPolicyColl->get_Enumerator failed with"...
0x18003734e  call    WppDbgPrint
0x180037353  mov     edx, 0Fh
0x180037358  jmp     loc_180037747
0x18003735d  mov     rcx, [rbp+var_30]
0x180037361  lea     rdx, [rbp+var_38]
0x180037365  mov     rax, [rcx]
0x180037368  mov     rax, [rax+40h]
0x18003736c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037371  mov     ebx, eax
0x180037373  test    eax, eax
0x180037375  jnz     loc_18003770E
0x18003737b  mov     rcx, [rbp+var_38]
0x18003737f  lea     r8, [rbp+arg_10]
0x180037383  mov     [rbp+arg_10], 0
0x18003738b  lea     rdx, IID_IIASPolicy
0x180037392  mov     rax, [rcx]
0x180037395  mov     rax, [rax]
0x180037398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003739d  mov     ebx, eax
0x18003739f  test    eax, eax
0x1800373a1  js      loc_1800376AC
0x1800373a7  lea     rcx, [rbp+var_38]
0x1800373ab  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x1800373b0  mov     rcx, [rbp+arg_10]
0x1800373b4  lea     rdx, [rbp+arg_8]
0x1800373b8  mov     [rbp+arg_8], 0
0x1800373c0  mov     rax, [rcx]
0x1800373c3  mov     rax, [rax+0B8h]
0x1800373ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373cf  mov     ebx, eax
0x1800373d1  test    eax, eax
0x1800373d3  js      loc_18003764A
0x1800373d9  mov     rcx, [rbp+arg_8]
0x1800373dd  lea     rdx, [rbp+var_40]
0x1800373e1  mov     [rbp+var_40], 0
0x1800373e9  mov     rax, [rcx]
0x1800373ec  mov     rax, [rax+50h]
0x1800373f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373f5  mov     ebx, eax
0x1800373f7  test    eax, eax
0x1800373f9  js      loc_1800375E8
0x1800373ff  mov     [rbp+arg_18], 0
0x180037407  mov     rcx, [rbp+var_40]
0x18003740b  lea     rdx, [rbp+arg_18]
0x18003740f  mov     rax, [rcx]
0x180037412  mov     rax, [rax+40h]
0x180037416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003741b  mov     ebx, eax
0x18003741d  test    eax, eax
0x18003741f  jnz     short loc_18003748C
0x180037421  lea     rcx, [rbp+pvarg]; pvarg
0x180037425  mov     [rbp+arg_0], eax
0x180037428  call    cs:__imp_VariantInit
0x18003742e  mov     rcx, [rbp+arg_8]
0x180037432  lea     r9, [rbp+pvarg]
0x180037436  mov     rdx, [rbp+arg_18]
0x18003743a  lea     r8, [rbp+arg_0]
0x18003743e  mov     rax, [rcx]
0x180037441  mov     rax, [rax+68h]
0x180037445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003744a  mov     ebx, eax
0x18003744c  test    eax, eax
0x18003744e  js      loc_180037521
0x180037454  mov     eax, [rbp+arg_0]
0x180037457  add     eax, 0FFFFEFD7h
0x18003745c  test    eax, 0FFFFFFFDh
0x180037461  jnz     short loc_180037475
0x180037463  mov     rdx, qword ptr [rbp+pvarg+8]; String2
0x180037467  mov     rcx, [rdi+10h]; String1
0x18003746b  call    cs:__imp__wcsicmp
0x180037471  test    eax, eax
0x180037473  jz      short loc_1800374BD
0x180037475  lea     rcx, [rbp+arg_18]
0x180037479  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x18003747e  lea     rcx, [rbp+pvarg]; this
0x180037482  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180037487  jmp     loc_180037407
0x18003748c  test    ebx, ebx
0x18003748e  js      loc_18003758F
0x180037494  lea     rcx, [rbp+arg_18]
0x180037498  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003749d  lea     rcx, [rbp+var_40]
0x1800374a1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800374a6  lea     rcx, [rbp+arg_8]
0x1800374aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800374af  lea     rcx, [rbp+arg_10]
0x1800374b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800374b8  jmp     loc_18003735D
0x1800374bd  mov     ebx, 80FE0001h
0x1800374c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374c9  lea     rax, WPP_GLOBAL_Control
0x1800374d0  cmp     rcx, rax
0x1800374d3  jz      loc_180037578
0x1800374d9  cmp     byte ptr [rcx+19h], 2
0x1800374dd  jb      loc_180037578
0x1800374e3  test    dword ptr [rcx+1Ch], 400h
0x1800374ea  jz      loc_180037578
0x1800374f0  lea     rcx, aCannotRemoveSe; "Cannot remove server group -- reference"...
0x1800374f7  call    WppDbgPrint
0x1800374fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180037503  lea     r9, aNpssdo; "NPSSDO"
0x18003750a  mov     edx, 14h
0x18003750f  lea     r8, WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids
0x180037516  mov     rcx, [rcx+10h]
0x18003751a  call    WPP_SF_s
0x18003751f  jmp     short loc_180037578
0x180037521  mov     rcx, cs:WPP_GLOBAL_Control
0x180037528  lea     rax, WPP_GLOBAL_Control
0x18003752f  cmp     rcx, rax
0x180037532  jz      short loc_180037578
0x180037534  cmp     byte ptr [rcx+19h], 2
0x180037538  jb      short loc_180037578
0x18003753a  test    dword ptr [rcx+1Ch], 400h
0x180037541  jz      short loc_180037578
0x180037543  mov     edx, ebx
0x180037545  lea     rcx, aPattribsGetatt; "pAttribs->GetAttributeValue failed with"...
0x18003754c  call    WppDbgPrint
0x180037551  mov     rcx, cs:WPP_GLOBAL_Control
0x180037558  lea     r9, aNpssdo; "NPSSDO"
0x18003755f  mov     edx, 13h
0x180037564  mov     dword ptr [rsp+70h+var_50], ebx
0x180037568  lea     r8, WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids
0x18003756f  mov     rcx, [rcx+10h]
0x180037573  call    WPP_SF_sd
0x180037578  lea     rcx, [rbp+pvarg]; this
0x18003757c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180037581  lea     rcx, [rbp+arg_18]
0x180037585  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003758a  jmp     loc_18003763F
0x18003758f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037596  lea     rax, WPP_GLOBAL_Control
0x18003759d  cmp     rcx, rax
0x1800375a0  jz      short loc_180037581
0x1800375a2  cmp     byte ptr [rcx+19h], 2
0x1800375a6  jb      short loc_180037581
0x1800375a8  test    dword ptr [rcx+1Ch], 400h
0x1800375af  jz      short loc_180037581
0x1800375b1  mov     edx, ebx
0x1800375b3  lea     rcx, aPenumGetnextit_0; "pEnum->GetNextItem failed with 0x%x"
0x1800375ba  call    WppDbgPrint
0x1800375bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375c6  lea     r9, aNpssdo; "NPSSDO"
0x1800375cd  mov     edx, 15h
0x1800375d2  mov     dword ptr [rsp+70h+var_50], ebx
0x1800375d6  lea     r8, WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids
0x1800375dd  mov     rcx, [rcx+10h]
0x1800375e1  call    WPP_SF_sd
0x1800375e6  jmp     short loc_180037581
0x1800375e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375ef  lea     rax, WPP_GLOBAL_Control
0x1800375f6  cmp     rcx, rax
0x1800375f9  jz      short loc_18003763F
0x1800375fb  cmp     byte ptr [rcx+19h], 2
0x1800375ff  jb      short loc_18003763F
0x180037601  test    dword ptr [rcx+1Ch], 400h
0x180037608  jz      short loc_18003763F
0x18003760a  mov     edx, ebx
0x18003760c  lea     rcx, aPattribsGetEnu; "pAttribs->get_Enumerator failed with 0x"...
0x180037613  call    WppDbgPrint
0x180037618  mov     rcx, cs:WPP_GLOBAL_Control
0x18003761f  lea     r9, aNpssdo; "NPSSDO"
0x180037626  mov     edx, 12h
0x18003762b  mov     dword ptr [rsp+70h+var_50], ebx
0x18003762f  lea     r8, WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids
0x180037636  mov     rcx, [rcx+10h]
0x18003763a  call    WPP_SF_sd
0x18003763f  lea     rcx, [rbp+var_40]
0x180037643  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037648  jmp     short loc_1800376A1
0x18003764a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037651  lea     rax, WPP_GLOBAL_Control
0x180037658  cmp     rcx, rax
0x18003765b  jz      short loc_1800376A1
0x18003765d  cmp     byte ptr [rcx+19h], 2
0x180037661  jb      short loc_1800376A1
0x180037663  test    dword ptr [rcx+1Ch], 400h
0x18003766a  jz      short loc_1800376A1
0x18003766c  mov     edx, ebx
0x18003766e  lea     rcx, aPpolicyGetProf; "pPolicy->get_ProfileAttributesCollectio"...
0x180037675  call    WppDbgPrint
0x18003767a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037681  lea     r9, aNpssdo; "NPSSDO"
0x180037688  mov     edx, 11h
0x18003768d  mov     dword ptr [rsp+70h+var_50], ebx
0x180037691  lea     r8, WPP_c220831c841235f6ef540fee8a23bbf7_Traceguids
0x180037698  mov     rcx, [rcx+10h]
0x18003769c  call    WPP_SF_sd
0x1800376a1  lea     rcx, [rbp+arg_8]
0x1800376a5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800376aa  jmp     short loc_180037703
0x1800376ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376b3  lea     rax, WPP_GLOBAL_Control
0x1800376ba  cmp     rcx, rax
0x1800376bd  jz      short loc_180037703
0x1800376bf  cmp     byte ptr [rcx+19h], 2
0x1800376c3  jb      short loc_180037703
0x1800376c5  test    dword ptr [rcx+1Ch], 400h
0x1800376cc  jz      short loc_180037703
0x1800376ce  mov     edx, ebx
0x1800376d0  lea     rcx, aPitemQiIidIias; "pItem->QI(IID_IIASPolicy) failed with 0"...
  ... truncated ...
```
