# sub_18001CEDC

- ea: `0x18001cedc`
- end: `0x18001cf35`
- name: `sub_18001CEDC`
- size: `89`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a030`
- `0x18001a270`
- `0x18001cf3c`
- `0x18001cfe8`
- `0x18001d060`
- `0x18008d560`
- `0x18008fe1c`

## callees

- `0x18001cedc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cf23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cf23`

## pseudocode

```c
ULONG __fastcall sub_18001CEDC(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_1800E0028;
  if ( qword_1800E0028 )
  {
    UserData->Ptr = qword_1800E0028;
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
  return EventWriteTransfer(RegHandle, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001cedc  sub     rsp, 38h
0x18001cee0  mov     rcx, cs:qword_1800E0028
0x18001cee7  mov     rax, [rsp+38h+arg_20]
0x18001ceec  test    rcx, rcx
0x18001ceef  jnz     short loc_18001CEF9
0x18001cef1  mov     [rax], rcx
0x18001cef4  xor     r8d, r8d
0x18001cef7  jmp     short loc_18001CF05
0x18001cef9  mov     [rax], rcx
0x18001cefc  mov     r8d, 2
0x18001cf02  movzx   ecx, word ptr [rcx]
0x18001cf05  mov     [rax+8], ecx
0x18001cf08  mov     [rax+0Ch], r8d
0x18001cf0c  xor     r8d, r8d; ActivityId
0x18001cf0f  mov     rcx, cs:RegHandle; RegHandle
0x18001cf16  mov     [rsp+38h+UserData], rax; UserData
0x18001cf1b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001cf20  xor     r9d, r9d; RelatedActivityId
0x18001cf23  call    cs:EventWriteTransfer
0x18001cf2a  nop     dword ptr [rax+rax+00h]
0x18001cf2f  add     rsp, 38h
0x18001cf33  retn
```
