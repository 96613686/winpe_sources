# Windows::System::Internal::_CapabilityAccessCheck(ushort *,void *)

- ea: `0x1800d2db4`
- end: `0x1800d2ee6`
- name: `?_CapabilityAccessCheck@Internal@System@Windows@@YAJPEAGPEAX@Z`
- size: `306`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066008`
- `0x18009a320`

## callees

- `0x180015960`
- `0x1800d2db4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d2e4a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d2e56`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d2e4a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d2e56`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800d2e86`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800d2e86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d2e1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d2e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d2e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d2e67`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d2e7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d2e7e`
- `ntdll!RtlCapabilityCheck` at `0x1800d2eb6`
- `ntdll!RtlCapabilityCheck` at `0x1800d2eb6`
- `ntdll!RtlInitUnicodeString` at `0x1800d2dee`
- `ntdll!RtlInitUnicodeString` at `0x1800d2dee`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d2df4`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d2df4`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::_CapabilityAccessCheck(
        PCWSTR SourceString,
        unsigned __int16 *a2,
        void *a3)
{
  __int64 v3; // rcx
  signed int v4; // eax
  unsigned int v5; // ebx
  int LastError; // eax
  void *v7; // rcx
  HANDLE CurrentThread; // rax
  BOOL v9; // ebx
  bool v10; // sf
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v14; // [rsp+68h] [rbp+18h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  v14 = a2;
  TokenHandle = 0;
  LOBYTE(v14) = 0;
  ReturnLength = 0;
  DestinationString = 0;
  TokenInformation = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( (unsigned __int8)RtlIsMultiSessionSku(v3) )
  {
    LastError = CoImpersonateClient();
    if ( LastError != -2147417833 )
      goto LABEL_9;
    goto LABEL_7;
  }
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( !TokenInformation )
    {
      LastError = CoImpersonateClient();
LABEL_9:
      if ( LastError < 0 )
        goto LABEL_19;
      CurrentThread = GetCurrentThread();
      v9 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
      LastError = CoRevertToSelf();
      if ( LastError < 0 )
        goto LABEL_19;
      if ( !v9 )
      {
        LastError = GetLastError();
        v10 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v10 = LastError < 0;
        }
        if ( v10 )
          goto LABEL_19;
      }
      v7 = TokenHandle;
LABEL_16:
      LastError = RtlCapabilityCheck(v7, &DestinationString, &v14) | 0x10000000;
      if ( LastError >= 0 && !(_BYTE)v14 )
        LastError = -2147024891;
LABEL_19:
      v5 = LastError;
      goto LABEL_20;
    }
LABEL_7:
    v7 = 0;
    goto LABEL_16;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_20:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800d2db4  mov     [rsp-8+arg_0], rbx
0x1800d2db9  mov     [rsp-8+arg_8], rdx
0x1800d2dbe  push    rbp
0x1800d2dbf  mov     rbp, rsp
0x1800d2dc2  sub     rsp, 50h
0x1800d2dc6  xorps   xmm0, xmm0
0x1800d2dc9  mov     [rbp+TokenHandle], 0
0x1800d2dd1  mov     rdx, rcx; SourceString
0x1800d2dd4  mov     byte ptr [rbp+arg_8], 0
0x1800d2dd8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800d2ddc  mov     [rbp+arg_18], 0
0x1800d2de3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800d2de7  mov     [rbp+TokenInformation], 0
0x1800d2dee  call    cs:__imp_RtlInitUnicodeString
0x1800d2df4  call    cs:__imp_RtlIsMultiSessionSku
0x1800d2dfa  test    al, al
0x1800d2dfc  jnz     short loc_1800D2E56
0x1800d2dfe  mov     r9d, 4; TokenInformationLength
0x1800d2e04  lea     rax, [rbp+arg_18]
0x1800d2e08  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800d2e0c  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800d2e11  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800d2e18  lea     edx, [r9+19h]; TokenInformationClass
0x1800d2e1c  call    cs:__imp_GetTokenInformation
0x1800d2e22  test    eax, eax
0x1800d2e24  jnz     short loc_1800D2E44
0x1800d2e26  call    cs:__imp_GetLastError
0x1800d2e2c  mov     ebx, eax
0x1800d2e2e  test    eax, eax
0x1800d2e30  jle     loc_1800D2ED0
0x1800d2e36  movzx   ebx, ax
0x1800d2e39  or      ebx, 80070000h
0x1800d2e3f  jmp     loc_1800D2ED0
0x1800d2e44  cmp     [rbp+TokenInformation], 0
0x1800d2e48  jnz     short loc_1800D2E52
0x1800d2e4a  call    cs:__imp_CoImpersonateClient
0x1800d2e50  jmp     short loc_1800D2E63
0x1800d2e52  xor     ecx, ecx
0x1800d2e54  jmp     short loc_1800D2EAE
0x1800d2e56  call    cs:__imp_CoImpersonateClient
0x1800d2e5c  cmp     eax, 80010117h
0x1800d2e61  jz      short loc_1800D2E52
0x1800d2e63  test    eax, eax
0x1800d2e65  js      short loc_1800D2ECE
0x1800d2e67  call    cs:__imp_GetCurrentThread
0x1800d2e6d  mov     r8d, 1; OpenAsSelf
0x1800d2e73  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d2e77  mov     rcx, rax; ThreadHandle
0x1800d2e7a  lea     edx, [r8+7]; DesiredAccess
0x1800d2e7e  call    cs:__imp_OpenThreadToken
0x1800d2e84  mov     ebx, eax
0x1800d2e86  call    cs:__imp_CoRevertToSelf
0x1800d2e8c  test    eax, eax
0x1800d2e8e  js      short loc_1800D2ECE
0x1800d2e90  test    ebx, ebx
0x1800d2e92  jnz     short loc_1800D2EAA
0x1800d2e94  call    cs:__imp_GetLastError
0x1800d2e9a  test    eax, eax
0x1800d2e9c  jle     short loc_1800D2EA8
0x1800d2e9e  movzx   eax, ax
0x1800d2ea1  or      eax, 80070000h
0x1800d2ea6  test    eax, eax
0x1800d2ea8  js      short loc_1800D2ECE
0x1800d2eaa  mov     rcx, [rbp+TokenHandle]
0x1800d2eae  lea     r8, [rbp+arg_8]
0x1800d2eb2  lea     rdx, [rbp+DestinationString]
0x1800d2eb6  call    cs:__imp_RtlCapabilityCheck
0x1800d2ebc  or      eax, 10000000h
0x1800d2ec1  jl      short loc_1800D2ECE
0x1800d2ec3  cmp     byte ptr [rbp+arg_8], 0
0x1800d2ec7  jnz     short loc_1800D2ECE
0x1800d2ec9  mov     eax, 80070005h
0x1800d2ece  mov     ebx, eax
0x1800d2ed0  lea     rcx, [rbp+TokenHandle]
0x1800d2ed4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d2ed9  mov     eax, ebx
0x1800d2edb  mov     rbx, [rsp+50h+arg_0]
0x1800d2ee0  add     rsp, 50h
0x1800d2ee4  pop     rbp
0x1800d2ee5  retn
```
