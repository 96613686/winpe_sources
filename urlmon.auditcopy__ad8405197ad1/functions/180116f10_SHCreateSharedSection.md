# SHCreateSharedSection

- ea: `0x180116f10`
- end: `0x180117028`
- name: `SHCreateSharedSection`
- size: `280`
- prototype: `signed int __fastcall(__int64, __int64, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180117754`

## callees

- `0x1800a4318`
- `0x180116ab4`
- `0x180116f10`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180116f52`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180116f67`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180116f52`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180116f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180116f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180116f93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180116f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180116f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fe2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180116fc5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180116fc5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180116f33`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180116fff`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180116f33`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180116fff`

## pseudocode

```c
signed int __fastcall SHCreateSharedSection(__int64 a1, __int64 a2, void *a3, _QWORD *a4)
{
  HANDLE v5; // rax
  __int64 v6; // rcx
  HANDLE NamedSection; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  HANDLE TargetHandle; // [rsp+60h] [rbp+18h] BYREF

  TargetHandle = a3;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
  if ( v5 )
    goto LABEL_7;
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) && (unsigned __int8)IEConfiguration_GetBool(536870916) )
    goto LABEL_6;
  NamedSection = CreateNamedSection(v6);
  if ( NamedSection )
  {
    CurrentProcess = GetCurrentProcess();
    v9 = GetCurrentProcess();
    DuplicateHandle(v9, NamedSection, CurrentProcess, &TargetHandle, 6u, 0, 1u);
LABEL_6:
    v5 = TargetHandle;
    goto LABEL_7;
  }
  if ( GetLastError() != 5 )
    goto LABEL_6;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
LABEL_7:
  *a4 = v5;
  if ( v5 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180116f10  mov     [rsp+arg_0], rbx
0x180116f15  mov     [rsp+arg_8], rsi
0x180116f1a  mov     [rsp+TargetHandle], r8
0x180116f1f  push    rdi
0x180116f20  sub     rsp, 40h
0x180116f24  xor     edx, edx; bInheritHandle
0x180116f26  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x180116f2d  mov     rsi, r9
0x180116f30  lea     ecx, [rdx+6]; dwDesiredAccess
0x180116f33  call    cs:__imp_OpenFileMappingW
0x180116f3a  nop     dword ptr [rax+rax+00h]
0x180116f3f  mov     [rsp+48h+TargetHandle], rax
0x180116f44  test    rax, rax
0x180116f47  jnz     loc_180116FD6
0x180116f4d  mov     ecx, 20000001h
0x180116f52  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180116f59  nop     dword ptr [rax+rax+00h]
0x180116f5e  test    al, al
0x180116f60  jnz     short loc_180116F77
0x180116f62  mov     ecx, 20000004h
0x180116f67  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180116f6e  nop     dword ptr [rax+rax+00h]
0x180116f73  test    al, al
0x180116f75  jnz     short loc_180116FD1
0x180116f77  call    _CreateNamedSection
0x180116f7c  mov     rdi, rax
0x180116f7f  test    rax, rax
0x180116f82  jz      short loc_180116FE2
0x180116f84  call    cs:__imp_GetCurrentProcess
0x180116f8b  nop     dword ptr [rax+rax+00h]
0x180116f90  mov     rbx, rax
0x180116f93  call    cs:__imp_GetCurrentProcess
0x180116f9a  nop     dword ptr [rax+rax+00h]
0x180116f9f  mov     [rsp+48h+dwOptions], 1; dwOptions
0x180116fa7  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180116fac  mov     rcx, rax; hSourceProcessHandle
0x180116faf  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180116fb7  mov     r8, rbx; hTargetProcessHandle
0x180116fba  mov     [rsp+48h+dwDesiredAccess], 6; dwDesiredAccess
0x180116fc2  mov     rdx, rdi; hSourceHandle
0x180116fc5  call    cs:__imp_DuplicateHandle
0x180116fcc  nop     dword ptr [rax+rax+00h]
0x180116fd1  mov     rax, [rsp+48h+TargetHandle]
0x180116fd6  mov     [rsi], rax
0x180116fd9  test    rax, rax
0x180116fdc  jz      short loc_180117012
0x180116fde  xor     eax, eax
0x180116fe0  jmp     short loc_180117017
0x180116fe2  call    cs:__imp_GetLastError
0x180116fe9  nop     dword ptr [rax+rax+00h]
0x180116fee  cmp     eax, 5
0x180116ff1  jnz     short loc_180116FD1
0x180116ff3  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x180116ffa  xor     edx, edx; bInheritHandle
0x180116ffc  lea     ecx, [rax+1]; dwDesiredAccess
0x180116fff  call    cs:__imp_OpenFileMappingW
0x180117006  nop     dword ptr [rax+rax+00h]
0x18011700b  mov     [rsp+48h+TargetHandle], rax
0x180117010  jmp     short loc_180116FD6
0x180117012  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180117017  mov     rbx, [rsp+48h+arg_0]
0x18011701c  mov     rsi, [rsp+48h+arg_8]
0x180117021  add     rsp, 40h
0x180117025  pop     rdi
0x180117026  retn
```
