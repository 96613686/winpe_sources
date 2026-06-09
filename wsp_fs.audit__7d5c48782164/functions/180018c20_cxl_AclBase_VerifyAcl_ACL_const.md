# cxl::AclBase::VerifyAcl(_ACL const *)

- ea: `0x180018c20`
- end: `0x180018cbd`
- name: `?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z`
- size: `157`
- prototype: `void __fastcall(const struct _ACL *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015b7c`
- `0x1800184e0`
- `0x180018600`
- `0x180018658`
- `0x180018938`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f034`
- `0x1800124ac`
- `0x180018c20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180018c39`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180018c39`

## string_xrefs

- `0x180018c64`: `IsValidAcl failed`

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
    cxl::TextWriter::WriteFmt<18>(v2, "IsValidAcl failed");
    v1 = 1336;
    cxl::Exception::Exception(pExceptionObject, &v1, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180018c20  sub     rsp, 0F8h
0x180018c27  mov     rax, cs:__security_cookie
0x180018c2e  xor     rax, rsp
0x180018c31  mov     [rsp+0F8h+var_18], rax
0x180018c39  call    cs:__imp_IsValidAcl
0x180018c40  nop     dword ptr [rax+rax+00h]
0x180018c45  test    eax, eax
0x180018c47  jnz     short loc_180018CA4
0x180018c49  lea     rcx, [rsp+0F8h+var_B0]
0x180018c4e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018c53  nop
0x180018c54  lea     rdx, [rsp+0F8h+var_B0]
0x180018c59  lea     rcx, [rsp+0F8h+var_D0]
0x180018c5e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018c63  nop
0x180018c64  lea     rdx, aIsvalidaclFail; "IsValidAcl failed"
0x180018c6b  lea     rcx, [rsp+0F8h+var_D0]
0x180018c70  call    ??$WriteFmt@$0BC@@TextWriter@cxl@@QEAAAEAV01@AEAY0BC@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<18>(char const (&)[18],cxl::Format const &)
0x180018c75  mov     [rsp+0F8h+var_D8], 538h
0x180018c7e  lea     r8, [rsp+0F8h+var_B0]
0x180018c83  lea     rdx, [rsp+0F8h+var_D8]
0x180018c88  lea     rcx, [rsp+0F8h+pExceptionObject]
0x180018c8d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018c92  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018c99  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180018c9e  call    _CxxThrowException_0
0x180018ca4  mov     rcx, [rsp+0F8h+var_18]
0x180018cac  xor     rcx, rsp; StackCookie
0x180018caf  call    __security_check_cookie
0x180018cb4  add     rsp, 0F8h
0x180018cbb  retn
```
