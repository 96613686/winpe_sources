# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180005a74`
- end: `0x180005b2e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `186`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180001118`
- `0x180001288`
- `0x1800013e0`
- `0x180001518`
- `0x180001630`
- `0x180001754`
- `0x180001858`
- `0x1800019a0`
- `0x180001ac8`
- `0x180001bc4`
- `0x180001cb8`
- `0x180001f6c`

## callees

- `0x180008a90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005b0f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005b0f`

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
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-20h] BYREF

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
0x180005a74  sub     rsp, 58h
0x180005a78  mov     rax, cs:__security_cookie
0x180005a7f  xor     rax, rsp
0x180005a82  mov     [rsp+58h+var_10], rax
0x180005a87  movzx   eax, byte ptr [rdx]
0x180005a8a  mov     r11, rcx
0x180005a8d  mov     r10, [rsp+58h+arg_28]
0x180005a95  shl     eax, 18h
0x180005a98  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180005a9c  movzx   eax, word ptr [rdx+1]
0x180005aa0  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180005aa4  mov     rax, [rdx+3]
0x180005aa8  add     rdx, 0Bh
0x180005aac  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180005ab1  mov     rax, [rcx+8]
0x180005ab5  mov     [r10], rax
0x180005ab8  mov     rax, [rcx+8]
0x180005abc  mov     [rsp+58h+UserData], r10; UserData
0x180005ac1  movzx   ecx, word ptr [rax]
0x180005ac4  mov     [r10+8], ecx
0x180005ac8  lea     rcx, _TraceLoggingMetadata
0x180005acf  mov     [r10+10h], rdx
0x180005ad3  mov     dword ptr [r10+0Ch], 2
0x180005adb  movzx   eax, word ptr [rdx]
0x180005ade  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180005ae3  mov     [r10+18h], eax
0x180005ae7  lea     rax, _TraceLoggingMetadataEnd
0x180005aee  sub     eax, ecx
0x180005af0  mov     dword ptr [r10+1Ch], 1
0x180005af8  mov     [rsp+58h+var_28], eax
0x180005afc  mov     eax, [rsp+58h+var_28]
0x180005b00  mov     eax, [rsp+58h+arg_20]
0x180005b07  mov     rcx, [r11+20h]; RegHandle
0x180005b0b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180005b0f  call    cs:__imp_EventWriteTransfer
0x180005b16  nop     dword ptr [rax+rax+00h]
0x180005b1b  mov     rcx, [rsp+58h+var_10]
0x180005b20  xor     rcx, rsp; StackCookie
0x180005b23  call    __security_check_cookie
0x180005b28  add     rsp, 58h
0x180005b2c  retn
```
