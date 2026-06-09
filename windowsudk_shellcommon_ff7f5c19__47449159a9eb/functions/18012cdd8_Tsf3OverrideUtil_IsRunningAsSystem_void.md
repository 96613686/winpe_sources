# Tsf3OverrideUtil::IsRunningAsSystem(void)

- ea: `0x18012cdd8`
- end: `0x18012ce82`
- name: `?IsRunningAsSystem@Tsf3OverrideUtil@@YA_NXZ`
- size: `170`
- prototype: `bool __fastcall(Tsf3OverrideUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c31d8`

## callees

- `0x1800a8430`
- `0x18012cdd8`
- `0x18012ce88`
- `0x180137f7c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012ce20`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012ce20`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18012ce41`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18012ce41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012cdec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18012cdec`

## pseudocode

```c
bool __fastcall Tsf3OverrideUtil::IsRunningAsSystem(Tsf3OverrideUtil *this)
{
  bool v1; // di
  HLOCAL v2; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rbx
  const char *v7; // r9
  __int64 v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF
  HLOCAL v13; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v2 = LocalAlloc(0, 0x44u);
  v6 = v2;
  v13 = v2;
  if ( v2 )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v2, &cbSid) )
    {
      IsMember = 0;
      if ( CheckTokenMembership(0, v6, &IsMember) )
      {
        v1 = IsMember != 0;
        goto LABEL_9;
      }
      v8 = 127;
    }
    else
    {
      v8 = 124;
    }
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      v7);
  }
  else
  {
    wil::details::in1diag3::_Log_NullAlloc(retaddr, v3, v4, v5);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v13);
  return v1;
}

```

## disassembly

```asm
0x18012cdd8  mov     [rsp+arg_18], rbx
0x18012cddd  push    rdi
0x18012cdde  sub     rsp, 20h
0x18012cde2  mov     edx, 44h ; 'D'; uBytes
0x18012cde7  xor     ecx, ecx; uFlags
0x18012cde9  xor     dil, dil
0x18012cdec  call    cs:__imp_LocalAlloc
0x18012cdf2  mov     rcx, [rsp+28h]; this
0x18012cdf7  mov     rbx, rax
0x18012cdfa  mov     [rsp+28h+arg_10], rax
0x18012cdff  test    rax, rax
0x18012ce02  jnz     short loc_18012CE0B
0x18012ce04  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x18012ce09  jmp     short loc_18012CE6A
0x18012ce0b  xor     edx, edx; DomainSid
0x18012ce0d  mov     [rsp+28h+cbSid], 44h ; 'D'
0x18012ce15  lea     r9, [rsp+28h+cbSid]; cbSid
0x18012ce1a  mov     r8, rbx; pSid
0x18012ce1d  lea     ecx, [rdx+16h]; WellKnownSidType
0x18012ce20  call    cs:__imp_CreateWellKnownSid
0x18012ce26  test    eax, eax
0x18012ce28  jnz     short loc_18012CE2F
0x18012ce2a  lea     edx, [rax+7Ch]
0x18012ce2d  jmp     short loc_18012CE4E
0x18012ce2f  lea     r8, [rsp+28h+IsMember]; IsMember
0x18012ce34  mov     [rsp+28h+IsMember], 0
0x18012ce3c  mov     rdx, rbx; SidToCheck
0x18012ce3f  xor     ecx, ecx; TokenHandle
0x18012ce41  call    cs:__imp_CheckTokenMembership
0x18012ce47  test    eax, eax
0x18012ce49  jnz     short loc_18012CE61
0x18012ce4b  lea     edx, [rax+7Fh]; void *
0x18012ce4e  mov     rcx, [rsp+28h]; this
0x18012ce53  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x18012ce5a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18012ce5f  jmp     short loc_18012CE6A
0x18012ce61  cmp     [rsp+28h+IsMember], 0
0x18012ce66  setnz   dil
0x18012ce6a  lea     rcx, [rsp+28h+arg_10]
0x18012ce6f  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18012ce74  mov     rbx, [rsp+28h+arg_18]
0x18012ce79  mov     al, dil
0x18012ce7c  add     rsp, 20h
0x18012ce80  pop     rdi
0x18012ce81  retn
```
