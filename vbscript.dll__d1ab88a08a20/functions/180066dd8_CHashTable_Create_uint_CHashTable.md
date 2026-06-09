# CHashTable::Create(uint,CHashTable * *)

- ea: `0x180066dd8`
- end: `0x180066ecc`
- name: `?Create@CHashTable@@SAJIPEAPEAV1@@Z`
- size: `244`
- prototype: `__int64 __fastcall(unsigned int, struct CHashTable **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180066ed4`
- `0x18006726c`
- `0x18006754c`

## callees

- `0x180046884`
- `0x180066c94`
- `0x180066dd8`
- `0x1800793fa`
- `0x180079436`

## import_xrefs

- `msvcrt!malloc` at `0x180066e54`
- `msvcrt!malloc` at `0x180066ea3`
- `msvcrt!malloc` at `0x180066e54`
- `msvcrt!malloc` at `0x180066ea3`

## pseudocode

```c
__int64 __fastcall CHashTable::Create(int a1, struct CHashTable **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  double v6; // xmm6_8
  unsigned int v7; // eax
  size_t v8; // rdi
  void *v9; // rax
  unsigned int v10; // edx
  __int64 result; // rax
  size_t v12; // rdi
  void *v13; // rax

  v4 = operator new(0x20u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[3] = 0;
  *(_DWORD *)v4 = 0;
  *((_DWORD *)v4 + 1) = a1;
  v6 = log_0((double)(a1 + 1));
  v7 = (1 << ((int)(v6 / log_0(2.0)) + 1)) - 1;
  v8 = 8LL * v7;
  *((_DWORD *)v5 + 2) = v7;
  v9 = malloc(v8);
  v5[2] = v9;
  if ( !v9 || (memset_0(v9, 0, v8), v12 = 16LL * *((unsigned int *)v5 + 1), v13 = malloc(v12), (v5[3] = v13) == 0) )
  {
    CHashTable::`scalar deleting destructor'((CHashTable *)v5, v10);
    return 2147942414LL;
  }
  memset_0(v13, 0, v12);
  result = 0;
  *a2 = (struct CHashTable *)v5;
  return result;
}

```

## disassembly

```asm
0x180066dd8  mov     [rsp+arg_0], rbx
0x180066ddd  mov     [rsp+arg_8], rsi
0x180066de2  push    rdi
0x180066de3  sub     rsp, 30h
0x180066de7  mov     edi, ecx
0x180066de9  movaps  [rsp+38h+var_18], xmm6
0x180066dee  mov     ecx, 20h ; ' '; Size
0x180066df3  mov     rsi, rdx
0x180066df6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066dfb  mov     rbx, rax
0x180066dfe  test    rax, rax
0x180066e01  jz      short loc_180066E71
0x180066e03  lea     edx, [rdi+1]
0x180066e06  mov     qword ptr [rax+18h], 0
0x180066e0e  xorps   xmm0, xmm0
0x180066e11  mov     dword ptr [rax], 0
0x180066e17  cvtsi2sd xmm0, rdx; X
0x180066e1c  mov     [rax+4], edi
0x180066e1f  call    log_0
0x180066e24  movaps  xmm6, xmm0
0x180066e27  movsd   xmm0, cs:__real@4000000000000000; X
0x180066e2f  call    log_0
0x180066e34  divsd   xmm6, xmm0
0x180066e38  mov     eax, 1
0x180066e3d  cvttsd2si rcx, xmm6
0x180066e42  add     ecx, eax
0x180066e44  shl     eax, cl
0x180066e46  dec     eax
0x180066e48  mov     edi, eax
0x180066e4a  shl     rdi, 3
0x180066e4e  mov     rcx, rdi; Size
0x180066e51  mov     [rbx+8], eax
0x180066e54  call    cs:__imp_malloc
0x180066e5b  nop     dword ptr [rax+rax+00h]
0x180066e60  mov     [rbx+10h], rax
0x180066e64  test    rax, rax
0x180066e67  jnz     short loc_180066E8C
0x180066e69  mov     rcx, rbx; this
0x180066e6c  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180066e71  mov     eax, 8007000Eh
0x180066e76  mov     rbx, [rsp+38h+arg_0]
0x180066e7b  mov     rsi, [rsp+38h+arg_8]
0x180066e80  movaps  xmm6, [rsp+38h+var_18]
0x180066e85  add     rsp, 30h
0x180066e89  pop     rdi
0x180066e8a  retn
0x180066e8c  mov     r8, rdi; Size
0x180066e8f  xor     edx, edx; Val
0x180066e91  mov     rcx, rax; void *
0x180066e94  call    memset_0
0x180066e99  mov     edi, [rbx+4]
0x180066e9c  shl     rdi, 4
0x180066ea0  mov     rcx, rdi; Size
0x180066ea3  call    cs:__imp_malloc
0x180066eaa  nop     dword ptr [rax+rax+00h]
0x180066eaf  mov     [rbx+18h], rax
0x180066eb3  test    rax, rax
0x180066eb6  jz      short loc_180066E69
0x180066eb8  mov     r8, rdi; Size
0x180066ebb  xor     edx, edx; Val
0x180066ebd  mov     rcx, rax; void *
0x180066ec0  call    memset_0
0x180066ec5  xor     eax, eax
0x180066ec7  mov     [rsi], rbx
0x180066eca  jmp     short loc_180066E76
```
