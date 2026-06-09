# CActiveThreadList::Grow(void)

- ea: `0x18000fd48`
- end: `0x18000fdbf`
- name: `?Grow@CActiveThreadList@@AEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(const void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004850`

## callees

- `0x18000dae8`
- `0x18000db28`
- `0x18000fd48`
- `0x180010fbe`

## pseudocode

```c
__int64 __fastcall CActiveThreadList::Grow(const void **this)
{
  unsigned int v2; // esi
  void *v3; // rax
  const void *v4; // rdi
  __int64 result; // rax
  void *v6; // rcx

  v2 = *(_DWORD *)this + 2;
  v3 = operator new(saturated_mul(v2, 4u));
  v4 = v3;
  if ( !v3 )
    return 2147942414LL;
  memcpy_0(v3, this[1], 4LL * *(unsigned int *)this);
  v6 = (void *)this[1];
  *(_DWORD *)this = v2;
  operator delete(v6);
  result = 0;
  this[1] = v4;
  return result;
}

```

## disassembly

```asm
0x18000fd48  mov     [rsp+arg_0], rbx
0x18000fd4d  mov     [rsp+arg_8], rsi
0x18000fd52  push    rdi
0x18000fd53  sub     rsp, 20h
0x18000fd57  mov     esi, [rcx]
0x18000fd59  mov     rbx, rcx
0x18000fd5c  add     esi, 2
0x18000fd5f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fd66  mov     edx, esi
0x18000fd68  mov     eax, 4
0x18000fd6d  mul     rdx
0x18000fd70  cmovb   rax, rcx
0x18000fd74  mov     rcx, rax; Size
0x18000fd77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd7c  mov     rdi, rax
0x18000fd7f  test    rax, rax
0x18000fd82  jnz     short loc_18000FD8B
0x18000fd84  mov     eax, 8007000Eh
0x18000fd89  jmp     short loc_18000FDAF
0x18000fd8b  mov     r8d, [rbx]
0x18000fd8e  mov     rcx, rdi; void *
0x18000fd91  mov     rdx, [rbx+8]; Src
0x18000fd95  shl     r8, 2; Size
0x18000fd99  call    memcpy_0
0x18000fd9e  mov     rcx, [rbx+8]; Block
0x18000fda2  mov     [rbx], esi
0x18000fda4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fda9  xor     eax, eax
0x18000fdab  mov     [rbx+8], rdi
0x18000fdaf  mov     rbx, [rsp+28h+arg_0]
0x18000fdb4  mov     rsi, [rsp+28h+arg_8]
0x18000fdb9  add     rsp, 20h
0x18000fdbd  pop     rdi
0x18000fdbe  retn
```
