# CCountedObject::Release(void)

- ea: `0x180003f90`
- end: `0x180003fbe`
- name: `?Release@CCountedObject@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(CCountedObject *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180003280`
- `0x180003790`
- `0x180004178`
- `0x180004d80`
- `0x180006580`
- `0x18000697c`
- `0x18000a730`
- `0x18000db00`
- `0x18000eba0`
- `0x18000ecd4`
- `0x18000ee4c`

## callees

- `0x180003f90`
- `0x180010010`

## pseudocode

```c
void __fastcall CCountedObject::Release(CCountedObject *this)
{
  void (__fastcall **v1)(CCountedObject *, __int64); // rax

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    v1 = *(void (__fastcall ***)(CCountedObject *, __int64))this;
    *((_BYTE *)this + 12) = 1;
    (*v1)(this, 1);
  }
}

```

## disassembly

```asm
0x180003f90  sub     rsp, 28h
0x180003f94  mov     eax, 0FFFFFFFFh
0x180003f99  lock xadd [rcx+8], eax
0x180003f9e  cmp     eax, 1
0x180003fa1  jz      short loc_180003FA8
0x180003fa3  add     rsp, 28h
0x180003fa7  retn
0x180003fa8  mov     rax, [rcx]
0x180003fab  mov     edx, 1
0x180003fb0  mov     byte ptr [rcx+0Ch], 1
0x180003fb4  mov     rax, [rax]
0x180003fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fbc  jmp     short loc_180003FA3
```
