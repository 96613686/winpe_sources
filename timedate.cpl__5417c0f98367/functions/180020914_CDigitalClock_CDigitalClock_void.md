# CDigitalClock::~CDigitalClock(void)

- ea: `0x180020914`
- end: `0x18002092f`
- name: `??1CDigitalClock@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(CDigitalClock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020938`

## callees

- `0x180020914`

## import_xrefs

- `GDI32!DeleteObject` at `0x180020924`
- `GDI32!DeleteObject` at `0x180020924`

## pseudocode

```c
void __fastcall CDigitalClock::~CDigitalClock(CDigitalClock *this)
{
  void *v1; // rcx

  v1 = (void *)*((_QWORD *)this + 19);
  if ( v1 )
    DeleteObject(v1);
}

```

## disassembly

```asm
0x180020914  sub     rsp, 28h
0x180020918  mov     rcx, [rcx+98h]; ho
0x18002091f  test    rcx, rcx
0x180020922  jz      short loc_18002092A
0x180020924  call    cs:__imp_DeleteObject
0x18002092a  add     rsp, 28h
0x18002092e  retn
```
