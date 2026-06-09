# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000c9cc`
- end: `0x18000c9f9`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `45`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cf28`
- `0x18000e170`
- `0x18000f4e8`

## callees

- `0x18000c9cc`
- `0x18001c860`

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
0x18000c9cc  sub     rsp, 28h
0x18000c9d0  movzx   eax, word ptr [rcx+8]
0x18000c9d4  mov     r9, rdx
0x18000c9d7  cmp     r8, rax
0x18000c9da  jnz     short loc_18000C9ED
0x18000c9dc  mov     rdx, [rcx+18h]; Buf2
0x18000c9e0  mov     rcx, r9; Buf1
0x18000c9e3  call    memcmp_0
0x18000c9e8  mov     r8d, eax
0x18000c9eb  jmp     short loc_18000C9F0
0x18000c9ed  sub     r8d, eax
0x18000c9f0  mov     eax, r8d
0x18000c9f3  add     rsp, 28h
0x18000c9f7  retn
```
