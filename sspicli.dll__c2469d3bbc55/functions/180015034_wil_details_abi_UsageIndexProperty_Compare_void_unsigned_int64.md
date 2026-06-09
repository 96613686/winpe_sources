# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180015034`
- end: `0x180015060`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012620`

## callees

- `0x180015034`
- `0x18002203b`

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
0x180015034  sub     rsp, 28h
0x180015038  movzx   eax, word ptr [rcx+8]
0x18001503c  mov     r9, rdx
0x18001503f  cmp     r8, rax
0x180015042  jnz     short loc_180015055
0x180015044  mov     rdx, [rcx+18h]; Buf2
0x180015048  mov     rcx, r9; Buf1
0x18001504b  call    memcmp_0
0x180015050  mov     r8d, eax
0x180015053  jmp     short loc_180015058
0x180015055  sub     r8d, eax
0x180015058  mov     eax, r8d
0x18001505b  add     rsp, 28h
0x18001505f  retn
```
