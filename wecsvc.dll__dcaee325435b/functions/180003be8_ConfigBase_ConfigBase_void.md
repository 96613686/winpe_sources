# ConfigBase::~ConfigBase(void)

- ea: `0x180003be8`
- end: `0x180003c0a`
- name: `??1ConfigBase@@UEAA@XZ`
- size: `34`
- prototype: `void __fastcall(ConfigBase *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003c88`
- `0x1800042d0`
- `0x180004760`
- `0x180004b80`
- `0x1800052cc`
- `0x180007844`
- `0x180007c00`
- `0x1800087b0`
- `0x18001483c`
- `0x1800154cc`
- `0x1800222fa`
- `0x18002230c`

## callees

- `0x180003e6c`

## pseudocode

```c
void __fastcall ConfigBase::~ConfigBase(ConfigBase *this)
{
  wmi::AutoRegKey::Close((ConfigBase *)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180003be8  push    rbx
0x180003bea  sub     rsp, 20h
0x180003bee  mov     rbx, rcx
0x180003bf1  add     rcx, 10h; this
0x180003bf5  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180003bfa  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180003c01  mov     [rbx], rax
0x180003c04  add     rsp, 20h
0x180003c08  pop     rbx
0x180003c09  retn
```
