# cxl::SidBase::VerifySid(_SID const *)

- ea: `0x180015d8c`
- end: `0x180015e1b`
- name: `?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z`
- size: `143`
- prototype: `void __fastcall(const struct _SID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013e70`
- `0x180015a0c`
- `0x180015b24`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000e544`
- `0x180010ca4`
- `0x180015d8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015da5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015da5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    cxl::TextWriter::Write<18>((__int64)v2);
    v1 = 1337;
    cxl::Exception::Exception(pExceptionObject, &v1, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180015d8c  sub     rsp, 0F8h
0x180015d93  mov     rax, cs:__security_cookie
0x180015d9a  xor     rax, rsp
0x180015d9d  mov     [rsp+0F8h+var_18], rax
0x180015da5  call    cs:__imp_IsValidSid
0x180015dab  test    eax, eax
0x180015dad  jnz     short loc_180015E03
0x180015daf  lea     rcx, [rsp+0F8h+var_B0]
0x180015db4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015db9  nop
0x180015dba  lea     rdx, [rsp+0F8h+var_B0]
0x180015dbf  lea     rcx, [rsp+0F8h+var_D0]
0x180015dc4  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015dc9  nop
0x180015dca  lea     rcx, [rsp+0F8h+var_D0]
0x180015dcf  call    ??$Write@$0BC@@TextWriter@cxl@@QEAAAEAV01@AEAY0BC@$$CBD@Z; cxl::TextWriter::Write<18>(char const (&)[18])
0x180015dd4  mov     [rsp+0F8h+var_D8], 539h
0x180015ddd  lea     r8, [rsp+0F8h+var_B0]
0x180015de2  lea     rdx, [rsp+0F8h+var_D8]
0x180015de7  lea     rcx, [rsp+0F8h+pExceptionObject]
0x180015dec  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015df1  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015df8  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180015dfd  call    _CxxThrowException_0
0x180015e03  mov     rcx, [rsp+0F8h+var_18]
0x180015e0b  xor     rcx, rsp; StackCookie
0x180015e0e  call    __security_check_cookie
0x180015e13  add     rsp, 0F8h
0x180015e1a  retn
```
