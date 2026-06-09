# ThreadHasIOPending(void)

- ea: `0x180003c84`
- end: `0x180003cc5`
- name: `?ThreadHasIOPending@@YAHXZ`
- size: `65`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003c90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003c90`
- `ntdll!NtQueryInformationThread` at `0x180003cb1`
- `ntdll!NtQueryInformationThread` at `0x180003cb1`

## pseudocode

```c
_BOOL8 ThreadHasIOPending(void)
{
  HANDLE CurrentThread; // rax
  int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF

  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  NtQueryInformationThread(CurrentThread, ThreadIsIoPending, &ThreadInformation, 4u, 0);
  return ThreadInformation != 0;
}

```

## disassembly

```asm
0x180003c84  sub     rsp, 38h
0x180003c88  mov     [rsp+38h+ThreadInformation], 0
0x180003c90  call    cs:__imp_GetCurrentThread
0x180003c96  mov     r9d, 4; ThreadInformationLength
0x180003c9c  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180003ca5  mov     rcx, rax; ThreadHandle
0x180003ca8  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180003cad  lea     edx, [r9+0Ch]; ThreadInformationClass
0x180003cb1  call    cs:__imp_NtQueryInformationThread
0x180003cb7  xor     eax, eax
0x180003cb9  cmp     [rsp+38h+ThreadInformation], eax
0x180003cbd  setnz   al
0x180003cc0  add     rsp, 38h
0x180003cc4  retn
```
