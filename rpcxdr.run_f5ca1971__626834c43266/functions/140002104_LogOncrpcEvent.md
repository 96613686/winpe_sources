# LogOncrpcEvent

- ea: `0x140002104`
- end: `0x140002168`
- name: `LogOncrpcEvent`
- size: `100`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000350c`
- `0x14000377c`
- `0x140006f90`
- `0x1400085c0`
- `0x14000df80`
- `0x14000e8e0`
- `0x14000fa0c`
- `0x140010080`

## callees

- `0x140002104`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140002123`
- `ntoskrnl!EtwEventEnabled` at `0x140002123`
- `ntoskrnl!EtwWrite` at `0x14000214c`
- `ntoskrnl!EtwWrite` at `0x14000214c`

## pseudocode

```c
NTSTATUS __fastcall LogOncrpcEvent(PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId)
{
  if ( RegHandle && EtwEventEnabled(RegHandle, EventDescriptor) )
    return EtwWrite(RegHandle, EventDescriptor, ActivityId, 0, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x140002104  mov     [rsp+arg_0], rbx
0x140002109  push    rdi
0x14000210a  sub     rsp, 30h
0x14000210e  mov     rbx, rcx
0x140002111  mov     rdi, rdx
0x140002114  mov     rcx, cs:RegHandle; RegHandle
0x14000211b  test    rcx, rcx
0x14000211e  jz      short loc_14000215A
0x140002120  mov     rdx, rbx; EventDescriptor
0x140002123  call    cs:__imp_EtwEventEnabled
0x14000212a  nop     dword ptr [rax+rax+00h]
0x14000212f  test    al, al
0x140002131  jz      short loc_14000215A
0x140002133  mov     rcx, cs:RegHandle; RegHandle
0x14000213a  xor     r9d, r9d; UserDataCount
0x14000213d  mov     r8, rdi; ActivityId
0x140002140  mov     [rsp+38h+UserData], 0; UserData
0x140002149  mov     rdx, rbx; EventDescriptor
0x14000214c  call    cs:__imp_EtwWrite
0x140002153  nop     dword ptr [rax+rax+00h]
0x140002158  jmp     short loc_14000215C
0x14000215a  xor     eax, eax
0x14000215c  mov     rbx, [rsp+38h+arg_0]
0x140002161  add     rsp, 30h
0x140002165  pop     rdi
0x140002166  retn
```
