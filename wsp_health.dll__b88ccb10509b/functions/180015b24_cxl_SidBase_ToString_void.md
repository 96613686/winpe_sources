# cxl::SidBase::ToString(void)

- ea: `0x180015b24`
- end: `0x180015c25`
- name: `?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001880c`
- `0x180019838`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000e724`
- `0x18000f3e8`
- `0x180010ca4`
- `0x18001131c`
- `0x180015b24`
- `0x180015d8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bf3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015b86`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015b86`

## string_xrefs

- `0x180015be3`: `ConvertSidToStringSidW failed`

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
    cxl::TextWriter::Write<30>((__int64)v8, (__int64)"ConvertSidToStringSidW failed");
    v6[0] = GetLastError();
    v6[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v6, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::wstring::assign(a2, StringSid);
  cxl::LocalHeap::Free(StringSid);
  return a2;
}

```

## disassembly

```asm
0x180015b24  mov     [rsp-8+arg_10], rbx
0x180015b29  mov     [rsp-8+arg_18], rdi
0x180015b2e  push    rbp
0x180015b2f  lea     rbp, [rsp-57h]
0x180015b34  sub     rsp, 100h
0x180015b3b  mov     rax, cs:__security_cookie
0x180015b42  xor     rax, rsp
0x180015b45  mov     [rbp+57h+var_10], rax
0x180015b49  mov     rdi, rdx
0x180015b4c  mov     rbx, rcx
0x180015b4f  mov     [rbp+57h+var_C8], rdx
0x180015b53  mov     [rsp+100h+var_E0], 0
0x180015b5b  mov     rcx, rdx
0x180015b5e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015b63  mov     [rsp+100h+var_E0], 1
0x180015b6b  mov     rcx, [rbx+10h]; struct _SID *
0x180015b6f  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180015b74  mov     [rsp+100h+StringSid], 0
0x180015b7d  lea     rdx, [rsp+100h+StringSid]; StringSid
0x180015b82  mov     rcx, [rbx+10h]; Sid
0x180015b86  call    cs:__imp_ConvertSidToStringSidW
0x180015b8c  test    eax, eax
0x180015b8e  jz      short loc_180015BCB
0x180015b90  mov     rdx, [rsp+100h+StringSid]
0x180015b95  mov     rcx, rdi
0x180015b98  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180015b9d  mov     rcx, [rsp+100h+StringSid]; void *
0x180015ba2  call    ?Free@LocalHeap@cxl@@SAXPEAX@Z; cxl::LocalHeap::Free(void *)
0x180015ba7  mov     rax, rdi
0x180015baa  mov     rcx, [rbp+57h+var_10]
0x180015bae  xor     rcx, rsp; StackCookie
0x180015bb1  call    __security_check_cookie
0x180015bb6  lea     r11, [rsp+100h+var_s0]
0x180015bbe  mov     rbx, [r11+20h]
0x180015bc2  mov     rdi, [r11+28h]
0x180015bc6  mov     rsp, r11
0x180015bc9  pop     rbp
0x180015bca  retn
0x180015bcb  lea     rcx, [rbp+57h+var_A0]
0x180015bcf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015bd4  nop
0x180015bd5  lea     rdx, [rbp+57h+var_A0]
0x180015bd9  lea     rcx, [rbp+57h+var_C0]
0x180015bdd  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015be2  nop
0x180015be3  lea     rdx, aConvertsidtost; "ConvertSidToStringSidW failed"
0x180015bea  lea     rcx, [rbp+57h+var_C0]
0x180015bee  call    ??$Write@$0BO@@TextWriter@cxl@@QEAAAEAV01@AEAY0BO@$$CBD@Z; cxl::TextWriter::Write<30>(char const (&)[30])
0x180015bf3  call    cs:__imp_GetLastError
0x180015bf9  mov     [rbp+57h+var_D0], eax
0x180015bfc  mov     [rbp+57h+var_CC], 0
0x180015c03  lea     r8, [rbp+57h+var_A0]
0x180015c07  lea     rdx, [rbp+57h+var_D0]
0x180015c0b  lea     rcx, [rbp+57h+pExceptionObject]
0x180015c0f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015c14  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015c1b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180015c1f  call    _CxxThrowException_0
```
