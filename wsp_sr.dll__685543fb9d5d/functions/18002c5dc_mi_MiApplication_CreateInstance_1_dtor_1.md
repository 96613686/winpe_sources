# _mi::MiApplication::CreateInstance_::_1_::dtor$1

- ea: `0x18002c5dc`
- end: `0x18002c603`
- name: `_mi::MiApplication::CreateInstance_::_1_::dtor$1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180026c30`
- `0x18002c5dc`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    mi::MiInstance::~MiInstance(*(std::_Ref_count_base ***)(a2 + 56));
  }
}

```

## disassembly

```asm
0x18002c5dc  push    rbp
0x18002c5de  sub     rsp, 20h
0x18002c5e2  mov     rbp, rdx
0x18002c5e5  mov     eax, [rbp+30h]
0x18002c5e8  and     eax, 1
0x18002c5eb  test    eax, eax
0x18002c5ed  jz      short loc_18002C5FC
0x18002c5ef  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18002c5f3  mov     rcx, [rbp+38h]; this
0x18002c5f7  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18002c5fc  add     rsp, 20h
0x18002c600  pop     rbp
0x18002c601  retn
```
