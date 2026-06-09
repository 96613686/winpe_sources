# _mi::MiCreator_mi::MiInstance_::Create_::_1_::dtor$0

- ea: `0x18002ae26`
- end: `0x18002ae4c`
- name: `_mi::MiCreator_mi::MiInstance_::Create_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800268e4`
- `0x18002ae26`

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
0x18002ae26  push    rbp
0x18002ae28  sub     rsp, 20h
0x18002ae2c  mov     rbp, rdx
0x18002ae2f  mov     eax, [rbp+20h]
0x18002ae32  and     eax, 1
0x18002ae35  test    eax, eax
0x18002ae37  jz      short loc_18002AE46
0x18002ae39  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002ae3d  mov     rcx, [rbp+40h]; this
0x18002ae41  call    ??1MiInstance@mi@@QEAA@XZ
0x18002ae46  add     rsp, 20h
0x18002ae4a  pop     rbp
0x18002ae4b  retn
```
