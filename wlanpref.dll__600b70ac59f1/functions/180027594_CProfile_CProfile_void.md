# CProfile::~CProfile(void)

- ea: `0x180027594`
- end: `0x1800275fc`
- name: `??1CProfile@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(CProfile *__hidden this)`
- caller_count: `30`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d6b0`
- `0x18000e610`
- `0x18000e660`
- `0x18000e700`
- `0x18000eb50`
- `0x18000f448`
- `0x18000f770`
- `0x18000fdf0`
- `0x180010bf0`
- `0x1800114c0`
- `0x180012610`
- `0x1800134f4`
- `0x180013738`
- `0x1800138d0`
- `0x1800139a0`
- `0x180013bb4`
- `0x1800140c0`
- `0x180027610`
- `0x18002bb40`
- `0x18002dfd1`
- `0x18002dfe3`
- `0x18002e0bb`
- `0x18002e0f1`
- `0x18002e1f3`
- `0x18002e2a5`
- `0x18002e3bb`
- `0x18002e4be`
- `0x18002e565`
- `0x18002e589`
- `0x18002ea6f`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x180027594`
- `0x18002771c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CProfile::~CProfile(CProfile *this)
{
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &CProfile::`vftable';
  WTL::CString::~CString((CProfile *)((char *)this + 72));
  WTL::CString::~CString((CProfile *)((char *)this + 64));
  WTL::CString::~CString((CProfile *)((char *)this + 56));
  WTL::CString::~CString((CProfile *)((char *)this + 48));
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v2,
    (struct _RTL_CRITICAL_SECTION *)CSingletonPtr<CProfileProps>::s_syncObject);
  if ( !--CSingletonPtr<CProfileProps>::s_lRefcount )
    CSingletonPtr<CProfileProps>::DeleteSingleton();
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v2);
}

```

## disassembly

```asm
0x180027594  push    rbx
0x180027596  sub     rsp, 30h
0x18002759a  mov     rbx, rcx
0x18002759d  lea     rax, ??_7CProfile@@6B@; const CProfile::`vftable'
0x1800275a4  mov     [rcx], rax
0x1800275a7  add     rcx, 48h ; 'H'; this
0x1800275ab  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800275b0  lea     rcx, [rbx+40h]; this
0x1800275b4  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800275b9  lea     rcx, [rbx+38h]; this
0x1800275bd  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800275c2  lea     rcx, [rbx+30h]; this
0x1800275c6  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800275cb  nop
0x1800275cc  lea     rdx, ?s_syncObject@?$CSingletonPtr@VCProfileProps@@@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection CSingletonPtr<CProfileProps>::s_syncObject
0x1800275d3  lea     rcx, [rsp+38h+var_18]
0x1800275d8  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800275dd  sub     cs:?s_lRefcount@?$CSingletonPtr@VCProfileProps@@@@0JA, 1; long CSingletonPtr<CProfileProps>::s_lRefcount
0x1800275e4  jnz     short loc_1800275EB
0x1800275e6  call    ?DeleteSingleton@?$CSingletonPtr@VCProfileProps@@@@IEAAJXZ; CSingletonPtr<CProfileProps>::DeleteSingleton(void)
0x1800275eb  lea     rcx, [rsp+38h+var_18]
0x1800275f0  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800275f5  nop
0x1800275f6  add     rsp, 30h
0x1800275fa  pop     rbx
0x1800275fb  retn
```
