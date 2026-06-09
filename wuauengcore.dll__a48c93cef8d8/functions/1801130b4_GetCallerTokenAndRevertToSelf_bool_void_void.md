# GetCallerTokenAndRevertToSelf(bool,void * *,void * *)

- ea: `0x1801130b4`
- end: `0x1801132ed`
- name: `?GetCallerTokenAndRevertToSelf@@YAJ_NPEAPEAX1@Z`
- size: `569`
- prototype: `__int64 __fastcall(__int64, void **, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c710`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1800549f4`
- `0x1800d9a70`
- `0x1801130b4`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011313f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801131d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011313f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801131d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180113135`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801131c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180113135`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801131c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011311d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801131b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011311d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801131b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801131ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801132a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801132c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801131ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801132a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801132c0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180113153`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180113153`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801131de`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801131de`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180113281`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180113281`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180113175`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180113175`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180113213`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180113213`

## string_xrefs

- `0x1801130ff`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x180113188`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x1801131fe`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x180113221`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18011323f`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18011328f`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetCallerTokenAndRevertToSelf(__int64 a1, void **a2, void **a3)
{
  int v3; // r14d
  int v4; // esi
  unsigned int v7; // ebx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  DWORD LastError; // edi
  HANDLE v15; // rax
  __int64 v16; // rdx
  const char *v17; // r9
  const char *v18; // r9
  HANDLE hObject; // [rsp+20h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v3 = 0;
  TokenHandle = 0;
  v4 = 0;
  hObject = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)0x80004003LL,
      (int)hObject);
    goto LABEL_35;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
LABEL_13:
    v4 = 1;
LABEL_14:
    LastError = 0;
    v15 = GetCurrentThread();
    if ( !OpenThreadToken(v15, 0xBu, 1, &hObject) )
      LastError = GetLastError();
    if ( v3 )
    {
      v11 = CoRevertToSelf();
      v7 = v11;
      if ( LastError )
      {
        v16 = 272;
LABEL_27:
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v16,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
                (const char *)LastError,
                (unsigned int)hObject);
        goto LABEL_28;
      }
      if ( v11 < 0 )
      {
        v12 = 273;
        goto LABEL_21;
      }
    }
    else
    {
      if ( v4 && !RevertToSelf() )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x115,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
          v17);
      if ( LastError )
      {
        v16 = 280;
        goto LABEL_27;
      }
    }
    *a2 = hObject;
    hObject = 0;
    if ( a3 )
    {
      *a3 = TokenHandle;
      TokenHandle = 0;
    }
    v7 = 0;
    goto LABEL_32;
  }
  if ( GetLastError() != 1008 )
  {
    v10 = 232;
LABEL_11:
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v10,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
            v9);
LABEL_28:
    v7 = v13;
    goto LABEL_32;
  }
  v11 = CoImpersonateClient();
  v7 = v11;
  if ( v11 >= 0 )
  {
    v3 = 1;
    goto LABEL_14;
  }
  if ( v11 == -2147417833 )
  {
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      v10 = 243;
      goto LABEL_11;
    }
    goto LABEL_13;
  }
  v12 = 239;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
    (const char *)(unsigned int)v11,
    (int)hObject);
LABEL_32:
  if ( TokenHandle && !ImpersonateLoggedOnUser(TokenHandle) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      v18);
LABEL_35:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x1801130b4  mov     [rsp-28h+arg_0], rbx
0x1801130b9  mov     [rsp-28h+arg_18], rsi
0x1801130be  push    rbp
0x1801130bf  push    rdi
0x1801130c0  push    r12
0x1801130c2  push    r14
0x1801130c4  push    r15
0x1801130c6  mov     rbp, rsp
0x1801130c9  sub     rsp, 40h
0x1801130cd  mov     rax, cs:__security_cookie
0x1801130d4  xor     rax, rsp
0x1801130d7  mov     [rbp+var_10], rax
0x1801130db  xor     r14d, r14d
0x1801130de  mov     [rbp+TokenHandle], 0
0x1801130e6  xor     esi, esi
0x1801130e8  mov     [rbp+hObject], 0
0x1801130f0  mov     r15, r8
0x1801130f3  mov     r12, rdx
0x1801130f6  test    rdx, rdx
0x1801130f9  jnz     short loc_18011311D
0x1801130fb  mov     rcx, [rbp+28h]; this
0x1801130ff  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113106  mov     ebx, 80004003h
0x18011310b  mov     edx, 0D7h; void *
0x180113110  mov     r9d, ebx; char *
0x180113113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113118  jmp     loc_1801132A0
0x18011311d  call    cs:__imp_GetCurrentThread
0x180113123  mov     edi, 1
0x180113128  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18011312c  mov     r8d, edi; OpenAsSelf
0x18011312f  mov     rcx, rax; ThreadHandle
0x180113132  lea     edx, [rdi+0Bh]; DesiredAccess
0x180113135  call    cs:__imp_OpenThreadToken
0x18011313b  test    eax, eax
0x18011313d  jnz     short loc_18011319E
0x18011313f  call    cs:__imp_GetLastError
0x180113145  cmp     eax, 3F0h
0x18011314a  jz      short loc_180113153
0x18011314c  mov     edx, 0E8h
0x180113151  jmp     short loc_180113184
0x180113153  call    cs:__imp_CoImpersonateClient
0x180113159  mov     ebx, eax
0x18011315b  test    eax, eax
0x18011315d  jns     short loc_180113199
0x18011315f  cmp     eax, 80010117h
0x180113164  jz      short loc_180113170
0x180113166  mov     edx, 0EFh
0x18011316b  jmp     loc_1801131FA
0x180113170  mov     ecx, 2; ImpersonationLevel
0x180113175  call    cs:__imp_ImpersonateSelf
0x18011317b  test    eax, eax
0x18011317d  jnz     short loc_18011319E
0x18011317f  mov     edx, 0F3h; void *
0x180113184  mov     rcx, [rbp+28h]; this
0x180113188  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011318f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180113194  jmp     loc_18011324E
0x180113199  mov     r14d, edi
0x18011319c  jmp     short loc_1801131A0
0x18011319e  mov     esi, edi
0x1801131a0  mov     rcx, [rbp+hObject]; hObject
0x1801131a4  xor     edi, edi
0x1801131a6  test    rcx, rcx
0x1801131a9  jz      short loc_1801131B1
0x1801131ab  call    cs:__imp_CloseHandle
0x1801131b1  call    cs:__imp_GetCurrentThread
0x1801131b7  mov     edx, 0Bh; DesiredAccess
0x1801131bc  lea     r9, [rbp+hObject]; TokenHandle
0x1801131c0  mov     rcx, rax; ThreadHandle
0x1801131c3  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x1801131c7  call    cs:__imp_OpenThreadToken
0x1801131cd  test    eax, eax
0x1801131cf  jnz     short loc_1801131D9
0x1801131d1  call    cs:__imp_GetLastError
0x1801131d7  mov     edi, eax
0x1801131d9  test    r14d, r14d
0x1801131dc  jz      short loc_18011320F
0x1801131de  call    cs:__imp_CoRevertToSelf
0x1801131e4  mov     ebx, eax
0x1801131e6  test    edi, edi
0x1801131e8  jz      short loc_1801131F1
0x1801131ea  mov     edx, 110h
0x1801131ef  jmp     short loc_18011323B
0x1801131f1  test    eax, eax
0x1801131f3  jns     short loc_180113252
0x1801131f5  mov     edx, 111h; void *
0x1801131fa  mov     rcx, [rbp+28h]; this
0x1801131fe  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113205  mov     r9d, eax; char *
0x180113208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011320d  jmp     short loc_180113278
0x18011320f  test    esi, esi
0x180113211  jz      short loc_180113232
0x180113213  call    cs:__imp_RevertToSelf
0x180113219  test    eax, eax
0x18011321b  jnz     short loc_180113232
0x18011321d  mov     rcx, [rbp+28h]; this
0x180113221  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113228  mov     edx, 115h; void *
0x18011322d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180113232  test    edi, edi
0x180113234  jz      short loc_180113252
0x180113236  mov     edx, 118h; void *
0x18011323b  mov     rcx, [rbp+28h]; this
0x18011323f  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113246  mov     r9d, edi; char *
0x180113249  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011324e  mov     ebx, eax
0x180113250  jmp     short loc_180113278
0x180113252  mov     rax, [rbp+hObject]
0x180113256  mov     [r12], rax
0x18011325a  mov     [rbp+hObject], 0
0x180113262  test    r15, r15
0x180113265  jz      short loc_180113276
0x180113267  mov     rax, [rbp+TokenHandle]
0x18011326b  mov     [r15], rax
0x18011326e  mov     [rbp+TokenHandle], 0
0x180113276  xor     ebx, ebx
0x180113278  mov     rcx, [rbp+TokenHandle]; hToken
0x18011327c  test    rcx, rcx
0x18011327f  jz      short loc_1801132A0
0x180113281  call    cs:__imp_ImpersonateLoggedOnUser
0x180113287  test    eax, eax
0x180113289  jnz     short loc_1801132A0
0x18011328b  mov     rcx, [rbp+28h]; this
0x18011328f  lea     r8, aCW1SSrcClientL_69; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113296  mov     edx, 0DEh; void *
0x18011329b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801132a0  mov     rcx, [rbp+hObject]; hObject
0x1801132a4  test    rcx, rcx
0x1801132a7  jz      short loc_1801132B7
0x1801132a9  call    cs:__imp_CloseHandle
0x1801132af  mov     [rbp+hObject], 0
0x1801132b7  mov     rcx, [rbp+TokenHandle]; hObject
0x1801132bb  test    rcx, rcx
0x1801132be  jz      short loc_1801132C6
0x1801132c0  call    cs:__imp_CloseHandle
0x1801132c6  mov     eax, ebx
0x1801132c8  mov     rcx, [rbp+var_10]
0x1801132cc  xor     rcx, rsp; StackCookie
0x1801132cf  call    __security_check_cookie
0x1801132d4  lea     r11, [rsp+40h+var_s0]
0x1801132d9  mov     rbx, [r11+30h]
0x1801132dd  mov     rsi, [r11+48h]
0x1801132e1  mov     rsp, r11
0x1801132e4  pop     r15
0x1801132e6  pop     r14
0x1801132e8  pop     r12
0x1801132ea  pop     rdi
0x1801132eb  pop     rbp
0x1801132ec  retn
```
