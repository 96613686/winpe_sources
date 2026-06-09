# _mi::MiApplication::Create_::_1_::dtor$0

- ea: `0x18002c5af`
- end: `0x18002c5d6`
- name: `_mi::MiApplication::Create_::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005a70`
- `0x18002c5af`

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
0x18002c5af  push    rbp
0x18002c5b1  sub     rsp, 20h
0x18002c5b5  mov     rbp, rdx
0x18002c5b8  mov     eax, [rbp+20h]
0x18002c5bb  and     eax, 1
0x18002c5be  test    eax, eax
0x18002c5c0  jz      short loc_18002C5CF
0x18002c5c2  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002c5c6  mov     rcx, [rbp+60h]
0x18002c5ca  call    ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
0x18002c5cf  add     rsp, 20h
0x18002c5d3  pop     rbp
0x18002c5d4  retn
```
