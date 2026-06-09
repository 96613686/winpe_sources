# CipIsCustomSigningPolicyActive

- ea: `0x180048398`
- end: `0x1800483ad`
- name: `CipIsCustomSigningPolicyActive`
- size: `21`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180010bd4`
- `0x180048080`
- `0x180048268`
- `0x1800482bc`
- `0x18004840c`
- `0x18004a364`

## callees

- `0x180048398`

## pseudocode

```c
bool CipIsCustomSigningPolicyActive()
{
  bool result; // al

  result = 0;
  if ( g_CiSignersCount )
    return dword_18003F200 != 0;
  return result;
}

```

## disassembly

```asm
0x180048398  xor     eax, eax
0x18004839a  cmp     cs:g_CiSignersCount, eax
0x1800483a0  jz      short locret_1800483AC
0x1800483a2  cmp     cs:dword_18003F200, eax
0x1800483a8  jz      short locret_1800483AC
0x1800483aa  mov     al, 1
0x1800483ac  retn
```
