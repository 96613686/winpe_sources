# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180017b0c`
- end: `0x180017b38`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017e44`
- `0x1800190e4`
- `0x180019d60`

## callees

- `0x180017b0c`
- `0x18001bc96`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexProperty::Compare(const void **this, void *a2, size_t a3)
{
  __int64 v3; // rax

  v3 = *((unsigned __int16 *)this + 4);
  if ( a3 == v3 )
    return (unsigned int)memcmp_0(a2, this[3], a3);
  else
    return (unsigned int)(a3 - v3);
}

```

## disassembly

```asm
0x180017b0c  sub     rsp, 28h
0x180017b10  movzx   eax, word ptr [rcx+8]
0x180017b14  mov     r9, rdx
0x180017b17  cmp     r8, rax
0x180017b1a  jnz     short loc_180017B2D
0x180017b1c  mov     rdx, [rcx+18h]; Buf2
0x180017b20  mov     rcx, r9; Buf1
0x180017b23  call    memcmp_0
0x180017b28  mov     r8d, eax
0x180017b2b  jmp     short loc_180017B30
0x180017b2d  sub     r8d, eax
0x180017b30  mov     eax, r8d
0x180017b33  add     rsp, 28h
0x180017b37  retn
```
