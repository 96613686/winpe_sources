# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001b98`
- end: `0x180001c2f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010c0`
- `0x180001374`
- `0x1800013e4`
- `0x180001474`
- `0x180001718`
- `0x180001c38`
- `0x180001d2c`
- `0x180001e24`
- `0x180001f18`
- `0x180001fe0`
- `0x180002088`
- `0x1800021b0`
- `0x180002294`
- `0x18000235c`
- `0x1800024ac`
- `0x1800025c4`
- `0x1800026ec`
- `0x1800027b4`
- `0x1800086b0`
- `0x180041ef0`
- `0x18004a79c`
- `0x18004b0c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c24`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c24`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180001b98  sub     rsp, 48h
0x180001b9c  movzx   eax, byte ptr [rdx]
0x180001b9f  mov     r11, rcx
0x180001ba2  shl     eax, 18h
0x180001ba5  mov     r10, r8
0x180001ba8  mov     r8, [rsp+48h+arg_28]
0x180001bad  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001bb1  movzx   eax, word ptr [rdx+1]
0x180001bb5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001bb9  mov     rax, [rdx+3]
0x180001bbd  add     rdx, 0Bh
0x180001bc1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001bc6  mov     rax, [rcx+8]
0x180001bca  mov     [r8], rax
0x180001bcd  mov     rax, [rcx+8]
0x180001bd1  mov     [rsp+48h+UserData], r8; UserData
0x180001bd6  movzx   ecx, word ptr [rax]
0x180001bd9  mov     [r8+8], ecx
0x180001bdd  lea     rcx, _TraceLoggingMetadata
0x180001be4  mov     [r8+10h], rdx
0x180001be8  mov     dword ptr [r8+0Ch], 2
0x180001bf0  movzx   eax, word ptr [rdx]
0x180001bf3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001bf8  mov     [r8+18h], eax
0x180001bfc  lea     rax, _TraceLoggingMetadataEnd
0x180001c03  sub     eax, ecx
0x180001c05  mov     dword ptr [r8+1Ch], 1
0x180001c0d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001c11  mov     r8, r10; ActivityId
0x180001c14  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001c18  mov     eax, [rsp+48h+arg_20]
0x180001c1c  mov     rcx, [r11+20h]; RegHandle
0x180001c20  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001c24  call    cs:__imp_EventWriteTransfer
0x180001c2a  add     rsp, 48h
0x180001c2e  retn
```
