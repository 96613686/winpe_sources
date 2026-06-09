# CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(void)

- ea: `0x1800028a8`
- end: `0x180002911`
- name: `?Clear@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAXXZ`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007c28`
- `0x180009490`
- `0x18000af80`

## callees

- `0x180002878`
- `0x1800028a8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800028e8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800028e8`

## pseudocode

```c
void __fastcall CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  CImageCache::Image *v4; // rcx

  if ( *(_DWORD *)(a1 + 12) )
  {
    v2 = *(unsigned int *)(a1 + 12);
    v3 = 0;
    do
    {
      v4 = *(CImageCache::Image **)(v3 + *(_QWORD *)a1);
      if ( v4 )
        CImageCache::Image::`scalar deleting destructor'(v4);
      v3 += 8;
      --v2;
    }
    while ( v2 );
  }
  if ( *(_QWORD *)a1 )
  {
    operator delete[](*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 12) = 0;
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800028a8  mov     [rsp+arg_0], rbx
0x1800028ad  mov     [rsp+arg_8], rsi
0x1800028b2  push    rdi
0x1800028b3  sub     rsp, 20h
0x1800028b7  cmp     dword ptr [rcx+0Ch], 0
0x1800028bb  mov     rbx, rcx
0x1800028be  jbe     short loc_1800028E0
0x1800028c0  mov     esi, [rcx+0Ch]
0x1800028c3  xor     edi, edi
0x1800028c5  mov     rax, [rbx]
0x1800028c8  mov     rcx, [rdi+rax]; this
0x1800028cc  test    rcx, rcx
0x1800028cf  jz      short loc_1800028D6
0x1800028d1  call    ??_GImage@CImageCache@@QEAAPEAXI@Z; CImageCache::Image::`scalar deleting destructor'(uint)
0x1800028d6  add     rdi, 8
0x1800028da  sub     rsi, 1
0x1800028de  jnz     short loc_1800028C5
0x1800028e0  mov     rcx, [rbx]
0x1800028e3  test    rcx, rcx
0x1800028e6  jz      short loc_180002900
0x1800028e8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800028ef  nop     dword ptr [rax+rax+00h]
0x1800028f4  and     qword ptr [rbx], 0
0x1800028f8  and     dword ptr [rbx+0Ch], 0
0x1800028fc  and     dword ptr [rbx+8], 0
0x180002900  mov     rbx, [rsp+28h+arg_0]
0x180002905  mov     rsi, [rsp+28h+arg_8]
0x18000290a  add     rsp, 20h
0x18000290e  pop     rdi
0x18000290f  retn
```
