# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x18004ef58`
- end: `0x18004f076`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `286`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004eeb8`

## callees

- `0x180014d60`
- `0x18004ef58`
- `0x18004f0ac`
- `0x18004f0f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ef72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ef72`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ef89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ef89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f012`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004efc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004efc8`

## pseudocode

```c
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  BOOL v5; // eax
  _QWORD *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  const wchar_t *v11; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  v1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = 15;
    goto LABEL_10;
  }
  LODWORD(TokenInformation) = 0;
  ReturnLength = 0;
  v5 = GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  v6 = WPP_GLOBAL_Control;
  if ( v5 )
  {
    v1 = (unsigned int)((_DWORD)TokenInformation - 2) <= 1;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v9 = 14;
LABEL_10:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, LastError);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
  {
    v10 = v6[2];
    v11 = L"YES";
    if ( !v1 )
      v11 = L"NO";
    WPP_SF_S(v10, v3, v4, v11);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18004ef58  mov     [rsp+arg_18], rbx
0x18004ef5d  mov     [rsp+TokenInformation], rcx
0x18004ef62  push    rbp
0x18004ef63  sub     rsp, 30h
0x18004ef67  xor     bl, bl
0x18004ef69  mov     [rsp+38h+TokenHandle], 0
0x18004ef72  call    cs:__imp_GetCurrentThread
0x18004ef78  mov     edx, 8; DesiredAccess
0x18004ef7d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004ef82  mov     rcx, rax; ThreadHandle
0x18004ef85  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ef89  call    cs:__imp_OpenThreadToken
0x18004ef8f  lea     rbp, WPP_GLOBAL_Control
0x18004ef96  test    eax, eax
0x18004ef98  jz      short loc_18004F000
0x18004ef9a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18004ef9f  lea     rax, [rsp+38h+arg_8]
0x18004efa4  mov     r9d, 4; TokenInformationLength
0x18004efaa  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18004efb2  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004efb7  mov     [rsp+38h+arg_8], 0
0x18004efbf  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004efc4  lea     edx, [r9+5]; TokenInformationClass
0x18004efc8  call    cs:__imp_GetTokenInformation
0x18004efce  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efd5  test    eax, eax
0x18004efd7  jz      short loc_18004EFE8
0x18004efd9  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x18004efdd  add     eax, 0FFFFFFFEh
0x18004efe0  cmp     eax, 1
0x18004efe3  setbe   bl
0x18004efe6  jmp     short loc_18004F037
0x18004efe8  cmp     rcx, rbp
0x18004efeb  jz      short loc_18004F05F
0x18004efed  test    byte ptr [rcx+1Ch], 2
0x18004eff1  jz      short loc_18004F037
0x18004eff3  call    cs:__imp_GetLastError
0x18004eff9  mov     edx, 0Eh
0x18004effe  jmp     short loc_18004F01D
0x18004f000  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f007  cmp     rcx, rbp
0x18004f00a  jz      short loc_18004F05F
0x18004f00c  test    byte ptr [rcx+1Ch], 2
0x18004f010  jz      short loc_18004F037
0x18004f012  call    cs:__imp_GetLastError
0x18004f018  mov     edx, 0Fh
0x18004f01d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f024  mov     r9d, eax
0x18004f027  mov     rcx, [rcx+10h]
0x18004f02b  call    WPP_SF_D
0x18004f030  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f037  cmp     rcx, rbp
0x18004f03a  jz      short loc_18004F05F
0x18004f03c  test    byte ptr [rcx+1Ch], 2
0x18004f040  jz      short loc_18004F05F
0x18004f042  mov     rcx, [rcx+10h]
0x18004f046  lea     rax, aNo; "NO"
0x18004f04d  test    bl, bl
0x18004f04f  lea     r9, aYes; "YES"
0x18004f056  cmovz   r9, rax
0x18004f05a  call    WPP_SF_S
0x18004f05f  lea     rcx, [rsp+38h+TokenHandle]
0x18004f064  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f069  mov     al, bl
0x18004f06b  mov     rbx, [rsp+38h+arg_18]
0x18004f070  add     rsp, 30h
0x18004f074  pop     rbp
0x18004f075  retn
```
