# CSWbemObject::SetFromText_(ushort *,WbemObjectTextFormatEnum,long,IDispatch *)

- ea: `0x18002c0c0`
- end: `0x18002c1d6`
- name: `?SetFromText_@CSWbemObject@@UEAAJPEAGW4WbemObjectTextFormatEnum@@JPEAUIDispatch@@@Z`
- size: `278`
- prototype: `__int64 __usercall@<rax>(CSWbemObject *__hidden this@<rcx>, unsigned __int16 *@<rdx>, enum WbemObjectTextFormatEnum@<r8d>, int@<r9d>, struct IDispatch *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180006300`
- `0x18000c0b0`
- `0x180014f20`
- `0x180018038`
- `0x180024774`
- `0x18002c0c0`
- `0x18002c1dc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c146`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c146`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSWbemObject::SetFromText_(
        CSWbemObject *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        struct IDispatch *a5)
{
  int v9; // ebx
  struct IWbemContext *IWbemContext; // rax
  CWbemDispatchMgr *v11; // rcx
  LPVOID ppv; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+48h] [rbp-10h] BYREF
  struct IWbemClassObject *v15; // [rsp+98h] [rbp+40h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v9 = -2147217400;
LABEL_9:
    v11 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v11 )
      CWbemDispatchMgr::RaiseException(v11, v9);
    return (unsigned int)v9;
  }
  v9 = -2147217407;
  if ( !*((_QWORD *)this + 8) )
    goto LABEL_9;
  v14[0] = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, *((struct IServiceProvider **)this + 10));
  ATL::CComPtr<IWbemContext>::Attach(v14, IWbemContext);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_WbemObjectTextSrc, 0, 1u, &IID_IWbemObjectTextSrc, &ppv) >= 0 )
  {
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, _QWORD, _QWORD, struct IWbemClassObject **))(*(_QWORD *)ppv + 32LL))(
           ppv,
           a4,
           a2,
           a3,
           v14[0],
           &v15);
    if ( v9 >= 0 )
      CSWbemObject::SetIWbemClassObject(this, v15);
    ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v15);
  }
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&ppv);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(v14);
  if ( v9 < 0 )
    goto LABEL_9;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c0c0  push    rbp
0x18002c0c2  push    rbx
0x18002c0c3  push    rsi
0x18002c0c4  push    rdi
0x18002c0c5  push    r14
0x18002c0c7  push    r15
0x18002c0c9  mov     rbp, rsp
0x18002c0cc  sub     rsp, 58h
0x18002c0d0  mov     r14d, r9d
0x18002c0d3  mov     r15d, r8d
0x18002c0d6  mov     rsi, rdx
0x18002c0d9  mov     rdi, rcx
0x18002c0dc  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002c0e1  test    rsi, rsi
0x18002c0e4  jnz     short loc_18002C0F0
0x18002c0e6  mov     ebx, 80041008h
0x18002c0eb  jmp     loc_18002C1B7
0x18002c0f0  mov     ebx, 80041001h
0x18002c0f5  cmp     qword ptr [rdi+40h], 0
0x18002c0fa  jz      loc_18002C1B7
0x18002c100  mov     [rbp+var_10], 0
0x18002c108  mov     rdx, [rdi+50h]; struct IServiceProvider *
0x18002c10c  mov     rcx, [rbp+arg_20]; struct IDispatch *
0x18002c110  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002c115  mov     rdx, rax
0x18002c118  lea     rcx, [rbp+var_10]
0x18002c11c  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x18002c121  mov     [rbp+var_18], 0
0x18002c129  lea     rax, [rbp+var_18]
0x18002c12d  mov     [rsp+58h+ppv], rax; ppv
0x18002c132  lea     r9, IID_IWbemObjectTextSrc; riid
0x18002c139  xor     edx, edx; pUnkOuter
0x18002c13b  lea     r8d, [rdx+1]; dwClsContext
0x18002c13f  lea     rcx, CLSID_WbemObjectTextSrc; rclsid
0x18002c146  call    cs:__imp_CoCreateInstance
0x18002c14c  test    eax, eax
0x18002c14e  js      short loc_18002C1A0
0x18002c150  mov     [rbp+arg_8], 0
0x18002c158  mov     rcx, [rbp+var_18]
0x18002c15c  mov     rax, [rcx]
0x18002c15f  lea     rdx, [rbp+arg_8]
0x18002c163  mov     [rsp+58h+var_30], rdx
0x18002c168  mov     rdx, [rbp+var_10]
0x18002c16c  mov     [rsp+58h+ppv], rdx
0x18002c171  mov     r9d, r15d
0x18002c174  mov     r8, rsi
0x18002c177  mov     edx, r14d
0x18002c17a  mov     rax, [rax+20h]
0x18002c17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c183  mov     ebx, eax
0x18002c185  test    eax, eax
0x18002c187  js      short loc_18002C196
0x18002c189  mov     rdx, [rbp+arg_8]; struct IWbemClassObject *
0x18002c18d  mov     rcx, rdi; this
0x18002c190  call    ?SetIWbemClassObject@CSWbemObject@@QEAAXPEAUIWbemClassObject@@@Z; CSWbemObject::SetIWbemClassObject(IWbemClassObject *)
0x18002c195  nop
0x18002c196  lea     rcx, [rbp+arg_8]
0x18002c19a  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002c19f  nop
0x18002c1a0  lea     rcx, [rbp+var_18]
0x18002c1a4  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002c1a9  nop
0x18002c1aa  lea     rcx, [rbp+var_10]
0x18002c1ae  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002c1b3  test    ebx, ebx
0x18002c1b5  jns     short loc_18002C1C7
0x18002c1b7  mov     rcx, [rdi+48h]; this
0x18002c1bb  test    rcx, rcx
0x18002c1be  jz      short loc_18002C1C7
0x18002c1c0  mov     edx, ebx; int
0x18002c1c2  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002c1c7  mov     eax, ebx
0x18002c1c9  add     rsp, 58h
0x18002c1cd  pop     r15
0x18002c1cf  pop     r14
0x18002c1d1  pop     rdi
0x18002c1d2  pop     rsi
0x18002c1d3  pop     rbx
0x18002c1d4  pop     rbp
0x18002c1d5  retn
```
