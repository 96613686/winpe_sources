# SXReadBase::~SXReadBase(void)

- ea: `0x10040e630`
- end: `0x10040eb42`
- name: `??1SXReadBase@@MEAA@XZ`
- size: `1298`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1004043c0`
- `0x10040e590`

## callees

- `0x100406550`
- `0x10040e630`
- `0x10040eb50`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040e6c2`
- `KERNEL32!HeapFree` at `0x10040e70a`
- `KERNEL32!HeapFree` at `0x10040e7d8`
- `KERNEL32!HeapFree` at `0x10040e824`
- `KERNEL32!HeapFree` at `0x10040e89a`
- `KERNEL32!HeapFree` at `0x10040e8e8`
- `KERNEL32!HeapFree` at `0x10040e936`
- `KERNEL32!HeapFree` at `0x10040e984`
- `KERNEL32!HeapFree` at `0x10040e9d2`
- `KERNEL32!HeapFree` at `0x10040ea20`
- `KERNEL32!HeapFree` at `0x10040ea6e`
- `KERNEL32!HeapFree` at `0x10040eacd`
- `KERNEL32!HeapFree` at `0x10040eb23`
- `KERNEL32!HeapFree` at `0x10040e6c2`
- `KERNEL32!HeapFree` at `0x10040e70a`
- `KERNEL32!HeapFree` at `0x10040e7d8`
- `KERNEL32!HeapFree` at `0x10040e824`
- `KERNEL32!HeapFree` at `0x10040e89a`
- `KERNEL32!HeapFree` at `0x10040e8e8`
- `KERNEL32!HeapFree` at `0x10040e936`
- `KERNEL32!HeapFree` at `0x10040e984`
- `KERNEL32!HeapFree` at `0x10040e9d2`
- `KERNEL32!HeapFree` at `0x10040ea20`
- `KERNEL32!HeapFree` at `0x10040ea6e`
- `KERNEL32!HeapFree` at `0x10040eacd`
- `KERNEL32!HeapFree` at `0x10040eb23`

## pseudocode

```c
void __fastcall SXReadBase::~SXReadBase(SXReadBase *this)
{
  int v2; // eax
  LPVOID *v3; // r9
  struct IMalloc *v4; // rcx
  bool v5; // zf
  void *v6; // r8
  struct IMalloc *v7; // rcx
  __int64 v8; // rbx
  LPVOID *v9; // rbx
  __int64 v10; // rsi
  struct IMalloc *v11; // rcx
  void *v12; // r8
  struct IMalloc *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  struct IMalloc *v16; // rcx
  __int64 v17; // r8
  struct IMalloc *v18; // rcx
  __int64 v19; // r8
  struct IMalloc *v20; // rcx
  __int64 v21; // r8
  struct IMalloc *v22; // rcx
  __int64 v23; // r8
  struct IMalloc *v24; // rcx
  __int64 v25; // r8
  struct IMalloc *v26; // rcx
  __int64 v27; // r8
  struct IMalloc *v28; // rcx
  char *v29; // r8
  struct IMalloc *v30; // rcx
  char *v31; // r8
  struct IMalloc *v32; // rcx

  *(_QWORD *)this = &SXReadBase::`vftable';
  v2 = *((_DWORD *)this + 30);
  if ( v2 )
  {
    do
    {
      v3 = (LPVOID *)(*((_QWORD *)this + 14) + 48LL * (unsigned int)(v2 - 1));
      if ( *((int *)v3 + 7) < -1 )
        break;
      *(_DWORD *)(*((_QWORD *)this + 11) + 4LL * (unsigned int)(*((_DWORD *)v3 + 9) % *((_DWORD *)this + 21))) = *((_DWORD *)v3 + 10);
      if ( *v3 )
      {
        v4 = (struct IMalloc *)*((_QWORD *)this + 1);
        if ( v4 || (v4 = g_pMalloc) != 0 )
          ((void (__fastcall *)(struct IMalloc *, LPVOID))v4->lpVtbl->Free)(v4, *v3);
        else
          HeapFree(g_hHeap, 0, *v3);
      }
      v5 = (*((_DWORD *)this + 30))-- == 1;
      v2 = *((_DWORD *)this + 30);
    }
    while ( !v5 );
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    v7 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v7 || (v7 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v7->lpVtbl->Free)(v7, *((_QWORD *)this + 11));
    else
      HeapFree(g_hHeap, 0, v6);
  }
  RStringPtr::assign((SXReadBase *)((char *)this + 1184), 0);
  RStringPtr::assign((SXReadBase *)((char *)this + 1176), 0);
  RStringPtr::assign((SXReadBase *)((char *)this + 1192), 0);
  while ( *((_DWORD *)this + 188) )
  {
    v8 = *((_QWORD *)this + 93) + 32LL * (unsigned int)--*((_DWORD *)this + 188);
    RStringPtr::assign((RStringPtr *)(v8 + 8), 0);
    RStringPtr::assign((RStringPtr *)v8, 0);
    RStringPtr::assign((RStringPtr *)(v8 + 16), 0);
  }
  v9 = (LPVOID *)((char *)this + 24);
  v10 = 4;
  do
  {
    if ( *v9 )
    {
      v11 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v11 || (v11 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, LPVOID))v11->lpVtbl->Free)(v11, *v9);
      else
        HeapFree(g_hHeap, 0, *v9);
    }
    v9 += 2;
    --v10;
  }
  while ( v10 );
  v12 = (void *)*((_QWORD *)this + 177);
  if ( v12 )
  {
    v13 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v13 || (v13 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v13->lpVtbl->Free)(v13, *((_QWORD *)this + 177));
    else
      HeapFree(g_hHeap, 0, v12);
  }
  v14 = *((_QWORD *)this + 180);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  SXReadBase::Clear(this);
  v15 = *((_QWORD *)this + 159);
  if ( v15 )
  {
    v5 = (*(_DWORD *)(v15 + 20))-- == 1;
    if ( v5 && (void ***)v15 != &cspNull )
    {
      v16 = *(struct IMalloc **)(v15 + 8);
      if ( v16 || (v16 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v16->lpVtbl->Free)(v16, v15);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v15);
    }
  }
  v17 = *((_QWORD *)this + 155);
  if ( v17 )
  {
    v5 = (*(_DWORD *)(v17 + 20))-- == 1;
    if ( v5 && (void ***)v17 != &cspNull )
    {
      v18 = *(struct IMalloc **)(v17 + 8);
      if ( v18 || (v18 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v18->lpVtbl->Free)(v18, v17);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v17);
    }
  }
  v19 = *((_QWORD *)this + 154);
  if ( v19 )
  {
    v5 = (*(_DWORD *)(v19 + 20))-- == 1;
    if ( v5 && (void ***)v19 != &cspNull )
    {
      v20 = *(struct IMalloc **)(v19 + 8);
      if ( v20 || (v20 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v20->lpVtbl->Free)(v20, v19);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v19);
    }
  }
  v21 = *((_QWORD *)this + 153);
  if ( v21 )
  {
    v5 = (*(_DWORD *)(v21 + 20))-- == 1;
    if ( v5 && (void ***)v21 != &cspNull )
    {
      v22 = *(struct IMalloc **)(v21 + 8);
      if ( v22 || (v22 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v22->lpVtbl->Free)(v22, v21);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v21);
    }
  }
  v23 = *((_QWORD *)this + 149);
  if ( v23 )
  {
    v5 = (*(_DWORD *)(v23 + 20))-- == 1;
    if ( v5 && (void ***)v23 != &cspNull )
    {
      v24 = *(struct IMalloc **)(v23 + 8);
      if ( v24 || (v24 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v24->lpVtbl->Free)(v24, v23);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v23);
    }
  }
  v25 = *((_QWORD *)this + 148);
  if ( v25 )
  {
    v5 = (*(_DWORD *)(v25 + 20))-- == 1;
    if ( v5 && (void ***)v25 != &cspNull )
    {
      v26 = *(struct IMalloc **)(v25 + 8);
      if ( v26 || (v26 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v26->lpVtbl->Free)(v26, v25);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v25);
    }
  }
  v27 = *((_QWORD *)this + 147);
  if ( v27 )
  {
    v5 = (*(_DWORD *)(v27 + 20))-- == 1;
    if ( v5 && (void ***)v27 != &cspNull )
    {
      v28 = *(struct IMalloc **)(v27 + 8);
      if ( v28 || (v28 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v28->lpVtbl->Free)(v28, v27);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v27);
    }
  }
  v29 = (char *)*((_QWORD *)this + 93);
  *((_QWORD *)this + 91) = &_stackZeroed<ELEMENT_DATA,10>::`vftable';
  if ( v29 && v29 != (char *)this + 760 )
  {
    v30 = (struct IMalloc *)*((_QWORD *)this + 92);
    if ( v30 || (v30 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v30->lpVtbl->Free)(v30, v29);
    else
      HeapFree(g_hHeap, 0, v29);
  }
  v31 = (char *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 12) = &_stackZeroed<SXReadBase::XmlNsDecl,10>::`vftable';
  if ( v31 && v31 != (char *)this + 128 )
  {
    v32 = (struct IMalloc *)*((_QWORD *)this + 13);
    if ( v32 || (v32 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v32->lpVtbl->Free)(v32, v31);
    else
      HeapFree(g_hHeap, 0, v31);
  }
}

```

## disassembly

```asm
0x10040e630  mov     [rsp+arg_0], rbx
0x10040e635  mov     [rsp+arg_8], rbp
0x10040e63a  mov     [rsp+arg_10], rsi
0x10040e63f  push    rdi
0x10040e640  push    r14
0x10040e642  push    r15
0x10040e644  sub     rsp, 20h
0x10040e648  lea     rax, ??_7SXReadBase@@6B@; const SXReadBase::`vftable'
0x10040e64f  mov     rdi, rcx
0x10040e652  mov     [rcx], rax
0x10040e655  mov     eax, [rcx+78h]
0x10040e658  test    eax, eax
0x10040e65a  jz      short loc_10040E6D1
0x10040e65c  nop     dword ptr [rax+00h]
0x10040e660  lea     eax, [rax-1]
0x10040e663  lea     r9, [rax+rax*2]
0x10040e667  shl     r9, 4
0x10040e66b  add     r9, [rdi+70h]
0x10040e66f  cmp     dword ptr [r9+1Ch], 0FFFFFFFFh
0x10040e674  jl      short loc_10040E6D1
0x10040e676  mov     eax, [r9+24h]
0x10040e67a  xor     edx, edx
0x10040e67c  div     dword ptr [rdi+54h]
0x10040e67f  mov     rcx, [rdi+58h]
0x10040e683  mov     eax, [r9+28h]
0x10040e687  mov     [rcx+rdx*4], eax
0x10040e68a  mov     r8, [r9]; lpMem
0x10040e68d  test    r8, r8
0x10040e690  jz      short loc_10040E6C8
0x10040e692  mov     rcx, [rdi+8]
0x10040e696  test    rcx, rcx
0x10040e699  jnz     short loc_10040E6A7
0x10040e69b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e6a2  test    rcx, rcx
0x10040e6a5  jz      short loc_10040E6B9
0x10040e6a7  mov     rax, [rcx]
0x10040e6aa  mov     rdx, r8
0x10040e6ad  mov     rax, [rax+28h]
0x10040e6b1  call    cs:__guard_dispatch_icall_fptr
0x10040e6b7  jmp     short loc_10040E6C8
0x10040e6b9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e6c0  xor     edx, edx; dwFlags
0x10040e6c2  call    cs:__imp_HeapFree
0x10040e6c8  add     dword ptr [rdi+78h], 0FFFFFFFFh
0x10040e6cc  mov     eax, [rdi+78h]
0x10040e6cf  jnz     short loc_10040E660
0x10040e6d1  mov     r8, [rdi+58h]; lpMem
0x10040e6d5  test    r8, r8
0x10040e6d8  jz      short loc_10040E710
0x10040e6da  mov     rcx, [rdi+8]
0x10040e6de  test    rcx, rcx
0x10040e6e1  jnz     short loc_10040E6EF
0x10040e6e3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e6ea  test    rcx, rcx
0x10040e6ed  jz      short loc_10040E701
0x10040e6ef  mov     rax, [rcx]
0x10040e6f2  mov     rdx, r8
0x10040e6f5  mov     rax, [rax+28h]
0x10040e6f9  call    cs:__guard_dispatch_icall_fptr
0x10040e6ff  jmp     short loc_10040E710
0x10040e701  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e708  xor     edx, edx; dwFlags
0x10040e70a  call    cs:__imp_HeapFree
0x10040e710  xor     edx, edx; struct CStringPtr *
0x10040e712  lea     rcx, [rdi+4A0h]; this
0x10040e719  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e71e  xor     edx, edx; struct CStringPtr *
0x10040e720  lea     rcx, [rdi+498h]; this
0x10040e727  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e72c  xor     edx, edx; struct CStringPtr *
0x10040e72e  lea     rcx, [rdi+4A8h]; this
0x10040e735  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e73a  cmp     dword ptr [rdi+2F0h], 0
0x10040e741  jz      short loc_10040E790
0x10040e743  nop     dword ptr [rax+00h]
0x10040e747  nop     word ptr [rax+rax+00000000h]
0x10040e750  dec     dword ptr [rdi+2F0h]
0x10040e756  xor     edx, edx; struct CStringPtr *
0x10040e758  mov     ebx, [rdi+2F0h]
0x10040e75e  shl     rbx, 5
0x10040e762  add     rbx, [rdi+2E8h]
0x10040e769  lea     rcx, [rbx+8]; this
0x10040e76d  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e772  xor     edx, edx; struct CStringPtr *
0x10040e774  mov     rcx, rbx; this
0x10040e777  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e77c  lea     rcx, [rbx+10h]; this
0x10040e780  xor     edx, edx; struct CStringPtr *
0x10040e782  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040e787  cmp     dword ptr [rdi+2F0h], 0
0x10040e78e  jnz     short loc_10040E750
0x10040e790  lea     rbx, [rdi+18h]
0x10040e794  mov     esi, 4
0x10040e799  nop     dword ptr [rax+00000000h]
0x10040e7a0  mov     r8, [rbx]; lpMem
0x10040e7a3  test    r8, r8
0x10040e7a6  jz      short loc_10040E7DE
0x10040e7a8  mov     rcx, [rdi+8]
0x10040e7ac  test    rcx, rcx
0x10040e7af  jnz     short loc_10040E7BD
0x10040e7b1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e7b8  test    rcx, rcx
0x10040e7bb  jz      short loc_10040E7CF
0x10040e7bd  mov     rax, [rcx]
0x10040e7c0  mov     rdx, r8
0x10040e7c3  mov     rax, [rax+28h]
0x10040e7c7  call    cs:__guard_dispatch_icall_fptr
0x10040e7cd  jmp     short loc_10040E7DE
0x10040e7cf  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e7d6  xor     edx, edx; dwFlags
0x10040e7d8  call    cs:__imp_HeapFree
0x10040e7de  add     rbx, 10h
0x10040e7e2  sub     rsi, 1
0x10040e7e6  jnz     short loc_10040E7A0
0x10040e7e8  mov     r8, [rdi+588h]; lpMem
0x10040e7ef  test    r8, r8
0x10040e7f2  jz      short loc_10040E82A
0x10040e7f4  mov     rcx, [rdi+8]
0x10040e7f8  test    rcx, rcx
0x10040e7fb  jnz     short loc_10040E809
0x10040e7fd  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e804  test    rcx, rcx
0x10040e807  jz      short loc_10040E81B
0x10040e809  mov     rax, [rcx]
0x10040e80c  mov     rdx, r8
0x10040e80f  mov     rax, [rax+28h]
0x10040e813  call    cs:__guard_dispatch_icall_fptr
0x10040e819  jmp     short loc_10040E82A
0x10040e81b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e822  xor     edx, edx; dwFlags
0x10040e824  call    cs:__imp_HeapFree
0x10040e82a  mov     rcx, [rdi+5A0h]
0x10040e831  test    rcx, rcx
0x10040e834  jz      short loc_10040E843
0x10040e836  mov     rax, [rcx]
0x10040e839  mov     rax, [rax+10h]
0x10040e83d  call    cs:__guard_dispatch_icall_fptr
0x10040e843  mov     rcx, rdi; this
0x10040e846  call    ?Clear@SXReadBase@@IEAAXXZ; SXReadBase::Clear(void)
0x10040e84b  mov     r8, [rdi+4F8h]; lpMem
0x10040e852  lea     rbx, ?cspNull@@3VCStringPtr@@A; CStringPtr cspNull
0x10040e859  test    r8, r8
0x10040e85c  jz      short loc_10040E8A0
0x10040e85e  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e863  jnz     short loc_10040E8A0
0x10040e865  cmp     r8, rbx
0x10040e868  jz      short loc_10040E8A0
0x10040e86a  mov     rcx, [r8+8]
0x10040e86e  test    rcx, rcx
0x10040e871  jnz     short loc_10040E87F
0x10040e873  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e87a  test    rcx, rcx
0x10040e87d  jz      short loc_10040E891
0x10040e87f  mov     rax, [rcx]
0x10040e882  mov     rdx, r8
0x10040e885  mov     rax, [rax+28h]
0x10040e889  call    cs:__guard_dispatch_icall_fptr
0x10040e88f  jmp     short loc_10040E8A0
0x10040e891  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e898  xor     edx, edx; dwFlags
0x10040e89a  call    cs:__imp_HeapFree
0x10040e8a0  mov     r8, [rdi+4D8h]; lpMem
0x10040e8a7  test    r8, r8
0x10040e8aa  jz      short loc_10040E8EE
0x10040e8ac  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e8b1  jnz     short loc_10040E8EE
0x10040e8b3  cmp     r8, rbx
0x10040e8b6  jz      short loc_10040E8EE
0x10040e8b8  mov     rcx, [r8+8]
0x10040e8bc  test    rcx, rcx
0x10040e8bf  jnz     short loc_10040E8CD
0x10040e8c1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e8c8  test    rcx, rcx
0x10040e8cb  jz      short loc_10040E8DF
0x10040e8cd  mov     rax, [rcx]
0x10040e8d0  mov     rdx, r8
0x10040e8d3  mov     rax, [rax+28h]
0x10040e8d7  call    cs:__guard_dispatch_icall_fptr
0x10040e8dd  jmp     short loc_10040E8EE
0x10040e8df  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e8e6  xor     edx, edx; dwFlags
0x10040e8e8  call    cs:__imp_HeapFree
0x10040e8ee  mov     r8, [rdi+4D0h]; lpMem
0x10040e8f5  test    r8, r8
0x10040e8f8  jz      short loc_10040E93C
0x10040e8fa  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e8ff  jnz     short loc_10040E93C
0x10040e901  cmp     r8, rbx
0x10040e904  jz      short loc_10040E93C
0x10040e906  mov     rcx, [r8+8]
0x10040e90a  test    rcx, rcx
0x10040e90d  jnz     short loc_10040E91B
0x10040e90f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e916  test    rcx, rcx
0x10040e919  jz      short loc_10040E92D
0x10040e91b  mov     rax, [rcx]
0x10040e91e  mov     rdx, r8
0x10040e921  mov     rax, [rax+28h]
0x10040e925  call    cs:__guard_dispatch_icall_fptr
0x10040e92b  jmp     short loc_10040E93C
0x10040e92d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e934  xor     edx, edx; dwFlags
0x10040e936  call    cs:__imp_HeapFree
0x10040e93c  mov     r8, [rdi+4C8h]; lpMem
0x10040e943  test    r8, r8
0x10040e946  jz      short loc_10040E98A
0x10040e948  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e94d  jnz     short loc_10040E98A
0x10040e94f  cmp     r8, rbx
0x10040e952  jz      short loc_10040E98A
0x10040e954  mov     rcx, [r8+8]
0x10040e958  test    rcx, rcx
0x10040e95b  jnz     short loc_10040E969
0x10040e95d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e964  test    rcx, rcx
0x10040e967  jz      short loc_10040E97B
0x10040e969  mov     rax, [rcx]
0x10040e96c  mov     rdx, r8
0x10040e96f  mov     rax, [rax+28h]
0x10040e973  call    cs:__guard_dispatch_icall_fptr
0x10040e979  jmp     short loc_10040E98A
0x10040e97b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e982  xor     edx, edx; dwFlags
0x10040e984  call    cs:__imp_HeapFree
0x10040e98a  mov     r8, [rdi+4A8h]; lpMem
0x10040e991  test    r8, r8
0x10040e994  jz      short loc_10040E9D8
0x10040e996  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e99b  jnz     short loc_10040E9D8
0x10040e99d  cmp     r8, rbx
0x10040e9a0  jz      short loc_10040E9D8
0x10040e9a2  mov     rcx, [r8+8]
0x10040e9a6  test    rcx, rcx
0x10040e9a9  jnz     short loc_10040E9B7
0x10040e9ab  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e9b2  test    rcx, rcx
0x10040e9b5  jz      short loc_10040E9C9
0x10040e9b7  mov     rax, [rcx]
0x10040e9ba  mov     rdx, r8
0x10040e9bd  mov     rax, [rax+28h]
0x10040e9c1  call    cs:__guard_dispatch_icall_fptr
0x10040e9c7  jmp     short loc_10040E9D8
0x10040e9c9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e9d0  xor     edx, edx; dwFlags
0x10040e9d2  call    cs:__imp_HeapFree
0x10040e9d8  mov     r8, [rdi+4A0h]; lpMem
0x10040e9df  test    r8, r8
0x10040e9e2  jz      short loc_10040EA26
0x10040e9e4  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040e9e9  jnz     short loc_10040EA26
0x10040e9eb  cmp     r8, rbx
0x10040e9ee  jz      short loc_10040EA26
0x10040e9f0  mov     rcx, [r8+8]
0x10040e9f4  test    rcx, rcx
0x10040e9f7  jnz     short loc_10040EA05
0x10040e9f9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ea00  test    rcx, rcx
0x10040ea03  jz      short loc_10040EA17
0x10040ea05  mov     rax, [rcx]
0x10040ea08  mov     rdx, r8
0x10040ea0b  mov     rax, [rax+28h]
0x10040ea0f  call    cs:__guard_dispatch_icall_fptr
0x10040ea15  jmp     short loc_10040EA26
0x10040ea17  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ea1e  xor     edx, edx; dwFlags
0x10040ea20  call    cs:__imp_HeapFree
0x10040ea26  mov     r8, [rdi+498h]; lpMem
0x10040ea2d  test    r8, r8
0x10040ea30  jz      short loc_10040EA74
0x10040ea32  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040ea37  jnz     short loc_10040EA74
0x10040ea39  cmp     r8, rbx
0x10040ea3c  jz      short loc_10040EA74
0x10040ea3e  mov     rcx, [r8+8]
0x10040ea42  test    rcx, rcx
0x10040ea45  jnz     short loc_10040EA53
0x10040ea47  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ea4e  test    rcx, rcx
0x10040ea51  jz      short loc_10040EA65
0x10040ea53  mov     rax, [rcx]
0x10040ea56  mov     rdx, r8
0x10040ea59  mov     rax, [rax+28h]
0x10040ea5d  call    cs:__guard_dispatch_icall_fptr
0x10040ea63  jmp     short loc_10040EA74
0x10040ea65  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ea6c  xor     edx, edx; dwFlags
0x10040ea6e  call    cs:__imp_HeapFree
0x10040ea74  mov     r8, [rdi+2E8h]; lpMem
0x10040ea7b  lea     rax, ??_7?$_stackZeroed@UELEMENT_DATA@@$09@@6B@; const _stackZeroed<ELEMENT_DATA,10>::`vftable'
0x10040ea82  mov     [rdi+2D8h], rax
0x10040ea89  test    r8, r8
0x10040ea8c  jz      short loc_10040EAD3
0x10040ea8e  lea     rax, [rdi+2F8h]
0x10040ea95  cmp     r8, rax
0x10040ea98  jz      short loc_10040EAD3
0x10040ea9a  mov     rcx, [rdi+2E0h]
0x10040eaa1  test    rcx, rcx
0x10040eaa4  jnz     short loc_10040EAB2
0x10040eaa6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040eaad  test    rcx, rcx
  ... truncated ...
```
