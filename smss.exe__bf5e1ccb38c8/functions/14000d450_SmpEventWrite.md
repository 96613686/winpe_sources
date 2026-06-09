# SmpEventWrite

- ea: `0x14000d450`
- end: `0x14000d48e`
- name: `SmpEventWrite`
- size: `62`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000c638`
- `0x14000d418`
- `0x140015ae8`

## callees

- `0x14000d450`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x14000d482`
- `ntdll!EtwEventWrite` at `0x14000d482`
- `ntdll!EtwEventEnabled` at `0x14000d468`
- `ntdll!EtwEventEnabled` at `0x14000d468`

## pseudocode

```c
void __fastcall SmpEventWrite(PCEVENT_DESCRIPTOR EventDescriptor)
{
  if ( SmpTraceHandle )
  {
    if ( EtwEventEnabled(SmpTraceHandle, EventDescriptor) )
      EtwEventWrite(SmpTraceHandle, EventDescriptor, 0, 0);
  }
}

```

## disassembly

```asm
0x14000d450  push    rbx
0x14000d452  sub     rsp, 20h
0x14000d456  mov     rbx, rcx
0x14000d459  mov     rcx, cs:SmpTraceHandle; RegHandle
0x14000d460  test    rcx, rcx
0x14000d463  jz      short loc_14000D488
0x14000d465  mov     rdx, rbx; EventDescriptor
0x14000d468  call    cs:__imp_EtwEventEnabled
0x14000d46e  test    al, al
0x14000d470  jz      short loc_14000D488
0x14000d472  mov     rcx, cs:SmpTraceHandle
0x14000d479  xor     r9d, r9d
0x14000d47c  xor     r8d, r8d
0x14000d47f  mov     rdx, rbx
0x14000d482  call    cs:__imp_EtwEventWrite
0x14000d488  add     rsp, 20h
0x14000d48c  pop     rbx
0x14000d48d  retn
```
