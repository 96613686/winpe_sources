# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001350`
- end: `0x180001403`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000109c`
- `0x18000140c`
- `0x180001704`
- `0x1800017ec`
- `0x18000187c`
- `0x180001b20`
- `0x180001eb0`
- `0x180002204`
- `0x180017f20`
- `0x1800360f8`
- `0x1800362e4`
- `0x180036b44`
- `0x1800371e8`
- `0x1800373a8`

## callees

- `0x18008fe00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013eb`

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
0x180001350  sub     rsp, 58h
0x180001354  mov     rax, cs:__security_cookie
0x18000135b  xor     rax, rsp
0x18000135e  mov     [rsp+58h+var_10], rax
0x180001363  movzx   eax, byte ptr [rdx]
0x180001366  mov     r11, rcx
0x180001369  mov     r10, [rsp+58h+arg_28]
0x180001371  shl     eax, 18h
0x180001374  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001378  movzx   eax, word ptr [rdx+1]
0x18000137c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001380  mov     rax, [rdx+3]
0x180001384  add     rdx, 0Bh
0x180001388  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x18000138d  mov     rax, [rcx+8]
0x180001391  mov     [r10], rax
0x180001394  mov     rax, [rcx+8]
0x180001398  mov     [rsp+58h+UserData], r10; UserData
0x18000139d  movzx   ecx, word ptr [rax]
0x1800013a0  mov     [r10+8], ecx
0x1800013a4  lea     rcx, _TraceLoggingMetadata
0x1800013ab  mov     [r10+10h], rdx
0x1800013af  mov     dword ptr [r10+0Ch], 2
0x1800013b7  movzx   eax, word ptr [rdx]
0x1800013ba  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800013bf  mov     [r10+18h], eax
0x1800013c3  lea     rax, _TraceLoggingMetadataEnd
0x1800013ca  sub     eax, ecx
0x1800013cc  mov     dword ptr [r10+1Ch], 1
0x1800013d4  mov     [rsp+58h+var_28], eax
0x1800013d8  mov     eax, [rsp+58h+var_28]
0x1800013dc  mov     eax, [rsp+58h+arg_20]
0x1800013e3  mov     rcx, [r11+20h]; RegHandle
0x1800013e7  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800013eb  call    cs:__imp_EventWriteTransfer
0x1800013f1  mov     rcx, [rsp+58h+var_10]
0x1800013f6  xor     rcx, rsp; StackCookie
0x1800013f9  call    __security_check_cookie
0x1800013fe  add     rsp, 58h
0x180001402  retn
```
