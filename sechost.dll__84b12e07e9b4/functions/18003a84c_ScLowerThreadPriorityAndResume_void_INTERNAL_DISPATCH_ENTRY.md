# ScLowerThreadPriorityAndResume(void *,_INTERNAL_DISPATCH_ENTRY *)

- ea: `0x18003a84c`
- end: `0x18003a8d4`
- name: `?ScLowerThreadPriorityAndResume@@YAKPEAXPEAU_INTERNAL_DISPATCH_ENTRY@@@Z`
- size: `136`
- prototype: `unsigned int __fastcall(HANDLE hThread, struct _INTERNAL_DISPATCH_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bfb0`

## callees

- `0x18003a84c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18003a89c`
- `ntdll!NtSetInformationThread` at `0x18003a89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a880`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a86a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a86a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003a8a5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003a8a5`

## pseudocode

```c
__int64 __fastcall ScLowerThreadPriorityAndResume(HANDLE hThread, struct _INTERNAL_DISPATCH_ENTRY *a2)
{
  DWORD LastError; // edi
  void *v5; // rcx
  int ThreadInformation; // [rsp+40h] [rbp+18h] BYREF

  LastError = 0;
  ThreadInformation = 0;
  if ( SetThreadPriority(hThread, -2) )
  {
    v5 = (void *)_InterlockedExchange64((volatile __int64 *)a2 + 10, (__int64)hThread);
    if ( v5 )
      CloseHandle(v5);
    ThreadInformation = 0;
    NtSetInformationThread(hThread, ThreadIoPriority, &ThreadInformation, 4u);
  }
  if ( ResumeThread(hThread) == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
      _InterlockedExchange64((volatile __int64 *)a2 + 10, 0);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003a84c  mov     [rsp+arg_0], rbx
0x18003a851  mov     [rsp+arg_8], rsi
0x18003a856  push    rdi
0x18003a857  sub     rsp, 20h
0x18003a85b  xor     edi, edi
0x18003a85d  mov     rbx, rdx
0x18003a860  mov     rsi, rcx
0x18003a863  mov     [rsp+28h+ThreadInformation], edi
0x18003a867  lea     edx, [rdi-2]; nPriority
0x18003a86a  call    cs:__imp_SetThreadPriority
0x18003a870  test    eax, eax
0x18003a872  jz      short loc_18003A8A2
0x18003a874  mov     rcx, rsi
0x18003a877  xchg    rcx, [rbx+50h]; hObject
0x18003a87b  test    rcx, rcx
0x18003a87e  jz      short loc_18003A886
0x18003a880  call    cs:__imp_CloseHandle
0x18003a886  mov     r9d, 4; ThreadInformationLength
0x18003a88c  mov     [rsp+28h+ThreadInformation], edi
0x18003a890  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18003a895  mov     rcx, rsi; ThreadHandle
0x18003a898  lea     edx, [r9+12h]; ThreadInformationClass
0x18003a89c  call    cs:__imp_NtSetInformationThread
0x18003a8a2  mov     rcx, rsi; hThread
0x18003a8a5  call    cs:__imp_ResumeThread
0x18003a8ab  cmp     eax, 0FFFFFFFFh
0x18003a8ae  jnz     short loc_18003A8C2
0x18003a8b0  call    cs:__imp_GetLastError
0x18003a8b6  mov     edi, eax
0x18003a8b8  test    eax, eax
0x18003a8ba  jz      short loc_18003A8C2
0x18003a8bc  xor     ecx, ecx
0x18003a8be  xchg    rcx, [rbx+50h]
0x18003a8c2  mov     rbx, [rsp+28h+arg_0]
0x18003a8c7  mov     eax, edi
0x18003a8c9  mov     rsi, [rsp+28h+arg_8]
0x18003a8ce  add     rsp, 20h
0x18003a8d2  pop     rdi
0x18003a8d3  retn
```
