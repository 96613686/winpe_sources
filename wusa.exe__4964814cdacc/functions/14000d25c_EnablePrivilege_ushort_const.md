# EnablePrivilege(ushort const *)

- ea: `0x14000d25c`
- end: `0x14000d42c`
- name: `?EnablePrivilege@@YAJPEBG@Z`
- size: `464`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140006fb8`
- `0x140008ff8`

## callees

- `0x14000d25c`
- `0x14000e280`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x14000d297`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14000d297`
- `ADVAPI32!OpenProcessToken` at `0x14000d300`
- `ADVAPI32!OpenProcessToken` at `0x14000d300`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000d359`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000d359`
- `KERNEL32!CloseHandle` at `0x14000d3c1`
- `KERNEL32!CloseHandle` at `0x14000d3c1`
- `KERNEL32!LocalFree` at `0x14000d40e`
- `KERNEL32!LocalFree` at `0x14000d40e`
- `KERNEL32!GetCurrentProcess` at `0x14000d2ee`
- `KERNEL32!GetCurrentProcess` at `0x14000d2ee`
- `KERNEL32!GetLastError` at `0x14000d2a8`
- `KERNEL32!GetLastError` at `0x14000d30a`
- `KERNEL32!GetLastError` at `0x14000d363`
- `KERNEL32!GetLastError` at `0x14000d392`
- `KERNEL32!GetLastError` at `0x14000d2a8`
- `KERNEL32!GetLastError` at `0x14000d30a`
- `KERNEL32!GetLastError` at `0x14000d363`
- `KERNEL32!GetLastError` at `0x14000d392`

## string_xrefs

- `0x14000d2bf`: `Failed: LookupPrivilegeValue()`
- `0x14000d29d`: `EnablePrivilege`
- `0x14000d321`: `Failed: OpenProcessToken()`
- `0x14000d37a`: `Failed: AdjustTokenPrivileges()`
- `0x14000d3a4`: `Failed: AdjustTokenPrivileges(); not all token privileges were assigned`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(LPCWSTR lpName)
{
  signed int v1; // eax
  signed int v2; // ebx
  const char *v3; // r8
  __int64 v4; // rdx
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  signed int LastError; // eax
  HLOCAL v8; // rdi
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-20h] BYREF

  Luid = 0;
  TokenHandle = 0;
  NewState = 0;
  if ( LookupPrivilegeValueW(0, lpName, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
      {
        v2 = 0;
        if ( GetLastError() != 1300 )
          goto LABEL_22;
        v2 = -2147023596;
        v3 = "Failed: AdjustTokenPrivileges(); not all token privileges were assigned";
        v4 = 631;
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        v3 = "Failed: AdjustTokenPrivileges()";
        v4 = 626;
        if ( v2 >= 0 )
          v2 = -2147467259;
      }
    }
    else
    {
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      v3 = "Failed: OpenProcessToken()";
      v4 = 615;
      if ( v2 >= 0 )
        v2 = -2147467259;
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    v3 = "Failed: LookupPrivilegeValue()";
    v4 = 603;
    if ( v2 >= 0 )
      v2 = -2147467259;
  }
  WusaLogDebugEventA(L"EnablePrivilege", v4, v3);
LABEL_22:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v2 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v2, (unsigned __int16 **)&hMem);
    v8 = hMem;
    WusaLogDebugEventA(L"EnablePrivilege", 638, "Exit with error code 0X%x (%ls)", v2, (const wchar_t *)hMem);
    if ( v8 )
      LocalFree(v8);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000d25c  push    rbp
0x14000d25e  push    rbx
0x14000d25f  push    rdi
0x14000d260  push    r14
0x14000d262  mov     rbp, rsp
0x14000d265  sub     rsp, 68h
0x14000d269  mov     rax, cs:__security_cookie
0x14000d270  xor     rax, rsp
0x14000d273  mov     [rbp+var_10], rax
0x14000d277  xorps   xmm0, xmm0
0x14000d27a  mov     qword ptr [rbp+Luid.LowPart], 0
0x14000d282  mov     rdx, rcx; lpName
0x14000d285  mov     [rbp+TokenHandle], 0
0x14000d28d  xor     ecx, ecx; lpSystemName
0x14000d28f  lea     r8, [rbp+Luid]; lpLuid
0x14000d293  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x14000d297  call    cs:__imp_LookupPrivilegeValueW
0x14000d29d  lea     r14, aEnableprivileg; "EnablePrivilege"
0x14000d2a4  test    eax, eax
0x14000d2a6  jnz     short loc_14000D2D8
0x14000d2a8  call    cs:__imp_GetLastError
0x14000d2ae  mov     ebx, eax
0x14000d2b0  test    eax, eax
0x14000d2b2  jle     short loc_14000D2BD
0x14000d2b4  movzx   ebx, ax
0x14000d2b7  or      ebx, 80070000h
0x14000d2bd  test    ebx, ebx
0x14000d2bf  lea     r8, aFailedLookuppr; "Failed: LookupPrivilegeValue()"
0x14000d2c6  mov     eax, 80004005h
0x14000d2cb  mov     edx, 25Bh
0x14000d2d0  cmovns  ebx, eax
0x14000d2d3  jmp     loc_14000D3B0
0x14000d2d8  mov     rax, qword ptr [rbp+Luid.LowPart]
0x14000d2dc  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x14000d2e0  mov     [rbp+NewState.PrivilegeCount], 1
0x14000d2e7  mov     [rbp+NewState.Privileges.Attributes], 2
0x14000d2ee  call    cs:__imp_GetCurrentProcess
0x14000d2f4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000d2f8  mov     edx, 28h ; '('; DesiredAccess
0x14000d2fd  mov     rcx, rax; ProcessHandle
0x14000d300  call    cs:__imp_OpenProcessToken
0x14000d306  test    eax, eax
0x14000d308  jnz     short loc_14000D337
0x14000d30a  call    cs:__imp_GetLastError
0x14000d310  mov     ebx, eax
0x14000d312  test    eax, eax
0x14000d314  jle     short loc_14000D31F
0x14000d316  movzx   ebx, ax
0x14000d319  or      ebx, 80070000h
0x14000d31f  test    ebx, ebx
0x14000d321  lea     r8, aFailedOpenproc; "Failed: OpenProcessToken()"
0x14000d328  mov     eax, 80004005h
0x14000d32d  mov     edx, 267h
0x14000d332  cmovns  ebx, eax
0x14000d335  jmp     short loc_14000D3B0
0x14000d337  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000d33b  lea     r8, [rbp+NewState]; NewState
0x14000d33f  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x14000d348  mov     r9d, 10h; BufferLength
0x14000d34e  xor     edx, edx; DisableAllPrivileges
0x14000d350  mov     [rsp+68h+PreviousState], 0; PreviousState
0x14000d359  call    cs:__imp_AdjustTokenPrivileges
0x14000d35f  test    eax, eax
0x14000d361  jnz     short loc_14000D390
0x14000d363  call    cs:__imp_GetLastError
0x14000d369  mov     ebx, eax
0x14000d36b  test    eax, eax
0x14000d36d  jle     short loc_14000D378
0x14000d36f  movzx   ebx, ax
0x14000d372  or      ebx, 80070000h
0x14000d378  test    ebx, ebx
0x14000d37a  lea     r8, aFailedAdjustto; "Failed: AdjustTokenPrivileges()"
0x14000d381  mov     eax, 80004005h
0x14000d386  mov     edx, 272h
0x14000d38b  cmovns  ebx, eax
0x14000d38e  jmp     short loc_14000D3B0
0x14000d390  xor     ebx, ebx
0x14000d392  call    cs:__imp_GetLastError
0x14000d398  cmp     eax, 514h
0x14000d39d  jnz     short loc_14000D3B8
0x14000d39f  mov     ebx, 80070514h
0x14000d3a4  lea     r8, aFailedAdjustto_0; "Failed: AdjustTokenPrivileges(); not al"...
0x14000d3ab  mov     edx, 277h
0x14000d3b0  mov     rcx, r14
0x14000d3b3  call    WusaLogDebugEventA
0x14000d3b8  mov     rcx, [rbp+TokenHandle]; hObject
0x14000d3bc  test    rcx, rcx
0x14000d3bf  jz      short loc_14000D3CF
0x14000d3c1  call    cs:__imp_CloseHandle
0x14000d3c7  mov     [rbp+TokenHandle], 0
0x14000d3cf  test    ebx, ebx
0x14000d3d1  jns     short loc_14000D414
0x14000d3d3  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000d3d7  mov     [rbp+hMem], 0
0x14000d3df  mov     ecx, ebx; dwMessageId
0x14000d3e1  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000d3e6  mov     rdi, [rbp+hMem]
0x14000d3ea  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000d3f1  mov     r9d, ebx
0x14000d3f4  mov     [rsp+68h+PreviousState], rdi
0x14000d3f9  mov     edx, 27Eh
0x14000d3fe  mov     rcx, r14
0x14000d401  call    WusaLogDebugEventA
0x14000d406  test    rdi, rdi
0x14000d409  jz      short loc_14000D414
0x14000d40b  mov     rcx, rdi; hMem
0x14000d40e  call    cs:__imp_LocalFree
0x14000d414  mov     eax, ebx
0x14000d416  mov     rcx, [rbp+var_10]
0x14000d41a  xor     rcx, rsp; StackCookie
0x14000d41d  call    __security_check_cookie
0x14000d422  add     rsp, 68h
0x14000d426  pop     r14
0x14000d428  pop     rdi
0x14000d429  pop     rbx
0x14000d42a  pop     rbp
0x14000d42b  retn
```
