# SXTokenTable::Initialize(void)

- ea: `0x100406e70`
- end: `0x100407042`
- name: `?Initialize@SXTokenTable@@QEAAXXZ`
- size: `466`
- prototype: `void __fastcall(SXTokenTable *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100407050`

## callees

- `0x100401350`
- `0x100406550`
- `0x100406e70`
- `0x1004130c0`
- `0x100413a50`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100406ec6`
- `KERNEL32!HeapAlloc` at `0x100406f45`
- `KERNEL32!HeapAlloc` at `0x100406ec6`
- `KERNEL32!HeapAlloc` at `0x100406f45`

## pseudocode

```c
void __fastcall SXTokenTable::Initialize(SXTokenTable *this)
{
  struct IMalloc *v2; // rcx
  SIZE_T v3; // r8
  void *v4; // rax
  struct IMalloc *v5; // rcx
  SIZE_T v6; // r8
  void *v7; // rax
  size_t v8; // r8
  unsigned int v9; // eax
  unsigned int v10; // edx
  _DWORD *v11; // rbx

  v2 = (struct IMalloc *)*((_QWORD *)this + 7);
  v3 = 24LL * *((unsigned int *)this + 19);
  if ( !is_mul_ok(*((unsigned int *)this + 19), 0x18u) )
    v3 = -1;
  if ( v2 || (v2 = g_pMalloc) != 0 )
    v4 = (void *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v2->lpVtbl->Alloc)(v2, v3);
  else
    v4 = HeapAlloc(g_hHeap, 0, v3);
  if ( !v4 )
    goto LABEL_19;
  *((_QWORD *)this + 8) = v4;
  memset(v4, -1, 24LL * *((unsigned int *)this + 19));
  *((_DWORD *)this + 20) = 2 * (*((_DWORD *)this + 19) / 3u);
  v5 = (struct IMalloc *)*((_QWORD *)this + 17);
  v6 = 56LL * *((unsigned int *)this + 39);
  if ( !is_mul_ok(*((unsigned int *)this + 39), 0x38u) )
    v6 = -1;
  if ( v5 || (v5 = g_pMalloc) != 0 )
    v7 = (void *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v5->lpVtbl->Alloc)(v5, v6);
  else
    v7 = HeapAlloc(g_hHeap, 0, v6);
  if ( !v7 )
  {
LABEL_19:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  v8 = 56LL * *((unsigned int *)this + 39);
  *((_QWORD *)this + 18) = v7;
  memset(v7, -1, v8);
  *((_DWORD *)this + 40) = 2 * (*((_DWORD *)this + 39) / 3u);
  SXTokenTable::putName(this, 0, 0);
  v9 = *((_DWORD *)this + 29);
  v10 = v9 + 1;
  if ( v9 + 1 < v9 )
  {
    MXRRaiseException(-2147352566);
    JUMPOUT(0x100407041LL);
  }
  if ( v10 > *((_DWORD *)this + 28) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((SXTokenTable *)((char *)this + 96), v10, 0x28u);
    v9 = *((_DWORD *)this + 29);
  }
  v11 = (_DWORD *)(*((_QWORD *)this + 15) + 40LL * v9);
  *((_DWORD *)this + 29) = v9 + 1;
  RStringPtr::assign((RStringPtr *)v11, *((struct CStringPtr **)this + 22));
  RStringPtr::assign((RStringPtr *)(v11 + 2), *((struct CStringPtr **)this + 23));
  RStringPtr::assign((RStringPtr *)(v11 + 4), *((struct CStringPtr **)this + 24));
  v11[6] = *((_DWORD *)this + 50);
  v11[7] = *((_DWORD *)this + 51);
  v11[8] = *((_DWORD *)this + 52);
}

```

## disassembly

```asm
0x100406e70  mov     [rsp+arg_8], rbx
0x100406e75  push    rdi
0x100406e76  sub     rsp, 20h
0x100406e7a  mov     rdi, rcx
0x100406e7d  mov     eax, 18h
0x100406e82  mov     rcx, [rcx+38h]
0x100406e86  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100406e8d  mov     edx, [rdi+4Ch]
0x100406e90  mul     rdx
0x100406e93  mov     r8, rax
0x100406e96  cmovo   r8, rbx; dwBytes
0x100406e9a  test    rcx, rcx
0x100406e9d  jz      short loc_100406EB1
0x100406e9f  mov     rax, [rcx]
0x100406ea2  mov     rdx, r8
0x100406ea5  mov     rax, [rax+18h]
0x100406ea9  call    cs:__guard_dispatch_icall_fptr
0x100406eaf  jmp     short loc_100406ECC
0x100406eb1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100406eb8  test    rcx, rcx
0x100406ebb  jnz     short loc_100406E9F
0x100406ebd  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100406ec4  xor     edx, edx; dwFlags
0x100406ec6  call    cs:__imp_HeapAlloc
0x100406ecc  mov     rcx, rax; void *
0x100406ecf  test    rax, rax
0x100406ed2  jz      loc_10040702C
0x100406ed8  mov     [rdi+40h], rax
0x100406edc  mov     edx, ebx; Val
0x100406ede  mov     eax, [rdi+4Ch]
0x100406ee1  lea     r8, [rax+rax*2]
0x100406ee5  shl     r8, 3; Size
0x100406ee9  call    memset
0x100406eee  mov     eax, 0AAAAAAABh
0x100406ef3  mul     dword ptr [rdi+4Ch]
0x100406ef6  mov     eax, 38h ; '8'
0x100406efb  shr     edx, 1
0x100406efd  add     edx, edx
0x100406eff  mov     [rdi+50h], edx
0x100406f02  mov     edx, [rdi+9Ch]
0x100406f08  mov     rcx, [rdi+88h]
0x100406f0f  mul     rdx
0x100406f12  mov     r8, rax
0x100406f15  cmovo   r8, rbx; dwBytes
0x100406f19  test    rcx, rcx
0x100406f1c  jnz     short loc_100406F2A
0x100406f1e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100406f25  test    rcx, rcx
0x100406f28  jz      short loc_100406F3C
0x100406f2a  mov     rax, [rcx]
0x100406f2d  mov     rdx, r8
0x100406f30  mov     rax, [rax+18h]
0x100406f34  call    cs:__guard_dispatch_icall_fptr
0x100406f3a  jmp     short loc_100406F4B
0x100406f3c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100406f43  xor     edx, edx; dwFlags
0x100406f45  call    cs:__imp_HeapAlloc
0x100406f4b  test    rax, rax
0x100406f4e  jz      loc_10040702C
0x100406f54  mov     ecx, [rdi+9Ch]
0x100406f5a  mov     edx, ebx; Val
0x100406f5c  imul    r8, rcx, 38h ; '8'; Size
0x100406f60  mov     rcx, rax; void *
0x100406f63  mov     [rsp+28h+arg_0], rsi
0x100406f68  mov     [rdi+90h], rax
0x100406f6f  call    memset
0x100406f74  mov     eax, 0AAAAAAABh
0x100406f79  xor     r8d, r8d; unsigned int
0x100406f7c  mul     dword ptr [rdi+9Ch]
0x100406f82  mov     rcx, rdi; this
0x100406f85  shr     edx, 1
0x100406f87  add     edx, edx
0x100406f89  mov     [rdi+0A0h], edx
0x100406f8f  xor     edx, edx; wchar_t *
0x100406f91  call    ?putName@SXTokenTable@@QEAAXPEB_WK@Z; SXTokenTable::putName(wchar_t const *,ulong)
0x100406f96  mov     eax, [rdi+74h]
0x100406f99  lea     edx, [rax+1]; unsigned int
0x100406f9c  cmp     edx, eax
0x100406f9e  jb      loc_100407037
0x100406fa4  cmp     edx, [rdi+70h]
0x100406fa7  jbe     short loc_100406FBE
0x100406fa9  lfence
0x100406fac  mov     r8d, 28h ; '('; unsigned __int64
0x100406fb2  lea     rcx, [rdi+60h]; this
0x100406fb6  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100406fbb  mov     eax, [rdi+74h]
0x100406fbe  mov     edx, eax
0x100406fc0  mov     rax, [rdi+78h]
0x100406fc4  lea     rcx, [rdx+rdx*4]
0x100406fc8  lea     rbx, [rax+rcx*8]
0x100406fcc  lea     eax, [rdx+1]
0x100406fcf  mov     rcx, rbx; this
0x100406fd2  mov     [rdi+74h], eax
0x100406fd5  mov     rdx, [rdi+0B0h]; struct CStringPtr *
0x100406fdc  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100406fe1  mov     rdx, [rdi+0B8h]; struct CStringPtr *
0x100406fe8  lea     rcx, [rbx+8]; this
0x100406fec  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100406ff1  mov     rdx, [rdi+0C0h]; struct CStringPtr *
0x100406ff8  lea     rcx, [rbx+10h]; this
0x100406ffc  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100407001  mov     eax, [rdi+0C8h]
0x100407007  mov     rsi, [rsp+28h+arg_0]
0x10040700c  mov     [rbx+18h], eax
0x10040700f  mov     eax, [rdi+0CCh]
0x100407015  mov     [rbx+1Ch], eax
0x100407018  mov     eax, [rdi+0D0h]
0x10040701e  mov     [rbx+20h], eax
0x100407021  mov     rbx, [rsp+28h+arg_8]
0x100407026  add     rsp, 20h
0x10040702a  pop     rdi
0x10040702b  retn
0x10040702c  mov     ecx, 8007000Eh; int
0x100407031  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100407036  int     3; Trap to Debugger
0x100407037  mov     ecx, 8002000Ah; int
0x10040703c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
