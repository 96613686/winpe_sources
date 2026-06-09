# WinNatDereferenceGlobal

- ea: `0x14000c440`
- end: `0x14000c474`
- name: `WinNatDereferenceGlobal`
- size: `52`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f188`
- `0x14000f9a4`
- `0x1400136f0`
- `0x14002f4e0`
- `0x1400311f4`
- `0x140032430`
- `0x140033e5c`

## callees

- `0x14000c440`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c462`
- `ntoskrnl!KeSetEvent` at `0x14000c462`

## pseudocode

```c
LONG WinNatDereferenceGlobal()
{
  LONG result; // eax

  result = _InterlockedExchangeAdd(&dword_140027A84, 0xFFFFFFFE);
  if ( result == 3 )
    return KeSetEvent(&Event, 0, 0);
  return result;
}

```

## disassembly

```asm
0x14000c440  sub     rsp, 28h
0x14000c444  mov     eax, 0FFFFFFFEh
0x14000c449  lock xadd cs:dword_140027A84, eax
0x14000c451  cmp     eax, 3
0x14000c454  jnz     short loc_14000C46E
0x14000c456  xor     r8d, r8d; Wait
0x14000c459  lea     rcx, Event; Event
0x14000c460  xor     edx, edx; Increment
0x14000c462  call    cs:__imp_KeSetEvent
0x14000c469  nop     dword ptr [rax+rax+00h]
0x14000c46e  add     rsp, 28h
0x14000c472  retn
```
