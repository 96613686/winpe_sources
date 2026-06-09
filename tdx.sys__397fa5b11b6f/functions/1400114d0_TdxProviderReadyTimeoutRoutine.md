# TdxProviderReadyTimeoutRoutine

- ea: `0x1400114d0`
- end: `0x140011543`
- name: `TdxProviderReadyTimeoutRoutine`
- size: `115`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400114d0`
- `0x140013c84`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140011531`
- `ntoskrnl!IoQueueWorkItem` at `0x140011531`

## string_xrefs

- `0x1400114fc`: `TdxProviderReadyTimeoutRoutine`

## pseudocode

```c
void __fastcall TdxProviderReadyTimeoutRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      (unsigned int)WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
      (unsigned int)"TdxProviderReadyTimeoutRoutine",
      SBYTE4(qword_14001E508));
  }
  IoQueueWorkItem(qword_14001E500, (PIO_WORKITEM_ROUTINE)TdxProviderReadyWorkItemRoutine, DelayedWorkQueue, 0);
}

```

## disassembly

```asm
0x1400114d0  sub     rsp, 38h
0x1400114d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114db  lea     rax, WPP_GLOBAL_Control
0x1400114e2  cmp     rcx, rax
0x1400114e5  jz      short loc_14001151C
0x1400114e7  cmp     byte ptr [rcx+29h], 3
0x1400114eb  jb      short loc_14001151C
0x1400114ed  test    dword ptr [rcx+2Ch], 200h
0x1400114f4  jz      short loc_14001151C
0x1400114f6  mov     eax, dword ptr cs:qword_14001E508+4
0x1400114fc  lea     r9, aTdxproviderrea; "TdxProviderReadyTimeoutRoutine"
0x140011503  mov     rcx, [rcx+18h]
0x140011507  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14001150e  mov     edx, 32h ; '2'
0x140011513  mov     [rsp+38h+var_18], eax
0x140011517  call    WPP_SF_sd
0x14001151c  mov     rcx, cs:qword_14001E500; IoWorkItem
0x140011523  lea     rdx, TdxProviderReadyWorkItemRoutine; WorkerRoutine
0x14001152a  xor     r9d, r9d; Context
0x14001152d  lea     r8d, [r9+1]; QueueType
0x140011531  call    cs:__imp_IoQueueWorkItem
0x140011538  nop     dword ptr [rax+rax+00h]
0x14001153d  add     rsp, 38h
0x140011541  retn
```
