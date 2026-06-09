# CXWizardSourceStub::QueryInterface(_GUID const &,void * *)

- ea: `0x180019df0`
- end: `0x180019fd5`
- name: `?QueryInterface@CXWizardSourceStub@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `485`
- prototype: `int(CXWizardSourceStub *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019fe0`

## callees

- `0x18000ae04`
- `0x180019df0`
- `0x18002cb38`
- `0x18002cf38`
- `0x18002d320`
- `0x18002d838`
- `0x18002dbbc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019fca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019fca`

## pseudocode

```c
HRESULT __fastcall CXWizardSourceStub::QueryInterface(
        struct IPXWizardPropertyBagStub **this,
        const struct _GUID *a2,
        struct IXWizardTaskReport **ppv)
{
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IPXWizardInternalSource )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c2e592ad02ca3a8df39afd6e192fa8c5_Traceguids, 2147500034LL);
    return -2147467262;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardSource.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardSource.Data4 )
  {
    *ppv = (struct IXWizardTaskReport *)this;
    (*((void (__fastcall **)(char *))this[1] + 3))((char *)this + 8);
    (*((void (__fastcall **)(struct IPXWizardPropertyBagStub **))*this + 1))(this);
    return 0;
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardTaskReport.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardTaskReport.Data4 )
  {
    return CXWizardTaskReportProxy::HrCreateInstance(this[6], ppv);
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardPageReport.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardPageReport.Data4 )
  {
    return CXWizardPageReportProxy::HrCreateInstance(this[7], ppv);
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardTransaction.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardTransaction.Data4 )
  {
    return CXWizardTransactionProxy::HrCreateInstance(this[4], ppv);
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardNavigate.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardNavigate.Data4 )
  {
    return CXWizardNavigateProxy::HrCreateInstance(this[5], ppv);
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardPropertyBag.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardPropertyBag.Data4 )
  {
    return CXWizardPropertyBagProxy::HrCreateInstance(this[3], ppv);
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_ISimpleMarshal.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_ISimpleMarshal.Data4 )
    {
      return -2147467262;
    }
    return CoCreateInstance(&CLSID_CSimpleMarshal, 0, 0x401u, &IID_ISimpleMarshal, (LPVOID *)ppv);
  }
}

```

## disassembly

```asm
0x180019df0  push    rbx
0x180019df2  sub     rsp, 30h
0x180019df6  mov     rbx, rcx
0x180019df9  test    r8, r8
0x180019dfc  jnz     short loc_180019E05
0x180019dfe  mov     eax, 80004003h
0x180019e03  jmp     short loc_180019E5E
0x180019e05  mov     qword ptr [r8], 0
0x180019e0c  mov     rax, [rdx]
0x180019e0f  cmp     rax, qword ptr cs:IID_IPXWizardInternalSource.Data1
0x180019e16  jnz     short loc_180019E64
0x180019e18  mov     rax, [rdx+8]
0x180019e1c  cmp     rax, qword ptr cs:IID_IPXWizardInternalSource.Data4
0x180019e23  jnz     short loc_180019E64
0x180019e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e2c  lea     rax, WPP_GLOBAL_Control
0x180019e33  cmp     rcx, rax
0x180019e36  jz      short loc_180019E59
0x180019e38  test    byte ptr [rcx+1Ch], 2
0x180019e3c  jz      short loc_180019E59
0x180019e3e  mov     rcx, [rcx+10h]
0x180019e42  lea     r8, WPP_c2e592ad02ca3a8df39afd6e192fa8c5_Traceguids
0x180019e49  mov     edx, 0Ah
0x180019e4e  mov     r9d, 80004002h
0x180019e54  call    WPP_SF_d
0x180019e59  mov     eax, 80004002h
0x180019e5e  add     rsp, 30h
0x180019e62  pop     rbx
0x180019e63  retn
0x180019e64  mov     rax, [rdx]
0x180019e67  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180019e6e  jnz     short loc_180019E7D
0x180019e70  mov     rax, [rdx+8]
0x180019e74  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180019e7b  jz      short loc_180019E96
0x180019e7d  mov     rax, [rdx]
0x180019e80  cmp     rax, qword ptr cs:IID_IXWizardSource.Data1
0x180019e87  jnz     short loc_180019EBC
0x180019e89  mov     rax, [rdx+8]
0x180019e8d  cmp     rax, qword ptr cs:IID_IXWizardSource.Data4
0x180019e94  jnz     short loc_180019EBC
0x180019e96  add     rcx, 8
0x180019e9a  mov     [r8], rbx
0x180019e9d  mov     rax, [rcx]
0x180019ea0  mov     rax, [rax+18h]
0x180019ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ea9  mov     rax, [rbx]
0x180019eac  mov     rcx, rbx
0x180019eaf  mov     rax, [rax+8]
0x180019eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eb8  xor     eax, eax
0x180019eba  jmp     short loc_180019E5E
0x180019ebc  mov     rax, [rdx]
0x180019ebf  cmp     rax, qword ptr cs:IID_IXWizardTaskReport.Data1
0x180019ec6  jnz     short loc_180019EE6
0x180019ec8  mov     rax, [rdx+8]
0x180019ecc  cmp     rax, qword ptr cs:IID_IXWizardTaskReport.Data4
0x180019ed3  jnz     short loc_180019EE6
0x180019ed5  mov     rcx, [rcx+30h]; struct IPXWizardTaskReportStub *
0x180019ed9  mov     rdx, r8; struct IXWizardTaskReport **
0x180019edc  add     rsp, 30h
0x180019ee0  pop     rbx
0x180019ee1  jmp     ?HrCreateInstance@CXWizardTaskReportProxy@@SAJPEAUIPXWizardTaskReportStub@@PEAPEAUIXWizardTaskReport@@@Z; CXWizardTaskReportProxy::HrCreateInstance(IPXWizardTaskReportStub *,IXWizardTaskReport * *)
0x180019ee6  mov     rax, [rdx]
0x180019ee9  cmp     rax, qword ptr cs:IID_IXWizardPageReport.Data1
0x180019ef0  jnz     short loc_180019F10
0x180019ef2  mov     rax, [rdx+8]
0x180019ef6  cmp     rax, qword ptr cs:IID_IXWizardPageReport.Data4
0x180019efd  jnz     short loc_180019F10
0x180019eff  mov     rcx, [rcx+38h]; struct IPXWizardPageReportStub *
0x180019f03  mov     rdx, r8; struct IXWizardPageReport **
0x180019f06  add     rsp, 30h
0x180019f0a  pop     rbx
0x180019f0b  jmp     ?HrCreateInstance@CXWizardPageReportProxy@@SAJPEAUIPXWizardPageReportStub@@PEAPEAUIXWizardPageReport@@@Z; CXWizardPageReportProxy::HrCreateInstance(IPXWizardPageReportStub *,IXWizardPageReport * *)
0x180019f10  mov     rax, [rdx]
0x180019f13  cmp     rax, qword ptr cs:IID_IXWizardTransaction.Data1
0x180019f1a  jnz     short loc_180019F3A
0x180019f1c  mov     rax, [rdx+8]
0x180019f20  cmp     rax, qword ptr cs:IID_IXWizardTransaction.Data4
0x180019f27  jnz     short loc_180019F3A
0x180019f29  mov     rcx, [rcx+20h]; struct IPXWizardTransactionStub *
0x180019f2d  mov     rdx, r8; struct IXWizardTransaction **
0x180019f30  add     rsp, 30h
0x180019f34  pop     rbx
0x180019f35  jmp     ?HrCreateInstance@CXWizardTransactionProxy@@SAJPEAUIPXWizardTransactionStub@@PEAPEAUIXWizardTransaction@@@Z; CXWizardTransactionProxy::HrCreateInstance(IPXWizardTransactionStub *,IXWizardTransaction * *)
0x180019f3a  mov     rax, [rdx]
0x180019f3d  cmp     rax, qword ptr cs:IID_IXWizardNavigate.Data1
0x180019f44  jnz     short loc_180019F64
0x180019f46  mov     rax, [rdx+8]
0x180019f4a  cmp     rax, qword ptr cs:IID_IXWizardNavigate.Data4
0x180019f51  jnz     short loc_180019F64
0x180019f53  mov     rcx, [rcx+28h]; struct IPXWizardNavigateStub *
0x180019f57  mov     rdx, r8; struct IXWizardNavigate **
0x180019f5a  add     rsp, 30h
0x180019f5e  pop     rbx
0x180019f5f  jmp     ?HrCreateInstance@CXWizardNavigateProxy@@SAJPEAUIPXWizardNavigateStub@@PEAPEAUIXWizardNavigate@@@Z; CXWizardNavigateProxy::HrCreateInstance(IPXWizardNavigateStub *,IXWizardNavigate * *)
0x180019f64  mov     rax, [rdx]
0x180019f67  cmp     rax, qword ptr cs:IID_IXWizardPropertyBag.Data1
0x180019f6e  jnz     short loc_180019F8E
0x180019f70  mov     rax, [rdx+8]
0x180019f74  cmp     rax, qword ptr cs:IID_IXWizardPropertyBag.Data4
0x180019f7b  jnz     short loc_180019F8E
0x180019f7d  mov     rcx, [rcx+18h]; struct IPXWizardPropertyBagStub *
0x180019f81  mov     rdx, r8; struct IXWizardPropertyBag **
0x180019f84  add     rsp, 30h
0x180019f88  pop     rbx
0x180019f89  jmp     ?HrCreateInstance@CXWizardPropertyBagProxy@@SAJPEAUIPXWizardPropertyBagStub@@PEAPEAUIXWizardPropertyBag@@@Z; CXWizardPropertyBagProxy::HrCreateInstance(IPXWizardPropertyBagStub *,IXWizardPropertyBag * *)
0x180019f8e  mov     rax, [rdx]
0x180019f91  cmp     rax, qword ptr cs:IID_ISimpleMarshal.Data1
0x180019f98  jnz     loc_180019E59
0x180019f9e  mov     rax, [rdx+8]
0x180019fa2  cmp     rax, qword ptr cs:IID_ISimpleMarshal.Data4
0x180019fa9  jnz     loc_180019E59
0x180019faf  mov     [rsp+38h+ppv], r8; ppv
0x180019fb4  lea     r9, IID_ISimpleMarshal; riid
0x180019fbb  mov     r8d, 401h; dwClsContext
0x180019fc1  lea     rcx, CLSID_CSimpleMarshal; rclsid
0x180019fc8  xor     edx, edx; pUnkOuter
0x180019fca  call    cs:__imp_CoCreateInstance
0x180019fd0  jmp     loc_180019E5E
```
