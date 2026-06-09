# _anonymous_namespace_::security_impersonation_state::impersonate

- ea: `0x18008113c`
- end: `0x180081442`
- name: `_anonymous_namespace_::security_impersonation_state::impersonate`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082af0`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x18008113c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008122e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008123b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008125a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008122e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008123b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008125a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008120e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008120e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081250`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081250`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180081224`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180081224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800812ec`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800811ed`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800811ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180081174`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180081174`

## string_xrefs

- `0x180081320`: `impersonate`
- `0x18008135c`: `impersonate`
- `0x180081398`: `impersonate`
- `0x1800813d4`: `impersonate`
- `0x180081410`: `impersonate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
DWORD __fastcall anonymous_namespace_::security_impersonation_state::impersonate(__int64 a1, DWORD a2)
{
  HANDLE v3; // rbx
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  HANDLE CurrentThread; // rax
  DWORD v8; // eax
  DWORD result; // eax
  HANDLE v10; // rcx
  HANDLE v11; // rcx
  void *v12; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = OpenProcess(0x1000u, 0, a2);
  TokenHandle[1] = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "impersonate",
        27);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  TokenHandle[0] = 0;
  if ( !OpenProcessToken(v3, 0x2000000u, TokenHandle) )
  {
    v5 = GetLastError();
    if ( v5 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v5,
        0,
        "[%s:%d] failed; ",
        "impersonate",
        30);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  Token = 0;
  if ( !DuplicateTokenEx(TokenHandle[0], 4u, 0, SecurityImpersonation, TokenImpersonation, &Token) )
  {
    v6 = GetLastError();
    if ( v6 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v6,
        0,
        "[%s:%d] failed; ",
        "impersonate",
        34);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 0, &hObject) && GetLastError() != 1008 )
  {
    v8 = GetLastError();
    if ( v8 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v8,
        0,
        "[%s:%d] failed; ",
        "impersonate",
        38);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  result = SetThreadToken(0, Token);
  if ( !result )
  {
    result = GetLastError();
    if ( result )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        result,
        0,
        "[%s:%d] failed; ",
        "impersonate",
        40);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  if ( *(_BYTE *)(a1 + 8) )
  {
    v10 = hObject;
  }
  else
  {
    result = (unsigned int)hObject;
    v10 = 0;
    *(_QWORD *)a1 = hObject;
    *(_BYTE *)(a1 + 8) = 1;
  }
  if ( v10 )
  {
    hObject = 0;
    result = CloseHandle(v10);
  }
  hObject = 0;
  v11 = Token;
  if ( Token )
  {
    Token = 0;
    result = CloseHandle(v11);
  }
  Token = 0;
  v12 = TokenHandle[0];
  if ( TokenHandle[0] )
  {
    TokenHandle[0] = 0;
    result = CloseHandle(v12);
  }
  TokenHandle[0] = 0;
  if ( v3 )
    return CloseHandle(v3);
  return result;
}

```

## disassembly

```asm
0x18008113c  mov     [rsp-8+arg_10], rbx
0x180081141  mov     [rsp-8+arg_18], rdi
0x180081146  push    rbp
0x180081147  lea     rbp, [rsp-390h]
0x18008114f  sub     rsp, 490h
0x180081156  mov     rax, cs:__security_cookie
0x18008115d  xor     rax, rsp
0x180081160  mov     [rbp+390h+var_10], rax
0x180081167  mov     rdi, rcx
0x18008116a  mov     r8d, edx; dwProcessId
0x18008116d  xor     edx, edx; bInheritHandle
0x18008116f  mov     ecx, 1000h; dwDesiredAccess
0x180081174  call    cs:__imp_OpenProcess
0x18008117a  mov     rbx, rax
0x18008117d  mov     [rsp+490h+var_448], rax
0x180081182  test    rax, rax
0x180081185  jnz     short loc_180081195
0x180081187  call    cs:__imp_GetLastError
0x18008118d  test    eax, eax
0x18008118f  jnz     loc_180081352
0x180081195  mov     [rsp+490h+TokenHandle], 0
0x18008119e  lea     r8, [rsp+490h+TokenHandle]; TokenHandle
0x1800811a3  mov     edx, 2000000h; DesiredAccess
0x1800811a8  mov     rcx, rbx; ProcessHandle
0x1800811ab  call    cs:__imp_OpenProcessToken
0x1800811b1  test    eax, eax
0x1800811b3  jnz     short loc_1800811C3
0x1800811b5  call    cs:__imp_GetLastError
0x1800811bb  test    eax, eax
0x1800811bd  jnz     loc_18008138E
0x1800811c3  mov     [rsp+490h+Token], 0
0x1800811cc  lea     rax, [rsp+490h+Token]
0x1800811d1  mov     [rsp+490h+phNewToken], rax; phNewToken
0x1800811d6  mov     r9d, 2; ImpersonationLevel
0x1800811dc  mov     [rsp+490h+TokenType], r9d; TokenType
0x1800811e1  xor     r8d, r8d; lpTokenAttributes
0x1800811e4  lea     edx, [r9+2]; dwDesiredAccess
0x1800811e8  mov     rcx, [rsp+490h+TokenHandle]; hExistingToken
0x1800811ed  call    cs:__imp_DuplicateTokenEx
0x1800811f3  test    eax, eax
0x1800811f5  jnz     short loc_180081205
0x1800811f7  call    cs:__imp_GetLastError
0x1800811fd  test    eax, eax
0x1800811ff  jnz     loc_1800813CA
0x180081205  mov     [rsp+490h+hObject], 0
0x18008120e  call    cs:__imp_GetCurrentThread
0x180081214  lea     r9, [rsp+490h+hObject]; TokenHandle
0x180081219  xor     r8d, r8d; OpenAsSelf
0x18008121c  mov     edx, 2000000h; DesiredAccess
0x180081221  mov     rcx, rax; ThreadHandle
0x180081224  call    cs:__imp_OpenThreadToken
0x18008122a  test    eax, eax
0x18008122c  jnz     short loc_180081249
0x18008122e  call    cs:__imp_GetLastError
0x180081234  cmp     eax, 3F0h
0x180081239  jz      short loc_180081249
0x18008123b  call    cs:__imp_GetLastError
0x180081241  test    eax, eax
0x180081243  jnz     loc_180081406
0x180081249  mov     rdx, [rsp+490h+Token]; Token
0x18008124e  xor     ecx, ecx; Thread
0x180081250  call    cs:__imp_SetThreadToken
0x180081256  test    eax, eax
0x180081258  jnz     short loc_180081268
0x18008125a  call    cs:__imp_GetLastError
0x180081260  test    eax, eax
0x180081262  jnz     loc_180081316
0x180081268  cmp     byte ptr [rdi+8], 0
0x18008126c  jnz     short loc_18008127E
0x18008126e  mov     rax, [rsp+490h+hObject]
0x180081273  xor     ecx, ecx
0x180081275  mov     [rdi], rax
0x180081278  mov     byte ptr [rdi+8], 1
0x18008127c  jmp     short loc_180081283
0x18008127e  mov     rcx, [rsp+490h+hObject]; hObject
0x180081283  test    rcx, rcx
0x180081286  jz      short loc_180081297
0x180081288  mov     [rsp+490h+hObject], 0
0x180081291  call    cs:__imp_CloseHandle
0x180081297  mov     [rsp+490h+hObject], 0
0x1800812a0  mov     rcx, [rsp+490h+Token]; hObject
0x1800812a5  test    rcx, rcx
0x1800812a8  jz      short loc_1800812B9
0x1800812aa  mov     [rsp+490h+Token], 0
0x1800812b3  call    cs:__imp_CloseHandle
0x1800812b9  mov     [rsp+490h+Token], 0
0x1800812c2  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x1800812c7  test    rcx, rcx
0x1800812ca  jz      short loc_1800812DB
0x1800812cc  mov     [rsp+490h+TokenHandle], 0
0x1800812d5  call    cs:__imp_CloseHandle
0x1800812db  mov     [rsp+490h+TokenHandle], 0
0x1800812e4  test    rbx, rbx
0x1800812e7  jz      short loc_1800812F2
0x1800812e9  mov     rcx, rbx; hObject
0x1800812ec  call    cs:__imp_CloseHandle
0x1800812f2  mov     rcx, [rbp+390h+var_10]
0x1800812f9  xor     rcx, rsp; StackCookie
0x1800812fc  call    __security_check_cookie
0x180081301  lea     r11, [rsp+490h+var_s0]
0x180081309  mov     rbx, [r11+20h]
0x18008130d  mov     rdi, [r11+28h]
0x180081311  mov     rsp, r11
0x180081314  pop     rbp
0x180081315  retn
0x180081316  mov     edx, eax; __int64
0x180081318  mov     dword ptr [rsp+490h+phNewToken], 28h ; '('
0x180081320  lea     rax, aImpersonate; "impersonate"
0x180081327  mov     qword ptr [rsp+490h+TokenType], rax
0x18008132c  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180081333  xor     r8d, r8d; void *
0x180081336  lea     rcx, [rsp+490h+pExceptionObject]; this
0x18008133b  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180081340  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180081347  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x18008134c  call    _CxxThrowException_0
0x180081352  mov     edx, eax; __int64
0x180081354  mov     dword ptr [rsp+490h+phNewToken], 1Bh
0x18008135c  lea     rax, aImpersonate; "impersonate"
0x180081363  mov     qword ptr [rsp+490h+TokenType], rax
0x180081368  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008136f  xor     r8d, r8d; void *
0x180081372  lea     rcx, [rsp+490h+pExceptionObject]; this
0x180081377  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008137c  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180081383  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x180081388  call    _CxxThrowException_0
0x18008138e  mov     edx, eax; __int64
0x180081390  mov     dword ptr [rsp+490h+phNewToken], 1Eh
0x180081398  lea     rax, aImpersonate; "impersonate"
0x18008139f  mov     qword ptr [rsp+490h+TokenType], rax
0x1800813a4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800813ab  xor     r8d, r8d; void *
0x1800813ae  lea     rcx, [rsp+490h+pExceptionObject]; this
0x1800813b3  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800813b8  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800813bf  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x1800813c4  call    _CxxThrowException_0
0x1800813ca  mov     edx, eax; __int64
0x1800813cc  mov     dword ptr [rsp+490h+phNewToken], 22h ; '"'
0x1800813d4  lea     rax, aImpersonate; "impersonate"
0x1800813db  mov     qword ptr [rsp+490h+TokenType], rax
0x1800813e0  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800813e7  xor     r8d, r8d; void *
0x1800813ea  lea     rcx, [rsp+490h+pExceptionObject]; this
0x1800813ef  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800813f4  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800813fb  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x180081400  call    _CxxThrowException_0
0x180081406  mov     edx, eax; __int64
0x180081408  mov     dword ptr [rsp+490h+phNewToken], 26h ; '&'
0x180081410  lea     rax, aImpersonate; "impersonate"
0x180081417  mov     qword ptr [rsp+490h+TokenType], rax
0x18008141c  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180081423  xor     r8d, r8d; void *
0x180081426  lea     rcx, [rsp+490h+pExceptionObject]; this
0x18008142b  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180081430  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180081437  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x18008143c  call    _CxxThrowException_0
```
