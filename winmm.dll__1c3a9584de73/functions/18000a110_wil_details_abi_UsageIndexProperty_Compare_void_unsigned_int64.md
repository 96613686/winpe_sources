# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000a110`
- end: `0x18000a13c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800068f4`
- `0x180006c6c`

## callees

- `0x18000a110`
- `0x18001a805`

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
0x18000a110  sub     rsp, 28h
0x18000a114  movzx   eax, word ptr [rcx+8]
0x18000a118  mov     r9, rdx
0x18000a11b  cmp     r8, rax
0x18000a11e  jnz     short loc_18000A131
0x18000a120  mov     rdx, [rcx+18h]; Buf2
0x18000a124  mov     rcx, r9; Buf1
0x18000a127  call    memcmp_0
0x18000a12c  mov     r8d, eax
0x18000a12f  jmp     short loc_18000A134
0x18000a131  sub     r8d, eax
0x18000a134  mov     eax, r8d
0x18000a137  add     rsp, 28h
0x18000a13b  retn
```
