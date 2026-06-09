# write_buffer_aligned::write<ulong>(ulong const &)

- ea: `0x140008d80`
- end: `0x140008e6a`
- name: `??$write@K@write_buffer_aligned@@QEAAJAEBK@Z`
- size: `234`
- prototype: `__int64 __fastcall(write_buffer_uchar *this, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d380`
- `0x14000d440`
- `0x14000d4b0`

## callees

- `0x140008d80`
- `0x14000cfa0`
- `0x14000d5e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008ddc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ddc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e43`

## pseudocode

```c
unsigned __int64 __fastcall write_buffer_aligned::write<unsigned long>(write_buffer_uchar *this, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  PVOID v6; // rbx
  int v7; // esi
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]

  v4 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  if ( (v4 & 3) == 0 )
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 4u);
  v9 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::resize(P, v4 & 3) )
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
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 4u);
  }
  if ( v6 != (PVOID)-1LL && v6 )
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008d80  push    rbx
0x140008d82  push    rbp
0x140008d83  push    rsi
0x140008d84  push    rdi
0x140008d85  sub     rsp, 48h
0x140008d89  mov     rbp, rdx
0x140008d8c  mov     rdi, rcx
0x140008d8f  mov     rdx, [rcx+8]
0x140008d93  sub     rdx, [rcx]
0x140008d96  test    dl, 3
0x140008d99  jz      loc_140008E4F
0x140008d9f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008da7  lea     rcx, [rsp+68h+P]
0x140008dac  and     edx, 3
0x140008daf  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x140008db8  movdqu  xmmword ptr [rsp+68h+P], xmm0
0x140008dbe  call    ?resize@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::resize(unsigned __int64)
0x140008dc3  test    al, al
0x140008dc5  jnz     short loc_140008DEF
0x140008dc7  mov     rcx, [rsp+68h+P]; P
0x140008dcc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140008dd0  jz      short loc_140008DE8
0x140008dd2  test    rcx, rcx
0x140008dd5  jz      short loc_140008DE8
0x140008dd7  mov     edx, 6E6D7377h; Tag
0x140008ddc  call    cs:__imp_ExFreePoolWithTag
0x140008de3  nop     dword ptr [rax+rax+00h]
0x140008de8  mov     eax, 0C000009Ah
0x140008ded  jmp     short loc_140008E60
0x140008def  mov     r8d, dword ptr [rsp+68h+P+8]
0x140008df4  mov     rcx, rdi; this
0x140008df7  mov     rbx, [rsp+68h+P]
0x140008dfc  sub     r8d, ebx; unsigned int
0x140008dff  mov     rdx, rbx; unsigned __int8 *
0x140008e02  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008e07  mov     esi, eax
0x140008e09  test    eax, eax
0x140008e0b  jns     short loc_140008E30
0x140008e0d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008e11  jz      short loc_140008E2C
0x140008e13  test    rbx, rbx
0x140008e16  jz      short loc_140008E2C
0x140008e18  mov     edx, 6E6D7377h; Tag
0x140008e1d  mov     rcx, rbx; P
0x140008e20  call    cs:__imp_ExFreePoolWithTag
0x140008e27  nop     dword ptr [rax+rax+00h]
0x140008e2c  mov     eax, esi
0x140008e2e  jmp     short loc_140008E60
0x140008e30  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008e34  jz      short loc_140008E4F
0x140008e36  test    rbx, rbx
0x140008e39  jz      short loc_140008E4F
0x140008e3b  mov     edx, 6E6D7377h; Tag
0x140008e40  mov     rcx, rbx; P
0x140008e43  call    cs:__imp_ExFreePoolWithTag
0x140008e4a  nop     dword ptr [rax+rax+00h]
0x140008e4f  mov     r8d, 4; unsigned int
0x140008e55  mov     rdx, rbp; unsigned __int8 *
0x140008e58  mov     rcx, rdi; this
0x140008e5b  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008e60  add     rsp, 48h
0x140008e64  pop     rdi
0x140008e65  pop     rsi
0x140008e66  pop     rbp
0x140008e67  pop     rbx
0x140008e68  retn
```
