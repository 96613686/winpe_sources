# CSWbemObject::GetText_(WbemObjectTextFormatEnum,long,IDispatch *,ushort * *)

- ea: `0x18002b610`
- end: `0x18002b71f`
- name: `?GetText_@CSWbemObject@@UEAAJW4WbemObjectTextFormatEnum@@JPEAUIDispatch@@PEAPEAG@Z`
- size: `271`
- prototype: `int(CSWbemObject *__hidden this, enum WbemObjectTextFormatEnum, int, struct IDispatch *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180006300`
- `0x18000c0b0`
- `0x180014f20`
- `0x180018038`
- `0x180024774`
- `0x18002b610`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b6ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b6ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemObject::GetText_(
        CSWbemObject *this,
        unsigned int a2,
        unsigned int a3,
        struct IDispatch *a4,
        unsigned __int16 **ppv)
{
  unsigned __int16 **v9; // rsi
  int v10; // ebx
  struct IWbemContext *IWbemContext; // rax
  CWbemDispatchMgr *v12; // rcx
  _QWORD v14[9]; // [rsp+40h] [rbp-48h] BYREF

  ResetLastErrors();
  v9 = ppv;
  if ( !ppv )
  {
    v10 = -2147217400;
LABEL_7:
    v12 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v12 )
      CWbemDispatchMgr::RaiseException(v12, v10);
    return (unsigned int)v10;
  }
  v10 = -2147217407;
  if ( !*((_QWORD *)this + 8) )
    goto LABEL_7;
  *ppv = 0;
  v14[0] = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a4, *((struct IServiceProvider **)this + 10));
  ATL::CComPtr<IWbemContext>::Attach(v14, IWbemContext);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_WbemObjectTextSrc, 0, 1u, &IID_IWbemObjectTextSrc, (LPVOID *)&ppv) >= 0 )
    v10 = (*((__int64 (__fastcall **)(unsigned __int16 **, _QWORD, _QWORD, _QWORD, _QWORD, unsigned __int16 **))*ppv + 3))(
            ppv,
            a3,
            *((_QWORD *)this + 8),
            a2,
            v14[0],
            v9);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&ppv);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(v14);
  if ( v10 < 0 )
    goto LABEL_7;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b610  push    rbx
0x18002b612  push    rbp
0x18002b613  push    rsi
0x18002b614  push    rdi
0x18002b615  push    r14
0x18002b617  push    r15
0x18002b619  sub     rsp, 58h
0x18002b61d  mov     rbp, r9
0x18002b620  mov     r14d, r8d
0x18002b623  mov     r15d, edx
0x18002b626  mov     rdi, rcx
0x18002b629  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002b62e  mov     rsi, [rsp+88h+arg_20]
0x18002b636  test    rsi, rsi
0x18002b639  jnz     short loc_18002B645
0x18002b63b  mov     ebx, 80041008h
0x18002b640  jmp     loc_18002B700
0x18002b645  mov     ebx, 80041001h
0x18002b64a  cmp     qword ptr [rdi+40h], 0
0x18002b64f  jz      loc_18002B700
0x18002b655  mov     qword ptr [rsi], 0
0x18002b65c  mov     [rsp+88h+var_48], 0
0x18002b665  mov     rdx, [rdi+50h]; struct IServiceProvider *
0x18002b669  mov     rcx, rbp; struct IDispatch *
0x18002b66c  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002b671  mov     rdx, rax
0x18002b674  lea     rcx, [rsp+88h+var_48]
0x18002b679  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x18002b67e  mov     [rsp+88h+arg_20], 0
0x18002b68a  lea     rax, [rsp+88h+arg_20]
0x18002b692  mov     [rsp+88h+ppv], rax; ppv
0x18002b697  lea     r9, IID_IWbemObjectTextSrc; riid
0x18002b69e  xor     edx, edx; pUnkOuter
0x18002b6a0  lea     r8d, [rdx+1]; dwClsContext
0x18002b6a4  lea     rcx, CLSID_WbemObjectTextSrc; rclsid
0x18002b6ab  call    cs:__imp_CoCreateInstance
0x18002b6b1  test    eax, eax
0x18002b6b3  js      short loc_18002B6E4
0x18002b6b5  mov     rcx, [rsp+88h+arg_20]
0x18002b6bd  mov     rax, [rcx]
0x18002b6c0  mov     [rsp+88h+var_60], rsi
0x18002b6c5  mov     rdx, [rsp+88h+var_48]
0x18002b6ca  mov     [rsp+88h+ppv], rdx
0x18002b6cf  mov     r9d, r15d
0x18002b6d2  mov     r8, [rdi+40h]
0x18002b6d6  mov     edx, r14d
0x18002b6d9  mov     rax, [rax+18h]
0x18002b6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6e2  mov     ebx, eax
0x18002b6e4  lea     rcx, [rsp+88h+arg_20]
0x18002b6ec  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002b6f1  nop
0x18002b6f2  lea     rcx, [rsp+88h+var_48]
0x18002b6f7  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18002b6fc  test    ebx, ebx
0x18002b6fe  jns     short loc_18002B710
0x18002b700  mov     rcx, [rdi+48h]; this
0x18002b704  test    rcx, rcx
0x18002b707  jz      short loc_18002B710
0x18002b709  mov     edx, ebx; int
0x18002b70b  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002b710  mov     eax, ebx
0x18002b712  add     rsp, 58h
0x18002b716  pop     r15
0x18002b718  pop     r14
0x18002b71a  pop     rdi
0x18002b71b  pop     rsi
0x18002b71c  pop     rbp
0x18002b71d  pop     rbx
0x18002b71e  retn
```
