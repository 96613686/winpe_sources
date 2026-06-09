# PowerNotificationThread

- ea: `0x180003bc0`
- end: `0x180003c32`
- name: `PowerNotificationThread`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800025f8`
- `0x180002684`
- `0x180003114`
- `0x180003bc0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180003c07`
- `ntdll!NtWaitForSingleObject` at `0x180003c07`
- `ntdll!NtSetInformationThread` at `0x180003bec`
- `ntdll!NtSetInformationThread` at `0x180003bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003bce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003bce`

## pseudocode

```c
void __noreturn PowerNotificationThread()
{
  HANDLE CurrentThread; // rax
  HANDLE v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8
  int ThreadInformation; // [rsp+38h] [rbp+10h] BYREF

  ThreadInformation = 15;
  CurrentThread = GetCurrentThread();
  NtSetInformationThread(CurrentThread, ThreadPriority, &ThreadInformation, 4u);
  v1 = ghPowerRequestEvent;
  while ( 1 )
  {
    while ( NtWaitForSingleObject(v1, 1u, 0) )
      ;
    EtwLogNotificationStart(254, v2, v3);
    HandlePowerCallout();
    EtwLogNotificationStop(254);
  }
}

```

## disassembly

```asm
0x180003bc0  push    rbx
0x180003bc2  sub     rsp, 20h
0x180003bc6  mov     [rsp+28h+ThreadInformation], 0Fh
0x180003bce  call    cs:__imp_GetCurrentThread
0x180003bd5  nop     dword ptr [rax+rax+00h]
0x180003bda  mov     r9d, 4; ThreadInformationLength
0x180003be0  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180003be5  mov     rcx, rax; ThreadHandle
0x180003be8  lea     edx, [r9-2]; ThreadInformationClass
0x180003bec  call    cs:__imp_NtSetInformationThread
0x180003bf3  nop     dword ptr [rax+rax+00h]
0x180003bf8  mov     rbx, cs:ghPowerRequestEvent
0x180003bff  xor     r8d, r8d; Timeout
0x180003c02  mov     dl, 1; Alertable
0x180003c04  mov     rcx, rbx; Handle
0x180003c07  call    cs:__imp_NtWaitForSingleObject
0x180003c0e  nop     dword ptr [rax+rax+00h]
0x180003c13  test    eax, eax
0x180003c15  jnz     short loc_180003BFF
0x180003c17  mov     ecx, 0FEh
0x180003c1c  call    EtwLogNotificationStart
0x180003c21  call    HandlePowerCallout
0x180003c26  mov     ecx, 0FEh
0x180003c2b  call    EtwLogNotificationStop
0x180003c30  jmp     short loc_180003BFF
```
