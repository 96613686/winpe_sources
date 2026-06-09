# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000da20`
- end: `0x18000da4c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ae64`
- `0x18000dcdc`
- `0x18000ed20`

## callees

- `0x18000da20`
- `0x18001c630`

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
0x18000da20  sub     rsp, 28h
0x18000da24  movzx   eax, word ptr [rcx+8]
0x18000da28  mov     r9, rdx
0x18000da2b  cmp     r8, rax
0x18000da2e  jnz     short loc_18000DA41
0x18000da30  mov     rdx, [rcx+18h]; Buf2
0x18000da34  mov     rcx, r9; Buf1
0x18000da37  call    memcmp_0
0x18000da3c  mov     r8d, eax
0x18000da3f  jmp     short loc_18000DA44
0x18000da41  sub     r8d, eax
0x18000da44  mov     eax, r8d
0x18000da47  add     rsp, 28h
0x18000da4b  retn
```
