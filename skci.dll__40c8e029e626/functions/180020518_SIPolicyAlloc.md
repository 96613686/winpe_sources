# SIPolicyAlloc

- ea: `0x180020518`
- end: `0x180020563`
- name: `SIPolicyAlloc`
- size: `75`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `21`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019300`
- `0x180019410`
- `0x180019720`
- `0x18001c380`
- `0x18001c76c`
- `0x18001cd1c`
- `0x18001dfa8`
- `0x18001e0b8`
- `0x18001e244`
- `0x18001e3a8`
- `0x18001e674`
- `0x18001ef1c`
- `0x18001f33c`
- `0x18001f624`
- `0x18001f800`
- `0x18001fb08`
- `0x18001fd8c`
- `0x18001ff54`
- `0x180021304`
- `0x180047a80`
- `0x18004a97c`

## callees

- `0x180020518`
- `0x180033950`

## import_xrefs

- `securekernel!SkAllocatePool` at `0x180020533`
- `securekernel!SkAllocatePool` at `0x180020533`

## pseudocode

```c
void *__fastcall SIPolicyAlloc(size_t Size)
{
  void *Pool; // rax
  void *v3; // rbx

  Pool = (void *)SkAllocatePool(1, Size, 1867532627);
  v3 = Pool;
  if ( Pool )
    memset_0(Pool, 0, Size);
  return v3;
}

```

## disassembly

```asm
0x180020518  mov     [rsp+arg_0], rbx
0x18002051d  push    rdi
0x18002051e  sub     rsp, 20h
0x180020522  mov     rdi, rcx
0x180020525  mov     rdx, rcx
0x180020528  mov     ecx, 1
0x18002052d  mov     r8d, 6F504953h
0x180020533  call    cs:__imp_SkAllocatePool
0x18002053a  nop     dword ptr [rax+rax+00h]
0x18002053f  mov     rbx, rax
0x180020542  test    rax, rax
0x180020545  jz      short loc_180020554
0x180020547  mov     r8, rdi; Size
0x18002054a  xor     edx, edx; Val
0x18002054c  mov     rcx, rax; void *
0x18002054f  call    memset_0
0x180020554  mov     rax, rbx
0x180020557  mov     rbx, [rsp+28h+arg_0]
0x18002055c  add     rsp, 20h
0x180020560  pop     rdi
0x180020561  retn
```
