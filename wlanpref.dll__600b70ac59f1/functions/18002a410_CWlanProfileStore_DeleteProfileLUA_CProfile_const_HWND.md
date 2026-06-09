# CWlanProfileStore::DeleteProfileLUA(CProfile const &,HWND__ *)

- ea: `0x18002a410`
- end: `0x18002a508`
- name: `?DeleteProfileLUA@CWlanProfileStore@@UEAAJAEBVCProfile@@PEAUHWND__@@@Z`
- size: `248`
- prototype: `int(CWlanProfileStore *__hidden this, const struct CProfile *, HWND)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x180003458`
- `0x1800036ac`
- `0x18000cdcc`
- `0x18000f390`
- `0x180014ef8`
- `0x18002a410`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002a4c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a4c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWlanProfileStore::DeleteProfileLUA(
        CWlanProfileStore *this,
        const struct CProfile *a2,
        struct _GUID *a3)
{
  int v5; // ebx
  const unsigned __int16 **Name; // rax
  void *v8; // [rsp+20h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v12[16]; // [rsp+48h] [rbp-28h] BYREF
  GUID v13; // [rsp+58h] [rbp-18h] BYREF

  v8 = 0;
  v5 = NtlCoCreateInstanceAsNetConfigOpOrAdmin((HWND)a3, (const struct _GUID *)a2, a3, &v8);
  if ( v5 >= 0 )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v12,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v11,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 872));
    v13 = GUID_NULL;
    Name = (const unsigned __int16 **)CProfile::GetName(a2, v10);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *Name);
    WTL::CString::~CString((WTL::CString *)v10);
    v13 = *(GUID *)((char *)a2 + 28);
    v5 = (*(__int64 (__fastcall **)(void *, GUID *, BSTR))(*(_QWORD *)v8 + 72LL))(v8, &v13, bstrString);
    SysFreeString(bstrString);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v11);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v12);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a410  mov     [rsp-18h+arg_18], rbx
0x18002a415  push    rbp
0x18002a416  push    rsi
0x18002a417  push    rdi
0x18002a418  mov     rbp, rsp
0x18002a41b  sub     rsp, 70h
0x18002a41f  mov     rax, cs:__security_cookie
0x18002a426  xor     rax, rsp
0x18002a429  mov     [rbp+var_8], rax
0x18002a42d  mov     rsi, rdx
0x18002a430  mov     rdi, rcx
0x18002a433  mov     [rbp+var_50], 0
0x18002a43b  lea     r9, [rbp+var_50]; void **
0x18002a43f  mov     rcx, r8; HWND
0x18002a442  call    ?NtlCoCreateInstanceAsNetConfigOpOrAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002a447  mov     ebx, eax
0x18002a449  test    eax, eax
0x18002a44b  js      loc_18002A4E1
0x18002a451  lea     rdx, [rdi+60h]
0x18002a455  lea     rcx, [rbp+var_28]
0x18002a459  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002a45e  nop
0x18002a45f  lea     rdx, [rdi+368h]
0x18002a466  lea     rcx, [rbp+var_38]
0x18002a46a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002a46f  nop
0x18002a470  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002a477  movdqu  [rbp+var_18], xmm0
0x18002a47c  lea     rdx, [rbp+var_40]
0x18002a480  mov     rcx, rsi
0x18002a483  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18002a488  nop
0x18002a489  mov     rdx, [rax]; unsigned __int16 *
0x18002a48c  lea     rcx, [rbp+bstrString]; this
0x18002a490  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002a495  nop
0x18002a496  lea     rcx, [rbp+var_40]; this
0x18002a49a  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002a49f  movups  xmm0, xmmword ptr [rsi+1Ch]
0x18002a4a3  movdqu  [rbp+var_18], xmm0
0x18002a4a8  mov     rcx, [rbp+var_50]
0x18002a4ac  mov     rax, [rcx]
0x18002a4af  mov     r8, [rbp+bstrString]
0x18002a4b3  lea     rdx, [rbp+var_18]
0x18002a4b7  mov     rax, [rax+48h]
0x18002a4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4c0  mov     ebx, eax
0x18002a4c2  mov     rcx, [rbp+bstrString]; bstrString
0x18002a4c6  call    cs:__imp_SysFreeString
0x18002a4cc  nop
0x18002a4cd  lea     rcx, [rbp+var_38]
0x18002a4d1  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002a4d6  nop
0x18002a4d7  lea     rcx, [rbp+var_28]
0x18002a4db  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002a4e0  nop
0x18002a4e1  lea     rcx, [rbp+var_50]
0x18002a4e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002a4ea  mov     eax, ebx
0x18002a4ec  mov     rcx, [rbp+var_8]
0x18002a4f0  xor     rcx, rsp; StackCookie
0x18002a4f3  call    __security_check_cookie
0x18002a4f8  mov     rbx, [rsp+70h+arg_18]
0x18002a500  add     rsp, 70h
0x18002a504  pop     rdi
0x18002a505  pop     rsi
0x18002a506  pop     rbp
0x18002a507  retn
```
