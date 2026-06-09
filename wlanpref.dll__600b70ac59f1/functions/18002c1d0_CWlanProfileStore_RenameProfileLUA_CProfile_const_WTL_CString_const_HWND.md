# CWlanProfileStore::RenameProfileLUA(CProfile const &,WTL::CString const &,HWND__ *)

- ea: `0x18002c1d0`
- end: `0x18002c30f`
- name: `?RenameProfileLUA@CWlanProfileStore@@UEAAJAEBVCProfile@@AEBVCString@WTL@@PEAUHWND__@@@Z`
- size: `319`
- prototype: `int(CWlanProfileStore *__hidden this, const struct CProfile *, const struct WTL::CString *, HWND)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x180003458`
- `0x1800036ac`
- `0x18000cdcc`
- `0x18000cee0`
- `0x18000f390`
- `0x180014ef8`
- `0x18002c1d0`
- `0x18002c5e8`
- `0x18002c674`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002c2bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c2c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c2bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c2c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWlanProfileStore::RenameProfileLUA(
        CWlanProfileStore *this,
        const struct CProfile *a2,
        const struct WTL::CString *a3,
        HWND a4)
{
  const struct _GUID *v7; // rdx
  const struct _GUID *v8; // r8
  int v9; // ebx
  const unsigned __int16 **Name; // rax
  void *v11; // rdi
  __int64 (__fastcall *v12)(void *, __int128 *, BSTR, _QWORD); // rbx
  _QWORD *v13; // rax
  unsigned __int16 *v15; // [rsp+30h] [rbp-29h] BYREF
  void *v16; // [rsp+38h] [rbp-21h] BYREF
  BSTR v17; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[16]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v21[16]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v22; // [rsp+78h] [rbp+1Fh] BYREF

  WTL::CString::CString((WTL::CString *)&v15, a3);
  WTL::CString::TrimLeft((WTL::CString *)&v15);
  WTL::CString::TrimRight((WTL::CString *)&v15);
  v16 = 0;
  v9 = NtlCoCreateInstanceAsNetConfigOpOrAdmin(a4, v7, v8, &v16);
  if ( v9 >= 0 )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v21,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v20,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 872));
    v22 = 0;
    Name = (const unsigned __int16 **)CProfile::GetName(a2, v18);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v17, *Name);
    WTL::CString::~CString((WTL::CString *)v18);
    v22 = *(_OWORD *)((char *)a2 + 28);
    v11 = v16;
    v12 = *(__int64 (__fastcall **)(void *, __int128 *, BSTR, _QWORD))(*(_QWORD *)v16 + 80LL);
    v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v15);
    v9 = v12(v11, &v22, v17, *v13);
    SysFreeString(bstrString);
    SysFreeString(v17);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v20);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v21);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
  WTL::CString::~CString((WTL::CString *)&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c1d0  push    rbp
0x18002c1d2  push    rbx
0x18002c1d3  push    rsi
0x18002c1d4  push    rdi
0x18002c1d5  lea     rbp, [rsp-3Fh]
0x18002c1da  sub     rsp, 98h
0x18002c1e1  mov     rax, cs:__security_cookie
0x18002c1e8  xor     rax, rsp
0x18002c1eb  mov     [rbp+57h+var_28], rax
0x18002c1ef  mov     rbx, r9
0x18002c1f2  mov     rsi, rdx
0x18002c1f5  mov     rdi, rcx
0x18002c1f8  mov     rdx, r8; struct WTL::CString *
0x18002c1fb  lea     rcx, [rbp+57h+var_80]; this
0x18002c1ff  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18002c204  nop
0x18002c205  lea     rcx, [rbp+57h+var_80]; this
0x18002c209  call    ?TrimLeft@CString@WTL@@QEAAXXZ; WTL::CString::TrimLeft(void)
0x18002c20e  lea     rcx, [rbp+57h+var_80]; this
0x18002c212  call    ?TrimRight@CString@WTL@@QEAAXXZ; WTL::CString::TrimRight(void)
0x18002c217  mov     [rbp+57h+var_78], 0
0x18002c21f  lea     r9, [rbp+57h+var_78]; void **
0x18002c223  mov     rcx, rbx; HWND
0x18002c226  call    ?NtlCoCreateInstanceAsNetConfigOpOrAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002c22b  mov     ebx, eax
0x18002c22d  test    eax, eax
0x18002c22f  js      loc_18002C2E2
0x18002c235  lea     rdx, [rdi+60h]
0x18002c239  lea     rcx, [rbp+57h+var_48]
0x18002c23d  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c242  nop
0x18002c243  lea     rdx, [rdi+368h]
0x18002c24a  lea     rcx, [rbp+57h+var_58]
0x18002c24e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c253  nop
0x18002c254  xorps   xmm0, xmm0
0x18002c257  movups  [rbp+57h+var_38], xmm0
0x18002c25b  lea     rdx, [rbp+57h+var_68]
0x18002c25f  mov     rcx, rsi
0x18002c262  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18002c267  nop
0x18002c268  mov     rdx, [rax]; unsigned __int16 *
0x18002c26b  lea     rcx, [rbp+57h+var_70]; this
0x18002c26f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c274  nop
0x18002c275  lea     rcx, [rbp+57h+var_68]; this
0x18002c279  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c27e  movups  xmm0, xmmword ptr [rsi+1Ch]
0x18002c282  movdqu  [rbp+57h+var_38], xmm0
0x18002c287  mov     rdi, [rbp+57h+var_78]
0x18002c28b  mov     rax, [rdi]
0x18002c28e  mov     rbx, [rax+50h]
0x18002c292  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18002c296  lea     rcx, [rbp+57h+bstrString]; this
0x18002c29a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c29f  nop
0x18002c2a0  mov     r9, [rax]
0x18002c2a3  mov     r8, [rbp+57h+var_70]
0x18002c2a7  lea     rdx, [rbp+57h+var_38]
0x18002c2ab  mov     rcx, rdi
0x18002c2ae  mov     rax, rbx
0x18002c2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2b6  mov     ebx, eax
0x18002c2b8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002c2bc  call    cs:__imp_SysFreeString
0x18002c2c2  nop
0x18002c2c3  mov     rcx, [rbp+57h+var_70]; bstrString
0x18002c2c7  call    cs:__imp_SysFreeString
0x18002c2cd  nop
0x18002c2ce  lea     rcx, [rbp+57h+var_58]
0x18002c2d2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c2d7  nop
0x18002c2d8  lea     rcx, [rbp+57h+var_48]
0x18002c2dc  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c2e1  nop
0x18002c2e2  lea     rcx, [rbp+57h+var_78]
0x18002c2e6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002c2eb  nop
0x18002c2ec  lea     rcx, [rbp+57h+var_80]; this
0x18002c2f0  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c2f5  mov     eax, ebx
0x18002c2f7  mov     rcx, [rbp+57h+var_28]
0x18002c2fb  xor     rcx, rsp; StackCookie
0x18002c2fe  call    __security_check_cookie
0x18002c303  add     rsp, 98h
0x18002c30a  pop     rdi
0x18002c30b  pop     rsi
0x18002c30c  pop     rbx
0x18002c30d  pop     rbp
0x18002c30e  retn
```
