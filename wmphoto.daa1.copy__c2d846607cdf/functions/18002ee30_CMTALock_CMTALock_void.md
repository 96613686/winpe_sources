# CMTALock::CMTALock(void)

- ea: `0x18002ee30`
- end: `0x18002ee59`
- name: `??0CMTALock@@QEAA@XZ`
- size: `41`
- prototype: `CMTALock *__fastcall(CMTALock *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002eb90`
- `0x18002ed90`
- `0x180034a40`
- `0x18003b040`

## callees

- `0x18002ee78`

## pseudocode

```c
CMTALock *__fastcall CMTALock::CMTALock(CMTALock *this)
{
  CCriticalSection *v2; // rcx

  *(_QWORD *)this = &CMTALock::`vftable';
  v2 = (CMTALock *)((char *)this + 8);
  *((_BYTE *)v2 + 40) = 0;
  CCriticalSection::Init(v2);
  return this;
}

```

## disassembly

```asm
0x18002ee30  push    rbx
0x18002ee32  sub     rsp, 20h
0x18002ee36  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x18002ee3d  mov     rbx, rcx
0x18002ee40  mov     [rcx], rax
0x18002ee43  add     rcx, 8; this
0x18002ee47  mov     byte ptr [rcx+28h], 0
0x18002ee4b  call    ?Init@CCriticalSection@@QEAAJXZ; CCriticalSection::Init(void)
0x18002ee50  mov     rax, rbx
0x18002ee53  add     rsp, 20h
0x18002ee57  pop     rbx
0x18002ee58  retn
```
