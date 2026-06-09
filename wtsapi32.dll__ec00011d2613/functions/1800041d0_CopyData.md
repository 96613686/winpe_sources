# _CopyData

- ea: `0x1800041d0`
- end: `0x18000422b`
- name: `_CopyData`
- size: `91`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d20`
- `0x180005c60`

## callees

- `0x1800041d0`
- `0x180015582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800041ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800041ed`

## pseudocode

```c
__int64 __fastcall CopyData(void *Src, size_t Size, void **a3, _DWORD *a4)
{
  size_t v4; // rdi
  __int64 result; // rax

  v4 = (unsigned int)Size;
  result = (__int64)LocalAlloc(0x40u, (unsigned int)Size);
  *a3 = (void *)result;
  if ( result )
  {
    if ( a4 )
      *a4 = v4;
    memcpy_0(*a3, Src, v4);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800041d0  push    rbx
0x1800041d2  push    rbp
0x1800041d3  push    rsi
0x1800041d4  push    rdi
0x1800041d5  push    r14
0x1800041d7  sub     rsp, 20h
0x1800041db  mov     edi, edx
0x1800041dd  mov     r14, rcx
0x1800041e0  mov     edx, edx; uBytes
0x1800041e2  mov     ecx, 40h ; '@'; uFlags
0x1800041e7  mov     rbx, r9
0x1800041ea  mov     rsi, r8
0x1800041ed  call    cs:__imp_LocalAlloc
0x1800041f3  mov     [rsi], rax
0x1800041f6  test    rax, rax
0x1800041f9  jz      short loc_180004220
0x1800041fb  test    rbx, rbx
0x1800041fe  jz      short loc_180004202
0x180004200  mov     [rbx], edi
0x180004202  mov     rcx, [rsi]; void *
0x180004205  mov     r8, rdi; Size
0x180004208  mov     rdx, r14; Src
0x18000420b  call    memcpy_0
0x180004210  mov     eax, 1
0x180004215  add     rsp, 20h
0x180004219  pop     r14
0x18000421b  pop     rdi
0x18000421c  pop     rsi
0x18000421d  pop     rbp
0x18000421e  pop     rbx
0x18000421f  retn
0x180004220  add     rsp, 20h
0x180004224  pop     r14
0x180004226  pop     rdi
0x180004227  pop     rsi
0x180004228  pop     rbp
0x180004229  pop     rbx
0x18000422a  retn
```
