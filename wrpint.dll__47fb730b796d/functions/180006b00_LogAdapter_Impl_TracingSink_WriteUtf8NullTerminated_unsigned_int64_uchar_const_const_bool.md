# LogAdapter::Impl::TracingSink::WriteUtf8NullTerminated(unsigned __int64,uchar const * const,bool)

- ea: `0x180006b00`
- end: `0x180006b4d`
- name: `?WriteUtf8NullTerminated@TracingSink@Impl@LogAdapter@@UEAAX_KQEBE_N@Z`
- size: `77`
- prototype: `void __fastcall(LogAdapter::Impl::TracingSink *this, rsize_t, const unsigned __int8 *const)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006b2f`
- `msvcrt!memcpy_s` at `0x180006b2f`

## pseudocode

```c
void __fastcall LogAdapter::Impl::TracingSink::WriteUtf8NullTerminated(
        LogAdapter::Impl::TracingSink *this,
        rsize_t a2,
        const unsigned __int8 *const a3)
{
  rsize_t v4; // r10
  rsize_t v5; // rbx

  v4 = 4095LL - *((_QWORD *)this + 1);
  v5 = v4;
  if ( a2 < v4 )
    v5 = a2;
  memcpy_s((char *)this + *((_QWORD *)this + 1) + 16, v4, a3, v5);
  *((_QWORD *)this + 1) += v5;
  *((_BYTE *)this + *((_QWORD *)this + 1) + 16) = 0;
}

```

## disassembly

```asm
0x180006b00  mov     [rsp+arg_0], rbx
0x180006b05  push    rdi
0x180006b06  sub     rsp, 20h
0x180006b0a  mov     rdi, rcx
0x180006b0d  mov     r10d, 0FFFh
0x180006b13  sub     r10, [rcx+8]
0x180006b17  cmp     rdx, r10
0x180006b1a  mov     rbx, r10
0x180006b1d  cmovb   rbx, rdx
0x180006b21  add     rcx, 10h
0x180006b25  add     rcx, [rdi+8]; Destination
0x180006b29  mov     r9, rbx; SourceSize
0x180006b2c  mov     rdx, r10; DestinationSize
0x180006b2f  call    cs:__imp_memcpy_s
0x180006b35  add     [rdi+8], rbx
0x180006b39  mov     rax, [rdi+8]
0x180006b3d  mov     rbx, [rsp+28h+arg_0]
0x180006b42  mov     byte ptr [rax+rdi+10h], 0
0x180006b47  add     rsp, 20h
0x180006b4b  pop     rdi
0x180006b4c  retn
```
