# allocateQuantizer

- ea: `0x1800118d8`
- end: `0x18001193e`
- name: `allocateQuantizer`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000129c`
- `0x1800110d0`
- `0x180031110`
- `0x180032738`
- `0x180032914`
- `0x180042088`
- `0x180042294`

## callees

- `0x1800118d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800118fb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800118fb`

## pseudocode

```c
__int64 __fastcall allocateQuantizer(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  void *v5; // rax
  unsigned __int64 i; // rcx

  if ( a3 > 0x11 )
    return 0xFFFFFFFFLL;
  if ( a2 > 0x10 )
    return 0xFFFFFFFFLL;
  v5 = malloc(340 * a2);
  *a1 = v5;
  if ( !v5 )
    return 0xFFFFFFFFLL;
  for ( i = 1; i < a2; ++i )
    a1[i] = a1[i - 1] + 340LL;
  return 0;
}

```

## disassembly

```asm
0x1800118d8  mov     [rsp+arg_0], rbx
0x1800118dd  push    rdi
0x1800118de  sub     rsp, 20h
0x1800118e2  mov     rbx, rdx
0x1800118e5  mov     rdi, rcx
0x1800118e8  cmp     r8, 11h
0x1800118ec  ja      short loc_180011920
0x1800118ee  cmp     rdx, 10h
0x1800118f2  ja      short loc_180011920
0x1800118f4  imul    rcx, rbx, 154h; Size
0x1800118fb  call    cs:__imp_malloc
0x180011901  mov     [rdi], rax
0x180011904  test    rax, rax
0x180011907  jz      short loc_180011920
0x180011909  mov     ecx, 1
0x18001190e  cmp     rbx, rcx
0x180011911  ja      short loc_180011925
0x180011913  xor     eax, eax
0x180011915  mov     rbx, [rsp+28h+arg_0]
0x18001191a  add     rsp, 20h
0x18001191e  pop     rdi
0x18001191f  retn
0x180011920  or      eax, 0FFFFFFFFh
0x180011923  jmp     short loc_180011915
0x180011925  mov     rax, [rdi+rcx*8-8]
0x18001192a  add     rax, 154h
0x180011930  mov     [rdi+rcx*8], rax
0x180011934  inc     rcx
0x180011937  cmp     rcx, rbx
0x18001193a  jb      short loc_180011925
0x18001193c  jmp     short loc_180011913
```
