# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000200c`
- end: `0x18000215e`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `338`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800045a0`

## callees

- `0x180001040`
- `0x180001494`
- `0x18000200c`
- `0x180004f4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800020df`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800020df`
- `ole32!CoTaskMemFree` at `0x1800020ed`
- `ole32!CoTaskMemFree` at `0x1800020f7`
- `ole32!CoTaskMemFree` at `0x18000212b`
- `ole32!CoTaskMemFree` at `0x180002135`
- `ole32!CoTaskMemFree` at `0x1800020ed`
- `ole32!CoTaskMemFree` at `0x1800020f7`
- `ole32!CoTaskMemFree` at `0x18000212b`
- `ole32!CoTaskMemFree` at `0x180002135`
- `ole32!CoTaskMemAlloc` at `0x18000207f`
- `ole32!CoTaskMemAlloc` at `0x180002093`
- `ole32!CoTaskMemAlloc` at `0x18000207f`
- `ole32!CoTaskMemAlloc` at `0x180002093`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  SIZE_T v9; // r15
  unsigned int v10; // esi
  LPVOID v11; // rax
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // edx

  v6 = (void **)operator new(0x10u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = -1;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( a3 )
  {
    do
      ++v7;
    while ( a3[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v9 = (unsigned int)(2 * v8 + 2);
  *v6 = CoTaskMemAlloc(v9);
  v10 = 2 * v7 + 2;
  v11 = CoTaskMemAlloc(v10);
  v12 = *v6;
  v6[1] = v11;
  if ( !v12 || !v11 )
  {
    CoTaskMemFree(v12);
    CoTaskMemFree(v6[1]);
    operator delete(v6);
    return (unsigned int)-2147024882;
  }
  memcpy_0(v12, a2, (unsigned int)v9);
  memcpy_0(v6[1], a3, v10);
  v13 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == v13 )
  {
    v14 = *(_QWORD *)this;
    v15 = 2 * v13;
    *((_DWORD *)this + 3) = v15;
    v16 = _o_realloc(v14, 8LL * v15);
    if ( !v16 )
    {
      CoTaskMemFree(*v6);
      CoTaskMemFree(v6[1]);
      operator delete(v6);
      *((int *)this + 3) /= 2;
      return (unsigned int)-2147024882;
    }
    *(_QWORD *)this = v16;
  }
  v17 = 0;
  *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
  return v17;
}

```

## disassembly

```asm
0x18000200c  push    rbx
0x18000200e  push    rbp
0x18000200f  push    rsi
0x180002010  push    rdi
0x180002011  push    r12
0x180002013  push    r13
0x180002015  push    r14
0x180002017  push    r15
0x180002019  sub     rsp, 28h
0x18000201d  mov     rbx, rcx
0x180002020  mov     r13d, 10h
0x180002026  mov     ecx, r13d; Size
0x180002029  mov     r14, r8
0x18000202c  mov     rbp, rdx
0x18000202f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002034  xor     r12d, r12d
0x180002037  mov     rdi, rax
0x18000203a  test    rax, rax
0x18000203d  jz      loc_180002146
0x180002043  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002047  test    rbp, rbp
0x18000204a  jnz     short loc_180002051
0x18000204c  mov     eax, r12d
0x18000204f  jmp     short loc_18000205F
0x180002051  mov     rax, rsi
0x180002054  inc     rax
0x180002057  cmp     [rbp+rax*2+0], r12w
0x18000205d  jnz     short loc_180002054
0x18000205f  test    r14, r14
0x180002062  jnz     short loc_180002069
0x180002064  mov     esi, r12d
0x180002067  jmp     short loc_180002073
0x180002069  inc     rsi
0x18000206c  cmp     [r14+rsi*2], r12w
0x180002071  jnz     short loc_180002069
0x180002073  lea     eax, ds:2[rax*2]
0x18000207a  mov     ecx, eax; cb
0x18000207c  mov     r15d, eax
0x18000207f  call    cs:__imp_CoTaskMemAlloc
0x180002085  mov     [rdi], rax
0x180002088  lea     eax, ds:2[rsi*2]
0x18000208f  mov     ecx, eax; cb
0x180002091  mov     esi, eax
0x180002093  call    cs:__imp_CoTaskMemAlloc
0x180002099  mov     rcx, [rdi]; void *
0x18000209c  mov     [rdi+8], rax
0x1800020a0  test    rcx, rcx
0x1800020a3  jz      loc_18000212B
0x1800020a9  test    rax, rax
0x1800020ac  jz      short loc_18000212B
0x1800020ae  mov     r8d, r15d; Size
0x1800020b1  mov     rdx, rbp; Src
0x1800020b4  call    memcpy_0
0x1800020b9  mov     rcx, [rdi+8]; void *
0x1800020bd  mov     r8d, esi; Size
0x1800020c0  mov     rdx, r14; Src
0x1800020c3  call    memcpy_0
0x1800020c8  mov     eax, [rbx+0Ch]
0x1800020cb  cmp     [rbx+8], eax
0x1800020ce  jnz     short loc_180002118
0x1800020d0  mov     rcx, [rbx]
0x1800020d3  add     eax, eax
0x1800020d5  movsxd  rdx, eax
0x1800020d8  shl     rdx, 3
0x1800020dc  mov     [rbx+0Ch], eax
0x1800020df  call    cs:__imp__o_realloc
0x1800020e5  test    rax, rax
0x1800020e8  jnz     short loc_180002115
0x1800020ea  mov     rcx, [rdi]; pv
0x1800020ed  call    cs:__imp_CoTaskMemFree
0x1800020f3  mov     rcx, [rdi+8]; pv
0x1800020f7  call    cs:__imp_CoTaskMemFree
0x1800020fd  mov     rdx, r13; unsigned __int64
0x180002100  mov     rcx, rdi; void *
0x180002103  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002108  mov     eax, [rbx+0Ch]
0x18000210b  cdq
0x18000210c  sub     eax, edx
0x18000210e  sar     eax, 1
0x180002110  mov     [rbx+0Ch], eax
0x180002113  jmp     short loc_180002146
0x180002115  mov     [rbx], rax
0x180002118  movsxd  rcx, dword ptr [rbx+8]
0x18000211c  mov     edx, r12d
0x18000211f  mov     rax, [rbx]
0x180002122  mov     [rax+rcx*8], rdi
0x180002126  inc     dword ptr [rbx+8]
0x180002129  jmp     short loc_18000214B
0x18000212b  call    cs:__imp_CoTaskMemFree
0x180002131  mov     rcx, [rdi+8]; pv
0x180002135  call    cs:__imp_CoTaskMemFree
0x18000213b  mov     rdx, r13; unsigned __int64
0x18000213e  mov     rcx, rdi; void *
0x180002141  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002146  mov     edx, 8007000Eh
0x18000214b  mov     eax, edx
0x18000214d  add     rsp, 28h
0x180002151  pop     r15
0x180002153  pop     r14
0x180002155  pop     r13
0x180002157  pop     r12
0x180002159  pop     rdi
0x18000215a  pop     rsi
0x18000215b  pop     rbp
0x18000215c  pop     rbx
0x18000215d  retn
```
