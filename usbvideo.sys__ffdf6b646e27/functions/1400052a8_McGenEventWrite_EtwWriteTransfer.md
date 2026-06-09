# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400052a8`
- end: `0x140005301`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005238`
- `0x140005308`
- `0x1400054c0`
- `0x140018990`
- `0x14001b37c`
- `0x14001b558`
- `0x14001d7bc`
- `0x14001f460`
- `0x1400230e8`
- `0x1400400cc`

## callees

- `0x1400052a8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400052e1`
- `ntoskrnl!EtwWriteTransfer` at `0x1400052e1`

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

  v5 = (unsigned __int16 *)qword_14004C1A8;
  if ( qword_14004C1A8 )
  {
    UserData->Ptr = qword_14004C1A8;
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
  return EtwWriteTransfer(Microsoft_Windows_USBVideo_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400052a8  sub     rsp, 38h
0x1400052ac  mov     rcx, cs:qword_14004C1A8
0x1400052b3  mov     rax, [rsp+38h+arg_20]
0x1400052b8  test    rcx, rcx
0x1400052bb  jnz     short loc_1400052F3
0x1400052bd  mov     [rax], rcx
0x1400052c0  xor     r8d, r8d
0x1400052c3  mov     [rax+8], ecx
0x1400052c6  mov     [rax+0Ch], r8d
0x1400052ca  xor     r8d, r8d; ActivityId
0x1400052cd  mov     rcx, cs:Microsoft_Windows_USBVideo_Context; RegHandle
0x1400052d4  mov     [rsp+38h+UserData], rax; UserData
0x1400052d9  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400052de  xor     r9d, r9d; RelatedActivityId
0x1400052e1  call    cs:__imp_EtwWriteTransfer
0x1400052e8  nop     dword ptr [rax+rax+00h]
0x1400052ed  add     rsp, 38h
0x1400052f1  retn
0x1400052f3  mov     [rax], rcx
0x1400052f6  mov     r8d, 2
0x1400052fc  movzx   ecx, word ptr [rcx]
0x1400052ff  jmp     short loc_1400052C3
```
