# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180007864`
- end: `0x180007890`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003af0`
- `0x180007c64`
- `0x1800092bc`

## callees

- `0x180007864`
- `0x180015030`

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
0x180007864  sub     rsp, 28h
0x180007868  movzx   eax, word ptr [rcx+8]
0x18000786c  mov     r9, rdx
0x18000786f  cmp     r8, rax
0x180007872  jnz     short loc_180007885
0x180007874  mov     rdx, [rcx+18h]; Buf2
0x180007878  mov     rcx, r9; Buf1
0x18000787b  call    memcmp_0
0x180007880  mov     r8d, eax
0x180007883  jmp     short loc_180007888
0x180007885  sub     r8d, eax
0x180007888  mov     eax, r8d
0x18000788b  add     rsp, 28h
0x18000788f  retn
```
