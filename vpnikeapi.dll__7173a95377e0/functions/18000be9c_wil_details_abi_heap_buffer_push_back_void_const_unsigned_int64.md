# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000be9c`
- end: `0x18000bef7`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `91`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0a4`
- `0x18000b21c`
- `0x18000b3d8`

## callees

- `0x18000be6c`
- `0x18000be9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bedb`
- `msvcrt!memcpy_s` at `0x18000bedb`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(void **this, const void *a2, unsigned __int64 a3)
{
  bool result; // al

  result = wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)this, a3);
  if ( result )
  {
    memcpy_s(this[1], ((_BYTE *)this[2] - (_BYTE *)this[1]) & -(__int64)(this[1] < this[2]), a2, a3);
    this[1] = (char *)this[1] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000be9c  mov     [rsp+arg_0], rbx
0x18000bea1  mov     [rsp+arg_8], rsi
0x18000bea6  push    rdi
0x18000bea7  sub     rsp, 20h
0x18000beab  mov     rsi, rdx
0x18000beae  mov     rdi, r8
0x18000beb1  mov     rdx, r8; unsigned __int64
0x18000beb4  mov     rbx, rcx
0x18000beb7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000bebc  test    al, al
0x18000bebe  jz      short loc_18000BEE7
0x18000bec0  mov     rcx, [rbx+8]; Destination
0x18000bec4  mov     r9, rdi; SourceSize
0x18000bec7  mov     rax, [rbx+10h]
0x18000becb  mov     r8, rsi; Source
0x18000bece  sub     rax, rcx
0x18000bed1  cmp     rcx, [rbx+10h]
0x18000bed5  sbb     rdx, rdx
0x18000bed8  and     rdx, rax; DestinationSize
0x18000bedb  call    cs:__imp_memcpy_s
0x18000bee1  add     [rbx+8], rdi
0x18000bee5  mov     al, 1
0x18000bee7  mov     rbx, [rsp+28h+arg_0]
0x18000beec  mov     rsi, [rsp+28h+arg_8]
0x18000bef1  add     rsp, 20h
0x18000bef5  pop     rdi
0x18000bef6  retn
```
