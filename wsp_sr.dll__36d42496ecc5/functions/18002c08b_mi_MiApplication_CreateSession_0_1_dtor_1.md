# _mi::MiApplication::CreateSession_0__::_1_::dtor$1

- ea: `0x18002c08b`
- end: `0x18002c0b1`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$1`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005a30`
- `0x18002c08b`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_0__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(*(_QWORD *)(a2 + 120));
  }
}

```

## disassembly

```asm
0x18002c08b  push    rbp
0x18002c08d  sub     rsp, 20h
0x18002c091  mov     rbp, rdx
0x18002c094  mov     eax, [rbp+20h]
0x18002c097  and     eax, 1
0x18002c09a  test    eax, eax
0x18002c09c  jz      short loc_18002C0AB
0x18002c09e  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002c0a2  mov     rcx, [rbp+78h]
0x18002c0a6  call    ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
0x18002c0ab  add     rsp, 20h
0x18002c0af  pop     rbp
0x18002c0b0  retn
```
