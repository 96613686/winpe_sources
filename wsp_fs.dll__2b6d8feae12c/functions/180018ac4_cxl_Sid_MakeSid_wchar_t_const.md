# cxl::Sid::MakeSid(wchar_t const *)

- ea: `0x180018ac4`
- end: `0x180018b9b`
- name: `?MakeSid@Sid@cxl@@QEAAXPEB_W@Z`
- size: `215`
- prototype: `void __fastcall(cxl::Sid *__hidden this, LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f634`
- `0x1800667cc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000edf8`
- `0x180012028`
- `0x1800154ac`
- `0x180018ac4`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018b0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018b0a`

## string_xrefs

- `0x180018b59`: `ConvertStringSidToSid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::Sid::MakeSid(cxl::Sid *this, LPCWSTR StringSid)
{
  PSID Sid; // [rsp+20h] [rbp-79h] BYREF
  _DWORD v5[2]; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-29h] BYREF

  (*(void (__fastcall **)(cxl::Sid *))(*(_QWORD *)this + 8LL))(this);
  Sid = 0;
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    cxl::TextWriter::WriteFmt<29>((__int64)v6, (__int64)"ConvertStringSidToSid failed");
    v5[0] = GetLastError();
    v5[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v5, v7);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::SidBase::Attach(this, (struct _SID *)Sid);
}

```

## disassembly

```asm
0x180018ac4  mov     [rsp-8+arg_10], rbx
0x180018ac9  mov     [rsp-8+arg_18], rdi
0x180018ace  push    rbp
0x180018acf  lea     rbp, [rsp-57h]
0x180018ad4  sub     rsp, 0F0h
0x180018adb  mov     rax, cs:__security_cookie
0x180018ae2  xor     rax, rsp
0x180018ae5  mov     [rbp+57h+var_10], rax
0x180018ae9  mov     rbx, rdx
0x180018aec  mov     rdi, rcx
0x180018aef  mov     rax, [rcx]
0x180018af2  mov     rax, [rax+8]
0x180018af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018afb  mov     [rbp+57h+Sid], 0
0x180018b03  lea     rdx, [rbp+57h+Sid]; Sid
0x180018b07  mov     rcx, rbx; StringSid
0x180018b0a  call    cs:__imp_ConvertStringSidToSidW
0x180018b10  test    eax, eax
0x180018b12  jz      short loc_180018B41
0x180018b14  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x180018b18  mov     rcx, rdi; this
0x180018b1b  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180018b20  mov     rcx, [rbp+57h+var_10]
0x180018b24  xor     rcx, rsp; StackCookie
0x180018b27  call    __security_check_cookie
0x180018b2c  lea     r11, [rsp+0F0h+var_s0]
0x180018b34  mov     rbx, [r11+20h]
0x180018b38  mov     rdi, [r11+28h]
0x180018b3c  mov     rsp, r11
0x180018b3f  pop     rbp
0x180018b40  retn
0x180018b41  lea     rcx, [rbp+57h+var_A0]
0x180018b45  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018b4a  nop
0x180018b4b  lea     rdx, [rbp+57h+var_A0]
0x180018b4f  lea     rcx, [rbp+57h+var_C0]
0x180018b53  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018b58  nop
0x180018b59  lea     rdx, aConvertstrings; "ConvertStringSidToSid failed"
0x180018b60  lea     rcx, [rbp+57h+var_C0]
0x180018b64  call    ??$WriteFmt@$0BN@@TextWriter@cxl@@QEAAAEAV01@AEAY0BN@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<29>(char const (&)[29],cxl::Format const &)
0x180018b69  call    cs:__imp_GetLastError
0x180018b6f  mov     [rbp+57h+var_C8], eax
0x180018b72  mov     [rbp+57h+var_C4], 0
0x180018b79  lea     r8, [rbp+57h+var_A0]
0x180018b7d  lea     rdx, [rbp+57h+var_C8]
0x180018b81  lea     rcx, [rbp+57h+pExceptionObject]
0x180018b85  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018b8a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018b91  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018b95  call    _CxxThrowException_0
```
