# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180018eb8`
- end: `0x180018ee5`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `45`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019218`
- `0x18001a560`
- `0x18001b25c`

## callees

- `0x180018eb8`
- `0x18001d1b6`

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
0x180018eb8  sub     rsp, 28h
0x180018ebc  movzx   eax, word ptr [rcx+8]
0x180018ec0  mov     r9, rdx
0x180018ec3  cmp     r8, rax
0x180018ec6  jnz     short loc_180018ED9
0x180018ec8  mov     rdx, [rcx+18h]; Buf2
0x180018ecc  mov     rcx, r9; Buf1
0x180018ecf  call    memcmp_0
0x180018ed4  mov     r8d, eax
0x180018ed7  jmp     short loc_180018EDC
0x180018ed9  sub     r8d, eax
0x180018edc  mov     eax, r8d
0x180018edf  add     rsp, 28h
0x180018ee3  retn
```
