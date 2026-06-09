# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180027530`
- end: `0x18002755c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800277a4`
- `0x180027c64`
- `0x180028cf4`

## callees

- `0x180027530`
- `0x18002af84`

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
0x180027530  sub     rsp, 28h
0x180027534  movzx   eax, word ptr [rcx+8]
0x180027538  mov     r9, rdx
0x18002753b  cmp     r8, rax
0x18002753e  jnz     short loc_180027551
0x180027540  mov     rdx, [rcx+18h]; Buf2
0x180027544  mov     rcx, r9; Buf1
0x180027547  call    memcmp_0
0x18002754c  mov     r8d, eax
0x18002754f  jmp     short loc_180027554
0x180027551  sub     r8d, eax
0x180027554  mov     eax, r8d
0x180027557  add     rsp, 28h
0x18002755b  retn
```
