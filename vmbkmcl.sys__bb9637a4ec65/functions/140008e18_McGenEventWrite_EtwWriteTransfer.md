# McGenEventWrite_EtwWriteTransfer

- ea: `0x140008e18`
- end: `0x140008e71`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008e78`
- `0x140008ef0`
- `0x140008f90`

## callees

- `0x140008e18`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140008e5f`
- `ntoskrnl!EtwWriteTransfer` at `0x140008e5f`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_140016018;
  if ( qword_140016018 )
  {
    UserData->Ptr = qword_140016018;
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
  return EtwWriteTransfer(VMBKMCL_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140008e18  sub     rsp, 38h
0x140008e1c  mov     rcx, cs:qword_140016018
0x140008e23  mov     rax, [rsp+38h+arg_20]
0x140008e28  test    rcx, rcx
0x140008e2b  jnz     short loc_140008E35
0x140008e2d  mov     [rax], rcx
0x140008e30  xor     r8d, r8d
0x140008e33  jmp     short loc_140008E41
0x140008e35  mov     [rax], rcx
0x140008e38  mov     r8d, 2
0x140008e3e  movzx   ecx, word ptr [rcx]
0x140008e41  mov     [rax+8], ecx
0x140008e44  mov     [rax+0Ch], r8d
0x140008e48  xor     r8d, r8d; ActivityId
0x140008e4b  mov     rcx, cs:VMBKMCL_PROVIDER_Context; RegHandle
0x140008e52  mov     [rsp+38h+UserData], rax; UserData
0x140008e57  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140008e5c  xor     r9d, r9d; RelatedActivityId
0x140008e5f  call    cs:__imp_EtwWriteTransfer
0x140008e66  nop     dword ptr [rax+rax+00h]
0x140008e6b  add     rsp, 38h
0x140008e6f  retn
```
