# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000bcac`
- end: `0x18000bd06`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e98`
- `0x180007fd8`
- `0x180008118`
- `0x1800097ac`
- `0x18000984c`
- `0x18000af90`
- `0x18000b124`

## callees

- `0x18000bc7c`
- `0x18000bcac`
- `0x18000f1d8`

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
0x18000bcac  mov     [rsp+arg_0], rbx
0x18000bcb1  mov     [rsp+arg_8], rsi
0x18000bcb6  push    rdi
0x18000bcb7  sub     rsp, 20h
0x18000bcbb  mov     rsi, rdx
0x18000bcbe  mov     rdi, r8
0x18000bcc1  mov     rdx, r8; unsigned __int64
0x18000bcc4  mov     rbx, rcx
0x18000bcc7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000bccc  test    al, al
0x18000bcce  jz      short loc_18000BCF6
0x18000bcd0  mov     rcx, [rbx+8]; Destination
0x18000bcd4  mov     r9, rdi; SourceSize
0x18000bcd7  mov     rax, [rbx+10h]
0x18000bcdb  mov     r8, rsi; Source
0x18000bcde  sub     rax, rcx
0x18000bce1  cmp     rcx, [rbx+10h]
0x18000bce5  sbb     rdx, rdx
0x18000bce8  and     rdx, rax; DestinationSize
0x18000bceb  call    memcpy_s
0x18000bcf0  add     [rbx+8], rdi
0x18000bcf4  mov     al, 1
0x18000bcf6  mov     rbx, [rsp+28h+arg_0]
0x18000bcfb  mov     rsi, [rsp+28h+arg_8]
0x18000bd00  add     rsp, 20h
0x18000bd04  pop     rdi
0x18000bd05  retn
```
