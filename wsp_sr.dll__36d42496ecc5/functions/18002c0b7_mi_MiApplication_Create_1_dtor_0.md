# _mi::MiApplication::Create_::_1_::dtor$0

- ea: `0x18002c0b7`
- end: `0x18002c0dd`
- name: `_mi::MiApplication::Create_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005a30`
- `0x18002c0b7`

## pseudocode

```c
void __fastcall mi::MiApplication::Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(*(_QWORD *)(a2 + 96));
  }
}

```

## disassembly

```asm
0x18002c0b7  push    rbp
0x18002c0b9  sub     rsp, 20h
0x18002c0bd  mov     rbp, rdx
0x18002c0c0  mov     eax, [rbp+20h]
0x18002c0c3  and     eax, 1
0x18002c0c6  test    eax, eax
0x18002c0c8  jz      short loc_18002C0D7
0x18002c0ca  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002c0ce  mov     rcx, [rbp+60h]
0x18002c0d2  call    ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
0x18002c0d7  add     rsp, 20h
0x18002c0db  pop     rbp
0x18002c0dc  retn
```
