# CMTALock::CMTALock(void)

- ea: `0x18002f1c0`
- end: `0x18002f1ea`
- name: `??0CMTALock@@QEAA@XZ`
- size: `42`
- prototype: `CMTALock *__fastcall(CMTALock *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ef14`
- `0x18002f120`
- `0x180035018`
- `0x18003b7f8`

## callees

- `0x18002f208`

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
0x18002f1c0  push    rbx
0x18002f1c2  sub     rsp, 20h
0x18002f1c6  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x18002f1cd  mov     rbx, rcx
0x18002f1d0  mov     [rcx], rax
0x18002f1d3  add     rcx, 8; this
0x18002f1d7  mov     byte ptr [rcx+28h], 0
0x18002f1db  call    ?Init@CCriticalSection@@QEAAJXZ; CCriticalSection::Init(void)
0x18002f1e0  mov     rax, rbx
0x18002f1e3  add     rsp, 20h
0x18002f1e7  pop     rbx
0x18002f1e8  retn
```
