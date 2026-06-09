# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400019f8`
- end: `0x140001a4e`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x140001a54`
- `0x140001a98`
- `0x140001b14`
- `0x140001f04`
- `0x140001f94`
- `0x140001ffc`
- `0x140002078`
- `0x140002108`
- `0x140002384`
- `0x1400065b0`
- `0x140006644`
- `0x1400066d4`
- `0x1400083b4`
- `0x14000c2bc`
- `0x14000f304`
- `0x14000f37c`
- `0x14001c570`
- `0x14001c5f4`
- `0x14001c674`
- `0x14001c704`
- `0x14001c7a4`
- `0x14001cad4`
- `0x14001cb98`
- `0x14002d794`
- `0x14002d868`
- `0x1400337f8`
- `0x1400338f8`
- `0x140041928`
- `0x1400419b0`

## callees

- `0x1400019f8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001a3c`
- `ntoskrnl!EtwWriteTransfer` at `0x140001a3c`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_14006B318;
  if ( qword_14006B318 )
  {
    UserData->Ptr = qword_14006B318;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(MS_USBHUB3_ETW_PROVIDER_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400019f8  sub     rsp, 38h
0x1400019fc  mov     rcx, cs:qword_14006B318
0x140001a03  mov     rax, [rsp+38h+arg_20]
0x140001a08  test    rcx, rcx
0x140001a0b  jnz     short loc_140001A15
0x140001a0d  mov     [rax], rcx
0x140001a10  xor     r10d, r10d
0x140001a13  jmp     short loc_140001A21
0x140001a15  mov     [rax], rcx
0x140001a18  mov     r10d, 2
0x140001a1e  movzx   ecx, word ptr [rcx]
0x140001a21  mov     [rax+8], ecx
0x140001a24  mov     [rsp+38h+UserData], rax; UserData
0x140001a29  mov     [rax+0Ch], r10d
0x140001a2d  mov     rcx, cs:MS_USBHUB3_ETW_PROVIDER_Context; RegHandle
0x140001a34  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140001a39  xor     r9d, r9d; RelatedActivityId
0x140001a3c  call    cs:__imp_EtwWriteTransfer
0x140001a43  nop     dword ptr [rax+rax+00h]
0x140001a48  add     rsp, 38h
0x140001a4c  retn
```
