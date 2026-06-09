# CSWbemObject::Refresh_(long,IDispatch *)

- ea: `0x18002bd60`
- end: `0x18002c05c`
- name: `?Refresh_@CSWbemObject@@UEAAJJPEAUIDispatch@@@Z`
- size: `764`
- prototype: `__int64 __fastcall(CSWbemObject *__hidden this, int, struct IDispatch *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000311c`
- `0x180006300`
- `0x1800077d0`
- `0x18000c0b0`
- `0x180014f20`
- `0x180018038`
- `0x180018130`
- `0x180019980`
- `0x180024774`
- `0x18002bd60`
- `0x18002c1dc`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002bfe9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bfe9`
- `OLEAUT32!__imp_VariantClear` at `0x18002c008`
- `OLEAUT32!__imp_VariantClear` at `0x18002c008`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002be6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002be6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSWbemObject::Refresh_(CSWbemObject *this, int a2, struct IDispatch *a3)
{
  int v6; // r14d
  bool v7; // r12
  struct IWbemContext *IWbemContext; // rax
  struct IWbemServices *IWbemServices; // rax
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rdi
  _QWORD *v13; // r15
  int v14; // eax
  CWbemDispatchMgr *v15; // rcx
  struct IWbemClassObject *v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  struct IWbemClassObject *v21; // [rsp+B0h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp+58h] BYREF

  v6 = -2147217407;
  ResetLastErrors();
  v7 = 0;
  if ( *((_QWORD *)this + 7) && *((_QWORD *)this + 8) )
  {
    v19 = 0;
    IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a3, *((struct IServiceProvider **)this + 10));
    ATL::CComPtr<IWbemContext>::Attach(&v19, IWbemContext);
    v18 = 0;
    IWbemServices = CSWbemServices::GetIWbemServices(*((CSWbemServices **)this + 7));
    ATL::CComPtr<IWbemServices>::Attach(&v18, IWbemServices);
    v10 = v18;
    if ( !v18 )
    {
LABEL_30:
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v18);
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v19);
      goto LABEL_31;
    }
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 32LL))(
            *((_QWORD *)this + 8),
            L"__GENUS",
            0,
            &pvarg,
            0,
            0);
    v12 = v19;
    if ( (v11 || pvarg.lVal != 1) && v19 || !*((_BYTE *)this + 96) )
      goto LABEL_22;
    v13 = (_QWORD *)((char *)this + 88);
    if ( !*((_QWORD *)this + 11) )
    {
      *((_BYTE *)this + 96) = 0;
      if ( CoCreateInstance(&CLSID_WbemRefresher, 0, 1u, &IID_IWbemRefresher, (LPVOID *)this + 11) >= 0 )
      {
        bstrString = 0;
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, BSTR *))*v13)(*v13, &IID_IWbemConfigureRefresher, &bstrString) >= 0 )
        {
          v17 = 0;
          LODWORD(v21) = 0;
          v14 = (*(__int64 (__fastcall **)(BSTR, __int64, _QWORD, _QWORD, __int64, struct IWbemClassObject **, struct IWbemClassObject **))(*(_QWORD *)bstrString + 32LL))(
                  bstrString,
                  v10,
                  *((_QWORD *)this + 8),
                  a2 & 0x20000,
                  v12,
                  &v17,
                  &v21);
          if ( v14 < 0 )
          {
            if ( v14 != -2147217386 )
              v7 = v14 != -2147217400;
          }
          else
          {
            *((_BYTE *)this + 96) = 1;
            CSWbemObject::SetIWbemClassObject(this, v17);
          }
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
          ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v17);
        }
        if ( !*((_BYTE *)this + 96) )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
          *v13 = 0;
        }
      }
    }
    if ( v7 )
      goto LABEL_27;
    if ( *((_BYTE *)this + 96) && *v13 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v13 + 24LL))(*v13, a2 & 1);
    }
    else
    {
LABEL_22:
      bstrString = 0;
      if ( CSWbemObjectPath::GetObjectPath(*((struct IWbemClassObject **)this + 8), (struct ATL::CComBSTR *)&bstrString) )
      {
        v21 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, __int64, struct IWbemClassObject **, _QWORD))(*(_QWORD *)v10 + 48LL))(
               v10,
               bstrString,
               a2 & 0xFFFFFFFE,
               v12,
               &v21,
               0);
        if ( v6 >= 0 )
          CSWbemObject::SetIWbemClassObject(this, v21);
        ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v21);
      }
      SysFreeString(bstrString);
    }
LABEL_27:
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    goto LABEL_30;
  }
LABEL_31:
  SetWbemError(*((const OLECHAR ***)this + 7));
  if ( v6 < 0 )
  {
    v15 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v15 )
      CWbemDispatchMgr::RaiseException(v15, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002bd60  mov     [rsp-38h+arg_8], rbx
0x18002bd65  push    rbp
0x18002bd66  push    rsi
0x18002bd67  push    rdi
0x18002bd68  push    r12
0x18002bd6a  push    r13
0x18002bd6c  push    r14
0x18002bd6e  push    r15
0x18002bd70  mov     rbp, rsp
0x18002bd73  sub     rsp, 70h
0x18002bd77  mov     rbx, r8
0x18002bd7a  mov     r13d, edx
0x18002bd7d  mov     rsi, rcx
0x18002bd80  mov     r14d, 80041001h
0x18002bd86  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002bd8b  xor     r12d, r12d
0x18002bd8e  cmp     [rsi+38h], r12
0x18002bd92  jz      loc_18002C022
0x18002bd98  cmp     [rsi+40h], r12
0x18002bd9c  jz      loc_18002C022
0x18002bda2  mov     [rbp+var_20], r12
0x18002bda6  mov     rdx, [rsi+50h]; struct IServiceProvider *
0x18002bdaa  mov     rcx, rbx; struct IDispatch *
0x18002bdad  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002bdb2  mov     rdx, rax
0x18002bdb5  lea     rcx, [rbp+var_20]
0x18002bdb9  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x18002bdbe  mov     [rbp+var_28], r12
0x18002bdc2  mov     rcx, [rsi+38h]; this
0x18002bdc6  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x18002bdcb  mov     rdx, rax
0x18002bdce  lea     rcx, [rbp+var_28]
0x18002bdd2  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x18002bdd7  mov     rbx, [rbp+var_28]
0x18002bddb  test    rbx, rbx
0x18002bdde  jz      loc_18002C00F
0x18002bde4  xorps   xmm0, xmm0
0x18002bde7  xor     eax, eax
0x18002bde9  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002bded  mov     qword ptr [rbp+pvarg+10h], rax
0x18002bdf1  mov     word ptr [rbp+pvarg], r12w
0x18002bdf6  mov     rcx, [rsi+40h]
0x18002bdfa  mov     rax, [rcx]
0x18002bdfd  mov     [rsp+70h+var_48], r12
0x18002be02  mov     [rsp+70h+ppv], r12
0x18002be07  lea     r9, [rbp+pvarg]
0x18002be0b  xor     r8d, r8d
0x18002be0e  lea     rdx, aGenus; "__GENUS"
0x18002be15  mov     rax, [rax+20h]
0x18002be19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be1e  mov     rdi, [rbp+var_20]
0x18002be22  lea     edx, [r12+1]
0x18002be27  test    eax, eax
0x18002be29  jnz     short loc_18002BE30
0x18002be2b  cmp     dword ptr [rbp+pvarg+8], edx
0x18002be2e  jz      short loc_18002BE39
0x18002be30  test    rdi, rdi
0x18002be33  jnz     loc_18002BF83
0x18002be39  cmp     [rsi+60h], r12b
0x18002be3d  jz      loc_18002BF83
0x18002be43  lea     r15, [rsi+58h]
0x18002be47  cmp     qword ptr [r15], 0
0x18002be4b  jnz     loc_18002BF55
0x18002be51  mov     byte ptr [rsi+60h], 0
0x18002be55  mov     [rsp+70h+ppv], r15; ppv
0x18002be5a  lea     r9, IID_IWbemRefresher; riid
0x18002be61  mov     r8d, edx; dwClsContext
0x18002be64  xor     edx, edx; pUnkOuter
0x18002be66  lea     rcx, CLSID_WbemRefresher; rclsid
0x18002be6d  call    cs:__imp_CoCreateInstance
0x18002be73  test    eax, eax
0x18002be75  js      loc_18002BF50
0x18002be7b  mov     [rbp+bstrString], 0
0x18002be83  mov     rcx, [r15]
0x18002be86  mov     rax, [rcx]
0x18002be89  lea     r8, [rbp+bstrString]
0x18002be8d  lea     rdx, IID_IWbemConfigureRefresher
0x18002be94  mov     rax, [rax]
0x18002be97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be9c  test    eax, eax
0x18002be9e  js      loc_18002BF34
0x18002bea4  mov     [rbp+var_30], 0
0x18002beac  mov     dword ptr [rbp+arg_0], 0
0x18002beb3  mov     rcx, [rbp+bstrString]
0x18002beb7  mov     rax, [rcx]
0x18002beba  mov     r9d, r13d
0x18002bebd  and     r9d, 20000h
0x18002bec4  lea     rdx, [rbp+arg_0]
0x18002bec8  mov     [rsp+70h+var_40], rdx
0x18002becd  lea     rdx, [rbp+var_30]
0x18002bed1  mov     [rsp+70h+var_48], rdx
0x18002bed6  mov     [rsp+70h+ppv], rdi
0x18002bedb  mov     r8, [rsi+40h]
0x18002bedf  mov     rdx, rbx
0x18002bee2  mov     rax, [rax+20h]
0x18002bee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beeb  test    eax, eax
0x18002beed  js      short loc_18002BF01
0x18002beef  mov     byte ptr [rsi+60h], 1
0x18002bef3  mov     rdx, [rbp+var_30]; struct IWbemClassObject *
0x18002bef7  mov     rcx, rsi; this
0x18002befa  call    ?SetIWbemClassObject@CSWbemObject@@QEAAXPEAUIWbemClassObject@@@Z; CSWbemObject::SetIWbemClassObject(IWbemClassObject *)
0x18002beff  jmp     short loc_18002BF1A
0x18002bf01  cmp     eax, 80041016h
0x18002bf06  jz      short loc_18002BF1A
0x18002bf08  movzx   r12d, r12b
0x18002bf0c  cmp     eax, 80041008h
0x18002bf11  mov     eax, 1
0x18002bf16  cmovnz  r12d, eax
0x18002bf1a  mov     rcx, [rbp+bstrString]
0x18002bf1e  mov     rax, [rcx]
0x18002bf21  mov     rax, [rax+10h]
0x18002bf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf2a  nop
0x18002bf2b  lea     rcx, [rbp+var_30]
0x18002bf2f  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002bf34  cmp     byte ptr [rsi+60h], 0
0x18002bf38  jnz     short loc_18002BF50
0x18002bf3a  mov     rcx, [r15]
0x18002bf3d  mov     rax, [rcx]
0x18002bf40  mov     rax, [rax+10h]
0x18002bf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf49  mov     qword ptr [r15], 0
0x18002bf50  mov     edx, 1
0x18002bf55  test    r12b, r12b
0x18002bf58  jnz     loc_18002BFF0
0x18002bf5e  xor     r12d, r12d
0x18002bf61  cmp     [rsi+60h], r12b
0x18002bf65  jz      short loc_18002BF83
0x18002bf67  mov     rcx, [r15]
0x18002bf6a  test    rcx, rcx
0x18002bf6d  jz      short loc_18002BF83
0x18002bf6f  mov     rax, [rcx]
0x18002bf72  and     edx, r13d
0x18002bf75  mov     rax, [rax+18h]
0x18002bf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf7e  mov     r14d, eax
0x18002bf81  jmp     short loc_18002BFF0
0x18002bf83  mov     [rbp+bstrString], r12
0x18002bf87  lea     rdx, [rbp+bstrString]; struct ATL::CComBSTR *
0x18002bf8b  mov     rcx, [rsi+40h]; struct IWbemClassObject *
0x18002bf8f  call    ?GetObjectPath@CSWbemObjectPath@@SA_NPEAUIWbemClassObject@@AEAVCComBSTR@ATL@@@Z; CSWbemObjectPath::GetObjectPath(IWbemClassObject *,ATL::CComBSTR &)
0x18002bf94  test    al, al
0x18002bf96  jz      short loc_18002BFE5
0x18002bf98  mov     [rbp+arg_0], r12
0x18002bf9c  mov     rax, [rbx]
0x18002bf9f  and     r13d, 0FFFFFFFEh
0x18002bfa3  mov     [rsp+70h+var_48], r12
0x18002bfa8  lea     rcx, [rbp+arg_0]
0x18002bfac  mov     [rsp+70h+ppv], rcx
0x18002bfb1  mov     r9, rdi
0x18002bfb4  mov     r8d, r13d
0x18002bfb7  mov     rdx, [rbp+bstrString]
0x18002bfbb  mov     rcx, rbx
0x18002bfbe  mov     rax, [rax+30h]
0x18002bfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfc7  mov     r14d, eax
0x18002bfca  test    eax, eax
0x18002bfcc  js      short loc_18002BFDB
0x18002bfce  mov     rdx, [rbp+arg_0]; struct IWbemClassObject *
0x18002bfd2  mov     rcx, rsi; this
0x18002bfd5  call    ?SetIWbemClassObject@CSWbemObject@@QEAAXPEAUIWbemClassObject@@@Z; CSWbemObject::SetIWbemClassObject(IWbemClassObject *)
0x18002bfda  nop
0x18002bfdb  lea     rcx, [rbp+arg_0]
0x18002bfdf  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002bfe4  nop
0x18002bfe5  mov     rcx, [rbp+bstrString]; bstrString
0x18002bfe9  call    cs:__imp_SysFreeString
0x18002bfef  nop
0x18002bff0  mov     eax, 0FFFh
0x18002bff5  cmp     word ptr [rbp+pvarg], ax
0x18002bff9  jnz     short loc_18002C004
0x18002bffb  mov     eax, 8
0x18002c000  mov     word ptr [rbp+pvarg], ax
0x18002c004  lea     rcx, [rbp+pvarg]; pvarg
0x18002c008  call    cs:__imp_VariantClear
0x18002c00e  nop
0x18002c00f  lea     rcx, [rbp+var_28]
0x18002c013  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002c018  nop
0x18002c019  lea     rcx, [rbp+var_20]
0x18002c01d  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002c022  mov     rcx, [rsi+38h]; this
0x18002c026  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18002c02b  test    r14d, r14d
0x18002c02e  jns     short loc_18002C041
0x18002c030  mov     rcx, [rsi+48h]; this
0x18002c034  test    rcx, rcx
0x18002c037  jz      short loc_18002C041
0x18002c039  mov     edx, r14d; int
0x18002c03c  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002c041  mov     eax, r14d
0x18002c044  mov     rbx, [rsp+70h+arg_8]
0x18002c04c  add     rsp, 70h
0x18002c050  pop     r15
0x18002c052  pop     r14
0x18002c054  pop     r13
0x18002c056  pop     r12
0x18002c058  pop     rdi
0x18002c059  pop     rsi
0x18002c05a  pop     rbp
0x18002c05b  retn
```
