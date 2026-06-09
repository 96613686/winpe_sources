# CASFMMStream::OnDestroyReadPacket(uchar *,ulong,ulong)

- ea: `0x1800137d0`
- end: `0x1800137f0`
- name: `?OnDestroyReadPacket@CASFMMStream@@MEAAXPEAEKK@Z`
- size: `32`
- prototype: `void __fastcall(CASFMMStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800137d0`
- `0x18002b010`

## pseudocode

```c
void __fastcall CASFMMStream::OnDestroyReadPacket(CASFMMStream *this, unsigned __int8 *a2)
{
  void (__fastcall ***v2)(_QWORD, unsigned __int8 *); // rcx

  v2 = (void (__fastcall ***)(_QWORD, unsigned __int8 *))*((_QWORD *)this + 93);
  if ( v2 )
    (**v2)(v2, a2);
}

```

## disassembly

```asm
0x1800137d0  sub     rsp, 38h
0x1800137d4  mov     rcx, [rcx+2E8h]
0x1800137db  test    rcx, rcx
0x1800137de  jz      short loc_1800137EB
0x1800137e0  mov     rax, [rcx]
0x1800137e3  mov     rax, [rax]
0x1800137e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137eb  add     rsp, 38h
0x1800137ef  retn
```
