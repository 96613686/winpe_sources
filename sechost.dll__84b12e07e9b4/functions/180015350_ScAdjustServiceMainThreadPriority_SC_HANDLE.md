# ScAdjustServiceMainThreadPriority(SC_HANDLE__ *)

- ea: `0x180015350`
- end: `0x180015440`
- name: `?ScAdjustServiceMainThreadPriority@@YAKPEAUSC_HANDLE__@@@Z`
- size: `240`
- prototype: `unsigned int __fastcall(struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180012840`

## callees

- `0x180015350`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001541b`
- `ntdll!RtlNtStatusToDosError` at `0x18001541b`
- `ntdll!NtSetInformationThread` at `0x18001540f`
- `ntdll!NtSetInformationThread` at `0x18001540f`
- `ntdll!NtQueryInformationThread` at `0x1800153e5`
- `ntdll!NtQueryInformationThread` at `0x1800153e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015426`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800153a1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800153a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800153c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800153c0`

## pseudocode

```c
__int64 __fastcall ScAdjustServiceMainThreadPriority(struct SC_HANDLE__ *a1)
{
  char *v1; // rax
  DWORD v2; // ebx
  void *v3; // rdi
  int ThreadPriority; // eax
  DWORD LastError; // eax
  int v6; // eax
  int ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  v1 = (char *)hMem + 8;
  ThreadInformation = 0;
  while ( 1 )
  {
    if ( !*((_QWORD *)v1 + 1) )
      return 1083;
    if ( *((struct SC_HANDLE__ **)v1 + 6) == a1 )
      break;
    v1 += 96;
  }
  if ( v1 )
  {
    v2 = 0;
    v3 = (void *)_InterlockedExchange64((volatile __int64 *)v1 + 10, 0);
    if ( !v3 )
      return v2;
    ThreadPriority = GetThreadPriority(v3);
    if ( ThreadPriority == 0x7FFFFFFF || ThreadPriority == -2 && !SetThreadPriority(v3, 0) )
    {
      LastError = GetLastError();
    }
    else
    {
      ThreadInformation = 0;
      v6 = NtQueryInformationThread(v3, ThreadIoPriority, &ThreadInformation, 4u, 0);
      if ( v6 >= 0 )
      {
        if ( ThreadInformation )
          goto LABEL_16;
        ThreadInformation = 2;
        v6 = NtSetInformationThread(v3, ThreadIoPriority, &ThreadInformation, 4u);
        if ( v6 >= 0 )
          goto LABEL_16;
      }
      LastError = RtlNtStatusToDosError(v6);
    }
    v2 = LastError;
LABEL_16:
    CloseHandle(v3);
    return v2;
  }
  return 1083;
}

```

## disassembly

```asm
0x180015350  mov     [rsp+arg_0], rbx
0x180015355  push    rdi
0x180015356  sub     rsp, 30h
0x18001535a  mov     rax, cs:hMem
0x180015361  add     rax, 8
0x180015365  mov     [rsp+38h+ThreadInformation], 0
0x18001536d  cmp     qword ptr [rax+8], 0
0x180015372  jz      loc_18001542E
0x180015378  cmp     [rax+30h], rcx
0x18001537c  jz      short loc_180015384
0x18001537e  add     rax, 60h ; '`'
0x180015382  jmp     short loc_18001536D
0x180015384  test    rax, rax
0x180015387  jz      loc_18001542E
0x18001538d  xor     edi, edi
0x18001538f  xor     ebx, ebx
0x180015391  xchg    rdi, [rax+50h]
0x180015395  test    rdi, rdi
0x180015398  jz      loc_180015433
0x18001539e  mov     rcx, rdi; hThread
0x1800153a1  call    cs:__imp_GetThreadPriority
0x1800153a7  cmp     eax, 7FFFFFFFh
0x1800153ac  jnz     short loc_1800153B6
0x1800153ae  call    cs:__imp_GetLastError
0x1800153b4  jmp     short loc_180015421
0x1800153b6  cmp     eax, 0FFFFFFFEh
0x1800153b9  jnz     short loc_1800153CA
0x1800153bb  xor     edx, edx; nPriority
0x1800153bd  mov     rcx, rdi; hThread
0x1800153c0  call    cs:__imp_SetThreadPriority
0x1800153c6  test    eax, eax
0x1800153c8  jz      short loc_1800153AE
0x1800153ca  mov     r9d, 4; ThreadInformationLength
0x1800153d0  mov     [rsp+38h+ThreadInformation], ebx
0x1800153d4  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800153d9  mov     [rsp+38h+ReturnLength], rbx; ReturnLength
0x1800153de  mov     rcx, rdi; ThreadHandle
0x1800153e1  lea     edx, [r9+12h]; ThreadInformationClass
0x1800153e5  call    cs:__imp_NtQueryInformationThread
0x1800153eb  test    eax, eax
0x1800153ed  js      short loc_180015419
0x1800153ef  cmp     [rsp+38h+ThreadInformation], ebx
0x1800153f3  jnz     short loc_180015423
0x1800153f5  mov     r9d, 4; ThreadInformationLength
0x1800153fb  mov     [rsp+38h+ThreadInformation], 2
0x180015403  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180015408  mov     rcx, rdi; ThreadHandle
0x18001540b  lea     edx, [r9+12h]; ThreadInformationClass
0x18001540f  call    cs:__imp_NtSetInformationThread
0x180015415  test    eax, eax
0x180015417  jns     short loc_180015423
0x180015419  mov     ecx, eax; Status
0x18001541b  call    cs:__imp_RtlNtStatusToDosError
0x180015421  mov     ebx, eax
0x180015423  mov     rcx, rdi; hObject
0x180015426  call    cs:__imp_CloseHandle
0x18001542c  jmp     short loc_180015433
0x18001542e  mov     ebx, 43Bh
0x180015433  mov     eax, ebx
0x180015435  mov     rbx, [rsp+38h+arg_0]
0x18001543a  add     rsp, 30h
0x18001543e  pop     rdi
0x18001543f  retn
```
