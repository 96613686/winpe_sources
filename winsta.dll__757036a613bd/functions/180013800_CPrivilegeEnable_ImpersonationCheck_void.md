# CPrivilegeEnable::ImpersonationCheck(void)

- ea: `0x180013800`
- end: `0x180013901`
- name: `?ImpersonationCheck@CPrivilegeEnable@@AEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CPrivilegeEnable *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028790`

## callees

- `0x180007890`
- `0x180013800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001384a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001384a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013840`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800138ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800138ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800138a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800138a6`

## string_xrefs

- `0x180013875`: `CPrivilegeEnable::ImpersonationCheck`
- `0x18001386b`: `OpenThreadToken failed: 0x%x in %s`
- `0x1800138c9`: `GetTokenInformation failed: 0x%x in %s`

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
0x180013800  mov     rax, rsp
0x180013803  mov     [rax+20h], rbx
0x180013807  push    rdi
0x180013808  sub     rsp, 30h
0x18001380c  mov     rdi, rcx
0x18001380f  mov     qword ptr [rax+18h], 0
0x180013817  mov     dword ptr [rax+8], 0
0x18001381e  mov     dword ptr [rax+10h], 0
0x180013825  mov     byte ptr [rcx+5], 0
0x180013829  call    cs:__imp_GetCurrentThread
0x18001382f  mov     edx, 8; DesiredAccess
0x180013834  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180013839  mov     rcx, rax; ThreadHandle
0x18001383c  lea     r8d, [rdx-7]; OpenAsSelf
0x180013840  call    cs:__imp_OpenThreadToken
0x180013846  test    eax, eax
0x180013848  jnz     short loc_180013888
0x18001384a  call    cs:__imp_GetLastError
0x180013850  mov     ebx, eax
0x180013852  test    eax, eax
0x180013854  jle     short loc_18001385F
0x180013856  movzx   ebx, ax
0x180013859  or      ebx, 80070000h
0x18001385f  cmp     ebx, 800703F0h
0x180013865  jz      short loc_1800138E2
0x180013867  test    ebx, ebx
0x180013869  jns     short loc_180013888
0x18001386b  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180013872  mov     r8d, ebx
0x180013875  lea     r9, aCprivilegeenab_0; "CPrivilegeEnable::ImpersonationCheck"
0x18001387c  mov     ecx, 8; int
0x180013881  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013886  jmp     short loc_1800138E4
0x180013888  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18001388d  lea     rax, [rsp+38h+arg_8]
0x180013892  mov     r9d, 4; TokenInformationLength
0x180013898  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001389d  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800138a2  lea     edx, [r9+5]; TokenInformationClass
0x1800138a6  call    cs:__imp_GetTokenInformation
0x1800138ac  test    eax, eax
0x1800138ae  jnz     short loc_1800138D2
0x1800138b0  call    cs:__imp_GetLastError
0x1800138b6  mov     ebx, eax
0x1800138b8  test    eax, eax
0x1800138ba  jle     short loc_1800138C5
0x1800138bc  movzx   ebx, ax
0x1800138bf  or      ebx, 80070000h
0x1800138c5  test    ebx, ebx
0x1800138c7  jns     short loc_1800138D2
0x1800138c9  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x1800138d0  jmp     short loc_180013872
0x1800138d2  mov     eax, [rsp+38h+TokenInformation]
0x1800138d6  add     eax, 0FFFFFFFEh
0x1800138d9  cmp     eax, 1
0x1800138dc  ja      short loc_1800138E2
0x1800138de  mov     byte ptr [rdi+5], 1
0x1800138e2  xor     ebx, ebx
0x1800138e4  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800138e9  test    rcx, rcx
0x1800138ec  jz      short loc_1800138F4
0x1800138ee  call    cs:__imp_CloseHandle
0x1800138f4  mov     eax, ebx
0x1800138f6  mov     rbx, [rsp+38h+arg_18]
0x1800138fb  add     rsp, 30h
0x1800138ff  pop     rdi
0x180013900  retn
```
