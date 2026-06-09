# PfsUpdateOldPagesInWorkingSet

- ea: `0x18003c46c`
- end: `0x18003c52c`
- name: `PfsUpdateOldPagesInWorkingSet`
- size: `192`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18003c250`

## callees

- `0x18003c46c`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x18003c4f1`
- `ntdll!NtSetSystemInformation` at `0x18003c4f1`
- `ntdll!RtlNtStatusToDosError` at `0x18003c518`
- `ntdll!RtlNtStatusToDosError` at `0x18003c518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c522`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003c49c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003c49c`

## pseudocode

```c
__int64 __fastcall PfsUpdateOldPagesInWorkingSet(DWORD dwProcessId)
{
  ULONG v1; // ebx
  HANDLE v2; // rdi
  int v3; // eax
  __int128 v5; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  __int128 SystemInformation; // [rsp+38h] [rbp-28h] BYREF
  __int128 v8; // [rsp+48h] [rbp-18h]

  LODWORD(v6) = 0;
  SystemInformation = 0;
  v8 = 0;
  v5 = 0;
  v1 = 0;
  v2 = OpenProcess(0x2000u, 0, dwProcessId);
  if ( v2 )
  {
    *((_QWORD *)&SystemInformation + 1) = 26;
    *(_QWORD *)&v8 = &v5;
    *((_QWORD *)&v8 + 1) = 24;
    *(_QWORD *)&SystemInformation = 0x6B7568430000002DLL;
    *(_QWORD *)&v5 = 3;
    v6 = 24;
    *((_QWORD *)&v5 + 1) = v2;
    v3 = NtSetSystemInformation(SystemSuperfetchInformation, &SystemInformation, 0x20u);
    if ( v3 < 0 )
      v1 = RtlNtStatusToDosError(v3);
    CloseHandle(v2);
  }
  else
  {
    return GetLastError();
  }
  return v1;
}

```

## disassembly

```asm
0x18003c46c  mov     [rsp-8+arg_0], rbx
0x18003c471  mov     [rsp-8+arg_8], rdi
0x18003c476  push    rbp
0x18003c477  mov     rbp, rsp
0x18003c47a  sub     rsp, 60h
0x18003c47e  xorps   xmm0, xmm0
0x18003c481  xor     eax, eax
0x18003c483  mov     r8d, ecx; dwProcessId
0x18003c486  mov     dword ptr [rbp+var_30], eax
0x18003c489  mov     ecx, 2000h; dwDesiredAccess
0x18003c48e  xor     edx, edx; bInheritHandle
0x18003c490  movups  [rbp+SystemInformation], xmm0
0x18003c494  movups  [rbp+var_18], xmm0
0x18003c498  movups  [rbp+var_40], xmm0
0x18003c49c  call    cs:__imp_OpenProcess
0x18003c4a2  xor     ebx, ebx
0x18003c4a4  mov     rdi, rax
0x18003c4a7  test    rax, rax
0x18003c4aa  jz      short loc_18003C522
0x18003c4ac  lea     rax, [rbp+var_40]
0x18003c4b0  mov     qword ptr [rbp+SystemInformation+8], 1Ah
0x18003c4b8  lea     r8d, [rbx+20h]; SystemInformationLength
0x18003c4bc  mov     qword ptr [rbp+var_18], rax
0x18003c4c0  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18003c4c4  mov     qword ptr [rbp+var_18+8], 18h
0x18003c4cc  lea     ecx, [rbx+4Fh]; SystemInformationClass
0x18003c4cf  mov     dword ptr [rbp+SystemInformation], 2Dh ; '-'
0x18003c4d6  mov     dword ptr [rbp+SystemInformation+4], 6B756843h
0x18003c4dd  mov     qword ptr [rbp+var_40], 3
0x18003c4e5  mov     [rbp+var_30], 18h
0x18003c4ed  mov     qword ptr [rbp+var_40+8], rdi
0x18003c4f1  call    cs:__imp_NtSetSystemInformation
0x18003c4f7  test    eax, eax
0x18003c4f9  js      short loc_18003C516
0x18003c4fb  mov     rcx, rdi; hObject
0x18003c4fe  call    cs:__imp_CloseHandle
0x18003c504  mov     rdi, [rsp+60h+arg_8]
0x18003c509  mov     eax, ebx
0x18003c50b  mov     rbx, [rsp+60h+arg_0]
0x18003c510  add     rsp, 60h
0x18003c514  pop     rbp
0x18003c515  retn
0x18003c516  mov     ecx, eax; Status
0x18003c518  call    cs:__imp_RtlNtStatusToDosError
0x18003c51e  mov     ebx, eax
0x18003c520  jmp     short loc_18003C4FB
0x18003c522  call    cs:__imp_GetLastError
0x18003c528  mov     ebx, eax
0x18003c52a  jmp     short loc_18003C504
```
