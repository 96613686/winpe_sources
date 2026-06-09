# Buffer::Read(void *,ulong)

- ea: `0x18000b620`
- end: `0x18000b672`
- name: `?Read@Buffer@@UEAAXPEAXK@Z`
- size: `82`
- prototype: `void __fastcall(Buffer *this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001ac6`
- `0x18000b620`
- `0x18000b804`

## pseudocode

```c
void __fastcall Buffer::Read(Buffer *this, void *a2, unsigned int a3)
{
  if ( !*((_QWORD *)this + 2) || a3 > 0x10000000 || a3 > *((_DWORD *)this + 2) - *((_DWORD *)this + 6) )
    UserBuffer::ThrowUnexpectedEOFException();
  memcpy_0(a2, (const void *)(*((_QWORD *)this + 2) + *((unsigned int *)this + 6)), a3);
  *((_DWORD *)this + 6) += a3;
}

```

## disassembly

```asm
0x18000b620  mov     [rsp+arg_0], rbx
0x18000b625  push    rdi
0x18000b626  sub     rsp, 20h
0x18000b62a  cmp     qword ptr [rcx+10h], 0
0x18000b62f  mov     r9, rdx
0x18000b632  mov     edi, r8d
0x18000b635  mov     rbx, rcx
0x18000b638  jz      short loc_18000B66C
0x18000b63a  cmp     edi, 10000000h
0x18000b640  ja      short loc_18000B66C
0x18000b642  mov     eax, [rcx+8]
0x18000b645  sub     eax, [rcx+18h]
0x18000b648  cmp     edi, eax
0x18000b64a  ja      short loc_18000B66C
0x18000b64c  mov     edx, [rcx+18h]
0x18000b64f  mov     r8d, edi; Size
0x18000b652  add     rdx, [rcx+10h]; Src
0x18000b656  mov     rcx, r9; void *
0x18000b659  call    memcpy_0
0x18000b65e  add     [rbx+18h], edi
0x18000b661  mov     rbx, [rsp+28h+arg_0]
0x18000b666  add     rsp, 20h
0x18000b66a  pop     rdi
0x18000b66b  retn
0x18000b66c  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
```
