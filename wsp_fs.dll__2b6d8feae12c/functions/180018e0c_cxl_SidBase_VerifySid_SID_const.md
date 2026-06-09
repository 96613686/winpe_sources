# cxl::SidBase::VerifySid(_SID const *)

- ea: `0x180018e0c`
- end: `0x180018ea2`
- name: `?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z`
- size: `150`
- prototype: `void __fastcall(const struct _SID *)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800154ac`
- `0x180017e4c`
- `0x1800180fc`
- `0x18001873c`
- `0x180018890`
- `0x180018ba4`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ebf4`
- `0x180012028`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018e25`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018e25`

## string_xrefs

- `0x180018e4a`: `IsValidSid failed`

## pseudocode

```c
void __fastcall cxl::SidBase::VerifySid(struct _SID *a1)
{
  __int64 v1; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v2[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v3[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  if ( !IsValidSid(a1) )
  {
    std::wstring::wstring(v3);
    cxl::StringWriter::StringWriter(v2, v3);
    cxl::TextWriter::WriteFmt<18>((__int64)v2, (__int64)"IsValidSid failed");
    v1 = 1337;
    cxl::Exception::Exception(pExceptionObject, &v1, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180018e0c  sub     rsp, 0F8h
0x180018e13  mov     rax, cs:__security_cookie
0x180018e1a  xor     rax, rsp
0x180018e1d  mov     [rsp+0F8h+var_18], rax
0x180018e25  call    cs:__imp_IsValidSid
0x180018e2b  test    eax, eax
0x180018e2d  jnz     short loc_180018E8A
0x180018e2f  lea     rcx, [rsp+0F8h+var_B0]
0x180018e34  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018e39  nop
0x180018e3a  lea     rdx, [rsp+0F8h+var_B0]
0x180018e3f  lea     rcx, [rsp+0F8h+var_D0]
0x180018e44  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018e49  nop
0x180018e4a  lea     rdx, aIsvalidsidFail; "IsValidSid failed"
0x180018e51  lea     rcx, [rsp+0F8h+var_D0]
0x180018e56  call    ??$WriteFmt@$0BC@@TextWriter@cxl@@QEAAAEAV01@AEAY0BC@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<18>(char const (&)[18],cxl::Format const &)
0x180018e5b  mov     [rsp+0F8h+var_D8], 539h
0x180018e64  lea     r8, [rsp+0F8h+var_B0]
0x180018e69  lea     rdx, [rsp+0F8h+var_D8]
0x180018e6e  lea     rcx, [rsp+0F8h+pExceptionObject]
0x180018e73  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018e78  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018e7f  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180018e84  call    _CxxThrowException_0
0x180018e8a  mov     rcx, [rsp+0F8h+var_18]
0x180018e92  xor     rcx, rsp; StackCookie
0x180018e95  call    __security_check_cookie
0x180018e9a  add     rsp, 0F8h
0x180018ea1  retn
```
