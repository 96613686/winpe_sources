# _mi::MiApplication::CreateParameterSet_::_1_::dtor$1

- ea: `0x18002c10f`
- end: `0x18002c138`
- name: `_mi::MiApplication::CreateParameterSet_::_1_::dtor$1`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800268e4`
- `0x18002c10f`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateParameterSet_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    mi::MiInstance::~MiInstance(*(std::_Ref_count_base ***)(a2 + 136));
  }
}

```

## disassembly

```asm
0x18002c10f  push    rbp
0x18002c111  sub     rsp, 20h
0x18002c115  mov     rbp, rdx
0x18002c118  mov     eax, [rbp+30h]
0x18002c11b  and     eax, 1
0x18002c11e  test    eax, eax
0x18002c120  jz      short loc_18002C132
0x18002c122  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18002c126  mov     rcx, [rbp+88h]; this
0x18002c12d  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18002c132  add     rsp, 20h
0x18002c136  pop     rbp
0x18002c137  retn
```
