# ProcessEventUninitialize

- ea: `0x14000b34c`
- end: `0x14000b411`
- name: `ProcessEventUninitialize`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b614`

## callees

- `0x140001118`
- `0x14000aad0`
- `0x14000b34c`

## import_xrefs

- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b3e7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000bc7a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b3e7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000bc7a`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b375`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b375`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000b39e`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000b39e`

## string_xrefs

- `0x14000b381`: `UevFilter.CloseProcessEventCompletionPort: Entry\n`
- `0x14000b3b5`: `UevFilter.CloseProcessEventCompletionPort: Exit\n`

## pseudocode

```c
__int64 ProcessEventUninitialize()
{
  DbgTrace(2, "UevFilter.ProcessEventUninitialize: Entry\n");
  if ( byte_140007138 == 1 )
  {
    KeAcquireGuardedMutex(&Mutex);
    DbgTrace(2, "UevFilter.CloseProcessEventCompletionPort: Entry\n");
    if ( ServerPort )
    {
      FltCloseCommunicationPort(ServerPort);
      ServerPort = 0;
    }
    DbgTrace(2, "UevFilter.CloseProcessEventCompletionPort: Exit\n");
    if ( P )
    {
      FreeFilterHashTable();
      P = 0;
    }
    KeReleaseGuardedMutex(&Mutex);
    byte_140007138 = 0;
  }
  return DbgTrace(2, "UevFilter.ProcessEventUninitialize: Exit\n");
}

```

## disassembly

```asm
0x14000b34c  sub     rsp, 28h
0x14000b350  lea     rdx, aUevfilterProce_11; "UevFilter.ProcessEventUninitialize: Ent"...
0x14000b357  mov     ecx, 2
0x14000b35c  call    DbgTrace
0x14000b361  cmp     cs:byte_140007138, 1
0x14000b368  jnz     loc_14000B3FA
0x14000b36e  lea     rcx, Mutex; Mutex
0x14000b375  call    cs:__imp_KeAcquireGuardedMutex
0x14000b37c  nop     dword ptr [rax+rax+00h]
0x14000b381  lea     rdx, aUevfilterClose_0; "UevFilter.CloseProcessEventCompletionPo"...
0x14000b388  mov     ecx, 2
0x14000b38d  call    DbgTrace
0x14000b392  mov     rcx, cs:ServerPort; ServerPort
0x14000b399  test    rcx, rcx
0x14000b39c  jz      short loc_14000B3B5
0x14000b39e  call    cs:__imp_FltCloseCommunicationPort
0x14000b3a5  nop     dword ptr [rax+rax+00h]
0x14000b3aa  mov     cs:ServerPort, 0
0x14000b3b5  lea     rdx, aUevfilterClose; "UevFilter.CloseProcessEventCompletionPo"...
0x14000b3bc  mov     ecx, 2
0x14000b3c1  call    DbgTrace
0x14000b3c6  cmp     cs:P, 0
0x14000b3ce  jz      short loc_14000B3E0
0x14000b3d0  call    FreeFilterHashTable
0x14000b3d5  mov     cs:P, 0
0x14000b3e0  lea     rcx, Mutex; Mutex
0x14000b3e7  call    cs:__imp_KeReleaseGuardedMutex
0x14000b3ee  nop     dword ptr [rax+rax+00h]
0x14000b3f3  mov     cs:byte_140007138, 0
0x14000b3fa  lea     rdx, aUevfilterProce_5; "UevFilter.ProcessEventUninitialize: Exi"...
0x14000b401  mov     ecx, 2
0x14000b406  call    DbgTrace
0x14000b40b  add     rsp, 28h
0x14000b40f  retn
0x14000bc6a  push    rbp
0x14000bc6c  sub     rsp, 20h
0x14000bc70  mov     rbp, rdx
0x14000bc73  lea     rcx, Mutex; Mutex
0x14000bc7a  call    cs:__imp_KeReleaseGuardedMutex
0x14000bc81  nop     dword ptr [rax+rax+00h]
0x14000bc86  mov     cs:byte_140007138, 0
0x14000bc8d  add     rsp, 20h
0x14000bc91  pop     rbp
0x14000bc92  retn
```
