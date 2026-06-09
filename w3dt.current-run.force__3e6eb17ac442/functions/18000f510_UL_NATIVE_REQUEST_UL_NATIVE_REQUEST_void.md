# UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(void)

- ea: `0x18000f510`
- end: `0x18000f5e9`
- name: `??0UL_NATIVE_REQUEST@@QEAA@XZ`
- size: `217`
- prototype: `UL_NATIVE_REQUEST *__fastcall(UL_NATIVE_REQUEST *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000edc0`
- `0x18000eef0`

## callees

- `0x18000f5f0`
- `0x18000f660`
- `0x180016072`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000f53e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000f53e`

## pseudocode

```c
UL_NATIVE_REQUEST *__fastcall UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(UL_NATIVE_REQUEST *this)
{
  char *v1; // rbx
  UL_NATIVE_REQUEST *result; // rax

  v1 = (char *)this + 32;
  *((_DWORD *)this + 738) = 2912;
  *((_QWORD *)this + 368) = (char *)this + 32;
  BUFFER::BUFFER((UL_NATIVE_REQUEST *)((char *)this + 2960));
  *((_QWORD *)this + 376) = 0;
  *((_QWORD *)this + 377) = 0;
  *((_QWORD *)this + 381) = 0;
  *(_OWORD *)((char *)this + 3064) = 0;
  *(_OWORD *)((char *)this + 3080) = 0;
  *((_QWORD *)this + 382) = &UL_SEND_CONTEXT::`vftable';
  *((_OWORD *)this + 194) = 0;
  *((_OWORD *)this + 195) = 0;
  *((_QWORD *)this + 387) = &UL_RECEIVE_CONTEXT::`vftable';
  *((_DWORD *)this + 784) = 0;
  *((_QWORD *)this + 379) = 0;
  *((_QWORD *)this + 380) = 0;
  UL_NATIVE_REQUEST::AddToRequestList(this);
  memset_0(v1, 0, 0xB60u);
  UL_NATIVE_REQUEST::Reset(this);
  result = this;
  *((_DWORD *)this + 756) = 0;
  *(_DWORD *)this = 1363497550;
  return result;
}

```

## disassembly

```asm
0x18000f510  mov     [rsp+arg_0], rbx
0x18000f515  mov     [rsp+arg_8], rsi
0x18000f51a  push    rdi
0x18000f51b  sub     rsp, 20h
0x18000f51f  lea     rbx, [rcx+20h]
0x18000f523  mov     dword ptr [rcx+0B88h], 0B60h
0x18000f52d  mov     [rcx+0B80h], rbx
0x18000f534  mov     rdi, rcx
0x18000f537  add     rcx, 0B90h
0x18000f53e  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000f544  xor     esi, esi
0x18000f546  lea     rax, ??_7UL_SEND_CONTEXT@@6B@; const UL_SEND_CONTEXT::`vftable'
0x18000f54d  mov     [rdi+0BC0h], rsi
0x18000f554  xorps   xmm0, xmm0
0x18000f557  mov     [rdi+0BC8h], rsi
0x18000f55e  mov     rcx, rdi; this
0x18000f561  mov     [rdi+0BE8h], rsi
0x18000f568  movups  xmmword ptr [rdi+0BF8h], xmm0
0x18000f56f  movups  xmmword ptr [rdi+0C08h], xmm0
0x18000f576  mov     [rdi+0BF0h], rax
0x18000f57d  lea     rax, ??_7UL_RECEIVE_CONTEXT@@6B@; const UL_RECEIVE_CONTEXT::`vftable'
0x18000f584  movups  xmmword ptr [rdi+0C20h], xmm0
0x18000f58b  movups  xmmword ptr [rdi+0C30h], xmm0
0x18000f592  mov     [rdi+0C18h], rax
0x18000f599  mov     [rdi+0C40h], esi
0x18000f59f  mov     [rdi+0BD8h], rsi
0x18000f5a6  mov     [rdi+0BE0h], rsi
0x18000f5ad  call    ?AddToRequestList@UL_NATIVE_REQUEST@@QEAAXXZ; UL_NATIVE_REQUEST::AddToRequestList(void)
0x18000f5b2  xor     edx, edx; Val
0x18000f5b4  mov     r8d, 0B60h; Size
0x18000f5ba  mov     rcx, rbx; void *
0x18000f5bd  call    memset_0
0x18000f5c2  mov     rcx, rdi; this
0x18000f5c5  call    ?Reset@UL_NATIVE_REQUEST@@AEAAXXZ; UL_NATIVE_REQUEST::Reset(void)
0x18000f5ca  mov     rbx, [rsp+28h+arg_0]
0x18000f5cf  mov     rax, rdi
0x18000f5d2  mov     [rdi+0BD0h], esi
0x18000f5d8  mov     rsi, [rsp+28h+arg_8]
0x18000f5dd  mov     dword ptr [rdi], 5145524Eh
0x18000f5e3  add     rsp, 20h
0x18000f5e7  pop     rdi
0x18000f5e8  retn
```
