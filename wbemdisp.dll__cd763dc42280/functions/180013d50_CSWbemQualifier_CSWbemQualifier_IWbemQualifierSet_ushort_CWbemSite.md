# CSWbemQualifier::CSWbemQualifier(IWbemQualifierSet *,ushort *,CWbemSite *)

- ea: `0x180013d50`
- end: `0x180013e22`
- name: `??0CSWbemQualifier@@QEAA@PEAUIWbemQualifierSet@@PEAGPEAVCWbemSite@@@Z`
- size: `210`
- prototype: `CSWbemQualifier *(CSWbemQualifier *__hidden this, struct IWbemQualifierSet *, unsigned __int16 *, struct CWbemSite *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180020ff0`
- `0x1800213d0`

## callees

- `0x180013d50`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180013dce`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e05`
- `OLEAUT32!__imp_SysAllocString` at `0x180013dce`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemQualifier *__fastcall CSWbemQualifier::CSWbemQualifier(
        CSWbemQualifier *this,
        struct IWbemQualifierSet *a2,
        unsigned __int16 *a3,
        struct CWbemSite *a4)
{
  *(_QWORD *)this = &CSWbemQualifier::`vftable'{for `ISWbemQualifier'};
  *((_QWORD *)this + 1) = &CSWbemQualifier::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemQualifier::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = &CSWbemQualifier::CQualifierDispatchHelp::`vftable';
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemQualifier;
  *((GUID *)this + 6) = CLSID_SWbemQualifier;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemQualifier");
  *((_DWORD *)this + 32) = 1;
  *((_QWORD *)this + 3) = a2;
  ((void (__fastcall *)(struct IWbemQualifierSet *))a2->lpVtbl->AddRef)(a2);
  if ( a4 )
  {
    *((_QWORD *)this + 15) = a4;
    _InterlockedIncrement((volatile signed __int32 *)a4 + 2);
  }
  *((_QWORD *)this + 14) = SysAllocString(a3);
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180013d50  mov     [rsp+arg_0], rcx
0x180013d55  push    rbx
0x180013d56  push    rbp
0x180013d57  push    rsi
0x180013d58  push    rdi
0x180013d59  sub     rsp, 28h
0x180013d5d  mov     rbx, r9
0x180013d60  mov     rbp, r8
0x180013d63  mov     rdi, rdx
0x180013d66  mov     rsi, rcx
0x180013d69  lea     rax, ??_7CSWbemQualifier@@6BISWbemQualifier@@@; const CSWbemQualifier::`vftable'{for `ISWbemQualifier'}
0x180013d70  mov     [rcx], rax
0x180013d73  lea     rax, ??_7CSWbemQualifier@@6BISupportErrorInfo@@@; const CSWbemQualifier::`vftable'{for `ISupportErrorInfo'}
0x180013d7a  mov     [rcx+8], rax
0x180013d7e  lea     rax, ??_7CSWbemQualifier@@6BIProvideClassInfo@@@; const CSWbemQualifier::`vftable'{for `IProvideClassInfo'}
0x180013d85  mov     [rcx+10h], rax
0x180013d89  xor     ecx, ecx
0x180013d8b  mov     [rsi+38h], rcx
0x180013d8f  mov     [rsi+40h], rcx
0x180013d93  mov     [rsi+48h], rcx
0x180013d97  mov     [rsi+28h], rcx
0x180013d9b  mov     [rsi+30h], ecx
0x180013d9e  lea     rax, ??_7CQualifierDispatchHelp@CSWbemQualifier@@6B@; const CSWbemQualifier::CQualifierDispatchHelp::`vftable'
0x180013da5  mov     [rsi+20h], rax
0x180013da9  mov     [rsi+78h], rcx
0x180013dad  movups  xmm1, xmmword ptr cs:CLSID_SWbemQualifier.Data1
0x180013db4  movups  xmm0, xmmword ptr cs:IID_ISWbemQualifier.Data1
0x180013dbb  mov     [rsi+48h], rsi
0x180013dbf  movups  xmmword ptr [rsi+50h], xmm0
0x180013dc3  movups  xmmword ptr [rsi+60h], xmm1
0x180013dc7  lea     rcx, aSwbemqualifier_0; "SWbemQualifier"
0x180013dce  call    cs:__imp_SysAllocString
0x180013dd4  mov     [rsi+28h], rax
0x180013dd8  mov     dword ptr [rsi+80h], 1
0x180013de2  mov     [rsi+18h], rdi
0x180013de6  mov     rax, [rdi]
0x180013de9  mov     rcx, rdi
0x180013dec  mov     rax, [rax+8]
0x180013df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df5  test    rbx, rbx
0x180013df8  jz      short loc_180013E02
0x180013dfa  mov     [rsi+78h], rbx
0x180013dfe  lock inc dword ptr [rbx+8]
0x180013e02  mov     rcx, rbp; psz
0x180013e05  call    cs:__imp_SysAllocString
0x180013e0b  mov     [rsi+70h], rax
0x180013e0f  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180013e16  mov     rax, rsi
0x180013e19  add     rsp, 28h
0x180013e1d  pop     rdi
0x180013e1e  pop     rsi
0x180013e1f  pop     rbp
0x180013e20  pop     rbx
0x180013e21  retn
```
