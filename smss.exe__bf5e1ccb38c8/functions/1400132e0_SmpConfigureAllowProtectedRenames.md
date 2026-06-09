# SmpConfigureAllowProtectedRenames

- ea: `0x1400132e0`
- end: `0x1400132f7`
- name: `SmpConfigureAllowProtectedRenames`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400132e0`

## pseudocode

```c
__int64 __fastcall SmpConfigureAllowProtectedRenames(__int64 a1, __int64 a2, _DWORD *a3, int a4)
{
  bool v4; // al

  v4 = 0;
  if ( a4 == 4 )
    v4 = *a3 != 0;
  SmpAllowProtectedRenames = v4;
  return 0;
}

```

## disassembly

```asm
0x1400132e0  xor     eax, eax
0x1400132e2  cmp     r9d, 4
0x1400132e6  jnz     short loc_1400132EE
0x1400132e8  cmp     [r8], eax
0x1400132eb  setnz   al
0x1400132ee  mov     cs:SmpAllowProtectedRenames, al
0x1400132f4  xor     eax, eax
0x1400132f6  retn
```
