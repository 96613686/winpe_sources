# Windows::GetPolicyValue(tagEnterprisePolicy)

- ea: `0x1800a7244`
- end: `0x1800a73ac`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@W4tagEnterprisePolicy@@@Z`
- size: `360`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a73c0`
- `0x1800a76b0`
- `0x1800a79e0`

## callees

- `0x18002e168`
- `0x1800a7244`
- `0x1800a7e60`
- `0x1800a8cd4`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a72b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a72b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a72ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a72ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7335`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7325`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7325`

## string_xrefs

- `0x1800a72f6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::GetPolicyValue(__int64 a1, unsigned int a2)
{
  int (__fastcall *v4)(LPVOID, _QWORD, LPVOID *); // r12
  int v5; // eax
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-49h]
  __m128i v9; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  LPVOID v11; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  pv = 0;
  v11 = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v11);
  v4 = *(int (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)v11 + 48LL);
  pv = 0;
  if ( v4(v11, a2, &pv) < 0 )
  {
LABEL_4:
    *(_BYTE *)(a1 + 32) = 0;
    if ( v11 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, a2, v12);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x967,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      (const char *)(unsigned int)v5,
      v8);
    goto LABEL_4;
  }
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)pv + v7) );
  v9.m128i_i64[0] = (__int64)pv;
  v9.m128i_i64[1] = v7;
  Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1>>(a1, &v9, (__int64)v12);
  if ( v11 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_6:
  VariantClear(&pvarg);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x1800a7244  mov     [rsp-8+arg_10], rbx
0x1800a7249  push    rbp
0x1800a724a  push    rsi
0x1800a724b  push    rdi
0x1800a724c  push    r12
0x1800a724e  push    r13
0x1800a7250  push    r14
0x1800a7252  push    r15
0x1800a7254  lea     rbp, [rsp-27h]
0x1800a7259  sub     rsp, 90h
0x1800a7260  mov     rax, cs:__security_cookie
0x1800a7267  xor     rax, rsp
0x1800a726a  mov     [rbp+57h+var_40], rax
0x1800a726e  mov     r15d, edx
0x1800a7271  mov     rsi, rcx
0x1800a7274  mov     [rbp+57h+var_78], rcx
0x1800a7278  xor     r13d, r13d
0x1800a727b  mov     [rbp+57h+pv], r13
0x1800a727f  mov     [rbp+57h+var_78], r13
0x1800a7283  lea     rcx, [rbp+57h+var_78]
0x1800a7287  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x1800a728c  nop
0x1800a728d  mov     rbx, [rbp+57h+var_78]
0x1800a7291  mov     rax, [rbx]
0x1800a7294  mov     r12, [rax+30h]
0x1800a7298  mov     r14, [rbp+57h+pv]
0x1800a729c  test    r14, r14
0x1800a729f  jz      short loc_1800A72BA
0x1800a72a1  call    cs:__imp_GetLastError
0x1800a72a7  mov     edi, eax
0x1800a72a9  mov     rcx, r14; pv
0x1800a72ac  call    cs:__imp_CoTaskMemFree
0x1800a72b2  mov     ecx, edi; dwErrCode
0x1800a72b4  call    cs:__imp_SetLastError
0x1800a72ba  mov     [rbp+57h+pv], r13
0x1800a72be  lea     r8, [rbp+57h+pv]
0x1800a72c2  mov     edx, r15d
0x1800a72c5  mov     rcx, rbx
0x1800a72c8  mov     rax, r12
0x1800a72cb  call    _guard_dispatch_icall
0x1800a72d0  test    eax, eax
0x1800a72d2  js      short loc_1800A7307
0x1800a72d4  mov     rcx, [rbp+57h+var_78]
0x1800a72d8  mov     rax, [rcx]
0x1800a72db  lea     r8, [rbp+57h+var_70]
0x1800a72df  mov     edx, r15d
0x1800a72e2  mov     rax, [rax+20h]
0x1800a72e6  call    _guard_dispatch_icall
0x1800a72eb  mov     rcx, [rbp+5Fh]; this
0x1800a72ef  test    eax, eax
0x1800a72f1  jns     short loc_1800A7365
0x1800a72f3  mov     r9d, eax; char *
0x1800a72f6  lea     r8, aCW1SSrcOrchest_20; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800a72fd  mov     edx, 967h; void *
0x1800a7302  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7307  mov     [rsi+20h], r13b
0x1800a730b  mov     rcx, [rbp+57h+var_78]
0x1800a730f  test    rcx, rcx
0x1800a7312  jz      short loc_1800A7321
0x1800a7314  mov     rax, [rcx]
0x1800a7317  mov     rax, [rax+10h]
0x1800a731b  call    _guard_dispatch_icall
0x1800a7320  nop
0x1800a7321  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800a7325  call    cs:__imp_VariantClear
0x1800a732b  nop
0x1800a732c  mov     rcx, [rbp+57h+pv]; pv
0x1800a7330  test    rcx, rcx
0x1800a7333  jz      short loc_1800A733B
0x1800a7335  call    cs:__imp_CoTaskMemFree
0x1800a733b  mov     rax, rsi
0x1800a733e  mov     rcx, [rbp+57h+var_40]
0x1800a7342  xor     rcx, rsp; StackCookie
0x1800a7345  call    __security_check_cookie
0x1800a734a  mov     rbx, [rsp+0C0h+arg_10]
0x1800a7352  add     rsp, 90h
0x1800a7359  pop     r15
0x1800a735b  pop     r14
0x1800a735d  pop     r13
0x1800a735f  pop     r12
0x1800a7361  pop     rdi
0x1800a7362  pop     rsi
0x1800a7363  pop     rbp
0x1800a7364  retn
0x1800a7365  mov     rax, [rbp+57h+pv]
0x1800a7369  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a736d  inc     rcx
0x1800a7370  cmp     [rax+rcx*2], r13w
0x1800a7375  jnz     short loc_1800A736D
0x1800a7377  mov     [rbp+57h+var_90], rax
0x1800a737b  mov     [rbp+57h+var_88], rcx
0x1800a737f  lea     r8, [rbp+57h+var_70]
0x1800a7383  lea     rdx, [rbp+57h+var_90]
0x1800a7387  mov     rcx, rsi
0x1800a738a  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagEnterprisePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@AEBV?$WrappedPolicyValue@UtagEnterprisePolicyValue_V1@@@0@_N@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1>>(wil::basic_zstring_view<wchar_t>,Windows::WrappedPolicyValue<tagEnterprisePolicyValue_V1> const &,bool)
0x1800a738f  nop
0x1800a7390  mov     rcx, [rbp+57h+var_78]
0x1800a7394  test    rcx, rcx
0x1800a7397  jz      short loc_1800A73A6
0x1800a7399  mov     rax, [rcx]
0x1800a739c  mov     rax, [rax+10h]
0x1800a73a0  call    _guard_dispatch_icall
0x1800a73a5  nop
0x1800a73a6  jmp     loc_1800A7321
```
