# CWdsMetadataValue::Shutdown(void)

- ea: `0x18000bec0`
- end: `0x18000bef5`
- name: `?Shutdown@CWdsMetadataValue@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(CWdsMetadataValue *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800055b0`
- `0x180009194`
- `0x180009300`
- `0x180009554`
- `0x180009990`
- `0x180009ba8`
- `0x18000b8ec`
- `0x18000b960`
- `0x18000be44`

## callees

- `0x1800015d4`
- `0x18000bec0`

## pseudocode

```c
void __fastcall CWdsMetadataValue::Shutdown(CWdsMetadataValue *this)
{
  void *v2; // rcx

  if ( *(_DWORD *)this == 1 || *(_DWORD *)this == 7 )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
      operator delete(v2);
  }
  *(_DWORD *)this = 0;
  *(_OWORD *)((char *)this + 8) = 0;
}

```

## disassembly

```asm
0x18000bec0  push    rbx
0x18000bec2  sub     rsp, 20h
0x18000bec6  cmp     dword ptr [rcx], 1
0x18000bec9  mov     rbx, rcx
0x18000becc  jz      short loc_18000BED3
0x18000bece  cmp     dword ptr [rcx], 7
0x18000bed1  jnz     short loc_18000BEE1
0x18000bed3  mov     rcx, [rcx+8]; Block
0x18000bed7  test    rcx, rcx
0x18000beda  jz      short loc_18000BEE1
0x18000bedc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bee1  xorps   xmm0, xmm0
0x18000bee4  mov     dword ptr [rbx], 0
0x18000beea  movups  xmmword ptr [rbx+8], xmm0
0x18000beee  add     rsp, 20h
0x18000bef2  pop     rbx
0x18000bef3  retn
```
