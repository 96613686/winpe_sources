# cxl::SidBase::ToString(void)

- ea: `0x18001633c`
- end: `0x18001644a`
- name: `?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800191d0`
- `0x18001a240`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000ebb4`
- `0x18000f89c`
- `0x180011184`
- `0x18001182c`
- `0x18001633c`
- `0x1800165d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016412`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001639e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001639e`

## string_xrefs

- `0x180016402`: `ConvertSidToStringSidW failed`

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
    cxl::TextWriter::Write<30>(v8, "ConvertSidToStringSidW failed");
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
0x18001633c  mov     [rsp-8+arg_10], rbx
0x180016341  mov     [rsp-8+arg_18], rdi
0x180016346  push    rbp
0x180016347  lea     rbp, [rsp-57h]
0x18001634c  sub     rsp, 100h
0x180016353  mov     rax, cs:__security_cookie
0x18001635a  xor     rax, rsp
0x18001635d  mov     [rbp+57h+var_10], rax
0x180016361  mov     rdi, rdx
0x180016364  mov     rbx, rcx
0x180016367  mov     [rbp+57h+var_C8], rdx
0x18001636b  mov     [rsp+100h+var_E0], 0
0x180016373  mov     rcx, rdx
0x180016376  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001637b  mov     [rsp+100h+var_E0], 1
0x180016383  mov     rcx, [rbx+10h]; struct _SID *
0x180016387  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18001638c  mov     [rsp+100h+StringSid], 0
0x180016395  lea     rdx, [rsp+100h+StringSid]; StringSid
0x18001639a  mov     rcx, [rbx+10h]; Sid
0x18001639e  call    cs:__imp_ConvertSidToStringSidW
0x1800163a5  nop     dword ptr [rax+rax+00h]
0x1800163aa  test    eax, eax
0x1800163ac  jz      short loc_1800163EA
0x1800163ae  mov     rdx, [rsp+100h+StringSid]
0x1800163b3  mov     rcx, rdi
0x1800163b6  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800163bb  mov     rcx, [rsp+100h+StringSid]; void *
0x1800163c0  call    ?Free@LocalHeap@cxl@@SAXPEAX@Z; cxl::LocalHeap::Free(void *)
0x1800163c5  mov     rax, rdi
0x1800163c8  mov     rcx, [rbp+57h+var_10]
0x1800163cc  xor     rcx, rsp; StackCookie
0x1800163cf  call    __security_check_cookie
0x1800163d4  lea     r11, [rsp+100h+var_s0]
0x1800163dc  mov     rbx, [r11+20h]
0x1800163e0  mov     rdi, [r11+28h]
0x1800163e4  mov     rsp, r11
0x1800163e7  pop     rbp
0x1800163e8  retn
0x1800163ea  lea     rcx, [rbp+57h+var_A0]
0x1800163ee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800163f3  nop
0x1800163f4  lea     rdx, [rbp+57h+var_A0]
0x1800163f8  lea     rcx, [rbp+57h+var_C0]
0x1800163fc  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180016401  nop
0x180016402  lea     rdx, aConvertsidtost; "ConvertSidToStringSidW failed"
0x180016409  lea     rcx, [rbp+57h+var_C0]
0x18001640d  call    ??$Write@$0BO@@TextWriter@cxl@@QEAAAEAV01@AEAY0BO@$$CBD@Z; cxl::TextWriter::Write<30>(char const (&)[30])
0x180016412  call    cs:__imp_GetLastError
0x180016419  nop     dword ptr [rax+rax+00h]
0x18001641e  mov     [rbp+57h+var_D0], eax
0x180016421  mov     [rbp+57h+var_CC], 0
0x180016428  lea     r8, [rbp+57h+var_A0]
0x18001642c  lea     rdx, [rbp+57h+var_D0]
0x180016430  lea     rcx, [rbp+57h+pExceptionObject]
0x180016434  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180016439  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180016440  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180016444  call    _CxxThrowException_0
```
