# NThreadingLibrary::TWorkCrew::`scalar deleting destructor'(uint)

- ea: `0x140013380`
- end: `0x1400133b4`
- name: `??_GTWorkCrew@NThreadingLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(NThreadingLibrary::TWorkCrew *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140013310`

## callees

- `0x140001b90`
- `0x1400131c4`
- `0x140013380`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall NThreadingLibrary::TWorkCrew::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        void **a2)
{
  char v2; // bl

  v2 = (char)a2;
  NThreadingLibrary::TWorkCrew::~TWorkCrew(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140013380  mov     [rsp+arg_0], rbx
0x140013385  push    rdi
0x140013386  sub     rsp, 20h
0x14001338a  mov     ebx, edx
0x14001338c  mov     rdi, rcx
0x14001338f  call    ??1TWorkCrew@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TWorkCrew::~TWorkCrew(void)
0x140013394  test    bl, 1
0x140013397  jz      short loc_1400133A6
0x140013399  mov     edx, 0E8h
0x14001339e  mov     rcx, rdi; Block
0x1400133a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400133a6  mov     rbx, [rsp+28h+arg_0]
0x1400133ab  mov     rax, rdi
0x1400133ae  add     rsp, 20h
0x1400133b2  pop     rdi
0x1400133b3  retn
```
