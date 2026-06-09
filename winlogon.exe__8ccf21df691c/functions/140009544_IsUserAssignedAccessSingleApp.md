# IsUserAssignedAccessSingleApp

- ea: `0x140009544`
- end: `0x1400096eb`
- name: `IsUserAssignedAccessSingleApp`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008d74`

## callees

- `0x140009544`
- `0x140009900`
- `0x14000aa04`
- `0x140049e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000969b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000969b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000958b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400095c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000958b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400095c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009693`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400096c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400096d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009693`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400096c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400096d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000959c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000959c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400095ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400095ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009688`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14000967b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14000967b`

## string_xrefs

- `0x1400095db`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14000963b`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x1400096ae`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
_BOOL8 __fastcall IsUserAssignedAccessSingleApp(HANDLE TokenHandle)
{
  PSID *v2; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // edi
  __int64 v6; // rdx
  int AssignedAccessTypeForUser_0; // eax
  DWORD v8; // ecx
  BOOL v9; // ebx
  const char *v11; // r9
  int ReturnLength; // [rsp+20h] [rbp-30h]
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h]
  __int64 v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+18h] BYREF

  StringSid = 0;
  v14 = 0;
  v15 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v2 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
    if ( !v2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      goto LABEL_13;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
    {
      v14 = -1;
      v15 = -1;
      if ( ConvertSidToStringSidW(*v2, &StringSid) )
      {
        CoTaskMemFree(v2);
        goto LABEL_7;
      }
      v4 = 36;
    }
    else
    {
      v4 = 35;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v3);
    CoTaskMemFree(v2);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1F,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v11);
  }
  if ( LastError >= 0 )
  {
LABEL_7:
    LOBYTE(v6) = 1;
    TokenInformationLength = 0;
    AssignedAccessTypeForUser_0 = GetAssignedAccessTypeForUser_0(StringSid, v6, &TokenInformationLength);
    v8 = 0;
    if ( AssignedAccessTypeForUser_0 >= 0 )
      v8 = TokenInformationLength;
    v9 = v8 == 1;
    if ( StringSid )
      LocalFree(StringSid);
    return v9;
  }
LABEL_13:
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x140009544  mov     [rsp-8+arg_0], rbx
0x140009549  mov     [rsp-8+arg_10], rdi
0x14000954e  push    rbp
0x14000954f  mov     rbp, rsp
0x140009552  sub     rsp, 50h
0x140009556  xor     r9d, r9d; TokenInformationLength
0x140009559  mov     [rbp+StringSid], 0
0x140009561  lea     rax, [rbp+TokenInformationLength]
0x140009565  mov     [rbp+var_18], 0
0x14000956d  xor     r8d, r8d; TokenInformation
0x140009570  mov     [rbp+var_10], 0
0x140009578  mov     rdi, rcx
0x14000957b  mov     [rbp+TokenInformationLength], 0
0x140009582  lea     edx, [r9+1]; TokenInformationClass
0x140009586  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x14000958b  call    cs:__imp_GetTokenInformation
0x140009591  test    eax, eax
0x140009593  jz      loc_14000969B
0x140009599  mov     ecx, [rbp+TokenInformationLength]; cb
0x14000959c  call    cs:__imp_CoTaskMemAlloc
0x1400095a2  mov     rbx, rax
0x1400095a5  test    rax, rax
0x1400095a8  jz      loc_140009637
0x1400095ae  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400095b2  lea     rax, [rbp+TokenInformationLength]
0x1400095b6  mov     r8, rbx; TokenInformation
0x1400095b9  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1400095be  mov     edx, 1; TokenInformationClass
0x1400095c3  mov     rcx, rdi; TokenHandle
0x1400095c6  call    cs:__imp_GetTokenInformation
0x1400095cc  test    eax, eax
0x1400095ce  jnz     loc_14000965F
0x1400095d4  lea     edx, [rax+23h]; void *
0x1400095d7  mov     rcx, [rbp+8]; this
0x1400095db  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1400095e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400095e7  mov     rcx, rbx; pv
0x1400095ea  mov     edi, eax
0x1400095ec  call    cs:__imp_CoTaskMemFree
0x1400095f2  test    edi, edi
0x1400095f4  js      short loc_140009652
0x1400095f6  mov     rcx, [rbp+StringSid]
0x1400095fa  lea     r8, [rbp+TokenInformationLength]
0x1400095fe  mov     dl, 1
0x140009600  mov     [rbp+TokenInformationLength], 0
0x140009607  call    GetAssignedAccessTypeForUser_0
0x14000960c  xor     ecx, ecx
0x14000960e  test    eax, eax
0x140009610  cmovns  ecx, [rbp+TokenInformationLength]
0x140009614  xor     ebx, ebx
0x140009616  cmp     ecx, 1
0x140009619  mov     rcx, [rbp+StringSid]; hMem
0x14000961d  setz    bl
0x140009620  test    rcx, rcx
0x140009623  jnz     short loc_140009693
0x140009625  mov     eax, ebx
0x140009627  mov     rbx, [rsp+50h+arg_0]
0x14000962c  mov     rdi, [rsp+50h+arg_10]
0x140009631  add     rsp, 50h
0x140009635  pop     rbp
0x140009636  retn
0x140009637  mov     rcx, [rbp+8]; this
0x14000963b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x140009642  mov     r9d, 8007000Eh; char *
0x140009648  mov     edx, 22h ; '"'; void *
0x14000964d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009652  mov     rcx, [rbp+StringSid]; hMem
0x140009656  test    rcx, rcx
0x140009659  jnz     short loc_1400096D6
0x14000965b  xor     eax, eax
0x14000965d  jmp     short loc_140009627
0x14000965f  mov     rcx, [rbp+StringSid]; hMem
0x140009663  test    rcx, rcx
0x140009666  jnz     short loc_1400096C6
0x140009668  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000966c  lea     rdx, [rbp+StringSid]; StringSid
0x140009670  mov     [rbp+var_18], rax
0x140009674  mov     [rbp+var_10], rax
0x140009678  mov     rcx, [rbx]; Sid
0x14000967b  call    cs:__imp_ConvertSidToStringSidW
0x140009681  test    eax, eax
0x140009683  jz      short loc_1400096E1
0x140009685  mov     rcx, rbx; pv
0x140009688  call    cs:__imp_CoTaskMemFree
0x14000968e  jmp     loc_1400095F6
0x140009693  call    cs:__imp_LocalFree
0x140009699  jmp     short loc_140009625
0x14000969b  call    cs:__imp_GetLastError
0x1400096a1  cmp     eax, 7Ah ; 'z'
0x1400096a4  jz      loc_140009599
0x1400096aa  mov     rcx, [rbp+8]; this
0x1400096ae  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1400096b5  mov     edx, 1Fh; void *
0x1400096ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400096bf  mov     edi, eax
0x1400096c1  jmp     loc_1400095F2
0x1400096c6  call    cs:__imp_LocalFree
0x1400096cc  mov     [rbp+StringSid], 0
0x1400096d4  jmp     short loc_140009668
0x1400096d6  call    cs:__imp_LocalFree
0x1400096dc  jmp     loc_14000965B
0x1400096e1  mov     edx, 24h ; '$'
0x1400096e6  jmp     loc_1400095D7
```
