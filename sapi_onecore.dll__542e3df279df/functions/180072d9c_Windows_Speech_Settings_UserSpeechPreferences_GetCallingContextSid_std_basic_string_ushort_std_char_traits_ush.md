# Windows::Speech::Settings::UserSpeechPreferences::GetCallingContextSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong)

- ea: `0x180072d9c`
- end: `0x180072f43`
- name: `?GetCallingContextSid@UserSpeechPreferences@Settings@Speech@Windows@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180072b3c`

## callees

- `0x1800213f0`
- `0x180026ae4`
- `0x18002d404`
- `0x18005cd84`
- `0x180072d9c`
- `0x18007a31c`
- `0x1800cec88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072dc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072dc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072dd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072de2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072de2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180072eb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180072eb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072e32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072e65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072e32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072e65`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Speech::Settings::UserSpeechPreferences::GetCallingContextSid(__int64 a1, DWORD a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  PSID *v8; // rbx
  const char *v9; // r9
  unsigned int v10; // ebx
  const char *v11; // r9
  const char *v12; // r9
  unsigned int LastError; // ebx
  __int64 v14; // r8
  _QWORD v15[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+20h] BYREF

  TokenInformationLength = a2;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    try
    {
      v8 = (PSID *)operator new[](TokenInformationLength);
      v15[0] = v8;
      if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(*v8, &StringSid) )
        {
          v14 = -1;
          do
            ++v14;
          while ( StringSid[v14] );
          std::wstring::_Assign<unsigned short>(a1, StringSid, v14);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(v15);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x257,
                        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\settings\\userspeechpreferences.cpp",
                        v12);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(v15);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          result = LastError;
        }
      }
      else
      {
        v10 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x251,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\settings\\userspeechpreferences.cpp",
                v9);
        CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(v15);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        result = v10;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x25C,
                             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\settings\\userspeechpreferences.cpp",
                             v11);
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x24A,
           (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\settings\\userspeechpreferences.cpp",
           v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180072d9c  mov     [rsp+TokenInformationLength], edx
0x180072da0  push    rbx
0x180072da1  push    rsi
0x180072da2  push    rdi
0x180072da3  sub     rsp, 40h
0x180072da7  mov     rdi, rcx
0x180072daa  xor     esi, esi
0x180072dac  mov     [rsp+58h+TokenHandle], rsi
0x180072db1  call    cs:__imp_GetCurrentThread
0x180072db7  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180072dbc  lea     ebx, [rsi+8]
0x180072dbf  lea     r8d, [rsi+1]; OpenAsSelf
0x180072dc3  mov     edx, ebx; DesiredAccess
0x180072dc5  mov     rcx, rax; ThreadHandle
0x180072dc8  call    cs:__imp_OpenThreadToken
0x180072dce  test    eax, eax
0x180072dd0  jnz     short loc_180072E15
0x180072dd2  call    cs:__imp_GetCurrentProcess
0x180072dd8  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180072ddd  mov     edx, ebx; DesiredAccess
0x180072ddf  mov     rcx, rax; ProcessHandle
0x180072de2  call    cs:__imp_OpenProcessToken
0x180072de8  test    eax, eax
0x180072dea  jnz     short loc_180072E15
0x180072dec  mov     rcx, [rsp+58h]; this
0x180072df1  lea     r8, aOnecoreuapEndu_197; "onecoreuap\\enduser\\nui\\onecore\\sett"...
0x180072df8  mov     edx, 24Ah; void *
0x180072dfd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072e02  mov     ebx, eax
0x180072e04  lea     rcx, [rsp+58h+TokenHandle]
0x180072e09  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072e0e  mov     eax, ebx
0x180072e10  jmp     loc_180072F3A
0x180072e15  mov     [rsp+58h+TokenInformationLength], esi
0x180072e19  lea     rax, [rsp+58h+TokenInformationLength]
0x180072e1e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180072e23  xor     r9d, r9d; TokenInformationLength
0x180072e26  xor     r8d, r8d; TokenInformation
0x180072e29  lea     edx, [r9+1]; TokenInformationClass
0x180072e2d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180072e32  call    cs:__imp_GetTokenInformation
0x180072e38  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180072e3c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180072e41  mov     rbx, rax
0x180072e44  mov     [rsp+58h+var_28], rax
0x180072e49  lea     rax, [rsp+58h+TokenInformationLength]
0x180072e4e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180072e53  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180072e58  mov     r8, rbx; TokenInformation
0x180072e5b  mov     edx, 1; TokenInformationClass
0x180072e60  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180072e65  call    cs:__imp_GetTokenInformation
0x180072e6b  test    eax, eax
0x180072e6d  jnz     short loc_180072EA3
0x180072e6f  mov     rcx, [rsp+58h]; this
0x180072e74  lea     r8, aOnecoreuapEndu_197; "onecoreuap\\enduser\\nui\\onecore\\sett"...
0x180072e7b  mov     edx, 251h; void *
0x180072e80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072e85  mov     ebx, eax
0x180072e87  lea     rcx, [rsp+58h+var_28]
0x180072e8c  call    ??1?$CSpCollection@PEAVCSpCategory@@@@QEAA@XZ; CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(void)
0x180072e91  nop
0x180072e92  lea     rcx, [rsp+58h+TokenHandle]
0x180072e97  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072e9c  mov     eax, ebx
0x180072e9e  jmp     loc_180072F3A
0x180072ea3  mov     [rsp+58h+StringSid], rsi
0x180072ea8  lea     rdx, [rsp+58h+StringSid]; StringSid
0x180072ead  mov     rcx, [rbx]; Sid
0x180072eb0  call    cs:__imp_ConvertSidToStringSidW
0x180072eb6  test    eax, eax
0x180072eb8  jnz     short loc_180072EF6
0x180072eba  mov     rcx, [rsp+58h]; this
0x180072ebf  lea     r8, aOnecoreuapEndu_197; "onecoreuap\\enduser\\nui\\onecore\\sett"...
0x180072ec6  mov     edx, 257h; void *
0x180072ecb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072ed0  mov     ebx, eax
0x180072ed2  lea     rcx, [rsp+58h+StringSid]
0x180072ed7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072edc  nop
0x180072edd  lea     rcx, [rsp+58h+var_28]
0x180072ee2  call    ??1?$CSpCollection@PEAVCSpCategory@@@@QEAA@XZ; CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(void)
0x180072ee7  nop
0x180072ee8  lea     rcx, [rsp+58h+TokenHandle]
0x180072eed  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072ef2  mov     eax, ebx
0x180072ef4  jmp     short loc_180072F3A
0x180072ef6  mov     rdx, [rsp+58h+StringSid]
0x180072efb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180072eff  inc     r8
0x180072f02  cmp     [rdx+r8*2], si
0x180072f07  jnz     short loc_180072EFF
0x180072f09  mov     rcx, rdi
0x180072f0c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180072f11  nop
0x180072f12  lea     rcx, [rsp+58h+StringSid]
0x180072f17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072f1c  nop
0x180072f1d  lea     rcx, [rsp+58h+var_28]
0x180072f22  call    ??1?$CSpCollection@PEAVCSpCategory@@@@QEAA@XZ; CSpCollection<CSpCategory *>::~CSpCollection<CSpCategory *>(void)
0x180072f27  nop
0x180072f28  lea     rcx, [rsp+58h+TokenHandle]
0x180072f2d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072f32  xor     eax, eax
0x180072f34  jmp     short loc_180072F3A
0x180072f36  mov     eax, [rsp+58h+TokenInformationLength]
0x180072f3a  add     rsp, 40h
0x180072f3e  pop     rdi
0x180072f3f  pop     rsi
0x180072f40  pop     rbx
0x180072f41  retn
```
