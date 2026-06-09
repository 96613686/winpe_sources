# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002c6c`
- end: `0x180002d1f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `37`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180001068`
- `0x180001314`
- `0x1800013e4`
- `0x18000145c`
- `0x1800014f0`
- `0x1800015e4`
- `0x1800016f8`
- `0x1800017a8`
- `0x180001890`
- `0x18000198c`
- `0x180001a2c`
- `0x180001ae0`
- `0x180001ba4`
- `0x180001c78`
- `0x180001d5c`
- `0x180001e30`
- `0x180001f08`
- `0x180001fc8`
- `0x1800020bc`
- `0x18000219c`
- `0x180002230`
- `0x180002460`
- `0x1800024f4`
- `0x180002598`
- `0x180002640`
- `0x1800028f4`
- `0x18000cd74`
- `0x18000cdf4`
- `0x180010d90`
- `0x180016760`
- `0x1800183c0`
- `0x180019414`
- `0x1800273f0`
- `0x180027950`
- `0x18002cc94`
- `0x18002cd54`

## callees

- `0x180004120`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002d07`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002d07`

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
0x180002c6c  sub     rsp, 58h
0x180002c70  mov     rax, cs:__security_cookie
0x180002c77  xor     rax, rsp
0x180002c7a  mov     [rsp+58h+var_10], rax
0x180002c7f  movzx   eax, byte ptr [rdx]
0x180002c82  mov     r11, rcx
0x180002c85  mov     r10, [rsp+58h+arg_28]
0x180002c8d  shl     eax, 18h
0x180002c90  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180002c94  movzx   eax, word ptr [rdx+1]
0x180002c98  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180002c9c  mov     rax, [rdx+3]
0x180002ca0  add     rdx, 0Bh
0x180002ca4  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180002ca9  mov     rax, [rcx+8]
0x180002cad  mov     [r10], rax
0x180002cb0  mov     rax, [rcx+8]
0x180002cb4  mov     [rsp+58h+UserData], r10; UserData
0x180002cb9  movzx   ecx, word ptr [rax]
0x180002cbc  mov     [r10+8], ecx
0x180002cc0  lea     rcx, _TraceLoggingMetadata
0x180002cc7  mov     [r10+10h], rdx
0x180002ccb  mov     dword ptr [r10+0Ch], 2
0x180002cd3  movzx   eax, word ptr [rdx]
0x180002cd6  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180002cdb  mov     [r10+18h], eax
0x180002cdf  lea     rax, _TraceLoggingMetadataEnd
0x180002ce6  sub     eax, ecx
0x180002ce8  mov     dword ptr [r10+1Ch], 1
0x180002cf0  mov     [rsp+58h+var_28], eax
0x180002cf4  mov     eax, [rsp+58h+var_28]
0x180002cf8  mov     eax, [rsp+58h+arg_20]
0x180002cff  mov     rcx, [r11+20h]; RegHandle
0x180002d03  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180002d07  call    cs:__imp_EventWriteTransfer
0x180002d0d  mov     rcx, [rsp+58h+var_10]
0x180002d12  xor     rcx, rsp; StackCookie
0x180002d15  call    __security_check_cookie
0x180002d1a  add     rsp, 58h
0x180002d1e  retn
```
