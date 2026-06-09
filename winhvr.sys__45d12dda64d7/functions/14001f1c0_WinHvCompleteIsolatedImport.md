# WinHvCompleteIsolatedImport

- ea: `0x14001f1c0`
- end: `0x14001f24f`
- name: `WinHvCompleteIsolatedImport`
- size: `143`
- prototype: `__int64 __fastcall(int, void *Src)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001ef0`
- `0x140009d40`
- `0x14000a040`
- `0x14001f1c0`

## pseudocode

```c
__int64 __fastcall WinHvCompleteIsolatedImport(__int64 a1, void *Src)
{
  __int64 v5; // [rsp+40h] [rbp-D18h] BYREF
  _BYTE v6[3344]; // [rsp+48h] [rbp-D10h] BYREF

  memset(v6, 0, 0xD08u);
  v5 = a1;
  if ( Src )
    memmove(v6, Src, 0xD08u);
  return WinHvpAllocatingHypercall(a1, 0x8000FFFF, 241, 1, &v5, 0xD10u, 0, 0);
}

```

## disassembly

```asm
0x14001f1c0  mov     [rsp+arg_0], rbx
0x14001f1c5  push    rdi
0x14001f1c6  sub     rsp, 0D50h
0x14001f1cd  mov     rbx, rdx
0x14001f1d0  mov     rdi, rcx
0x14001f1d3  xor     edx, edx; Val
0x14001f1d5  lea     rcx, [rsp+0D58h+var_D10]; void *
0x14001f1da  mov     r8d, 0D08h; Size
0x14001f1e0  call    memset
0x14001f1e5  mov     [rsp+0D58h+var_D18], rdi
0x14001f1ea  test    rbx, rbx
0x14001f1ed  jz      short loc_14001F202
0x14001f1ef  lea     rcx, [rsp+0D58h+var_D10]; void *
0x14001f1f4  mov     rdx, rbx; Src
0x14001f1f7  mov     r8d, 0D08h; Size
0x14001f1fd  call    memmove
0x14001f202  mov     [rsp+0D58h+var_D20], 0; size_t
0x14001f20b  lea     rax, [rsp+0D58h+var_D18]
0x14001f210  mov     [rsp+0D58h+var_D28], 0; void *
0x14001f219  mov     r9b, 1; int
0x14001f21c  mov     [rsp+0D58h+Size], 0D10h; Size
0x14001f225  mov     edx, 8000FFFFh; int
0x14001f22a  mov     r8d, 0F1h; int
0x14001f230  mov     [rsp+0D58h+Src], rax; Src
0x14001f235  mov     rcx, rdi; int
0x14001f238  call    WinHvpAllocatingHypercall
0x14001f23d  mov     rbx, [rsp+0D58h+arg_0]
0x14001f245  add     rsp, 0D50h
0x14001f24c  pop     rdi
0x14001f24d  retn
```
