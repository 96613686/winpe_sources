# IPxlatRemoveFiltersForInstance

- ea: `0x1400185a0`
- end: `0x1400185b1`
- name: `IPxlatRemoveFiltersForInstance`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003476c`

## callees

- `0x1400177b8`

## pseudocode

```c
__int64 __fastcall IPxlatRemoveFiltersForInstance(__int64 a1)
{
  return IPxlatConfigureFiltersForInstance(a1, 0);
}

```

## disassembly

```asm
0x1400185a0  sub     rsp, 28h
0x1400185a4  xor     edx, edx
0x1400185a6  call    IPxlatConfigureFiltersForInstance
0x1400185ab  add     rsp, 28h
0x1400185af  retn
```
