# CWuaClassFactoryBase::~CWuaClassFactoryBase(void)

- ea: `0x14000beac`
- end: `0x14000bed5`
- name: `??1CWuaClassFactoryBase@@MEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CWuaClassFactoryBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000be70`
- `0x14000c2f0`
- `0x140018ddc`

## callees

- `0x14000beac`
- `0x1400206e0`

## pseudocode

```c
void __fastcall CWuaClassFactoryBase::~CWuaClassFactoryBase(CWuaClassFactoryBase *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CWuaClassFactoryBase::`vftable';
  v1 = *((_QWORD *)this + 4);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14000beac  sub     rsp, 28h
0x14000beb0  lea     rax, ??_7CWuaClassFactoryBase@@6B@; const CWuaClassFactoryBase::`vftable'
0x14000beb7  mov     [rcx], rax
0x14000beba  mov     rcx, [rcx+20h]
0x14000bebe  test    rcx, rcx
0x14000bec1  jz      short loc_14000BED0
0x14000bec3  mov     rax, [rcx]
0x14000bec6  mov     rax, [rax+10h]
0x14000beca  call    _guard_dispatch_icall
0x14000becf  nop
0x14000bed0  add     rsp, 28h
0x14000bed4  retn
```
