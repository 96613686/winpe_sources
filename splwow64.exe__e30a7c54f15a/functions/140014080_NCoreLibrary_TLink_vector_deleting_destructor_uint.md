# NCoreLibrary::TLink::`vector deleting destructor'(uint)

- ea: `0x140014080`
- end: `0x1400140af`
- name: `??_ETLink@NCoreLibrary@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(NCoreLibrary::TLink *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001b44`
- `0x140014038`
- `0x140014080`

## pseudocode

```c
NCoreLibrary::TLink *__fastcall NCoreLibrary::TLink::`vector deleting destructor'(NCoreLibrary::TLink *this, char a2)
{
  NCoreLibrary::TLink::~TLink(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140014080  mov     [rsp+arg_0], rbx
0x140014085  push    rdi
0x140014086  sub     rsp, 20h
0x14001408a  mov     ebx, edx
0x14001408c  mov     rdi, rcx
0x14001408f  call    ??1TLink@NCoreLibrary@@UEAA@XZ; NCoreLibrary::TLink::~TLink(void)
0x140014094  test    bl, 1
0x140014097  jz      short loc_1400140A1
0x140014099  mov     rcx, rdi; Block
0x14001409c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400140a1  mov     rbx, [rsp+28h+arg_0]
0x1400140a6  mov     rax, rdi
0x1400140a9  add     rsp, 20h
0x1400140ad  pop     rdi
0x1400140ae  retn
```
