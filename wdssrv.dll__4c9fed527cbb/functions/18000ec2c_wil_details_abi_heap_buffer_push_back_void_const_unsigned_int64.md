# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000ec2c`
- end: `0x18000ecd1`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `165`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, const void *Source, rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae68`
- `0x18000afb4`
- `0x18000da58`
- `0x18000dd34`

## callees

- `0x18000ec2c`
- `0x18000ecd8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000eca4`
- `msvcrt!memcpy_s` at `0x18000eca4`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(
        wil::details_abi::heap_buffer *this,
        const void *Source,
        rsize_t SourceSize)
{
  rsize_t v6; // rcx
  _QWORD *v7; // rdi
  unsigned __int64 v8; // rdx
  bool result; // al

  v6 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( SourceSize + *((_QWORD *)this + 1) - *(_QWORD *)this < v6 )
  {
    v7 = (_QWORD *)((char *)this + 8);
LABEL_7:
    memcpy_s(
      *((void *const *)this + 1),
      (*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) & -(__int64)(*((_QWORD *)this + 1) < *((_QWORD *)this + 2)),
      Source,
      SourceSize);
    *v7 += SourceSize;
    return 1;
  }
  v8 = SourceSize;
  if ( SourceSize < 2 * v6 )
    v8 = 2 * v6;
  result = wil::details_abi::heap_buffer::reserve(this, v8);
  if ( result )
  {
    v7 = (_QWORD *)((char *)this + 8);
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x18000ec2c  mov     rax, rsp
0x18000ec2f  mov     [rax+8], rbx
0x18000ec33  mov     [rax+10h], rbp
0x18000ec37  mov     [rax+18h], rsi
0x18000ec3b  mov     [rax+20h], rdi
0x18000ec3f  push    r14
0x18000ec41  sub     rsp, 20h
0x18000ec45  mov     rbx, rcx
0x18000ec48  mov     rbp, r8
0x18000ec4b  mov     rcx, [rcx+10h]
0x18000ec4f  mov     r14, rdx
0x18000ec52  sub     rcx, [rbx]
0x18000ec55  lea     rsi, [rbx+8]
0x18000ec59  mov     rax, [rsi]
0x18000ec5c  sub     rax, [rbx]
0x18000ec5f  add     rax, r8
0x18000ec62  cmp     rax, rcx
0x18000ec65  jnb     short loc_18000EC6C
0x18000ec67  mov     rdi, rsi
0x18000ec6a  jmp     short loc_18000EC8A
0x18000ec6c  lea     rax, [rcx+rcx]
0x18000ec70  mov     rdx, rbp
0x18000ec73  cmp     rbp, rax
0x18000ec76  mov     rcx, rbx; this
0x18000ec79  cmovb   rdx, rax; unsigned __int64
0x18000ec7d  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x18000ec82  test    al, al
0x18000ec84  jz      short loc_18000ECB5
0x18000ec86  lea     rdi, [rbx+8]
0x18000ec8a  mov     rcx, [rsi]; Destination
0x18000ec8d  mov     r9, rbp; SourceSize
0x18000ec90  mov     rax, [rbx+10h]
0x18000ec94  mov     r8, r14; Source
0x18000ec97  sub     rax, rcx
0x18000ec9a  cmp     rcx, [rbx+10h]
0x18000ec9e  sbb     rdx, rdx
0x18000eca1  and     rdx, rax; DestinationSize
0x18000eca4  call    cs:__imp_memcpy_s
0x18000ecab  nop     dword ptr [rax+rax+00h]
0x18000ecb0  add     [rdi], rbp
0x18000ecb3  mov     al, 1
0x18000ecb5  mov     rbx, [rsp+28h+arg_0]
0x18000ecba  mov     rbp, [rsp+28h+arg_8]
0x18000ecbf  mov     rsi, [rsp+28h+arg_10]
0x18000ecc4  mov     rdi, [rsp+28h+arg_18]
0x18000ecc9  add     rsp, 20h
0x18000eccd  pop     r14
0x18000eccf  retn
```
