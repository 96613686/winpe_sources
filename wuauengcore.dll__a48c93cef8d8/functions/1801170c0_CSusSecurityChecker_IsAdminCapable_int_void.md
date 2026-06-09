# CSusSecurityChecker::IsAdminCapable(int *,void *)

- ea: `0x1801170c0`
- end: `0x180117226`
- name: `?IsAdminCapable@CSusSecurityChecker@@QEAAJPEAHPEAX@Z`
- size: `358`
- prototype: `int(CSusSecurityChecker *__hidden this, int *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800466d0`
- `0x1801051cc`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x180117018`
- `0x1801170c0`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180117193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180117193`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801171a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801171a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011715e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011715e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180117146`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180117146`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011720a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011720a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801171d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801171d1`

## string_xrefs

- `0x1801170fe`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`
- `0x1801171e4`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`

## pseudocode

```c
__int64 __fastcall CSusSecurityChecker::IsAdminCapable(CSusSecurityChecker *this, int *a2, void *a3)
{
  HANDLE v3; // rbx
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rax
  int ReturnLength; // [rsp+20h] [rbp-30h]
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-18h] BYREF
  DWORD v14; // [rsp+3Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  hObject = 0;
  v3 = a3;
  TokenInformation = 0;
  v14 = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_19;
  }
  if ( CSusSecurityChecker::IsAdmin(this, a2, a3) < 0 || !*a2 )
  {
    if ( !v3 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
      {
        if ( GetLastError() != 1008 )
        {
          v8 = 182;
LABEL_16:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v8,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
                        v7);
          goto LABEL_19;
        }
        if ( hObject )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &hObject) )
        {
          v8 = 185;
          goto LABEL_16;
        }
      }
      v3 = hObject;
    }
    if ( !GetTokenInformation(v3, TokenElevationType, &TokenInformation, 4u, &v14) )
    {
      v8 = 192;
      goto LABEL_16;
    }
    *a2 = TokenInformation == 3;
  }
  LastError = 0;
LABEL_19:
  if ( hObject )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x1801170c0  push    rbp
0x1801170c2  push    rbx
0x1801170c3  push    rdi
0x1801170c4  mov     rbp, rsp
0x1801170c7  sub     rsp, 50h
0x1801170cb  mov     rax, cs:__security_cookie
0x1801170d2  xor     rax, rsp
0x1801170d5  mov     [rbp+var_10], rax
0x1801170d9  mov     [rbp+hObject], 0
0x1801170e1  mov     rbx, r8
0x1801170e4  mov     [rbp+TokenInformation], 0
0x1801170eb  mov     rdi, rdx
0x1801170ee  mov     [rbp+var_14], 0
0x1801170f5  test    rdx, rdx
0x1801170f8  jnz     short loc_18011711C
0x1801170fa  mov     rcx, [rbp+18h]; this
0x1801170fe  lea     r8, aCW1SSrcClientL_64; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180117105  mov     ebx, 80004003h
0x18011710a  mov     edx, 0AFh; void *
0x18011710f  mov     r9d, ebx; char *
0x180117112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117117  jmp     loc_180117201
0x18011711c  call    ?IsAdmin@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdmin(int *,void *)
0x180117121  test    eax, eax
0x180117123  js      short loc_18011712E
0x180117125  cmp     dword ptr [rdi], 0
0x180117128  jnz     loc_1801171FF
0x18011712e  test    rbx, rbx
0x180117131  jnz     loc_1801171B7
0x180117137  mov     rcx, [rbp+hObject]; hObject
0x18011713b  test    rcx, rcx
0x18011713e  jz      short loc_180117146
0x180117140  call    cs:__imp_CloseHandle
0x180117146  call    cs:__imp_GetCurrentThread
0x18011714c  mov     ebx, 8
0x180117151  lea     r9, [rbp+hObject]; TokenHandle
0x180117155  mov     edx, ebx; DesiredAccess
0x180117157  mov     rcx, rax; ThreadHandle
0x18011715a  lea     r8d, [rbx-7]; OpenAsSelf
0x18011715e  call    cs:__imp_OpenThreadToken
0x180117164  test    eax, eax
0x180117166  jnz     short loc_1801171B3
0x180117168  call    cs:__imp_GetLastError
0x18011716e  cmp     eax, 3F0h
0x180117173  jz      short loc_18011717C
0x180117175  mov     edx, 0B6h
0x18011717a  jmp     short loc_1801171E0
0x18011717c  mov     rcx, [rbp+hObject]; hObject
0x180117180  test    rcx, rcx
0x180117183  jz      short loc_180117193
0x180117185  call    cs:__imp_CloseHandle
0x18011718b  mov     [rbp+hObject], 0
0x180117193  call    cs:__imp_GetCurrentProcess
0x180117199  lea     r8, [rbp+hObject]; TokenHandle
0x18011719d  mov     edx, ebx; DesiredAccess
0x18011719f  mov     rcx, rax; ProcessHandle
0x1801171a2  call    cs:__imp_OpenProcessToken
0x1801171a8  test    eax, eax
0x1801171aa  jnz     short loc_1801171B3
0x1801171ac  mov     edx, 0B9h
0x1801171b1  jmp     short loc_1801171E0
0x1801171b3  mov     rbx, [rbp+hObject]
0x1801171b7  mov     r9d, 4; TokenInformationLength
0x1801171bd  lea     rax, [rbp+var_14]
0x1801171c1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1801171c5  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1801171ca  mov     rcx, rbx; TokenHandle
0x1801171cd  lea     edx, [r9+0Eh]; TokenInformationClass
0x1801171d1  call    cs:__imp_GetTokenInformation
0x1801171d7  test    eax, eax
0x1801171d9  jnz     short loc_1801171F4
0x1801171db  mov     edx, 0C0h; void *
0x1801171e0  mov     rcx, [rbp+18h]; this
0x1801171e4  lea     r8, aCW1SSrcClientL_64; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801171eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801171f0  mov     ebx, eax
0x1801171f2  jmp     short loc_180117201
0x1801171f4  xor     eax, eax
0x1801171f6  cmp     [rbp+TokenInformation], 3
0x1801171fa  setz    al
0x1801171fd  mov     [rdi], eax
0x1801171ff  xor     ebx, ebx
0x180117201  mov     rcx, [rbp+hObject]; hObject
0x180117205  test    rcx, rcx
0x180117208  jz      short loc_180117210
0x18011720a  call    cs:__imp_CloseHandle
0x180117210  mov     eax, ebx
0x180117212  mov     rcx, [rbp+var_10]
0x180117216  xor     rcx, rsp; StackCookie
0x180117219  call    __security_check_cookie
0x18011721e  add     rsp, 50h
0x180117222  pop     rdi
0x180117223  pop     rbx
0x180117224  pop     rbp
0x180117225  retn
```
