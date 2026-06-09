# CreateProcessWithImpersonation(ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x1803103ec`
- end: `0x1803105e2`
- name: `?CreateProcessWithImpersonation@@YAHPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `502`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpApplicationName@<rcx>, LPWSTR lpCommandLine@<rdx>, struct _SECURITY_ATTRIBUTES *@<r8>, struct _SECURITY_ATTRIBUTES *@<r9>, int, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801e776c`

## callees

- `0x1803103ec`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180310559`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180310559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803104fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180310567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803104fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180310567`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1803104f0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1803104f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18031042b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18031042b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180310448`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180310448`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1803105a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1803105a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18031052e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180310547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18031052e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180310547`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180310489`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180310489`
- `USERENV!CreateEnvironmentBlock` at `0x1803104a4`
- `USERENV!CreateEnvironmentBlock` at `0x1803104a4`
- `USERENV!DestroyEnvironmentBlock` at `0x180310515`
- `USERENV!DestroyEnvironmentBlock` at `0x180310515`

## pseudocode

```c
__int64 __fastcall CreateProcessWithImpersonation(
        LPCWSTR lpApplicationName,
        LPWSTR lpCommandLine,
        struct _SECURITY_ATTRIBUTES *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        int a5,
        unsigned int a6,
        void *a7,
        const unsigned __int16 *a8,
        struct _STARTUPINFOW *lpStartupInfo,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  HANDLE CurrentThread; // rax
  unsigned int ProcessAsUserW; // ebx
  DWORD LastError; // edi
  HANDLE hToken; // [rsp+60h] [rbp-20h] BYREF
  LPVOID Environment; // [rsp+68h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xBu, 1, &TokenHandle) )
  {
    hToken = 0;
    ProcessAsUserW = 0;
    Environment = 0;
    if ( DuplicateTokenEx(TokenHandle, 0xFu, 0, SecurityImpersonation, TokenPrimary, &hToken)
      && CreateEnvironmentBlock(&Environment, hToken, 0)
      && Environment )
    {
      ProcessAsUserW = CreateProcessAsUserW(
                         hToken,
                         lpApplicationName,
                         lpCommandLine,
                         0,
                         0,
                         0,
                         0x400u,
                         Environment,
                         0,
                         lpStartupInfo,
                         lpProcessInformation);
    }
    LastError = GetLastError();
    if ( Environment )
    {
      DestroyEnvironmentBlock(Environment);
      Environment = 0;
    }
    if ( hToken )
    {
      CloseHandle(hToken);
      hToken = 0;
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    SetLastError(LastError);
  }
  else
  {
    return GetLastError() == 1008
        && CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0, 0, 0, lpStartupInfo, lpProcessInformation);
  }
  return ProcessAsUserW;
}

```

## disassembly

```asm
0x1803103ec  mov     [rsp-28h+arg_10], rbx
0x1803103f1  mov     [rsp-28h+arg_18], rsi
0x1803103f6  push    rbp
0x1803103f7  push    rdi
0x1803103f8  push    r12
0x1803103fa  push    r14
0x1803103fc  push    r15
0x1803103fe  mov     rbp, rsp
0x180310401  sub     rsp, 80h
0x180310408  mov     rax, cs:__security_cookie
0x18031040f  xor     rax, rsp
0x180310412  mov     [rbp+var_8], rax
0x180310416  mov     r14, [rbp+arg_40]
0x18031041a  xor     r12d, r12d
0x18031041d  mov     r15, [rbp+arg_48]
0x180310421  mov     rsi, rdx
0x180310424  mov     [rbp+TokenHandle], r12
0x180310428  mov     rdi, rcx
0x18031042b  call    cs:__imp_GetCurrentThread
0x180310432  nop     dword ptr [rax+rax+00h]
0x180310437  mov     rcx, rax; ThreadHandle
0x18031043a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18031043e  lea     edx, [r12+0Bh]; DesiredAccess
0x180310443  lea     r8d, [r12+1]; OpenAsSelf
0x180310448  call    cs:__imp_OpenThreadToken
0x18031044f  nop     dword ptr [rax+rax+00h]
0x180310454  test    eax, eax
0x180310456  jz      loc_180310567
0x18031045c  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180310460  lea     rax, [rbp+hToken]
0x180310464  mov     [rsp+80h+phNewToken], rax; phNewToken
0x180310469  lea     r9d, [r12+2]; ImpersonationLevel
0x18031046e  xor     r8d, r8d; lpTokenAttributes
0x180310471  mov     [rsp+80h+TokenType], 1; TokenType
0x180310479  lea     edx, [r12+0Fh]; dwDesiredAccess
0x18031047e  mov     [rbp+hToken], r12
0x180310482  mov     ebx, r12d
0x180310485  mov     [rbp+Environment], r12
0x180310489  call    cs:__imp_DuplicateTokenEx
0x180310490  nop     dword ptr [rax+rax+00h]
0x180310495  test    eax, eax
0x180310497  jz      short loc_1803104FE
0x180310499  mov     rdx, [rbp+hToken]; hToken
0x18031049d  lea     rcx, [rbp+Environment]; lpEnvironment
0x1803104a1  xor     r8d, r8d; bInherit
0x1803104a4  call    cs:__imp_CreateEnvironmentBlock
0x1803104ab  nop     dword ptr [rax+rax+00h]
0x1803104b0  test    eax, eax
0x1803104b2  jz      short loc_1803104FE
0x1803104b4  mov     rax, [rbp+Environment]
0x1803104b8  test    rax, rax
0x1803104bb  jz      short loc_1803104FE
0x1803104bd  mov     rcx, [rbp+hToken]; hToken
0x1803104c1  xor     r9d, r9d; lpProcessAttributes
0x1803104c4  mov     [rsp+80h+lpProcessInformation], r15; lpProcessInformation
0x1803104c9  mov     r8, rsi; lpCommandLine
0x1803104cc  mov     [rsp+80h+lpStartupInfo], r14; lpStartupInfo
0x1803104d1  mov     rdx, rdi; lpApplicationName
0x1803104d4  mov     [rsp+80h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1803104d9  mov     [rsp+80h+lpEnvironment], rax; lpEnvironment
0x1803104de  mov     [rsp+80h+dwCreationFlags], 400h; dwCreationFlags
0x1803104e6  mov     dword ptr [rsp+80h+phNewToken], r12d; bInheritHandles
0x1803104eb  mov     qword ptr [rsp+80h+TokenType], r12; lpThreadAttributes
0x1803104f0  call    cs:__imp_CreateProcessAsUserW
0x1803104f7  nop     dword ptr [rax+rax+00h]
0x1803104fc  mov     ebx, eax
0x1803104fe  call    cs:__imp_GetLastError
0x180310505  nop     dword ptr [rax+rax+00h]
0x18031050a  mov     rcx, [rbp+Environment]; lpEnvironment
0x18031050e  mov     edi, eax
0x180310510  test    rcx, rcx
0x180310513  jz      short loc_180310525
0x180310515  call    cs:__imp_DestroyEnvironmentBlock
0x18031051c  nop     dword ptr [rax+rax+00h]
0x180310521  mov     [rbp+Environment], r12
0x180310525  mov     rcx, [rbp+hToken]; hObject
0x180310529  test    rcx, rcx
0x18031052c  jz      short loc_18031053E
0x18031052e  call    cs:__imp_CloseHandle
0x180310535  nop     dword ptr [rax+rax+00h]
0x18031053a  mov     [rbp+hToken], r12
0x18031053e  mov     rcx, [rbp+TokenHandle]; hObject
0x180310542  test    rcx, rcx
0x180310545  jz      short loc_180310557
0x180310547  call    cs:__imp_CloseHandle
0x18031054e  nop     dword ptr [rax+rax+00h]
0x180310553  mov     [rbp+TokenHandle], r12
0x180310557  mov     ecx, edi; dwErrCode
0x180310559  call    cs:__imp_SetLastError
0x180310560  nop     dword ptr [rax+rax+00h]
0x180310565  jmp     short loc_1803105B7
0x180310567  call    cs:__imp_GetLastError
0x18031056e  nop     dword ptr [rax+rax+00h]
0x180310573  cmp     eax, 3F0h
0x180310578  jnz     short loc_1803105B4
0x18031057a  mov     [rsp+80h+lpStartupInfo], r15; lpProcessInformation
0x18031057f  xor     r9d, r9d; lpThreadAttributes
0x180310582  mov     [rsp+80h+lpCurrentDirectory], r14; lpStartupInfo
0x180310587  xor     r8d, r8d; lpProcessAttributes
0x18031058a  mov     [rsp+80h+lpEnvironment], r12; lpCurrentDirectory
0x18031058f  mov     rdx, rsi; lpCommandLine
0x180310592  mov     qword ptr [rsp+80h+dwCreationFlags], r12; lpEnvironment
0x180310597  mov     rcx, rdi; lpApplicationName
0x18031059a  mov     dword ptr [rsp+80h+phNewToken], r12d; dwCreationFlags
0x18031059f  mov     [rsp+80h+TokenType], r12d; bInheritHandles
0x1803105a4  call    cs:__imp_CreateProcessW
0x1803105ab  nop     dword ptr [rax+rax+00h]
0x1803105b0  mov     ebx, eax
0x1803105b2  jmp     short loc_1803105B7
0x1803105b4  mov     ebx, r12d
0x1803105b7  mov     eax, ebx
0x1803105b9  mov     rcx, [rbp+var_8]
0x1803105bd  xor     rcx, rsp; StackCookie
0x1803105c0  call    __security_check_cookie
0x1803105c5  lea     r11, [rsp+80h+var_s0]
0x1803105cd  mov     rbx, [r11+40h]
0x1803105d1  mov     rsi, [r11+48h]
0x1803105d5  mov     rsp, r11
0x1803105d8  pop     r15
0x1803105da  pop     r14
0x1803105dc  pop     r12
0x1803105de  pop     rdi
0x1803105df  pop     rbp
0x1803105e0  retn
```
