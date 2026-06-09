# mi::MiInstance::~MiInstance(void)

- ea: `0x180026c30`
- end: `0x180026c6b`
- name: `??1MiInstance@mi@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(mi::MiInstance *__hidden this)`
- caller_count: `94`
- callee_count: `4`
- tags: ``

## callers

- `0x180006360`
- `0x1800089d4`
- `0x180009bd8`
- `0x180009d9c`
- `0x18000aa00`
- `0x18000cec8`
- `0x18000fc70`
- `0x18001152c`
- `0x180011784`
- `0x1800118e4`
- `0x180012594`
- `0x180012c94`
- `0x180012f18`
- `0x180013f60`
- `0x180016684`
- `0x180016e4c`
- `0x180019584`
- `0x18001a0fc`
- `0x18001cfb0`
- `0x18001d42c`
- `0x18001d9f8`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`
- `0x18001eec0`
- `0x18001f18c`
- `0x18001f354`
- `0x18001f4e4`
- `0x18001f674`
- `0x18001f7d8`
- `0x18001fa48`
- `0x180020190`
- `0x1800201dc`
- `0x180020280`
- `0x180020754`
- `0x180020800`
- `0x180020ac0`
- `0x18002119c`
- `0x180021210`
- `0x1800216f0`
- `0x18002173c`
- `0x1800217ac`
- `0x1800217f8`
- `0x180021844`

## callees

- `0x180006630`
- `0x180026194`
- `0x180026c30`
- `0x18002728c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall mi::MiInstance::~MiInstance(std::_Ref_count_base **this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  mi::MiInstance::Close((mi::MiInstance *)this);
  v2 = this[5];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = this[3];
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  mi::MiObjectPtr<_MI_Instance>::Close(this);
}

```

## disassembly

```asm
0x180026c30  push    rbx
0x180026c32  sub     rsp, 20h
0x180026c36  mov     rbx, rcx
0x180026c39  call    ?Close@MiInstance@mi@@AEAAXXZ; mi::MiInstance::Close(void)
0x180026c3e  mov     rcx, [rbx+28h]; this
0x180026c42  test    rcx, rcx
0x180026c45  jz      short loc_180026C4C
0x180026c47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026c4c  mov     rcx, [rbx+18h]; this
0x180026c50  test    rcx, rcx
0x180026c53  jz      short loc_180026C5B
0x180026c55  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026c5a  nop
0x180026c5b  mov     rcx, rbx
0x180026c5e  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x180026c63  nop
0x180026c64  add     rsp, 20h
0x180026c68  pop     rbx
0x180026c69  retn
```
