# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x180001008`
- end: `0x1800010c5`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010cc`
- `0x1800011ec`

## callees

- `0x1800428e4`

## import_xrefs

- `ADVAPI32!EventWriteEx` at `0x1800010b6`
- `ADVAPI32!EventWriteEx` at `0x1800010b6`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_BrowserWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v9; // rax
  unsigned __int16 *v10; // rdx
  ULONG BrowserEventFlags; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-38h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v9 = *(_QWORD *)(a2 + 3);
  v10 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v9;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v10;
  UserData[1].Size = *v10;
  UserData[1].Reserved = 1;
  BrowserEventFlags = GetBrowserEventFlags((const struct _EVENT_DESCRIPTOR *)&TraceLoggingMetadata);
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, BrowserEventFlags, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180001008  push    rbx
0x18000100a  push    rbp
0x18000100b  push    rsi
0x18000100c  push    rdi
0x18000100d  sub     rsp, 58h
0x180001011  movzx   eax, byte ptr [rdx]
0x180001014  mov     rbp, rcx
0x180001017  mov     rbx, [rsp+78h+arg_28]
0x18000101f  mov     rdi, r9
0x180001022  shl     eax, 18h
0x180001025  mov     rsi, r8
0x180001028  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x18000102c  movzx   eax, word ptr [rdx+1]
0x180001030  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x180001034  mov     rax, [rdx+3]
0x180001038  add     rdx, 0Bh
0x18000103c  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x180001041  mov     rax, [rcx+8]
0x180001045  mov     [rbx], rax
0x180001048  mov     rax, [rcx+8]
0x18000104c  movzx   ecx, word ptr [rax]
0x18000104f  mov     [rbx+8], ecx
0x180001052  lea     rcx, _TraceLoggingMetadata; struct _EVENT_DESCRIPTOR *
0x180001059  mov     dword ptr [rbx+0Ch], 2
0x180001060  mov     [rbx+10h], rdx
0x180001064  movzx   eax, word ptr [rdx]
0x180001067  mov     [rbx+18h], eax
0x18000106a  lea     rax, _TraceLoggingMetadataEnd
0x180001071  sub     eax, ecx
0x180001073  mov     dword ptr [rbx+1Ch], 1
0x18000107a  mov     dword ptr [rsp+78h+arg_28], eax
0x180001081  mov     eax, dword ptr [rsp+78h+arg_28]
0x180001088  call    ?GetBrowserEventFlags@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; GetBrowserEventFlags(_EVENT_DESCRIPTOR const *)
0x18000108d  mov     ecx, [rsp+78h+arg_20]
0x180001094  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x180001099  mov     [rsp+78h+UserData], rbx; UserData
0x18000109e  mov     r9d, eax; Flags
0x1800010a1  mov     [rsp+78h+UserDataCount], ecx; UserDataCount
0x1800010a5  xor     r8d, r8d; Filter
0x1800010a8  mov     rcx, [rbp+20h]; RegHandle
0x1800010ac  mov     [rsp+78h+RelatedActivityId], rdi; RelatedActivityId
0x1800010b1  mov     [rsp+78h+ActivityId], rsi; ActivityId
0x1800010b6  call    cs:__imp_EventWriteEx
0x1800010bc  add     rsp, 58h
0x1800010c0  pop     rdi
0x1800010c1  pop     rsi
0x1800010c2  pop     rbp
0x1800010c3  pop     rbx
0x1800010c4  retn
```
