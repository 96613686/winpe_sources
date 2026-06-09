# utl::default_delete<BinXmlExtractor>::operator()(BinXmlExtractor *)

- ea: `0x18001a4ac`
- end: `0x18001a4d4`
- name: `??R?$default_delete@VBinXmlExtractor@@@utl@@QEBAXPEAVBinXmlExtractor@@@Z`
- size: `40`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180008bb8`
- `0x18001a0d8`
- `0x18001a3e4`
- `0x18001a490`

## callees

- `0x18000a0d0`
- `0x18001a4ac`
- `0x18001a4dc`

## pseudocode

```c
void __fastcall utl::default_delete<BinXmlExtractor>::operator()(__int64 a1, BinXmlExtractor *a2)
{
  if ( a2 )
  {
    BinXmlExtractor::~BinXmlExtractor(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18001a4ac  test    rdx, rdx
0x18001a4af  jz      short locret_18001A4D3
0x18001a4b1  push    rbx
0x18001a4b2  sub     rsp, 20h
0x18001a4b6  mov     rcx, rdx; this
0x18001a4b9  mov     rbx, rdx
0x18001a4bc  call    ??1BinXmlExtractor@@QEAA@XZ; BinXmlExtractor::~BinXmlExtractor(void)
0x18001a4c1  mov     edx, 90h; unsigned __int64
0x18001a4c6  mov     rcx, rbx; void *
0x18001a4c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a4ce  add     rsp, 20h
0x18001a4d2  pop     rbx
0x18001a4d3  retn
```
