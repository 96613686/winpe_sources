# CPxeProvider::~CPxeProvider(void)

- ea: `0x180004004`
- end: `0x180004027`
- name: `??1CPxeProvider@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CPxeProvider *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000523c`
- `0x180006adc`

## callees

- `0x180004848`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000401b`

## pseudocode

```c
void __fastcall CPxeProvider::~CPxeProvider(CPxeProvider *this)
{
  CPxeProvider::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
}

```

## disassembly

```asm
0x180004004  push    rbx
0x180004006  sub     rsp, 20h
0x18000400a  mov     rbx, rcx
0x18000400d  call    ?Shutdown@CPxeProvider@@QEAAKXZ; CPxeProvider::Shutdown(void)
0x180004012  lea     rcx, [rbx+70h]
0x180004016  add     rsp, 20h
0x18000401a  pop     rbx
0x18000401b  jmp     cs:__imp_DeleteCriticalSection
```
