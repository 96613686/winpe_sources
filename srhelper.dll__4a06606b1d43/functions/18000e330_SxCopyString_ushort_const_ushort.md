# SxCopyString(ushort const *,ushort * *)

- ea: `0x18000e330`
- end: `0x18000e3b2`
- name: `?SxCopyString@@YAJPEBGPEAPEAG@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800044ac`
- `0x18000572c`
- `0x18000c100`

## callees

- `0x18000e330`
- `0x1800157b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000e36d`
- `ole32!CoTaskMemAlloc` at `0x18000e36d`
- `ole32!CoTaskMemFree` at `0x18000e39f`
- `ole32!CoTaskMemFree` at `0x18000e39f`

## pseudocode

```c
__int64 __fastcall SxCopyString(const unsigned __int16 *Src, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  __int64 v5; // rax
  SIZE_T v6; // rbp
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx

  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_10;
  }
  *a2 = 0;
  v4 = 0;
  if ( !Src )
    goto LABEL_8;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  v6 = 2 * v5 + 2;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
  v4 = v7;
  if ( v7 )
  {
    memcpy_0(v7, Src, v6);
LABEL_8:
    v8 = 0;
    *a2 = v4;
    goto LABEL_10;
  }
  v8 = -2147024882;
LABEL_10:
  CoTaskMemFree(0);
  return v8;
}

```

## disassembly

```asm
0x18000e330  push    rbx
0x18000e332  push    rbp
0x18000e333  push    rsi
0x18000e334  push    rdi
0x18000e335  push    r14
0x18000e337  sub     rsp, 20h
0x18000e33b  xor     r14d, r14d
0x18000e33e  mov     rsi, rdx
0x18000e341  mov     rbx, rcx
0x18000e344  test    rdx, rdx
0x18000e347  jz      short loc_18000E398
0x18000e349  mov     [rdx], r14
0x18000e34c  mov     edi, r14d
0x18000e34f  test    rcx, rcx
0x18000e352  jz      short loc_18000E390
0x18000e354  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e358  inc     rax
0x18000e35b  cmp     [rcx+rax*2], r14w
0x18000e360  jnz     short loc_18000E358
0x18000e362  lea     rbp, ds:2[rax*2]
0x18000e36a  mov     rcx, rbp; cb
0x18000e36d  call    cs:__imp_CoTaskMemAlloc
0x18000e373  mov     rdi, rax
0x18000e376  test    rax, rax
0x18000e379  jnz     short loc_18000E382
0x18000e37b  mov     ebx, 8007000Eh
0x18000e380  jmp     short loc_18000E39D
0x18000e382  mov     r8, rbp; Size
0x18000e385  mov     rdx, rbx; Src
0x18000e388  mov     rcx, rax; void *
0x18000e38b  call    memcpy_0
0x18000e390  mov     ebx, r14d
0x18000e393  mov     [rsi], rdi
0x18000e396  jmp     short loc_18000E39D
0x18000e398  mov     ebx, 80070057h
0x18000e39d  xor     ecx, ecx; pv
0x18000e39f  call    cs:__imp_CoTaskMemFree
0x18000e3a5  mov     eax, ebx
0x18000e3a7  add     rsp, 20h
0x18000e3ab  pop     r14
0x18000e3ad  pop     rdi
0x18000e3ae  pop     rsi
0x18000e3af  pop     rbp
0x18000e3b0  pop     rbx
0x18000e3b1  retn
```
