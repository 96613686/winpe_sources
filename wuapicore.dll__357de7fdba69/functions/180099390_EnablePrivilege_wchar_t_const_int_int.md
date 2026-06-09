# EnablePrivilege(wchar_t const *,int,int *)

- ea: `0x180099390`
- end: `0x1800994f7`
- name: `?EnablePrivilege@@YAJPEB_WHPEAH@Z`
- size: `359`
- prototype: `__int64 __fastcall(const wchar_t *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180099500`

## callees

- `0x180007d34`
- `0x180099390`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099429`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800993d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800993d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800993e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800993e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180099417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180099417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800993ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800993ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800994cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800994cd`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180099489`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180099489`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180099445`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180099445`

## string_xrefs

- `0x18009943e`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(const wchar_t *a1, DWORD a2, DWORD *a3)
{
  DWORD v3; // ebx
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rax
  unsigned int LastError; // edi
  void *TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid[2]; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v3 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  PreviousState = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
      v8 = 53;
LABEL_12:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v8,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\reboot\\rebootutil.cpp",
                    v7);
      goto LABEL_17;
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      v8 = 57;
      goto LABEL_12;
    }
  }
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
  {
    v8 = 60;
    goto LABEL_12;
  }
  Luid[0].LowPart = 1;
  Luid[1].HighPart = a2 != 0 ? 2 : 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, &PreviousState, &ReturnLength) )
  {
    v8 = 66;
    goto LABEL_12;
  }
  if ( PreviousState.PrivilegeCount )
    v3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
  else
    v3 = a2;
  LastError = 0;
LABEL_17:
  if ( a3 )
    *a3 = v3;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180099390  mov     [rsp-8+arg_0], rbx
0x180099395  mov     [rsp-8+arg_8], rsi
0x18009939a  mov     [rsp-8+arg_10], rdi
0x18009939f  push    rbp
0x1800993a0  mov     rbp, rsp
0x1800993a3  sub     rsp, 70h
0x1800993a7  mov     rax, cs:__security_cookie
0x1800993ae  xor     rax, rsp
0x1800993b1  mov     [rbp+var_8], rax
0x1800993b5  xor     ebx, ebx
0x1800993b7  xorps   xmm0, xmm0
0x1800993ba  xorps   xmm1, xmm1
0x1800993bd  mov     [rbp+TokenHandle], rbx
0x1800993c1  mov     [rbp+var_38], ebx
0x1800993c4  mov     rsi, r8
0x1800993c7  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x1800993cb  mov     edi, edx
0x1800993cd  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x1800993d1  call    cs:__imp_GetCurrentThread
0x1800993d7  mov     rcx, rax; ThreadHandle
0x1800993da  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800993de  lea     edx, [rbx+28h]; DesiredAccess
0x1800993e1  lea     r8d, [rbx+1]; OpenAsSelf
0x1800993e5  call    cs:__imp_OpenThreadToken
0x1800993eb  test    eax, eax
0x1800993ed  jnz     short loc_180099438
0x1800993ef  call    cs:__imp_GetLastError
0x1800993f5  cmp     eax, 3F0h
0x1800993fa  jz      short loc_180099404
0x1800993fc  lea     edx, [rbx+35h]
0x1800993ff  jmp     loc_180099496
0x180099404  mov     rcx, [rbp+TokenHandle]; hObject
0x180099408  test    rcx, rcx
0x18009940b  jz      short loc_180099417
0x18009940d  call    cs:__imp_CloseHandle
0x180099413  mov     [rbp+TokenHandle], rbx
0x180099417  call    cs:__imp_GetCurrentProcess
0x18009941d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180099421  mov     edx, 28h ; '('; DesiredAccess
0x180099426  mov     rcx, rax; ProcessHandle
0x180099429  call    cs:__imp_OpenProcessToken
0x18009942f  test    eax, eax
0x180099431  jnz     short loc_180099438
0x180099433  lea     edx, [rax+39h]
0x180099436  jmp     short loc_180099496
0x180099438  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x18009943c  xor     ecx, ecx; lpSystemName
0x18009943e  lea     rdx, Name; "SeShutdownPrivilege"
0x180099445  call    cs:__imp_LookupPrivilegeValueW
0x18009944b  test    eax, eax
0x18009944d  jnz     short loc_180099454
0x18009944f  lea     edx, [rax+3Ch]
0x180099452  jmp     short loc_180099496
0x180099454  mov     eax, edi
0x180099456  mov     [rbp+Luid.LowPart], 1
0x18009945d  neg     eax
0x18009945f  lea     r8, [rbp+Luid]; NewState
0x180099463  lea     rax, [rbp+var_38]
0x180099467  mov     r9d, 10h; BufferLength
0x18009946d  sbb     ecx, ecx
0x18009946f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180099474  and     ecx, 2
0x180099477  lea     rax, [rbp+var_18]
0x18009947b  mov     [rbp+Luid.HighPart+8], ecx
0x18009947e  xor     edx, edx; DisableAllPrivileges
0x180099480  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180099484  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180099489  call    cs:__imp_AdjustTokenPrivileges
0x18009948f  test    eax, eax
0x180099491  jnz     short loc_1800994AA
0x180099493  lea     edx, [rax+42h]; void *
0x180099496  mov     rcx, [rbp+8]; this
0x18009949a  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\reboot"...
0x1800994a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800994a6  mov     edi, eax
0x1800994a8  jmp     short loc_1800994BD
0x1800994aa  cmp     [rbp+var_18.PrivilegeCount], ebx
0x1800994ad  jnz     short loc_1800994B3
0x1800994af  mov     ebx, edi
0x1800994b1  jmp     short loc_1800994BB
0x1800994b3  mov     ebx, [rbp+var_18.Privileges.Attributes]
0x1800994b6  shr     ebx, 1
0x1800994b8  and     ebx, 1
0x1800994bb  xor     edi, edi
0x1800994bd  test    rsi, rsi
0x1800994c0  jz      short loc_1800994C4
0x1800994c2  mov     [rsi], ebx
0x1800994c4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800994c8  test    rcx, rcx
0x1800994cb  jz      short loc_1800994D3
0x1800994cd  call    cs:__imp_CloseHandle
0x1800994d3  mov     eax, edi
0x1800994d5  mov     rcx, [rbp+var_8]
0x1800994d9  xor     rcx, rsp; StackCookie
0x1800994dc  call    __security_check_cookie
0x1800994e1  lea     r11, [rsp+70h+var_s0]
0x1800994e6  mov     rbx, [r11+10h]
0x1800994ea  mov     rsi, [r11+18h]
0x1800994ee  mov     rdi, [r11+20h]
0x1800994f2  mov     rsp, r11
0x1800994f5  pop     rbp
0x1800994f6  retn
```
