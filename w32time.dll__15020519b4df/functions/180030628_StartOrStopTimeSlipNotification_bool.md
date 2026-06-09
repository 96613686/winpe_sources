# StartOrStopTimeSlipNotification(bool)

- ea: `0x180030628`
- end: `0x180030814`
- name: `?StartOrStopTimeSlipNotification@@YAJ_N@Z`
- size: `492`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009a80`
- `0x180039100`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180030628`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030694`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030656`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003063d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003063d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800307e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800307e6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800306f0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800307ab`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800306f0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800307ab`
- `ntdll!NtSetSystemInformation` at `0x180030738`
- `ntdll!NtSetSystemInformation` at `0x180030738`
- `ntdll!RtlNtStatusToDosError` at `0x18003074a`
- `ntdll!RtlNtStatusToDosError` at `0x18003074a`

## pseudocode

```c
__int64 __fastcall StartOrStopTimeSlipNotification(char a1)
{
  HANDLE CurrentProcess; // rax
  struct _TOKEN_PRIVILEGES *v3; // rdi
  signed int LastError; // eax
  signed int v5; // ebx
  char *v6; // rax
  NTSTATUS v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  bool v10; // sf
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF
  __int64 SystemInformation; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v3 = 0;
LABEL_3:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_23;
  }
  v6 = (char *)LocalAlloc(0x40u, 0x10u);
  v3 = (struct _TOKEN_PRIVILEGES *)v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_23;
  }
  *(_DWORD *)v6 = 1;
  *((_DWORD *)v6 + 3) = 2;
  SystemInformation = 12;
  *(_QWORD *)(v6 + 4) = 12;
  AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)v6, 0, 0, 0);
  if ( GetLastError() )
    goto LABEL_3;
  if ( a1 == 1 )
    SystemInformation = (__int64)qword_1800A36F8;
  else
    SystemInformation = 0;
  v7 = NtSetSystemInformation(SystemTimeSlipNotification, &SystemInformation, 8u);
  if ( v7 )
  {
    v8 = RtlNtStatusToDosError(v7);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAdd(L"SetTimeSlipNotification succeeds with 0x%08X.\n", 0);
    v5 = 0;
  }
  v3->Privileges[0].Attributes = 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, v3, 0, 0, 0) )
  {
    v9 = GetLastError();
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( v10 && v5 >= 0 )
      v5 = v9;
  }
LABEL_23:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030628  mov     [rsp+arg_0], rbx
0x18003062d  push    rdi
0x18003062e  sub     rsp, 30h
0x180030632  mov     bl, cl
0x180030634  mov     [rsp+38h+TokenHandle], 0
0x18003063d  call    cs:__imp_GetCurrentProcess
0x180030644  nop     dword ptr [rax+rax+00h]
0x180030649  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003064e  mov     edx, 28h ; '('; DesiredAccess
0x180030653  mov     rcx, rax; ProcessHandle
0x180030656  call    cs:__imp_OpenProcessToken
0x18003065d  nop     dword ptr [rax+rax+00h]
0x180030662  test    eax, eax
0x180030664  jnz     short loc_18003068C
0x180030666  xor     edi, edi
0x180030668  call    cs:__imp_GetLastError
0x18003066f  nop     dword ptr [rax+rax+00h]
0x180030674  mov     ebx, eax
0x180030676  test    eax, eax
0x180030678  jle     loc_1800307DC
0x18003067e  movzx   ebx, ax
0x180030681  or      ebx, 80070000h
0x180030687  jmp     loc_1800307DC
0x18003068c  mov     edx, 10h; uBytes
0x180030691  lea     ecx, [rdx+30h]; uFlags
0x180030694  call    cs:__imp_LocalAlloc
0x18003069b  nop     dword ptr [rax+rax+00h]
0x1800306a0  mov     rdi, rax
0x1800306a3  test    rax, rax
0x1800306a6  jnz     short loc_1800306B2
0x1800306a8  mov     ebx, 8007000Eh
0x1800306ad  jmp     loc_1800307DC
0x1800306b2  mov     dword ptr [rax], 1
0x1800306b8  xor     r9d, r9d; BufferLength
0x1800306bb  mov     dword ptr [rdi+0Ch], 2
0x1800306c2  mov     r8, rdi; NewState
0x1800306c5  mov     [rsp+38h+SystemInformation], 0Ch
0x1800306ce  xor     edx, edx; DisableAllPrivileges
0x1800306d0  mov     rax, [rsp+38h+SystemInformation]
0x1800306d5  mov     [rdi+4], rax
0x1800306d9  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800306de  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800306e7  mov     [rsp+38h+PreviousState], 0; PreviousState
0x1800306f0  call    cs:__imp_AdjustTokenPrivileges
0x1800306f7  nop     dword ptr [rax+rax+00h]
0x1800306fc  call    cs:__imp_GetLastError
0x180030703  nop     dword ptr [rax+rax+00h]
0x180030708  test    eax, eax
0x18003070a  jnz     loc_180030668
0x180030710  lea     r8d, [rax+8]; SystemInformationLength
0x180030714  lea     rdx, [rsp+38h+SystemInformation]; SystemInformation
0x180030719  lea     ecx, [rax+2Eh]; SystemInformationClass
0x18003071c  cmp     bl, 1
0x18003071f  jnz     short loc_18003072F
0x180030721  mov     rax, cs:qword_1800A36F8
0x180030728  mov     [rsp+38h+SystemInformation], rax
0x18003072d  jmp     short loc_180030738
0x18003072f  mov     [rsp+38h+SystemInformation], 0
0x180030738  call    cs:__imp_NtSetSystemInformation
0x18003073f  nop     dword ptr [rax+rax+00h]
0x180030744  test    eax, eax
0x180030746  jz      short loc_180030767
0x180030748  mov     ecx, eax; Status
0x18003074a  call    cs:__imp_RtlNtStatusToDosError
0x180030751  nop     dword ptr [rax+rax+00h]
0x180030756  mov     ebx, eax
0x180030758  test    eax, eax
0x18003075a  jle     short loc_180030785
0x18003075c  movzx   ebx, ax
0x18003075f  or      ebx, 80070000h
0x180030765  jmp     short loc_180030785
0x180030767  mov     ecx, 40h ; '@'
0x18003076c  call    FileLogAllowEntry
0x180030771  test    al, al
0x180030773  jz      short loc_180030783
0x180030775  xor     edx, edx
0x180030777  lea     rcx, aSettimeslipnot; "SetTimeSlipNotification succeeds with 0"...
0x18003077e  call    FileLogAdd
0x180030783  xor     ebx, ebx
0x180030785  mov     dword ptr [rdi+0Ch], 0
0x18003078c  xor     r9d, r9d; BufferLength
0x18003078f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180030794  mov     r8, rdi; NewState
0x180030797  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800307a0  xor     edx, edx; DisableAllPrivileges
0x1800307a2  mov     [rsp+38h+PreviousState], 0; PreviousState
0x1800307ab  call    cs:__imp_AdjustTokenPrivileges
0x1800307b2  nop     dword ptr [rax+rax+00h]
0x1800307b7  test    eax, eax
0x1800307b9  jnz     short loc_1800307DC
0x1800307bb  call    cs:__imp_GetLastError
0x1800307c2  nop     dword ptr [rax+rax+00h]
0x1800307c7  test    eax, eax
0x1800307c9  jle     short loc_1800307D5
0x1800307cb  movzx   eax, ax
0x1800307ce  or      eax, 80070000h
0x1800307d3  test    eax, eax
0x1800307d5  jns     short loc_1800307DC
0x1800307d7  test    ebx, ebx
0x1800307d9  cmovns  ebx, eax
0x1800307dc  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800307e1  test    rcx, rcx
0x1800307e4  jz      short loc_1800307F2
0x1800307e6  call    cs:__imp_CloseHandle
0x1800307ed  nop     dword ptr [rax+rax+00h]
0x1800307f2  test    rdi, rdi
0x1800307f5  jz      short loc_180030806
0x1800307f7  mov     rcx, rdi; hMem
0x1800307fa  call    cs:__imp_LocalFree
0x180030801  nop     dword ptr [rax+rax+00h]
0x180030806  mov     eax, ebx
0x180030808  mov     rbx, [rsp+38h+arg_0]
0x18003080d  add     rsp, 30h
0x180030811  pop     rdi
0x180030812  retn
```
