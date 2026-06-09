# McGenEventWrite_EtwWriteTransfer

- ea: `0x140003bf0`
- end: `0x140003c49`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039f0`
- `0x140003b00`

## callees

- `0x140003bf0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140003c37`
- `ntoskrnl!EtwWriteTransfer` at `0x140003c37`

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

  v5 = (unsigned __int16 *)qword_14000A008;
  if ( qword_14000A008 )
  {
    UserData->Ptr = qword_14000A008;
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
  return EtwWriteTransfer(StorageVolumeProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140003bf0  sub     rsp, 38h
0x140003bf4  mov     rcx, cs:qword_14000A008
0x140003bfb  mov     rax, [rsp+38h+arg_20]
0x140003c00  test    rcx, rcx
0x140003c03  jnz     short loc_140003C0D
0x140003c05  mov     [rax], rcx
0x140003c08  xor     r8d, r8d
0x140003c0b  jmp     short loc_140003C19
0x140003c0d  mov     [rax], rcx
0x140003c10  mov     r8d, 2
0x140003c16  movzx   ecx, word ptr [rcx]
0x140003c19  mov     [rax+8], ecx
0x140003c1c  mov     [rax+0Ch], r8d
0x140003c20  xor     r8d, r8d; ActivityId
0x140003c23  mov     rcx, cs:StorageVolumeProvider_Context; RegHandle
0x140003c2a  mov     [rsp+38h+UserData], rax; UserData
0x140003c2f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140003c34  xor     r9d, r9d; RelatedActivityId
0x140003c37  call    cs:__imp_EtwWriteTransfer
0x140003c3e  nop     dword ptr [rax+rax+00h]
0x140003c43  add     rsp, 38h
0x140003c47  retn
```
