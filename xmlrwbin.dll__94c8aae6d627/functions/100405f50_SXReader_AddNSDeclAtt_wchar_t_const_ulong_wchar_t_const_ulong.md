# SXReader::AddNSDeclAtt(wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x100405f50`
- end: `0x100406147`
- name: `?AddNSDeclAtt@SXReader@@AEAAXPEB_WK0K@Z`
- size: `503`
- prototype: `void(SXReader *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1004059a0`

## callees

- `0x100401350`
- `0x100405f50`
- `0x100406550`
- `0x100413a50`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004060b7`
- `KERNEL32!HeapAlloc` at `0x1004060b7`

## pseudocode

```c
void __fastcall SXReader::AddNSDeclAtt(SXReader *this, const wchar_t *a2, int a3, const wchar_t *a4, unsigned int a5)
{
  __int64 v5; // rbp
  unsigned int v10; // eax
  unsigned int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ebx
  struct IMalloc *v18; // rcx
  SIZE_T v19; // r8
  void *v20; // rax
  bool v21; // zf
  void *v22; // rdi
  __int64 v23; // rax
  unsigned int v24; // edx
  __int64 v25; // rcx

  v5 = *((_QWORD *)this + 188);
  v10 = *(_DWORD *)(v5 + 84);
  v11 = v10 + 1;
  if ( v10 + 1 < v10 )
    goto LABEL_24;
  if ( v11 > *(_DWORD *)(v5 + 80) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)(v5 + 64), v11, 0x90u);
    v10 = *(_DWORD *)(v5 + 84);
  }
  v12 = v10;
  v13 = *(_QWORD *)(v5 + 72);
  v14 = *(_QWORD *)(v5 + 88) + 144 * v12;
  if ( v14 )
  {
    *(_QWORD *)(v14 + 8) = v13;
    *(_QWORD *)v14 = &AttributeBase::`vftable';
    *(_QWORD *)(v14 + 32) = v13;
    *(_QWORD *)(v14 + 24) = &_xarray<AttributeValue,_xarray_item<AttributeValue>>::`vftable';
    *(_QWORD *)(v14 + 40) = 0;
    *(_QWORD *)(v14 + 48) = 0;
    *(_QWORD *)(v14 + 96) = 0;
    *(_QWORD *)(v14 + 104) = 0;
    *(_QWORD *)(v14 + 112) = 0;
    *(_QWORD *)(v14 + 80) = 0;
    *(_QWORD *)(v14 + 64) = 0;
    RStringPtr::assign((RStringPtr *)(v14 + 96), 0);
    RStringPtr::assign((RStringPtr *)(v14 + 104), 0);
    RStringPtr::assign((RStringPtr *)(v14 + 112), 0);
    *(_QWORD *)v14 = &AttributeNS::`vftable';
    LODWORD(v12) = *(_DWORD *)(v5 + 84);
  }
  *(_DWORD *)(v5 + 84) = v12 + 1;
  *(_DWORD *)(v14 + 120) = 0;
  *(_QWORD *)(v14 + 128) = a2;
  *(_DWORD *)(v14 + 136) = a3;
  v15 = *(_DWORD *)(v14 + 44);
  v16 = v15 + 1;
  if ( v15 + 1 < v15 )
  {
LABEL_24:
    MXRRaiseException(-2147352566);
    JUMPOUT(0x100406146LL);
  }
  if ( v16 > *(_DWORD *)(v14 + 40) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)(v14 + 24), v16, 0x10u);
  }
  v17 = 2 * a5;
  if ( 2 * a5 < a5 )
  {
LABEL_23:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  v18 = (struct IMalloc *)*((_QWORD *)this + 1);
  v19 = 8;
  if ( v17 )
    v19 = v17;
  if ( v18 )
  {
    _mm_lfence();
LABEL_14:
    v20 = (void *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v18->lpVtbl->Alloc)(v18, v19);
    goto LABEL_18;
  }
  v21 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v21 )
  {
    v18 = g_pMalloc;
    goto LABEL_14;
  }
  v20 = HeapAlloc(g_hHeap, 0, v19);
LABEL_18:
  v22 = v20;
  if ( !v20 )
    goto LABEL_23;
  memmove(v20, a4, v17);
  v23 = *(unsigned int *)(v14 + 44);
  v24 = v23 + 1;
  if ( (int)v23 + 1 < (unsigned int)v23 )
    goto LABEL_24;
  if ( v24 > *(_DWORD *)(v14 + 40) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)(v14 + 24), v24, 0x10u);
    v23 = *(unsigned int *)(v14 + 44);
  }
  v25 = *(_QWORD *)(v14 + 48) + 16 * v23;
  *(_DWORD *)(v14 + 44) = v23 + 1;
  *(_DWORD *)(v25 + 8) = v17;
  *(_DWORD *)(v25 + 12) = 17;
  *(_QWORD *)v25 = v22;
}

```

## disassembly

```asm
0x100405f50  mov     [rsp+arg_0], rbx
0x100405f55  mov     [rsp+arg_8], rbp
0x100405f5a  mov     [rsp+arg_10], rsi
0x100405f5f  push    rdi
0x100405f60  push    r12
0x100405f62  push    r13
0x100405f64  push    r14
0x100405f66  push    r15
0x100405f68  sub     rsp, 20h
0x100405f6c  mov     rbp, [rcx+5E0h]
0x100405f73  mov     r12, rdx
0x100405f76  mov     r13, r9
0x100405f79  mov     r15d, r8d
0x100405f7c  mov     r14, rcx
0x100405f7f  mov     eax, [rbp+54h]
0x100405f82  lea     edx, [rax+1]; unsigned int
0x100405f85  cmp     edx, eax
0x100405f87  jb      loc_10040613C
0x100405f8d  cmp     edx, [rbp+50h]
0x100405f90  jbe     short loc_100405FA7
0x100405f92  lfence
0x100405f95  mov     r8d, 90h; unsigned __int64
0x100405f9b  lea     rcx, [rbp+40h]; this
0x100405f9f  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100405fa4  mov     eax, [rbp+54h]
0x100405fa7  mov     ecx, eax
0x100405fa9  xor     edx, edx; struct CStringPtr *
0x100405fab  mov     rax, [rbp+48h]
0x100405faf  lea     rsi, [rcx+rcx*8]
0x100405fb3  shl     rsi, 4
0x100405fb7  add     rsi, [rbp+58h]
0x100405fbb  jz      short loc_100406023
0x100405fbd  lea     rcx, ??_7AttributeBase@@6B@; const AttributeBase::`vftable'
0x100405fc4  mov     [rsi+8], rax
0x100405fc8  mov     [rsi], rcx
0x100405fcb  lea     rcx, [rsi+60h]; this
0x100405fcf  mov     [rsi+20h], rax
0x100405fd3  lea     rax, ??_7?$_xarray@UAttributeValue@@V?$_xarray_item@UAttributeValue@@@@@@6B@; const _xarray<AttributeValue,_xarray_item<AttributeValue>>::`vftable'
0x100405fda  mov     [rsi+18h], rax
0x100405fde  mov     [rsi+28h], rdx
0x100405fe2  mov     [rsi+30h], rdx
0x100405fe6  mov     [rcx], rdx
0x100405fe9  mov     [rsi+68h], rdx
0x100405fed  mov     [rsi+70h], rdx
0x100405ff1  mov     [rsi+50h], rdx
0x100405ff5  mov     [rsi+40h], rdx
0x100405ff9  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405ffe  xor     edx, edx; struct CStringPtr *
0x100406000  lea     rcx, [rsi+68h]; this
0x100406004  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100406009  xor     edx, edx; struct CStringPtr *
0x10040600b  lea     rcx, [rsi+70h]; this
0x10040600f  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100406014  lea     rax, ??_7AttributeNS@@6B@; const AttributeNS::`vftable'
0x10040601b  xor     edx, edx
0x10040601d  mov     [rsi], rax
0x100406020  mov     ecx, [rbp+54h]
0x100406023  lea     eax, [rcx+1]
0x100406026  mov     [rbp+54h], eax
0x100406029  mov     [rsi+78h], edx
0x10040602c  mov     [rsi+80h], r12
0x100406033  mov     [rsi+88h], r15d
0x10040603a  mov     eax, [rsi+2Ch]
0x10040603d  lea     edx, [rax+1]; unsigned int
0x100406040  cmp     edx, eax
0x100406042  jb      loc_10040613C
0x100406048  cmp     edx, [rsi+28h]
0x10040604b  jbe     short loc_10040605F
0x10040604d  lfence
0x100406050  mov     r8d, 10h; unsigned __int64
0x100406056  lea     rcx, [rsi+18h]; this
0x10040605a  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x10040605f  mov     eax, [rsp+48h+arg_20]
0x100406063  lea     ebx, [rax+rax]
0x100406066  cmp     ebx, eax
0x100406068  jb      loc_100406131
0x10040606e  mov     rcx, [r14+8]
0x100406072  test    ebx, ebx
0x100406074  mov     r8d, 8
0x10040607a  cmovnz  r8d, ebx; dwBytes
0x10040607e  test    rcx, rcx
0x100406081  jz      short loc_100406098
0x100406083  lfence
0x100406086  mov     rax, [rcx]
0x100406089  mov     rdx, r8
0x10040608c  mov     rax, [rax+18h]
0x100406090  call    cs:__guard_dispatch_icall_fptr
0x100406096  jmp     short loc_1004060BD
0x100406098  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x1004060a0  lfence
0x1004060a3  jz      short loc_1004060AE
0x1004060a5  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004060ac  jmp     short loc_100406086
0x1004060ae  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004060b5  xor     edx, edx; dwFlags
0x1004060b7  call    cs:__imp_HeapAlloc
0x1004060bd  mov     rdi, rax
0x1004060c0  test    rax, rax
0x1004060c3  jz      short loc_100406131
0x1004060c5  mov     r8d, ebx; Size
0x1004060c8  mov     rdx, r13; Src
0x1004060cb  mov     rcx, rax; void *
0x1004060ce  call    memmove
0x1004060d3  mov     eax, [rsi+2Ch]
0x1004060d6  lea     edx, [rax+1]; unsigned int
0x1004060d9  cmp     edx, eax
0x1004060db  jb      short loc_10040613C
0x1004060dd  cmp     edx, [rsi+28h]
0x1004060e0  jbe     short loc_1004060F7
0x1004060e2  lfence
0x1004060e5  mov     r8d, 10h; unsigned __int64
0x1004060eb  lea     rcx, [rsi+18h]; this
0x1004060ef  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x1004060f4  mov     eax, [rsi+2Ch]
0x1004060f7  mov     rbp, [rsp+48h+arg_8]
0x1004060fc  mov     rcx, rax
0x1004060ff  shl     rcx, 4
0x100406103  add     rcx, [rsi+30h]
0x100406107  inc     eax
0x100406109  mov     [rsi+2Ch], eax
0x10040610c  mov     rsi, [rsp+48h+arg_10]
0x100406111  mov     [rcx+8], ebx
0x100406114  mov     rbx, [rsp+48h+arg_0]
0x100406119  mov     dword ptr [rcx+0Ch], 11h
0x100406120  mov     [rcx], rdi
0x100406123  add     rsp, 20h
0x100406127  pop     r15
0x100406129  pop     r14
0x10040612b  pop     r13
0x10040612d  pop     r12
0x10040612f  pop     rdi
0x100406130  retn
0x100406131  mov     ecx, 8007000Eh; int
0x100406136  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040613b  int     3; Trap to Debugger
0x10040613c  mov     ecx, 8002000Ah; int
0x100406141  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
