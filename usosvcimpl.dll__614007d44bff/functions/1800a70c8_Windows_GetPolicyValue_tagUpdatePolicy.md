# Windows::GetPolicyValue(tagUpdatePolicy)

- ea: `0x1800a70c8`
- end: `0x1800a723b`
- name: `?GetPolicyValue@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@W4tagUpdatePolicy@@@Z`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a73c0`
- `0x1800a76b0`

## callees

- `0x18002e168`
- `0x1800a70c8`
- `0x1800a7e60`
- `0x1800a8a5c`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a7135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a7135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a712d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a712d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a71b4`
- `OLEAUT32!__imp_VariantClear` at `0x1800a71a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800a71a4`

## string_xrefs

- `0x1800a7175`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::GetPolicyValue(__int64 a1, unsigned int a2)
{
  int (__fastcall *v4)(LPVOID, _QWORD, LPVOID *); // r12
  int v5; // eax
  char v7; // r9
  __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-60h]
  __m128i v10; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  LPVOID v12; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v13[16]; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  pv = 0;
  v12 = 0;
  wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(&v12);
  v4 = *(int (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)v12 + 40LL);
  pv = 0;
  if ( v4(v12, a2, &pv) < 0 )
  {
LABEL_4:
    *(_BYTE *)(a1 + 32) = 0;
    if ( v12 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BYTE *))(*(_QWORD *)v12 + 24LL))(v12, a2, v13);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x95A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      (const char *)(unsigned int)v5,
      v9);
    goto LABEL_4;
  }
  if ( a2 == 12 || (v7 = 0, a2 == 26) )
    v7 = 1;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)pv + v8) );
  v10.m128i_i64[0] = (__int64)pv;
  v10.m128i_i64[1] = v8;
  Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(a1, &v10, (__int64)v13, v7);
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_6:
  VariantClear(&pvarg);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x1800a70c8  mov     [rsp-38h+arg_10], rbx
0x1800a70cd  push    rbp
0x1800a70ce  push    rsi
0x1800a70cf  push    rdi
0x1800a70d0  push    r12
0x1800a70d2  push    r13
0x1800a70d4  push    r14
0x1800a70d6  push    r15
0x1800a70d8  mov     rbp, rsp
0x1800a70db  sub     rsp, 80h
0x1800a70e2  mov     rax, cs:__security_cookie
0x1800a70e9  xor     rax, rsp
0x1800a70ec  mov     [rbp+var_8], rax
0x1800a70f0  mov     esi, edx
0x1800a70f2  mov     r14, rcx
0x1800a70f5  mov     [rbp+var_38], rcx
0x1800a70f9  xor     r13d, r13d
0x1800a70fc  mov     [rbp+pv], r13
0x1800a7100  mov     [rbp+var_38], r13
0x1800a7104  lea     rcx, [rbp+var_38]
0x1800a7108  call    ??$CoCreateInstance@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdatePolicyReader@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUpdatePolicyReader,wil::err_exception_policy>(_GUID const &,ulong)
0x1800a710d  nop
0x1800a710e  mov     rbx, [rbp+var_38]
0x1800a7112  mov     rax, [rbx]
0x1800a7115  mov     r12, [rax+28h]
0x1800a7119  mov     r15, [rbp+pv]
0x1800a711d  test    r15, r15
0x1800a7120  jz      short loc_1800A713B
0x1800a7122  call    cs:__imp_GetLastError
0x1800a7128  mov     edi, eax
0x1800a712a  mov     rcx, r15; pv
0x1800a712d  call    cs:__imp_CoTaskMemFree
0x1800a7133  mov     ecx, edi; dwErrCode
0x1800a7135  call    cs:__imp_SetLastError
0x1800a713b  mov     [rbp+pv], r13
0x1800a713f  lea     r8, [rbp+pv]
0x1800a7143  mov     edx, esi
0x1800a7145  mov     rcx, rbx
0x1800a7148  mov     rax, r12
0x1800a714b  call    _guard_dispatch_icall
0x1800a7150  test    eax, eax
0x1800a7152  js      short loc_1800A7186
0x1800a7154  mov     rcx, [rbp+var_38]
0x1800a7158  mov     rax, [rcx]
0x1800a715b  lea     r8, [rbp+var_30]
0x1800a715f  mov     edx, esi
0x1800a7161  mov     rax, [rax+18h]
0x1800a7165  call    _guard_dispatch_icall
0x1800a716a  mov     rcx, [rbp+38h]; this
0x1800a716e  test    eax, eax
0x1800a7170  jns     short loc_1800A71E4
0x1800a7172  mov     r9d, eax; char *
0x1800a7175  lea     r8, aCW1SSrcOrchest_20; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800a717c  mov     edx, 95Ah; void *
0x1800a7181  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7186  mov     [r14+20h], r13b
0x1800a718a  mov     rcx, [rbp+var_38]
0x1800a718e  test    rcx, rcx
0x1800a7191  jz      short loc_1800A71A0
0x1800a7193  mov     rax, [rcx]
0x1800a7196  mov     rax, [rax+10h]
0x1800a719a  call    _guard_dispatch_icall
0x1800a719f  nop
0x1800a71a0  lea     rcx, [rbp+pvarg]; pvarg
0x1800a71a4  call    cs:__imp_VariantClear
0x1800a71aa  nop
0x1800a71ab  mov     rcx, [rbp+pv]; pv
0x1800a71af  test    rcx, rcx
0x1800a71b2  jz      short loc_1800A71BA
0x1800a71b4  call    cs:__imp_CoTaskMemFree
0x1800a71ba  mov     rax, r14
0x1800a71bd  mov     rcx, [rbp+var_8]
0x1800a71c1  xor     rcx, rsp; StackCookie
0x1800a71c4  call    __security_check_cookie
0x1800a71c9  mov     rbx, [rsp+80h+arg_10]
0x1800a71d1  add     rsp, 80h
0x1800a71d8  pop     r15
0x1800a71da  pop     r14
0x1800a71dc  pop     r13
0x1800a71de  pop     r12
0x1800a71e0  pop     rdi
0x1800a71e1  pop     rsi
0x1800a71e2  pop     rbp
0x1800a71e3  retn
0x1800a71e4  cmp     esi, 0Ch
0x1800a71e7  jz      short loc_1800A71F1
0x1800a71e9  cmp     esi, 1Ah
0x1800a71ec  mov     r9b, r13b
0x1800a71ef  jnz     short loc_1800A71F4
0x1800a71f1  mov     r9b, 1
0x1800a71f4  mov     rax, [rbp+pv]
0x1800a71f8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a71fc  inc     rcx
0x1800a71ff  cmp     [rax+rcx*2], r13w
0x1800a7204  jnz     short loc_1800A71FC
0x1800a7206  mov     [rbp+var_50], rax
0x1800a720a  mov     [rbp+var_48], rcx
0x1800a720e  lea     r8, [rbp+var_30]
0x1800a7212  lea     rdx, [rbp+var_50]
0x1800a7216  mov     rcx, r14
0x1800a7219  call    ??$FormatPolicyValue@V?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@Windows@@@Windows@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@AEBV?$WrappedPolicyValue@UtagUpdatePolicyValue_V1@@@0@_N@Z; Windows::FormatPolicyValue<Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1>>(wil::basic_zstring_view<wchar_t>,Windows::WrappedPolicyValue<tagUpdatePolicyValue_V1> const &,bool)
0x1800a721e  nop
0x1800a721f  mov     rcx, [rbp+var_38]
0x1800a7223  test    rcx, rcx
0x1800a7226  jz      short loc_1800A7235
0x1800a7228  mov     rax, [rcx]
0x1800a722b  mov     rax, [rax+10h]
0x1800a722f  call    _guard_dispatch_icall
0x1800a7234  nop
0x1800a7235  jmp     loc_1800A71A0
```
