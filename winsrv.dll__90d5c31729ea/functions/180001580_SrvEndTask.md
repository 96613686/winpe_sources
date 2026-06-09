# SrvEndTask

- ea: `0x180001580`
- end: `0x1800016d7`
- name: `SrvEndTask`
- size: `343`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001580`
- `0x180001740`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800015e4`
- `ntdll!NtQueryInformationProcess` at `0x1800015e4`
- `CSRSRV!CsrDereferenceProcess` at `0x1800016a7`
- `CSRSRV!CsrDereferenceProcess` at `0x1800016a7`
- `CSRSRV!CsrLockedReferenceProcess` at `0x180001634`
- `CSRSRV!CsrLockedReferenceProcess` at `0x180001634`
- `CSRSRV!CsrLockProcessByClientId` at `0x1800015a7`
- `CSRSRV!CsrLockProcessByClientId` at `0x1800015a7`
- `CSRSRV!CsrUnlockProcess` at `0x180001644`
- `CSRSRV!CsrUnlockProcess` at `0x1800016b9`
- `CSRSRV!CsrUnlockProcess` at `0x180001644`
- `CSRSRV!CsrUnlockProcess` at `0x1800016b9`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x180001658`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x180001658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001690`

## pseudocode

```c
__int64 __fastcall SrvEndTask(__int64 a1)
{
  __int64 v2; // rcx
  int CallbackThread; // ebx
  __int64 v5; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int64 ProcessInformation; // [rsp+60h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+38h]

  v2 = *(_QWORD *)(a1 + 80);
  if ( v2 )
  {
    v5 = 0;
    CallbackThread = CsrLockProcessByClientId(v2, &v5);
    if ( CallbackThread >= 0 )
    {
      ProcessInformation = 0;
      if ( NtQueryInformationProcess(
             *(HANDLE *)(v5 + 80),
             ProcessIoPriority|ProcessUserModeIOPL,
             &ProcessInformation,
             8u,
             0) >= 0
        && (ProcessInformation & 1) != 0
        && (ProcessInformation &= ~1uLL, *((_QWORD *)NtCurrentTeb()->CsrClientThread + 5) == ProcessInformation) )
      {
        hObject = 0;
        ProcessInformation = 0;
        CsrLockedReferenceProcess(v5);
        CsrUnlockProcess(v5);
        if ( (int)BaseGetProcessCrtlRoutine(v5, &ProcessInformation) < 0 )
        {
          CallbackThread = -1073741823;
        }
        else
        {
          CallbackThread = UserCreateCallbackThread(
                             *(PVOID *)(v5 + 80),
                             (PVOID)ProcessInformation,
                             (PVOID)*(unsigned int *)(a1 + 88));
          if ( CallbackThread >= 0 && hObject )
            CloseHandle(hObject);
        }
        CsrDereferenceProcess(v5);
      }
      else
      {
        CsrUnlockProcess(v5);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)CallbackThread;
}

```

## disassembly

```asm
0x180001580  push    rbp
0x180001582  push    rbx
0x180001583  push    rdi
0x180001584  mov     rbp, rsp
0x180001587  sub     rsp, 30h
0x18000158b  mov     rdi, rcx
0x18000158e  mov     rcx, [rcx+50h]
0x180001592  test    rcx, rcx
0x180001595  jz      loc_1800016C7
0x18000159b  lea     rdx, [rbp+arg_0]
0x18000159f  mov     [rbp+arg_0], 0
0x1800015a7  call    cs:__imp_CsrLockProcessByClientId
0x1800015ae  nop     dword ptr [rax+rax+00h]
0x1800015b3  mov     ebx, eax
0x1800015b5  test    eax, eax
0x1800015b7  js      loc_1800016CC
0x1800015bd  mov     rcx, [rbp+arg_0]
0x1800015c1  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x1800015c5  mov     r9d, 8; ProcessInformationLength
0x1800015cb  mov     [rbp+ProcessInformation], 0
0x1800015d3  mov     [rsp+30h+ReturnLength], 0; ReturnLength
0x1800015dc  mov     rcx, [rcx+50h]; ProcessHandle
0x1800015e0  lea     edx, [r9+29h]; ProcessInformationClass
0x1800015e4  call    cs:__imp_NtQueryInformationProcess
0x1800015eb  nop     dword ptr [rax+rax+00h]
0x1800015f0  test    eax, eax
0x1800015f2  js      loc_1800016B5
0x1800015f8  mov     rcx, [rbp+ProcessInformation]
0x1800015fc  test    cl, 1
0x1800015ff  jz      loc_1800016B5
0x180001605  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180001609  mov     [rbp+ProcessInformation], rcx
0x18000160d  mov     rax, gs:70h
0x180001616  cmp     [rax+28h], rcx
0x18000161a  jnz     loc_1800016B5
0x180001620  mov     rcx, [rbp+arg_0]
0x180001624  mov     [rbp+hObject], 0
0x18000162c  mov     [rbp+ProcessInformation], 0
0x180001634  call    cs:__imp_CsrLockedReferenceProcess
0x18000163b  nop     dword ptr [rax+rax+00h]
0x180001640  mov     rcx, [rbp+arg_0]
0x180001644  call    cs:__imp_CsrUnlockProcess
0x18000164b  nop     dword ptr [rax+rax+00h]
0x180001650  mov     rcx, [rbp+arg_0]
0x180001654  lea     rdx, [rbp+ProcessInformation]
0x180001658  call    cs:__imp_BaseGetProcessCrtlRoutine
0x18000165f  nop     dword ptr [rax+rax+00h]
0x180001664  test    eax, eax
0x180001666  js      short loc_18000169E
0x180001668  mov     rcx, [rbp+arg_0]
0x18000166c  lea     r9, [rbp+hObject]
0x180001670  mov     r8d, [rdi+58h]; Reserved6
0x180001674  mov     rdx, [rbp+ProcessInformation]; Reserved5
0x180001678  mov     rcx, [rcx+50h]; ThreadContext
0x18000167c  call    UserCreateCallbackThread
0x180001681  mov     ebx, eax
0x180001683  test    eax, eax
0x180001685  js      short loc_1800016A3
0x180001687  mov     rcx, [rbp+hObject]; hObject
0x18000168b  test    rcx, rcx
0x18000168e  jz      short loc_1800016A3
0x180001690  call    cs:__imp_CloseHandle
0x180001697  nop     dword ptr [rax+rax+00h]
0x18000169c  jmp     short loc_1800016A3
0x18000169e  mov     ebx, 0C0000001h
0x1800016a3  mov     rcx, [rbp+arg_0]
0x1800016a7  call    cs:__imp_CsrDereferenceProcess
0x1800016ae  nop     dword ptr [rax+rax+00h]
0x1800016b3  jmp     short loc_1800016CC
0x1800016b5  mov     rcx, [rbp+arg_0]
0x1800016b9  call    cs:__imp_CsrUnlockProcess
0x1800016c0  nop     dword ptr [rax+rax+00h]
0x1800016c5  jmp     short loc_1800016CC
0x1800016c7  mov     ebx, 0C000000Dh
0x1800016cc  mov     eax, ebx
0x1800016ce  add     rsp, 30h
0x1800016d2  pop     rdi
0x1800016d3  pop     rbx
0x1800016d4  pop     rbp
0x1800016d5  retn
```
