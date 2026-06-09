# CXWizardSource::QueryInterface(_GUID const &,void * *)

- ea: `0x180024e40`
- end: `0x1800250aa`
- name: `?QueryInterface@CXWizardSource@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `618`
- prototype: `int(CXWizardSource *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800250b0`

## callees

- `0x18000ae04`
- `0x180024e40`
- `0x180026558`
- `0x180026b34`
- `0x180027458`
- `0x180027834`
- `0x180027c78`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002508b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002508b`

## pseudocode

```c
HRESULT __fastcall CXWizardSource::QueryInterface(
        CXWizardSource *this,
        const struct _GUID *a2,
        struct IXWizardTaskReport **ppv)
{
  __int64 v6; // rax
  BOOL v7; // ecx
  __int64 v8; // r9
  __int64 v9; // rax
  const struct CTask *v10; // rcx

  if ( !ppv )
    return -2147467261;
  v6 = *((_QWORD *)this + 7) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v6 )
    v6 = *((_QWORD *)this + 8) - *(_QWORD *)GUID_NULL.Data4;
  v7 = v6 == 0;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPXWizardInternalSource.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IPXWizardInternalSource.Data4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, "~", 2147500034LL);
    *ppv = 0;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardSource.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardSource.Data4 )
    {
      *ppv = this;
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8);
      (*(void (__fastcall **)(CXWizardSource *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardTaskReport.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardTaskReport.Data4
      && (!*((_QWORD *)this + 4) || v6) )
    {
      return CXWizardTaskReport::HrCreateInstance(*((const struct CTask **)this + 3), ppv);
    }
    v8 = 2LL * (v6 != 0);
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardPageReport.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardPageReport.Data4
      && *((_QWORD *)this + 4) )
    {
      return CXWizardPageReport::HrCreateInstance(
               (const struct _GUID *)((char *)this + 8 * v8 + 40),
               *((const struct CTask **)this + 3),
               ppv);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardTransaction.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardTransaction.Data4 )
    {
      v9 = *((_QWORD *)this + 4);
      if ( !v9 || !v7 || *(_DWORD *)(v9 + 136) == 2 || (*(_DWORD *)(v9 + 48) & 0x10000) != 0 )
        return CXWizardTransaction::HrCreateInstance(*((const struct CTask **)this + 3), ppv);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardNavigate.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardNavigate.Data4 )
    {
      v10 = (const struct CTask *)*((_QWORD *)this + 3);
      if ( (*((_DWORD *)v10 + 55) & 0x600) != 0 )
        return CXWizardNavigate::HrCreateInstance(v10, ppv);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXWizardPropertyBag.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IXWizardPropertyBag.Data4 )
    {
      return CXWizardPropertyBag::HrCreateInstance(
               (const struct _GUID *)((char *)this + 8 * v8 + 40),
               *(const struct IPXWizardPropertyBag **)(*((_QWORD *)this + 3) + 272LL),
               ppv);
    }
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleMarshal.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISimpleMarshal.Data4 )
    {
      return CoCreateInstance(&CLSID_CSimpleMarshal, 0, 0x401u, &IID_ISimpleMarshal, (LPVOID *)ppv);
    }
    *ppv = 0;
  }
  return -2147467262;
}

```

## disassembly

```asm
0x180024e40  mov     [rsp+arg_0], rbx
0x180024e45  push    rdi
0x180024e46  sub     rsp, 30h
0x180024e4a  mov     rdi, r8
0x180024e4d  mov     rbx, rcx
0x180024e50  test    r8, r8
0x180024e53  jnz     short loc_180024E5F
0x180024e55  mov     eax, 80004003h
0x180024e5a  jmp     loc_18002509F
0x180024e5f  mov     rax, [rcx+38h]
0x180024e63  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180024e6a  jnz     short loc_180024E77
0x180024e6c  mov     rax, [rcx+40h]
0x180024e70  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180024e77  xor     ecx, ecx
0x180024e79  test    rax, rax
0x180024e7c  mov     rax, [rdx]
0x180024e7f  setz    cl
0x180024e82  cmp     rax, qword ptr cs:IID_IPXWizardInternalSource.Data1
0x180024e89  jnz     short loc_180024ED8
0x180024e8b  mov     rax, [rdx+8]
0x180024e8f  cmp     rax, qword ptr cs:IID_IPXWizardInternalSource.Data4
0x180024e96  jnz     short loc_180024ED8
0x180024e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e9f  lea     rax, WPP_GLOBAL_Control
0x180024ea6  cmp     rcx, rax
0x180024ea9  jz      short loc_180024ECC
0x180024eab  test    byte ptr [rcx+1Ch], 2
0x180024eaf  jz      short loc_180024ECC
0x180024eb1  mov     rcx, [rcx+10h]
0x180024eb5  lea     r8, WPP_a4a0007ef10a39cdef6e9949875faa85_Traceguids; "~"
0x180024ebc  mov     edx, 0Ah
0x180024ec1  mov     r9d, 80004002h
0x180024ec7  call    WPP_SF_d
0x180024ecc  mov     qword ptr [rdi], 0
0x180024ed3  jmp     loc_18002509A
0x180024ed8  mov     rax, [rdx]
0x180024edb  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180024ee2  jnz     short loc_180024EF1
0x180024ee4  mov     rax, [rdx+8]
0x180024ee8  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180024eef  jz      short loc_180024F0A
0x180024ef1  mov     rax, [rdx]
0x180024ef4  cmp     rax, qword ptr cs:IID_IXWizardSource.Data1
0x180024efb  jnz     short loc_180024F33
0x180024efd  mov     rax, [rdx+8]
0x180024f01  cmp     rax, qword ptr cs:IID_IXWizardSource.Data4
0x180024f08  jnz     short loc_180024F33
0x180024f0a  lea     rcx, [rbx+8]
0x180024f0e  mov     [r8], rbx
0x180024f11  mov     rax, [rcx]
0x180024f14  mov     rax, [rax+18h]
0x180024f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f1d  mov     rax, [rbx]
0x180024f20  mov     rcx, rbx
0x180024f23  mov     rax, [rax+8]
0x180024f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f2c  xor     eax, eax
0x180024f2e  jmp     loc_18002509F
0x180024f33  mov     rax, [rdx]
0x180024f36  cmp     rax, qword ptr cs:IID_IXWizardTaskReport.Data1
0x180024f3d  jnz     short loc_180024F68
0x180024f3f  mov     rax, [rdx+8]
0x180024f43  cmp     rax, qword ptr cs:IID_IXWizardTaskReport.Data4
0x180024f4a  jnz     short loc_180024F68
0x180024f4c  cmp     qword ptr [rbx+20h], 0
0x180024f51  jz      short loc_180024F57
0x180024f53  test    ecx, ecx
0x180024f55  jnz     short loc_180024F68
0x180024f57  mov     rcx, [rbx+18h]; struct CTask *
0x180024f5b  mov     rdx, rdi; struct IXWizardTaskReport **
0x180024f5e  call    ?HrCreateInstance@CXWizardTaskReport@@SAJPEBVCTask@@PEAPEAUIXWizardTaskReport@@@Z; CXWizardTaskReport::HrCreateInstance(CTask const *,IXWizardTaskReport * *)
0x180024f63  jmp     loc_18002509F
0x180024f68  mov     rax, [rdx]
0x180024f6b  mov     r9d, ecx
0x180024f6e  xor     r9, 1
0x180024f72  add     r9, r9
0x180024f75  cmp     rax, qword ptr cs:IID_IXWizardPageReport.Data1
0x180024f7c  jnz     short loc_180024FA8
0x180024f7e  mov     rax, [rdx+8]
0x180024f82  cmp     rax, qword ptr cs:IID_IXWizardPageReport.Data4
0x180024f89  jnz     short loc_180024FA8
0x180024f8b  cmp     qword ptr [rbx+20h], 0
0x180024f90  jz      short loc_180024FA8
0x180024f92  mov     rdx, [rbx+18h]; struct CTask *
0x180024f96  add     r9, 5
0x180024f9a  lea     rcx, [rbx+r9*8]; struct _GUID *
0x180024f9e  call    ?HrCreateInstance@CXWizardPageReport@@SAJPEBU_GUID@@PEBVCTask@@PEAPEAUIXWizardPageReport@@@Z; CXWizardPageReport::HrCreateInstance(_GUID const *,CTask const *,IXWizardPageReport * *)
0x180024fa3  jmp     loc_18002509F
0x180024fa8  mov     rax, [rdx]
0x180024fab  cmp     rax, qword ptr cs:IID_IXWizardTransaction.Data1
0x180024fb2  jnz     short loc_180024FF1
0x180024fb4  mov     rax, [rdx+8]
0x180024fb8  cmp     rax, qword ptr cs:IID_IXWizardTransaction.Data4
0x180024fbf  jnz     short loc_180024FF1
0x180024fc1  mov     rax, [rbx+20h]
0x180024fc5  test    rax, rax
0x180024fc8  jz      short loc_180024FE0
0x180024fca  test    ecx, ecx
0x180024fcc  jz      short loc_180024FE0
0x180024fce  cmp     dword ptr [rax+88h], 2
0x180024fd5  jz      short loc_180024FE0
0x180024fd7  test    dword ptr [rax+30h], 10000h
0x180024fde  jz      short loc_180024FF1
0x180024fe0  mov     rcx, [rbx+18h]; struct CTask *
0x180024fe4  mov     rdx, rdi; struct IXWizardTransaction **
0x180024fe7  call    ?HrCreateInstance@CXWizardTransaction@@SAJPEBVCTask@@PEAPEAUIXWizardTransaction@@@Z; CXWizardTransaction::HrCreateInstance(CTask const *,IXWizardTransaction * *)
0x180024fec  jmp     loc_18002509F
0x180024ff1  mov     rax, [rdx]
0x180024ff4  cmp     rax, qword ptr cs:IID_IXWizardNavigate.Data1
0x180024ffb  jnz     short loc_180025024
0x180024ffd  mov     rax, [rdx+8]
0x180025001  cmp     rax, qword ptr cs:IID_IXWizardNavigate.Data4
0x180025008  jnz     short loc_180025024
0x18002500a  mov     rcx, [rbx+18h]; struct CTask *
0x18002500e  test    dword ptr [rcx+0DCh], 600h
0x180025018  jz      short loc_180025024
0x18002501a  mov     rdx, rdi; struct IXWizardNavigate **
0x18002501d  call    ?HrCreateInstance@CXWizardNavigate@@SAJPEBVCTask@@PEAPEAUIXWizardNavigate@@@Z; CXWizardNavigate::HrCreateInstance(CTask const *,IXWizardNavigate * *)
0x180025022  jmp     short loc_18002509F
0x180025024  mov     rax, [rdx]
0x180025027  cmp     rax, qword ptr cs:IID_IXWizardPropertyBag.Data1
0x18002502e  jnz     short loc_180025057
0x180025030  mov     rax, [rdx+8]
0x180025034  cmp     rax, qword ptr cs:IID_IXWizardPropertyBag.Data4
0x18002503b  jnz     short loc_180025057
0x18002503d  mov     rdx, [rbx+18h]
0x180025041  add     r9, 5
0x180025045  mov     rdx, [rdx+110h]; struct IPXWizardPropertyBag *
0x18002504c  lea     rcx, [rbx+r9*8]; struct _GUID *
0x180025050  call    ?HrCreateInstance@CXWizardPropertyBag@@SAJPEBU_GUID@@PEBUIPXWizardPropertyBag@@PEAPEAUIXWizardPropertyBag@@@Z; CXWizardPropertyBag::HrCreateInstance(_GUID const *,IPXWizardPropertyBag const *,IXWizardPropertyBag * *)
0x180025055  jmp     short loc_18002509F
0x180025057  mov     rax, [rdx]
0x18002505a  cmp     rax, qword ptr cs:IID_ISimpleMarshal.Data1
0x180025061  jnz     short loc_180025093
0x180025063  mov     rax, [rdx+8]
0x180025067  cmp     rax, qword ptr cs:IID_ISimpleMarshal.Data4
0x18002506e  jnz     short loc_180025093
0x180025070  lea     r9, IID_ISimpleMarshal; riid
0x180025077  mov     [rsp+38h+ppv], rdi; ppv
0x18002507c  xor     edx, edx; pUnkOuter
0x18002507e  lea     rcx, CLSID_CSimpleMarshal; rclsid
0x180025085  mov     r8d, 401h; dwClsContext
0x18002508b  call    cs:__imp_CoCreateInstance
0x180025091  jmp     short loc_18002509F
0x180025093  mov     qword ptr [r8], 0
0x18002509a  mov     eax, 80004002h
0x18002509f  mov     rbx, [rsp+38h+arg_0]
0x1800250a4  add     rsp, 30h
0x1800250a8  pop     rdi
0x1800250a9  retn
```
