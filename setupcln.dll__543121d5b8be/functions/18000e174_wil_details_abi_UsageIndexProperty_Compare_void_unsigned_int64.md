# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000e174`
- end: `0x18000e1a0`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e4b4`
- `0x18000f9d0`
- `0x180010654`

## callees

- `0x18000e174`
- `0x180013196`

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
0x18000e174  sub     rsp, 28h
0x18000e178  movzx   eax, word ptr [rcx+8]
0x18000e17c  mov     r9, rdx
0x18000e17f  cmp     r8, rax
0x18000e182  jnz     short loc_18000E195
0x18000e184  mov     rdx, [rcx+18h]; Buf2
0x18000e188  mov     rcx, r9; Buf1
0x18000e18b  call    memcmp_0
0x18000e190  mov     r8d, eax
0x18000e193  jmp     short loc_18000E198
0x18000e195  sub     r8d, eax
0x18000e198  mov     eax, r8d
0x18000e19b  add     rsp, 28h
0x18000e19f  retn
```
