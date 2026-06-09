# IASItem::GetItemsCollection(ISdo *,ulong,_ITEMTYPE,IIASItemsCollection * *)

- ea: `0x18002f458`
- end: `0x18002f78d`
- name: `?GetItemsCollection@IASItem@@IEAAJPEAUISdo@@KW4_ITEMTYPE@@PEAPEAUIIASItemsCollection@@@Z`
- size: `821`
- prototype: `int __high(struct ISdo *, unsigned int, enum _ITEMTYPE, struct IIASItemsCollection **)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002f434`
- `0x180032ce0`
- `0x180032ea0`

## callees

- `0x180024cac`
- `0x180027ee4`
- `0x18002cd00`
- `0x18002d278`
- `0x18002f14c`
- `0x18002f240`
- `0x18002f300`
- `0x18002f458`
- `0x180030814`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002f482`
- `OLEAUT32!__imp_VariantInit` at `0x18002f482`

## string_xrefs

- `0x18002f5c5`: `CreateInstance(IASItemsCollection) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IASItem::GetItemsCollection(
        __int64 a1,
        struct ISdo *a2,
        unsigned int a3,
        unsigned int a4,
        _QWORD *a5)
{
  int SdoProperty; // ebx
  int v9; // eax
  char v10; // bl
  struct IUnknown **v11; // r15
  struct IUnknown *v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  struct IUnknown *v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF

  v15 = 0;
  VariantInit(&pvarg);
  v17 = 0;
  SdoProperty = GetSdoProperty(a2, a3, &pvarg);
  if ( SdoProperty >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_ISdoCollection, &v17);
    v10 = v9;
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("QI(ISdoCollection) failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids,
        (unsigned int)"NPSSDO",
        v10);
    }
    v16 = 0;
    SdoProperty = ATL::CComObject<IASItemsCollection>::CreateInstance(&v16);
    if ( SdoProperty >= 0 )
    {
      v11 = (struct IUnknown **)v16;
      SdoProperty = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v16->lpVtbl->QueryInterface)(
                      v16,
                      &IID_IIASItemsCollection,
                      &v15);
      if ( SdoProperty >= 0 )
      {
        v16 = 0;
        v12 = (struct IUnknown *)(**(__int64 (__fastcall ***)(__int64))a1)(a1);
        v16 = v12;
        if ( v12 && v11[8] != v12 )
          ATL::AtlComPtrAssign(v11 + 8, v12);
        SdoProperty = IASCollection::Initialize(
                        v11 + 1,
                        a4,
                        v17,
                        *(_QWORD *)(a1 + 24),
                        *(_QWORD *)(a1 + 32),
                        *(_QWORD *)(a1 + 40));
        if ( SdoProperty >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
          v13 = v15;
          v15 = 0;
          *a5 = v13;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRAPolicies->Initialize failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids,
              (unsigned int)"NPSSDO",
              SdoProperty);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("QI(IIASItemsCollection) failed with 0x%x");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids,
            (unsigned int)"NPSSDO",
            SdoProperty);
        }
        if ( v11 )
          ((void (__fastcall *)(struct IUnknown **, __int64))(*v11)[15].lpVtbl)(v11, 1);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateInstance(IASItemsCollection) failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids,
        (unsigned int)"NPSSDO",
        SdoProperty);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetProperty(%d) failed with 0x%x");
    WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  return (unsigned int)SdoProperty;
}

```

## disassembly

```asm
0x18002f458  mov     [rsp-30h+arg_18], r9d
0x18002f45d  push    rbp
0x18002f45e  push    rbx
0x18002f45f  push    rsi
0x18002f460  push    r13
0x18002f462  push    r14
0x18002f464  push    r15
0x18002f466  mov     rbp, rsp
0x18002f469  sub     rsp, 68h
0x18002f46d  mov     r15d, r8d
0x18002f470  mov     rbx, rdx
0x18002f473  mov     r13, rcx
0x18002f476  mov     [rbp+var_38], 0
0x18002f47e  lea     rcx, [rbp+pvarg]; pvarg
0x18002f482  call    cs:__imp_VariantInit
0x18002f488  nop
0x18002f489  mov     [rbp+var_28], 0
0x18002f491  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18002f495  mov     edx, r15d; unsigned int
0x18002f498  mov     rcx, rbx; struct ISdo *
0x18002f49b  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x18002f4a0  mov     ebx, eax
0x18002f4a2  test    eax, eax
0x18002f4a4  jns     short loc_18002F511
0x18002f4a6  lea     r14, WPP_GLOBAL_Control
0x18002f4ad  mov     rax, cs:WPP_GLOBAL_Control
0x18002f4b4  cmp     rax, r14
0x18002f4b7  jz      loc_18002F760
0x18002f4bd  cmp     byte ptr [rax+19h], 2
0x18002f4c1  jb      loc_18002F760
0x18002f4c7  mov     esi, 400h
0x18002f4cc  test    [rax+1Ch], esi
0x18002f4cf  jz      loc_18002F760
0x18002f4d5  mov     r8d, ebx
0x18002f4d8  mov     edx, r15d
0x18002f4db  lea     rcx, aGetpropertyDFa; "GetProperty(%d) failed with 0x%x"
0x18002f4e2  call    WppDbgPrint
0x18002f4e7  mov     edx, 0Ah
0x18002f4ec  mov     dword ptr [rsp+68h+var_40], ebx
0x18002f4f0  mov     dword ptr [rsp+68h+var_48], r15d
0x18002f4f5  lea     r8, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids
0x18002f4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f503  mov     rcx, [rcx+10h]
0x18002f507  call    WPP_SF_sdD
0x18002f50c  jmp     loc_18002F760
0x18002f511  mov     rcx, qword ptr [rbp+pvarg+8]
0x18002f515  mov     rax, [rcx]
0x18002f518  lea     r8, [rbp+var_28]
0x18002f51c  lea     rdx, IID_ISdoCollection
0x18002f523  mov     rax, [rax]
0x18002f526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f52b  mov     ebx, eax
0x18002f52d  mov     esi, 400h
0x18002f532  lea     r14, WPP_GLOBAL_Control
0x18002f539  test    eax, eax
0x18002f53b  jns     short loc_18002F589
0x18002f53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f544  cmp     rcx, r14
0x18002f547  jz      short loc_18002F589
0x18002f549  cmp     byte ptr [rcx+19h], 2
0x18002f54d  jb      short loc_18002F589
0x18002f54f  test    [rcx+1Ch], esi
0x18002f552  jz      short loc_18002F589
0x18002f554  mov     edx, eax
0x18002f556  lea     rcx, aQiIsdocollecti; "QI(ISdoCollection) failed with 0x%x"
0x18002f55d  call    WppDbgPrint
0x18002f562  mov     edx, 0Bh
0x18002f567  mov     dword ptr [rsp+68h+var_48], ebx
0x18002f56b  lea     r9, aNpssdo; "NPSSDO"
0x18002f572  lea     r8, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids
0x18002f579  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f580  mov     rcx, [rcx+10h]
0x18002f584  call    WPP_SF_sd
0x18002f589  mov     [rbp+var_30], 0
0x18002f591  lea     rcx, [rbp+var_30]
0x18002f595  call    ?CreateInstance@?$CComObject@VIASItemsCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASItemsCollection>::CreateInstance(ATL::CComObject<IASItemsCollection> * *)
0x18002f59a  mov     ebx, eax
0x18002f59c  test    eax, eax
0x18002f59e  jns     short loc_18002F5FD
0x18002f5a0  mov     rax, cs:WPP_GLOBAL_Control
0x18002f5a7  cmp     rax, r14
0x18002f5aa  jz      loc_18002F760
0x18002f5b0  cmp     byte ptr [rax+19h], 2
0x18002f5b4  jb      loc_18002F760
0x18002f5ba  test    [rax+1Ch], esi
0x18002f5bd  jz      loc_18002F760
0x18002f5c3  mov     edx, ebx
0x18002f5c5  lea     rcx, aCreateinstance_1; "CreateInstance(IASItemsCollection) fail"...
0x18002f5cc  call    WppDbgPrint
0x18002f5d1  mov     edx, 0Ch
0x18002f5d6  mov     dword ptr [rsp+68h+var_48], ebx
0x18002f5da  lea     r9, aNpssdo; "NPSSDO"
0x18002f5e1  lea     r8, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids
0x18002f5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5ef  mov     rcx, [rcx+10h]
0x18002f5f3  call    WPP_SF_sd
0x18002f5f8  jmp     loc_18002F760
0x18002f5fd  mov     r15, [rbp+var_30]
0x18002f601  mov     rax, [r15]
0x18002f604  lea     r8, [rbp+var_38]
0x18002f608  lea     rdx, IID_IIASItemsCollection
0x18002f60f  mov     rcx, r15
0x18002f612  mov     rax, [rax]
0x18002f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f61a  mov     ebx, eax
0x18002f61c  test    eax, eax
0x18002f61e  jns     short loc_18002F68E
0x18002f620  mov     rax, cs:WPP_GLOBAL_Control
0x18002f627  cmp     rax, r14
0x18002f62a  jz      short loc_18002F66C
0x18002f62c  cmp     byte ptr [rax+19h], 2
0x18002f630  jb      short loc_18002F66C
0x18002f632  test    [rax+1Ch], esi
0x18002f635  jz      short loc_18002F66C
0x18002f637  mov     edx, ebx
0x18002f639  lea     rcx, aQiIiasitemscol; "QI(IIASItemsCollection) failed with 0x%"...
0x18002f640  call    WppDbgPrint
0x18002f645  mov     edx, 0Dh
0x18002f64a  mov     dword ptr [rsp+68h+var_48], ebx
0x18002f64e  lea     r9, aNpssdo; "NPSSDO"
0x18002f655  lea     r8, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids
0x18002f65c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f663  mov     rcx, [rcx+10h]
0x18002f667  call    WPP_SF_sd
0x18002f66c  test    r15, r15
0x18002f66f  jz      loc_18002F760
0x18002f675  mov     rax, [r15]
0x18002f678  mov     edx, 1
0x18002f67d  mov     rcx, r15
0x18002f680  mov     rax, [rax+78h]
0x18002f684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f689  jmp     loc_18002F760
0x18002f68e  mov     [rbp+var_30], 0
0x18002f696  mov     rax, [r13+0]
0x18002f69a  mov     rcx, r13
0x18002f69d  mov     rax, [rax]
0x18002f6a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6a5  nop
0x18002f6a6  mov     [rbp+var_30], rax
0x18002f6aa  test    rax, rax
0x18002f6ad  jz      short loc_18002F6C0
0x18002f6af  lea     rcx, [r15+40h]; struct IUnknown **
0x18002f6b3  cmp     [rcx], rax
0x18002f6b6  jz      short loc_18002F6C0
0x18002f6b8  mov     rdx, rax; struct IUnknown *
0x18002f6bb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002f6c0  lea     rcx, [r15+8]
0x18002f6c4  mov     rax, [r13+28h]
0x18002f6c8  mov     [rsp+68h+var_40], rax
0x18002f6cd  mov     rax, [r13+20h]
0x18002f6d1  mov     [rsp+68h+var_48], rax
0x18002f6d6  mov     r9, [r13+18h]
0x18002f6da  mov     r8, [rbp+var_28]
0x18002f6de  mov     edx, [rbp+arg_18]
0x18002f6e1  call    ?Initialize@IASCollection@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASCollection::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x18002f6e6  mov     ebx, eax
0x18002f6e8  test    eax, eax
0x18002f6ea  jns     short loc_18002F744
0x18002f6ec  mov     rax, cs:WPP_GLOBAL_Control
0x18002f6f3  cmp     rax, r14
0x18002f6f6  jz      short loc_18002F739
0x18002f6f8  cmp     byte ptr [rax+19h], 2
0x18002f6fc  jb      short loc_18002F739
0x18002f6fe  test    [rax+1Ch], esi
0x18002f701  jz      short loc_18002F739
0x18002f703  mov     edx, ebx
0x18002f705  lea     rcx, aPrapoliciesIni; "pRAPolicies->Initialize failed with 0x%"...
0x18002f70c  call    WppDbgPrint
0x18002f711  mov     edx, 0Eh
0x18002f716  mov     dword ptr [rsp+68h+var_48], ebx
0x18002f71a  lea     r9, aNpssdo; "NPSSDO"
0x18002f721  lea     r8, WPP_29831ab5fb1132e4cbdf61de86601dce_Traceguids
0x18002f728  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f72f  mov     rcx, [rcx+10h]
0x18002f733  call    WPP_SF_sd
0x18002f738  nop
0x18002f739  lea     rcx, [rbp+var_30]
0x18002f73d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f742  jmp     short loc_18002F760
0x18002f744  lea     rcx, [rbp+var_30]
0x18002f748  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f74d  mov     rcx, [rbp+var_38]
0x18002f751  mov     [rbp+var_38], 0
0x18002f759  mov     rax, [rbp+arg_20]
0x18002f75d  mov     [rax], rcx
0x18002f760  lea     rcx, [rbp+var_28]
0x18002f764  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f769  nop
0x18002f76a  lea     rcx, [rbp+pvarg]; this
0x18002f76e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002f773  nop
0x18002f774  lea     rcx, [rbp+var_38]
0x18002f778  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f77d  mov     eax, ebx
0x18002f77f  add     rsp, 68h
0x18002f783  pop     r15
0x18002f785  pop     r14
0x18002f787  pop     r13
0x18002f789  pop     rsi
0x18002f78a  pop     rbx
0x18002f78b  pop     rbp
0x18002f78c  retn
```
