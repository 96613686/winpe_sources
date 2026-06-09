# SIPolicyReadSecureSettingValueType

- ea: `0x1800217b0`
- end: `0x1800217c7`
- name: `SIPolicyReadSecureSettingValueType`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f33c`
- `0x18001f624`
- `0x18001f800`
- `0x18001ff54`

## callees

- `0x180021748`

## pseudocode

```c
__int64 __fastcall SIPolicyReadSecureSettingValueType(__int64 *a1, void *a2)
{
  return SIPolicyReadPrimitive(a1, 4u, a2);
}

```

## disassembly

```asm
0x1800217b0  sub     rsp, 28h
0x1800217b4  mov     r8, rdx
0x1800217b7  mov     edx, 4
0x1800217bc  call    SIPolicyReadPrimitive
0x1800217c1  add     rsp, 28h
0x1800217c5  retn
```
