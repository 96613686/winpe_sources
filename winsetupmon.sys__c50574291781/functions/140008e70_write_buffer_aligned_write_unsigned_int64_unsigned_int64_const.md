# write_buffer_aligned::write<unsigned __int64>(unsigned __int64 const &)

- ea: `0x140008e70`
- end: `0x140008f5a`
- name: `??$write@_K@write_buffer_aligned@@QEAAJAEB_K@Z`
- size: `234`
- prototype: `__int64 __fastcall(write_buffer_uchar *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d300`

## callees

- `0x140008e70`
- `0x14000cfa0`
- `0x14000d5e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008ecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f33`

## pseudocode

```c
unsigned __int64 __fastcall write_buffer_aligned::write<unsigned __int64>(
        write_buffer_uchar *this,
        unsigned __int8 *a2)
{
  __int64 v4; // rdx
  PVOID v6; // rbx
  int v7; // esi
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]

  v4 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  if ( (v4 & 7) == 0 )
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 8u);
  v9 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::resize(P, v4 & 7) )
  {
    if ( P[0] != (PVOID)-1LL )
    {
      if ( P[0] )
        ExFreePoolWithTag(P[0], 0x6E6D7377u);
    }
    return 3221225626LL;
  }
  v6 = P[0];
  v7 = (unsigned int)write_buffer_uchar::write(this, (const unsigned __int8 *const)P[0], LODWORD(P[1]) - LODWORD(P[0]));
  if ( v7 >= 0 )
  {
    if ( v6 != (PVOID)-1LL && v6 )
      ExFreePoolWithTag(v6, 0x6E6D7377u);
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 8u);
  }
  if ( v6 != (PVOID)-1LL && v6 )
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008e70  push    rbx
0x140008e72  push    rbp
0x140008e73  push    rsi
0x140008e74  push    rdi
0x140008e75  sub     rsp, 48h
0x140008e79  mov     rbp, rdx
0x140008e7c  mov     rdi, rcx
0x140008e7f  mov     rdx, [rcx+8]
0x140008e83  sub     rdx, [rcx]
0x140008e86  test    dl, 7
0x140008e89  jz      loc_140008F3F
0x140008e8f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008e97  lea     rcx, [rsp+68h+P]
0x140008e9c  and     edx, 7
0x140008e9f  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x140008ea8  movdqu  xmmword ptr [rsp+68h+P], xmm0
0x140008eae  call    ?resize@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::resize(unsigned __int64)
0x140008eb3  test    al, al
0x140008eb5  jnz     short loc_140008EDF
0x140008eb7  mov     rcx, [rsp+68h+P]; P
0x140008ebc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140008ec0  jz      short loc_140008ED8
0x140008ec2  test    rcx, rcx
0x140008ec5  jz      short loc_140008ED8
0x140008ec7  mov     edx, 6E6D7377h; Tag
0x140008ecc  call    cs:__imp_ExFreePoolWithTag
0x140008ed3  nop     dword ptr [rax+rax+00h]
0x140008ed8  mov     eax, 0C000009Ah
0x140008edd  jmp     short loc_140008F50
0x140008edf  mov     r8d, dword ptr [rsp+68h+P+8]
0x140008ee4  mov     rcx, rdi; this
0x140008ee7  mov     rbx, [rsp+68h+P]
0x140008eec  sub     r8d, ebx; unsigned int
0x140008eef  mov     rdx, rbx; unsigned __int8 *
0x140008ef2  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008ef7  mov     esi, eax
0x140008ef9  test    eax, eax
0x140008efb  jns     short loc_140008F20
0x140008efd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008f01  jz      short loc_140008F1C
0x140008f03  test    rbx, rbx
0x140008f06  jz      short loc_140008F1C
0x140008f08  mov     edx, 6E6D7377h; Tag
0x140008f0d  mov     rcx, rbx; P
0x140008f10  call    cs:__imp_ExFreePoolWithTag
0x140008f17  nop     dword ptr [rax+rax+00h]
0x140008f1c  mov     eax, esi
0x140008f1e  jmp     short loc_140008F50
0x140008f20  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008f24  jz      short loc_140008F3F
0x140008f26  test    rbx, rbx
0x140008f29  jz      short loc_140008F3F
0x140008f2b  mov     edx, 6E6D7377h; Tag
0x140008f30  mov     rcx, rbx; P
0x140008f33  call    cs:__imp_ExFreePoolWithTag
0x140008f3a  nop     dword ptr [rax+rax+00h]
0x140008f3f  mov     r8d, 8; unsigned int
0x140008f45  mov     rdx, rbp; unsigned __int8 *
0x140008f48  mov     rcx, rdi; this
0x140008f4b  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008f50  add     rsp, 48h
0x140008f54  pop     rdi
0x140008f55  pop     rsi
0x140008f56  pop     rbp
0x140008f57  pop     rbx
0x140008f58  retn
```
