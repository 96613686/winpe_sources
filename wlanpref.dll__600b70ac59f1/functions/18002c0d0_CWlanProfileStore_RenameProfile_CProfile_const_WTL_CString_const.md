# CWlanProfileStore::RenameProfile(CProfile const &,WTL::CString const &)

- ea: `0x18002c0d0`
- end: `0x18002c1bd`
- name: `?RenameProfile@CWlanProfileStore@@UEAAJAEBVCProfile@@AEBVCString@WTL@@@Z`
- size: `237`
- prototype: `int(CWlanProfileStore *__hidden this, const struct CProfile *, const struct WTL::CString *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x18000cee0`
- `0x18000f390`
- `0x18002c0d0`
- `0x18002c5e8`
- `0x18002c674`
- `0x18002d840`

## import_xrefs

- `wlanapi!WlanRenameProfile` at `0x18002c168`
- `wlanapi!WlanRenameProfile` at `0x18002c168`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWlanProfileStore::RenameProfile(
        HANDLE *this,
        const struct CProfile *a2,
        const struct WTL::CString *a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  LPCWSTR strNewProfileName; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR strOldProfileName; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v10[16]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v11[16]; // [rsp+50h] [rbp-30h] BYREF
  GUID pInterfaceGuid; // [rsp+60h] [rbp-20h] BYREF

  WTL::CString::CString((WTL::CString *)&strNewProfileName, a3);
  WTL::CString::TrimLeft((WTL::CString *)&strNewProfileName);
  WTL::CString::TrimRight((WTL::CString *)&strNewProfileName);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v11, this + 12);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v10, this + 109);
  pInterfaceGuid = 0;
  CProfile::GetName(a2, &strOldProfileName);
  pInterfaceGuid = *(GUID *)((char *)a2 + 28);
  v5 = WlanRenameProfile(this[29], &pInterfaceGuid, strOldProfileName, strNewProfileName, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  WTL::CString::~CString((WTL::CString *)&strOldProfileName);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v10);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v11);
  WTL::CString::~CString((WTL::CString *)&strNewProfileName);
  return v6;
}

```

## disassembly

```asm
0x18002c0d0  push    rbp
0x18002c0d2  push    rbx
0x18002c0d3  push    rdi
0x18002c0d4  mov     rbp, rsp
0x18002c0d7  sub     rsp, 80h
0x18002c0de  mov     rax, cs:__security_cookie
0x18002c0e5  xor     rax, rsp
0x18002c0e8  mov     [rbp+var_10], rax
0x18002c0ec  mov     rbx, rdx
0x18002c0ef  mov     rdi, rcx
0x18002c0f2  mov     rdx, r8; struct WTL::CString *
0x18002c0f5  lea     rcx, [rbp+strNewProfileName]; this
0x18002c0f9  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18002c0fe  nop
0x18002c0ff  lea     rcx, [rbp+strNewProfileName]; this
0x18002c103  call    ?TrimLeft@CString@WTL@@QEAAXXZ; WTL::CString::TrimLeft(void)
0x18002c108  lea     rcx, [rbp+strNewProfileName]; this
0x18002c10c  call    ?TrimRight@CString@WTL@@QEAAXXZ; WTL::CString::TrimRight(void)
0x18002c111  lea     rdx, [rdi+60h]
0x18002c115  lea     rcx, [rbp+var_30]
0x18002c119  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c11e  nop
0x18002c11f  lea     rdx, [rdi+368h]
0x18002c126  lea     rcx, [rbp+var_40]
0x18002c12a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c12f  nop
0x18002c130  xorps   xmm0, xmm0
0x18002c133  movups  xmmword ptr [rbp+pInterfaceGuid.Data1], xmm0
0x18002c137  lea     rdx, [rbp+strOldProfileName]
0x18002c13b  mov     rcx, rbx
0x18002c13e  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18002c143  movups  xmm0, xmmword ptr [rbx+1Ch]
0x18002c147  movdqu  xmmword ptr [rbp+pInterfaceGuid.Data1], xmm0
0x18002c14c  mov     [rsp+80h+pReserved], 0; pReserved
0x18002c155  mov     r9, [rbp+strNewProfileName]; strNewProfileName
0x18002c159  mov     r8, [rbp+strOldProfileName]; strOldProfileName
0x18002c15d  lea     rdx, [rbp+pInterfaceGuid]; pInterfaceGuid
0x18002c161  mov     rcx, [rdi+0E8h]; hClientHandle
0x18002c168  call    cs:__imp_WlanRenameProfile
0x18002c16e  mov     ebx, eax
0x18002c170  test    eax, eax
0x18002c172  jle     short loc_18002C17D
0x18002c174  movzx   ebx, ax
0x18002c177  or      ebx, 80070000h
0x18002c17d  lea     rcx, [rbp+strOldProfileName]; this
0x18002c181  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c186  nop
0x18002c187  lea     rcx, [rbp+var_40]
0x18002c18b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c190  nop
0x18002c191  lea     rcx, [rbp+var_30]
0x18002c195  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c19a  nop
0x18002c19b  lea     rcx, [rbp+strNewProfileName]; this
0x18002c19f  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c1a4  mov     eax, ebx
0x18002c1a6  mov     rcx, [rbp+var_10]
0x18002c1aa  xor     rcx, rsp; StackCookie
0x18002c1ad  call    __security_check_cookie
0x18002c1b2  add     rsp, 80h
0x18002c1b9  pop     rdi
0x18002c1ba  pop     rbx
0x18002c1bb  pop     rbp
0x18002c1bc  retn
```
