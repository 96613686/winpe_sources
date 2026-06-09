# CWlanProfileStore::DeleteProfile(CProfile const &)

- ea: `0x18002a340`
- end: `0x18002a405`
- name: `?DeleteProfile@CWlanProfileStore@@UEAAJAEBVCProfile@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(CWlanProfileStore *__hidden this, const struct CProfile *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x18000f390`
- `0x18002a340`
- `0x18002d840`

## import_xrefs

- `wlanapi!WlanDeleteProfile` at `0x18002a3b3`
- `wlanapi!WlanDeleteProfile` at `0x18002a3b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWlanProfileStore::DeleteProfile(HANDLE *this, const struct CProfile *a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  LPCWSTR strProfileName; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v8[16]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-30h] BYREF
  GUID pInterfaceGuid; // [rsp+48h] [rbp-20h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v9, this + 12);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v8, this + 109);
  pInterfaceGuid = 0;
  CProfile::GetName(a2, &strProfileName);
  pInterfaceGuid = *(GUID *)((char *)a2 + 28);
  v4 = WlanDeleteProfile(this[29], &pInterfaceGuid, strProfileName, 0);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  WTL::CString::~CString((WTL::CString *)&strProfileName);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v9);
  return v5;
}

```

## disassembly

```asm
0x18002a340  mov     [rsp+arg_10], rbx
0x18002a345  push    rdi
0x18002a346  sub     rsp, 60h
0x18002a34a  mov     rax, cs:__security_cookie
0x18002a351  xor     rax, rsp
0x18002a354  mov     [rsp+68h+var_10], rax
0x18002a359  mov     rbx, rdx
0x18002a35c  mov     rdi, rcx
0x18002a35f  lea     rdx, [rcx+60h]
0x18002a363  lea     rcx, [rsp+68h+var_30]
0x18002a368  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002a36d  nop
0x18002a36e  lea     rdx, [rdi+368h]
0x18002a375  lea     rcx, [rsp+68h+var_40]
0x18002a37a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002a37f  nop
0x18002a380  xorps   xmm0, xmm0
0x18002a383  movups  xmmword ptr [rsp+68h+pInterfaceGuid.Data1], xmm0
0x18002a388  lea     rdx, [rsp+68h+strProfileName]
0x18002a38d  mov     rcx, rbx
0x18002a390  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18002a395  movups  xmm0, xmmword ptr [rbx+1Ch]
0x18002a399  movdqu  xmmword ptr [rsp+68h+pInterfaceGuid.Data1], xmm0
0x18002a39f  xor     r9d, r9d; pReserved
0x18002a3a2  mov     r8, [rsp+68h+strProfileName]; strProfileName
0x18002a3a7  lea     rdx, [rsp+68h+pInterfaceGuid]; pInterfaceGuid
0x18002a3ac  mov     rcx, [rdi+0E8h]; hClientHandle
0x18002a3b3  call    cs:__imp_WlanDeleteProfile
0x18002a3b9  mov     ebx, eax
0x18002a3bb  test    eax, eax
0x18002a3bd  jle     short loc_18002A3C8
0x18002a3bf  movzx   ebx, ax
0x18002a3c2  or      ebx, 80070000h
0x18002a3c8  lea     rcx, [rsp+68h+strProfileName]; this
0x18002a3cd  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002a3d2  nop
0x18002a3d3  lea     rcx, [rsp+68h+var_40]
0x18002a3d8  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002a3dd  nop
0x18002a3de  lea     rcx, [rsp+68h+var_30]
0x18002a3e3  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002a3e8  mov     eax, ebx
0x18002a3ea  mov     rcx, [rsp+68h+var_10]
0x18002a3ef  xor     rcx, rsp; StackCookie
0x18002a3f2  call    __security_check_cookie
0x18002a3f7  mov     rbx, [rsp+68h+arg_10]
0x18002a3ff  add     rsp, 60h
0x18002a403  pop     rdi
0x18002a404  retn
```
