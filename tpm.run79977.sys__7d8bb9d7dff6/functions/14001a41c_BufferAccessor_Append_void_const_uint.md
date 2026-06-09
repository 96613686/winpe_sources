# BufferAccessor::Append(void const *,uint)

- ea: `0x14001a41c`
- end: `0x14001a461`
- name: `?Append@BufferAccessor@@QEAAJPEBXI@Z`
- size: `69`
- prototype: `int(BufferAccessor *__hidden this, const void *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006300`
- `0x1400211dc`
- `0x140021a60`
- `0x14002aaa0`

## callees

- `0x14001a41c`
- `0x140039840`

## pseudocode

```c
__int64 __fastcall BufferAccessor::Append(BufferAccessor *this, const void *a2, unsigned int a3)
{
  __int64 v4; // rbx

  if ( a3 > *(_DWORD *)this + *((_DWORD *)this + 2) - *((_DWORD *)this + 4) )
    return 2147483653LL;
  v4 = a3;
  memmove(*((void **)this + 2), a2, a3);
  *((_QWORD *)this + 2) += v4;
  return 0;
}

```

## disassembly

```asm
0x14001a41c  mov     [rsp+arg_0], rbx
0x14001a421  push    rdi
0x14001a422  sub     rsp, 20h
0x14001a426  mov     r9d, [rcx+8]
0x14001a42a  mov     rdi, rcx
0x14001a42d  sub     r9d, [rcx+10h]
0x14001a431  add     r9d, [rcx]
0x14001a434  cmp     r8d, r9d
0x14001a437  ja      short loc_14001A450
0x14001a439  mov     rcx, [rcx+10h]; void *
0x14001a43d  mov     ebx, r8d
0x14001a440  mov     r8d, r8d; Size
0x14001a443  call    memmove
0x14001a448  add     [rdi+10h], rbx
0x14001a44c  xor     eax, eax
0x14001a44e  jmp     short loc_14001A455
0x14001a450  mov     eax, 80000005h
0x14001a455  mov     rbx, [rsp+28h+arg_0]
0x14001a45a  add     rsp, 20h
0x14001a45e  pop     rdi
0x14001a45f  retn
```
