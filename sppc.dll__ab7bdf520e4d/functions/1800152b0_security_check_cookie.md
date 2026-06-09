# __security_check_cookie

- ea: `0x1800152b0`
- end: `0x1800152ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010ec`
- `0x180001430`
- `0x180001760`
- `0x180001a90`
- `0x180001ec0`
- `0x1800021b0`
- `0x180002610`
- `0x1800028f0`
- `0x180002bf0`
- `0x180003030`
- `0x180003410`
- `0x18000812c`
- `0x1800082f8`
- `0x180008dc8`
- `0x18000991c`
- `0x18000a1bc`
- `0x18000a8d0`
- `0x18000b64c`
- `0x18000fe2c`
- `0x1800119e0`
- `0x180012080`
- `0x180012420`
- `0x180013060`
- `0x180014550`
- `0x1800151fc`

## callees

- `0x1800040d0`
- `0x1800152b0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_1800040D0(StackCookie);
}

```

## disassembly

```asm
0x1800152b0  cmp     rcx, cs:__security_cookie
0x1800152b7  jnz     short loc_1800152C9
0x1800152b9  rol     rcx, 10h
0x1800152bd  test    cx, 0FFFFh
0x1800152c2  jnz     short loc_1800152C5
0x1800152c4  retn
0x1800152c5  ror     rcx, 10h
0x1800152c9  jmp     sub_1800040D0
```
