# operator new(unsigned __int64)

- ea: `0x1800011d0`
- end: `0x180001201`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011c4`
- `0x180001d98`
- `0x1800039a0`
- `0x180003a90`
- `0x180003b90`
- `0x180007604`
- `0x180012124`
- `0x180013570`
- `0x1800160f0`
- `0x1800164c4`
- `0x180017ca0`
- `0x180017fcc`
- `0x18001ab44`
- `0x18001af34`
- `0x18001b050`
- `0x18001c3a7`
- `0x18001c474`

## callees

- `0x1800011d0`
- `0x180001378`
- `0x180001dbd`

## import_xrefs

- `msvcrt!malloc` at `0x1800011ea`
- `msvcrt!malloc` at `0x1800011ea`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x1800011d0  push    rbx
0x1800011d2  sub     rsp, 20h
0x1800011d6  mov     rbx, rcx
0x1800011d9  jmp     short loc_1800011EA
0x1800011db  mov     rcx, rbx; Size
0x1800011de  call    _callnewh_0
0x1800011e3  test    eax, eax
0x1800011e5  jz      short loc_1800011FB
0x1800011e7  mov     rcx, rbx; Size
0x1800011ea  call    cs:__imp_malloc
0x1800011f0  test    rax, rax
0x1800011f3  jz      short loc_1800011DB
0x1800011f5  add     rsp, 20h
0x1800011f9  pop     rbx
0x1800011fa  retn
0x1800011fb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
