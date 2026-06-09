# cxl::SidBase::ToString(void)

- ea: `0x180018ba4`
- end: `0x180018ca5`
- name: `?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `257`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800174b0`
- `0x180017580`
- `0x18001b8ec`
- `0x18001c91c`
- `0x180060e9c`
- `0x180066b84`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ee24`
- `0x18001072c`
- `0x180012028`
- `0x18001268c`
- `0x180018ba4`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c73`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018c06`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018c06`

## string_xrefs

- `0x180018c63`: `ConvertSidToStringSidW failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall cxl::SidBase::ToString(__int64 a1, __int64 a2)
{
  LPWSTR StringSid; // [rsp+28h] [rbp-81h] BYREF
  _DWORD v6[2]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v7; // [rsp+38h] [rbp-71h]
  _BYTE v8[32]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-29h] BYREF

  v7 = a2;
  std::wstring::wstring(a2);
  cxl::SidBase::VerifySid(*(const struct _SID **)(a1 + 16));
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)(a1 + 16), &StringSid) )
  {
    std::wstring::wstring(v9);
    cxl::StringWriter::StringWriter(v8, v9);
    cxl::TextWriter::WriteFmt<30>((__int64)v8, (__int64)"ConvertSidToStringSidW failed");
    v6[0] = GetLastError();
    v6[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v6, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::wstring::assign(a2);
  cxl::LocalHeap::Free(StringSid);
  return a2;
}

```

## disassembly

```asm
0x180018ba4  mov     [rsp-8+arg_10], rbx
0x180018ba9  mov     [rsp-8+arg_18], rdi
0x180018bae  push    rbp
0x180018baf  lea     rbp, [rsp-57h]
0x180018bb4  sub     rsp, 100h
0x180018bbb  mov     rax, cs:__security_cookie
0x180018bc2  xor     rax, rsp
0x180018bc5  mov     [rbp+57h+var_10], rax
0x180018bc9  mov     rdi, rdx
0x180018bcc  mov     rbx, rcx
0x180018bcf  mov     [rbp+57h+var_C8], rdx
0x180018bd3  mov     [rsp+100h+var_E0], 0
0x180018bdb  mov     rcx, rdx
0x180018bde  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018be3  mov     [rsp+100h+var_E0], 1
0x180018beb  mov     rcx, [rbx+10h]; struct _SID *
0x180018bef  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180018bf4  mov     [rsp+100h+StringSid], 0
0x180018bfd  lea     rdx, [rsp+100h+StringSid]; StringSid
0x180018c02  mov     rcx, [rbx+10h]; Sid
0x180018c06  call    cs:__imp_ConvertSidToStringSidW
0x180018c0c  test    eax, eax
0x180018c0e  jz      short loc_180018C4B
0x180018c10  mov     rdx, [rsp+100h+StringSid]
0x180018c15  mov     rcx, rdi
0x180018c18  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180018c1d  mov     rcx, [rsp+100h+StringSid]; void *
0x180018c22  call    ?Free@LocalHeap@cxl@@SAXPEAX@Z; cxl::LocalHeap::Free(void *)
0x180018c27  mov     rax, rdi
0x180018c2a  mov     rcx, [rbp+57h+var_10]
0x180018c2e  xor     rcx, rsp; StackCookie
0x180018c31  call    __security_check_cookie
0x180018c36  lea     r11, [rsp+100h+var_s0]
0x180018c3e  mov     rbx, [r11+20h]
0x180018c42  mov     rdi, [r11+28h]
0x180018c46  mov     rsp, r11
0x180018c49  pop     rbp
0x180018c4a  retn
0x180018c4b  lea     rcx, [rbp+57h+var_A0]
0x180018c4f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018c54  nop
0x180018c55  lea     rdx, [rbp+57h+var_A0]
0x180018c59  lea     rcx, [rbp+57h+var_C0]
0x180018c5d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018c62  nop
0x180018c63  lea     rdx, aConvertsidtost; "ConvertSidToStringSidW failed"
0x180018c6a  lea     rcx, [rbp+57h+var_C0]
0x180018c6e  call    ??$WriteFmt@$0BO@@TextWriter@cxl@@QEAAAEAV01@AEAY0BO@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<30>(char const (&)[30],cxl::Format const &)
0x180018c73  call    cs:__imp_GetLastError
0x180018c79  mov     [rbp+57h+var_D0], eax
0x180018c7c  mov     [rbp+57h+var_CC], 0
0x180018c83  lea     r8, [rbp+57h+var_A0]
0x180018c87  lea     rdx, [rbp+57h+var_D0]
0x180018c8b  lea     rcx, [rbp+57h+pExceptionObject]
0x180018c8f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018c94  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018c9b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018c9f  call    _CxxThrowException_0
```
