# _mi::MiApplication::CreateSession_0__::_1_::dtor$1

- ea: `0x18002c582`
- end: `0x18002c5a9`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005a70`
- `0x18002c582`

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
0x18002c582  push    rbp
0x18002c584  sub     rsp, 20h
0x18002c588  mov     rbp, rdx
0x18002c58b  mov     eax, [rbp+20h]
0x18002c58e  and     eax, 1
0x18002c591  test    eax, eax
0x18002c593  jz      short loc_18002C5A2
0x18002c595  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002c599  mov     rcx, [rbp+78h]
0x18002c59d  call    ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
0x18002c5a2  add     rsp, 20h
0x18002c5a6  pop     rbp
0x18002c5a7  retn
```
