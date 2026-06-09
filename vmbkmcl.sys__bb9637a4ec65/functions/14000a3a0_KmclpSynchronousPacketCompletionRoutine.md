# KmclpSynchronousPacketCompletionRoutine

- ea: `0x14000a3a0`
- end: `0x14000a3d3`
- name: `KmclpSynchronousPacketCompletionRoutine`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a3a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000a3c1`
- `ntoskrnl!KeSetEvent` at `0x14000a3c1`

## pseudocode

```c
LONG __fastcall KmclpSynchronousPacketCompletionRoutine(__int64 a1, LONG a2)
{
  struct _KEVENT *v2; // rcx

  if ( (unsigned int)(*(_DWORD *)(a1 + 24) - 1) > 4 )
    __fastfail(5u);
  v2 = *(struct _KEVENT **)(a1 + 32);
  v2[1].Header.LockNV = a2;
  return KeSetEvent(v2, 0, 0);
}

```

## disassembly

```asm
0x14000a3a0  sub     rsp, 28h
0x14000a3a4  mov     eax, [rcx+18h]
0x14000a3a7  dec     eax
0x14000a3a9  cmp     eax, 4
0x14000a3ac  jbe     short loc_14000A3B5
0x14000a3ae  mov     ecx, 5
0x14000a3b3  int     29h; Win8: RtlFailFast(ecx)
0x14000a3b5  mov     rcx, [rcx+20h]; Event
0x14000a3b9  xor     r8d, r8d; Wait
0x14000a3bc  mov     [rcx+18h], edx
0x14000a3bf  xor     edx, edx; Increment
0x14000a3c1  call    cs:__imp_KeSetEvent
0x14000a3c8  nop     dword ptr [rax+rax+00h]
0x14000a3cd  add     rsp, 28h
0x14000a3d1  retn
```
