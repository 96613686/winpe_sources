# CWMFileSinkV1::CreateMMStream(uchar,uchar,int)

- ea: `0x180008c70`
- end: `0x180008cb8`
- name: `?CreateMMStream@CWMFileSinkV1@@MEAAPEAVCASFMMStream@@EEH@Z`
- size: `72`
- prototype: `struct CASFMMStream *(CWMFileSinkV1 *__hidden this, unsigned __int8, unsigned __int8, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011a0`
- `0x180008c70`
- `0x1800119f4`

## pseudocode

```c
struct CASFMMStream *__fastcall CWMFileSinkV1::CreateMMStream(
        CWMFileSinkV1 *this,
        unsigned __int8 a2,
        unsigned __int8 a3,
        int a4)
{
  struct CASFMMStream *result; // rax

  result = (struct CASFMMStream *)operator new(0x558u);
  if ( result )
    return CASFMMStream::CASFMMStream(result, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180008c70  mov     [rsp+arg_0], rbx
0x180008c75  mov     [rsp+arg_8], rsi
0x180008c7a  push    rdi
0x180008c7b  sub     rsp, 20h
0x180008c7f  mov     ecx, 558h; Size
0x180008c84  mov     ebx, r9d
0x180008c87  mov     dil, r8b
0x180008c8a  mov     sil, dl
0x180008c8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c92  test    rax, rax
0x180008c95  jz      short loc_180008CA8
0x180008c97  mov     r9d, ebx; int
0x180008c9a  mov     r8b, dil; unsigned __int8
0x180008c9d  mov     dl, sil; unsigned __int8
0x180008ca0  mov     rcx, rax; this
0x180008ca3  call    ??0CASFMMStream@@QEAA@EEH@Z; CASFMMStream::CASFMMStream(uchar,uchar,int)
0x180008ca8  mov     rbx, [rsp+28h+arg_0]
0x180008cad  mov     rsi, [rsp+28h+arg_8]
0x180008cb2  add     rsp, 20h
0x180008cb6  pop     rdi
0x180008cb7  retn
```
