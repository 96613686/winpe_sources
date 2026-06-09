# cxl::Token::DuplicateWithDacl(void *,_SECURITY_IMPERSONATION_LEVEL,ulong)

- ea: `0x1800201b8`
- end: `0x1800202db`
- name: `?DuplicateWithDacl@Token@cxl@@QEAAXPEAXW4_SECURITY_IMPERSONATION_LEVEL@@K@Z`
- size: `291`
- prototype: `void __fastcall(cxl::Token *__hidden this, void *, enum _SECURITY_IMPERSONATION_LEVEL, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020928`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x180012660`
- `0x1800154e0`
- `0x1800200d8`
- `0x1800201b8`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002022a`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002022a`

## string_xrefs

- `0x180020236`: `GetSecurityInfo( existingTokenHandle, SE_KERNEL_OBJECT, DACL_SECURITY_INFORMATION, NULL, NULL, NULL, NULL, &pSecDesc )`

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
0x1800201b8  mov     [rsp-8+arg_10], rbx
0x1800201bd  push    rbp
0x1800201be  push    rsi
0x1800201bf  push    rdi
0x1800201c0  lea     rbp, [rsp-20h]
0x1800201c5  sub     rsp, 120h
0x1800201cc  mov     rax, cs:__security_cookie
0x1800201d3  xor     rax, rsp
0x1800201d6  mov     [rbp+30h+var_20], rax
0x1800201da  mov     rsi, rdx
0x1800201dd  mov     rdi, rcx
0x1800201e0  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x1800201e5  mov     [rsp+130h+var_E8], 0
0x1800201ee  mov     [rsp+130h+var_D8], 0
0x1800201f7  lea     rax, [rsp+130h+var_E8]
0x1800201fc  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180020201  mov     [rsp+130h+ppSacl], 0; ppSacl
0x18002020a  mov     [rsp+130h+ppDacl], 0; enum _TOKEN_TYPE
0x180020213  mov     [rsp+130h+ppsidGroup], 0; enum _SECURITY_IMPERSONATION_LEVEL
0x18002021c  xor     r9d, r9d; ppsidOwner
0x18002021f  lea     edx, [r9+6]; ObjectType
0x180020223  lea     r8d, [r9+4]; SecurityInfo
0x180020227  mov     rcx, rsi; handle
0x18002022a  call    cs:__imp_GetSecurityInfo
0x180020230  mov     ebx, eax
0x180020232  test    eax, eax
0x180020234  jz      short loc_180020276
0x180020236  lea     rdx, aGetsecurityinf; "GetSecurityInfo( existingTokenHandle, S"...
0x18002023d  lea     rcx, [rsp+130h+var_B8]
0x180020242  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020247  nop
0x180020248  mov     [rsp+130h+var_F0], ebx
0x18002024c  mov     [rsp+130h+var_EC], 0
0x180020254  mov     r8, rax
0x180020257  lea     rdx, [rsp+130h+var_F0]
0x18002025c  lea     rcx, [rbp+30h+pExceptionObject]
0x180020260  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020265  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18002026c  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180020270  call    _CxxThrowException_0
0x180020276  mov     rbx, [rsp+130h+var_E8]
0x18002027b  lea     rcx, [rsp+130h+var_E0]
0x180020280  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180020285  mov     [rsp+130h+var_D8], rbx
0x18002028a  mov     qword ptr [rsp+130h+var_D0.nLength], 18h
0x180020293  mov     qword ptr [rsp+130h+var_D0.bInheritHandle], 1
0x18002029c  mov     [rsp+130h+var_D0.lpSecurityDescriptor], rbx
0x1800202a1  lea     r9, [rsp+130h+var_D0]; struct _SECURITY_ATTRIBUTES *
0x1800202a6  mov     rdx, rsi; void *
0x1800202a9  mov     rcx, rdi; this
0x1800202ac  call    ?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x1800202b1  nop
0x1800202b2  lea     rcx, [rsp+130h+var_E0]
0x1800202b7  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x1800202bc  mov     rcx, [rbp+30h+var_20]
0x1800202c0  xor     rcx, rsp; StackCookie
0x1800202c3  call    __security_check_cookie
0x1800202c8  mov     rbx, [rsp+130h+arg_10]
0x1800202d0  add     rsp, 120h
0x1800202d7  pop     rdi
0x1800202d8  pop     rsi
0x1800202d9  pop     rbp
0x1800202da  retn
```
