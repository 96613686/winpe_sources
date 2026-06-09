# RebootSystem(wchar_t const *,int,int,ulong)

- ea: `0x180099500`
- end: `0x1800996c4`
- name: `?RebootSystem@@YAJPEB_WHHK@Z`
- size: `452`
- prototype: `__int64 __fastcall(const wchar_t *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b8e0`

## callees

- `0x180007d34`
- `0x180090bc8`
- `0x180099390`
- `0x180099500`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099520`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099535`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009953f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009953f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099584`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800995a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099584`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800995a3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180099646`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180099646`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180099558`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180099558`
- `USER32!ExitWindowsEx` at `0x18009960e`
- `USER32!ExitWindowsEx` at `0x18009960e`

## string_xrefs

- `0x18009956c`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x1800995e2`: `Attempting %ws reboot by invoking %ws`
- `0x180099660`: `Attempted to reboot system, but unnecessary since shutdown is in progress`

## pseudocode

```c
__int64 __fastcall RebootSystem(const wchar_t *a1)
{
  int v1; // edi
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  const wchar_t *v6; // rcx
  int v7; // ebx
  const wchar_t *v8; // rcx
  signed int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-38h]
  void *TokenHandle; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_11:
    v6 = (const wchar_t *)TokenHandle;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_13;
  }
  if ( GetLastError() != 1008 )
  {
    v4 = 500;
    goto LABEL_6;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v1 = 1;
    goto LABEL_11;
  }
  v4 = 504;
LABEL_6:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                v3);
  v6 = (const wchar_t *)TokenHandle;
  v7 = LastError;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v7 >= 0 )
  {
LABEL_13:
    LODWORD(TokenHandle) = 0;
    v7 = EnablePrivilege(v6, 1u, (DWORD *)&TokenHandle);
    if ( v7 >= 0 )
    {
      WUTrace(0, 0, 32, 5, 0, L"Attempting %ws reboot by invoking %ws", L"non-forced", L"ExitWindowsEx");
      if ( !ExitWindowsEx(2u, 0x80020002) )
      {
        v9 = GetLastError();
        v7 = (unsigned __int16)v9 | 0x80070000;
        if ( v9 <= 0 )
          v7 = v9;
        if ( v7 >= 0 )
          v7 = -2147418113;
      }
      EnablePrivilege(v8, (DWORD)TokenHandle, 0);
    }
    if ( v1 )
      RevertToSelf();
  }
  if ( v7 == -2147023781 )
  {
    WUTrace(0, 0, 32, 5, 0, L"Attempted to reboot system, but unnecessary since shutdown is in progress");
    return 0;
  }
  else if ( v7 >= 0 )
  {
    WUTrace(0, 0, 32, 5, 0, L"SUS Client is rebooting system.");
  }
  else
  {
    LODWORD(v11) = v7;
    WUTrace(0, 0, 32, 5, v11, L"reboot system");
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180099500  mov     [rsp+arg_0], rbx
0x180099505  push    rdi
0x180099506  sub     rsp, 50h
0x18009950a  mov     rax, cs:__security_cookie
0x180099511  xor     rax, rsp
0x180099514  mov     [rsp+58h+var_10], rax
0x180099519  xor     edi, edi
0x18009951b  mov     [rsp+58h+TokenHandle], rdi
0x180099520  call    cs:__imp_GetCurrentThread
0x180099526  mov     rcx, rax; ThreadHandle
0x180099529  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18009952e  lea     edx, [rdi+8]; DesiredAccess
0x180099531  lea     r8d, [rdi+1]; OpenAsSelf
0x180099535  call    cs:__imp_OpenThreadToken
0x18009953b  test    eax, eax
0x18009953d  jnz     short loc_180099599
0x18009953f  call    cs:__imp_GetLastError
0x180099545  cmp     eax, 3F0h
0x18009954a  jz      short loc_180099553
0x18009954c  mov     edx, 1F4h
0x180099551  jmp     short loc_180099567
0x180099553  mov     ecx, 2; ImpersonationLevel
0x180099558  call    cs:__imp_ImpersonateSelf
0x18009955e  test    eax, eax
0x180099560  jnz     short loc_180099594
0x180099562  mov     edx, 1F8h; void *
0x180099567  mov     rcx, [rsp+58h]; this
0x18009956c  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180099573  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099578  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18009957d  mov     ebx, eax
0x18009957f  test    rcx, rcx
0x180099582  jz      short loc_18009958A
0x180099584  call    cs:__imp_CloseHandle
0x18009958a  test    ebx, ebx
0x18009958c  js      loc_18009964C
0x180099592  jmp     short loc_1800995A9
0x180099594  mov     edi, 1
0x180099599  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18009959e  test    rcx, rcx
0x1800995a1  jz      short loc_1800995A9
0x1800995a3  call    cs:__imp_CloseHandle
0x1800995a9  lea     r8, [rsp+58h+TokenHandle]; int *
0x1800995ae  mov     dword ptr [rsp+58h+TokenHandle], 0
0x1800995b6  mov     edx, 1; int
0x1800995bb  call    ?EnablePrivilege@@YAJPEB_WHPEAH@Z; EnablePrivilege(wchar_t const *,int,int *)
0x1800995c0  mov     ebx, eax
0x1800995c2  test    eax, eax
0x1800995c4  js      short loc_180099642
0x1800995c6  xor     edx, edx
0x1800995c8  lea     rax, aExitwindowsex_0; "ExitWindowsEx"
0x1800995cf  mov     [rsp+58h+var_20], rax
0x1800995d4  xor     ecx, ecx
0x1800995d6  lea     rax, aNonForced; "non-forced"
0x1800995dd  mov     [rsp+58h+var_28], rax
0x1800995e2  lea     rax, aAttemptingWsRe; "Attempting %ws reboot by invoking %ws"
0x1800995e9  mov     [rsp+58h+var_30], rax
0x1800995ee  lea     r9d, [rdx+5]
0x1800995f2  lea     r8d, [rdx+20h]
0x1800995f6  mov     [rsp+58h+var_38], 0
0x1800995ff  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180099604  mov     edx, 80020002h; dwReason
0x180099609  mov     ecx, 2; uFlags
0x18009960e  call    cs:__imp_ExitWindowsEx
0x180099614  test    eax, eax
0x180099616  jnz     short loc_180099636
0x180099618  call    cs:__imp_GetLastError
0x18009961e  movzx   ebx, ax
0x180099621  or      ebx, 80070000h
0x180099627  test    eax, eax
0x180099629  cmovle  ebx, eax
0x18009962c  mov     eax, 8000FFFFh
0x180099631  test    ebx, ebx
0x180099633  cmovns  ebx, eax
0x180099636  mov     edx, dword ptr [rsp+58h+TokenHandle]; int
0x18009963a  xor     r8d, r8d; int *
0x18009963d  call    ?EnablePrivilege@@YAJPEB_WHPEAH@Z; EnablePrivilege(wchar_t const *,int,int *)
0x180099642  test    edi, edi
0x180099644  jz      short loc_18009964C
0x180099646  call    cs:__imp_RevertToSelf
0x18009964c  xor     edx, edx
0x18009964e  xor     ecx, ecx
0x180099650  lea     r9d, [rdx+5]
0x180099654  lea     r8d, [rdx+20h]
0x180099658  cmp     ebx, 8007045Bh
0x18009965e  jnz     short loc_18009967A
0x180099660  lea     rax, aAttemptedToReb; "Attempted to reboot system, but unneces"...
0x180099667  mov     [rsp+58h+var_30], rax
0x18009966c  mov     [rsp+58h+var_38], rcx
0x180099671  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180099676  xor     ebx, ebx
0x180099678  jmp     short loc_1800996AA
0x18009967a  test    ebx, ebx
0x18009967c  jns     short loc_180099690
0x18009967e  lea     rax, aRebootSystem; "reboot system"
0x180099685  mov     [rsp+58h+var_30], rax
0x18009968a  mov     dword ptr [rsp+58h+var_38], ebx
0x18009968e  jmp     short loc_1800996A5
0x180099690  lea     rax, aSusClientIsReb; "SUS Client is rebooting system."
0x180099697  mov     [rsp+58h+var_30], rax
0x18009969c  mov     [rsp+58h+var_38], 0
0x1800996a5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800996aa  mov     eax, ebx
0x1800996ac  mov     rcx, [rsp+58h+var_10]
0x1800996b1  xor     rcx, rsp; StackCookie
0x1800996b4  call    __security_check_cookie
0x1800996b9  mov     rbx, [rsp+58h+arg_0]
0x1800996be  add     rsp, 50h
0x1800996c2  pop     rdi
0x1800996c3  retn
```
