# CWdsMetadataValue::Shutdown(void)

- ea: `0x18000f9b8`
- end: `0x18000f9f1`
- name: `?Shutdown@CWdsMetadataValue@@QEAAXXZ`
- size: `57`
- prototype: `void __fastcall(CWdsMetadataValue *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800096e8`
- `0x18000d134`
- `0x18000dda0`
- `0x18000e110`
- `0x18000e330`
- `0x18000f92c`

## callees

- `0x18000f9b8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f9d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f9d4`

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
0x18000f9b8  push    rbx
0x18000f9ba  sub     rsp, 20h
0x18000f9be  cmp     dword ptr [rcx], 1
0x18000f9c1  mov     rbx, rcx
0x18000f9c4  jz      short loc_18000F9CB
0x18000f9c6  cmp     dword ptr [rcx], 7
0x18000f9c9  jnz     short loc_18000F9E0
0x18000f9cb  mov     rcx, [rcx+8]
0x18000f9cf  test    rcx, rcx
0x18000f9d2  jz      short loc_18000F9E0
0x18000f9d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f9db  nop     dword ptr [rax+rax+00h]
0x18000f9e0  and     dword ptr [rbx], 0
0x18000f9e3  xorps   xmm0, xmm0
0x18000f9e6  movups  xmmword ptr [rbx+8], xmm0
0x18000f9ea  add     rsp, 20h
0x18000f9ee  pop     rbx
0x18000f9ef  retn
```
