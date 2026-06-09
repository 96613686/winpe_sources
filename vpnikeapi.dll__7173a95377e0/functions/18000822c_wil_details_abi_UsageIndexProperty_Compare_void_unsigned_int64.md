# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000822c`
- end: `0x180008258`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008628`
- `0x1800099bc`
- `0x18000a7b4`

## callees

- `0x18000822c`
- `0x18000cfa6`

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
0x18000822c  sub     rsp, 28h
0x180008230  movzx   eax, word ptr [rcx+8]
0x180008234  mov     r9, rdx
0x180008237  cmp     r8, rax
0x18000823a  jnz     short loc_18000824D
0x18000823c  mov     rdx, [rcx+18h]; Buf2
0x180008240  mov     rcx, r9; Buf1
0x180008243  call    memcmp_0
0x180008248  mov     r8d, eax
0x18000824b  jmp     short loc_180008250
0x18000824d  sub     r8d, eax
0x180008250  mov     eax, r8d
0x180008253  add     rsp, 28h
0x180008257  retn
```
