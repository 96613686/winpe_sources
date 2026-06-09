# EncodingWriter::~EncodingWriter(void)

- ea: `0x100423040`
- end: `0x1004230f7`
- name: `??1EncodingWriter@@UEAA@XZ`
- size: `183`
- prototype: `void __fastcall(EncodingWriter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1004224d0`
- `0x100422cd0`

## callees

- `0x100423040`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10042308c`
- `KERNEL32!HeapFree` at `0x1004230cb`
- `KERNEL32!HeapFree` at `0x10042308c`
- `KERNEL32!HeapFree` at `0x1004230cb`

## pseudocode

```c
void __fastcall EncodingWriter::~EncodingWriter(EncodingWriter *this)
{
  void *v1; // r8
  struct IMalloc *v3; // rcx
  void *v4; // r8
  struct IMalloc *v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx

  v1 = (void *)*((_QWORD *)this + 5);
  *(_QWORD *)this = &EncodingWriter::`vftable';
  if ( v1 )
  {
    v3 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v3 || (v3 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v3->lpVtbl->Free)(v3, v1);
    else
      HeapFree(g_hHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v5->lpVtbl->Free)(v5, *((_QWORD *)this + 8));
    else
      HeapFree(g_hHeap, 0, v4);
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v6 )
    (**v6)(v6, 1);
}

```

## disassembly

```asm
0x100423040  push    rbx
0x100423042  sub     rsp, 20h
0x100423046  mov     r8, [rcx+28h]; lpMem
0x10042304a  lea     rax, ??_7EncodingWriter@@6B@; const EncodingWriter::`vftable'
0x100423051  mov     [rcx], rax
0x100423054  mov     rbx, rcx
0x100423057  test    r8, r8
0x10042305a  jz      short loc_100423092
0x10042305c  mov     rcx, [rcx+8]
0x100423060  test    rcx, rcx
0x100423063  jnz     short loc_100423071
0x100423065  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10042306c  test    rcx, rcx
0x10042306f  jz      short loc_100423083
0x100423071  mov     rax, [rcx]
0x100423074  mov     rdx, r8
0x100423077  mov     rax, [rax+28h]
0x10042307b  call    cs:__guard_dispatch_icall_fptr
0x100423081  jmp     short loc_100423092
0x100423083  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10042308a  xor     edx, edx; dwFlags
0x10042308c  call    cs:__imp_HeapFree
0x100423092  mov     r8, [rbx+40h]; lpMem
0x100423096  test    r8, r8
0x100423099  jz      short loc_1004230D1
0x10042309b  mov     rcx, [rbx+8]
0x10042309f  test    rcx, rcx
0x1004230a2  jnz     short loc_1004230B0
0x1004230a4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004230ab  test    rcx, rcx
0x1004230ae  jz      short loc_1004230C2
0x1004230b0  mov     rax, [rcx]
0x1004230b3  mov     rdx, r8
0x1004230b6  mov     rax, [rax+28h]
0x1004230ba  call    cs:__guard_dispatch_icall_fptr
0x1004230c0  jmp     short loc_1004230D1
0x1004230c2  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004230c9  xor     edx, edx; dwFlags
0x1004230cb  call    cs:__imp_HeapFree
0x1004230d1  mov     rcx, [rbx+10h]
0x1004230d5  test    rcx, rcx
0x1004230d8  jz      short loc_1004230F1
0x1004230da  mov     rax, [rcx]
0x1004230dd  mov     edx, 1
0x1004230e2  mov     rax, [rax]
0x1004230e5  add     rsp, 20h
0x1004230e9  pop     rbx
0x1004230ea  jmp     cs:__guard_dispatch_icall_fptr
0x1004230f1  add     rsp, 20h
0x1004230f5  pop     rbx
0x1004230f6  retn
```
