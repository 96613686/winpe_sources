# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000d32c`
- end: `0x18000d358`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d7c0`
- `0x18000f208`
- `0x1800101d8`

## callees

- `0x18000d32c`
- `0x18003c1f6`

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
0x18000d32c  sub     rsp, 28h
0x18000d330  movzx   eax, word ptr [rcx+8]
0x18000d334  mov     r9, rdx
0x18000d337  cmp     r8, rax
0x18000d33a  jnz     short loc_18000D34D
0x18000d33c  mov     rdx, [rcx+18h]; Buf2
0x18000d340  mov     rcx, r9; Buf1
0x18000d343  call    memcmp_0
0x18000d348  mov     r8d, eax
0x18000d34b  jmp     short loc_18000D350
0x18000d34d  sub     r8d, eax
0x18000d350  mov     eax, r8d
0x18000d353  add     rsp, 28h
0x18000d357  retn
```
