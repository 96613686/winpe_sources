# WinStationGetAllProcesses

- ea: `0x18000a3f0`
- end: `0x18000a640`
- name: `WinStationGetAllProcesses`
- size: `592`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800053c0`
- `0x180005b40`
- `0x18000a3f0`
- `0x18000a650`
- `0x18000a784`
- `0x18000ff10`
- `0x18002eaac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a5a3`
- `ntdll!RtlNtStatusToDosError` at `0x18000a5a3`
- `ntdll!NtQuerySystemInformation` at `0x18000a466`
- `ntdll!NtQuerySystemInformation` at `0x18000a4c3`
- `ntdll!NtQuerySystemInformation` at `0x18000a466`
- `ntdll!NtQuerySystemInformation` at `0x18000a4c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a569`

## string_xrefs

- `0x18000a5d3`: `CProcessUtils::GetSystemProcessInformation`

## pseudocode

```c
unsigned __int8 __fastcall WinStationGetAllProcesses(
        void *a1,
        __int64 a2,
        unsigned int *a3,
        struct _TS_ALL_PROCESSES_INFO_NT6 **a4)
{
  unsigned int v6; // edx
  CPublicBinding *v7; // rcx
  unsigned int *v8; // r8
  void **v9; // r9
  struct _SYSTEM_PROCESS_INFORMATION *v10; // rbx
  NTSTATUS v11; // eax
  int v12; // r14d
  char v13; // r15
  ULONG v14; // r8d
  NTSTATUS v15; // esi
  ULONG v16; // edi
  struct _SYSTEM_PROCESS_INFORMATION *v17; // rax
  int v18; // edi
  int v19; // eax
  DWORD v21; // eax
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  struct _TS_ALL_PROCESSES_INFO_NT6 *v23; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG ReturnLength; // [rsp+A0h] [rbp+50h] BYREF
  int v26; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 0;
  v24[0] = MIDL_user_allocate;
  v23 = 0;
  v24[1] = MIDL_user_free;
  v22 = 0;
  *a4 = 0;
  if ( !(unsigned int)IsLocalServer(a1) )
    return Legacy_WinStationGetAllProcesses(v7, v6, v8, v9);
  if ( v6 )
  {
    v15 = -1073741822;
LABEL_25:
    v21 = RtlNtStatusToDosError(v15);
    SetLastError(v21);
    return 0;
  }
  else
  {
    v10 = 0;
    ReturnLength = 0;
    v11 = NtQuerySystemInformation(SystemProcessInformation, 0, 0, &ReturnLength);
    v12 = 0;
    v13 = 1;
    while ( 1 )
    {
      v14 = ReturnLength;
      v15 = v11;
      if ( v11 != -1073741820 || !ReturnLength || v12 >= 5 )
        break;
      if ( v10 )
      {
        MIDL_user_free(v10);
        v14 = ReturnLength;
      }
      v16 = v14 + 1024;
      v17 = (struct _SYSTEM_PROCESS_INFORMATION *)MIDL_user_allocate(v14 + 1024);
      v10 = v17;
      if ( !v17 )
      {
        v15 = -1073741801;
        v18 = -2147467263;
LABEL_19:
        _DbgPrintMessage(
          8,
          "ProcessUtils.GetSessionProcessInformation failed: 0x%x in %s",
          v18,
          "WinStationGetAllProcesses");
        goto LABEL_21;
      }
      v11 = NtQuerySystemInformation(SystemProcessInformation, v17, v16, &ReturnLength);
      ++v12;
    }
    v18 = v11 | 0x10000000;
    if ( v11 < 0 )
    {
      _DbgPrintMessage(
        8,
        "NtQuerySystemInformation failed: 0x%x in %s",
        v18,
        "CProcessUtils::GetSystemProcessInformation");
      if ( v10 )
        MIDL_user_free(v10);
      goto LABEL_19;
    }
    if ( !ReturnLength && v10 )
    {
      MIDL_user_free(v10);
      v14 = ReturnLength;
      v10 = 0;
    }
    v26 = v15;
    if ( !v10 )
      return v13;
    if ( v14 )
    {
      v19 = CProcessUtils::ConvertSysProcInfoToTSAllProcInfo((CProcessUtils *)v24, v10, v14, &v23, &v22, &v26);
      v18 = v19;
      if ( v19 < 0 )
      {
        _DbgPrintMessage(
          8,
          "ProcessUtils.ConvertSysProcInfoToTSAllProcInfo failed: 0x%x in %s",
          v19,
          "WinStationGetAllProcesses");
      }
      else
      {
        *a3 = v22;
        *a4 = v23;
      }
      v15 = v26;
    }
    LocalFree(v10);
LABEL_21:
    if ( v18 < 0 )
      goto LABEL_25;
  }
  return v13;
}

```

## disassembly

```asm
0x18000a3f0  mov     [rsp-38h+arg_0], rbx
0x18000a3f5  push    rbp
0x18000a3f6  push    rsi
0x18000a3f7  push    rdi
0x18000a3f8  push    r12
0x18000a3fa  push    r13
0x18000a3fc  push    r14
0x18000a3fe  push    r15
0x18000a400  mov     rbp, rsp
0x18000a403  sub     rsp, 50h
0x18000a407  lea     rax, MIDL_user_allocate
0x18000a40e  mov     dword ptr [r8], 0
0x18000a415  mov     [rbp+var_10], rax
0x18000a419  mov     r12, r9
0x18000a41c  lea     rax, MIDL_user_free
0x18000a423  mov     [rbp+var_18], 0
0x18000a42b  mov     [rbp+var_8], rax
0x18000a42f  mov     r13, r8
0x18000a432  mov     [rbp+var_20], 0
0x18000a439  mov     qword ptr [r9], 0
0x18000a440  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18000a445  test    eax, eax
0x18000a447  jz      loc_18000A595
0x18000a44d  test    edx, edx
0x18000a44f  jnz     loc_18000A59C
0x18000a455  xor     ebx, ebx
0x18000a457  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000a45b  xor     r8d, r8d; SystemInformationLength
0x18000a45e  mov     [rbp+ReturnLength], ebx
0x18000a461  xor     edx, edx; SystemInformation
0x18000a463  lea     ecx, [rbx+5]; SystemInformationClass
0x18000a466  call    cs:__imp_NtQuerySystemInformation
0x18000a46d  nop     dword ptr [rax+rax+00h]
0x18000a472  xor     r14d, r14d
0x18000a475  lea     r15d, [rbx+1]
0x18000a479  mov     r8d, [rbp+ReturnLength]; unsigned int
0x18000a47d  mov     esi, eax
0x18000a47f  cmp     eax, 0C0000004h
0x18000a484  jnz     short loc_18000A4D4
0x18000a486  test    r8d, r8d
0x18000a489  jz      short loc_18000A4D4
0x18000a48b  cmp     r14d, 5
0x18000a48f  jge     short loc_18000A4D4
0x18000a491  test    rbx, rbx
0x18000a494  jnz     loc_18000A5C2
0x18000a49a  lea     edi, [r8+400h]
0x18000a4a1  mov     ecx, edi; size
0x18000a4a3  call    MIDL_user_allocate
0x18000a4a8  mov     rbx, rax
0x18000a4ab  test    rax, rax
0x18000a4ae  jz      loc_18000A53C
0x18000a4b4  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000a4b8  mov     r8d, edi; SystemInformationLength
0x18000a4bb  mov     rdx, rax; SystemInformation
0x18000a4be  mov     ecx, 5; SystemInformationClass
0x18000a4c3  call    cs:__imp_NtQuerySystemInformation
0x18000a4ca  nop     dword ptr [rax+rax+00h]
0x18000a4cf  add     r14d, r15d
0x18000a4d2  jmp     short loc_18000A479
0x18000a4d4  mov     edi, esi
0x18000a4d6  or      edi, 10000000h
0x18000a4dc  jl      loc_18000A5D3
0x18000a4e2  test    r8d, r8d
0x18000a4e5  jz      loc_18000A604
0x18000a4eb  mov     [rbp+arg_18], esi
0x18000a4ee  test    rbx, rbx
0x18000a4f1  jz      loc_18000A579
0x18000a4f7  test    r8d, r8d
0x18000a4fa  jz      short loc_18000A566
0x18000a4fc  lea     rax, [rbp+arg_18]
0x18000a500  mov     rdx, rbx; struct _SYSTEM_PROCESS_INFORMATION *
0x18000a503  mov     [rsp+50h+var_28], rax; int *
0x18000a508  lea     r9, [rbp+var_18]; struct _TS_ALL_PROCESSES_INFO_NT6 **
0x18000a50c  lea     rax, [rbp+var_20]
0x18000a510  lea     rcx, [rbp+var_10]; this
0x18000a514  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000a519  call    ?ConvertSysProcInfoToTSAllProcInfo@CProcessUtils@@QEAAJPEAU_SYSTEM_PROCESS_INFORMATION@@KPEAPEAU_TS_ALL_PROCESSES_INFO_NT6@@PEAKPEAJ@Z; CProcessUtils::ConvertSysProcInfoToTSAllProcInfo(_SYSTEM_PROCESS_INFORMATION *,ulong,_TS_ALL_PROCESSES_INFO_NT6 * *,ulong *,long *)
0x18000a51e  mov     edi, eax
0x18000a520  test    eax, eax
0x18000a522  js      loc_18000A620
0x18000a528  mov     eax, [rbp+var_20]
0x18000a52b  mov     [r13+0], eax
0x18000a52f  mov     rax, [rbp+var_18]
0x18000a533  mov     [r12], rax
0x18000a537  mov     esi, [rbp+arg_18]
0x18000a53a  jmp     short loc_18000A566
0x18000a53c  mov     esi, 0C0000017h
0x18000a541  mov     edi, 80004001h
0x18000a546  xor     ebx, ebx
0x18000a548  lea     r9, aWinstationgeta_9; "WinStationGetAllProcesses"
0x18000a54f  mov     r8d, edi
0x18000a552  lea     rdx, aProcessutilsGe; "ProcessUtils.GetSessionProcessInformati"...
0x18000a559  lea     ecx, [rbx+8]; int
0x18000a55c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a561  test    rbx, rbx
0x18000a564  jz      short loc_18000A575
0x18000a566  mov     rcx, rbx; hMem
0x18000a569  call    cs:__imp_LocalFree
0x18000a570  nop     dword ptr [rax+rax+00h]
0x18000a575  test    edi, edi
0x18000a577  js      short loc_18000A5A1
0x18000a579  mov     al, r15b
0x18000a57c  mov     rbx, [rsp+50h+arg_0]
0x18000a584  add     rsp, 50h
0x18000a588  pop     r15
0x18000a58a  pop     r14
0x18000a58c  pop     r13
0x18000a58e  pop     r12
0x18000a590  pop     rdi
0x18000a591  pop     rsi
0x18000a592  pop     rbp
0x18000a593  retn
0x18000a595  call    ?Legacy_WinStationGetAllProcesses@@YAEPEAXKPEAKPEAPEAX@Z; Legacy_WinStationGetAllProcesses(void *,ulong,ulong *,void * *)
0x18000a59a  jmp     short loc_18000A57C
0x18000a59c  mov     esi, 0C0000002h
0x18000a5a1  mov     ecx, esi; Status
0x18000a5a3  call    cs:__imp_RtlNtStatusToDosError
0x18000a5aa  nop     dword ptr [rax+rax+00h]
0x18000a5af  mov     ecx, eax; dwErrCode
0x18000a5b1  call    cs:__imp_SetLastError
0x18000a5b8  nop     dword ptr [rax+rax+00h]
0x18000a5bd  xor     r15b, r15b
0x18000a5c0  jmp     short loc_18000A579
0x18000a5c2  mov     rcx, rbx; void *
0x18000a5c5  call    MIDL_user_free
0x18000a5ca  mov     r8d, [rbp+ReturnLength]
0x18000a5ce  jmp     loc_18000A49A
0x18000a5d3  lea     r9, aCprocessutilsG_0; "CProcessUtils::GetSystemProcessInformat"...
0x18000a5da  mov     r8d, edi
0x18000a5dd  lea     rdx, aNtquerysystemi_0; "NtQuerySystemInformation failed: 0x%x i"...
0x18000a5e4  mov     ecx, 8; int
0x18000a5e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a5ee  test    rbx, rbx
0x18000a5f1  jz      loc_18000A546
0x18000a5f7  mov     rcx, rbx; void *
0x18000a5fa  call    MIDL_user_free
0x18000a5ff  jmp     loc_18000A546
0x18000a604  test    rbx, rbx
0x18000a607  jz      loc_18000A4EB
0x18000a60d  mov     rcx, rbx; void *
0x18000a610  call    MIDL_user_free
0x18000a615  mov     r8d, [rbp+ReturnLength]
0x18000a619  xor     ebx, ebx
0x18000a61b  jmp     loc_18000A4EB
0x18000a620  lea     r9, aWinstationgeta_9; "WinStationGetAllProcesses"
0x18000a627  mov     r8d, eax
0x18000a62a  lea     rdx, aProcessutilsCo; "ProcessUtils.ConvertSysProcInfoToTSAllP"...
0x18000a631  mov     ecx, 8; int
0x18000a636  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a63b  jmp     loc_18000A537
```
