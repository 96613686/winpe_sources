# GetGuestOSIntrinsicItems(IVmWmiClientContext *,IVmmsVirtualMachineObject *,tagSAFEARRAY * *,tagSAFEARRAY * *)

- ea: `0x14005cba8`
- end: `0x14005d141`
- name: `?GetGuestOSIntrinsicItems@@YAHPEAUIVmWmiClientContext@@PEAUIVmmsVirtualMachineObject@@PEAPEAUtagSAFEARRAY@@2@Z`
- size: `1433`
- prototype: `__int64 __fastcall(struct IVmWmiClientContext *, struct IVmmsVirtualMachineObject *, struct tagSAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140764a2c`

## callees

- `0x14002f1c4`
- `0x140034404`
- `0x14005c630`
- `0x14005cba8`
- `0x14005d148`
- `0x14005d970`
- `0x14005df58`
- `0x14005eee4`
- `0x140081f68`
- `0x140084120`
- `0x140084480`
- `0x140188e18`
- `0x1404828e0`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005cea9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005cf03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005cea9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005cf03`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ccc4`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ccc4`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d02e`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d086`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d02e`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d086`
- `OLEAUT32!__imp_VariantInit` at `0x14005cd05`
- `OLEAUT32!__imp_VariantInit` at `0x14005cd05`
- `OLEAUT32!__imp_VariantClear` at `0x14005d070`
- `OLEAUT32!__imp_VariantClear` at `0x14005d070`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005cd7e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005ce2b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005ce5f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005cd7e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005ce2b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14005ce5f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005cfeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d001`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d05f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005cfeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d001`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14005d05f`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14005cbf5`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14005cc34`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14005cbf5`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14005cc34`

## string_xrefs

- `0x14005cce2`: `onecore\vm\common\vml\VmBstr.h`
- `0x14005cc15`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005cc57`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005cd95`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d11a`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005d12f`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14005cc94`: `Msvm_KvpExchangeComponent`
- `0x14005cfd0`: `Msvm_KvpExchangeComponent for VM %ws returned malformed Guest OS intrinsic data item:\n\n%ws\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_BOOL8 __fastcall GetGuestOSIntrinsicItems(
        SAFEARRAY *a1,
        struct IVmmsVirtualMachineObject *a2,
        struct tagSAFEARRAY **a3,
        struct tagSAFEARRAY **a4)
{
  struct tagSAFEARRAY **v4; // r12
  struct tagSAFEARRAY **v5; // r14
  SAFEARRAY *v7; // rdi
  __int64 WmiLogicalDeviceObject; // rsi
  OLECHAR *v9; // r14
  int v10; // eax
  HRESULT v11; // eax
  _QWORD *v12; // rdx
  __int64 v13; // r13
  unsigned int v14; // r12d
  HRESULT v15; // eax
  HRESULT v16; // eax
  SAFEARRAY *v17; // rcx
  int v18; // ebx
  unsigned int v19; // edi
  __int64 v20; // r15
  int v21; // eax
  unsigned int v22; // ecx
  USHORT *v23; // rdi
  int v24; // ebx
  __int64 v25; // r15
  int v26; // eax
  char *v27; // rbx
  __int64 v28; // rax
  unsigned int v29; // eax
  SAFEARRAY *v30; // rcx
  BOOL v31; // ebx
  int v33; // [rsp+20h] [rbp-E0h]
  struct tagSAFEARRAY **p_pvarg; // [rsp+20h] [rbp-E0h]
  int v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  SAFEARRAY *v36; // [rsp+38h] [rbp-C8h] BYREF
  SAFEARRAY *Vector; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-B8h] BYREF
  SAFEARRAY *v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ElementCount; // [rsp+58h] [rbp-A8h]
  SAFEARRAY *v41; // [rsp+60h] [rbp-A0h]
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  struct tagSAFEARRAY **v43; // [rsp+70h] [rbp-90h]
  _QWORD *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  struct IVmmsVirtualMachineObject *v46; // [rsp+88h] [rbp-78h]
  Vml *v47; // [rsp+90h] [rbp-70h]
  struct tagSAFEARRAY **v48; // [rsp+98h] [rbp-68h]
  BSTR v49; // [rsp+A0h] [rbp-60h] BYREF
  void *ppvData[2]; // [rsp+A8h] [rbp-58h] BYREF
  SAFEARRAY *v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  SAFEARRAY *v52[2]; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = a4;
  v48 = a4;
  v5 = a3;
  v43 = a3;
  v46 = a2;
  Vector = SafeArrayCreateVectorEx(8u, 0, 0, 0);
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      v33);
  v7 = SafeArrayCreateVectorEx(0xCu, 0, 0, 0);
  v39 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      v33);
  v45 = 0;
  v36 = a1;
  if ( a1 )
    (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&a1->cDims + 8LL))(a1);
  WmiLogicalDeviceObject = GetWmiLogicalDeviceObject(&v36, (OLECHAR *)L"Msvm_KvpExchangeComponent");
  v45 = WmiLogicalDeviceObject;
  if ( WmiLogicalDeviceObject )
  {
    v49 = 0;
    v9 = SysAllocString(L"GuestIntrinsicExchangeItems");
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
        (const char *)0x8007000ELL,
        v33);
    Vml::VmBstr::Clear((Vml::VmBstr *)&v49);
    v49 = v9;
    VariantInit(&pvarg);
    p_pvarg = (struct tagSAFEARRAY **)&pvarg;
    v10 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *, __int64, BSTR *))(*(_QWORD *)WmiLogicalDeviceObject + 32LL))(
            WmiLogicalDeviceObject,
            a1,
            1,
            &v49);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x672,
        (unsigned int)"onecore\\vm\\vmms\\wmi\\wmiutilities.cpp",
        (const char *)(unsigned int)v10,
        (int)&pvarg);
    if ( pvarg.vt == 8200 )
    {
      ppvData[0] = pvarg.bstrVal;
      ppvData[1] = 0;
      v11 = SafeArrayAccessData(pvarg.parray, &ppvData[1]);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7D0,
          (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
          (const char *)(unsigned int)v11,
          (int)&pvarg);
      ElementCount = Vml::VmSafeArrayAccessor::GetElementCount((Vml::VmSafeArrayAccessor *)ppvData);
      v12 = ppvData[1];
      v44 = ppvData[1];
      v13 = 0;
      if ( ElementCount )
      {
        do
        {
          v47 = (Vml *)v12[v13];
          bstrString = 0;
          psa = 0;
          v36 = 0;
          Vml::VmlWmiParseEmbeddedInstance(
            v47,
            (const unsigned __int16 *)&bstrString,
            (unsigned __int16 **)&psa,
            &v36,
            p_pvarg);
          v14 = Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&psa);
          v52[0] = psa;
          v52[1] = 0;
          v15 = SafeArrayAccessData(psa, (void **)&v52[1]);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7B2,
              (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
              (const char *)(unsigned int)v15,
              (int)p_pvarg);
          v51[0] = v36;
          v51[1] = 0;
          v16 = SafeArrayAccessData(v36, (void **)&v51[1]);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7B2,
              (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
              (const char *)(unsigned int)v16,
              (int)p_pvarg);
          v17 = v52[1];
          *(SAFEARRAY **)v35 = v52[1];
          v41 = v51[1];
          v18 = 0;
          v19 = v14;
          while ( v18 != v19 )
          {
            v20 = v18 + ((v19 - v18) >> 1);
            v21 = _o__wcsicmp(L"Name", *((_QWORD *)&v17->cDims + v20));
            if ( !v21 )
            {
              v23 = &v41->cDims + 12 * v20;
              v17 = *(SAFEARRAY **)v35;
              goto LABEL_28;
            }
            v22 = v18 + ((v19 - v18) >> 1);
            if ( v21 >= 0 )
              v22 = v19;
            v19 = v22;
            if ( v21 >= 0 )
              v18 = v20 + 1;
            v17 = *(SAFEARRAY **)v35;
          }
          v23 = 0;
LABEL_28:
          v24 = 0;
          while ( v24 != v14 )
          {
            v25 = v24 + ((v14 - v24) >> 1);
            v26 = _o__wcsicmp(L"Data", *((_QWORD *)&v17->cDims + v25));
            if ( !v26 )
            {
              v27 = (char *)v41 + 24 * v25;
              goto LABEL_36;
            }
            if ( v26 >= 0 )
            {
              v24 = v25 + 1;
              LODWORD(v25) = v14;
            }
            v14 = v25;
            v17 = *(SAFEARRAY **)v35;
          }
          v27 = 0;
LABEL_36:
          if ( v23 && *v23 == 8 && v27 )
          {
            v35[0] = 0;
            if ( (unsigned int)Vml::VmSafeArray::Insert((Vml::VmSafeArray *)&Vector, v23 + 4, 1u, v35) )
            {
              Vml::VmSafeArray::InsertAt((Vml::VmSafeArray *)&v39, v35[0], v27);
            }
            else if ( (unsigned int)VmlIsDebugTraceEnabled(32865) )
            {
              VmlDebugTrace(
                32865,
                L"Duplicate guest OS intrinsic data item found! Name = \"%ws\"\n",
                *((_QWORD *)v23 + 1));
            }
          }
          else if ( (unsigned int)VmlIsDebugTraceEnabled(32865) )
          {
            v28 = (*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v46 + 32LL))(v46);
            VmlDebugTrace(
              32865,
              L"Msvm_KvpExchangeComponent for VM %ws returned malformed Guest OS intrinsic data item:\n\n%ws\n",
              v28,
              v47);
          }
          if ( v51[0] )
            SafeArrayUnaccessData(v51[0]);
          if ( v52[0] )
            SafeArrayUnaccessData(v52[0]);
          Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v36);
          Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&psa);
          if ( bstrString )
            SysFreeString(bstrString);
          v13 = (unsigned int)(v13 + 1);
          v12 = v44;
        }
        while ( (unsigned int)v13 < ElementCount );
        v7 = v39;
        v4 = v48;
      }
      if ( ppvData[0] )
        SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
    }
    VariantClear(&pvarg);
    if ( v49 )
      SysFreeString(v49);
    v5 = v43;
  }
  v29 = Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&Vector);
  if ( v29 )
  {
    v30 = Vector;
    Vector = 0;
    *v5 = v30;
    v39 = 0;
    *v4 = v7;
  }
  v31 = v29 != 0;
  if ( WmiLogicalDeviceObject )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)WmiLogicalDeviceObject + 16LL))(WmiLogicalDeviceObject);
  Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v39);
  Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&Vector);
  return v31;
}

```

## disassembly

```asm
0x14005cba8  push    rbp
0x14005cbaa  push    rbx
0x14005cbab  push    rsi
0x14005cbac  push    rdi
0x14005cbad  push    r12
0x14005cbaf  push    r13
0x14005cbb1  push    r14
0x14005cbb3  push    r15
0x14005cbb5  lea     rbp, [rsp-8]
0x14005cbba  sub     rsp, 108h
0x14005cbc1  mov     rax, cs:__security_cookie
0x14005cbc8  xor     rax, rsp
0x14005cbcb  mov     [rbp+40h+var_50], rax
0x14005cbcf  mov     r12, r9
0x14005cbd2  mov     [rbp+40h+var_A8], r9
0x14005cbd6  mov     r14, r8
0x14005cbd9  mov     [rsp+140h+var_D0], r8
0x14005cbde  mov     r15, rdx
0x14005cbe1  mov     [rbp+40h+var_B8], rdx
0x14005cbe5  mov     rbx, rcx
0x14005cbe8  mov     ecx, 8; vt
0x14005cbed  xor     r9d, r9d; pvExtra
0x14005cbf0  xor     r8d, r8d; cElements
0x14005cbf3  xor     edx, edx; lLbound
0x14005cbf5  call    cs:__imp_SafeArrayCreateVectorEx
0x14005cbfc  nop     dword ptr [rax+rax+00h]
0x14005cc01  mov     [rsp+140h+var_100], rax
0x14005cc06  test    rax, rax
0x14005cc09  jnz     short loc_14005CC27
0x14005cc0b  mov     rcx, [rbp+48h]; this
0x14005cc0f  mov     r9d, 8007000Eh; char *
0x14005cc15  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005cc1c  mov     edx, 1D9h; void *
0x14005cc21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005cc27  mov     ecx, 0Ch; vt
0x14005cc2c  xor     r9d, r9d; pvExtra
0x14005cc2f  xor     r8d, r8d; cElements
0x14005cc32  xor     edx, edx; lLbound
0x14005cc34  call    cs:__imp_SafeArrayCreateVectorEx
0x14005cc3b  nop     dword ptr [rax+rax+00h]
0x14005cc40  mov     rdi, rax
0x14005cc43  mov     [rsp+140h+var_F0], rax
0x14005cc48  test    rax, rax
0x14005cc4b  jnz     short loc_14005CC69
0x14005cc4d  mov     rcx, [rbp+48h]; this
0x14005cc51  mov     r9d, 8007000Eh; char *
0x14005cc57  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005cc5e  mov     edx, 1D9h; void *
0x14005cc63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005cc69  mov     [rbp+40h+var_C0], 0
0x14005cc71  mov     [rsp+140h+var_108], rbx
0x14005cc76  test    rbx, rbx
0x14005cc79  jz      short loc_14005CC8A
0x14005cc7b  mov     rax, [rbx]
0x14005cc7e  mov     rcx, rbx
0x14005cc81  mov     rax, [rax+8]
0x14005cc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cc8a  lea     r9, IC_KVPEXCHANGE_DEVICE_CLASS_ID
0x14005cc91  mov     r8, r15
0x14005cc94  lea     rdx, ?MsvmKvpExchangeComponent@@3QBGB; "Msvm_KvpExchangeComponent"
0x14005cc9b  lea     rcx, [rsp+140h+var_108]; void *
0x14005cca0  call    ?GetWmiLogicalDeviceObject@@YAPEAUIVmWmiObject@@V?$VmComPtr@UIVmWmiClientContext@@@Vml@@PEBGPEAUIVmmsVirtualMachineObject@@AEBU_GUID@@H@Z; GetWmiLogicalDeviceObject(Vml::VmComPtr<IVmWmiClientContext>,ushort const *,IVmmsVirtualMachineObject *,_GUID const &,int)
0x14005cca5  mov     rsi, rax
0x14005cca8  mov     [rbp+40h+var_C0], rax
0x14005ccac  test    rax, rax
0x14005ccaf  jz      loc_14005D097
0x14005ccb5  mov     [rbp+40h+var_A0], 0
0x14005ccbd  lea     rcx, aGuestintrinsic_0; "GuestIntrinsicExchangeItems"
0x14005ccc4  call    cs:__imp_SysAllocString
0x14005cccb  nop     dword ptr [rax+rax+00h]
0x14005ccd0  mov     r14, rax
0x14005ccd3  test    rax, rax
0x14005ccd6  jnz     short loc_14005CCF4
0x14005ccd8  mov     rcx, [rbp+48h]; this
0x14005ccdc  mov     r9d, 8007000Eh; char *
0x14005cce2  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmBstr.h"
0x14005cce9  mov     edx, 254h; void *
0x14005ccee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ccf4  lea     rcx, [rbp+40h+var_A0]; this
0x14005ccf8  call    ?Clear@VmBstr@Vml@@QEAAXXZ; Vml::VmBstr::Clear(void)
0x14005ccfd  mov     [rbp+40h+var_A0], r14
0x14005cd01  lea     rcx, [rbp+40h+pvarg]; pvarg
0x14005cd05  call    cs:__imp_VariantInit
0x14005cd0c  nop     dword ptr [rax+rax+00h]
0x14005cd11  nop
0x14005cd12  mov     rax, [rsi]
0x14005cd15  lea     rcx, [rbp+40h+pvarg]
0x14005cd19  mov     [rsp+140h+var_120], rcx; int
0x14005cd1e  lea     r9, [rbp+40h+var_A0]
0x14005cd22  mov     r8d, 1
0x14005cd28  mov     rdx, rbx
0x14005cd2b  mov     rcx, rsi
0x14005cd2e  mov     rax, [rax+20h]
0x14005cd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cd37  mov     rcx, [rbp+48h]; this
0x14005cd3b  test    eax, eax
0x14005cd3d  jns     short loc_14005CD54
0x14005cd3f  mov     r9d, eax; char *
0x14005cd42  lea     r8, aOnecoreVmVmmsW_162; "onecore\\vm\\vmms\\wmi\\wmiutilities.cp"...
0x14005cd49  mov     edx, 672h; void *
0x14005cd4e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005cd54  mov     eax, 2008h
0x14005cd59  cmp     ax, word ptr [rbp+40h+pvarg]
0x14005cd5d  jnz     loc_14005D06C
0x14005cd63  xorps   xmm0, xmm0
0x14005cd66  movups  xmmword ptr [rbp+40h+ppvData], xmm0
0x14005cd6a  mov     rcx, qword ptr [rbp+40h+pvarg+8]; psa
0x14005cd6e  mov     [rbp+40h+ppvData], rcx
0x14005cd72  mov     [rbp+40h+ppvData+8], 0
0x14005cd7a  lea     rdx, [rbp+40h+ppvData+8]; ppvData
0x14005cd7e  call    cs:__imp_SafeArrayAccessData
0x14005cd85  nop     dword ptr [rax+rax+00h]
0x14005cd8a  mov     rcx, [rbp+48h]; this
0x14005cd8e  test    eax, eax
0x14005cd90  jns     short loc_14005CDA7
0x14005cd92  mov     r9d, eax; char *
0x14005cd95  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14005cd9c  mov     edx, 7D0h; void *
0x14005cda1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005cda7  lea     rcx, [rbp+40h+ppvData]; this
0x14005cdab  call    ?GetElementCount@VmSafeArrayAccessor@Vml@@QEBAIXZ; Vml::VmSafeArrayAccessor::GetElementCount(void)
0x14005cdb0  mov     [rsp+140h+var_E8], eax
0x14005cdb4  mov     rdx, [rbp+40h+ppvData+8]
0x14005cdb8  mov     [rsp+140h+var_C8], rdx
0x14005cdbd  xor     r13d, r13d
0x14005cdc0  test    eax, eax
0x14005cdc2  jz      loc_14005D056
0x14005cdc8  mov     rax, [rdx+r13*8]
0x14005cdcc  mov     [rbp+40h+var_B0], rax
0x14005cdd0  mov     [rsp+140h+bstrString], 0
0x14005cdd9  mov     [rsp+140h+psa], 0
0x14005cde2  mov     [rsp+140h+var_108], 0
0x14005cdeb  lea     r9, [rsp+140h+var_108]; struct tagSAFEARRAY **
0x14005cdf0  lea     r8, [rsp+140h+psa]; unsigned __int16 **
0x14005cdf5  lea     rdx, [rsp+140h+bstrString]; unsigned __int16 *
0x14005cdfa  mov     rcx, rax; this
0x14005cdfd  call    ?VmlWmiParseEmbeddedInstance@Vml@@YAXPEBGPEAPEAGPEAPEAUtagSAFEARRAY@@2@Z; Vml::VmlWmiParseEmbeddedInstance(ushort const *,ushort * *,tagSAFEARRAY * *,tagSAFEARRAY * *)
0x14005ce02  lea     rcx, [rsp+140h+psa]; this
0x14005ce07  call    ?GetElementCount@VmSafeArray@Vml@@QEBAIXZ; Vml::VmSafeArray::GetElementCount(void)
0x14005ce0c  mov     r12d, eax
0x14005ce0f  xorps   xmm0, xmm0
0x14005ce12  movups  xmmword ptr [rbp+40h+var_78], xmm0
0x14005ce16  mov     rcx, [rsp+140h+psa]; psa
0x14005ce1b  mov     [rbp+40h+var_78], rcx
0x14005ce1f  mov     [rbp+40h+var_78+8], 0
0x14005ce27  lea     rdx, [rbp+40h+var_78+8]; ppvData
0x14005ce2b  call    cs:__imp_SafeArrayAccessData
0x14005ce32  nop     dword ptr [rax+rax+00h]
0x14005ce37  mov     rcx, [rbp+48h]; this
0x14005ce3b  test    eax, eax
0x14005ce3d  js      loc_14005D12C
0x14005ce43  xorps   xmm0, xmm0
0x14005ce46  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x14005ce4a  mov     rcx, [rsp+140h+var_108]; psa
0x14005ce4f  mov     [rbp+40h+var_88], rcx
0x14005ce53  mov     [rbp+40h+var_88+8], 0
0x14005ce5b  lea     rdx, [rbp+40h+var_88+8]; ppvData
0x14005ce5f  call    cs:__imp_SafeArrayAccessData
0x14005ce66  nop     dword ptr [rax+rax+00h]
0x14005ce6b  mov     rcx, [rbp+48h]; this
0x14005ce6f  test    eax, eax
0x14005ce71  js      loc_14005D117
0x14005ce77  mov     rcx, [rbp+40h+var_78+8]
0x14005ce7b  mov     qword ptr [rsp+140h+var_110], rcx
0x14005ce80  mov     rax, [rbp+40h+var_88+8]
0x14005ce84  mov     [rsp+140h+var_E0], rax
0x14005ce89  xor     ebx, ebx
0x14005ce8b  mov     edi, r12d
0x14005ce8e  cmp     ebx, edi
0x14005ce90  jz      short loc_14005CEE3
0x14005ce92  mov     r15d, edi
0x14005ce95  sub     r15d, ebx
0x14005ce98  shr     r15d, 1
0x14005ce9b  add     r15d, ebx
0x14005ce9e  mov     rdx, [rcx+r15*8]
0x14005cea2  lea     rcx, aName; "Name"
0x14005cea9  call    cs:__imp__o__wcsicmp
0x14005ceb0  nop     dword ptr [rax+rax+00h]
0x14005ceb5  test    eax, eax
0x14005ceb7  jz      short loc_14005CECF
0x14005ceb9  mov     ecx, r15d
0x14005cebc  cmovns  ecx, edi
0x14005cebf  mov     edi, ecx
0x14005cec1  lea     ecx, [r15+1]
0x14005cec5  cmovns  ebx, ecx
0x14005cec8  mov     rcx, qword ptr [rsp+140h+var_110]
0x14005cecd  jmp     short loc_14005CE8E
0x14005cecf  lea     rax, [r15+r15*2]
0x14005ced3  mov     rcx, [rsp+140h+var_E0]
0x14005ced8  lea     rdi, [rcx+rax*8]
0x14005cedc  mov     rcx, qword ptr [rsp+140h+var_110]
0x14005cee1  jmp     short loc_14005CEE5
0x14005cee3  xor     edi, edi
0x14005cee5  xor     ebx, ebx
0x14005cee7  cmp     ebx, r12d
0x14005ceea  jz      short loc_14005CF37
0x14005ceec  mov     r15d, r12d
0x14005ceef  sub     r15d, ebx
0x14005cef2  shr     r15d, 1
0x14005cef5  add     r15d, ebx
0x14005cef8  mov     rdx, [rcx+r15*8]
0x14005cefc  lea     rcx, aData; "Data"
0x14005cf03  call    cs:__imp__o__wcsicmp
0x14005cf0a  nop     dword ptr [rax+rax+00h]
0x14005cf0f  test    eax, eax
0x14005cf11  jz      short loc_14005CF28
0x14005cf13  lea     ecx, [r15+1]
0x14005cf17  cmovns  ebx, ecx
0x14005cf1a  cmovns  r15d, r12d
0x14005cf1e  mov     r12d, r15d
0x14005cf21  mov     rcx, qword ptr [rsp+140h+var_110]
0x14005cf26  jmp     short loc_14005CEE7
0x14005cf28  lea     rax, [r15+r15*2]
0x14005cf2c  mov     rcx, [rsp+140h+var_E0]
0x14005cf31  lea     rbx, [rcx+rax*8]
0x14005cf35  jmp     short loc_14005CF39
0x14005cf37  xor     ebx, ebx
0x14005cf39  test    rdi, rdi
0x14005cf3c  jz      short loc_14005CFA8
0x14005cf3e  mov     eax, 8
0x14005cf43  cmp     ax, [rdi]
0x14005cf46  jnz     short loc_14005CFA8
0x14005cf48  test    rbx, rbx
0x14005cf4b  jz      short loc_14005CFA8
0x14005cf4d  mov     [rsp+140h+var_110], 0
0x14005cf55  lea     r9, [rsp+140h+var_110]; int *
0x14005cf5a  lea     r8d, [rax-7]; unsigned int
0x14005cf5e  lea     rdx, [rdi+8]; void *
0x14005cf62  lea     rcx, [rsp+140h+var_100]; this
0x14005cf67  call    ?Insert@VmSafeArray@Vml@@QEAAHPEBXKPEAJ@Z; Vml::VmSafeArray::Insert(void const *,ulong,long *)
0x14005cf6c  test    eax, eax
0x14005cf6e  jz      short loc_14005CF83
0x14005cf70  mov     r8, rbx; void *
0x14005cf73  mov     edx, [rsp+140h+var_110]; int
0x14005cf77  lea     rcx, [rsp+140h+var_F0]; this
0x14005cf7c  call    ?InsertAt@VmSafeArray@Vml@@QEAAXJPEBX@Z; Vml::VmSafeArray::InsertAt(long,void const *)
0x14005cf81  jmp     short loc_14005CFE2
0x14005cf83  mov     ecx, 8061h
0x14005cf88  call    VmlIsDebugTraceEnabled
0x14005cf8d  test    eax, eax
0x14005cf8f  jz      short loc_14005CFE2
0x14005cf91  mov     r8, [rdi+8]
0x14005cf95  lea     rdx, aDuplicateGuest; "Duplicate guest OS intrinsic data item "...
0x14005cf9c  mov     ecx, 8061h
0x14005cfa1  call    VmlDebugTrace
0x14005cfa6  jmp     short loc_14005CFE2
0x14005cfa8  mov     ecx, 8061h
0x14005cfad  call    VmlIsDebugTraceEnabled
0x14005cfb2  test    eax, eax
0x14005cfb4  jz      short loc_14005CFE2
0x14005cfb6  mov     r15, [rbp+40h+var_B8]
0x14005cfba  mov     rax, [r15]
0x14005cfbd  mov     rcx, r15
0x14005cfc0  mov     rax, [rax+20h]
0x14005cfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cfc9  mov     r8, rax
0x14005cfcc  mov     r9, [rbp+40h+var_B0]
0x14005cfd0  lea     rdx, aMsvmKvpexchang_1; "Msvm_KvpExchangeComponent for VM %ws re"...
0x14005cfd7  mov     ecx, 8061h
0x14005cfdc  call    VmlDebugTrace
0x14005cfe1  nop
0x14005cfe2  mov     rcx, [rbp+40h+var_88]; psa
0x14005cfe6  test    rcx, rcx
0x14005cfe9  jz      short loc_14005CFF8
0x14005cfeb  call    cs:__imp_SafeArrayUnaccessData
0x14005cff2  nop     dword ptr [rax+rax+00h]
0x14005cff7  nop
0x14005cff8  mov     rcx, [rbp+40h+var_78]; psa
0x14005cffc  test    rcx, rcx
0x14005cfff  jz      short loc_14005D00E
0x14005d001  call    cs:__imp_SafeArrayUnaccessData
0x14005d008  nop     dword ptr [rax+rax+00h]
0x14005d00d  nop
0x14005d00e  lea     rcx, [rsp+140h+var_108]; this
0x14005d013  call    ??1VmSafeArray@Vml@@QEAA@XZ; Vml::VmSafeArray::~VmSafeArray(void)
0x14005d018  nop
0x14005d019  lea     rcx, [rsp+140h+psa]; this
0x14005d01e  call    ??1VmSafeArray@Vml@@QEAA@XZ; Vml::VmSafeArray::~VmSafeArray(void)
0x14005d023  nop
0x14005d024  mov     rcx, [rsp+140h+bstrString]; bstrString
0x14005d029  test    rcx, rcx
0x14005d02c  jz      short loc_14005D03A
0x14005d02e  call    cs:__imp_SysFreeString
0x14005d035  nop     dword ptr [rax+rax+00h]
0x14005d03a  inc     r13d
0x14005d03d  cmp     r13d, [rsp+140h+var_E8]
0x14005d042  mov     rdx, [rsp+140h+var_C8]
0x14005d047  jb      loc_14005CDC8
0x14005d04d  mov     rdi, [rsp+140h+var_F0]
0x14005d052  mov     r12, [rbp+40h+var_A8]
0x14005d056  mov     rcx, [rbp+40h+ppvData]; psa
0x14005d05a  test    rcx, rcx
0x14005d05d  jz      short loc_14005D06C
0x14005d05f  call    cs:__imp_SafeArrayUnaccessData
0x14005d066  nop     dword ptr [rax+rax+00h]
0x14005d06b  nop
0x14005d06c  lea     rcx, [rbp+40h+pvarg]; pvarg
0x14005d070  call    cs:__imp_VariantClear
0x14005d077  nop     dword ptr [rax+rax+00h]
0x14005d07c  nop
  ... truncated ...
```
