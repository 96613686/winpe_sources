# McGenEventWrite_EtwWriteTransfer

- ea: `0x140004e78`
- end: `0x140004ed4`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004edc`

## callees

- `0x140004e78`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140004ec2`
- `ntoskrnl!EtwWriteTransfer` at `0x140004ec2`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_14000F0F8;
  if ( qword_14000F0F8 )
  {
    UserData->Ptr = qword_14000F0F8;
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
  return EtwWriteTransfer(USB_Redirector_Event_Provider_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x140004e78  sub     rsp, 38h
0x140004e7c  mov     rcx, cs:qword_14000F0F8
0x140004e83  mov     rax, [rsp+38h+arg_20]
0x140004e88  test    rcx, rcx
0x140004e8b  jnz     short loc_140004E95
0x140004e8d  mov     [rax], rcx
0x140004e90  xor     r8d, r8d
0x140004e93  jmp     short loc_140004EA1
0x140004e95  mov     [rax], rcx
0x140004e98  mov     r8d, 2
0x140004e9e  movzx   ecx, word ptr [rcx]
0x140004ea1  mov     [rax+8], ecx
0x140004ea4  xor     r9d, r9d; RelatedActivityId
0x140004ea7  mov     [rax+0Ch], r8d
0x140004eab  xor     r8d, r8d; ActivityId
0x140004eae  mov     rcx, cs:USB_Redirector_Event_Provider_Context; RegHandle
0x140004eb5  mov     [rsp+38h+UserData], rax; UserData
0x140004eba  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x140004ec2  call    cs:__imp_EtwWriteTransfer
0x140004ec9  nop     dword ptr [rax+rax+00h]
0x140004ece  add     rsp, 38h
0x140004ed2  retn
```
