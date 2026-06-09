# WinStationGetAllProcesses

- ea: `0x180004200`
- end: `0x180004429`
- name: `WinStationGetAllProcesses`
- size: `553`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004200`
- `0x180004430`
- `0x180004554`
- `0x180007140`
- `0x180007890`
- `0x18000f400`
- `0x18002c79c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180004398`
- `ntdll!RtlNtStatusToDosError` at `0x180004398`
- `ntdll!NtQuerySystemInformation` at `0x180004276`
- `ntdll!NtQuerySystemInformation` at `0x1800042c9`
- `ntdll!NtQuerySystemInformation` at `0x180004276`
- `ntdll!NtQuerySystemInformation` at `0x1800042c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004365`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004365`

## string_xrefs

- `0x1800043bc`: `CProcessUtils::GetSystemProcessInformation`

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
  ULONG v21; // eax
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
0x180004200  mov     [rsp-38h+arg_0], rbx
0x180004205  push    rbp
0x180004206  push    rsi
0x180004207  push    rdi
0x180004208  push    r12
0x18000420a  push    r13
0x18000420c  push    r14
0x18000420e  push    r15
0x180004210  mov     rbp, rsp
0x180004213  sub     rsp, 50h
0x180004217  lea     rax, MIDL_user_allocate
0x18000421e  mov     dword ptr [r8], 0
0x180004225  mov     [rbp+var_10], rax
0x180004229  mov     r12, r9
0x18000422c  lea     rax, MIDL_user_free
0x180004233  mov     [rbp+var_18], 0
0x18000423b  mov     [rbp+var_8], rax
0x18000423f  mov     r13, r8
0x180004242  mov     [rbp+var_20], 0
0x180004249  mov     qword ptr [r9], 0
0x180004250  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180004255  test    eax, eax
0x180004257  jz      loc_18000438A
0x18000425d  test    edx, edx
0x18000425f  jnz     loc_180004391
0x180004265  xor     ebx, ebx
0x180004267  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000426b  xor     r8d, r8d; SystemInformationLength
0x18000426e  mov     [rbp+ReturnLength], ebx
0x180004271  xor     edx, edx; SystemInformation
0x180004273  lea     ecx, [rbx+5]; SystemInformationClass
0x180004276  call    cs:__imp_NtQuerySystemInformation
0x18000427c  xor     r14d, r14d
0x18000427f  lea     r15d, [rbx+1]
0x180004283  mov     r8d, [rbp+ReturnLength]; unsigned int
0x180004287  mov     esi, eax
0x180004289  cmp     eax, 0C0000004h
0x18000428e  jnz     short loc_1800042D4
0x180004290  test    r8d, r8d
0x180004293  jz      short loc_1800042D4
0x180004295  cmp     r14d, 5
0x180004299  jge     short loc_1800042D4
0x18000429b  test    rbx, rbx
0x18000429e  jnz     loc_1800043AB
0x1800042a4  lea     edi, [r8+400h]
0x1800042ab  mov     ecx, edi; size
0x1800042ad  call    MIDL_user_allocate
0x1800042b2  mov     rbx, rax
0x1800042b5  test    rax, rax
0x1800042b8  jz      short loc_180004338
0x1800042ba  lea     r9, [rbp+ReturnLength]; ReturnLength
0x1800042be  mov     r8d, edi; SystemInformationLength
0x1800042c1  mov     rdx, rax; SystemInformation
0x1800042c4  mov     ecx, 5; SystemInformationClass
0x1800042c9  call    cs:__imp_NtQuerySystemInformation
0x1800042cf  add     r14d, r15d
0x1800042d2  jmp     short loc_180004283
0x1800042d4  mov     edi, esi
0x1800042d6  or      edi, 10000000h
0x1800042dc  jl      loc_1800043BC
0x1800042e2  test    r8d, r8d
0x1800042e5  jz      loc_1800043ED
0x1800042eb  mov     [rbp+arg_18], esi
0x1800042ee  test    rbx, rbx
0x1800042f1  jz      short loc_18000436F
0x1800042f3  test    r8d, r8d
0x1800042f6  jz      short loc_180004362
0x1800042f8  lea     rax, [rbp+arg_18]
0x1800042fc  mov     rdx, rbx; struct _SYSTEM_PROCESS_INFORMATION *
0x1800042ff  mov     [rsp+50h+var_28], rax; int *
0x180004304  lea     r9, [rbp+var_18]; struct _TS_ALL_PROCESSES_INFO_NT6 **
0x180004308  lea     rax, [rbp+var_20]
0x18000430c  lea     rcx, [rbp+var_10]; this
0x180004310  mov     [rsp+50h+var_30], rax; unsigned int *
0x180004315  call    ?ConvertSysProcInfoToTSAllProcInfo@CProcessUtils@@QEAAJPEAU_SYSTEM_PROCESS_INFORMATION@@KPEAPEAU_TS_ALL_PROCESSES_INFO_NT6@@PEAKPEAJ@Z; CProcessUtils::ConvertSysProcInfoToTSAllProcInfo(_SYSTEM_PROCESS_INFORMATION *,ulong,_TS_ALL_PROCESSES_INFO_NT6 * *,ulong *,long *)
0x18000431a  mov     edi, eax
0x18000431c  test    eax, eax
0x18000431e  js      loc_180004409
0x180004324  mov     eax, [rbp+var_20]
0x180004327  mov     [r13+0], eax
0x18000432b  mov     rax, [rbp+var_18]
0x18000432f  mov     [r12], rax
0x180004333  mov     esi, [rbp+arg_18]
0x180004336  jmp     short loc_180004362
0x180004338  mov     esi, 0C0000017h
0x18000433d  mov     edi, 80004001h
0x180004342  xor     ebx, ebx
0x180004344  lea     r9, aWinstationgeta_9; "WinStationGetAllProcesses"
0x18000434b  mov     r8d, edi
0x18000434e  lea     rdx, aProcessutilsGe; "ProcessUtils.GetSessionProcessInformati"...
0x180004355  lea     ecx, [rbx+8]; int
0x180004358  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000435d  test    rbx, rbx
0x180004360  jz      short loc_18000436B
0x180004362  mov     rcx, rbx; hMem
0x180004365  call    cs:__imp_LocalFree
0x18000436b  test    edi, edi
0x18000436d  js      short loc_180004396
0x18000436f  mov     al, r15b
0x180004372  mov     rbx, [rsp+50h+arg_0]
0x18000437a  add     rsp, 50h
0x18000437e  pop     r15
0x180004380  pop     r14
0x180004382  pop     r13
0x180004384  pop     r12
0x180004386  pop     rdi
0x180004387  pop     rsi
0x180004388  pop     rbp
0x180004389  retn
0x18000438a  call    ?Legacy_WinStationGetAllProcesses@@YAEPEAXKPEAKPEAPEAX@Z; Legacy_WinStationGetAllProcesses(void *,ulong,ulong *,void * *)
0x18000438f  jmp     short loc_180004372
0x180004391  mov     esi, 0C0000002h
0x180004396  mov     ecx, esi; Status
0x180004398  call    cs:__imp_RtlNtStatusToDosError
0x18000439e  mov     ecx, eax; dwErrCode
0x1800043a0  call    cs:__imp_SetLastError
0x1800043a6  xor     r15b, r15b
0x1800043a9  jmp     short loc_18000436F
0x1800043ab  mov     rcx, rbx; void *
0x1800043ae  call    MIDL_user_free
0x1800043b3  mov     r8d, [rbp+ReturnLength]
0x1800043b7  jmp     loc_1800042A4
0x1800043bc  lea     r9, aCprocessutilsG_0; "CProcessUtils::GetSystemProcessInformat"...
0x1800043c3  mov     r8d, edi
0x1800043c6  lea     rdx, aNtquerysystemi_0; "NtQuerySystemInformation failed: 0x%x i"...
0x1800043cd  mov     ecx, 8; int
0x1800043d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800043d7  test    rbx, rbx
0x1800043da  jz      loc_180004342
0x1800043e0  mov     rcx, rbx; void *
0x1800043e3  call    MIDL_user_free
0x1800043e8  jmp     loc_180004342
0x1800043ed  test    rbx, rbx
0x1800043f0  jz      loc_1800042EB
0x1800043f6  mov     rcx, rbx; void *
0x1800043f9  call    MIDL_user_free
0x1800043fe  mov     r8d, [rbp+ReturnLength]
0x180004402  xor     ebx, ebx
0x180004404  jmp     loc_1800042EB
0x180004409  lea     r9, aWinstationgeta_9; "WinStationGetAllProcesses"
0x180004410  mov     r8d, eax
0x180004413  lea     rdx, aProcessutilsCo; "ProcessUtils.ConvertSysProcInfoToTSAllP"...
0x18000441a  mov     ecx, 8; int
0x18000441f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004424  jmp     loc_180004333
```
