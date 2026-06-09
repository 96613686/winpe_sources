# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)

- ea: `0x1800066a8`
- end: `0x18000674c`
- name: `?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z`
- size: `164`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002878`
- `0x180006828`
- `0x1800068cc`
- `0x180006b64`

## callees

- `0x180001680`
- `0x180001b58`
- `0x1800066a8`
- `0x180012172`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rdx
  __int64 v4; // r14
  char *v5; // rax
  char *v6; // rbx
  char v7; // si
  __int64 v8; // rbp

  v2 = (a2 + 8) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    return 0;
  v4 = 2 * v2;
  v5 = (char *)operator new(2 * v2, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = 1;
  v8 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
  memcpy_0(v5, *(const void **)a1, 2 * v8 + 2);
  if ( *(_QWORD *)a1 != a1 + 16 )
    operator delete(*(void **)a1);
  *(_QWORD *)a1 = v6;
  *(_QWORD *)(a1 + 8) = &v6[2 * v8];
  *(_QWORD *)(a1 + 16) = &v6[v4 - 2];
  return v7;
}

```

## disassembly

```asm
0x1800066a8  push    rbx
0x1800066aa  push    rbp
0x1800066ab  push    rsi
0x1800066ac  push    rdi
0x1800066ad  push    r14
0x1800066af  push    r15
0x1800066b1  sub     rsp, 28h
0x1800066b5  add     rdx, 8
0x1800066b9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800066c3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800066c7  mov     rdi, rcx
0x1800066ca  cmp     rdx, rax
0x1800066cd  ja      short loc_180006739
0x1800066cf  lea     r14, [rdx+rdx]
0x1800066d3  mov     rcx, r14; unsigned __int64
0x1800066d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800066dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800066e2  mov     rbx, rax
0x1800066e5  test    rax, rax
0x1800066e8  jz      short loc_180006739
0x1800066ea  mov     rbp, [rdi+8]
0x1800066ee  mov     rcx, rax; void *
0x1800066f1  sub     rbp, [rdi]
0x1800066f4  mov     sil, 1
0x1800066f7  mov     rdx, [rdi]; Src
0x1800066fa  sar     rbp, 1
0x1800066fd  lea     r8, ds:2[rbp*2]; Size
0x180006705  call    memcpy_0
0x18000670a  lea     r15, [rdi+10h]
0x18000670e  cmp     [rdi], r15
0x180006711  jz      short loc_180006722
0x180006713  mov     rcx, [rdi]; Block
0x180006716  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000671d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006722  lea     rax, [rbx+rbp*2]
0x180006726  mov     [rdi], rbx
0x180006729  mov     [rdi+8], rax
0x18000672d  lea     rax, [r14-2]
0x180006731  add     rax, rbx
0x180006734  mov     [r15], rax
0x180006737  jmp     short loc_18000673C
0x180006739  xor     sil, sil
0x18000673c  mov     al, sil
0x18000673f  add     rsp, 28h
0x180006743  pop     r15
0x180006745  pop     r14
0x180006747  pop     rdi
0x180006748  pop     rsi
0x180006749  pop     rbp
0x18000674a  pop     rbx
0x18000674b  retn
```
