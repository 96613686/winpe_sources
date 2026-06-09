# wsm_wstring::serialize(write_buffer_aligned &)

- ea: `0x14000d530`
- end: `0x14000d5da`
- name: `?serialize@wsm_wstring@@UEBAJAEAVwrite_buffer_aligned@@@Z`
- size: `170`
- prototype: `int(wsm_wstring *__hidden this, struct write_buffer_aligned *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008c90`
- `0x14000d530`
- `0x14000d734`

## pseudocode

```c
unsigned __int64 __fastcall wsm_wstring::serialize(wsm_wstring *this, struct write_buffer_aligned *a2)
{
  _QWORD *v2; // r8
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 result; // rax
  const unsigned __int8 **v8; // rax
  const unsigned __int8 *v9; // rdx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v5 = (__int64)(v2[1] - *v2) >> 1;
    if ( v5 )
    {
      v6 = v5 + 1;
      if ( v5 + 1 < v5 )
        return 3221225621LL;
      v10 = 0;
      LOWORD(v5) = 2 * v6;
      if ( !is_mul_ok(v6, 2u) || 2 * v6 > 0xFFFF )
        return 3221225621LL;
    }
  }
  else
  {
    LOWORD(v5) = 0;
  }
  LOWORD(v10) = v5;
  result = write_buffer_aligned::write<unsigned short>(a2, (unsigned __int8 *)&v10);
  if ( (result & 0x80000000) == 0LL && (_WORD)v10 )
  {
    v8 = (const unsigned __int8 **)*((_QWORD *)this + 1);
    if ( v8 )
      v9 = *v8;
    else
      v9 = 0;
    return write_buffer_aligned::write_pcwstr(a2, v9, v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000d530  mov     [rsp+arg_8], rbx
0x14000d535  mov     [rsp+arg_10], rsi
0x14000d53a  push    rdi
0x14000d53b  sub     rsp, 20h
0x14000d53f  mov     r8, [rcx+8]
0x14000d543  xor     esi, esi
0x14000d545  mov     rdi, rdx
0x14000d548  mov     rbx, rcx
0x14000d54b  test    r8, r8
0x14000d54e  jz      short loc_14000D58A
0x14000d550  mov     rax, [r8]
0x14000d553  mov     r8, [r8+8]
0x14000d557  sub     r8, rax
0x14000d55a  sar     r8, 1
0x14000d55d  jz      short loc_14000D58D
0x14000d55f  lea     rcx, [r8+1]
0x14000d563  cmp     rcx, r8
0x14000d566  jb      short loc_14000D583
0x14000d568  lea     eax, [rsi+2]
0x14000d56b  mov     [rsp+28h+arg_0], rsi
0x14000d570  mul     rcx
0x14000d573  mov     r8, rax
0x14000d576  test    rdx, rdx
0x14000d579  jnz     short loc_14000D583
0x14000d57b  cmp     rax, 0FFFFh
0x14000d581  jbe     short loc_14000D58D
0x14000d583  mov     eax, 0C0000095h
0x14000d588  jmp     short loc_14000D5C9
0x14000d58a  mov     r8, rsi
0x14000d58d  lea     rdx, [rsp+28h+arg_0]; unsigned __int8 *
0x14000d592  mov     word ptr [rsp+28h+arg_0], r8w
0x14000d598  mov     rcx, rdi; this
0x14000d59b  call    ??$write@G@write_buffer_aligned@@QEAAJAEBG@Z; write_buffer_aligned::write<ushort>(ushort const &)
0x14000d5a0  test    eax, eax
0x14000d5a2  js      short loc_14000D5C9
0x14000d5a4  movzx   r8d, word ptr [rsp+28h+arg_0]; unsigned __int16
0x14000d5aa  test    r8w, r8w
0x14000d5ae  jz      short loc_14000D5C9
0x14000d5b0  mov     rax, [rbx+8]
0x14000d5b4  test    rax, rax
0x14000d5b7  jz      short loc_14000D5BE
0x14000d5b9  mov     rdx, [rax]
0x14000d5bc  jmp     short loc_14000D5C1
0x14000d5be  mov     rdx, rsi; unsigned __int16 *
0x14000d5c1  mov     rcx, rdi; this
0x14000d5c4  call    ?write_pcwstr@write_buffer_aligned@@QEAAJPEBGG@Z; write_buffer_aligned::write_pcwstr(ushort const *,ushort)
0x14000d5c9  mov     rbx, [rsp+28h+arg_8]
0x14000d5ce  mov     rsi, [rsp+28h+arg_10]
0x14000d5d3  add     rsp, 20h
0x14000d5d7  pop     rdi
0x14000d5d8  retn
```
