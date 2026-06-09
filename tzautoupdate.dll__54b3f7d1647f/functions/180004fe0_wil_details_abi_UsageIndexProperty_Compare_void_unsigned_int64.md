# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180004fe0`
- end: `0x18000500c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000556c`
- `0x180006e28`
- `0x180007e38`

## callees

- `0x180004fe0`
- `0x18001b0ea`

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
0x180004fe0  sub     rsp, 28h
0x180004fe4  movzx   eax, word ptr [rcx+8]
0x180004fe8  mov     r9, rdx
0x180004feb  cmp     r8, rax
0x180004fee  jnz     short loc_180005001
0x180004ff0  mov     rdx, [rcx+18h]; Buf2
0x180004ff4  mov     rcx, r9; Buf1
0x180004ff7  call    memcmp_0
0x180004ffc  mov     r8d, eax
0x180004fff  jmp     short loc_180005004
0x180005001  sub     r8d, eax
0x180005004  mov     eax, r8d
0x180005007  add     rsp, 28h
0x18000500b  retn
```
