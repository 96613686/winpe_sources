# _mi::MiCreator_mi::MiInstance_::Create_::_1_::dtor$0

- ea: `0x18002b2f7`
- end: `0x18002b31e`
- name: `_mi::MiCreator_mi::MiInstance_::Create_::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180026c30`
- `0x18002b2f7`

## pseudocode

```c
void __fastcall mi::MiCreator_mi::MiInstance_::Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    mi::MiInstance::~MiInstance(*(std::_Ref_count_base ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18002b2f7  push    rbp
0x18002b2f9  sub     rsp, 20h
0x18002b2fd  mov     rbp, rdx
0x18002b300  mov     eax, [rbp+20h]
0x18002b303  and     eax, 1
0x18002b306  test    eax, eax
0x18002b308  jz      short loc_18002B317
0x18002b30a  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002b30e  mov     rcx, [rbp+40h]; this
0x18002b312  call    ??1MiInstance@mi@@QEAA@XZ
0x18002b317  add     rsp, 20h
0x18002b31b  pop     rbp
0x18002b31c  retn
```
