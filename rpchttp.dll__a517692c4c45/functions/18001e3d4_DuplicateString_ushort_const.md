# DuplicateString(ushort const *)

- ea: `0x18001e3d4`
- end: `0x18001e437`
- name: `?DuplicateString@@YAPEAGPEBG@Z`
- size: `99`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *Src)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c60`
- `0x180004714`
- `0x180004cf8`
- `0x1800059b0`
- `0x18000b920`
- `0x18000f74c`
- `0x18001fc58`
- `0x180020c3c`
- `0x1800222b4`

## callees

- `0x18001e3d4`
- `0x18002461d`

## import_xrefs

- `RPCRT4!I_RpcAllocate` at `0x18001e40a`
- `RPCRT4!I_RpcAllocate` at `0x18001e40a`

## pseudocode

```c
unsigned __int16 *__fastcall DuplicateString(const unsigned __int16 *Src)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rsi
  unsigned int v4; // eax
  void *v5; // rax
  void *v6; // rbx

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  if ( (unsigned int)v2 > 0x7FFF )
    return 0;
  v3 = (unsigned int)(v2 + 1);
  v4 = 2 * (v2 + 1);
  if ( !is_mul_ok(v3, 2u) )
    v4 = -1;
  v5 = I_RpcAllocate(v4);
  v6 = v5;
  if ( !v5 )
    return 0;
  memcpy_0(v5, Src, 2 * v3);
  return (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x18001e3d4  push    rbx
0x18001e3d6  push    rbp
0x18001e3d7  push    rsi
0x18001e3d8  push    rdi
0x18001e3d9  sub     rsp, 28h
0x18001e3dd  mov     rdi, rcx
0x18001e3e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e3e4  mov     rax, rcx
0x18001e3e7  xor     ebp, ebp
0x18001e3e9  inc     rax
0x18001e3ec  cmp     [rdi+rax*2], bp
0x18001e3f0  jnz     short loc_18001E3E9
0x18001e3f2  cmp     eax, 7FFFh
0x18001e3f7  ja      short loc_18001E42C
0x18001e3f9  lea     esi, [rax+1]
0x18001e3fc  mov     eax, 2
0x18001e401  mul     rsi
0x18001e404  cmovb   rax, rcx
0x18001e408  mov     ecx, eax; Size
0x18001e40a  call    cs:__imp_I_RpcAllocate
0x18001e410  mov     rbx, rax
0x18001e413  test    rax, rax
0x18001e416  jz      short loc_18001E42C
0x18001e418  lea     r8, [rsi+rsi]; Size
0x18001e41c  mov     rdx, rdi; Src
0x18001e41f  mov     rcx, rax; void *
0x18001e422  call    memcpy_0
0x18001e427  mov     rax, rbx
0x18001e42a  jmp     short loc_18001E42E
0x18001e42c  xor     eax, eax
0x18001e42e  add     rsp, 28h
0x18001e432  pop     rdi
0x18001e433  pop     rsi
0x18001e434  pop     rbp
0x18001e435  pop     rbx
0x18001e436  retn
```
