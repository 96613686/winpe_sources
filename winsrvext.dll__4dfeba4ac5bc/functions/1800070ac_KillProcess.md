# KillProcess

- ea: `0x1800070ac`
- end: `0x18000711e`
- name: `KillProcess`
- size: `114`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005474`
- `0x18000592c`

## callees

- `0x1800070ac`
- `0x18000b9a8`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x1800070c6`
- `ntdll!NtTerminateProcess` at `0x1800070c6`
- `ntdll!NtWaitForSingleObject` at `0x180007101`
- `ntdll!NtWaitForSingleObject` at `0x180007101`

## pseudocode

```c
NTSTATUS __fastcall KillProcess(HANDLE Handle, __int64 a2)
{
  NTSTATUS v4; // ebx
  NTSTATUS result; // eax
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+18h] BYREF

  v4 = NtTerminateProcess(Handle, -1073741510);
  result = BoostHardError(a2, 1);
  if ( v4 >= 0 )
  {
    Timeout.QuadPart = -10000LL * (unsigned int)gdwProcessTerminateTimeout;
    return NtWaitForSingleObject(Handle, 0, &Timeout);
  }
  return result;
}

```

## disassembly

```asm
0x1800070ac  mov     [rsp+arg_0], rbx
0x1800070b1  mov     [rsp+arg_8], rsi
0x1800070b6  push    rdi
0x1800070b7  sub     rsp, 20h
0x1800070bb  mov     rdi, rdx
0x1800070be  mov     rsi, rcx
0x1800070c1  mov     edx, 0C000013Ah; ExitStatus
0x1800070c6  call    cs:__imp_NtTerminateProcess
0x1800070cd  nop     dword ptr [rax+rax+00h]
0x1800070d2  mov     edx, 1
0x1800070d7  mov     rcx, rdi
0x1800070da  mov     ebx, eax
0x1800070dc  call    BoostHardError
0x1800070e1  test    ebx, ebx
0x1800070e3  js      short loc_18000710D
0x1800070e5  mov     eax, cs:gdwProcessTerminateTimeout
0x1800070eb  lea     r8, [rsp+28h+Timeout]; Timeout
0x1800070f0  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x1800070f7  mov     rcx, rsi; Handle
0x1800070fa  mov     qword ptr [rsp+28h+Timeout], rdx
0x1800070ff  xor     edx, edx; Alertable
0x180007101  call    cs:__imp_NtWaitForSingleObject
0x180007108  nop     dword ptr [rax+rax+00h]
0x18000710d  mov     rbx, [rsp+28h+arg_0]
0x180007112  mov     rsi, [rsp+28h+arg_8]
0x180007117  add     rsp, 20h
0x18000711b  pop     rdi
0x18000711c  retn
```
