# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001078`
- end: `0x14000111a`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `162`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, __int64)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140014b20`
- `0x140014d30`
- `0x14001f4f4`
- `0x140020704`
- `0x140021fb4`
- `0x140023dfc`
- `0x14003a830`
- `0x140040244`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001108`
- `ntoskrnl!EtwWriteTransfer` at `0x140001108`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        ULONG UserDataCount,
        struct _EVENT_DATA_DESCRIPTOR *a6)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR v9; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v9.Keyword = v6;
  a6->Ptr = *(_QWORD *)(a1 + 8);
  a6->Size = **(unsigned __int16 **)(a1 + 8);
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001078  mov     r11, rsp
0x14000107b  mov     [r11+20h], r9
0x14000107f  sub     rsp, 48h
0x140001083  movzx   eax, byte ptr [rdx]
0x140001086  mov     r10, rcx
0x140001089  mov     r8, [rsp+48h+arg_28]
0x14000108e  xor     r9d, r9d; RelatedActivityId
0x140001091  shl     eax, 18h
0x140001094  mov     [rsp+48h+var_18], eax
0x140001098  movzx   eax, word ptr [rdx+1]
0x14000109c  mov     [rsp+48h+var_14], eax
0x1400010a0  mov     rax, [rdx+3]
0x1400010a4  add     rdx, 0Bh
0x1400010a8  mov     [r11-10h], rax
0x1400010ac  mov     rax, [rcx+8]
0x1400010b0  mov     [r8], rax
0x1400010b3  mov     rax, [rcx+8]
0x1400010b7  mov     [r11-20h], r8
0x1400010bb  movzx   ecx, word ptr [rax]
0x1400010be  mov     [r8+8], ecx
0x1400010c2  lea     rcx, _TraceLoggingMetadata
0x1400010c9  mov     [r8+10h], rdx
0x1400010cd  mov     dword ptr [r8+0Ch], 2
0x1400010d5  movzx   eax, word ptr [rdx]
0x1400010d8  lea     rdx, [r11-18h]; EventDescriptor
0x1400010dc  mov     [r8+18h], eax
0x1400010e0  lea     rax, _TraceLoggingMetadataEnd
0x1400010e7  sub     eax, ecx
0x1400010e9  mov     dword ptr [r8+1Ch], 1
0x1400010f1  mov     [rsp+48h+arg_18], eax
0x1400010f5  xor     r8d, r8d; ActivityId
0x1400010f8  mov     eax, [rsp+48h+arg_18]
0x1400010fc  mov     eax, [rsp+48h+arg_20]
0x140001100  mov     rcx, [r10+20h]; RegHandle
0x140001104  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001108  call    cs:__imp_EtwWriteTransfer
0x14000110f  nop     dword ptr [rax+rax+00h]
0x140001114  add     rsp, 48h
0x140001118  retn
```
