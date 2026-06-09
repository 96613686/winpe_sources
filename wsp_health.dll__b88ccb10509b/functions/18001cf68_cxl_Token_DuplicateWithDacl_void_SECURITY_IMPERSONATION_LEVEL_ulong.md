# cxl::Token::DuplicateWithDacl(void *,_SECURITY_IMPERSONATION_LEVEL,ulong)

- ea: `0x18001cf68`
- end: `0x18001d08b`
- name: `?DuplicateWithDacl@Token@cxl@@QEAAXPEAXW4_SECURITY_IMPERSONATION_LEVEL@@K@Z`
- size: `291`
- prototype: `void __fastcall(cxl::Token *__hidden this, void *, enum _SECURITY_IMPERSONATION_LEVEL, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d6d8`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x1800112f0`
- `0x180013ec0`
- `0x18001ce88`
- `0x18001cf68`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18001cfda`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18001cfda`

## string_xrefs

- `0x18001cfe6`: `GetSecurityInfo( existingTokenHandle, SE_KERNEL_OBJECT, DACL_SECURITY_INFORMATION, NULL, NULL, NULL, NULL, &pSecDesc )`

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
0x18001cf68  mov     [rsp-8+arg_10], rbx
0x18001cf6d  push    rbp
0x18001cf6e  push    rsi
0x18001cf6f  push    rdi
0x18001cf70  lea     rbp, [rsp-20h]
0x18001cf75  sub     rsp, 120h
0x18001cf7c  mov     rax, cs:__security_cookie
0x18001cf83  xor     rax, rsp
0x18001cf86  mov     [rbp+30h+var_20], rax
0x18001cf8a  mov     rsi, rdx
0x18001cf8d  mov     rdi, rcx
0x18001cf90  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001cf95  mov     [rsp+130h+var_E8], 0
0x18001cf9e  mov     [rsp+130h+var_D8], 0
0x18001cfa7  lea     rax, [rsp+130h+var_E8]
0x18001cfac  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18001cfb1  mov     [rsp+130h+ppSacl], 0; ppSacl
0x18001cfba  mov     [rsp+130h+ppDacl], 0; enum _TOKEN_TYPE
0x18001cfc3  mov     [rsp+130h+ppsidGroup], 0; enum _SECURITY_IMPERSONATION_LEVEL
0x18001cfcc  xor     r9d, r9d; ppsidOwner
0x18001cfcf  lea     edx, [r9+6]; ObjectType
0x18001cfd3  lea     r8d, [r9+4]; SecurityInfo
0x18001cfd7  mov     rcx, rsi; handle
0x18001cfda  call    cs:__imp_GetSecurityInfo
0x18001cfe0  mov     ebx, eax
0x18001cfe2  test    eax, eax
0x18001cfe4  jz      short loc_18001D026
0x18001cfe6  lea     rdx, aGetsecurityinf; "GetSecurityInfo( existingTokenHandle, S"...
0x18001cfed  lea     rcx, [rsp+130h+var_B8]
0x18001cff2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001cff7  nop
0x18001cff8  mov     [rsp+130h+var_F0], ebx
0x18001cffc  mov     [rsp+130h+var_EC], 0
0x18001d004  mov     r8, rax
0x18001d007  lea     rdx, [rsp+130h+var_F0]
0x18001d00c  lea     rcx, [rbp+30h+pExceptionObject]
0x18001d010  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001d015  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001d01c  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18001d020  call    _CxxThrowException_0
0x18001d026  mov     rbx, [rsp+130h+var_E8]
0x18001d02b  lea     rcx, [rsp+130h+var_E0]
0x18001d030  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001d035  mov     [rsp+130h+var_D8], rbx
0x18001d03a  mov     qword ptr [rsp+130h+var_D0.nLength], 18h
0x18001d043  mov     qword ptr [rsp+130h+var_D0.bInheritHandle], 1
0x18001d04c  mov     [rsp+130h+var_D0.lpSecurityDescriptor], rbx
0x18001d051  lea     r9, [rsp+130h+var_D0]; struct _SECURITY_ATTRIBUTES *
0x18001d056  mov     rdx, rsi; void *
0x18001d059  mov     rcx, rdi; this
0x18001d05c  call    ?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x18001d061  nop
0x18001d062  lea     rcx, [rsp+130h+var_E0]
0x18001d067  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001d06c  mov     rcx, [rbp+30h+var_20]
0x18001d070  xor     rcx, rsp; StackCookie
0x18001d073  call    __security_check_cookie
0x18001d078  mov     rbx, [rsp+130h+arg_10]
0x18001d080  add     rsp, 120h
0x18001d087  pop     rdi
0x18001d088  pop     rsi
0x18001d089  pop     rbp
0x18001d08a  retn
```
