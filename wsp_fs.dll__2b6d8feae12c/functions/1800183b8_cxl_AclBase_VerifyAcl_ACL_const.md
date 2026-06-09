# cxl::AclBase::VerifyAcl(_ACL const *)

- ea: `0x1800183b8`
- end: `0x18001844e`
- name: `?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z`
- size: `150`
- prototype: `void __fastcall(const struct _ACL *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015478`
- `0x180017ce0`
- `0x180017df4`
- `0x180017e4c`
- `0x1800180fc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ebf4`
- `0x180012028`
- `0x1800183b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1800183d1`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1800183d1`

## string_xrefs

- `0x1800183f6`: `IsValidAcl failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::AclBase::VerifyAcl(struct _ACL *a1)
{
  __int64 v1; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v2[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v3[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  if ( !IsValidAcl(a1) )
  {
    std::wstring::wstring(v3);
    cxl::StringWriter::StringWriter(v2, v3);
    cxl::TextWriter::WriteFmt<18>((__int64)v2, (__int64)"IsValidAcl failed");
    v1 = 1336;
    cxl::Exception::Exception(pExceptionObject, &v1, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800183b8  sub     rsp, 0F8h
0x1800183bf  mov     rax, cs:__security_cookie
0x1800183c6  xor     rax, rsp
0x1800183c9  mov     [rsp+0F8h+var_18], rax
0x1800183d1  call    cs:__imp_IsValidAcl
0x1800183d7  test    eax, eax
0x1800183d9  jnz     short loc_180018436
0x1800183db  lea     rcx, [rsp+0F8h+var_B0]
0x1800183e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800183e5  nop
0x1800183e6  lea     rdx, [rsp+0F8h+var_B0]
0x1800183eb  lea     rcx, [rsp+0F8h+var_D0]
0x1800183f0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800183f5  nop
0x1800183f6  lea     rdx, aIsvalidaclFail; "IsValidAcl failed"
0x1800183fd  lea     rcx, [rsp+0F8h+var_D0]
0x180018402  call    ??$WriteFmt@$0BC@@TextWriter@cxl@@QEAAAEAV01@AEAY0BC@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<18>(char const (&)[18],cxl::Format const &)
0x180018407  mov     [rsp+0F8h+var_D8], 538h
0x180018410  lea     r8, [rsp+0F8h+var_B0]
0x180018415  lea     rdx, [rsp+0F8h+var_D8]
0x18001841a  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18001841f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018424  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001842b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180018430  call    _CxxThrowException_0
0x180018436  mov     rcx, [rsp+0F8h+var_18]
0x18001843e  xor     rcx, rsp; StackCookie
0x180018441  call    __security_check_cookie
0x180018446  add     rsp, 0F8h
0x18001844d  retn
```
