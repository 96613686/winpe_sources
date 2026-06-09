# CreateIsolatedProcessToken(_ISOLATION_CONTAINER *,void * *)

- ea: `0x18001b2b4`
- end: `0x18001b3b6`
- name: `?CreateIsolatedProcessToken@@YAJPEAU_ISOLATION_CONTAINER@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct _ISOLATION_CONTAINER *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ba10`

## callees

- `0x18001b2b4`
- `0x18001b3bc`
- `0x18001b564`
- `0x18001b5dc`
- `0x18001b600`
- `0x18001da38`
- `0x18001dbcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b36e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001b30e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001b30e`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18001b32c`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18001b32c`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001b364`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001b364`

## string_xrefs

- `0x18001b383`: `Call: CreateAppContainerToken()`
- `0x18001b2ed`: `Call: RestrictTokenIfElevated()`
- `0x18001b338`: `Call: DeriveAppContainerSidFromAppContainerName()`

## pseudocode

```c
__int64 __fastcall CreateIsolatedProcessToken(struct _ISOLATION_CONTAINER *a1, void **a2)
{
  signed int v4; // ebx
  const unsigned __int16 *v5; // rdx
  PSID v6; // rbx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // ecx
  signed int LastError; // eax
  _BYTE v12[8]; // [rsp+20h] [rbp-20h] BYREF
  __int128 v13; // [rsp+28h] [rbp-18h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h]
  PSID pSid; // [rsp+70h] [rbp+30h] BYREF
  void *v16; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  pSid = 0;
  v13 = 0;
  v16 = 0;
  v4 = RestrictTokenIfElevated(a1, &v16);
  if ( v4 < 0 )
  {
    v5 = L"Call: RestrictTokenIfElevated()";
LABEL_11:
    v9 = v4;
    goto LABEL_12;
  }
  v6 = pSid;
  if ( pSid )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v12);
    FreeSid(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
  }
  v7 = *(_QWORD *)a1;
  pSid = 0;
  v8 = DeriveAppContainerSidFromAppContainerName(v7, &pSid);
  v4 = v8;
  if ( v8 >= 0 )
  {
    *(_QWORD *)&v13 = pSid;
    *((_QWORD *)&v13 + 1) = *((_QWORD *)a1 + 3);
    LODWORD(v14) = *((_DWORD *)a1 + 8);
    if ( (unsigned int)CreateAppContainerToken(v16, &v13, a2) )
    {
      v4 = 0;
      goto LABEL_14;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"Call: CreateAppContainerToken()";
    goto LABEL_11;
  }
  v5 = L"Call: DeriveAppContainerSidFromAppContainerName()";
  v9 = v8;
LABEL_12:
  IsolationApi::TelemetryHelper::LogIsolatedProcessTokenCreationFailure(v9, v5);
LABEL_14:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b2b4  mov     [rsp-18h+arg_0], rbx
0x18001b2b9  push    rbp
0x18001b2ba  push    rsi
0x18001b2bb  push    rdi
0x18001b2bc  mov     rbp, rsp
0x18001b2bf  sub     rsp, 40h
0x18001b2c3  xor     eax, eax
0x18001b2c5  mov     rsi, rdx
0x18001b2c8  xorps   xmm0, xmm0
0x18001b2cb  mov     [rbp+var_8], rax
0x18001b2cf  lea     rdx, [rbp+arg_18]; void **
0x18001b2d3  mov     [rbp+pSid], rax
0x18001b2d7  movups  [rbp+var_18], xmm0
0x18001b2db  mov     [rbp+arg_18], rax
0x18001b2df  mov     rdi, rcx
0x18001b2e2  call    ?RestrictTokenIfElevated@@YAJPEAXPEAPEAX@Z; RestrictTokenIfElevated(void *,void * *)
0x18001b2e7  mov     ebx, eax
0x18001b2e9  test    eax, eax
0x18001b2eb  jns     short loc_18001B2F9
0x18001b2ed  lea     rdx, aCallRestrictto; "Call: RestrictTokenIfElevated()"
0x18001b2f4  jmp     loc_18001B38A
0x18001b2f9  mov     rbx, [rbp+pSid]
0x18001b2fd  test    rbx, rbx
0x18001b300  jz      short loc_18001B31D
0x18001b302  lea     rcx, [rbp+var_20]; this
0x18001b306  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b30b  mov     rcx, rbx; pSid
0x18001b30e  call    cs:__imp_FreeSid
0x18001b314  lea     rcx, [rbp+var_20]; this
0x18001b318  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b31d  mov     rcx, [rdi]
0x18001b320  lea     rdx, [rbp+pSid]
0x18001b324  mov     [rbp+pSid], 0
0x18001b32c  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18001b332  mov     ebx, eax
0x18001b334  test    eax, eax
0x18001b336  jns     short loc_18001B343
0x18001b338  lea     rdx, aCallDeriveappc; "Call: DeriveAppContainerSidFromAppConta"...
0x18001b33f  mov     ecx, eax
0x18001b341  jmp     short loc_18001B38C
0x18001b343  mov     rax, [rbp+pSid]
0x18001b347  lea     rdx, [rbp+var_18]
0x18001b34b  mov     rcx, [rbp+arg_18]
0x18001b34f  mov     r8, rsi
0x18001b352  mov     qword ptr [rbp+var_18], rax
0x18001b356  mov     rax, [rdi+18h]
0x18001b35a  mov     qword ptr [rbp+var_18+8], rax
0x18001b35e  mov     eax, [rdi+20h]
0x18001b361  mov     dword ptr [rbp+var_8], eax
0x18001b364  call    cs:__imp_CreateAppContainerToken
0x18001b36a  test    eax, eax
0x18001b36c  jnz     short loc_18001B393
0x18001b36e  call    cs:__imp_GetLastError
0x18001b374  mov     ebx, eax
0x18001b376  test    eax, eax
0x18001b378  jle     short loc_18001B383
0x18001b37a  movzx   ebx, ax
0x18001b37d  or      ebx, 80070000h
0x18001b383  lea     rdx, aCallCreateappc; "Call: CreateAppContainerToken()"
0x18001b38a  mov     ecx, ebx; int
0x18001b38c  call    ?LogIsolatedProcessTokenCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogIsolatedProcessTokenCreationFailure(long,ushort const *)
0x18001b391  jmp     short loc_18001B395
0x18001b393  xor     ebx, ebx
0x18001b395  lea     rcx, [rbp+arg_18]
0x18001b399  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b39e  lea     rcx, [rbp+pSid]
0x18001b3a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b3a7  mov     eax, ebx
0x18001b3a9  mov     rbx, [rsp+40h+arg_0]
0x18001b3ae  add     rsp, 40h
0x18001b3b2  pop     rdi
0x18001b3b3  pop     rsi
0x18001b3b4  pop     rbp
0x18001b3b5  retn
```
