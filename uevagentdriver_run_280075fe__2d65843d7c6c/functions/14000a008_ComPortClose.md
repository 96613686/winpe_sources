# ComPortClose

- ea: `0x14000a008`
- end: `0x14000a118`
- name: `ComPortClose`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b614`

## callees

- `0x140001118`
- `0x14000a008`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a0cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a0cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a0bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a0bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a055`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a055`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a040`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a040`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000a0eb`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000a0eb`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000a029`
- `FLTMGR!FltCloseCommunicationPort` at `0x14000a029`
- `FLTMGR!FltCloseClientPort` at `0x14000a0a1`
- `FLTMGR!FltCloseClientPort` at `0x14000a0a1`

## string_xrefs

- `0x14000a082`: `UevFilter.ComPort: Closing client port\n`
- `0x14000a00c`: `UevFilter.ComPortClose: Entry\n`
- `0x14000a101`: `UevFilter.ComportClose: Exit\n`

## pseudocode

```c
__int64 ComPortClose()
{
  bool v0; // zf
  _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  DbgTrace(2, "UevFilter.ComPortClose: Entry\n");
  if ( pServerPort )
  {
    FltCloseCommunicationPort(pServerPort);
    pServerPort = 0;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&comPortResource, 1u);
  if ( clientPortConnected )
  {
    v0 = clientPortRefCount == 1;
    clientPortConnected = 0;
    --clientPortRefCount;
    if ( v0 )
    {
      DbgTrace(2, "UevFilter.ComPort: Closing client port\n");
      FltCloseClientPort(g_pFilter, &pClientPort);
      pClientPort = 0;
    }
  }
  ExReleaseResourceLite(&comPortResource);
  KeLeaveCriticalRegion();
  while ( pClientPort )
  {
    Interval.QuadPart = -1000000;
    KeDelayExecutionThread(1, 1u, &Interval);
  }
  return DbgTrace(2, "UevFilter.ComportClose: Exit\n");
}

```

## disassembly

```asm
0x14000a008  sub     rsp, 28h
0x14000a00c  lea     rdx, aUevfilterCompo_17; "UevFilter.ComPortClose: Entry\n"
0x14000a013  mov     ecx, 2
0x14000a018  call    DbgTrace
0x14000a01d  mov     rcx, cs:pServerPort; ServerPort
0x14000a024  test    rcx, rcx
0x14000a027  jz      short loc_14000A040
0x14000a029  call    cs:__imp_FltCloseCommunicationPort
0x14000a030  nop     dword ptr [rax+rax+00h]
0x14000a035  mov     cs:pServerPort, 0
0x14000a040  call    cs:__imp_KeEnterCriticalRegion
0x14000a047  nop     dword ptr [rax+rax+00h]
0x14000a04c  mov     dl, 1; Wait
0x14000a04e  lea     rcx, comPortResource; Resource
0x14000a055  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a05c  nop     dword ptr [rax+rax+00h]
0x14000a061  cmp     cs:clientPortConnected, 0
0x14000a068  jz      short loc_14000A0B8
0x14000a06a  mov     eax, cs:clientPortRefCount
0x14000a070  add     eax, 0FFFFFFFFh
0x14000a073  mov     cs:clientPortConnected, 0
0x14000a07a  mov     cs:clientPortRefCount, eax
0x14000a080  jnz     short loc_14000A0B8
0x14000a082  lea     rdx, aUevfilterCompo_6; "UevFilter.ComPort: Closing client port"...
0x14000a089  mov     ecx, 2
0x14000a08e  call    DbgTrace
0x14000a093  mov     rcx, cs:g_pFilter; Filter
0x14000a09a  lea     rdx, pClientPort; ClientPort
0x14000a0a1  call    cs:__imp_FltCloseClientPort
0x14000a0a8  nop     dword ptr [rax+rax+00h]
0x14000a0ad  mov     cs:pClientPort, 0
0x14000a0b8  lea     rcx, comPortResource; Resource
0x14000a0bf  call    cs:__imp_ExReleaseResourceLite
0x14000a0c6  nop     dword ptr [rax+rax+00h]
0x14000a0cb  call    cs:__imp_KeLeaveCriticalRegion
0x14000a0d2  nop     dword ptr [rax+rax+00h]
0x14000a0d7  jmp     short loc_14000A0F7
0x14000a0d9  mov     dl, 1; Alertable
0x14000a0db  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFF0BDC0h
0x14000a0e4  mov     cl, dl; WaitMode
0x14000a0e6  lea     r8, [rsp+28h+Interval]; Interval
0x14000a0eb  call    cs:__imp_KeDelayExecutionThread
0x14000a0f2  nop     dword ptr [rax+rax+00h]
0x14000a0f7  cmp     cs:pClientPort, 0
0x14000a0ff  jnz     short loc_14000A0D9
0x14000a101  lea     rdx, aUevfilterCompo_2; "UevFilter.ComportClose: Exit\n"
0x14000a108  mov     ecx, 2
0x14000a10d  call    DbgTrace
0x14000a112  add     rsp, 28h
0x14000a116  retn
```
