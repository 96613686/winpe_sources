# _mi::MiApplication::CreateInstance_::_1_::dtor$1

- ea: `0x18002c0e3`
- end: `0x18002c109`
- name: `_mi::MiApplication::CreateInstance_::_1_::dtor$1`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800268e4`
- `0x18002c0e3`

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
0x18002c0e3  push    rbp
0x18002c0e5  sub     rsp, 20h
0x18002c0e9  mov     rbp, rdx
0x18002c0ec  mov     eax, [rbp+30h]
0x18002c0ef  and     eax, 1
0x18002c0f2  test    eax, eax
0x18002c0f4  jz      short loc_18002C103
0x18002c0f6  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18002c0fa  mov     rcx, [rbp+38h]; this
0x18002c0fe  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18002c103  add     rsp, 20h
0x18002c107  pop     rbp
0x18002c108  retn
```
