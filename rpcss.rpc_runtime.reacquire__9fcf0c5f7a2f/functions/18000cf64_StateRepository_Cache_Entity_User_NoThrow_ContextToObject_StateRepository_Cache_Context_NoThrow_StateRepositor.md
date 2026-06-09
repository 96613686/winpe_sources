# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x18000cf64`
- end: `0x18000d11f`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000dae4`

## callees

- `0x18000ce5c`
- `0x18000ce7c`
- `0x18000cf64`
- `0x18000d52c`
- `0x1800210f8`
- `0x180112d84`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d034`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d034`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d004`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d004`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000d05b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000d0c7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000d05b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000d0c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d082`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d0e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d0f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d082`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d0e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d0f4`

## string_xrefs

- `0x18000cf95`: `UserSid`
- `0x18000d0ab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000d109`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

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
0x18000cf64  mov     [rsp-18h+arg_0], rbx
0x18000cf69  mov     [rsp-18h+arg_8], rsi
0x18000cf6e  mov     [rsp-18h+StringSid], r8
0x18000cf73  push    rbp
0x18000cf74  push    rdi
0x18000cf75  push    r14
0x18000cf77  mov     rbp, rsp
0x18000cf7a  sub     rsp, 40h
0x18000cf7e  mov     rsi, rdx
0x18000cf81  mov     [rbp+StringSid], 0
0x18000cf89  lea     rax, [rbp+StringSid]
0x18000cf8d  mov     [rbp+Sid], 0
0x18000cf95  lea     rdx, aUsersid; "UserSid"
0x18000cf9c  mov     [rbp+var_18], rax
0x18000cfa0  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18000cfa4  mov     [rbp+var_8], 1
0x18000cfa8  mov     r14, r9
0x18000cfab  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000cfb0  cmp     [rbp+var_8], 0
0x18000cfb4  mov     ebx, eax
0x18000cfb6  jz      short loc_18000CFCF
0x18000cfb8  mov     r8, [rbp+var_18]
0x18000cfbc  mov     rdx, [rbp+Sid]
0x18000cfc0  mov     rcx, [r8]
0x18000cfc3  mov     [r8], rdx
0x18000cfc6  test    rcx, rcx
0x18000cfc9  jnz     loc_18000D0F4
0x18000cfcf  test    ebx, ebx
0x18000cfd1  js      loc_18000D105
0x18000cfd7  mov     rcx, [rbp+StringSid]; StringSid
0x18000cfdb  test    rcx, rcx
0x18000cfde  jz      loc_18000D06D
0x18000cfe4  lea     rax, [rbp+pSid]
0x18000cfe8  mov     [rbp+pSid], 0
0x18000cff0  lea     rdx, [rbp+Sid]; Sid
0x18000cff4  mov     [rbp+var_18], rax
0x18000cff8  mov     [rbp+Sid], 0
0x18000d000  mov     [rbp+var_8], 1
0x18000d004  call    cs:__imp_ConvertStringSidToSidW
0x18000d00b  nop     dword ptr [rax+rax+00h]
0x18000d010  cmp     [rbp+var_8], 0
0x18000d014  mov     ebx, eax
0x18000d016  jz      short loc_18000D025
0x18000d018  mov     rdx, [rbp+Sid]
0x18000d01c  mov     rcx, [rbp+var_18]
0x18000d020  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000d025  test    ebx, ebx
0x18000d027  jz      short loc_18000D0A7
0x18000d029  mov     rbx, [rbp+pSid]
0x18000d02d  lea     rdi, [rsi+8]
0x18000d031  mov     rcx, rbx; pSid
0x18000d034  call    cs:__imp_GetLengthSid
0x18000d03b  nop     dword ptr [rax+rax+00h]
0x18000d040  mov     r8d, eax; Size
0x18000d043  mov     rdx, rbx; Src
0x18000d046  mov     rcx, rdi; void *
0x18000d049  call    memcpy_0
0x18000d04e  mov     rcx, [rbp+pSid]; hMem
0x18000d052  mov     [rsi+50h], rdi
0x18000d056  test    rcx, rcx
0x18000d059  jz      short loc_18000D067
0x18000d05b  call    cs:__imp_LocalFree
0x18000d062  nop     dword ptr [rax+rax+00h]
0x18000d067  mov     rcx, [rbp+StringSid]
0x18000d06b  jmp     short loc_18000D075
0x18000d06d  mov     qword ptr [rsi+50h], 0
0x18000d075  mov     [rbp+StringSid], 0
0x18000d07d  test    rcx, rcx
0x18000d080  jz      short loc_18000D08E
0x18000d082  call    cs:__imp_SRCache_Free
0x18000d089  nop     dword ptr [rax+rax+00h]
0x18000d08e  mov     [rsi], r14
0x18000d091  xor     eax, eax
0x18000d093  mov     rbx, [rsp+40h+arg_0]
0x18000d098  mov     rsi, [rsp+40h+arg_8]
0x18000d09d  add     rsp, 40h
0x18000d0a1  pop     r14
0x18000d0a3  pop     rdi
0x18000d0a4  pop     rbp
0x18000d0a5  retn
0x18000d0a7  mov     rcx, [rbp+18h]; this
0x18000d0ab  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d0b2  mov     edx, 34Fh; void *
0x18000d0b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d0bc  mov     rcx, [rbp+pSid]; hMem
0x18000d0c0  mov     ebx, eax
0x18000d0c2  test    rcx, rcx
0x18000d0c5  jz      short loc_18000D0D3
0x18000d0c7  call    cs:__imp_LocalFree
0x18000d0ce  nop     dword ptr [rax+rax+00h]
0x18000d0d3  mov     rcx, [rbp+StringSid]
0x18000d0d7  mov     [rbp+StringSid], 0
0x18000d0df  test    rcx, rcx
0x18000d0e2  jz      short loc_18000D0F0
0x18000d0e4  call    cs:__imp_SRCache_Free
0x18000d0eb  nop     dword ptr [rax+rax+00h]
0x18000d0f0  mov     eax, ebx
0x18000d0f2  jmp     short loc_18000D093
0x18000d0f4  call    cs:__imp_SRCache_Free
0x18000d0fb  nop     dword ptr [rax+rax+00h]
0x18000d100  jmp     loc_18000CFCF
0x18000d105  mov     rcx, [rbp+18h]; this
0x18000d109  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d110  mov     r9d, ebx; char *
0x18000d113  mov     edx, 347h; void *
0x18000d118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d11d  jmp     short loc_18000D0D3
```
