# DeletePathEx

- ea: `0x18003eddc`
- end: `0x18003f06c`
- name: `DeletePathEx`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800185f0`

## callees

- `0x18003d150`
- `0x18003dd2c`
- `0x18003eba8`
- `0x18003eddc`
- `0x180040cb4`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18003ee4f`
- `KERNEL32!GetCurrentProcess` at `0x18003ee98`
- `KERNEL32!GetCurrentProcess` at `0x18003ef95`
- `KERNEL32!GetCurrentProcess` at `0x18003efd9`
- `KERNEL32!GetCurrentProcess` at `0x18003ee4f`
- `KERNEL32!GetCurrentProcess` at `0x18003ee98`
- `KERNEL32!GetCurrentProcess` at `0x18003ef95`
- `KERNEL32!GetCurrentProcess` at `0x18003efd9`
- `KERNEL32!Sleep` at `0x18003ef45`
- `KERNEL32!Sleep` at `0x18003ef45`
- `KERNEL32!GetLastError` at `0x18003eef3`
- `KERNEL32!GetLastError` at `0x18003ef15`
- `KERNEL32!GetLastError` at `0x18003eef3`
- `KERNEL32!GetLastError` at `0x18003ef15`
- `KERNEL32!SetLastError` at `0x18003f013`
- `KERNEL32!SetLastError` at `0x18003f040`
- `KERNEL32!SetLastError` at `0x18003f013`
- `KERNEL32!SetLastError` at `0x18003f040`
- `ADVAPI32!OpenProcessToken` at `0x18003ee67`
- `ADVAPI32!OpenProcessToken` at `0x18003eeb0`
- `ADVAPI32!OpenProcessToken` at `0x18003efad`
- `ADVAPI32!OpenProcessToken` at `0x18003eff0`
- `ADVAPI32!OpenProcessToken` at `0x18003ee67`
- `ADVAPI32!OpenProcessToken` at `0x18003eeb0`
- `ADVAPI32!OpenProcessToken` at `0x18003efad`
- `ADVAPI32!OpenProcessToken` at `0x18003eff0`

## string_xrefs

- `0x18003f023`: `DeletePath: Cannot delete <null>.`
- `0x18003ee2f`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x18003ef24`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x18003ef6a`: `DeletePath: Failed to obliterate [%s] after %d tries; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall DeletePathEx(_WORD *a1)
{
  unsigned int v2; // r13d
  DWORD v3; // edi
  int v4; // r14d
  int v5; // r15d
  DWORD v6; // ecx
  HANDLE CurrentProcess; // rax
  int v8; // eax
  int v9; // r12d
  HANDLE v10; // rax
  int v11; // eax
  unsigned int v12; // esi
  DWORD LastError; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  __int64 v17; // [rsp+20h] [rbp-30h]
  int v18; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  _DWORD v20[4]; // [rsp+40h] [rbp-10h] BYREF

  v18 = 0;
  v2 = 0;
  v20[0] = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !a1 || !*a1 )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Cannot delete <null>.");
    v6 = 87;
    goto LABEL_28;
  }
  if ( !(unsigned int)DirectoryExists() )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: [%s] doesn't exist as a directory; nothing to delete.", a1);
    v6 = 3;
LABEL_28:
    SetLastError(v6);
    return 0;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v8 = EnablePrivilegeEx2(17, 1, &v18, &TokenHandle);
    v4 = v18;
    v9 = v8;
  }
  else
  {
    v9 = 0;
  }
  v10 = GetCurrentProcess();
  if ( OpenProcessToken(v10, 0x28u, &TokenHandle) )
  {
    v11 = EnablePrivilegeEx2(18, 1, v20, &TokenHandle);
    v5 = v20[0];
    v18 = v11;
  }
  else
  {
    v18 = 0;
  }
  v12 = DeletePathEngine(a1);
  if ( !v12 )
  {
    do
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError == 1223 )
        break;
      if ( LastError == -2147023673 )
        break;
      if ( v2 >= 3 )
        break;
      LODWORD(v17) = GetLastError();
      LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...", a1, v17);
      Sleep(0x3E8u);
      ++v2;
      v12 = DeletePathEngine(a1);
    }
    while ( !v12 );
    if ( !v12 )
    {
      LODWORD(v17) = v2;
      LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Failed to obliterate [%s] after %d tries; GLE = 0x%x", a1, v17, v3);
    }
  }
  if ( v9 == 1 && !v4 )
  {
    v14 = GetCurrentProcess();
    if ( OpenProcessToken(v14, 0x28u, &TokenHandle) )
      EnablePrivilegeEx2(17, 0, 0, &TokenHandle);
  }
  if ( v18 == 1 && !v5 )
  {
    v15 = GetCurrentProcess();
    if ( OpenProcessToken(v15, 0x28u, &TokenHandle) )
      EnablePrivilegeEx2(18, 0, 0, &TokenHandle);
  }
  SetLastError(v3);
  return v12;
}

```

## disassembly

```asm
0x18003eddc  mov     [rsp-28h+arg_8], rbx
0x18003ede1  mov     [rsp-28h+arg_10], rsi
0x18003ede6  mov     [rsp-28h+arg_18], rdi
0x18003edeb  push    rbp
0x18003edec  push    r12
0x18003edee  push    r13
0x18003edf0  push    r14
0x18003edf2  push    r15
0x18003edf4  mov     rbp, rsp
0x18003edf7  sub     rsp, 50h
0x18003edfb  xor     esi, esi
0x18003edfd  mov     rbx, rcx
0x18003ee00  mov     [rbp+var_20], esi
0x18003ee03  mov     r13d, esi
0x18003ee06  mov     [rbp+var_10], esi
0x18003ee09  mov     edi, esi
0x18003ee0b  mov     r14d, esi
0x18003ee0e  mov     r15d, esi
0x18003ee11  test    rcx, rcx
0x18003ee14  jz      loc_18003F023
0x18003ee1a  cmp     si, [rcx]
0x18003ee1d  jz      loc_18003F023
0x18003ee23  call    DirectoryExists
0x18003ee28  test    eax, eax
0x18003ee2a  jnz     short loc_18003EE4F
0x18003ee2c  mov     r9, rbx
0x18003ee2f  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18003ee36  mov     edx, 2000000h
0x18003ee3b  lea     rcx, g_WdsLibLog
0x18003ee42  call    LibLog
0x18003ee47  lea     ecx, [rsi+3]
0x18003ee4a  jmp     loc_18003F040
0x18003ee4f  call    cs:__imp_GetCurrentProcess
0x18003ee56  nop     dword ptr [rax+rax+00h]
0x18003ee5b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003ee5f  mov     edx, 28h ; '('; DesiredAccess
0x18003ee64  mov     rcx, rax; ProcessHandle
0x18003ee67  call    cs:__imp_OpenProcessToken
0x18003ee6e  nop     dword ptr [rax+rax+00h]
0x18003ee73  test    eax, eax
0x18003ee75  jz      short loc_18003EE95
0x18003ee77  mov     edx, 1
0x18003ee7c  lea     r9, [rbp+TokenHandle]
0x18003ee80  lea     r8, [rbp+var_20]
0x18003ee84  lea     ecx, [rdx+10h]
0x18003ee87  call    EnablePrivilegeEx2
0x18003ee8c  mov     r14d, [rbp+var_20]
0x18003ee90  mov     r12d, eax
0x18003ee93  jmp     short loc_18003EE98
0x18003ee95  mov     r12d, esi
0x18003ee98  call    cs:__imp_GetCurrentProcess
0x18003ee9f  nop     dword ptr [rax+rax+00h]
0x18003eea4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003eea8  mov     edx, 28h ; '('; DesiredAccess
0x18003eead  mov     rcx, rax; ProcessHandle
0x18003eeb0  call    cs:__imp_OpenProcessToken
0x18003eeb7  nop     dword ptr [rax+rax+00h]
0x18003eebc  test    eax, eax
0x18003eebe  jz      short loc_18003EEDE
0x18003eec0  mov     edx, 1
0x18003eec5  lea     r9, [rbp+TokenHandle]
0x18003eec9  lea     r8, [rbp+var_10]
0x18003eecd  lea     ecx, [rdx+11h]
0x18003eed0  call    EnablePrivilegeEx2
0x18003eed5  mov     r15d, [rbp+var_10]
0x18003eed9  mov     [rbp+var_20], eax
0x18003eedc  jmp     short loc_18003EEE1
0x18003eede  mov     [rbp+var_20], esi
0x18003eee1  mov     rcx, rbx
0x18003eee4  call    DeletePathEngine
0x18003eee9  mov     esi, eax
0x18003eeeb  test    eax, eax
0x18003eeed  jnz     loc_18003EF8A
0x18003eef3  call    cs:__imp_GetLastError
0x18003eefa  nop     dword ptr [rax+rax+00h]
0x18003eeff  mov     edi, eax
0x18003ef01  cmp     eax, 4C7h
0x18003ef06  jz      short loc_18003EF62
0x18003ef08  cmp     eax, 800704C7h
0x18003ef0d  jz      short loc_18003EF62
0x18003ef0f  cmp     r13d, 3
0x18003ef13  jnb     short loc_18003EF62
0x18003ef15  call    cs:__imp_GetLastError
0x18003ef1c  nop     dword ptr [rax+rax+00h]
0x18003ef21  mov     r9, rbx
0x18003ef24  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] ("...
0x18003ef2b  lea     rcx, g_WdsLibLog
0x18003ef32  mov     dword ptr [rsp+50h+var_30], eax
0x18003ef36  mov     edx, 4000000h
0x18003ef3b  call    LibLog
0x18003ef40  mov     ecx, 3E8h; dwMilliseconds
0x18003ef45  call    cs:__imp_Sleep
0x18003ef4c  nop     dword ptr [rax+rax+00h]
0x18003ef51  mov     rcx, rbx
0x18003ef54  inc     r13d
0x18003ef57  call    DeletePathEngine
0x18003ef5c  mov     esi, eax
0x18003ef5e  test    eax, eax
0x18003ef60  jz      short loc_18003EEF3
0x18003ef62  test    esi, esi
0x18003ef64  jnz     short loc_18003EF8A
0x18003ef66  mov     [rsp+50h+var_28], edi
0x18003ef6a  lea     r8, aDeletepathFail_0; "DeletePath: Failed to obliterate [%s] a"...
0x18003ef71  mov     r9, rbx
0x18003ef74  mov     dword ptr [rsp+50h+var_30], r13d
0x18003ef79  mov     edx, 2000000h
0x18003ef7e  lea     rcx, g_WdsLibLog
0x18003ef85  call    LibLog
0x18003ef8a  cmp     r12d, 1
0x18003ef8e  jnz     short loc_18003EFCE
0x18003ef90  test    r14d, r14d
0x18003ef93  jnz     short loc_18003EFCE
0x18003ef95  call    cs:__imp_GetCurrentProcess
0x18003ef9c  nop     dword ptr [rax+rax+00h]
0x18003efa1  mov     rcx, rax; ProcessHandle
0x18003efa4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003efa8  lea     edx, [r12+27h]; DesiredAccess
0x18003efad  call    cs:__imp_OpenProcessToken
0x18003efb4  nop     dword ptr [rax+rax+00h]
0x18003efb9  test    eax, eax
0x18003efbb  jz      short loc_18003EFCE
0x18003efbd  xor     edx, edx
0x18003efbf  lea     r9, [rbp+TokenHandle]
0x18003efc3  xor     r8d, r8d
0x18003efc6  lea     ecx, [rdx+11h]
0x18003efc9  call    EnablePrivilegeEx2
0x18003efce  cmp     [rbp+var_20], 1
0x18003efd2  jnz     short loc_18003F011
0x18003efd4  test    r15d, r15d
0x18003efd7  jnz     short loc_18003F011
0x18003efd9  call    cs:__imp_GetCurrentProcess
0x18003efe0  nop     dword ptr [rax+rax+00h]
0x18003efe5  mov     rcx, rax; ProcessHandle
0x18003efe8  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003efec  lea     edx, [r15+28h]; DesiredAccess
0x18003eff0  call    cs:__imp_OpenProcessToken
0x18003eff7  nop     dword ptr [rax+rax+00h]
0x18003effc  test    eax, eax
0x18003effe  jz      short loc_18003F011
0x18003f000  xor     edx, edx
0x18003f002  lea     r9, [rbp+TokenHandle]
0x18003f006  xor     r8d, r8d
0x18003f009  lea     ecx, [rdx+12h]
0x18003f00c  call    EnablePrivilegeEx2
0x18003f011  mov     ecx, edi; dwErrCode
0x18003f013  call    cs:__imp_SetLastError
0x18003f01a  nop     dword ptr [rax+rax+00h]
0x18003f01f  mov     eax, esi
0x18003f021  jmp     short loc_18003F04E
0x18003f023  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x18003f02a  mov     edx, 2000000h
0x18003f02f  lea     rcx, g_WdsLibLog
0x18003f036  call    LibLog
0x18003f03b  mov     ecx, 57h ; 'W'; dwErrCode
0x18003f040  call    cs:__imp_SetLastError
0x18003f047  nop     dword ptr [rax+rax+00h]
0x18003f04c  xor     eax, eax
0x18003f04e  lea     r11, [rsp+50h+var_s0]
0x18003f053  mov     rbx, [r11+38h]
0x18003f057  mov     rsi, [r11+40h]
0x18003f05b  mov     rdi, [r11+48h]
0x18003f05f  mov     rsp, r11
0x18003f062  pop     r15
0x18003f064  pop     r14
0x18003f066  pop     r13
0x18003f068  pop     r12
0x18003f06a  pop     rbp
0x18003f06b  retn
```
