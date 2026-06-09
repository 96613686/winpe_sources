# cxl::Sid::MakeSid(wchar_t const *)

- ea: `0x1800193c0`
- end: `0x1800194a4`
- name: `?MakeSid@Sid@cxl@@QEAAXPEB_W@Z`
- size: `228`
- prototype: `void __fastcall(cxl::Sid *__hidden this, LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060850`
- `0x180067a9c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f238`
- `0x1800124ac`
- `0x180015bb0`
- `0x1800193c0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001946c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001946c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019406`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019406`

## string_xrefs

- `0x18001945c`: `ConvertStringSidToSid failed`

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
    cxl::TextWriter::WriteFmt<29>(v6, "ConvertStringSidToSid failed");
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
0x1800193c0  mov     [rsp-8+arg_10], rbx
0x1800193c5  mov     [rsp-8+arg_18], rdi
0x1800193ca  push    rbp
0x1800193cb  lea     rbp, [rsp-57h]
0x1800193d0  sub     rsp, 0F0h
0x1800193d7  mov     rax, cs:__security_cookie
0x1800193de  xor     rax, rsp
0x1800193e1  mov     [rbp+57h+var_10], rax
0x1800193e5  mov     rbx, rdx
0x1800193e8  mov     rdi, rcx
0x1800193eb  mov     rax, [rcx]
0x1800193ee  mov     rax, [rax+8]
0x1800193f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f7  mov     [rbp+57h+Sid], 0
0x1800193ff  lea     rdx, [rbp+57h+Sid]; Sid
0x180019403  mov     rcx, rbx; StringSid
0x180019406  call    cs:__imp_ConvertStringSidToSidW
0x18001940d  nop     dword ptr [rax+rax+00h]
0x180019412  test    eax, eax
0x180019414  jz      short loc_180019444
0x180019416  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x18001941a  mov     rcx, rdi; this
0x18001941d  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180019422  mov     rcx, [rbp+57h+var_10]
0x180019426  xor     rcx, rsp; StackCookie
0x180019429  call    __security_check_cookie
0x18001942e  lea     r11, [rsp+0F0h+var_s0]
0x180019436  mov     rbx, [r11+20h]
0x18001943a  mov     rdi, [r11+28h]
0x18001943e  mov     rsp, r11
0x180019441  pop     rbp
0x180019442  retn
0x180019444  lea     rcx, [rbp+57h+var_A0]
0x180019448  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001944d  nop
0x18001944e  lea     rdx, [rbp+57h+var_A0]
0x180019452  lea     rcx, [rbp+57h+var_C0]
0x180019456  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001945b  nop
0x18001945c  lea     rdx, aConvertstrings; "ConvertStringSidToSid failed"
0x180019463  lea     rcx, [rbp+57h+var_C0]
0x180019467  call    ??$WriteFmt@$0BN@@TextWriter@cxl@@QEAAAEAV01@AEAY0BN@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<29>(char const (&)[29],cxl::Format const &)
0x18001946c  call    cs:__imp_GetLastError
0x180019473  nop     dword ptr [rax+rax+00h]
0x180019478  mov     [rbp+57h+var_C8], eax
0x18001947b  mov     [rbp+57h+var_C4], 0
0x180019482  lea     r8, [rbp+57h+var_A0]
0x180019486  lea     rdx, [rbp+57h+var_C8]
0x18001948a  lea     rcx, [rbp+57h+pExceptionObject]
0x18001948e  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180019493  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001949a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001949e  call    _CxxThrowException_0
```
