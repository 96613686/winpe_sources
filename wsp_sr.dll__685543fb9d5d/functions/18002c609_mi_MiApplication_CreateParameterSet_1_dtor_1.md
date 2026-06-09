# _mi::MiApplication::CreateParameterSet_::_1_::dtor$1

- ea: `0x18002c609`
- end: `0x18002c633`
- name: `_mi::MiApplication::CreateParameterSet_::_1_::dtor$1`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180026c30`
- `0x18002c609`

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
0x18002c609  push    rbp
0x18002c60b  sub     rsp, 20h
0x18002c60f  mov     rbp, rdx
0x18002c612  mov     eax, [rbp+30h]
0x18002c615  and     eax, 1
0x18002c618  test    eax, eax
0x18002c61a  jz      short loc_18002C62C
0x18002c61c  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18002c620  mov     rcx, [rbp+88h]; this
0x18002c627  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18002c62c  add     rsp, 20h
0x18002c630  pop     rbp
0x18002c631  retn
```
