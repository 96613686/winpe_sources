# SmpConfigureBackgroundLoadKnownDlls

- ea: `0x140013300`
- end: `0x140013316`
- name: `SmpConfigureBackgroundLoadKnownDlls`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140013300`

## pseudocode

```c
__int64 __fastcall SmpConfigureBackgroundLoadKnownDlls(__int64 a1, int a2, int *a3, int a4)
{
  if ( a2 == 4 && a4 == 4 )
    SmpLoadKnownDllsFlags = *a3;
  return 0;
}

```

## disassembly

```asm
0x140013300  cmp     edx, 4
0x140013303  jnz     short loc_140013313
0x140013305  cmp     r9d, edx
0x140013308  jnz     short loc_140013313
0x14001330a  mov     eax, [r8]
0x14001330d  mov     cs:SmpLoadKnownDllsFlags, eax
0x140013313  xor     eax, eax
0x140013315  retn
```
