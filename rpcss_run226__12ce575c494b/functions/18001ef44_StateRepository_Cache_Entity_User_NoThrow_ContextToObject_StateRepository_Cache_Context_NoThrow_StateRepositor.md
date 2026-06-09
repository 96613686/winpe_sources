# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x18001ef44`
- end: `0x18001f0d0`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002000c`

## callees

- `0x18001ec28`
- `0x18001ef44`
- `0x18001f7a8`
- `0x18001f828`
- `0x18002ba28`
- `0x18010a084`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f00a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f00a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001efe0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001efe0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f02b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f08a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f02b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f08a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f04c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f0a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f0ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f04c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f0a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f0ab`

## string_xrefs

- `0x18001ef75`: `UserSid`
- `0x18001f06e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001f0ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v7; // rcx
  LPCWSTR v8; // rcx
  BOOL v9; // ebx
  const char *v10; // r9
  PSID v11; // rbx
  DWORD LengthSid; // eax
  PSID v13; // rcx
  LPCWSTR v15; // rcx
  PSID pSid; // [rsp+20h] [rbp-20h] BYREF
  __int64 *p_StringSid; // [rsp+28h] [rbp-18h]
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v19; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF

  StringSid = 0;
  Sid = 0;
  p_StringSid = (__int64 *)&StringSid;
  v19 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"UserSid", (unsigned __int16 **)&Sid);
  if ( v19 )
  {
    v7 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v7 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
  }
  else
  {
    v8 = StringSid;
    if ( !StringSid )
    {
      a2[10] = 0;
LABEL_13:
      StringSid = 0;
      if ( v8 )
        SRCache_Free();
      *a2 = a4;
      return 0;
    }
    pSid = 0;
    p_StringSid = (__int64 *)&pSid;
    Sid = 0;
    v19 = 1;
    v9 = ConvertStringSidToSidW(StringSid, &Sid);
    if ( v19 )
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        p_StringSid,
        Sid);
    if ( v9 )
    {
      v11 = pSid;
      LengthSid = GetLengthSid(pSid);
      memcpy_0(a2 + 1, v11, LengthSid);
      v13 = pSid;
      a2[10] = a2 + 1;
      if ( v13 )
        LocalFree(v13);
      v8 = StringSid;
      goto LABEL_13;
    }
    Field = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x34F,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
              v10);
    if ( pSid )
      LocalFree(pSid);
  }
  v15 = StringSid;
  StringSid = 0;
  if ( v15 )
    SRCache_Free();
  return (unsigned int)Field;
}

```

## disassembly

```asm
0x18001ef44  mov     [rsp-18h+arg_0], rbx
0x18001ef49  mov     [rsp-18h+arg_8], rsi
0x18001ef4e  mov     [rsp-18h+StringSid], r8
0x18001ef53  push    rbp
0x18001ef54  push    rdi
0x18001ef55  push    r14
0x18001ef57  mov     rbp, rsp
0x18001ef5a  sub     rsp, 40h
0x18001ef5e  mov     rsi, rdx
0x18001ef61  mov     [rbp+StringSid], 0
0x18001ef69  lea     rax, [rbp+StringSid]
0x18001ef6d  mov     [rbp+Sid], 0
0x18001ef75  lea     rdx, aUsersid; "UserSid"
0x18001ef7c  mov     [rbp+var_18], rax
0x18001ef80  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18001ef84  mov     [rbp+var_8], 1
0x18001ef88  mov     r14, r9
0x18001ef8b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001ef90  cmp     [rbp+var_8], 0
0x18001ef94  mov     ebx, eax
0x18001ef96  jz      short loc_18001EFAF
0x18001ef98  mov     r8, [rbp+var_18]
0x18001ef9c  mov     rdx, [rbp+Sid]
0x18001efa0  mov     rcx, [r8]
0x18001efa3  mov     [r8], rdx
0x18001efa6  test    rcx, rcx
0x18001efa9  jnz     loc_18001F0AB
0x18001efaf  test    ebx, ebx
0x18001efb1  js      loc_18001F0B6
0x18001efb7  mov     rcx, [rbp+StringSid]; StringSid
0x18001efbb  test    rcx, rcx
0x18001efbe  jz      short loc_18001F037
0x18001efc0  lea     rax, [rbp+pSid]
0x18001efc4  mov     [rbp+pSid], 0
0x18001efcc  lea     rdx, [rbp+Sid]; Sid
0x18001efd0  mov     [rbp+var_18], rax
0x18001efd4  mov     [rbp+Sid], 0
0x18001efdc  mov     [rbp+var_8], 1
0x18001efe0  call    cs:__imp_ConvertStringSidToSidW
0x18001efe6  cmp     [rbp+var_8], 0
0x18001efea  mov     ebx, eax
0x18001efec  jz      short loc_18001EFFB
0x18001efee  mov     rdx, [rbp+Sid]
0x18001eff2  mov     rcx, [rbp+var_18]
0x18001eff6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001effb  test    ebx, ebx
0x18001effd  jz      short loc_18001F06A
0x18001efff  mov     rbx, [rbp+pSid]
0x18001f003  lea     rdi, [rsi+8]
0x18001f007  mov     rcx, rbx; pSid
0x18001f00a  call    cs:__imp_GetLengthSid
0x18001f010  mov     r8d, eax; Size
0x18001f013  mov     rdx, rbx; Src
0x18001f016  mov     rcx, rdi; void *
0x18001f019  call    memcpy_0
0x18001f01e  mov     rcx, [rbp+pSid]; hMem
0x18001f022  mov     [rsi+50h], rdi
0x18001f026  test    rcx, rcx
0x18001f029  jz      short loc_18001F031
0x18001f02b  call    cs:__imp_LocalFree
0x18001f031  mov     rcx, [rbp+StringSid]
0x18001f035  jmp     short loc_18001F03F
0x18001f037  mov     qword ptr [rsi+50h], 0
0x18001f03f  mov     [rbp+StringSid], 0
0x18001f047  test    rcx, rcx
0x18001f04a  jz      short loc_18001F052
0x18001f04c  call    cs:__imp_SRCache_Free
0x18001f052  mov     [rsi], r14
0x18001f055  xor     eax, eax
0x18001f057  mov     rbx, [rsp+40h+arg_0]
0x18001f05c  mov     rsi, [rsp+40h+arg_8]
0x18001f061  add     rsp, 40h
0x18001f065  pop     r14
0x18001f067  pop     rdi
0x18001f068  pop     rbp
0x18001f069  retn
0x18001f06a  mov     rcx, [rbp+18h]; this
0x18001f06e  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f075  mov     edx, 34Fh; void *
0x18001f07a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f07f  mov     rcx, [rbp+pSid]; hMem
0x18001f083  mov     ebx, eax
0x18001f085  test    rcx, rcx
0x18001f088  jz      short loc_18001F090
0x18001f08a  call    cs:__imp_LocalFree
0x18001f090  mov     rcx, [rbp+StringSid]
0x18001f094  mov     [rbp+StringSid], 0
0x18001f09c  test    rcx, rcx
0x18001f09f  jz      short loc_18001F0A7
0x18001f0a1  call    cs:__imp_SRCache_Free
0x18001f0a7  mov     eax, ebx
0x18001f0a9  jmp     short loc_18001F057
0x18001f0ab  call    cs:__imp_SRCache_Free
0x18001f0b1  jmp     loc_18001EFAF
0x18001f0b6  mov     rcx, [rbp+18h]; this
0x18001f0ba  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f0c1  mov     r9d, ebx; char *
0x18001f0c4  mov     edx, 347h; void *
0x18001f0c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0ce  jmp     short loc_18001F090
```
