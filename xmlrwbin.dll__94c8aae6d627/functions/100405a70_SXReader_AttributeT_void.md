# SXReader::AttributeT(void)

- ea: `0x100405a70`
- end: `0x100405f3d`
- name: `?AttributeT@SXReader@@AEAAXXZ`
- size: `1229`
- prototype: `void __fastcall(SXReader *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x100405790`

## callees

- `0x100401350`
- `0x100405a70`
- `0x100406550`
- `0x100406be0`
- `0x10040f700`
- `0x100410ba0`
- `0x100411000`
- `0x100413a50`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100405ca5`
- `KERNEL32!HeapAlloc` at `0x100405dbd`
- `KERNEL32!HeapAlloc` at `0x100405ca5`
- `KERNEL32!HeapAlloc` at `0x100405dbd`

## pseudocode

```c
void __fastcall SXReader::AttributeT(SXReader *this)
{
  __int64 v1; // rbp
  unsigned int v2; // r13d
  const wchar_t *v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // edx
  unsigned __int64 v7; // r15
  bool v8; // zf
  unsigned __int64 v9; // r15
  unsigned int v10; // ecx
  __int64 v11; // rax
  int v12; // edi
  int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int Mb32; // eax
  __int64 v18; // rdx
  struct CStringPtr **v19; // r12
  __int64 v20; // rdi
  wchar_t *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // ecx
  SIZE_T v24; // r8
  struct IMalloc *v25; // rcx
  unsigned __int8 *v26; // rax
  __int64 v27; // rax
  unsigned int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rdx
  unsigned int v33; // r8d
  int i; // [rsp+60h] [rbp+8h]

  v1 = *((_QWORD *)this + 188);
  v2 = 0;
  v4 = 0;
  v5 = *(_DWORD *)(v1 + 52);
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
  {
LABEL_49:
    MXRRaiseException(-2147352566);
    __debugbreak();
  }
  if ( v6 > *(_DWORD *)(v1 + 48) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)(v1 + 32), v6, 0x80u);
    v5 = *(_DWORD *)(v1 + 52);
  }
  v7 = (unsigned __int64)v5 << 7;
  v8 = *(_QWORD *)(v1 + 56) + v7 == 0;
  v9 = *(_QWORD *)(v1 + 56) + v7;
  v10 = v5;
  v11 = *(_QWORD *)(v1 + 40);
  if ( !v8 )
  {
    *(_QWORD *)(v9 + 8) = v11;
    *(_QWORD *)v9 = &AttributeBase::`vftable';
    *(_QWORD *)(v9 + 32) = v11;
    *(_QWORD *)(v9 + 40) = 0;
    *(_QWORD *)(v9 + 24) = &_xarray<AttributeValue,_xarray_item<AttributeValue>>::`vftable';
    *(_QWORD *)(v9 + 48) = 0;
    *(_QWORD *)(v9 + 96) = 0;
    *(_QWORD *)(v9 + 104) = 0;
    *(_QWORD *)(v9 + 112) = 0;
    *(_QWORD *)(v9 + 80) = 0;
    *(_QWORD *)(v9 + 64) = 0;
    RStringPtr::assign((RStringPtr *)(v9 + 96), 0);
    RStringPtr::assign((RStringPtr *)(v9 + 104), 0);
    RStringPtr::assign((RStringPtr *)(v9 + 112), 0);
    *(_QWORD *)v9 = &AttributeData::`vftable';
    v10 = *(_DWORD *)(v1 + 52);
  }
  *(_DWORD *)(v1 + 52) = v10 + 1;
  RStringPtr::assign((RStringPtr *)(v9 + 96), *((struct CStringPtr **)this + 153));
  RStringPtr::assign((RStringPtr *)(v9 + 104), *((struct CStringPtr **)this + 155));
  RStringPtr::assign((RStringPtr *)(v9 + 112), *((struct CStringPtr **)this + 154));
  *(_DWORD *)(v9 + 120) = *((_DWORD *)this + 312);
  v12 = *(_DWORD *)(*((_QWORD *)this + 155) + 16LL);
  for ( i = v12; SXReadBase::ReadAttributeValueSizeAndType(this); *(_DWORD *)(v29 + 8) = *((_DWORD *)this + 326) )
  {
    v13 = 16924672;
    if ( !v12 )
    {
      v14 = *((_DWORD *)this + 305);
      if ( v14 > 0x18 || !_bittest(&v13, v14) || v4 )
      {
LABEL_50:
        MXRRaiseException(-2147467259);
        __debugbreak();
      }
    }
    v15 = *(_DWORD *)(v9 + 44);
    v16 = v15 + 1;
    if ( v15 + 1 < v15 )
      goto LABEL_49;
    if ( v16 > *(_DWORD *)(v9 + 40) )
    {
      _mm_lfence();
      _varray_base::_ensureCapacity_((_varray_base *)(v9 + 24), v16, 0x10u);
    }
    if ( *((_DWORD *)this + 305) == 140 )
    {
      Mb32 = SXReadBase::GetMb32(this);
      v18 = *((_QWORD *)this + 90);
      if ( Mb32 >= *(_DWORD *)(v18 + 116) )
        goto LABEL_50;
      _mm_lfence();
      v19 = (struct CStringPtr **)(*(_QWORD *)(v18 + 120) + 40LL * Mb32);
      SXReadBase::CheckNSDecl(
        this,
        (const wchar_t *)v19[1] + 12,
        *((_DWORD *)v19[1] + 4),
        (const wchar_t *)*v19 + 12,
        *((_DWORD *)*v19 + 4),
        0);
      v20 = *((_QWORD *)this + 1);
      if ( v20 )
      {
        v21 = (wchar_t *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v20 + 24LL))(*((_QWORD *)this + 1), 88);
      }
      else if ( g_pMalloc )
      {
        v21 = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 88);
      }
      else
      {
        v21 = (wchar_t *)HeapAlloc(g_hHeap, 0, 0x58u);
      }
      v4 = v21;
      if ( !v21 )
      {
LABEL_47:
        MXRRaiseException(-2147024882);
        __debugbreak();
      }
      *((_QWORD *)v21 + 1) = v20;
      *((_QWORD *)v21 + 1) = *((_QWORD *)this + 1);
      *(_QWORD *)v21 = &QNAME_TRIPLE_SAVED::`vftable';
      *((_QWORD *)v21 + 8) = 0;
      *((_QWORD *)v21 + 9) = 0;
      *((_QWORD *)v21 + 10) = 0;
      *((_QWORD *)v21 + 2) = (char *)*v19 + 24;
      *((_DWORD *)v21 + 6) = *((_DWORD *)*v19 + 4);
      *((_QWORD *)v21 + 4) = (char *)v19[1] + 24;
      *((_DWORD *)v21 + 10) = *((_DWORD *)v19[1] + 4);
      *((_QWORD *)v21 + 6) = (char *)v19[2] + 24;
      *((_DWORD *)v21 + 14) = *((_DWORD *)v19[2] + 4);
      RStringPtr::assign((RStringPtr *)(v21 + 32), *v19);
      RStringPtr::assign((RStringPtr *)(v4 + 36), v19[1]);
      RStringPtr::assign((RStringPtr *)(v4 + 40), v19[2]);
      v12 = i;
      *((_DWORD *)this + 326) = 88;
      *((_DWORD *)this + 305) = 141;
    }
    else
    {
      v22 = *((_DWORD *)this + 174);
      if ( v22 && *((_DWORD *)this + 326) > v22 )
      {
        MXRRaiseException(-1072897499);
        JUMPOUT(0x100405F3CLL);
      }
      v23 = *((_DWORD *)this + 326);
      v24 = 10;
      if ( v23 )
        v24 = v23;
      v25 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v25 || (v25 = g_pMalloc) != 0 )
        v26 = (unsigned __int8 *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v25->lpVtbl->Alloc)(v25, v24);
      else
        v26 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, v24);
      v4 = (const wchar_t *)v26;
      if ( !v26 )
        goto LABEL_47;
      SXReadBase::GetBytes(this, v26, *((_DWORD *)this + 326));
    }
    v27 = *(unsigned int *)(v9 + 44);
    v28 = v27 + 1;
    if ( (int)v27 + 1 < (unsigned int)v27 )
      goto LABEL_49;
    if ( v28 > *(_DWORD *)(v9 + 40) )
    {
      _mm_lfence();
      _varray_base::_ensureCapacity_((_varray_base *)(v9 + 24), v28, 0x10u);
      v27 = *(unsigned int *)(v9 + 44);
    }
    v29 = *(_QWORD *)(v9 + 48) + 16 * v27;
    *(_DWORD *)(v9 + 44) = v27 + 1;
    *(_DWORD *)(v29 + 12) = *((_DWORD *)this + 305);
    *(_QWORD *)v29 = v4;
  }
  if ( v12 )
  {
    v32 = *((_QWORD *)this + 154);
    v33 = *(_DWORD *)(v32 + 16);
    if ( v33 )
      SXReadBase::CheckNSDecl(
        this,
        (const wchar_t *)(v32 + 24),
        v33,
        (const wchar_t *)(*((_QWORD *)this + 153) + 24LL),
        *(_DWORD *)(*((_QWORD *)this + 153) + 16LL),
        0);
  }
  else
  {
    if ( v4 )
      v2 = *((_DWORD *)this + 326) >> 1;
    else
      v4 = &qword_10042F910;
    SXReadBase::CheckNSDecl(this, *((const wchar_t **)this + 157), *((_DWORD *)this + 316), v4, v2, 1);
    v30 = *((_QWORD *)this + 185);
    if ( v30 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const wchar_t *, unsigned int))(*(_QWORD *)v30 + 48LL))(
              v30,
              *((_QWORD *)this + 157),
              *((unsigned int *)this + 316),
              v4,
              v2);
      if ( v31 < 0 )
      {
        _mm_lfence();
        MXRRaiseException(v31);
        __debugbreak();
      }
    }
  }
}

```

## disassembly

```asm
0x100405a70  mov     [rsp+arg_8], rbx
0x100405a75  mov     [rsp+arg_10], rbp
0x100405a7a  mov     [rsp+arg_18], rsi
0x100405a7f  push    rdi
0x100405a80  push    r12
0x100405a82  push    r13
0x100405a84  push    r14
0x100405a86  push    r15
0x100405a88  sub     rsp, 30h
0x100405a8c  mov     rbp, [rcx+5E0h]
0x100405a93  xor     r13d, r13d
0x100405a96  mov     rbx, rcx
0x100405a99  mov     r14d, r13d
0x100405a9c  mov     eax, [rbp+34h]
0x100405a9f  lea     edx, [rax+1]; unsigned int
0x100405aa2  cmp     edx, eax
0x100405aa4  jb      loc_100405F1C
0x100405aaa  cmp     edx, [rbp+30h]
0x100405aad  jbe     short loc_100405AC4
0x100405aaf  lfence
0x100405ab2  mov     r8d, 80h; unsigned __int64
0x100405ab8  lea     rcx, [rbp+20h]; this
0x100405abc  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100405ac1  mov     eax, [rbp+34h]
0x100405ac4  mov     r15d, eax
0x100405ac7  shl     r15, 7
0x100405acb  add     r15, [rbp+38h]
0x100405acf  mov     ecx, eax
0x100405ad1  mov     rax, [rbp+28h]
0x100405ad5  lea     r12, [r15+60h]
0x100405ad9  jz      short loc_100405B41
0x100405adb  lea     rcx, ??_7AttributeBase@@6B@; const AttributeBase::`vftable'
0x100405ae2  mov     [r15+8], rax
0x100405ae6  mov     [r15], rcx
0x100405ae9  xor     edx, edx; struct CStringPtr *
0x100405aeb  mov     [r15+20h], rax
0x100405aef  mov     rcx, r12; this
0x100405af2  lea     rax, ??_7?$_xarray@UAttributeValue@@V?$_xarray_item@UAttributeValue@@@@@@6B@; const _xarray<AttributeValue,_xarray_item<AttributeValue>>::`vftable'
0x100405af9  mov     [r15+28h], r13
0x100405afd  mov     [r15+18h], rax
0x100405b01  mov     [r15+30h], r13
0x100405b05  mov     [r12], r13
0x100405b09  mov     [r15+68h], r13
0x100405b0d  mov     [r15+70h], r13
0x100405b11  mov     [r15+50h], r13
0x100405b15  mov     [r15+40h], r13
0x100405b19  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b1e  xor     edx, edx; struct CStringPtr *
0x100405b20  lea     rcx, [r15+68h]; this
0x100405b24  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b29  xor     edx, edx; struct CStringPtr *
0x100405b2b  lea     rcx, [r15+70h]; this
0x100405b2f  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b34  lea     rax, ??_7AttributeData@@6B@; const AttributeData::`vftable'
0x100405b3b  mov     [r15], rax
0x100405b3e  mov     ecx, [rbp+34h]
0x100405b41  lea     eax, [rcx+1]
0x100405b44  mov     rcx, r12; this
0x100405b47  mov     [rbp+34h], eax
0x100405b4a  mov     rdx, [rbx+4C8h]; struct CStringPtr *
0x100405b51  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b56  mov     rdx, [rbx+4D8h]; struct CStringPtr *
0x100405b5d  lea     rcx, [r15+68h]; this
0x100405b61  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b66  mov     rdx, [rbx+4D0h]; struct CStringPtr *
0x100405b6d  lea     rcx, [r15+70h]; this
0x100405b71  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405b76  mov     eax, [rbx+4E0h]
0x100405b7c  mov     rcx, rbx; this
0x100405b7f  mov     [r15+78h], eax
0x100405b83  mov     rax, [rbx+4D8h]
0x100405b8a  mov     edi, [rax+10h]
0x100405b8d  mov     [rsp+58h+arg_0], edi
0x100405b91  call    ?ReadAttributeValueSizeAndType@SXReadBase@@IEAA_NXZ; SXReadBase::ReadAttributeValueSizeAndType(void)
0x100405b96  test    al, al
0x100405b98  jz      loc_100405E42
0x100405b9e  lea     rsi, ??_7QNAME_TRIPLE_SAVED@@6B@; const QNAME_TRIPLE_SAVED::`vftable'
0x100405ba5  mov     ecx, 1024000h
0x100405baa  test    edi, edi
0x100405bac  jnz     short loc_100405BCF
0x100405bae  mov     eax, [rbx+4C4h]
0x100405bb4  cmp     eax, 18h
0x100405bb7  ja      loc_100405F27
0x100405bbd  bt      ecx, eax
0x100405bc0  jnb     loc_100405F27
0x100405bc6  test    r14, r14
0x100405bc9  jnz     loc_100405F27
0x100405bcf  mov     eax, [r15+2Ch]
0x100405bd3  lea     edx, [rax+1]; unsigned int
0x100405bd6  cmp     edx, eax
0x100405bd8  jb      loc_100405F1C
0x100405bde  cmp     edx, [r15+28h]
0x100405be2  jbe     short loc_100405BF6
0x100405be4  lfence
0x100405be7  mov     r8d, 10h; unsigned __int64
0x100405bed  lea     rcx, [r15+18h]; this
0x100405bf1  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100405bf6  cmp     dword ptr [rbx+4C4h], 8Ch
0x100405c00  jnz     loc_100405D65
0x100405c06  mov     rcx, rbx; this
0x100405c09  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x100405c0e  mov     rdx, [rbx+2D0h]
0x100405c15  cmp     eax, [rdx+74h]
0x100405c18  jnb     loc_100405F27
0x100405c1e  lfence
0x100405c21  mov     eax, eax
0x100405c23  mov     [rsp+58h+var_30], r13b; bool
0x100405c28  lea     rcx, [rax+rax*4]
0x100405c2c  mov     rax, [rdx+78h]
0x100405c30  lea     r12, [rax+rcx*8]
0x100405c34  mov     rcx, [rax+rcx*8+8]
0x100405c39  mov     rax, [r12]
0x100405c3d  mov     r8d, [rcx+10h]; unsigned int
0x100405c41  lea     rdx, [rcx+18h]; wchar_t *
0x100405c45  lea     r9, [rax+18h]; wchar_t *
0x100405c49  mov     rcx, rbx; this
0x100405c4c  mov     eax, [rax+10h]
0x100405c4f  mov     [rsp+58h+var_38], eax; unsigned int
0x100405c53  call    ?CheckNSDecl@SXReadBase@@IEAAXPEB_WK0K_N@Z; SXReadBase::CheckNSDecl(wchar_t const *,ulong,wchar_t const *,ulong,bool)
0x100405c58  mov     rdi, [rbx+8]
0x100405c5c  test    rdi, rdi
0x100405c5f  jz      short loc_100405C78
0x100405c61  mov     rax, [rdi]
0x100405c64  mov     edx, 58h ; 'X'
0x100405c69  mov     rcx, rdi
0x100405c6c  mov     rax, [rax+18h]
0x100405c70  call    cs:__guard_dispatch_icall_fptr
0x100405c76  jmp     short loc_100405CAB
0x100405c78  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100405c7f  test    rcx, rcx
0x100405c82  jz      short loc_100405C98
0x100405c84  mov     rax, [rcx]
0x100405c87  mov     edx, 58h ; 'X'
0x100405c8c  mov     rax, [rax+18h]
0x100405c90  call    cs:__guard_dispatch_icall_fptr
0x100405c96  jmp     short loc_100405CAB
0x100405c98  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100405c9f  xor     edx, edx; dwFlags
0x100405ca1  lea     r8d, [rdx+58h]; dwBytes
0x100405ca5  call    cs:__imp_HeapAlloc
0x100405cab  mov     r14, rax
0x100405cae  test    rax, rax
0x100405cb1  jz      loc_100405F06
0x100405cb7  mov     [rax+8], rdi
0x100405cbb  mov     rax, [rbx+8]
0x100405cbf  mov     [r14+8], rax
0x100405cc3  mov     [r14], rsi
0x100405cc6  mov     [r14+40h], r13
0x100405cca  mov     [r14+48h], r13
0x100405cce  mov     [r14+50h], r13
0x100405cd2  mov     rax, [r12]
0x100405cd6  add     rax, 18h
0x100405cda  mov     [r14+10h], rax
0x100405cde  mov     rax, [r12]
0x100405ce2  mov     ecx, [rax+10h]
0x100405ce5  mov     [r14+18h], ecx
0x100405ce9  lea     rcx, [r14+40h]; this
0x100405ced  mov     rax, [r12+8]
0x100405cf2  add     rax, 18h
0x100405cf6  mov     [r14+20h], rax
0x100405cfa  mov     rax, [r12+8]
0x100405cff  mov     edx, [rax+10h]
0x100405d02  mov     [r14+28h], edx
0x100405d06  mov     rax, [r12+10h]
0x100405d0b  add     rax, 18h
0x100405d0f  mov     [r14+30h], rax
0x100405d13  mov     rax, [r12+10h]
0x100405d18  mov     edx, [rax+10h]
0x100405d1b  mov     [r14+38h], edx
0x100405d1f  mov     rdx, [r12]; struct CStringPtr *
0x100405d23  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405d28  mov     rdx, [r12+8]; struct CStringPtr *
0x100405d2d  lea     rcx, [r14+48h]; this
0x100405d31  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405d36  mov     rdx, [r12+10h]; struct CStringPtr *
0x100405d3b  lea     rcx, [r14+50h]; this
0x100405d3f  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100405d44  mov     edi, [rsp+58h+arg_0]
0x100405d48  lea     rsi, ??_7QNAME_TRIPLE_SAVED@@6B@; const QNAME_TRIPLE_SAVED::`vftable'
0x100405d4f  mov     dword ptr [rbx+518h], 58h ; 'X'
0x100405d59  mov     dword ptr [rbx+4C4h], 8Dh
0x100405d63  jmp     short loc_100405DE1
0x100405d65  mov     eax, [rbx+2B8h]
0x100405d6b  test    eax, eax
0x100405d6d  jz      short loc_100405D7B
0x100405d6f  cmp     [rbx+518h], eax
0x100405d75  ja      loc_100405F32
0x100405d7b  mov     ecx, [rbx+518h]
0x100405d81  mov     r8d, 0Ah
0x100405d87  test    ecx, ecx
0x100405d89  cmovnz  r8d, ecx; dwBytes
0x100405d8d  mov     rcx, [rbx+8]
0x100405d91  test    rcx, rcx
0x100405d94  jz      short loc_100405DA8
0x100405d96  mov     rax, [rcx]
0x100405d99  mov     rdx, r8
0x100405d9c  mov     rax, [rax+18h]
0x100405da0  call    cs:__guard_dispatch_icall_fptr
0x100405da6  jmp     short loc_100405DC3
0x100405da8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100405daf  test    rcx, rcx
0x100405db2  jnz     short loc_100405D96
0x100405db4  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100405dbb  xor     edx, edx; dwFlags
0x100405dbd  call    cs:__imp_HeapAlloc
0x100405dc3  mov     r14, rax
0x100405dc6  test    rax, rax
0x100405dc9  jz      loc_100405F06
0x100405dcf  mov     r8d, [rbx+518h]; unsigned int
0x100405dd6  mov     rdx, rax; unsigned __int8 *
0x100405dd9  mov     rcx, rbx; this
0x100405ddc  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x100405de1  mov     eax, [r15+2Ch]
0x100405de5  lea     edx, [rax+1]; unsigned int
0x100405de8  cmp     edx, eax
0x100405dea  jb      loc_100405F1C
0x100405df0  cmp     edx, [r15+28h]
0x100405df4  jbe     short loc_100405E0C
0x100405df6  lfence
0x100405df9  mov     r8d, 10h; unsigned __int64
0x100405dff  lea     rcx, [r15+18h]; this
0x100405e03  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100405e08  mov     eax, [r15+2Ch]
0x100405e0c  mov     rcx, rax
0x100405e0f  shl     rcx, 4
0x100405e13  add     rcx, [r15+30h]
0x100405e17  inc     eax
0x100405e19  mov     [r15+2Ch], eax
0x100405e1d  mov     eax, [rbx+4C4h]
0x100405e23  mov     [rcx+0Ch], eax
0x100405e26  mov     [rcx], r14
0x100405e29  mov     eax, [rbx+518h]
0x100405e2f  mov     [rcx+8], eax
0x100405e32  mov     rcx, rbx; this
0x100405e35  call    ?ReadAttributeValueSizeAndType@SXReadBase@@IEAA_NXZ; SXReadBase::ReadAttributeValueSizeAndType(void)
0x100405e3a  test    al, al
0x100405e3c  jnz     loc_100405BA5
0x100405e42  test    edi, edi
0x100405e44  jnz     short loc_100405EB6
0x100405e46  test    r14, r14
0x100405e49  jz      short loc_100405E57
0x100405e4b  mov     r13d, [rbx+518h]
0x100405e52  shr     r13d, 1
0x100405e55  jmp     short loc_100405E5E
0x100405e57  lea     r14, qword_10042F910
0x100405e5e  mov     r8d, [rbx+4F0h]; unsigned int
0x100405e65  mov     r9, r14; wchar_t *
0x100405e68  mov     rdx, [rbx+4E8h]; wchar_t *
0x100405e6f  mov     rcx, rbx; this
0x100405e72  mov     [rsp+58h+var_30], 1; bool
0x100405e77  mov     [rsp+58h+var_38], r13d; unsigned int
0x100405e7c  call    ?CheckNSDecl@SXReadBase@@IEAAXPEB_WK0K_N@Z; SXReadBase::CheckNSDecl(wchar_t const *,ulong,wchar_t const *,ulong,bool)
0x100405e81  mov     rcx, [rbx+5C8h]
0x100405e88  test    rcx, rcx
0x100405e8b  jz      short loc_100405EE9
0x100405e8d  mov     rax, [rcx]
0x100405e90  mov     r9, r14
0x100405e93  mov     r8d, [rbx+4F0h]
0x100405e9a  mov     rdx, [rbx+4E8h]
0x100405ea1  mov     [rsp+58h+var_38], r13d
0x100405ea6  mov     rax, [rax+30h]
0x100405eaa  call    cs:__guard_dispatch_icall_fptr
0x100405eb0  test    eax, eax
0x100405eb2  js      short loc_100405F11
0x100405eb4  jmp     short loc_100405EE9
0x100405eb6  mov     rdx, [rbx+4D0h]
0x100405ebd  mov     r8d, [rdx+10h]; unsigned int
0x100405ec1  test    r8d, r8d
0x100405ec4  jz      short loc_100405EE9
0x100405ec6  mov     rax, [rbx+4C8h]
0x100405ecd  add     rdx, 18h; wchar_t *
0x100405ed1  mov     [rsp+58h+var_30], r13b; bool
0x100405ed6  mov     rcx, rbx; this
0x100405ed9  lea     r9, [rax+18h]; wchar_t *
0x100405edd  mov     eax, [rax+10h]
0x100405ee0  mov     [rsp+58h+var_38], eax; unsigned int
0x100405ee4  call    ?CheckNSDecl@SXReadBase@@IEAAXPEB_WK0K_N@Z; SXReadBase::CheckNSDecl(wchar_t const *,ulong,wchar_t const *,ulong,bool)
0x100405ee9  mov     rbx, [rsp+58h+arg_8]
0x100405eee  mov     rbp, [rsp+58h+arg_10]
0x100405ef3  mov     rsi, [rsp+58h+arg_18]
0x100405ef8  add     rsp, 30h
0x100405efc  pop     r15
0x100405efe  pop     r14
0x100405f00  pop     r13
0x100405f02  pop     r12
0x100405f04  pop     rdi
0x100405f05  retn
0x100405f06  mov     ecx, 8007000Eh; int
0x100405f0b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405f10  int     3; Trap to Debugger
0x100405f11  lfence
0x100405f14  mov     ecx, eax; int
0x100405f16  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405f1b  int     3; Trap to Debugger
0x100405f1c  mov     ecx, 8002000Ah; int
0x100405f21  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405f26  int     3; Trap to Debugger
0x100405f27  mov     ecx, 80004005h; int
0x100405f2c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405f31  int     3; Trap to Debugger
  ... truncated ...
```
