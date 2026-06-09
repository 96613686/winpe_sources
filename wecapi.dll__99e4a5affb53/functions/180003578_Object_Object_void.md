# Object::~Object(void)

- ea: `0x180003578`
- end: `0x180003583`
- name: `??1Object@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(Object *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bee2`
- `0x18000c45a`
- `0x18000c47e`

## pseudocode

```c
void __fastcall Object::~Object(Object *this)
{
  *(_QWORD *)this = &EventSourceCollection::`vftable';
}

```

## disassembly

```asm
0x180003578  lea     rax, ??_7EventSourceCollection@@6B@; const EventSourceCollection::`vftable'
0x18000357f  mov     [rcx], rax
0x180003582  retn
```
