# NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(void)

- ea: `0x140013ff8`
- end: `0x14001402f`
- name: `??1TCopyCritsec@NAdvancedLibrary@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(NAdvancedLibrary::TCopyCritsec *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140010400`
- `0x1400105e4`

## callees

- `0x140001b90`
- `0x140013ff8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001400f`
- `KERNEL32!DeleteCriticalSection` at `0x14001400f`

## pseudocode

```c
void __fastcall NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(LPCRITICAL_SECTION *this)
{
  LPCRITICAL_SECTION v1; // rbx

  v1 = *this;
  if ( *this )
  {
    if ( v1[1].LockCount >= 0 )
    {
      DeleteCriticalSection(*this);
      v1[1].LockCount = -2147467259;
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x140013ff8  push    rbx
0x140013ffa  sub     rsp, 20h
0x140013ffe  mov     rbx, [rcx]
0x140014001  test    rbx, rbx
0x140014004  jz      short loc_140014029
0x140014006  cmp     dword ptr [rbx+30h], 0
0x14001400a  jl      short loc_14001401C
0x14001400c  mov     rcx, rbx; lpCriticalSection
0x14001400f  call    cs:__imp_DeleteCriticalSection
0x140014015  mov     dword ptr [rbx+30h], 80004005h
0x14001401c  mov     edx, 38h ; '8'
0x140014021  mov     rcx, rbx; Block
0x140014024  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014029  add     rsp, 20h
0x14001402d  pop     rbx
0x14001402e  retn
```
