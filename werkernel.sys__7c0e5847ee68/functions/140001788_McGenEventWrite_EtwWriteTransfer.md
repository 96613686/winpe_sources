# McGenEventWrite_EtwWriteTransfer

- ea: `0x140001788`
- end: `0x1400017e1`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `NTSTATUS __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400017e8`
- `0x1400018bc`

## callees

- `0x140001788`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400017cf`
- `ntoskrnl!EtwWriteTransfer` at `0x1400017cf`

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

  v5 = (unsigned __int16 *)qword_140009008;
  if ( qword_140009008 )
  {
    UserData->Ptr = qword_140009008;
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
  return EtwWriteTransfer(WERKERNEL_EVENT_PROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001788  sub     rsp, 38h
0x14000178c  mov     rcx, cs:qword_140009008
0x140001793  mov     rax, [rsp+38h+arg_20]
0x140001798  test    rcx, rcx
0x14000179b  jnz     short loc_1400017A5
0x14000179d  mov     [rax], rcx
0x1400017a0  xor     r8d, r8d
0x1400017a3  jmp     short loc_1400017B1
0x1400017a5  mov     [rax], rcx
0x1400017a8  mov     r8d, 2
0x1400017ae  movzx   ecx, word ptr [rcx]
0x1400017b1  mov     [rax+8], ecx
0x1400017b4  mov     [rax+0Ch], r8d
0x1400017b8  xor     r8d, r8d; ActivityId
0x1400017bb  mov     rcx, cs:WERKERNEL_EVENT_PROVIDER_GUID_Context; RegHandle
0x1400017c2  mov     [rsp+38h+UserData], rax; UserData
0x1400017c7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400017cc  xor     r9d, r9d; RelatedActivityId
0x1400017cf  call    cs:__imp_EtwWriteTransfer
0x1400017d6  nop     dword ptr [rax+rax+00h]
0x1400017db  add     rsp, 38h
0x1400017df  retn
```
