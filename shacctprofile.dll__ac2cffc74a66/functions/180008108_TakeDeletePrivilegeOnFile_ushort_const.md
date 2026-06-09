# _TakeDeletePrivilegeOnFile(ushort const *)

- ea: `0x180008108`
- end: `0x180008345`
- name: `?_TakeDeletePrivilegeOnFile@@YAJPEBG@Z`
- size: `573`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000855c`

## callees

- `0x180002230`
- `0x180007fc4`
- `0x180008108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000820d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000820d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000816d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000816d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000813f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000813f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000819c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000830c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000819c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000830c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800081c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008203`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800081c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008203`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000827d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000827d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800082c9`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800082c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800082b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800082b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008315`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081de`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000814f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000814f`

## pseudocode

```c
__int64 __fastcall _TakeDeletePrivilegeOnFile(LPCWSTR lpFileName)
{
  PSID *v2; // rdi
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // r15
  signed int v6; // ebx
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  PSID v10; // rdx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+60h] [rbp-20h]
  _TOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp-18h] BYREF

  TokenHandle = 0;
  v2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x400u, 0, CurrentProcessId);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  v6 = 0;
  if ( !OpenProcessToken(v4, 0x28u, &TokenHandle) )
  {
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
  }
  CloseHandle(v5);
  if ( v6 >= 0 )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( !TokenInformationLength )
    {
LABEL_20:
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_27:
      if ( v6 >= 0 )
        v6 = -2147467259;
      goto LABEL_29;
    }
    v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v8 = GetLastError();
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    if ( v6 >= 0 )
    {
      v6 = _SetDeletePrivilegeOnFile(lpFileName, *v2);
      if ( v6 < 0 )
      {
        NewState.PrivilegeCount = 1;
        NewState.Privileges[0].Luid = (LUID)9LL;
        NewState.Privileges[0].Attributes = 2;
        if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
        {
          v10 = *v2;
          v16 = 0;
          memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
          if ( SetSecurityDescriptorOwner(pSecurityDescriptor, v10, 0) )
          {
            if ( SetFileSecurityW(lpFileName, 1u, pSecurityDescriptor) )
            {
              v6 = _SetDeletePrivilegeOnFile(lpFileName, *v2);
              goto LABEL_29;
            }
          }
        }
        goto LABEL_20;
      }
    }
  }
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LocalFree(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008108  mov     [rsp-28h+arg_8], rbx
0x18000810d  mov     [rsp-28h+arg_10], rsi
0x180008112  push    rbp
0x180008113  push    rdi
0x180008114  push    r12
0x180008116  push    r14
0x180008118  push    r15
0x18000811a  mov     rbp, rsp
0x18000811d  sub     rsp, 80h
0x180008124  mov     rax, cs:__security_cookie
0x18000812b  xor     rax, rsp
0x18000812e  mov     [rbp+var_8], rax
0x180008132  mov     r12, rcx
0x180008135  mov     [rbp+TokenHandle], 0
0x18000813d  xor     edi, edi
0x18000813f  call    cs:__imp_GetCurrentProcessId
0x180008145  xor     edx, edx; bInheritHandle
0x180008147  mov     ecx, 400h; dwDesiredAccess
0x18000814c  mov     r8d, eax; dwProcessId
0x18000814f  call    cs:__imp_OpenProcess
0x180008155  mov     r15, rax
0x180008158  test    rax, rax
0x18000815b  jz      loc_1800082E2
0x180008161  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180008165  mov     rcx, rax; ProcessHandle
0x180008168  lea     edx, [rdi+28h]; DesiredAccess
0x18000816b  xor     ebx, ebx
0x18000816d  call    cs:__imp_OpenProcessToken
0x180008173  mov     esi, 80070000h
0x180008178  mov     r14d, 80004005h
0x18000817e  test    eax, eax
0x180008180  jnz     short loc_180008199
0x180008182  call    cs:__imp_GetLastError
0x180008188  mov     ebx, eax
0x18000818a  test    eax, eax
0x18000818c  jle     short loc_180008193
0x18000818e  movzx   ebx, ax
0x180008191  or      ebx, esi
0x180008193  test    ebx, ebx
0x180008195  cmovns  ebx, r14d
0x180008199  mov     rcx, r15; hObject
0x18000819c  call    cs:__imp_CloseHandle
0x1800081a2  test    ebx, ebx
0x1800081a4  js      loc_180008303
0x1800081aa  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800081ae  lea     rax, [rbp+TokenInformationLength]
0x1800081b2  xor     r9d, r9d; TokenInformationLength
0x1800081b5  mov     [rbp+TokenInformationLength], edi
0x1800081b8  xor     r8d, r8d; TokenInformation
0x1800081bb  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800081c0  lea     r15d, [r9+1]
0x1800081c4  mov     edx, r15d; TokenInformationClass
0x1800081c7  call    cs:__imp_GetTokenInformation
0x1800081cd  mov     eax, [rbp+TokenInformationLength]
0x1800081d0  test    eax, eax
0x1800081d2  jz      loc_180008287
0x1800081d8  mov     edx, eax; uBytes
0x1800081da  lea     ecx, [r15+3Fh]; uFlags
0x1800081de  call    cs:__imp_LocalAlloc
0x1800081e4  mov     rdi, rax
0x1800081e7  test    rax, rax
0x1800081ea  jz      short loc_180008226
0x1800081ec  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800081f0  lea     rax, [rbp+TokenInformationLength]
0x1800081f4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800081f8  mov     r8, rdi; TokenInformation
0x1800081fb  mov     edx, r15d; TokenInformationClass
0x1800081fe  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180008203  call    cs:__imp_GetTokenInformation
0x180008209  test    eax, eax
0x18000820b  jnz     short loc_18000822B
0x18000820d  call    cs:__imp_GetLastError
0x180008213  mov     ebx, eax
0x180008215  test    eax, eax
0x180008217  jle     short loc_18000821E
0x180008219  movzx   ebx, ax
0x18000821c  or      ebx, esi
0x18000821e  test    ebx, ebx
0x180008220  cmovns  ebx, r14d
0x180008224  jmp     short loc_18000822B
0x180008226  mov     ebx, 8007000Eh
0x18000822b  test    ebx, ebx
0x18000822d  js      loc_180008303
0x180008233  mov     rdx, [rdi]; Sid
0x180008236  mov     rcx, r12; lpFileName
0x180008239  call    ?_SetDeletePrivilegeOnFile@@YAJPEBGPEAX@Z; _SetDeletePrivilegeOnFile(ushort const *,void *)
0x18000823e  mov     ebx, eax
0x180008240  test    eax, eax
0x180008242  jns     loc_180008303
0x180008248  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000824c  lea     r8, [rbp+NewState]; NewState
0x180008250  mov     [rsp+80h+var_58], 0; ReturnLength
0x180008259  mov     r9d, 10h; BufferLength
0x18000825f  xor     edx, edx; DisableAllPrivileges
0x180008261  mov     [rsp+80h+ReturnLength], 0; PreviousState
0x18000826a  mov     [rbp+NewState.PrivilegeCount], r15d
0x18000826e  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 9
0x180008276  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000827d  call    cs:__imp_AdjustTokenPrivileges
0x180008283  test    eax, eax
0x180008285  jnz     short loc_18000829A
0x180008287  call    cs:__imp_GetLastError
0x18000828d  mov     ebx, eax
0x18000828f  test    eax, eax
0x180008291  jle     short loc_1800082FD
0x180008293  movzx   ebx, ax
0x180008296  or      ebx, esi
0x180008298  jmp     short loc_1800082FD
0x18000829a  mov     rdx, [rdi]; pOwner
0x18000829d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800082a1  xorps   xmm0, xmm0
0x1800082a4  xor     eax, eax
0x1800082a6  xor     r8d, r8d; bOwnerDefaulted
0x1800082a9  mov     [rbp+var_20], rax
0x1800082ad  movups  [rbp+pSecurityDescriptor], xmm0
0x1800082b1  movups  [rbp+var_30], xmm0
0x1800082b5  call    cs:__imp_SetSecurityDescriptorOwner
0x1800082bb  test    eax, eax
0x1800082bd  jz      short loc_180008287
0x1800082bf  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800082c3  mov     edx, r15d; SecurityInformation
0x1800082c6  mov     rcx, r12; lpFileName
0x1800082c9  call    cs:__imp_SetFileSecurityW
0x1800082cf  test    eax, eax
0x1800082d1  jz      short loc_180008287
0x1800082d3  mov     rdx, [rdi]; Sid
0x1800082d6  mov     rcx, r12; lpFileName
0x1800082d9  call    ?_SetDeletePrivilegeOnFile@@YAJPEBGPEAX@Z; _SetDeletePrivilegeOnFile(ushort const *,void *)
0x1800082de  mov     ebx, eax
0x1800082e0  jmp     short loc_180008303
0x1800082e2  call    cs:__imp_GetLastError
0x1800082e8  mov     ebx, eax
0x1800082ea  test    eax, eax
0x1800082ec  jle     short loc_1800082F7
0x1800082ee  movzx   ebx, ax
0x1800082f1  or      ebx, 80070000h
0x1800082f7  mov     r14d, 80004005h
0x1800082fd  test    ebx, ebx
0x1800082ff  cmovns  ebx, r14d
0x180008303  mov     rcx, [rbp+TokenHandle]; hObject
0x180008307  test    rcx, rcx
0x18000830a  jz      short loc_180008312
0x18000830c  call    cs:__imp_CloseHandle
0x180008312  mov     rcx, rdi; hMem
0x180008315  call    cs:__imp_LocalFree
0x18000831b  mov     eax, ebx
0x18000831d  mov     rcx, [rbp+var_8]
0x180008321  xor     rcx, rsp; StackCookie
0x180008324  call    __security_check_cookie
0x180008329  lea     r11, [rsp+80h+var_s0]
0x180008331  mov     rbx, [r11+38h]
0x180008335  mov     rsi, [r11+40h]
0x180008339  mov     rsp, r11
0x18000833c  pop     r15
0x18000833e  pop     r14
0x180008340  pop     r12
0x180008342  pop     rdi
0x180008343  pop     rbp
0x180008344  retn
```
