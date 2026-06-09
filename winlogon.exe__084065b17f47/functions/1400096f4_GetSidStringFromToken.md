# GetSidStringFromToken

- ea: `0x1400096f4`
- end: `0x140009821`
- name: `GetSidStringFromToken`
- size: `301`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008cec`

## callees

- `0x1400096f4`
- `0x14000aa04`
- `0x140049e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400097e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400097e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140009724`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000975e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140009724`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000975e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009808`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140009736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140009736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009781`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400097d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400097d3`

## string_xrefs

- `0x140009770`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14000979e`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x1400097f5`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  PSID *v4; // rdi
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  const char *v9; // r9
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) || GetLastError() == 122 )
  {
    v4 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v4 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      return LastError;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, cb, (PDWORD)&cb) )
    {
      if ( *StringSid )
      {
        LocalFree(*StringSid);
        *StringSid = 0;
      }
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v4, StringSid) )
      {
        LastError = 0;
        goto LABEL_6;
      }
      v6 = 36;
    }
    else
    {
      v6 = 35;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v5);
LABEL_6:
    CoTaskMemFree(v4);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1F,
           (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
           v9);
}

```

## disassembly

```asm
0x1400096f4  mov     rax, rsp
0x1400096f7  mov     [rax+8], rbx
0x1400096fb  mov     [rax+10h], rsi
0x1400096ff  push    rdi
0x140009700  sub     rsp, 30h
0x140009704  xor     r9d, r9d; TokenInformationLength
0x140009707  mov     dword ptr [rax+18h], 0
0x14000970e  mov     rbx, rdx
0x140009711  lea     rax, [rax+18h]
0x140009715  xor     r8d, r8d; TokenInformation
0x140009718  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x14000971d  mov     rsi, rcx
0x140009720  lea     edx, [r9+1]; TokenInformationClass
0x140009724  call    cs:__imp_GetTokenInformation
0x14000972a  test    eax, eax
0x14000972c  jz      loc_1400097E1
0x140009732  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x140009736  call    cs:__imp_CoTaskMemAlloc
0x14000973c  mov     rdi, rax
0x14000973f  test    rax, rax
0x140009742  jz      short loc_140009799
0x140009744  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x140009749  lea     rax, [rsp+38h+cb]
0x14000974e  mov     r8, rdi; TokenInformation
0x140009751  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140009756  mov     edx, 1; TokenInformationClass
0x14000975b  mov     rcx, rsi; TokenHandle
0x14000975e  call    cs:__imp_GetTokenInformation
0x140009764  test    eax, eax
0x140009766  jnz     short loc_1400097B9
0x140009768  lea     edx, [rax+23h]; void *
0x14000976b  mov     rcx, [rsp+38h]; this
0x140009770  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x140009777  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000977c  mov     ebx, eax
0x14000977e  mov     rcx, rdi; pv
0x140009781  call    cs:__imp_CoTaskMemFree
0x140009787  mov     eax, ebx
0x140009789  mov     rbx, [rsp+38h+arg_0]
0x14000978e  mov     rsi, [rsp+38h+arg_8]
0x140009793  add     rsp, 30h
0x140009797  pop     rdi
0x140009798  retn
0x140009799  mov     rcx, [rsp+38h]; this
0x14000979e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1400097a5  mov     ebx, 8007000Eh
0x1400097aa  mov     edx, 22h ; '"'; void *
0x1400097af  mov     r9d, ebx; char *
0x1400097b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400097b7  jmp     short loc_140009787
0x1400097b9  mov     rcx, [rbx]; hMem
0x1400097bc  test    rcx, rcx
0x1400097bf  jnz     short loc_140009808
0x1400097c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400097c5  mov     rdx, rbx; StringSid
0x1400097c8  mov     [rbx+8], rax
0x1400097cc  mov     [rbx+10h], rax
0x1400097d0  mov     rcx, [rdi]; Sid
0x1400097d3  call    cs:__imp_ConvertSidToStringSidW
0x1400097d9  test    eax, eax
0x1400097db  jz      short loc_140009817
0x1400097dd  xor     ebx, ebx
0x1400097df  jmp     short loc_14000977E
0x1400097e1  call    cs:__imp_GetLastError
0x1400097e7  cmp     eax, 7Ah ; 'z'
0x1400097ea  jz      loc_140009732
0x1400097f0  mov     rcx, [rsp+38h]; this
0x1400097f5  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1400097fc  mov     edx, 1Fh; void *
0x140009801  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009806  jmp     short loc_140009789
0x140009808  call    cs:__imp_LocalFree
0x14000980e  mov     qword ptr [rbx], 0
0x140009815  jmp     short loc_1400097C1
0x140009817  mov     edx, 24h ; '$'
0x14000981c  jmp     loc_14000976B
```
