# KsppCopyData

- ea: `0x1800156c4`
- end: `0x180015720`
- name: `KsppCopyData`
- size: `92`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *, unsigned int, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180018968`
- `0x180019220`
- `0x18001c818`
- `0x18001e92c`
- `0x180021220`
- `0x1800229fc`

## callees

- `0x180009e76`
- `0x1800156c4`

## pseudocode

```c
__int64 __fastcall KsppCopyData(void *Src, size_t Size, void *a3, unsigned int a4, _DWORD *a5)
{
  int v5; // ebx

  v5 = Size;
  if ( !Src || !(_DWORD)Size || !a5 )
    return 2148073511LL;
  if ( a4 && a4 < (unsigned int)Size )
    return 122;
  if ( a3 )
    memcpy_0(a3, Src, (unsigned int)Size);
  *a5 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800156c4  mov     [rsp+arg_0], rbx
0x1800156c9  push    rdi
0x1800156ca  sub     rsp, 20h
0x1800156ce  mov     ebx, edx
0x1800156d0  mov     rax, r8
0x1800156d3  test    rcx, rcx
0x1800156d6  jz      short loc_180015710
0x1800156d8  test    edx, edx
0x1800156da  jz      short loc_180015710
0x1800156dc  mov     rdi, [rsp+28h+arg_20]
0x1800156e1  test    rdi, rdi
0x1800156e4  jz      short loc_180015710
0x1800156e6  test    r9d, r9d
0x1800156e9  jz      short loc_1800156F7
0x1800156eb  cmp     r9d, ebx
0x1800156ee  jnb     short loc_1800156F7
0x1800156f0  mov     eax, 7Ah ; 'z'
0x1800156f5  jmp     short loc_180015715
0x1800156f7  test    rax, rax
0x1800156fa  jz      short loc_18001570A
0x1800156fc  mov     rdx, rcx; Src
0x1800156ff  mov     r8, rbx; Size
0x180015702  mov     rcx, rax; void *
0x180015705  call    memcpy_0
0x18001570a  mov     [rdi], ebx
0x18001570c  xor     eax, eax
0x18001570e  jmp     short loc_180015715
0x180015710  mov     eax, 80090027h
0x180015715  mov     rbx, [rsp+28h+arg_0]
0x18001571a  add     rsp, 20h
0x18001571e  pop     rdi
0x18001571f  retn
```
