# CSusSecurityChecker::IsAdminCapable(int *,void *)

- ea: `0x1800810f0`
- end: `0x18008124d`
- name: `?IsAdminCapable@CSusSecurityChecker@@QEAAJPEAHPEAX@Z`
- size: `349`
- prototype: `__int64 __fastcall(CSusSecurityChecker *__hidden this, int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800816ac`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180081044`
- `0x1800810f0`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008116c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008116c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180081182`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180081182`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008118c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008118c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800811a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008122e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800811a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008122e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800811f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800811f5`

## string_xrefs

- `0x18008112d`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`
- `0x180081208`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`

## pseudocode

```c
__int64 __fastcall CSusSecurityChecker::IsAdminCapable(CSusSecurityChecker *this, int *a2, void *a3)
{
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HANDLE CurrentProcess; // rax
  int ReturnLength; // [rsp+20h] [rbp-30h]
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-18h] BYREF
  DWORD v13; // [rsp+3Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  hObject = 0;
  TokenInformation = 0;
  v13 = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_17;
  }
  if ( CSusSecurityChecker::IsAdmin(this, a2, a3) < 0 || !*a2 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
    {
      if ( GetLastError() != 1008 )
      {
        v7 = 182;
LABEL_14:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
                      v6);
        goto LABEL_17;
      }
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &hObject) )
      {
        v7 = 185;
        goto LABEL_14;
      }
    }
    if ( !GetTokenInformation(hObject, TokenElevationType, &TokenInformation, 4u, &v13) )
    {
      v7 = 192;
      goto LABEL_14;
    }
    *a2 = TokenInformation == 3;
  }
  LastError = 0;
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x1800810f0  mov     [rsp-8+arg_10], rbx
0x1800810f5  push    rbp
0x1800810f6  mov     rbp, rsp
0x1800810f9  sub     rsp, 50h
0x1800810fd  mov     rax, cs:__security_cookie
0x180081104  xor     rax, rsp
0x180081107  mov     [rbp+var_10], rax
0x18008110b  mov     [rbp+hObject], 0
0x180081113  mov     rbx, rdx
0x180081116  mov     [rbp+TokenInformation], 0
0x18008111d  mov     [rbp+var_14], 0
0x180081124  test    rdx, rdx
0x180081127  jnz     short loc_18008114B
0x180081129  mov     rcx, [rbp+8]; this
0x18008112d  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180081134  mov     ebx, 80004003h
0x180081139  mov     edx, 0AFh; void *
0x18008113e  mov     r9d, ebx; char *
0x180081141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081146  jmp     loc_180081225
0x18008114b  call    ?IsAdmin@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdmin(int *,void *)
0x180081150  test    eax, eax
0x180081152  js      short loc_18008115D
0x180081154  cmp     dword ptr [rbx], 0
0x180081157  jnz     loc_180081223
0x18008115d  mov     rcx, [rbp+hObject]; hObject
0x180081161  test    rcx, rcx
0x180081164  jz      short loc_18008116C
0x180081166  call    cs:__imp_CloseHandle
0x18008116c  call    cs:__imp_GetCurrentThread
0x180081172  mov     edx, 8; DesiredAccess
0x180081177  lea     r9, [rbp+hObject]; TokenHandle
0x18008117b  mov     rcx, rax; ThreadHandle
0x18008117e  lea     r8d, [rdx-7]; OpenAsSelf
0x180081182  call    cs:__imp_OpenThreadToken
0x180081188  test    eax, eax
0x18008118a  jnz     short loc_1800811DA
0x18008118c  call    cs:__imp_GetLastError
0x180081192  cmp     eax, 3F0h
0x180081197  jz      short loc_1800811A0
0x180081199  mov     edx, 0B6h
0x18008119e  jmp     short loc_180081204
0x1800811a0  mov     rcx, [rbp+hObject]; hObject
0x1800811a4  test    rcx, rcx
0x1800811a7  jz      short loc_1800811B7
0x1800811a9  call    cs:__imp_CloseHandle
0x1800811af  mov     [rbp+hObject], 0
0x1800811b7  call    cs:__imp_GetCurrentProcess
0x1800811bd  lea     r8, [rbp+hObject]; TokenHandle
0x1800811c1  mov     edx, 8; DesiredAccess
0x1800811c6  mov     rcx, rax; ProcessHandle
0x1800811c9  call    cs:__imp_OpenProcessToken
0x1800811cf  test    eax, eax
0x1800811d1  jnz     short loc_1800811DA
0x1800811d3  mov     edx, 0B9h
0x1800811d8  jmp     short loc_180081204
0x1800811da  mov     rcx, [rbp+hObject]; TokenHandle
0x1800811de  lea     rax, [rbp+var_14]
0x1800811e2  mov     r9d, 4; TokenInformationLength
0x1800811e8  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1800811ed  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800811f1  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800811f5  call    cs:__imp_GetTokenInformation
0x1800811fb  test    eax, eax
0x1800811fd  jnz     short loc_180081218
0x1800811ff  mov     edx, 0C0h; void *
0x180081204  mov     rcx, [rbp+8]; this
0x180081208  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008120f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180081214  mov     ebx, eax
0x180081216  jmp     short loc_180081225
0x180081218  xor     eax, eax
0x18008121a  cmp     [rbp+TokenInformation], 3
0x18008121e  setz    al
0x180081221  mov     [rbx], eax
0x180081223  xor     ebx, ebx
0x180081225  mov     rcx, [rbp+hObject]; hObject
0x180081229  test    rcx, rcx
0x18008122c  jz      short loc_180081234
0x18008122e  call    cs:__imp_CloseHandle
0x180081234  mov     eax, ebx
0x180081236  mov     rcx, [rbp+var_10]
0x18008123a  xor     rcx, rsp; StackCookie
0x18008123d  call    __security_check_cookie
0x180081242  mov     rbx, [rsp+50h+arg_10]
0x180081247  add     rsp, 50h
0x18008124b  pop     rbp
0x18008124c  retn
```
