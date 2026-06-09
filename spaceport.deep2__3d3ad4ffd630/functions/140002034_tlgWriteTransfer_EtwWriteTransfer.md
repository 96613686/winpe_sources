# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140002034`
- end: `0x1400020d2`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400011ac`
- `0x1400012f8`
- `0x140001480`
- `0x140001874`
- `0x140001a9c`
- `0x140001c0c`
- `0x140001e74`
- `0x1400020d8`
- `0x140002178`
- `0x140002260`
- `0x140002358`
- `0x14000264c`
- `0x14000284c`
- `0x1400028ec`
- `0x140002988`
- `0x140002a28`
- `0x140002ad8`
- `0x140002c94`
- `0x140002d8c`
- `0x140002e3c`
- `0x140002ee0`
- `0x1400030a4`
- `0x14000315c`
- `0x140003210`
- `0x1400032c4`
- `0x1400034dc`
- `0x140003680`
- `0x140003864`
- `0x140003918`
- `0x140038370`
- `0x140093f68`
- `0x14009a4d4`
- `0x14009f3d0`
- `0x1400a0500`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400020c0`
- `ntoskrnl!EtwWriteTransfer` at `0x1400020c0`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140002034  sub     rsp, 48h
0x140002038  movzx   eax, byte ptr [rdx]
0x14000203b  mov     r11, rcx
0x14000203e  shl     eax, 18h
0x140002041  mov     r10, r8
0x140002044  mov     r8, [rsp+48h+arg_28]
0x140002049  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000204d  movzx   eax, word ptr [rdx+1]
0x140002051  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140002055  mov     rax, [rdx+3]
0x140002059  add     rdx, 0Bh
0x14000205d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140002062  mov     rax, [rcx+8]
0x140002066  mov     [r8], rax
0x140002069  mov     rax, [rcx+8]
0x14000206d  mov     [rsp+48h+UserData], r8; UserData
0x140002072  movzx   ecx, word ptr [rax]
0x140002075  mov     [r8+8], ecx
0x140002079  lea     rcx, _TraceLoggingMetadata
0x140002080  mov     [r8+10h], rdx
0x140002084  mov     dword ptr [r8+0Ch], 2
0x14000208c  movzx   eax, word ptr [rdx]
0x14000208f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002094  mov     [r8+18h], eax
0x140002098  lea     rax, _TraceLoggingMetadataEnd
0x14000209f  sub     eax, ecx
0x1400020a1  mov     dword ptr [r8+1Ch], 1
0x1400020a9  mov     dword ptr [rsp+48h+arg_28], eax
0x1400020ad  mov     r8, r10; ActivityId
0x1400020b0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400020b4  mov     eax, [rsp+48h+arg_20]
0x1400020b8  mov     rcx, [r11+20h]; RegHandle
0x1400020bc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400020c0  call    cs:__imp_EtwWriteTransfer
0x1400020c7  nop     dword ptr [rax+rax+00h]
0x1400020cc  add     rsp, 48h
0x1400020d0  retn
```
