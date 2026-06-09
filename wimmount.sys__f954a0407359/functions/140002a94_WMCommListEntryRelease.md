# WMCommListEntryRelease

- ea: `0x140002a94`
- end: `0x140002afc`
- name: `WMCommListEntryRelease`
- size: `104`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009aa0`
- `0x14000a230`
- `0x14000a920`
- `0x14000aa34`
- `0x14000b9d8`

## callees

- `0x140002a94`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140002ab8`
- `ntoskrnl!ZwClose` at `0x140002ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ae9`
- `FLTMGR!FltCloseClientPort` at `0x140002ad5`
- `FLTMGR!FltCloseClientPort` at `0x140002ad5`

## pseudocode

```c
void __fastcall WMCommListEntryRelease(PVOID P)
{
  void *v2; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 4, 0xFFFFFFFF) == 1 && P )
  {
    v2 = (void *)*((_QWORD *)P + 6);
    if ( v2 )
      ZwClose(v2);
    if ( *((_QWORD *)P + 5) )
      FltCloseClientPort(gFilterHandle, (PFLT_PORT *)P + 5);
    ExFreePoolWithTag(P, 0x574D6365u);
  }
}

```

## disassembly

```asm
0x140002a94  push    rbx
0x140002a96  sub     rsp, 20h
0x140002a9a  mov     rbx, rcx
0x140002a9d  or      eax, 0FFFFFFFFh
0x140002aa0  lock xadd [rcx+10h], eax
0x140002aa5  cmp     eax, 1
0x140002aa8  jnz     short loc_140002AF5
0x140002aaa  test    rcx, rcx
0x140002aad  jz      short loc_140002AF5
0x140002aaf  mov     rcx, [rcx+30h]; Handle
0x140002ab3  test    rcx, rcx
0x140002ab6  jz      short loc_140002AC4
0x140002ab8  call    cs:__imp_ZwClose
0x140002abf  nop     dword ptr [rax+rax+00h]
0x140002ac4  lea     rdx, [rbx+28h]; ClientPort
0x140002ac8  cmp     qword ptr [rdx], 0
0x140002acc  jz      short loc_140002AE1
0x140002ace  mov     rcx, cs:gFilterHandle; Filter
0x140002ad5  call    cs:__imp_FltCloseClientPort
0x140002adc  nop     dword ptr [rax+rax+00h]
0x140002ae1  mov     edx, 574D6365h; Tag
0x140002ae6  mov     rcx, rbx; P
0x140002ae9  call    cs:__imp_ExFreePoolWithTag
0x140002af0  nop     dword ptr [rax+rax+00h]
0x140002af5  add     rsp, 20h
0x140002af9  pop     rbx
0x140002afa  retn
```
