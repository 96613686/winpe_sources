# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001038`
- end: `0x1400010e0`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140007310`
- `0x14001ba40`
- `0x14001be40`
- `0x14001e4a0`
- `0x14001e7e4`
- `0x14001ea54`
- `0x14001ed50`
- `0x14001f2d0`
- `0x1400202cc`
- `0x1400204a4`
- `0x140022920`
- `0x14002a080`
- `0x14002a678`
- `0x14002a804`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010ce`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010ce`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
  a6->Ptr = (ULONGLONG)EventInformation;
  a6->Size = *(unsigned __int16 *)EventInformation;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &v9, a3, a4, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001038  mov     r11, rsp
0x14000103b  mov     [r11+8], rcx
0x14000103f  sub     rsp, 48h
0x140001043  movzx   eax, byte ptr [rdx]
0x140001046  mov     r10, r9
0x140001049  mov     r9, [rsp+48h+arg_28]
0x14000104e  shl     eax, 18h
0x140001051  mov     [rsp+48h+var_18], eax
0x140001055  movzx   eax, word ptr [rdx+1]
0x140001059  mov     [rsp+48h+var_14], eax
0x14000105d  mov     rax, [rdx+3]
0x140001061  add     rdx, 0Bh
0x140001065  mov     [r11-10h], rax
0x140001069  mov     rax, cs:EventInformation
0x140001070  mov     [r9], rax
0x140001073  mov     rax, cs:EventInformation
0x14000107a  mov     [r11-20h], r9
0x14000107e  movzx   ecx, word ptr [rax]
0x140001081  mov     [r9+8], ecx
0x140001085  lea     rcx, _TraceLoggingMetadata
0x14000108c  mov     [r9+10h], rdx
0x140001090  mov     dword ptr [r9+0Ch], 2
0x140001098  movzx   eax, word ptr [rdx]
0x14000109b  lea     rdx, [r11-18h]; EventDescriptor
0x14000109f  mov     [r9+18h], eax
0x1400010a3  lea     rax, _TraceLoggingMetadataEnd
0x1400010aa  sub     eax, ecx
0x1400010ac  mov     dword ptr [r9+1Ch], 1
0x1400010b4  mov     [rsp+48h+arg_0], eax
0x1400010b8  mov     r9, r10; RelatedActivityId
0x1400010bb  mov     eax, [rsp+48h+arg_0]
0x1400010bf  mov     eax, [rsp+48h+arg_20]
0x1400010c3  mov     rcx, cs:RegHandle; RegHandle
0x1400010ca  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010ce  call    cs:__imp_EtwWriteTransfer
0x1400010d5  nop     dword ptr [rax+rax+00h]
0x1400010da  add     rsp, 48h
0x1400010de  retn
```
