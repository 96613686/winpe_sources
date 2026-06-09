# WldpIsDebugAllowed

- ea: `0x180029040`
- end: `0x1800291e2`
- name: `WldpIsDebugAllowed`
- size: `418`
- prototype: `__int64 __fastcall(HANDLE hProcess, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180014eb0`
- `0x180027260`
- `0x180027e94`
- `0x180029040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029102`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002910c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002910c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291cf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002916f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002916f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029145`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029145`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x1800290de`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x1800290de`

## pseudocode

```c
__int64 __fastcall WldpIsDebugAllowed(HANDLE hProcess, _DWORD *a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp-8h]
  int v12; // [rsp+A8h] [rbp+38h] BYREF
  int TokenInformation; // [rsp+B0h] [rbp+40h] BYREF
  int v14; // [rsp+B8h] [rbp+48h] BYREF

  ReturnLength = 0;
  TokenHandle = 0;
  hObject = 0;
  v14 = 0;
  v12 = 0;
  v11 = 0;
  memset(v10, 0, sizeof(v10));
  if ( a2 && hProcess )
  {
    *a2 = 0;
    v4 = 0;
    GetStateInfo(v10);
    if ( (DWORD1(v10[0]) & 0x80000004) == 0x80000000
      || (((DWORD1(v10[0]) & 0x8000001C) + 2147483628) & 0xFFFFFFF7) == 0
      || BYTE6(v11)
      || HIBYTE(v11) && (int)IsDeveloperModeEnabled(&v12) >= 0 && v12 )
    {
      goto LABEL_19;
    }
    TokenInformation = 0;
    if ( OpenProcessToken(hProcess, 0xEu, &TokenHandle)
      && GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
      && DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      if ( TokenInformation )
      {
        if ( !(unsigned int)VerifyClaim(hObject) )
        {
          v4 = CheckIfStoreApp(hProcess, &v14);
          if ( v4 >= 0 && (!v14 || BYTE5(v11)) )
LABEL_19:
            *a2 = 1;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029040  push    rbp
0x180029042  push    rbx
0x180029043  push    rsi
0x180029044  push    rdi
0x180029045  push    r14
0x180029047  mov     rbp, rsp
0x18002904a  sub     rsp, 70h
0x18002904e  xor     r14d, r14d
0x180029051  xor     eax, eax
0x180029053  mov     [rbp+var_40], r14d
0x180029057  xorps   xmm0, xmm0
0x18002905a  mov     [rbp+TokenHandle], r14
0x18002905e  mov     rdi, rdx
0x180029061  mov     [rbp+hObject], r14
0x180029065  mov     rsi, rcx
0x180029068  mov     [rbp+arg_18], r14d
0x18002906c  mov     [rbp+arg_8], r14d
0x180029070  mov     [rbp+var_8], rax
0x180029074  movups  [rbp+var_28], xmm0
0x180029078  movups  [rbp+var_18], xmm0
0x18002907c  test    rdx, rdx
0x18002907f  jz      loc_1800291B2
0x180029085  test    rcx, rcx
0x180029088  jz      loc_1800291B2
0x18002908e  lea     rcx, [rbp+var_28]
0x180029092  mov     [rdx], r14d
0x180029095  mov     ebx, r14d
0x180029098  call    GetStateInfo
0x18002909d  mov     ecx, dword ptr [rbp+var_28+4]
0x1800290a0  mov     eax, ecx
0x1800290a2  and     eax, 80000004h
0x1800290a7  cmp     eax, 80000000h
0x1800290ac  jz      loc_1800291AA
0x1800290b2  and     ecx, 8000001Ch
0x1800290b8  add     ecx, 7FFFFFECh
0x1800290be  test    ecx, 0FFFFFFF7h
0x1800290c4  jz      loc_1800291AA
0x1800290ca  cmp     byte ptr [rbp+var_8+6], r14b
0x1800290ce  jnz     loc_1800291AA
0x1800290d4  cmp     byte ptr [rbp+var_8+7], r14b
0x1800290d8  jz      short loc_1800290F2
0x1800290da  lea     rcx, [rbp+arg_8]
0x1800290de  call    cs:__imp_IsDeveloperModeEnabled
0x1800290e4  test    eax, eax
0x1800290e6  js      short loc_1800290F2
0x1800290e8  cmp     [rbp+arg_8], r14d
0x1800290ec  jnz     loc_1800291AA
0x1800290f2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800290f6  mov     [rbp+TokenInformation], r14d
0x1800290fa  mov     edx, 0Eh; DesiredAccess
0x1800290ff  mov     rcx, rsi; ProcessHandle
0x180029102  call    cs:__imp_OpenProcessToken
0x180029108  test    eax, eax
0x18002910a  jnz     short loc_18002912A
0x18002910c  call    cs:__imp_GetLastError
0x180029112  mov     ebx, eax
0x180029114  test    eax, eax
0x180029116  jle     loc_1800291B7
0x18002911c  movzx   ebx, ax
0x18002911f  or      ebx, 80070000h
0x180029125  jmp     loc_1800291B7
0x18002912a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002912e  lea     rax, [rbp+var_40]
0x180029132  mov     r9d, 4; TokenInformationLength
0x180029138  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002913d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180029141  lea     edx, [r9+19h]; TokenInformationClass
0x180029145  call    cs:__imp_GetTokenInformation
0x18002914b  test    eax, eax
0x18002914d  jz      short loc_18002910C
0x18002914f  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180029153  lea     rax, [rbp+hObject]
0x180029157  mov     r9d, 2; ImpersonationLevel
0x18002915d  mov     [rsp+70h+phNewToken], rax; phNewToken
0x180029162  xor     r8d, r8d; lpTokenAttributes
0x180029165  mov     dword ptr [rsp+70h+ReturnLength], r9d; TokenType
0x18002916a  mov     edx, 2000000h; dwDesiredAccess
0x18002916f  call    cs:__imp_DuplicateTokenEx
0x180029175  test    eax, eax
0x180029177  jz      short loc_18002910C
0x180029179  cmp     [rbp+TokenInformation], r14d
0x18002917d  jz      short loc_1800291B7
0x18002917f  mov     rcx, [rbp+hObject]; ClientToken
0x180029183  call    VerifyClaim
0x180029188  test    eax, eax
0x18002918a  jnz     short loc_1800291B7
0x18002918c  lea     rdx, [rbp+arg_18]; int *
0x180029190  mov     rcx, rsi; hProcess
0x180029193  call    ?CheckIfStoreApp@@YAJPEAXPEAH@Z; CheckIfStoreApp(void *,int *)
0x180029198  mov     ebx, eax
0x18002919a  test    eax, eax
0x18002919c  js      short loc_1800291B7
0x18002919e  cmp     [rbp+arg_18], r14d
0x1800291a2  jz      short loc_1800291AA
0x1800291a4  cmp     byte ptr [rbp+var_8+5], r14b
0x1800291a8  jz      short loc_1800291B7
0x1800291aa  mov     dword ptr [rdi], 1
0x1800291b0  jmp     short loc_1800291B7
0x1800291b2  mov     ebx, 80070057h
0x1800291b7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800291bb  test    rcx, rcx
0x1800291be  jz      short loc_1800291C6
0x1800291c0  call    cs:__imp_CloseHandle
0x1800291c6  mov     rcx, [rbp+hObject]; hObject
0x1800291ca  test    rcx, rcx
0x1800291cd  jz      short loc_1800291D5
0x1800291cf  call    cs:__imp_CloseHandle
0x1800291d5  mov     eax, ebx
0x1800291d7  add     rsp, 70h
0x1800291db  pop     r14
0x1800291dd  pop     rdi
0x1800291de  pop     rsi
0x1800291df  pop     rbx
0x1800291e0  pop     rbp
0x1800291e1  retn
```
