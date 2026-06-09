# CSWbemServices::CSWbemServices(IWbemServices *,ushort *,ushort *,ushort *,ushort *,CWbemLocatorSecurity *,ushort *)

- ea: `0x18000b580`
- end: `0x18000b704`
- name: `??0CSWbemServices@@QEAA@PEAUIWbemServices@@PEAG111PEAVCWbemLocatorSecurity@@1@Z`
- size: `388`
- prototype: `CSWbemServices *(CSWbemServices *__hidden this, struct IWbemServices *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct CWbemLocatorSecurity *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e9a0`

## callees

- `0x180009c20`
- `0x18000b580`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b66a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b6da`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b6f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b66a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b6da`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b6f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6d1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b679`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b679`

## string_xrefs

- `0x18000b663`: `SWbemServicesEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CSWbemServices *__fastcall CSWbemServices::CSWbemServices(
        CSWbemServices *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct CWbemLocatorSecurity *a7,
        unsigned __int16 *psz)
{
  CSWbemSecurity *v12; // rax

  *(_QWORD *)this = &CSWbemServices::`vftable'{for `ISWbemServicesEx'};
  *((_QWORD *)this + 1) = &CSWbemServices::`vftable'{for `IDispatchEx'};
  *((_QWORD *)this + 2) = &CSWbemServices::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &CSWbemServices::`vftable'{for `ISWbemInternalServices'};
  *((_QWORD *)this + 4) = &CSWbemServices::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  _InterlockedIncrement(&g_cObj);
  *((_QWORD *)this + 12) = this;
  *(GUID *)((char *)this + 104) = IID_ISWbemServicesEx;
  *(GUID *)((char *)this + 120) = CLSID_SWbemServicesEx;
  *((_QWORD *)this + 8) = SysAllocString(L"SWbemServicesEx");
  v12 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
  if ( v12 )
    v12 = CSWbemSecurity::CSWbemSecurity(v12, a2, a4, a5, a6, (struct ISWbemSecurity *)a7);
  *((_QWORD *)this + 17) = v12;
  if ( psz )
    *((_QWORD *)this + 6) = SysAllocString(psz);
  if ( a3 )
  {
    SysFreeString(*((BSTR *)this + 5));
    *((_QWORD *)this + 5) = SysAllocString(a3);
  }
  return this;
}

```

## disassembly

```asm
0x18000b580  mov     [rsp+arg_8], rbx
0x18000b585  mov     [rsp+arg_0], rcx
0x18000b58a  push    rbp
0x18000b58b  push    rsi
0x18000b58c  push    rdi
0x18000b58d  sub     rsp, 30h
0x18000b591  mov     rsi, r9
0x18000b594  mov     rdi, r8
0x18000b597  mov     rbp, rdx
0x18000b59a  mov     rbx, rcx
0x18000b59d  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x18000b5a4  mov     [rcx], rax
0x18000b5a7  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x18000b5ae  mov     [rcx+8], rax
0x18000b5b2  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x18000b5b9  mov     [rcx+10h], rax
0x18000b5bd  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x18000b5c4  mov     [rcx+18h], rax
0x18000b5c8  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x18000b5cf  mov     [rcx+20h], rax
0x18000b5d3  mov     qword ptr [rcx+28h], 0
0x18000b5db  mov     qword ptr [rcx+30h], 0
0x18000b5e3  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000b5ea  mov     [rcx+38h], rax
0x18000b5ee  mov     qword ptr [rcx+50h], 0
0x18000b5f6  mov     qword ptr [rcx+58h], 0
0x18000b5fe  mov     qword ptr [rcx+60h], 0
0x18000b606  mov     qword ptr [rcx+40h], 0
0x18000b60e  mov     dword ptr [rcx+48h], 0
0x18000b615  mov     qword ptr [rcx+88h], 0
0x18000b620  mov     qword ptr [rcx+90h], 0
0x18000b62b  mov     qword ptr [rcx+98h], 0
0x18000b636  mov     dword ptr [rcx+0A0h], 0
0x18000b640  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18000b647  movups  xmm1, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x18000b64e  movups  xmm0, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x18000b655  mov     [rcx+60h], rcx
0x18000b659  movdqu  xmmword ptr [rcx+68h], xmm0
0x18000b65e  movdqu  xmmword ptr [rcx+78h], xmm1
0x18000b663  lea     rcx, aSwbemservicese; "SWbemServicesEx"
0x18000b66a  call    cs:__imp_SysAllocString
0x18000b670  mov     [rbx+40h], rax
0x18000b674  mov     ecx, 90h
0x18000b679  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000b67f  mov     [rsp+48h+arg_10], rax
0x18000b684  test    rax, rax
0x18000b687  jz      short loc_18000B6B4
0x18000b689  mov     rcx, [rsp+48h+arg_30]
0x18000b691  mov     [rsp+48h+var_20], rcx; struct CWbemLocatorSecurity *
0x18000b696  mov     rcx, [rsp+48h+arg_28]
0x18000b69b  mov     [rsp+48h+var_28], rcx; unsigned __int16 *
0x18000b6a0  mov     r9, [rsp+48h+arg_20]; unsigned __int16 *
0x18000b6a5  mov     r8, rsi; unsigned __int16 *
0x18000b6a8  mov     rdx, rbp; struct IUnknown *
0x18000b6ab  mov     rcx, rax; this
0x18000b6ae  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAG11PEAVCWbemLocatorSecurity@@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,ushort *,ushort *,ushort *,CWbemLocatorSecurity *)
0x18000b6b3  nop
0x18000b6b4  mov     [rbx+88h], rax
0x18000b6bb  mov     rcx, [rsp+48h+psz]; psz
0x18000b6c3  test    rcx, rcx
0x18000b6c6  jnz     short loc_18000B6F6
0x18000b6c8  test    rdi, rdi
0x18000b6cb  jz      short loc_18000B6E4
0x18000b6cd  mov     rcx, [rbx+28h]; bstrString
0x18000b6d1  call    cs:__imp_SysFreeString
0x18000b6d7  mov     rcx, rdi; psz
0x18000b6da  call    cs:__imp_SysAllocString
0x18000b6e0  mov     [rbx+28h], rax
0x18000b6e4  mov     rax, rbx
0x18000b6e7  mov     rbx, [rsp+48h+arg_8]
0x18000b6ec  add     rsp, 30h
0x18000b6f0  pop     rdi
0x18000b6f1  pop     rsi
0x18000b6f2  pop     rbp
0x18000b6f3  retn
0x18000b6f4  jmp     short loc_18000B6B4
0x18000b6f6  call    cs:__imp_SysAllocString
0x18000b6fc  nop
0x18000b6fd  mov     [rbx+30h], rax
0x18000b701  jmp     short loc_18000B6C8
```
