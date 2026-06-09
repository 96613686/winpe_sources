# std::_Copy_memmove_n<uchar const *,uchar *>(uchar const *,unsigned __int64,uchar *)

- ea: `0x180006204`
- end: `0x180006231`
- name: `??$_Copy_memmove_n@PEBEPEAE@std@@YAPEAEPEBE_KPEAE@Z`
- size: `45`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006128`
- `0x18000cae0`
- `0x180025b5c`

## callees

- `0x180034b20`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<unsigned char const *,unsigned char *>(void *Src, size_t Size, void *a3)
{
  memmove_0(a3, Src, Size);
  return (__int64)a3 + Size;
}

```

## disassembly

```asm
0x180006204  mov     [rsp+arg_0], rbx
0x180006209  push    rdi
0x18000620a  sub     rsp, 20h
0x18000620e  mov     rdi, r8
0x180006211  mov     rbx, rdx
0x180006214  mov     r8, rdx; Size
0x180006217  mov     rdx, rcx; Src
0x18000621a  mov     rcx, rdi; void *
0x18000621d  call    memmove_0
0x180006222  lea     rax, [rbx+rdi]
0x180006226  mov     rbx, [rsp+28h+arg_0]
0x18000622b  add     rsp, 20h
0x18000622f  pop     rdi
0x180006230  retn
```
