# cxl::Token::DuplicateWithDacl(void *,_SECURITY_IMPERSONATION_LEVEL,ulong)

- ea: `0x180020e3c`
- end: `0x180020f66`
- name: `?DuplicateWithDacl@Token@cxl@@QEAAXPEAXW4_SECURITY_IMPERSONATION_LEVEL@@K@Z`
- size: `298`
- prototype: `void __fastcall(cxl::Token *__hidden this, void *, enum _SECURITY_IMPERSONATION_LEVEL, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800215c0`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x180012b00`
- `0x180015be4`
- `0x180020d50`
- `0x180020e3c`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180020eae`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180020eae`

## string_xrefs

- `0x180020ec0`: `GetSecurityInfo( existingTokenHandle, SE_KERNEL_OBJECT, DACL_SECURITY_INFORMATION, NULL, NULL, NULL, NULL, &pSecDesc )`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::Token::DuplicateWithDacl(cxl::Token *this, void *a2, enum _SECURITY_IMPERSONATION_LEVEL a3)
{
  DWORD SecurityInfo; // ebx
  __int64 v6; // rax
  PSECURITY_DESCRIPTOR v7; // rbx
  unsigned int v8; // r8d
  enum _SECURITY_IMPERSONATION_LEVEL ppsidGroup; // [rsp+20h] [rbp-E0h]
  enum _TOKEN_TYPE ppDacl; // [rsp+28h] [rbp-D8h]
  _DWORD v11[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR v14; // [rsp+58h] [rbp-A8h]
  _SECURITY_ATTRIBUTES v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  cxl::Token::Clear(this);
  ppSecurityDescriptor = 0;
  v14 = 0;
  SecurityInfo = GetSecurityInfo(a2, SE_KERNEL_OBJECT, 4u, 0, 0, 0, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    v6 = std::wstring::wstring(
           v16,
           L"GetSecurityInfo( existingTokenHandle, SE_KERNEL_OBJECT, DACL_SECURITY_INFORMATION, NULL, NULL, NULL, NULL, &pSecDesc )");
    v11[0] = SecurityInfo;
    v11[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v11, v6);
    throw (cxl::Exception *)pExceptionObject;
  }
  v7 = ppSecurityDescriptor;
  cxl::LocalHeapPtr<unsigned char>::Clear(v13);
  v14 = v7;
  *(_QWORD *)&v15.nLength = 24;
  *(_QWORD *)&v15.bInheritHandle = 1;
  v15.lpSecurityDescriptor = v7;
  cxl::Token::DuplicateEx(this, a2, v8, &v15, ppsidGroup, ppDacl);
  cxl::LocalHeapPtr<unsigned char>::Clear(v13);
}

```

## disassembly

```asm
0x180020e3c  mov     [rsp-8+arg_10], rbx
0x180020e41  push    rbp
0x180020e42  push    rsi
0x180020e43  push    rdi
0x180020e44  lea     rbp, [rsp-20h]
0x180020e49  sub     rsp, 120h
0x180020e50  mov     rax, cs:__security_cookie
0x180020e57  xor     rax, rsp
0x180020e5a  mov     [rbp+30h+var_20], rax
0x180020e5e  mov     rsi, rdx
0x180020e61  mov     rdi, rcx
0x180020e64  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180020e69  mov     [rsp+130h+var_E8], 0
0x180020e72  mov     [rsp+130h+var_D8], 0
0x180020e7b  lea     rax, [rsp+130h+var_E8]
0x180020e80  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180020e85  mov     [rsp+130h+ppSacl], 0; ppSacl
0x180020e8e  mov     [rsp+130h+ppDacl], 0; enum _TOKEN_TYPE
0x180020e97  mov     [rsp+130h+ppsidGroup], 0; enum _SECURITY_IMPERSONATION_LEVEL
0x180020ea0  xor     r9d, r9d; ppsidOwner
0x180020ea3  lea     edx, [r9+6]; ObjectType
0x180020ea7  lea     r8d, [r9+4]; SecurityInfo
0x180020eab  mov     rcx, rsi; handle
0x180020eae  call    cs:__imp_GetSecurityInfo
0x180020eb5  nop     dword ptr [rax+rax+00h]
0x180020eba  mov     ebx, eax
0x180020ebc  test    eax, eax
0x180020ebe  jz      short loc_180020F00
0x180020ec0  lea     rdx, aGetsecurityinf; "GetSecurityInfo( existingTokenHandle, S"...
0x180020ec7  lea     rcx, [rsp+130h+var_B8]
0x180020ecc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020ed1  nop
0x180020ed2  mov     [rsp+130h+var_F0], ebx
0x180020ed6  mov     [rsp+130h+var_EC], 0
0x180020ede  mov     r8, rax
0x180020ee1  lea     rdx, [rsp+130h+var_F0]
0x180020ee6  lea     rcx, [rbp+30h+pExceptionObject]
0x180020eea  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020eef  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020ef6  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180020efa  call    _CxxThrowException_0
0x180020f00  mov     rbx, [rsp+130h+var_E8]
0x180020f05  lea     rcx, [rsp+130h+var_E0]
0x180020f0a  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180020f0f  mov     [rsp+130h+var_D8], rbx
0x180020f14  mov     qword ptr [rsp+130h+var_D0.nLength], 18h
0x180020f1d  mov     qword ptr [rsp+130h+var_D0.bInheritHandle], 1
0x180020f26  mov     [rsp+130h+var_D0.lpSecurityDescriptor], rbx
0x180020f2b  lea     r9, [rsp+130h+var_D0]; struct _SECURITY_ATTRIBUTES *
0x180020f30  mov     rdx, rsi; void *
0x180020f33  mov     rcx, rdi; this
0x180020f36  call    ?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x180020f3b  nop
0x180020f3c  lea     rcx, [rsp+130h+var_E0]
0x180020f41  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180020f46  mov     rcx, [rbp+30h+var_20]
0x180020f4a  xor     rcx, rsp; StackCookie
0x180020f4d  call    __security_check_cookie
0x180020f52  mov     rbx, [rsp+130h+arg_10]
0x180020f5a  add     rsp, 120h
0x180020f61  pop     rdi
0x180020f62  pop     rsi
0x180020f63  pop     rbp
0x180020f64  retn
```
