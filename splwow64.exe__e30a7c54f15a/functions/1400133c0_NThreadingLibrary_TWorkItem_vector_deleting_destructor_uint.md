# NThreadingLibrary::TWorkItem::`vector deleting destructor'(uint)

- ea: `0x1400133c0`
- end: `0x1400133f4`
- name: `??_ETWorkItem@NThreadingLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(NThreadingLibrary::TWorkItem *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140013320`
- `0x140013330`

## callees

- `0x140001b90`
- `0x1400132a8`
- `0x1400133c0`

## pseudocode

```c
NThreadingLibrary::TWorkItem *__fastcall NThreadingLibrary::TWorkItem::`vector deleting destructor'(
        NThreadingLibrary::TWorkItem *this,
        char a2)
{
  NThreadingLibrary::TWorkItem::~TWorkItem(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400133c0  mov     [rsp+arg_0], rbx
0x1400133c5  push    rdi
0x1400133c6  sub     rsp, 20h
0x1400133ca  mov     ebx, edx
0x1400133cc  mov     rdi, rcx
0x1400133cf  call    ??1TWorkItem@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TWorkItem::~TWorkItem(void)
0x1400133d4  test    bl, 1
0x1400133d7  jz      short loc_1400133E6
0x1400133d9  mov     edx, 60h ; '`'
0x1400133de  mov     rcx, rdi; Block
0x1400133e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400133e6  mov     rbx, [rsp+28h+arg_0]
0x1400133eb  mov     rax, rdi
0x1400133ee  add     rsp, 20h
0x1400133f2  pop     rdi
0x1400133f3  retn
```
