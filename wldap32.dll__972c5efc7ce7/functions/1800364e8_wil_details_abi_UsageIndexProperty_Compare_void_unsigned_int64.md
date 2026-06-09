# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1800364e8`
- end: `0x180036515`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `45`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033dd8`
- `0x1800367bc`
- `0x1800377a0`

## callees

- `0x1800364e8`
- `0x18004c760`

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
0x1800364e8  sub     rsp, 28h
0x1800364ec  movzx   eax, word ptr [rcx+8]
0x1800364f0  mov     r9, rdx
0x1800364f3  cmp     r8, rax
0x1800364f6  jnz     short loc_180036509
0x1800364f8  mov     rdx, [rcx+18h]; Buf2
0x1800364fc  mov     rcx, r9; Buf1
0x1800364ff  call    memcmp_0
0x180036504  mov     r8d, eax
0x180036507  jmp     short loc_18003650C
0x180036509  sub     r8d, eax
0x18003650c  mov     eax, r8d
0x18003650f  add     rsp, 28h
0x180036513  retn
```
