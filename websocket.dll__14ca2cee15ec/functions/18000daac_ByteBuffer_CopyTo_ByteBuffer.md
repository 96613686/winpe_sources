# ByteBuffer::CopyTo(ByteBuffer *)

- ea: `0x18000daac`
- end: `0x18000db00`
- name: `?CopyTo@ByteBuffer@@QEAAXPEAV1@@Z`
- size: `84`
- prototype: `void __fastcall(ByteBuffer *__hidden this, struct ByteBuffer *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb2c`
- `0x18000c7c0`

## callees

- `0x18000daac`
- `0x18000dc00`

## pseudocode

```c
void __fastcall ByteBuffer::CopyTo(ByteBuffer *this, struct ByteBuffer *a2)
{
  unsigned int v4; // ebx

  v4 = *((_DWORD *)this + 3) - *((_DWORD *)this + 4);
  if ( v4 >= *((_DWORD *)a2 + 2) - *((_DWORD *)a2 + 3) )
    v4 = *((_DWORD *)a2 + 2) - *((_DWORD *)a2 + 3);
  if ( v4 )
  {
    memcpy_0(
      (void *)(*(_QWORD *)a2 + *((unsigned int *)a2 + 3)),
      (const void *)(*(_QWORD *)this + *((unsigned int *)this + 4)),
      v4);
    *((_DWORD *)this + 4) += v4;
    *((_DWORD *)a2 + 3) += v4;
  }
}

```

## disassembly

```asm
0x18000daac  mov     [rsp+arg_0], rbx
0x18000dab1  mov     [rsp+arg_8], rsi
0x18000dab6  push    rdi
0x18000dab7  sub     rsp, 20h
0x18000dabb  mov     eax, [rdx+8]
0x18000dabe  mov     rdi, rdx
0x18000dac1  sub     eax, [rdx+0Ch]
0x18000dac4  mov     rsi, rcx
0x18000dac7  mov     ebx, [rcx+0Ch]
0x18000daca  sub     ebx, [rcx+10h]
0x18000dacd  cmp     ebx, eax
0x18000dacf  cmovnb  ebx, eax
0x18000dad2  test    ebx, ebx
0x18000dad4  jz      short loc_18000DAF0
0x18000dad6  mov     edx, [rcx+10h]
0x18000dad9  add     rdx, [rcx]; Src
0x18000dadc  mov     ecx, [rdi+0Ch]
0x18000dadf  add     rcx, [rdi]; void *
0x18000dae2  mov     r8d, ebx; Size
0x18000dae5  call    memcpy_0
0x18000daea  add     [rsi+10h], ebx
0x18000daed  add     [rdi+0Ch], ebx
0x18000daf0  mov     rbx, [rsp+28h+arg_0]
0x18000daf5  mov     rsi, [rsp+28h+arg_8]
0x18000dafa  add     rsp, 20h
0x18000dafe  pop     rdi
0x18000daff  retn
```
