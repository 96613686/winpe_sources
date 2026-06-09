# CPrivilegeEnable::ImpersonationCheck(void)

- ea: `0x180014744`
- end: `0x18001486e`
- name: `?ImpersonationCheck@CPrivilegeEnable@@AEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(CPrivilegeEnable *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a340`

## callees

- `0x180005b40`
- `0x180014744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001479a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001479a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014810`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001478a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001478a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001476d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001476d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014854`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014854`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014800`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014800`

## string_xrefs

- `0x1800147cf`: `CPrivilegeEnable::ImpersonationCheck`
- `0x1800147c5`: `OpenThreadToken failed: 0x%x in %s`
- `0x18001482f`: `GetTokenInformation failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CPrivilegeEnable::ImpersonationCheck(CPrivilegeEnable *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  signed int v5; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  *((_BYTE *)this + 5) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 == -2147023888 )
  {
LABEL_15:
    v4 = 0;
    goto LABEL_16;
  }
  if ( v4 >= 0 )
  {
LABEL_11:
    if ( !GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 < 0 )
      {
        _DbgPrintMessage(
          8,
          "GetTokenInformation failed: 0x%x in %s",
          (unsigned int)v4,
          "CPrivilegeEnable::ImpersonationCheck");
        goto LABEL_16;
      }
    }
    if ( (unsigned int)(TokenInformation - 2) <= 1 )
      *((_BYTE *)this + 5) = 1;
    goto LABEL_15;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v4, "CPrivilegeEnable::ImpersonationCheck");
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014744  mov     rax, rsp
0x180014747  mov     [rax+20h], rbx
0x18001474b  push    rdi
0x18001474c  sub     rsp, 30h
0x180014750  mov     rdi, rcx
0x180014753  mov     qword ptr [rax+18h], 0
0x18001475b  mov     dword ptr [rax+8], 0
0x180014762  mov     dword ptr [rax+10h], 0
0x180014769  mov     byte ptr [rcx+5], 0
0x18001476d  call    cs:__imp_GetCurrentThread
0x180014774  nop     dword ptr [rax+rax+00h]
0x180014779  mov     edx, 8; DesiredAccess
0x18001477e  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180014783  mov     rcx, rax; ThreadHandle
0x180014786  lea     r8d, [rdx-7]; OpenAsSelf
0x18001478a  call    cs:__imp_OpenThreadToken
0x180014791  nop     dword ptr [rax+rax+00h]
0x180014796  test    eax, eax
0x180014798  jnz     short loc_1800147E2
0x18001479a  call    cs:__imp_GetLastError
0x1800147a1  nop     dword ptr [rax+rax+00h]
0x1800147a6  mov     ebx, eax
0x1800147a8  test    eax, eax
0x1800147aa  jle     short loc_1800147B5
0x1800147ac  movzx   ebx, ax
0x1800147af  or      ebx, 80070000h
0x1800147b5  cmp     ebx, 800703F0h
0x1800147bb  jz      loc_180014848
0x1800147c1  test    ebx, ebx
0x1800147c3  jns     short loc_1800147E2
0x1800147c5  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x1800147cc  mov     r8d, ebx
0x1800147cf  lea     r9, aCprivilegeenab_0; "CPrivilegeEnable::ImpersonationCheck"
0x1800147d6  mov     ecx, 8; int
0x1800147db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800147e0  jmp     short loc_18001484A
0x1800147e2  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800147e7  lea     rax, [rsp+38h+arg_8]
0x1800147ec  mov     r9d, 4; TokenInformationLength
0x1800147f2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800147f7  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800147fc  lea     edx, [r9+5]; TokenInformationClass
0x180014800  call    cs:__imp_GetTokenInformation
0x180014807  nop     dword ptr [rax+rax+00h]
0x18001480c  test    eax, eax
0x18001480e  jnz     short loc_180014838
0x180014810  call    cs:__imp_GetLastError
0x180014817  nop     dword ptr [rax+rax+00h]
0x18001481c  mov     ebx, eax
0x18001481e  test    eax, eax
0x180014820  jle     short loc_18001482B
0x180014822  movzx   ebx, ax
0x180014825  or      ebx, 80070000h
0x18001482b  test    ebx, ebx
0x18001482d  jns     short loc_180014838
0x18001482f  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x180014836  jmp     short loc_1800147CC
0x180014838  mov     eax, [rsp+38h+TokenInformation]
0x18001483c  add     eax, 0FFFFFFFEh
0x18001483f  cmp     eax, 1
0x180014842  ja      short loc_180014848
0x180014844  mov     byte ptr [rdi+5], 1
0x180014848  xor     ebx, ebx
0x18001484a  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18001484f  test    rcx, rcx
0x180014852  jz      short loc_180014860
0x180014854  call    cs:__imp_CloseHandle
0x18001485b  nop     dword ptr [rax+rax+00h]
0x180014860  mov     eax, ebx
0x180014862  mov     rbx, [rsp+38h+arg_18]
0x180014867  add     rsp, 30h
0x18001486b  pop     rdi
0x18001486c  retn
```
