# META_SCRIPT_MAP_TABLE::Dereference(void)

- ea: `0x180004528`
- end: `0x180004555`
- name: `?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(META_SCRIPT_MAP_TABLE *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002c04`
- `0x18000439c`
- `0x180005e30`
- `0x1800066b0`

## callees

- `0x180001398`
- `0x180004528`
- `0x1800057f8`

## pseudocode

```c
void __fastcall META_SCRIPT_MAP_TABLE::Dereference(META_SCRIPT_MAP_TABLE *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180004528  push    rbx
0x18000452a  sub     rsp, 20h
0x18000452e  mov     rbx, rcx
0x180004531  or      eax, 0FFFFFFFFh
0x180004534  lock xadd [rcx], eax
0x180004538  cmp     eax, 1
0x18000453b  jnz     short loc_18000454F
0x18000453d  test    rcx, rcx
0x180004540  jz      short loc_18000454F
0x180004542  call    ??1META_SCRIPT_MAP_TABLE@@AEAA@XZ; META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(void)
0x180004547  mov     rcx, rbx; Block
0x18000454a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000454f  add     rsp, 20h
0x180004553  pop     rbx
0x180004554  retn
```
