# IsHTTPv2Protocol(int)

- ea: `0x18000eebc`
- end: `0x18000eed4`
- name: `?IsHTTPv2Protocol@@YAHH@Z`
- size: `24`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b4c0`
- `0x18000bd30`
- `0x18000caf0`

## callees

- `0x18000eebc`

## pseudocode

```c
_BOOL8 __fastcall IsHTTPv2Protocol(int a1)
{
  return ((a1 - 10) & 0xFFFFFFFC) == 0 && a1 != 12;
}

```

## disassembly

```asm
0x18000eebc  lea     eax, [rcx-0Ah]
0x18000eebf  test    eax, 0FFFFFFFCh
0x18000eec4  jnz     short loc_18000EED1
0x18000eec6  cmp     ecx, 0Ch
0x18000eec9  jz      short loc_18000EED1
0x18000eecb  mov     eax, 1
0x18000eed0  retn
0x18000eed1  xor     eax, eax
0x18000eed3  retn
```
