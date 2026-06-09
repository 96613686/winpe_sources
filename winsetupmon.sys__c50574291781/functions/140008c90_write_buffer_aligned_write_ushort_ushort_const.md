# write_buffer_aligned::write<ushort>(ushort const &)

- ea: `0x140008c90`
- end: `0x140008d7a`
- name: `??$write@G@write_buffer_aligned@@QEAAJAEBG@Z`
- size: `234`
- prototype: `__int64 __fastcall(write_buffer_uchar *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d530`

## callees

- `0x140008c90`
- `0x14000cfa0`
- `0x14000d5e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d53`

## pseudocode

```c
unsigned __int64 __fastcall write_buffer_aligned::write<unsigned short>(write_buffer_uchar *this, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  PVOID v6; // rbx
  int v7; // esi
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]

  v4 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  if ( (v4 & 1) == 0 )
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 2u);
  v9 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::resize(P, v4 & 1) )
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
    return (unsigned __int64)write_buffer_uchar::write(this, a2, 2u);
  }
  if ( v6 != (PVOID)-1LL && v6 )
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008c90  push    rbx
0x140008c92  push    rbp
0x140008c93  push    rsi
0x140008c94  push    rdi
0x140008c95  sub     rsp, 48h
0x140008c99  mov     rbp, rdx
0x140008c9c  mov     rdi, rcx
0x140008c9f  mov     rdx, [rcx+8]
0x140008ca3  sub     rdx, [rcx]
0x140008ca6  test    dl, 1
0x140008ca9  jz      loc_140008D5F
0x140008caf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140008cb7  lea     rcx, [rsp+68h+P]
0x140008cbc  and     edx, 1
0x140008cbf  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x140008cc8  movdqu  xmmword ptr [rsp+68h+P], xmm0
0x140008cce  call    ?resize@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::resize(unsigned __int64)
0x140008cd3  test    al, al
0x140008cd5  jnz     short loc_140008CFF
0x140008cd7  mov     rcx, [rsp+68h+P]; P
0x140008cdc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140008ce0  jz      short loc_140008CF8
0x140008ce2  test    rcx, rcx
0x140008ce5  jz      short loc_140008CF8
0x140008ce7  mov     edx, 6E6D7377h; Tag
0x140008cec  call    cs:__imp_ExFreePoolWithTag
0x140008cf3  nop     dword ptr [rax+rax+00h]
0x140008cf8  mov     eax, 0C000009Ah
0x140008cfd  jmp     short loc_140008D70
0x140008cff  mov     r8d, dword ptr [rsp+68h+P+8]
0x140008d04  mov     rcx, rdi; this
0x140008d07  mov     rbx, [rsp+68h+P]
0x140008d0c  sub     r8d, ebx; unsigned int
0x140008d0f  mov     rdx, rbx; unsigned __int8 *
0x140008d12  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008d17  mov     esi, eax
0x140008d19  test    eax, eax
0x140008d1b  jns     short loc_140008D40
0x140008d1d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008d21  jz      short loc_140008D3C
0x140008d23  test    rbx, rbx
0x140008d26  jz      short loc_140008D3C
0x140008d28  mov     edx, 6E6D7377h; Tag
0x140008d2d  mov     rcx, rbx; P
0x140008d30  call    cs:__imp_ExFreePoolWithTag
0x140008d37  nop     dword ptr [rax+rax+00h]
0x140008d3c  mov     eax, esi
0x140008d3e  jmp     short loc_140008D70
0x140008d40  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008d44  jz      short loc_140008D5F
0x140008d46  test    rbx, rbx
0x140008d49  jz      short loc_140008D5F
0x140008d4b  mov     edx, 6E6D7377h; Tag
0x140008d50  mov     rcx, rbx; P
0x140008d53  call    cs:__imp_ExFreePoolWithTag
0x140008d5a  nop     dword ptr [rax+rax+00h]
0x140008d5f  mov     r8d, 2; unsigned int
0x140008d65  mov     rdx, rbp; unsigned __int8 *
0x140008d68  mov     rcx, rdi; this
0x140008d6b  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x140008d70  add     rsp, 48h
0x140008d74  pop     rdi
0x140008d75  pop     rsi
0x140008d76  pop     rbp
0x140008d77  pop     rbx
0x140008d78  retn
```
