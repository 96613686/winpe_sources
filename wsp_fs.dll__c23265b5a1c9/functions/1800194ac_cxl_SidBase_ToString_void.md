# cxl::SidBase::ToString(void)

- ea: `0x1800194ac`
- end: `0x1800195ba`
- name: `?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `270`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017c60`
- `0x180017d30`
- `0x18001c3a0`
- `0x18001d418`
- `0x1800620cc`
- `0x180067e54`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f264`
- `0x180010b90`
- `0x1800124ac`
- `0x180012b2c`
- `0x1800194ac`
- `0x180019740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019582`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001950e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001950e`

## string_xrefs

- `0x180019572`: `ConvertSidToStringSidW failed`

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
    cxl::TextWriter::WriteFmt<30>(v8, "ConvertSidToStringSidW failed");
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
0x1800194ac  mov     [rsp-8+arg_10], rbx
0x1800194b1  mov     [rsp-8+arg_18], rdi
0x1800194b6  push    rbp
0x1800194b7  lea     rbp, [rsp-57h]
0x1800194bc  sub     rsp, 100h
0x1800194c3  mov     rax, cs:__security_cookie
0x1800194ca  xor     rax, rsp
0x1800194cd  mov     [rbp+57h+var_10], rax
0x1800194d1  mov     rdi, rdx
0x1800194d4  mov     rbx, rcx
0x1800194d7  mov     [rbp+57h+var_C8], rdx
0x1800194db  mov     [rsp+100h+var_E0], 0
0x1800194e3  mov     rcx, rdx
0x1800194e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800194eb  mov     [rsp+100h+var_E0], 1
0x1800194f3  mov     rcx, [rbx+10h]; struct _SID *
0x1800194f7  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x1800194fc  mov     [rsp+100h+StringSid], 0
0x180019505  lea     rdx, [rsp+100h+StringSid]; StringSid
0x18001950a  mov     rcx, [rbx+10h]; Sid
0x18001950e  call    cs:__imp_ConvertSidToStringSidW
0x180019515  nop     dword ptr [rax+rax+00h]
0x18001951a  test    eax, eax
0x18001951c  jz      short loc_18001955A
0x18001951e  mov     rdx, [rsp+100h+StringSid]
0x180019523  mov     rcx, rdi
0x180019526  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18001952b  mov     rcx, [rsp+100h+StringSid]; void *
0x180019530  call    ?Free@LocalHeap@cxl@@SAXPEAX@Z; cxl::LocalHeap::Free(void *)
0x180019535  mov     rax, rdi
0x180019538  mov     rcx, [rbp+57h+var_10]
0x18001953c  xor     rcx, rsp; StackCookie
0x18001953f  call    __security_check_cookie
0x180019544  lea     r11, [rsp+100h+var_s0]
0x18001954c  mov     rbx, [r11+20h]
0x180019550  mov     rdi, [r11+28h]
0x180019554  mov     rsp, r11
0x180019557  pop     rbp
0x180019558  retn
0x18001955a  lea     rcx, [rbp+57h+var_A0]
0x18001955e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019563  nop
0x180019564  lea     rdx, [rbp+57h+var_A0]
0x180019568  lea     rcx, [rbp+57h+var_C0]
0x18001956c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180019571  nop
0x180019572  lea     rdx, aConvertsidtost; "ConvertSidToStringSidW failed"
0x180019579  lea     rcx, [rbp+57h+var_C0]
0x18001957d  call    ??$WriteFmt@$0BO@@TextWriter@cxl@@QEAAAEAV01@AEAY0BO@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<30>(char const (&)[30],cxl::Format const &)
0x180019582  call    cs:__imp_GetLastError
0x180019589  nop     dword ptr [rax+rax+00h]
0x18001958e  mov     [rbp+57h+var_D0], eax
0x180019591  mov     [rbp+57h+var_CC], 0
0x180019598  lea     r8, [rbp+57h+var_A0]
0x18001959c  lea     rdx, [rbp+57h+var_D0]
0x1800195a0  lea     rcx, [rbp+57h+pExceptionObject]
0x1800195a4  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800195a9  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800195b0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800195b4  call    _CxxThrowException_0
```
