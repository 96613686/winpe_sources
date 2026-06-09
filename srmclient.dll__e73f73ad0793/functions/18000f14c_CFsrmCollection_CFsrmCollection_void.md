# CFsrmCollection::~CFsrmCollection(void)

- ea: `0x18000f14c`
- end: `0x18000f1ea`
- name: `??1CFsrmCollection@@UEAA@XZ`
- size: `158`
- prototype: `void __fastcall(CFsrmCollection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f298`

## callees

- `0x180001350`
- `0x18000f0c0`
- `0x18000f14c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000f199`
- `OLEAUT32!__imp_VariantClear` at `0x18000f199`
- `KERNEL32!DeleteCriticalSection` at `0x18000f170`
- `KERNEL32!DeleteCriticalSection` at `0x18000f1da`
- `KERNEL32!DeleteCriticalSection` at `0x18000f170`
- `KERNEL32!DeleteCriticalSection` at `0x18000f1da`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmCollection::~CFsrmCollection(CFsrmCollection *this)
{
  VARIANTARG *v2; // rdi
  VARIANTARG *v3; // rbp

  *((_QWORD *)this + 5) = &CFsrmCollectionBase::`vftable';
  if ( *((_BYTE *)this + 136) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    *((_BYTE *)this + 136) = 0;
  }
  std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>((char *)this + 64);
  v2 = (VARIANTARG *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = (VARIANTARG *)*((_QWORD *)this + 2);
    while ( v2 != v3 )
      VariantClear(v2++);
    operator delete(*((void **)this + 1));
  }
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  if ( *((_BYTE *)this + 192) )
  {
    *((_BYTE *)this + 192) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  }
}

```

## disassembly

```asm
0x18000f14c  push    rbx
0x18000f14e  push    rbp
0x18000f14f  push    rsi
0x18000f150  push    rdi
0x18000f151  sub     rsp, 28h
0x18000f155  mov     rbx, rcx
0x18000f158  lea     rax, ??_7CFsrmCollectionBase@@6B@; const CFsrmCollectionBase::`vftable'
0x18000f15f  mov     [rcx+28h], rax
0x18000f163  cmp     byte ptr [rcx+88h], 0
0x18000f16a  jz      short loc_18000F17D
0x18000f16c  add     rcx, 60h ; '`'; lpCriticalSection
0x18000f170  call    cs:__imp_DeleteCriticalSection
0x18000f176  mov     byte ptr [rbx+88h], 0
0x18000f17d  lea     rcx, [rbx+40h]
0x18000f181  call    ??1?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>(void)
0x18000f186  nop
0x18000f187  mov     rdi, [rbx+8]
0x18000f18b  test    rdi, rdi
0x18000f18e  jz      short loc_18000F1B1
0x18000f190  mov     rbp, [rbx+10h]
0x18000f194  jmp     short loc_18000F1A3
0x18000f196  mov     rcx, rdi; pvarg
0x18000f199  call    cs:__imp_VariantClear
0x18000f19f  add     rdi, 18h
0x18000f1a3  cmp     rdi, rbp
0x18000f1a6  jnz     short loc_18000F196
0x18000f1a8  mov     rcx, [rbx+8]; Block
0x18000f1ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f1b1  mov     qword ptr [rbx+8], 0
0x18000f1b9  mov     qword ptr [rbx+10h], 0
0x18000f1c1  mov     qword ptr [rbx+18h], 0
0x18000f1c9  lea     rcx, [rbx+98h]; lpCriticalSection
0x18000f1d0  cmp     byte ptr [rcx+28h], 0
0x18000f1d4  jz      short loc_18000F1E1
0x18000f1d6  mov     byte ptr [rcx+28h], 0
0x18000f1da  call    cs:__imp_DeleteCriticalSection
0x18000f1e0  nop
0x18000f1e1  add     rsp, 28h
0x18000f1e5  pop     rdi
0x18000f1e6  pop     rsi
0x18000f1e7  pop     rbp
0x18000f1e8  pop     rbx
0x18000f1e9  retn
```
