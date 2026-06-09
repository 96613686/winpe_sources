# CPropertyProxy::CreateInstance(_FSRM_AGGREGATED_PROPERTY const &,ATL::CComObject<CPropertyProxy> * *)

- ea: `0x18004b4a4`
- end: `0x18004b6ed`
- name: `?CreateInstance@CPropertyProxy@@SAXAEBU_FSRM_AGGREGATED_PROPERTY@@PEAPEAV?$CComObject@VCPropertyProxy@@@ATL@@@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004bd6c`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18004b364`
- `0x18004b4a4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004b62c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b642`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b62c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b642`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b59a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b59a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5c3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b5d1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b5d1`

## string_xrefs

- `0x18004b4e2`: `CPropertyProxy::CreateInstance`
- `0x18004b4d6`: `base\fs\fsrm\service\modulewrp\pbfproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPropertyProxy::CreateInstance(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rbx
  BSTR v6; // rax
  const OLECHAR *v7; // rcx
  BSTR v8; // rax
  HRESULT v9; // eax
  int v10; // eax
  char v11; // al
  int Hr; // eax
  char v13; // al
  _QWORD *pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v16[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+4Ch] [rbp-B4h]
  int v19; // [rsp+50h] [rbp-B0h]
  _BYTE v20[96]; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+B8h] [rbp-48h]
  void **v22; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+C8h] [rbp-38h]

  pExceptionObject = v16;
  v16[0] = L"base\\fs\\fsrm\\service\\modulewrp\\pbfproxy.cpp";
  v16[1] = L"CPropertyProxy::CreateInstance";
  v16[2] = L"PBFPROXC";
  v17 = 70;
  v18 = 22;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v22, (const struct CSrmDebugInfo *)v16, 0);
  *a2 = 0;
  v15 = 0;
  v4 = ATL::CComObject<CPropertyProxy>::CreateInstance(&v15);
  v23 = v4;
  if ( v4 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v22, Hr);
    v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v22, 0x4Eu, v13, 0, pExceptionObject);
  }
  v23 = v4;
  v5 = v15;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  if ( *(_QWORD *)a1 )
  {
    v6 = SysAllocString(*(const OLECHAR **)a1);
    pExceptionObject = v6;
    if ( !v6 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    pExceptionObject = 0;
    v6 = 0;
  }
  pExceptionObject = 0;
  *(_QWORD *)(v5 + 64) = v6;
  SysFreeString(0);
  v7 = *(const OLECHAR **)(a1 + 8);
  if ( v7 )
  {
    v8 = SysAllocString(v7);
    pExceptionObject = v8;
    if ( !v8 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    pExceptionObject = 0;
    v8 = 0;
  }
  pExceptionObject = 0;
  *(_QWORD *)(v5 + 72) = v8;
  SysFreeString(0);
  v9 = SafeArrayCopy(*(SAFEARRAY **)(a1 + 16), (SAFEARRAY **)(v5 + 80));
  v23 = v9;
  if ( v9 < 0 )
  {
    v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v22, v10);
    v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v22);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v22, 0x55u, v11, 0, pExceptionObject);
  }
  v23 = v9;
  *(_DWORD *)(v5 + 88) = *(_DWORD *)(a1 + 24);
  *(_DWORD *)(v5 + 92) = *(_DWORD *)(a1 + 28);
  v15 = 0;
  *a2 = v5;
  v22 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v22);
}

```

## disassembly

```asm
0x18004b4a4  mov     [rsp-8+arg_10], rbx
0x18004b4a9  push    rbp
0x18004b4aa  push    rsi
0x18004b4ab  push    rdi
0x18004b4ac  lea     rbp, [rsp-80h]
0x18004b4b1  sub     rsp, 180h
0x18004b4b8  mov     rax, cs:__security_cookie
0x18004b4bf  xor     rax, rsp
0x18004b4c2  mov     [rbp+90h+var_20], rax
0x18004b4c6  mov     rsi, rdx
0x18004b4c9  mov     rdi, rcx
0x18004b4cc  lea     rax, [rsp+190h+var_160]
0x18004b4d1  mov     [rsp+190h+pExceptionObject], rax
0x18004b4d6  lea     rax, aBaseFsFsrmServ_15; "base\\fs\\fsrm\\service\\modulewrp\\pbf"...
0x18004b4dd  mov     [rsp+190h+var_160], rax
0x18004b4e2  lea     rax, aCpropertyproxy; "CPropertyProxy::CreateInstance"
0x18004b4e9  mov     [rsp+190h+var_158], rax
0x18004b4ee  lea     rax, aPbfproxc; "PBFPROXC"
0x18004b4f5  mov     [rsp+190h+var_150], rax
0x18004b4fa  mov     [rsp+190h+var_148], 46h ; 'F'
0x18004b502  mov     [rsp+190h+var_144], 16h
0x18004b50a  mov     [rsp+190h+var_140], 0FFh
0x18004b512  mov     [rbp+90h+var_D8], 1000000h
0x18004b519  xor     edx, edx; Val
0x18004b51b  lea     r8d, [rdx+60h]; Size
0x18004b51f  lea     rcx, [rsp+190h+var_138]; void *
0x18004b524  call    memset_0
0x18004b529  nop
0x18004b52a  xor     r8d, r8d
0x18004b52d  lea     rdx, [rsp+190h+var_160]
0x18004b532  lea     rcx, [rbp+90h+var_D0]
0x18004b536  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004b53b  nop
0x18004b53c  mov     qword ptr [rsi], 0
0x18004b543  mov     [rsp+190h+var_168], 0
0x18004b54c  lea     rcx, [rsp+190h+var_168]
0x18004b551  call    ?CreateInstance@?$CComObject@VCPropertyProxy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPropertyProxy>::CreateInstance(ATL::CComObject<CPropertyProxy> * *)
0x18004b556  mov     [rbp+90h+var_C8], eax
0x18004b559  test    eax, eax
0x18004b55b  js      loc_18004B6BC
0x18004b561  mov     [rbp+90h+var_C8], eax
0x18004b564  mov     rbx, [rsp+190h+var_168]
0x18004b569  mov     rax, [rbx]
0x18004b56c  mov     rcx, rbx
0x18004b56f  mov     rax, [rax+8]
0x18004b573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b578  mov     rcx, [rdi]; psz
0x18004b57b  test    rcx, rcx
0x18004b57e  jnz     loc_18004B62C
0x18004b584  mov     [rsp+190h+pExceptionObject], rcx
0x18004b589  xor     eax, eax
0x18004b58b  mov     [rsp+190h+pExceptionObject], 0
0x18004b594  mov     [rbx+40h], rax
0x18004b598  xor     ecx, ecx; bstrString
0x18004b59a  call    cs:__imp_SysFreeString
0x18004b5a0  mov     rcx, [rdi+8]; psz
0x18004b5a4  test    rcx, rcx
0x18004b5a7  jnz     loc_18004B642
0x18004b5ad  mov     [rsp+190h+pExceptionObject], rcx
0x18004b5b2  xor     eax, eax
0x18004b5b4  mov     [rsp+190h+pExceptionObject], 0
0x18004b5bd  mov     [rbx+48h], rax
0x18004b5c1  xor     ecx, ecx; bstrString
0x18004b5c3  call    cs:__imp_SysFreeString
0x18004b5c9  lea     rdx, [rbx+50h]; ppsaOut
0x18004b5cd  mov     rcx, [rdi+10h]; psa
0x18004b5d1  call    cs:__imp_SafeArrayCopy
0x18004b5d7  mov     [rbp+90h+var_C8], eax
0x18004b5da  test    eax, eax
0x18004b5dc  js      short loc_18004B657
0x18004b5de  mov     [rbp+90h+var_C8], eax
0x18004b5e1  mov     eax, [rdi+18h]
0x18004b5e4  mov     [rbx+58h], eax
0x18004b5e7  mov     eax, [rdi+1Ch]
0x18004b5ea  mov     [rbx+5Ch], eax
0x18004b5ed  mov     [rsp+190h+var_168], 0
0x18004b5f6  mov     [rsi], rbx
0x18004b5f9  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004b600  mov     [rbp+90h+var_D0], rax
0x18004b604  lea     rcx, [rbp+90h+var_D0]; this
0x18004b608  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004b60d  mov     rcx, [rbp+90h+var_20]
0x18004b611  xor     rcx, rsp; StackCookie
0x18004b614  call    __security_check_cookie
0x18004b619  mov     rbx, [rsp+190h+arg_10]
0x18004b621  add     rsp, 180h
0x18004b628  pop     rdi
0x18004b629  pop     rsi
0x18004b62a  pop     rbp
0x18004b62b  retn
0x18004b62c  call    cs:__imp_SysAllocString
0x18004b632  nop
0x18004b633  mov     [rsp+190h+pExceptionObject], rax
0x18004b638  test    rax, rax
0x18004b63b  jz      short loc_18004B688
0x18004b63d  jmp     loc_18004B58B
0x18004b642  call    cs:__imp_SysAllocString
0x18004b648  mov     [rsp+190h+pExceptionObject], rax
0x18004b64d  test    rax, rax
0x18004b650  jz      short loc_18004B6A2
0x18004b652  jmp     loc_18004B5B4
0x18004b657  lea     rcx, [rbp+90h+var_D0]; this
0x18004b65b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004b660  mov     edx, eax; int
0x18004b662  lea     rcx, [rbp+90h+var_D0]; this
0x18004b666  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004b66b  lea     rcx, [rbp+90h+var_D0]; this
0x18004b66f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004b674  mov     r8d, eax; char
0x18004b677  xor     r9d, r9d; unsigned __int16 *
0x18004b67a  lea     edx, [r9+55h]; unsigned int
0x18004b67e  lea     rcx, [rbp+90h+var_D0]; this
0x18004b682  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004b688  mov     dword ptr [rsp+190h+pExceptionObject], 8007000Eh
0x18004b690  lea     rdx, _TI1J; pThrowInfo
0x18004b697  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x18004b69c  call    _CxxThrowException_0
0x18004b6a2  mov     dword ptr [rsp+190h+pExceptionObject], 8007000Eh
0x18004b6aa  lea     rdx, _TI1J; pThrowInfo
0x18004b6b1  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x18004b6b6  call    _CxxThrowException_0
0x18004b6bc  lea     rcx, [rbp+90h+var_D0]; this
0x18004b6c0  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004b6c5  mov     edx, eax; int
0x18004b6c7  lea     rcx, [rbp+90h+var_D0]; this
0x18004b6cb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004b6d0  lea     rcx, [rbp+90h+var_D0]; this
0x18004b6d4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004b6d9  mov     r8d, eax; char
0x18004b6dc  xor     r9d, r9d; unsigned __int16 *
0x18004b6df  lea     edx, [r9+4Eh]; unsigned int
0x18004b6e3  lea     rcx, [rbp+90h+var_D0]; this
0x18004b6e7  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
