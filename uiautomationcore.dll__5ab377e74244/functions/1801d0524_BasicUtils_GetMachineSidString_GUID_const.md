# BasicUtils::GetMachineSidString(_GUID const &)

- ea: `0x1801d0524`
- end: `0x1801d06f4`
- name: `?GetMachineSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801d02b0`
- `0x1801d03f0`

## callees

- `0x180032724`
- `0x1800dbd88`
- `0x18014c3ec`
- `0x18014d04c`
- `0x180164470`
- `0x1801a4e68`
- `0x1801d0524`
- `0x1801e8320`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1801d05f4`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1801d05f4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0619`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d062d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0644`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0658`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d066c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0680`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0619`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d062d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0644`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0658`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d066c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1801d0680`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1801d05a4`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1801d05a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801d05b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801d05b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801d06a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801d06a6`

## string_xrefs

- `0x1801d0583`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1801d05d8`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1801d0602`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1801d06b4`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall BasicUtils::GetMachineSidString(LPWSTR *StringSid, DWORD *a2)
{
  __int64 v4; // rax
  DWORD SidLengthRequired; // eax
  HLOCAL v6; // rax
  const char *v7; // r9
  PSID v8; // rbx
  const char *v9; // r9
  DWORD v10; // edi
  DWORD v11; // edi
  DWORD v12; // edi
  DWORD v13; // edi
  const char *v14; // r9
  PSID Sid[2]; // [rsp+28h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  Sid[1] = StringSid;
  v4 = *(_QWORD *)a2 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&GUID_NULL.Data1 )
    v4 = *((_QWORD *)a2 + 1) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      (const char *)0x80070057LL,
      0);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidLengthRequired = GetSidLengthRequired(6u);
  Sid[0] = 0;
  v6 = LocalAlloc(0x40u, SidLengthRequired);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    Sid,
    v6);
  v8 = Sid[0];
  if ( !Sid[0] )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v7);
  if ( !InitializeSid(Sid[0], &pIdentifierAuthority, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v9);
  *GetSidSubAuthority(v8, 0) = 83;
  *GetSidSubAuthority(v8, 1u) = 1;
  v10 = *a2;
  *GetSidSubAuthority(v8, 2u) = v10;
  v11 = a2[1];
  *GetSidSubAuthority(v8, 3u) = v11;
  v12 = a2[2];
  *GetSidSubAuthority(v8, 4u) = v12;
  v13 = a2[3];
  *GetSidSubAuthority(v8, 5u) = v13;
  *StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    StringSid,
    0);
  if ( !ConvertSidToStringSidW(v8, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
  return StringSid;
}

```

## disassembly

```asm
0x1801d0524  mov     [rsp-18h+arg_8], rbx
0x1801d0529  mov     [rsp-18h+arg_10], rsi
0x1801d052e  push    rbp
0x1801d052f  push    rdi
0x1801d0530  push    r14
0x1801d0532  mov     rbp, rsp
0x1801d0535  sub     rsp, 50h
0x1801d0539  mov     rax, cs:__security_cookie
0x1801d0540  xor     rax, rsp
0x1801d0543  mov     [rbp+var_10], rax
0x1801d0547  mov     r14, rdx
0x1801d054a  mov     rsi, rcx
0x1801d054d  mov     [rbp+var_20], rcx
0x1801d0551  mov     [rbp+var_30], 0
0x1801d0558  mov     rax, [rdx]
0x1801d055b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1801d0562  jnz     short loc_1801D056F
0x1801d0564  mov     rax, [rdx+8]
0x1801d0568  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1801d056f  test    rax, rax
0x1801d0572  setz    al
0x1801d0575  mov     rcx, [rbp+18h]; this
0x1801d0579  test    al, al
0x1801d057b  jz      short loc_1801D0595
0x1801d057d  mov     r9d, 80070057h; char *
0x1801d0583  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x1801d058a  mov     edx, 8Eh; void *
0x1801d058f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d0595  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x1801d059c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1801d05a2  mov     cl, 6; nSubAuthorityCount
0x1801d05a4  call    cs:__imp_GetSidLengthRequired
0x1801d05aa  mov     [rbp+Sid], 0
0x1801d05b2  mov     edx, eax; uBytes
0x1801d05b4  mov     ecx, 40h ; '@'; uFlags
0x1801d05b9  call    cs:__imp_LocalAlloc
0x1801d05bf  mov     rdx, rax
0x1801d05c2  lea     rcx, [rbp+Sid]
0x1801d05c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801d05cb  mov     rcx, [rbp+18h]; this
0x1801d05cf  mov     rbx, [rbp+Sid]
0x1801d05d3  test    rbx, rbx
0x1801d05d6  jnz     short loc_1801D05EA
0x1801d05d8  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x1801d05df  mov     edx, 96h; void *
0x1801d05e4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1801d05ea  mov     r8b, 6; nSubAuthorityCount
0x1801d05ed  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1801d05f1  mov     rcx, rbx; Sid
0x1801d05f4  call    cs:__imp_InitializeSid
0x1801d05fa  mov     rcx, [rbp+18h]; this
0x1801d05fe  test    eax, eax
0x1801d0600  jnz     short loc_1801D0614
0x1801d0602  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x1801d0609  mov     edx, 9Ah; void *
0x1801d060e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801d0614  xor     edx, edx; nSubAuthority
0x1801d0616  mov     rcx, rbx; pSid
0x1801d0619  call    cs:__imp_GetSidSubAuthority
0x1801d061f  mov     dword ptr [rax], 53h ; 'S'
0x1801d0625  mov     edx, 1; nSubAuthority
0x1801d062a  mov     rcx, rbx; pSid
0x1801d062d  call    cs:__imp_GetSidSubAuthority
0x1801d0633  mov     dword ptr [rax], 1
0x1801d0639  mov     edi, [r14]
0x1801d063c  mov     edx, 2; nSubAuthority
0x1801d0641  mov     rcx, rbx; pSid
0x1801d0644  call    cs:__imp_GetSidSubAuthority
0x1801d064a  mov     [rax], edi
0x1801d064c  mov     edi, [r14+4]
0x1801d0650  mov     edx, 3; nSubAuthority
0x1801d0655  mov     rcx, rbx; pSid
0x1801d0658  call    cs:__imp_GetSidSubAuthority
0x1801d065e  mov     [rax], edi
0x1801d0660  mov     edi, [r14+8]
0x1801d0664  mov     edx, 4; nSubAuthority
0x1801d0669  mov     rcx, rbx; pSid
0x1801d066c  call    cs:__imp_GetSidSubAuthority
0x1801d0672  mov     [rax], edi
0x1801d0674  mov     edi, [r14+0Ch]
0x1801d0678  mov     edx, 5; nSubAuthority
0x1801d067d  mov     rcx, rbx; pSid
0x1801d0680  call    cs:__imp_GetSidSubAuthority
0x1801d0686  mov     [rax], edi
0x1801d0688  mov     qword ptr [rsi], 0
0x1801d068f  mov     [rbp+var_30], 1
0x1801d0696  xor     edx, edx
0x1801d0698  mov     rcx, rsi
0x1801d069b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801d06a0  mov     rdx, rsi; StringSid
0x1801d06a3  mov     rcx, rbx; Sid
0x1801d06a6  call    cs:__imp_ConvertSidToStringSidW
0x1801d06ac  mov     rcx, [rbp+18h]; this
0x1801d06b0  test    eax, eax
0x1801d06b2  jnz     short loc_1801D06C6
0x1801d06b4  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x1801d06bb  mov     edx, 0A6h; void *
0x1801d06c0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801d06c6  lea     rcx, [rbp+Sid]
0x1801d06ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801d06cf  mov     rax, rsi
0x1801d06d2  mov     rcx, [rbp+var_10]
0x1801d06d6  xor     rcx, rsp; StackCookie
0x1801d06d9  call    __security_check_cookie
0x1801d06de  lea     r11, [rsp+50h+var_s0]
0x1801d06e3  mov     rbx, [r11+28h]
0x1801d06e7  mov     rsi, [r11+30h]
0x1801d06eb  mov     rsp, r11
0x1801d06ee  pop     r14
0x1801d06f0  pop     rdi
0x1801d06f1  pop     rbp
0x1801d06f2  retn
```
