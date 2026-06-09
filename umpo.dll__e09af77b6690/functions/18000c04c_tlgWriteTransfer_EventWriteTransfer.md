# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000c04c`
- end: `0x18000c0ed`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, ULONG UserDataCount, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002288`
- `0x180009b50`
- `0x180009f14`
- `0x18000c34c`
- `0x18000d080`
- `0x18000d2f4`
- `0x18000f6f4`
- `0x180015e68`
- `0x180015f78`
- `0x1800160e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0e2`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  a6->Ptr = (ULONGLONG)off_180024198;
  a6->Size = *(unsigned __int16 *)off_180024198;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x18000c04c  mov     r11, rsp
0x18000c04f  mov     [r11+20h], r9
0x18000c053  sub     rsp, 48h
0x18000c057  movzx   eax, byte ptr [rdx]
0x18000c05a  xor     r9d, r9d; RelatedActivityId
0x18000c05d  mov     r8, [rsp+48h+arg_28]
0x18000c062  shl     eax, 18h
0x18000c065  mov     [rsp+48h+var_18], eax
0x18000c069  movzx   eax, word ptr [rdx+1]
0x18000c06d  mov     [rsp+48h+var_14], eax
0x18000c071  mov     rax, [rdx+3]
0x18000c075  add     rdx, 0Bh
0x18000c079  mov     [r11-10h], rax
0x18000c07d  mov     rax, cs:off_180024198
0x18000c084  mov     [r8], rax
0x18000c087  mov     rax, cs:off_180024198
0x18000c08e  mov     [r11-20h], r8
0x18000c092  movzx   ecx, word ptr [rax]
0x18000c095  mov     [r8+8], ecx
0x18000c099  lea     rcx, _TraceLoggingMetadata
0x18000c0a0  mov     [r8+10h], rdx
0x18000c0a4  mov     dword ptr [r8+0Ch], 2
0x18000c0ac  movzx   eax, word ptr [rdx]
0x18000c0af  lea     rdx, [r11-18h]; EventDescriptor
0x18000c0b3  mov     [r8+18h], eax
0x18000c0b7  lea     rax, _TraceLoggingMetadataEnd
0x18000c0be  sub     eax, ecx
0x18000c0c0  mov     dword ptr [r8+1Ch], 1
0x18000c0c8  mov     [rsp+48h+arg_18], eax
0x18000c0cc  xor     r8d, r8d; ActivityId
0x18000c0cf  mov     eax, [rsp+48h+arg_18]
0x18000c0d3  mov     eax, [rsp+48h+arg_20]
0x18000c0d7  mov     rcx, cs:RegHandle; RegHandle
0x18000c0de  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000c0e2  call    cs:__imp_EventWriteTransfer
0x18000c0e8  add     rsp, 48h
0x18000c0ec  retn
```
