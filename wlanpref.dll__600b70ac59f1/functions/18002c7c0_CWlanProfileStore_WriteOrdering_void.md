# CWlanProfileStore::WriteOrdering(void)

- ea: `0x18002c7c0`
- end: `0x18002c8a1`
- name: `?WriteOrdering@CWlanProfileStore@@UEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CWlanProfileStore *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x18000cee0`
- `0x18002c7c0`
- `0x18002d840`

## import_xrefs

- `wlanapi!WlanSetProfilePosition` at `0x18002c847`
- `wlanapi!WlanSetProfilePosition` at `0x18002c847`

## pseudocode

```c
__int64 __fastcall CWlanProfileStore::WriteOrdering(CWlanProfileStore *this)
{
  __int64 v2; // rbp
  _QWORD *v3; // rdi
  signed int v4; // eax
  signed int v5; // ebx
  LPCWSTR strProfileName; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v8[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v9[16]; // [rsp+48h] [rbp-50h] BYREF
  GUID pInterfaceGuid; // [rsp+58h] [rbp-40h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v9,
    (char *)this + 96);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v8,
    (char *)this + 872);
  v2 = *((_QWORD *)this + 19);
  v3 = (_QWORD *)*((_QWORD *)this + 23);
  while ( v3 )
  {
    WTL::CString::CString((WTL::CString *)&strProfileName, (const struct WTL::CString *)(v3 + 8));
    pInterfaceGuid = (GUID)xmmword_1800403B8;
    v4 = WlanSetProfilePosition(*((HANDLE *)this + 29), &pInterfaceGuid, strProfileName, v2, 0);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    WTL::CString::~CString((WTL::CString *)&strProfileName);
    if ( v5 < 0 )
      goto LABEL_8;
    v3 = (_QWORD *)*v3;
    LODWORD(v2) = v2 + 1;
  }
  v5 = 0;
LABEL_8:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c7c0  push    rbx
0x18002c7c2  push    rbp
0x18002c7c3  push    rsi
0x18002c7c4  push    rdi
0x18002c7c5  sub     rsp, 78h
0x18002c7c9  mov     rax, cs:__security_cookie
0x18002c7d0  xor     rax, rsp
0x18002c7d3  mov     [rsp+98h+var_30], rax
0x18002c7d8  mov     rsi, rcx
0x18002c7db  lea     rdx, [rcx+60h]
0x18002c7df  lea     rcx, [rsp+98h+var_50]
0x18002c7e4  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c7e9  nop
0x18002c7ea  lea     rdx, [rsi+368h]
0x18002c7f1  lea     rcx, [rsp+98h+var_60]
0x18002c7f6  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002c7fb  nop
0x18002c7fc  mov     rbp, [rsi+98h]
0x18002c803  mov     rdi, [rsi+0B8h]
0x18002c80a  test    rdi, rdi
0x18002c80d  jz      short loc_18002C872
0x18002c80f  lea     rdx, [rdi+40h]; struct WTL::CString *
0x18002c813  lea     rcx, [rsp+98h+strProfileName]; this
0x18002c818  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18002c81d  movups  xmm0, cs:xmmword_1800403B8
0x18002c824  movdqu  xmmword ptr [rsp+98h+pInterfaceGuid.Data1], xmm0
0x18002c82a  mov     r9d, ebp; dwPosition
0x18002c82d  mov     [rsp+98h+pReserved], 0; pReserved
0x18002c836  mov     r8, [rsp+98h+strProfileName]; strProfileName
0x18002c83b  lea     rdx, [rsp+98h+pInterfaceGuid]; pInterfaceGuid
0x18002c840  mov     rcx, [rsi+0E8h]; hClientHandle
0x18002c847  call    cs:__imp_WlanSetProfilePosition
0x18002c84d  mov     ebx, eax
0x18002c84f  test    eax, eax
0x18002c851  jle     short loc_18002C85C
0x18002c853  movzx   ebx, ax
0x18002c856  or      ebx, 80070000h
0x18002c85c  lea     rcx, [rsp+98h+strProfileName]; this
0x18002c861  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c866  test    ebx, ebx
0x18002c868  js      short loc_18002C874
0x18002c86a  mov     rdi, [rdi]
0x18002c86d  inc     rbp
0x18002c870  jmp     short loc_18002C80A
0x18002c872  xor     ebx, ebx
0x18002c874  lea     rcx, [rsp+98h+var_60]
0x18002c879  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c87e  nop
0x18002c87f  lea     rcx, [rsp+98h+var_50]
0x18002c884  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002c889  mov     eax, ebx
0x18002c88b  mov     rcx, [rsp+98h+var_30]
0x18002c890  xor     rcx, rsp; StackCookie
0x18002c893  call    __security_check_cookie
0x18002c898  add     rsp, 78h
0x18002c89c  pop     rdi
0x18002c89d  pop     rsi
0x18002c89e  pop     rbp
0x18002c89f  pop     rbx
0x18002c8a0  retn
```
