# VMX_TRANSFER_PACKET::operator delete(void *)

- ea: `0x140004f40`
- end: `0x140004fb9`
- name: `??3VMX_TRANSFER_PACKET@@SAXPEAX@Z`
- size: `121`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x14000ac60`
- `0x14000ad20`
- `0x14000ade0`

## callees

- `0x140004f40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004fab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004f9b`

## pseudocode

```c
void __fastcall VMX_TRANSFER_PACKET::operator delete(_BYTE *Entry)
{
  char v1; // al

  if ( Entry )
  {
    v1 = Entry[80];
    switch ( v1 )
    {
      case 1:
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)WPP_MAIN_CB.DeviceExtension, Entry);
        break;
      case 2:
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)WPP_MAIN_CB.Queue.ListEntry.Flink, Entry);
        break;
      case 3:
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceType, Entry);
        break;
      default:
        ExFreePoolWithTag(Entry, 0);
        break;
    }
  }
}

```

## disassembly

```asm
0x140004f40  sub     rsp, 28h
0x140004f44  test    rcx, rcx
0x140004f47  jz      short loc_140004F67
0x140004f49  movzx   eax, byte ptr [rcx+50h]
0x140004f4d  cmp     al, 1
0x140004f4f  jnz     short loc_140004F6D
0x140004f51  mov     rdx, rcx; Entry
0x140004f54  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Lookaside
0x140004f5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004f62  nop     dword ptr [rax+rax+00h]
0x140004f67  add     rsp, 28h
0x140004f6b  retn
0x140004f6d  cmp     al, 2
0x140004f6f  jnz     short loc_140004F8D
0x140004f71  mov     rdx, rcx; Entry
0x140004f74  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x140004f7b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004f82  nop     dword ptr [rax+rax+00h]
0x140004f87  add     rsp, 28h
0x140004f8b  retn
0x140004f8d  cmp     al, 3
0x140004f8f  jnz     short loc_140004FA9
0x140004f91  mov     rdx, rcx; Entry
0x140004f94  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Lookaside
0x140004f9b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004fa2  nop     dword ptr [rax+rax+00h]
0x140004fa7  jmp     short loc_140004F67
0x140004fa9  xor     edx, edx; Tag
0x140004fab  call    cs:__imp_ExFreePoolWithTag
0x140004fb2  nop     dword ptr [rax+rax+00h]
0x140004fb7  jmp     short loc_140004F67
```
