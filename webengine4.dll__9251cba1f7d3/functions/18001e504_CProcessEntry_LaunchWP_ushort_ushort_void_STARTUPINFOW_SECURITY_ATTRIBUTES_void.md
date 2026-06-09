# CProcessEntry::LaunchWP(ushort *,ushort *,void *,_STARTUPINFOW *,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x18001e504`
- end: `0x18001e672`
- name: `?LaunchWP@CProcessEntry@@AEAAJPEAG0PEAXPEAU_STARTUPINFOW@@PEAU_SECURITY_ATTRIBUTES@@1@Z`
- size: `366`
- prototype: `__int64 __fastcall(CProcessEntry *this, unsigned __int16 *, unsigned __int16 *, void *, struct _STARTUPINFOW *lpStartupInfo, struct _SECURITY_ATTRIBUTES *lpProcessAttributes, void *lpEnvironment)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001dc88`

## callees

- `0x18001e504`
- `0x18004d350`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001e5d5`
- `KERNEL32!CloseHandle` at `0x18001e5d5`
- `KERNEL32!WaitForSingleObject` at `0x18001e639`
- `KERNEL32!WaitForSingleObject` at `0x18001e639`
- `KERNEL32!WaitForMultipleObjects` at `0x18001e602`
- `KERNEL32!WaitForMultipleObjects` at `0x18001e602`
- `KERNEL32!GetExitCodeProcess` at `0x18001e61a`
- `KERNEL32!GetExitCodeProcess` at `0x18001e61a`
- `KERNEL32!CreateProcessW` at `0x18001e587`
- `KERNEL32!CreateProcessW` at `0x18001e587`
- `ADVAPI32!CreateProcessAsUserW` at `0x18001e5c9`
- `ADVAPI32!CreateProcessAsUserW` at `0x18001e5c9`

## pseudocode

```c
__int64 __fastcall CProcessEntry::LaunchWP(
        CProcessEntry *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4,
        struct _STARTUPINFOW *lpStartupInfo,
        struct _SECURITY_ATTRIBUTES *lpProcessAttributes,
        void *lpEnvironment)
{
  DWORD dwCreationFlags; // ecx
  BOOL v9; // eax
  __int64 result; // rax
  HANDLE hProcess; // rcx
  void *v12; // rax
  DWORD v13; // eax
  HANDLE Handles[2]; // [rsp+68h] [rbp+Fh] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp+1Fh] BYREF
  DWORD ExitCode; // [rsp+C0h] [rbp+67h] BYREF

  ExitCode = 0;
  dwCreationFlags = lpEnvironment != 0 ? 134218752 : 0x8000000;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a4 )
    v9 = CreateProcessAsUserW(
           a4,
           a2,
           a3,
           lpProcessAttributes,
           lpProcessAttributes,
           0,
           dwCreationFlags,
           lpEnvironment,
           0,
           lpStartupInfo,
           &ProcessInformation);
  else
    v9 = CreateProcessW(a2, a3, 0, 0, 0, dwCreationFlags, lpEnvironment, 0, lpStartupInfo, &ProcessInformation);
  if ( !v9 )
    return GetLastWin32Error();
  CloseHandle(ProcessInformation.hThread);
  hProcess = ProcessInformation.hProcess;
  v12 = (void *)*((_QWORD *)this + 24);
  *(_QWORD *)this = ProcessInformation.hProcess;
  Handles[1] = hProcess;
  Handles[0] = v12;
  v13 = WaitForMultipleObjects(2u, Handles, 0, 0x493E0u);
  if ( v13 )
  {
    if ( v13 == 258 )
      return 2147943860LL;
    if ( !GetExitCodeProcess(*(HANDLE *)this, &ExitCode) )
      return 2147500037LL;
    result = ExitCode;
    if ( (ExitCode & 0x80000000) == 0 )
      return 2147500037LL;
  }
  else
  {
    if ( WaitForSingleObject(*(HANDLE *)this, 0) != 258 )
      return 2147500037LL;
    *((_DWORD *)this + 88) = ProcessInformation.dwProcessId;
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x18001e504  mov     rax, rsp
0x18001e507  mov     [rax+8], rbx
0x18001e50b  mov     [rax+10h], rsi
0x18001e50f  mov     [rax+18h], rdi
0x18001e513  push    rbp
0x18001e514  lea     rbp, [rax-47h]
0x18001e518  sub     rsp, 90h
0x18001e51f  and     [rbp+3Fh+ExitCode], 0
0x18001e523  mov     rbx, rcx
0x18001e526  mov     r10, [rbp+3Fh+arg_30]
0x18001e52a  xorps   xmm0, xmm0
0x18001e52d  mov     rax, r10
0x18001e530  mov     r11, r9
0x18001e533  neg     rax
0x18001e536  mov     rdi, r8
0x18001e539  mov     rsi, rdx
0x18001e53c  sbb     ecx, ecx
0x18001e53e  xor     eax, eax
0x18001e540  and     ecx, 400h
0x18001e546  mov     qword ptr [rbp+3Fh+ProcessInformation.dwProcessId], rax
0x18001e54a  add     ecx, 8000000h
0x18001e550  lea     rax, [rbp+3Fh+ProcessInformation]
0x18001e554  movups  xmmword ptr [rbp+3Fh+ProcessInformation.hProcess], xmm0
0x18001e558  test    r9, r9
0x18001e55b  jnz     short loc_18001E59B
0x18001e55d  mov     [rsp+90h+lpProcessInformation], rax; lpProcessInformation
0x18001e562  xor     r8d, r8d; lpProcessAttributes
0x18001e565  mov     rax, [rbp+3Fh+arg_20]
0x18001e569  mov     rdx, rdi; lpCommandLine
0x18001e56c  mov     [rsp+90h+lpStartupInfo], rax; lpStartupInfo
0x18001e571  and     [rsp+90h+var_58], r9
0x18001e576  mov     [rsp+90h+lpEnvironment], r10; lpEnvironment
0x18001e57b  mov     [rsp+90h+dwCreationFlags], ecx; dwCreationFlags
0x18001e57f  mov     rcx, rsi; lpApplicationName
0x18001e582  and     dword ptr [rsp+90h+lpThreadAttributes], r9d
0x18001e587  call    cs:__imp_CreateProcessW
0x18001e58d  test    eax, eax
0x18001e58f  jnz     short loc_18001E5D1
0x18001e591  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001e596  jmp     loc_18001E659
0x18001e59b  mov     r9, [rbp+3Fh+lpProcessAttributes]; lpProcessAttributes
0x18001e59f  mov     [rsp+90h+var_40], rax; lpProcessInformation
0x18001e5a4  mov     rax, [rbp+3Fh+arg_20]
0x18001e5a8  mov     [rsp+90h+lpProcessInformation], rax; lpStartupInfo
0x18001e5ad  and     [rsp+90h+lpStartupInfo], 0
0x18001e5b3  mov     [rsp+90h+var_58], r10; lpEnvironment
0x18001e5b8  mov     dword ptr [rsp+90h+lpEnvironment], ecx; dwCreationFlags
0x18001e5bc  mov     rcx, r11; hToken
0x18001e5bf  and     [rsp+90h+dwCreationFlags], 0
0x18001e5c4  mov     [rsp+90h+lpThreadAttributes], r9; lpThreadAttributes
0x18001e5c9  call    cs:__imp_CreateProcessAsUserW
0x18001e5cf  jmp     short loc_18001E58D
0x18001e5d1  mov     rcx, [rbp+3Fh+ProcessInformation.hThread]; hObject
0x18001e5d5  call    cs:__imp_CloseHandle
0x18001e5db  mov     rcx, [rbp+3Fh+ProcessInformation.hProcess]
0x18001e5df  lea     rdx, [rbp+3Fh+Handles]; lpHandles
0x18001e5e3  mov     rax, [rbx+0C0h]
0x18001e5ea  xor     r8d, r8d; bWaitAll
0x18001e5ed  mov     [rbx], rcx
0x18001e5f0  mov     r9d, 493E0h; dwMilliseconds
0x18001e5f6  mov     [rbp+3Fh+var_28], rcx
0x18001e5fa  mov     [rbp+3Fh+Handles], rax
0x18001e5fe  lea     ecx, [r8+2]; nCount
0x18001e602  call    cs:__imp_WaitForMultipleObjects
0x18001e608  test    eax, eax
0x18001e60a  jz      short loc_18001E634
0x18001e60c  cmp     eax, 102h
0x18001e611  jz      short loc_18001E62D
0x18001e613  mov     rcx, [rbx]; hProcess
0x18001e616  lea     rdx, [rbp+3Fh+ExitCode]; lpExitCode
0x18001e61a  call    cs:__imp_GetExitCodeProcess
0x18001e620  test    eax, eax
0x18001e622  jz      short loc_18001E646
0x18001e624  mov     eax, [rbp+3Fh+ExitCode]
0x18001e627  test    eax, eax
0x18001e629  js      short loc_18001E659
0x18001e62b  jmp     short loc_18001E646
0x18001e62d  mov     eax, 800705B4h
0x18001e632  jmp     short loc_18001E659
0x18001e634  mov     rcx, [rbx]; hHandle
0x18001e637  xor     edx, edx; dwMilliseconds
0x18001e639  call    cs:__imp_WaitForSingleObject
0x18001e63f  cmp     eax, 102h
0x18001e644  jz      short loc_18001E64D
0x18001e646  mov     eax, 80004005h
0x18001e64b  jmp     short loc_18001E659
0x18001e64d  mov     eax, [rbp+3Fh+ProcessInformation.dwProcessId]
0x18001e650  mov     [rbx+160h], eax
0x18001e656  mov     eax, [rbp+3Fh+ExitCode]
0x18001e659  lea     r11, [rsp+90h+var_s0]
0x18001e661  mov     rbx, [r11+10h]
0x18001e665  mov     rsi, [r11+18h]
0x18001e669  mov     rdi, [r11+20h]
0x18001e66d  mov     rsp, r11
0x18001e670  pop     rbp
0x18001e671  retn
```
