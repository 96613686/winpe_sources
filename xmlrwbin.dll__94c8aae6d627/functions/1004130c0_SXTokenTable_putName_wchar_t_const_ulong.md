# SXTokenTable::putName(wchar_t const *,ulong)

- ea: `0x1004130c0`
- end: `0x1004131f8`
- name: `?putName@SXTokenTable@@QEAAXPEB_WK@Z`
- size: `312`
- prototype: `void __fastcall(SXTokenTable *this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x100406e70`
- `0x10040ff60`

## callees

- `0x100401350`
- `0x100406550`
- `0x1004130c0`
- `0x100413a50`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041313e`
- `KERNEL32!HeapAlloc` at `0x10041313e`

## pseudocode

```c
void __fastcall SXTokenTable::putName(SXTokenTable *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned __int64 v5; // r14
  unsigned int v7; // edx
  struct IMalloc *v8; // rcx
  char *v9; // rax
  struct CStringPtr *v10; // rdi
  unsigned int v11; // eax
  unsigned int v12; // edx
  __int64 v13; // rdx
  RStringPtr *v14; // rcx

  v3 = *((_DWORD *)this + 9);
  v5 = a3;
  v7 = v3 + 1;
  if ( v3 + 1 < v3 )
    goto LABEL_15;
  if ( v7 > *((_DWORD *)this + 8) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((SXTokenTable *)((char *)this + 16), v7, 8u);
  }
  v8 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v8 || (v8 = g_pMalloc) != 0 )
    v9 = (char *)((__int64 (__fastcall *)(struct IMalloc *, unsigned __int64))v8->lpVtbl->Alloc)(v8, 2 * v5 + 30);
  else
    v9 = (char *)HeapAlloc(g_hHeap, 0, 2 * v5 + 30);
  v10 = (struct CStringPtr *)v9;
  if ( !v9 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x1004131F7LL);
  }
  *((_QWORD *)v9 + 1) = *((_QWORD *)this + 1);
  *(_QWORD *)v9 = &CStringPtr::`vftable';
  *((_DWORD *)v9 + 5) = 0;
  *((_DWORD *)v9 + 4) = v5;
  if ( 2 * v5 < v5 )
  {
    MXRRaiseException(-2147467259);
    __debugbreak();
  }
  memmove(v9 + 24, a2, 2 * v5);
  v11 = *((_DWORD *)this + 9);
  v12 = v11 + 1;
  if ( v11 + 1 < v11 )
  {
LABEL_15:
    MXRRaiseException(-2147352566);
    __debugbreak();
  }
  _mm_lfence();
  if ( v12 > *((_DWORD *)this + 8) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((SXTokenTable *)((char *)this + 16), v12, 8u);
  }
  v13 = *((unsigned int *)this + 9);
  v14 = (RStringPtr *)(*((_QWORD *)this + 5) + 8 * v13);
  *((_DWORD *)this + 9) = v13 + 1;
  RStringPtr::assign(v14, v10);
}

```

## disassembly

```asm
0x1004130c0  mov     [rsp+arg_0], rbx
0x1004130c5  mov     [rsp+arg_8], rbp
0x1004130ca  mov     [rsp+arg_10], rsi
0x1004130cf  push    rdi
0x1004130d0  push    r14
0x1004130d2  push    r15
0x1004130d4  sub     rsp, 20h
0x1004130d8  mov     eax, [rcx+24h]
0x1004130db  mov     r15, rdx
0x1004130de  mov     r14d, r8d
0x1004130e1  mov     rbp, rcx
0x1004130e4  lea     edx, [rax+1]; unsigned int
0x1004130e7  cmp     edx, eax
0x1004130e9  jb      loc_1004131E2
0x1004130ef  cmp     edx, [rcx+20h]
0x1004130f2  jbe     short loc_100413106
0x1004130f4  lfence
0x1004130f7  mov     r8d, 8; unsigned __int64
0x1004130fd  add     rcx, 10h; this
0x100413101  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100413106  mov     rcx, [rbp+8]
0x10041310a  lea     r8, ds:1Eh[r14*2]; dwBytes
0x100413112  test    rcx, rcx
0x100413115  jz      short loc_100413129
0x100413117  mov     rax, [rcx]
0x10041311a  mov     rdx, r8
0x10041311d  mov     rax, [rax+18h]
0x100413121  call    cs:__guard_dispatch_icall_fptr
0x100413127  jmp     short loc_100413144
0x100413129  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100413130  test    rcx, rcx
0x100413133  jnz     short loc_100413117
0x100413135  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041313c  xor     edx, edx; dwFlags
0x10041313e  call    cs:__imp_HeapAlloc
0x100413144  mov     rdi, rax
0x100413147  test    rax, rax
0x10041314a  jz      loc_1004131ED
0x100413150  mov     rax, [rbp+8]
0x100413154  lea     r8, [r14+r14]; Size
0x100413158  mov     [rdi+8], rax
0x10041315c  lea     rax, ??_7CStringPtr@@6B@; const CStringPtr::`vftable'
0x100413163  mov     [rdi], rax
0x100413166  mov     dword ptr [rdi+14h], 0
0x10041316d  mov     [rdi+10h], r14d
0x100413171  cmp     r8, r14
0x100413174  jb      short loc_1004131D7
0x100413176  lea     rcx, [rdi+18h]; void *
0x10041317a  mov     rdx, r15; Src
0x10041317d  call    memmove
0x100413182  mov     eax, [rbp+24h]
0x100413185  lea     edx, [rax+1]; unsigned int
0x100413188  cmp     edx, eax
0x10041318a  jb      short loc_1004131E2
0x10041318c  lfence
0x10041318f  cmp     edx, [rbp+20h]
0x100413192  jbe     short loc_1004131A6
0x100413194  lfence
0x100413197  mov     r8d, 8; unsigned __int64
0x10041319d  lea     rcx, [rbp+10h]; this
0x1004131a1  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x1004131a6  mov     edx, [rbp+24h]
0x1004131a9  mov     rax, [rbp+28h]
0x1004131ad  lea     rcx, [rax+rdx*8]; this
0x1004131b1  lea     eax, [rdx+1]
0x1004131b4  mov     rdx, rdi; struct CStringPtr *
0x1004131b7  mov     [rbp+24h], eax
0x1004131ba  mov     rbx, [rsp+38h+arg_0]
0x1004131bf  mov     rbp, [rsp+38h+arg_8]
0x1004131c4  mov     rsi, [rsp+38h+arg_10]
0x1004131c9  add     rsp, 20h
0x1004131cd  pop     r15
0x1004131cf  pop     r14
0x1004131d1  pop     rdi
0x1004131d2  jmp     ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x1004131d7  mov     ecx, 80004005h; int
0x1004131dc  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004131e1  int     3; Trap to Debugger
0x1004131e2  mov     ecx, 8002000Ah; int
0x1004131e7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004131ec  int     3; Trap to Debugger
0x1004131ed  mov     ecx, 8007000Eh; int
0x1004131f2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
