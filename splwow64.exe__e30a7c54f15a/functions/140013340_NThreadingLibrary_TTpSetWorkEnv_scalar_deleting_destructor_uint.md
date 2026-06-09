# NThreadingLibrary::TTpSetWorkEnv::`scalar deleting destructor'(uint)

- ea: `0x140013340`
- end: `0x140013374`
- name: `??_GTTpSetWorkEnv@NThreadingLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(NThreadingLibrary::TTpSetWorkEnv *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001b90`
- `0x140013174`
- `0x140013340`

## pseudocode

```c
NThreadingLibrary::TTpSetWorkEnv *__fastcall NThreadingLibrary::TTpSetWorkEnv::`scalar deleting destructor'(
        NThreadingLibrary::TTpSetWorkEnv *this,
        char a2)
{
  NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140013340  mov     [rsp+arg_0], rbx
0x140013345  push    rdi
0x140013346  sub     rsp, 20h
0x14001334a  mov     ebx, edx
0x14001334c  mov     rdi, rcx
0x14001334f  call    ??1TTpSetWorkEnv@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(void)
0x140013354  test    bl, 1
0x140013357  jz      short loc_140013366
0x140013359  mov     edx, 10h
0x14001335e  mov     rcx, rdi; Block
0x140013361  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013366  mov     rbx, [rsp+28h+arg_0]
0x14001336b  mov     rax, rdi
0x14001336e  add     rsp, 20h
0x140013372  pop     rdi
0x140013373  retn
```
