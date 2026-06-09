# IPxlatRemoveFiltersForInstance

- ea: `0x14001784c`
- end: `0x14001785d`
- name: `IPxlatRemoveFiltersForInstance`
- size: `17`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003363c`

## callees

- `0x140016aec`

## pseudocode

```c
__int64 __fastcall IPxlatRemoveFiltersForInstance(__int64 a1)
{
  return IPxlatConfigureFiltersForInstance(a1, 0);
}

```

## disassembly

```asm
0x14001784c  sub     rsp, 28h
0x140017850  xor     edx, edx
0x140017852  call    IPxlatConfigureFiltersForInstance
0x140017857  add     rsp, 28h
0x14001785b  retn
```
