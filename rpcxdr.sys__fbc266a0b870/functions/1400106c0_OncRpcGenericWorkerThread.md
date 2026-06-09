# OncRpcGenericWorkerThread

- ea: `0x1400106c0`
- end: `0x1400107ca`
- name: `OncRpcGenericWorkerThread`
- size: `266`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b1b8`
- `0x1400106c0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400107b6`
- `ntoskrnl!KeClearEvent` at `0x1400107b6`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140010705`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140010705`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400106eb`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400106eb`
- `ntoskrnl!KeSetEvent` at `0x140010724`
- `ntoskrnl!KeSetEvent` at `0x140010724`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140010785`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140010785`

## pseudocode

```c
void __fastcall OncRpcGenericWorkerThread(PVOID StartContext)
{
  NTSTATUS v1; // eax
  int v2; // eax
  PVOID Object[3]; // [rsp+40h] [rbp-18h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+68h] [rbp+10h] BYREF

  Timeout.QuadPart = 0;
  *((_QWORD *)DeviceExtension + 15) = KeGetCurrentThread();
  IoSetThreadHardErrorMode(0);
  KeSetBasePriorityThread(KeGetCurrentThread(), 5);
  KeSetEvent((PRKEVENT)((char *)DeviceExtension + 136), 0, 0);
  Object[0] = (char *)DeviceExtension + 160;
  Object[1] = (char *)DeviceExtension + 184;
LABEL_2:
  Timeout.QuadPart = -300000000;
  while ( 1 )
  {
    v1 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
    if ( !v1 )
      break;
    v2 = v1 - 1;
    if ( v2 )
    {
      if ( v2 == 257 )
        goto LABEL_2;
    }
    else
    {
      OncRpcSepInboundFreeOrphanGssCtx();
      KeClearEvent((PRKEVENT)((char *)DeviceExtension + 184));
    }
  }
}

```

## disassembly

```asm
0x1400106c0  sub     rsp, 58h
0x1400106c4  xorps   xmm0, xmm0
0x1400106c7  mov     qword ptr [rsp+58h+arg_8], 0
0x1400106d0  movups  xmmword ptr [rsp+58h+Object], xmm0
0x1400106d5  mov     rcx, gs:188h
0x1400106de  mov     rax, cs:DeviceExtension
0x1400106e5  mov     [rax+78h], rcx
0x1400106e9  xor     ecx, ecx; EnableHardErrors
0x1400106eb  call    cs:__imp_IoSetThreadHardErrorMode
0x1400106f2  nop     dword ptr [rax+rax+00h]
0x1400106f7  mov     rcx, gs:188h; Thread
0x140010700  mov     edx, 5; Increment
0x140010705  call    cs:__imp_KeSetBasePriorityThread
0x14001070c  nop     dword ptr [rax+rax+00h]
0x140010711  mov     rcx, cs:DeviceExtension
0x140010718  xor     r8d, r8d; Wait
0x14001071b  add     rcx, 88h; Event
0x140010722  xor     edx, edx; Increment
0x140010724  call    cs:__imp_KeSetEvent
0x14001072b  nop     dword ptr [rax+rax+00h]
0x140010730  mov     rcx, cs:DeviceExtension
0x140010737  lea     rax, [rcx+0A0h]
0x14001073e  mov     [rsp+58h+Object], rax
0x140010743  lea     rax, [rcx+0B8h]
0x14001074a  mov     [rsp+58h+Object+8], rax
0x14001074f  mov     qword ptr [rsp+58h+arg_8], 0FFFFFFFFEE1E5D00h
0x140010758  xor     r9d, r9d; WaitReason
0x14001075b  mov     [rsp+58h+WaitBlockArray], 0; WaitBlockArray
0x140010764  lea     rax, [rsp+58h+arg_8]
0x140010769  mov     [rsp+58h+Timeout], rax; Timeout
0x14001076e  lea     rdx, [rsp+58h+Object]; Object
0x140010773  mov     [rsp+58h+Alertable], 0; Alertable
0x140010778  lea     r8d, [r9+1]; WaitType
0x14001077c  mov     [rsp+58h+WaitMode], 0; WaitMode
0x140010781  lea     ecx, [r9+2]; Count
0x140010785  call    cs:__imp_KeWaitForMultipleObjects
0x14001078c  nop     dword ptr [rax+rax+00h]
0x140010791  test    eax, eax
0x140010793  jz      short loc_1400107C4
0x140010795  sub     eax, 1
0x140010798  jz      short loc_1400107A3
0x14001079a  cmp     eax, 101h
0x14001079f  jnz     short loc_140010758
0x1400107a1  jmp     short loc_14001074F
0x1400107a3  call    OncRpcSepInboundFreeOrphanGssCtx
0x1400107a8  mov     rcx, cs:DeviceExtension
0x1400107af  add     rcx, 0B8h; Event
0x1400107b6  call    cs:__imp_KeClearEvent
0x1400107bd  nop     dword ptr [rax+rax+00h]
0x1400107c2  jmp     short loc_140010758
0x1400107c4  add     rsp, 58h
0x1400107c8  retn
```
