# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400120f4`
- end: `0x140012154`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001215c`

## callees

- `0x1400120f4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140012142`
- `ntoskrnl!EtwWriteTransfer` at `0x140012142`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_14001C108;
  if ( qword_14001C108 )
  {
    UserData->Ptr = qword_14001C108;
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
  return EtwWriteTransfer(VMBUS_PROVIDER_Context, &VMBUSCLASS_WRONG_VERSION_CLIENT, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x1400120f4  sub     rsp, 38h
0x1400120f8  mov     rcx, cs:qword_14001C108
0x1400120ff  mov     rax, [rsp+38h+arg_20]
0x140012104  test    rcx, rcx
0x140012107  jnz     short loc_140012110
0x140012109  mov     [rax], rcx
0x14001210c  xor     edx, edx
0x14001210e  jmp     short loc_14001211B
0x140012110  mov     [rax], rcx
0x140012113  mov     edx, 2
0x140012118  movzx   ecx, word ptr [rcx]
0x14001211b  mov     [rax+8], ecx
0x14001211e  xor     r9d, r9d; RelatedActivityId
0x140012121  mov     [rax+0Ch], edx
0x140012124  xor     r8d, r8d; ActivityId
0x140012127  mov     rcx, cs:VMBUS_PROVIDER_Context; RegHandle
0x14001212e  lea     rdx, VMBUSCLASS_WRONG_VERSION_CLIENT; EventDescriptor
0x140012135  mov     [rsp+38h+UserData], rax; UserData
0x14001213a  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x140012142  call    cs:__imp_EtwWriteTransfer
0x140012149  nop     dword ptr [rax+rax+00h]
0x14001214e  add     rsp, 38h
0x140012152  retn
```
