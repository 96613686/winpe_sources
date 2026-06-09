# CreateAc(_ISOLATION_CONTAINER *)

- ea: `0x180049184`
- end: `0x18004922c`
- name: `?CreateAc@@YAJPEAU_ISOLATION_CONTAINER@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct _ISOLATION_CONTAINER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180049234`

## callees

- `0x18001b600`
- `0x18001da38`
- `0x18001dbcc`
- `0x180049184`
- `0x18004a568`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800491e1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800491e1`
- `USERENV!CreateAppContainerProfile` at `0x1800491b7`
- `USERENV!CreateAppContainerProfile` at `0x1800491b7`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180049202`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180049202`

## pseudocode

```c
__int64 __fastcall CreateAc(struct _ISOLATION_CONTAINER *a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  int v4; // eax
  int v5; // eax
  int v6; // ebx
  PSID v7; // rbx
  __int64 v8; // rcx
  PSID pSid; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+48h] [rbp+10h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  v4 = *((_DWORD *)a1 + 8);
  v1 = *(_QWORD *)a1;
  pSid = 0;
  v5 = CreateAppContainerProfile(v1, v1, v1, v2, v4, &pSid);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147024713 )
      goto LABEL_6;
    v7 = pSid;
    if ( pSid )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
      FreeSid(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
    }
    v8 = *(_QWORD *)a1;
    pSid = 0;
    v6 = AppContainerDeriveSidFromMoniker(v8, &pSid);
    if ( v6 < 0 )
LABEL_6:
      IsolationApi::TelemetryHelper::LogAppContainerCreationFailure(v6);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049184  mov     r11, rsp
0x180049187  mov     [r11+18h], rbx
0x18004918b  push    rdi
0x18004918c  sub     rsp, 30h
0x180049190  mov     r8, [rcx]
0x180049193  lea     rax, [r11+8]
0x180049197  mov     r9, [rcx+18h]
0x18004919b  mov     rdi, rcx
0x18004919e  mov     [r11-10h], rax
0x1800491a2  mov     rdx, r8
0x1800491a5  mov     eax, [rcx+20h]
0x1800491a8  mov     rcx, r8
0x1800491ab  mov     qword ptr [r11+8], 0
0x1800491b3  mov     [rsp+38h+var_18], eax
0x1800491b7  call    cs:__imp_CreateAppContainerProfile
0x1800491bd  mov     ebx, eax
0x1800491bf  test    eax, eax
0x1800491c1  jns     short loc_180049215
0x1800491c3  cmp     eax, 800700B7h
0x1800491c8  jnz     short loc_18004920E
0x1800491ca  mov     rbx, [rsp+38h+pSid]
0x1800491cf  test    rbx, rbx
0x1800491d2  jz      short loc_1800491F1
0x1800491d4  lea     rcx, [rsp+38h+arg_8]; this
0x1800491d9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800491de  mov     rcx, rbx; pSid
0x1800491e1  call    cs:__imp_FreeSid
0x1800491e7  lea     rcx, [rsp+38h+arg_8]; this
0x1800491ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800491f1  mov     rcx, [rdi]
0x1800491f4  lea     rdx, [rsp+38h+pSid]
0x1800491f9  mov     [rsp+38h+pSid], 0
0x180049202  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180049208  mov     ebx, eax
0x18004920a  test    eax, eax
0x18004920c  jns     short loc_180049215
0x18004920e  mov     ecx, ebx; int
0x180049210  call    ?LogAppContainerCreationFailure@TelemetryHelper@IsolationApi@@SAXJ@Z; IsolationApi::TelemetryHelper::LogAppContainerCreationFailure(long)
0x180049215  lea     rcx, [rsp+38h+pSid]
0x18004921a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004921f  mov     eax, ebx
0x180049221  mov     rbx, [rsp+38h+arg_10]
0x180049226  add     rsp, 30h
0x18004922a  pop     rdi
0x18004922b  retn
```
