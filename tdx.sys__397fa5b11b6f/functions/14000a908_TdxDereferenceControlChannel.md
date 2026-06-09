# TdxDereferenceControlChannel

- ea: `0x14000a908`
- end: `0x14000a93b`
- name: `TdxDereferenceControlChannel`
- size: `51`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003840`
- `0x140009290`
- `0x140010b90`
- `0x140015780`

## callees

- `0x140008c50`
- `0x14000a908`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a928`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a928`

## pseudocode

```c
void __fastcall TdxDereferenceControlChannel(volatile signed __int32 *P)
{
  if ( _InterlockedExchangeAdd(P + 4, 0xFFFFFFFF) == 1 )
  {
    TdxCleanupObjectHeader((__int64)P);
    ExFreePoolWithTag((PVOID)P, 0);
  }
}

```

## disassembly

```asm
0x14000a908  push    rbx
0x14000a90a  sub     rsp, 20h
0x14000a90e  mov     rbx, rcx
0x14000a911  or      eax, 0FFFFFFFFh
0x14000a914  lock xadd [rcx+10h], eax
0x14000a919  cmp     eax, 1
0x14000a91c  jnz     short loc_14000A934
0x14000a91e  call    TdxCleanupObjectHeader
0x14000a923  xor     edx, edx; Tag
0x14000a925  mov     rcx, rbx; P
0x14000a928  call    cs:__imp_ExFreePoolWithTag
0x14000a92f  nop     dword ptr [rax+rax+00h]
0x14000a934  add     rsp, 20h
0x14000a938  pop     rbx
0x14000a939  retn
```
