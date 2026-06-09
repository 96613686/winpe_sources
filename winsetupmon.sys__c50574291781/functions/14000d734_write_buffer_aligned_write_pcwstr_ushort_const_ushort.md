# write_buffer_aligned::write_pcwstr(ushort const *,ushort)

- ea: `0x14000d734`
- end: `0x14000d823`
- name: `?write_pcwstr@write_buffer_aligned@@QEAAJPEBGG@Z`
- size: `239`
- prototype: `__int64 __fastcall(write_buffer_aligned *__hidden this, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d530`

## callees

- `0x14000cfa0`
- `0x14000d5e0`
- `0x14000d734`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d796`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d796`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7fd`

## pseudocode

```c
unsigned __int64 __fastcall write_buffer_aligned::write_pcwstr(
        write_buffer_aligned *this,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  unsigned int v4; // ebp
  __int64 v6; // rdx
  PVOID v8; // rbx
  int v9; // esi
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]

  v4 = a3;
  v6 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  if ( (v6 & 1) == 0 )
    return (unsigned __int64)write_buffer_uchar::write(this, a2, v4);
  v11 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::resize(P, v6 & 1) )
  {
    if ( P[0] != (PVOID)-1LL )
    {
      if ( P[0] )
        ExFreePoolWithTag(P[0], 0x6E6D7377u);
    }
    return 3221225626LL;
  }
  v8 = P[0];
  v9 = (unsigned int)write_buffer_uchar::write(this, (const unsigned __int8 *const)P[0], LODWORD(P[1]) - LODWORD(P[0]));
  if ( v9 >= 0 )
  {
    if ( v8 != (PVOID)-1LL && v8 )
      ExFreePoolWithTag(v8, 0x6E6D7377u);
    return (unsigned __int64)write_buffer_uchar::write(this, a2, v4);
  }
  if ( v8 != (PVOID)-1LL && v8 )
    ExFreePoolWithTag(v8, 0x6E6D7377u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000d734  push    rbx
0x14000d736  push    rbp
0x14000d737  push    rsi
0x14000d738  push    rdi
0x14000d739  push    r14
0x14000d73b  sub     rsp, 40h
0x14000d73f  mov     r14, rdx
0x14000d742  movzx   ebp, r8w
0x14000d746  mov     rdx, [rcx+8]
0x14000d74a  mov     rdi, rcx
0x14000d74d  sub     rdx, [rcx]
0x14000d750  test    dl, 1
0x14000d753  jz      loc_14000D809
0x14000d759  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000d761  lea     rcx, [rsp+68h+P]
0x14000d766  and     edx, 1
0x14000d769  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x14000d772  movdqu  xmmword ptr [rsp+68h+P], xmm0
0x14000d778  call    ?resize@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::resize(unsigned __int64)
0x14000d77d  test    al, al
0x14000d77f  jnz     short loc_14000D7A9
0x14000d781  mov     rcx, [rsp+68h+P]; P
0x14000d786  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d78a  jz      short loc_14000D7A2
0x14000d78c  test    rcx, rcx
0x14000d78f  jz      short loc_14000D7A2
0x14000d791  mov     edx, 6E6D7377h; Tag
0x14000d796  call    cs:__imp_ExFreePoolWithTag
0x14000d79d  nop     dword ptr [rax+rax+00h]
0x14000d7a2  mov     eax, 0C000009Ah
0x14000d7a7  jmp     short loc_14000D817
0x14000d7a9  mov     r8d, dword ptr [rsp+68h+P+8]
0x14000d7ae  mov     rcx, rdi; this
0x14000d7b1  mov     rbx, [rsp+68h+P]
0x14000d7b6  sub     r8d, ebx; unsigned int
0x14000d7b9  mov     rdx, rbx; unsigned __int8 *
0x14000d7bc  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x14000d7c1  mov     esi, eax
0x14000d7c3  test    eax, eax
0x14000d7c5  jns     short loc_14000D7EA
0x14000d7c7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d7cb  jz      short loc_14000D7E6
0x14000d7cd  test    rbx, rbx
0x14000d7d0  jz      short loc_14000D7E6
0x14000d7d2  mov     edx, 6E6D7377h; Tag
0x14000d7d7  mov     rcx, rbx; P
0x14000d7da  call    cs:__imp_ExFreePoolWithTag
0x14000d7e1  nop     dword ptr [rax+rax+00h]
0x14000d7e6  mov     eax, esi
0x14000d7e8  jmp     short loc_14000D817
0x14000d7ea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d7ee  jz      short loc_14000D809
0x14000d7f0  test    rbx, rbx
0x14000d7f3  jz      short loc_14000D809
0x14000d7f5  mov     edx, 6E6D7377h; Tag
0x14000d7fa  mov     rcx, rbx; P
0x14000d7fd  call    cs:__imp_ExFreePoolWithTag
0x14000d804  nop     dword ptr [rax+rax+00h]
0x14000d809  mov     r8d, ebp; unsigned int
0x14000d80c  mov     rdx, r14; unsigned __int8 *
0x14000d80f  mov     rcx, rdi; this
0x14000d812  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x14000d817  add     rsp, 40h
0x14000d81b  pop     r14
0x14000d81d  pop     rdi
0x14000d81e  pop     rsi
0x14000d81f  pop     rbp
0x14000d820  pop     rbx
0x14000d821  retn
```
