# ChLocalOfferRemoveThreadEntry

- ea: `0x140010110`
- end: `0x140010165`
- name: `ChLocalOfferRemoveThreadEntry`
- size: `85`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ff34`
- `0x140010110`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x140010153`
- `ntoskrnl!PsTerminateSystemThread` at `0x140010153`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001012e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001012e`

## pseudocode

```c
void __fastcall ChLocalOfferRemoveThreadEntry(PVOID StartContext)
{
  while ( !ChLocalOfferRemoveThreadTerminate )
  {
    KeWaitForSingleObject(&ChLocalOfferRemoveThreadWake, Executive, 0, 0, 0);
    if ( ChLocalOfferRemoveThreadTerminate )
      break;
    ChDestroyChannelWorkItem();
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140010110  sub     rsp, 38h
0x140010114  jmp     short loc_140010148
0x140010116  xor     r9d, r9d; Alertable
0x140010119  mov     [rsp+38h+Timeout], 0; Timeout
0x140010122  xor     r8d, r8d; WaitMode
0x140010125  lea     rcx, ChLocalOfferRemoveThreadWake; Object
0x14001012c  xor     edx, edx; WaitReason
0x14001012e  call    cs:__imp_KeWaitForSingleObject
0x140010135  nop     dword ptr [rax+rax+00h]
0x14001013a  cmp     cs:ChLocalOfferRemoveThreadTerminate, 0
0x140010141  jnz     short loc_140010151
0x140010143  call    ChDestroyChannelWorkItem
0x140010148  cmp     cs:ChLocalOfferRemoveThreadTerminate, 0
0x14001014f  jz      short loc_140010116
0x140010151  xor     ecx, ecx; ExitStatus
0x140010153  call    cs:__imp_PsTerminateSystemThread
0x14001015a  nop     dword ptr [rax+rax+00h]
0x14001015f  add     rsp, 38h
0x140010163  retn
```
