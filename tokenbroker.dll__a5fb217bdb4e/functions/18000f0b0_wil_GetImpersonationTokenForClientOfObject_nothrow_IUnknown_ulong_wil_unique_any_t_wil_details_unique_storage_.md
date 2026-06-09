# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18000f0b0`
- end: `0x18000f2c8`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e9d0`
- `0x18000ee40`
- `0x18000f3f4`
- `0x1800f03a4`
- `0x1800f0ad4`

## callees

- `0x18000bd40`
- `0x18000f0b0`
- `0x1800565a0`
- `0x18007c220`
- `0x1800af930`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f189`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f0f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f0f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f10b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f10b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f14a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f14a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f19d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f19d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f25e`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000f0c9`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000f0c9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000f29b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000f2c0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000f29b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000f2c0`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, DWORD a2, HANDLE *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  void *v12; // rcx
  const char *v13; // r9
  unsigned int v15; // ebx
  unsigned int v16; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-38h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(TokenHandle) = 0;
  v5 = CoImpersonateClientOfObject(a1, &TokenHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v5,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v6,
      TokenTypea);
    return v6;
  }
  v7 = (_DWORD)TokenHandle != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, 1, a3) )
  {
    if ( v7 )
LABEL_25:
      CoRevertToSelf();
    return 0;
  }
  LastError = GetLastError();
  if ( v7 || LastError != 1008 )
  {
    if ( LastError )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x188,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
              (const char *)LastError,
              TokenType);
      if ( v7 )
        CoRevertToSelf();
      return v16;
    }
    if ( v7 )
      goto LABEL_25;
    return 0;
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, a2 | 2, &TokenHandle) )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
            v11);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v15;
  }
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  v12 = TokenHandle;
  *a3 = 0;
  if ( DuplicateTokenEx(v12, a2, 0, SecurityImpersonation, TokenImpersonation, a3) )
  {
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      return 0;
    }
    return 0;
  }
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x184,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          v13);
  if ( !TokenHandle )
    return v15;
  CloseHandle(TokenHandle);
  return v15;
}

```

## disassembly

```asm
0x18000f0b0  push    rbx
0x18000f0b2  push    rbp
0x18000f0b3  push    rsi
0x18000f0b4  push    rdi
0x18000f0b5  sub     rsp, 38h
0x18000f0b9  mov     esi, edx
0x18000f0bb  xor     ebp, ebp
0x18000f0bd  lea     rdx, [rsp+58h+TokenHandle]
0x18000f0c2  mov     dword ptr [rsp+58h+TokenHandle], ebp
0x18000f0c6  mov     rdi, r8
0x18000f0c9  call    cs:__imp_CoImpersonateClientOfObject
0x18000f0cf  mov     ebx, eax
0x18000f0d1  test    eax, eax
0x18000f0d3  js      loc_18000F1FF
0x18000f0d9  xor     bl, bl
0x18000f0db  cmp     dword ptr [rsp+58h+TokenHandle], ebp
0x18000f0df  jz      short loc_18000F0E3
0x18000f0e1  mov     bl, 1
0x18000f0e3  mov     rcx, [rdi]; hObject
0x18000f0e6  lea     rax, [rcx-1]
0x18000f0ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f0ee  jbe     loc_18000F2A6
0x18000f0f4  mov     [rdi], rbp
0x18000f0f7  call    cs:__imp_GetCurrentThread
0x18000f0fd  mov     r9, rdi; TokenHandle
0x18000f100  mov     r8d, 1; OpenAsSelf
0x18000f106  mov     rcx, rax; ThreadHandle
0x18000f109  mov     edx, esi; DesiredAccess
0x18000f10b  call    cs:__imp_OpenThreadToken
0x18000f111  test    eax, eax
0x18000f113  jnz     loc_18000F1AE
0x18000f119  call    cs:__imp_GetLastError
0x18000f11f  test    bl, bl
0x18000f121  jnz     loc_18000F2BA
0x18000f127  cmp     eax, 3F0h
0x18000f12c  jnz     loc_18000F2BA
0x18000f132  mov     [rsp+58h+TokenHandle], rbp
0x18000f137  call    cs:__imp_GetCurrentProcess
0x18000f13d  mov     edx, esi
0x18000f13f  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000f144  or      edx, 2; DesiredAccess
0x18000f147  mov     rcx, rax; ProcessHandle
0x18000f14a  call    cs:__imp_OpenProcessToken
0x18000f150  test    eax, eax
0x18000f152  jz      loc_18000F23C
0x18000f158  mov     rcx, [rdi]; hObject
0x18000f15b  lea     rax, [rcx-1]
0x18000f15f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f163  jbe     loc_18000F2B0
0x18000f169  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x18000f16e  mov     r9d, 2; ImpersonationLevel
0x18000f174  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x18000f179  xor     r8d, r8d; lpTokenAttributes
0x18000f17c  mov     edx, esi; dwDesiredAccess
0x18000f17e  mov     [rsp+58h+TokenType], 2; TokenType
0x18000f186  mov     [rdi], rbp
0x18000f189  call    cs:__imp_DuplicateTokenEx
0x18000f18f  test    eax, eax
0x18000f191  jz      short loc_18000F1C1
0x18000f193  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000f198  test    rcx, rcx
0x18000f19b  jz      short loc_18000F1B6
0x18000f19d  call    cs:__imp_CloseHandle
0x18000f1a3  xor     eax, eax
0x18000f1a5  add     rsp, 38h
0x18000f1a9  pop     rdi
0x18000f1aa  pop     rsi
0x18000f1ab  pop     rbp
0x18000f1ac  pop     rbx
0x18000f1ad  retn
0x18000f1ae  test    bl, bl
0x18000f1b0  jnz     loc_18000F29B
0x18000f1b6  xor     eax, eax
0x18000f1b8  add     rsp, 38h
0x18000f1bc  pop     rdi
0x18000f1bd  pop     rsi
0x18000f1be  pop     rbp
0x18000f1bf  pop     rbx
0x18000f1c0  retn
0x18000f1c1  mov     rcx, [rsp+58h]; this
0x18000f1c6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000f1cd  mov     edx, 184h; void *
0x18000f1d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f1d7  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000f1dc  mov     ebx, eax
0x18000f1de  test    rcx, rcx
0x18000f1e1  jnz     short loc_18000F1EE
0x18000f1e3  mov     eax, ebx
0x18000f1e5  add     rsp, 38h
0x18000f1e9  pop     rdi
0x18000f1ea  pop     rsi
0x18000f1eb  pop     rbp
0x18000f1ec  pop     rbx
0x18000f1ed  retn
0x18000f1ee  call    cs:__imp_CloseHandle
0x18000f1f4  mov     eax, ebx
0x18000f1f6  add     rsp, 38h
0x18000f1fa  pop     rdi
0x18000f1fb  pop     rsi
0x18000f1fc  pop     rbp
0x18000f1fd  pop     rbx
0x18000f1fe  retn
0x18000f1ff  mov     rcx, [rsp+58h]; this
0x18000f204  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000f20b  mov     r9d, ebx; char *
0x18000f20e  mov     edx, 157h; void *
0x18000f213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f218  mov     rcx, [rsp+58h]; this
0x18000f21d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000f224  mov     r9d, ebx; char *
0x18000f227  mov     edx, 177h; void *
0x18000f22c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f231  mov     eax, ebx
0x18000f233  add     rsp, 38h
0x18000f237  pop     rdi
0x18000f238  pop     rsi
0x18000f239  pop     rbp
0x18000f23a  pop     rbx
0x18000f23b  retn
0x18000f23c  mov     rcx, [rsp+58h]; this
0x18000f241  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000f248  mov     edx, 182h; void *
0x18000f24d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f252  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000f257  mov     ebx, eax
0x18000f259  test    rcx, rcx
0x18000f25c  jz      short loc_18000F1E3
0x18000f25e  call    cs:__imp_CloseHandle
0x18000f264  jmp     loc_18000F1E3
0x18000f269  mov     rcx, [rsp+58h]; this
0x18000f26e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000f275  mov     r9d, eax; char *
0x18000f278  mov     edx, 188h; void *
0x18000f27d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000f282  mov     edi, eax
0x18000f284  test    bl, bl
0x18000f286  jnz     short loc_18000F2C0
0x18000f288  mov     eax, edi
0x18000f28a  add     rsp, 38h
0x18000f28e  pop     rdi
0x18000f28f  pop     rsi
0x18000f290  pop     rbp
0x18000f291  pop     rbx
0x18000f292  retn
0x18000f293  test    bl, bl
0x18000f295  jz      loc_18000F1B6
0x18000f29b  call    cs:__imp_CoRevertToSelf
0x18000f2a1  jmp     loc_18000F1B6
0x18000f2a6  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000f2ab  jmp     loc_18000F0F4
0x18000f2b0  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000f2b5  jmp     loc_18000F169
0x18000f2ba  test    eax, eax
0x18000f2bc  jz      short loc_18000F293
0x18000f2be  jmp     short loc_18000F269
0x18000f2c0  call    cs:__imp_CoRevertToSelf
0x18000f2c6  jmp     short loc_18000F288
```
