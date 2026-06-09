# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000ab8c`
- end: `0x18000abb8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007188`
- `0x18000b200`
- `0x18000b608`

## callees

- `0x18000ab8c`
- `0x18000f9b6`

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
0x18000ab8c  sub     rsp, 28h
0x18000ab90  movzx   eax, word ptr [rcx+8]
0x18000ab94  mov     r9, rdx
0x18000ab97  cmp     r8, rax
0x18000ab9a  jnz     short loc_18000ABAD
0x18000ab9c  mov     rdx, [rcx+18h]; Buf2
0x18000aba0  mov     rcx, r9; Buf1
0x18000aba3  call    memcmp_0
0x18000aba8  mov     r8d, eax
0x18000abab  jmp     short loc_18000ABB0
0x18000abad  sub     r8d, eax
0x18000abb0  mov     eax, r8d
0x18000abb3  add     rsp, 28h
0x18000abb7  retn
```
