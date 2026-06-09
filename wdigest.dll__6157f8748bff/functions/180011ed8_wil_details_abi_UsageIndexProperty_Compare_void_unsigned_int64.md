# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180011ed8`
- end: `0x180011f04`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f800`
- `0x180011978`

## callees

- `0x180011ed8`
- `0x1800377b0`

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
0x180011ed8  sub     rsp, 28h
0x180011edc  movzx   eax, word ptr [rcx+8]
0x180011ee0  mov     r9, rdx
0x180011ee3  cmp     r8, rax
0x180011ee6  jnz     short loc_180011EF9
0x180011ee8  mov     rdx, [rcx+18h]; Buf2
0x180011eec  mov     rcx, r9; Buf1
0x180011eef  call    memcmp_0
0x180011ef4  mov     r8d, eax
0x180011ef7  jmp     short loc_180011EFC
0x180011ef9  sub     r8d, eax
0x180011efc  mov     eax, r8d
0x180011eff  add     rsp, 28h
0x180011f03  retn
```
