# CVarVector::GetNewSafeArray(void)

- ea: `0x180008cc0`
- end: `0x1800094e4`
- name: `?GetNewSafeArray@CVarVector@@QEAAPEAUtagSAFEARRAY@@XZ`
- size: `2084`
- prototype: `struct tagSAFEARRAY *__fastcall(CVarVector *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x180007770`
- `0x180039710`

## callees

- `0x180004e60`
- `0x180005500`
- `0x180005590`
- `0x1800056c0`
- `0x180005880`
- `0x180005e34`
- `0x18000723c`
- `0x180007280`
- `0x180007990`
- `0x180007e30`
- `0x180008cc0`
- `0x1800094f0`
- `0x180010370`
- `0x180014120`
- `0x1800243c0`
- `0x180027660`
- `0x180029040`
- `0x18002ca74`
- `0x18002ee7c`
- `0x18002ee96`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d00`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f44`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f44`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fb6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008d42`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008d42`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180008d5f`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180008d5f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008dff`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180009093`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180009133`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008dff`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180009093`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180009133`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008e6d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008e6d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800090f6`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800090f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct tagSAFEARRAY *__fastcall CVarVector::GetNewSafeArray(CVarVector *this)
{
  char *v2; // rsi
  int v3; // ecx
  SAFEARRAY *v4; // rax
  _DWORD *v5; // r12
  int v6; // r12d
  int i; // edi
  int v8; // r14d
  SAFEARRAY **v9; // rcx
  char (**v10)[4]; // rdx
  int v11; // r8d
  unsigned __int8 v12; // cl
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  __m128i v15; // xmm6
  unsigned int v16; // xmm0_4
  unsigned __int16 *v17; // r15
  SAFEARRAYBOUND *v18; // rdx
  int v19; // ecx
  HRESULT v20; // eax
  size_t v21; // r9
  unsigned __int16 *BSTRAtThrow; // rax
  OLECHAR *v23; // r14
  __int64 v24; // rbx
  unsigned int v25; // edx
  const struct CVar **v27; // rax
  unsigned int v28; // edx
  int v29; // eax
  HRESULT v30; // eax
  struct IUnknown *UnknownAt; // rax
  struct IUnknown *Unknown; // r14
  _WORD *ScalarAt; // rax
  unsigned int v34; // edx
  int v35; // [rsp+28h] [rbp-89h] BYREF
  struct IUnknown *v36[2]; // [rsp+30h] [rbp-81h] BYREF
  int v37; // [rsp+40h] [rbp-71h]
  int v38; // [rsp+44h] [rbp-6Dh]
  int v39; // [rsp+48h] [rbp-69h] BYREF
  __int128 v40; // [rsp+50h] [rbp-61h]
  int v41; // [rsp+60h] [rbp-51h]
  int v42; // [rsp+64h] [rbp-4Dh]
  struct IUnknown *v43; // [rsp+68h] [rbp-49h]
  struct IUnknown *v44; // [rsp+70h] [rbp-41h]
  unsigned __int16 *v45; // [rsp+78h] [rbp-39h]
  CSafeArray *v46; // [rsp+80h] [rbp-31h] BYREF
  char v47[8]; // [rsp+88h] [rbp-29h] BYREF
  char v48[8]; // [rsp+90h] [rbp-21h] BYREF
  char v49[8]; // [rsp+98h] [rbp-19h] BYREF
  BSTR *p_bstrString; // [rsp+A0h] [rbp-11h]
  OLECHAR *v51; // [rsp+A8h] [rbp-9h]
  __int64 rgIndices; // [rsp+120h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+128h] [rbp+77h] BYREF
  __int64 pv; // [rsp+130h] [rbp+7Fh] BYREF

  if ( hHeap )
    v2 = (char *)HeapAlloc(hHeap, 0, 0x28u);
  else
    v2 = 0;
  rgIndices = (__int64)v2;
  if ( v2 )
  {
    v3 = *(_DWORD *)this;
    *(_DWORD *)v2 = -1;
    *((_DWORD *)v2 + 1) = 1;
    *((_DWORD *)v2 + 2) = 32;
    *((_DWORD *)v2 + 4) = v3;
    *((_DWORD *)v2 + 6) = 32;
    *((_DWORD *)v2 + 7) = 0;
    v4 = SafeArrayCreate(v3, 1u, (SAFEARRAYBOUND *)v2 + 3);
    if ( !v4 )
      _ThrowMemoryException_();
    *((_QWORD *)v2 + 4) = v4;
    *((_DWORD *)v2 + 3) = 0;
    *((_DWORD *)v2 + 5) = SafeArrayGetElemsize(v4);
  }
  if ( !v2 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&rgIndices;
  }
  v46 = (CSafeArray *)v2;
  v5 = (_DWORD *)*((_QWORD *)this + 13);
  if ( v5 )
    v6 = *v5 + 1;
  else
    v6 = *((_DWORD *)this + 2);
  for ( i = 0; i < v6; ++i )
  {
    v37 = 0;
    v8 = 0;
    v35 = 0;
    v38 = 1;
    *(_OWORD *)v36 = 0;
    v9 = (SAFEARRAY **)*((_QWORD *)this + 13);
    if ( !v9 )
    {
      v27 = (const struct CVar **)CFlexArray::operator[]((__int64)this + 8, i);
      CVar::CVar((CVar *)&v39, *v27);
      v15 = (__m128i)(unsigned __int64)v40;
      *(_OWORD *)v36 = v40;
      v40 = 0u;
      v8 = v39;
      v35 = v39;
      v39 = 0;
      v37 = v41;
      v41 = 0;
      v38 = v42;
      v42 = 1;
      CVar::~CVar((CVar *)&v39, v28);
      v14 = (unsigned int)_mm_cvtsi128_si32(v15);
      v13 = LOWORD(v36[0]);
      v12 = (unsigned __int8)v36[0];
      goto LABEL_17;
    }
    v10 = (char (**)[4])*((_QWORD *)this + 14);
    v11 = *(_DWORD *)this;
    if ( v10 )
    {
      if ( v11 == 8 )
      {
        v10 += i;
        if ( !*v10 )
          v10 = &off_180068020;
LABEL_28:
        v21 = 8;
      }
      else
      {
        v21 = 0;
        switch ( v11 )
        {
          case 2:
          case 11:
            v10 = (char (**)[4])((char *)v10 + 2 * i);
            v21 = 2;
            break;
          case 3:
          case 4:
            v10 = (char (**)[4])((char *)v10 + 4 * i);
            v21 = 4;
            break;
          case 5:
          case 13:
            v10 += i;
            goto LABEL_28;
          case 17:
            v10 = (char (**)[4])((char *)v10 + i);
            v21 = 1;
            break;
          default:
            break;
        }
      }
      v35 = *(_DWORD *)this;
      memcpy_0(v36, v10, v21);
      v37 = 0;
      v38 = 0;
      v8 = v35;
LABEL_30:
      v15.m128i_i64[0] = (__int64)v36[0];
      v14 = LODWORD(v36[0]);
LABEL_31:
      v13 = LOWORD(v36[0]);
LABEL_32:
      v12 = v13;
      goto LABEL_17;
    }
    if ( v11 == 17 )
    {
      LODWORD(rgIndices) = i;
      pv = 0;
      if ( i <= *(_DWORD *)v9 + 1 )
        SafeArrayGetElement(v9[4], (LONG *)&rgIndices, &pv);
      v12 = pv;
      v8 = 17;
      v35 = 17;
      LOBYTE(v36[0]) = pv;
      v13 = LOWORD(v36[0]);
      v14 = LODWORD(v36[0]);
      v15.m128i_i64[0] = (__int64)v36[0];
LABEL_17:
      v16 = v14;
LABEL_18:
      v17 = (unsigned __int16 *)v15.m128i_i64[0];
      goto LABEL_19;
    }
    switch ( v11 )
    {
      case 2:
        LODWORD(rgIndices) = i;
        pv = 0;
        if ( i <= *(_DWORD *)v9 + 1 )
          SafeArrayGetElement(v9[4], (LONG *)&rgIndices, &pv);
        v13 = (unsigned __int16)pv;
        v8 = 2;
        v35 = 2;
        LOWORD(v36[0]) = pv;
        v14 = LODWORD(v36[0]);
        v15.m128i_i64[0] = (__int64)v36[0];
        v12 = pv;
        goto LABEL_17;
      case 3:
        LODWORD(rgIndices) = i;
        pv = 0;
        if ( i <= *(_DWORD *)v9 + 1 )
          SafeArrayGetElement(v9[4], (LONG *)&rgIndices, &pv);
        v14 = (unsigned int)pv;
        LODWORD(v36[0]) = pv;
        v8 = 3;
        v35 = 3;
        v13 = (unsigned int)pv;
        v15.m128i_i64[0] = (__int64)v36[0];
        v12 = pv;
        goto LABEL_17;
      case 4:
        LODWORD(v36[0]) = *(_DWORD *)CSafeArray::GetScalarAt(v9, v48, (unsigned int)i);
        v16 = (unsigned int)v36[0];
        v8 = 4;
        v35 = 4;
        v13 = LOWORD(v36[0]);
        v14 = (unsigned int)_mm_cvtsi128_si32((__m128i)LODWORD(v36[0]));
        v15.m128i_i64[0] = (__int64)v36[0];
        v12 = (unsigned __int8)v36[0];
        goto LABEL_18;
      case 5:
        v36[0] = *(struct IUnknown **)CSafeArray::GetScalarAt(v9, v49, (unsigned int)i);
        v15.m128i_i64[0] = (__int64)v36[0];
        v8 = 5;
        v35 = 5;
        v14 = (unsigned int)_mm_cvtsi128_si32((__m128i)(unsigned __int64)v36[0]);
        goto LABEL_31;
      case 8:
        BSTRAtThrow = CSafeArray::GetBSTRAtThrow((CSafeArray *)v9, i);
        p_bstrString = &bstrString;
        v8 = 8;
        v35 = 8;
        v17 = BSTRAtThrow;
        bstrString = 0;
        v36[0] = (struct IUnknown *)BSTRAtThrow;
        SysFreeString(0);
        v13 = (unsigned __int16)v17;
        v14 = (unsigned __int64)v17;
        v16 = (unsigned int)v17;
        v15.m128i_i64[0] = (__int64)v17;
        v12 = (unsigned __int8)v17;
        break;
      case 11:
        ScalarAt = (_WORD *)CSafeArray::GetScalarAt(v9, v47, (unsigned int)i);
        v13 = (unsigned __int16)*ScalarAt;
        LOWORD(v36[0]) = *ScalarAt;
        v8 = 11;
        v35 = 11;
        v14 = LODWORD(v36[0]);
        v15.m128i_i64[0] = (__int64)v36[0];
        goto LABEL_32;
      case 13:
        UnknownAt = CSafeArray::GetUnknownAt((CSafeArray *)v9, i);
        v17 = (unsigned __int16 *)UnknownAt;
        v43 = UnknownAt;
        v8 = 13;
        v35 = 13;
        v36[0] = UnknownAt;
        if ( UnknownAt )
          ((void (__fastcall *)(struct IUnknown *))UnknownAt->lpVtbl->AddRef)(UnknownAt);
        if ( v17 )
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v17 + 16LL))(v17);
        v43 = 0;
        v13 = (unsigned __int16)v17;
        v14 = (unsigned int)v17;
        v16 = (unsigned int)v17;
        v15.m128i_i64[0] = (__int64)v17;
        v12 = (unsigned __int8)v17;
        break;
      default:
        goto LABEL_30;
    }
LABEL_19:
    if ( *(_DWORD *)this != 17 )
    {
      switch ( *(_DWORD *)this )
      {
        case 2:
        case 0xB:
          rgIndices = (unsigned __int16)v13;
          CSafeArray::AddScalar(v2, (unsigned __int16)v13, v13);
          goto LABEL_24;
        case 3:
          rgIndices = (unsigned int)v14;
          CSafeArray::AddScalar(v2, (unsigned int)v14, v13);
          goto LABEL_24;
        case 4:
          rgIndices = v16;
          CSafeArray::AddScalar(v2, v16, v13);
          goto LABEL_24;
        case 5:
          rgIndices = v15.m128i_i64[0];
          CSafeArray::AddScalar(v2, v15.m128i_i64[0], v13);
          goto LABEL_24;
        case 8:
          if ( v8 == 8 )
            v23 = COleAuto::_SysAllocString(v17);
          else
            v23 = 0;
          v51 = v23;
          CSafeArray::AddBSTR((LONG *)v2, v23);
          if ( v23 )
            SysFreeString(v23);
          goto LABEL_24;
        case 9:
          Unknown = CVar::GetUnknown((CVar *)&v35);
          v44 = Unknown;
          CSafeArray::AddUnknown((CSafeArray *)v2, Unknown);
          if ( Unknown )
            ((void (__fastcall *)(struct IUnknown *))Unknown->lpVtbl->Release)(Unknown);
          v44 = 0;
          goto LABEL_24;
        case 0xD:
          if ( v17 )
            (*(void (__fastcall **)(unsigned __int16 *, unsigned __int64, __int64))(*(_QWORD *)v17 + 8LL))(
              v17,
              v14,
              v13);
          v45 = v17;
          CSafeArray::AddUnknown((CSafeArray *)v2, (struct IUnknown *)v17);
          if ( v17 )
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v17 + 16LL))(v17);
          v45 = 0;
          goto LABEL_24;
        default:
          *((_DWORD *)v2 + 1) = 2;
          CVar::~CVar((CVar *)&v35, v14);
          CDeleteMe<CSafeArray>::~CDeleteMe<CSafeArray>(&v46, v34);
          return 0;
      }
    }
    rgIndices = v12;
    v18 = (SAFEARRAYBOUND *)(v2 + 24);
    v19 = *((_DWORD *)v2 + 6);
    if ( *(_DWORD *)v2 == v19 - 1 )
    {
      v29 = *((_DWORD *)v2 + 2);
      if ( !v29 )
        goto LABEL_24;
      v18->cElements = v19 + v29;
      v30 = SafeArrayRedim(*((SAFEARRAY **)v2 + 4), v18);
      if ( v30 == -2147024882 )
LABEL_54:
        _ThrowMemoryException_();
      if ( v30 )
        *((_DWORD *)v2 + 3) = 1;
    }
    ++*(_DWORD *)v2;
    v20 = SafeArrayPutElement(*((SAFEARRAY **)v2 + 4), (LONG *)v2, &rgIndices);
    if ( v20 == -2147024882 )
      goto LABEL_54;
    if ( v20 )
      *((_DWORD *)v2 + 3) = 1;
LABEL_24:
    CVar::~CVar((CVar *)&v35, (unsigned int)v18);
  }
  CSafeArray::Trim((CSafeArray *)v2);
  v24 = *((_QWORD *)v2 + 4);
  CSafeArray::`scalar deleting destructor'((CSafeArray *)v2, v25);
  return (struct tagSAFEARRAY *)v24;
}

```

## disassembly

```asm
0x180008cc0  mov     rax, rsp
0x180008cc3  mov     [rax+8], rbx
0x180008cc7  push    rbp
0x180008cc8  push    rsi
0x180008cc9  push    rdi
0x180008cca  push    r12
0x180008ccc  push    r13
0x180008cce  push    r14
0x180008cd0  push    r15
0x180008cd2  lea     rbp, [rax-5Fh]
0x180008cd6  sub     rsp, 0D0h
0x180008cdd  movaps  xmmword ptr [rax-48h], xmm6
0x180008ce1  movaps  xmmword ptr [rax-58h], xmm7
0x180008ce5  mov     rbx, rcx
0x180008ce8  mov     rcx, cs:hHeap; hHeap
0x180008cef  test    rcx, rcx
0x180008cf2  jz      loc_18000926F
0x180008cf8  xor     edx, edx; dwFlags
0x180008cfa  mov     r8d, 28h ; '('; dwBytes
0x180008d00  call    cs:__imp_HeapAlloc
0x180008d06  mov     rsi, rax
0x180008d09  mov     [rbp+57h+rgIndices], rsi
0x180008d0d  test    rsi, rsi
0x180008d10  jz      short loc_180008D68
0x180008d12  mov     ecx, [rbx]; vt
0x180008d14  mov     dword ptr [rsi], 0FFFFFFFFh
0x180008d1a  mov     dword ptr [rsi+4], 1
0x180008d21  mov     dword ptr [rsi+8], 20h ; ' '
0x180008d28  mov     [rsi+10h], ecx
0x180008d2b  lea     r8, [rsi+18h]; rgsabound
0x180008d2f  mov     dword ptr [r8], 20h ; ' '
0x180008d36  mov     dword ptr [rsi+1Ch], 0
0x180008d3d  mov     edx, 1; cDims
0x180008d42  call    cs:__imp_SafeArrayCreate
0x180008d48  test    rax, rax
0x180008d4b  jz      loc_180009276
0x180008d51  mov     [rsi+20h], rax
0x180008d55  mov     dword ptr [rsi+0Ch], 0
0x180008d5c  mov     rcx, rax; psa
0x180008d5f  call    cs:__imp_SafeArrayGetElemsize
0x180008d65  mov     [rsi+14h], eax
0x180008d68  test    rsi, rsi
0x180008d6b  jz      loc_18000927C
0x180008d71  mov     [rbp+57h+var_88], rsi
0x180008d75  mov     r12, [rbx+68h]
0x180008d79  test    r12, r12
0x180008d7c  jz      loc_1800090BC
0x180008d82  mov     r12d, [r12]
0x180008d86  inc     r12d
0x180008d89  xor     edi, edi
0x180008d8b  xorps   xmm7, xmm7
0x180008d8e  lea     r10, __ImageBase
0x180008d95  cmp     edi, r12d
0x180008d98  jge     loc_180008FC1
0x180008d9e  xor     r15d, r15d
0x180008da1  mov     [rbp+57h+var_C8], r15d
0x180008da5  xor     r14d, r14d
0x180008da8  mov     dword ptr [rsp+100h+var_E0], r14d
0x180008dad  mov     [rbp+57h+var_C4], 1
0x180008db4  xorps   xmm0, xmm0
0x180008db7  movups  xmmword ptr [rsp+100h+var_E0+8], xmm0
0x180008dbc  mov     rcx, [rbx+68h]; this
0x180008dc0  test    rcx, rcx
0x180008dc3  jz      loc_180008FFD
0x180008dc9  mov     rdx, [rbx+70h]
0x180008dcd  mov     r8d, [rbx]
0x180008dd0  test    rdx, rdx
0x180008dd3  jnz     loc_180008E97
0x180008dd9  cmp     r8d, 11h
0x180008ddd  jnz     loc_180008EF7
0x180008de3  mov     dword ptr [rbp+57h+rgIndices], edi
0x180008de6  movsd   [rbp+57h+pv], xmm7
0x180008deb  mov     eax, [rcx]
0x180008ded  inc     eax
0x180008def  cmp     edi, eax
0x180008df1  jg      short loc_180008E05
0x180008df3  lea     r8, [rbp+57h+pv]; pv
0x180008df7  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180008dfb  mov     rcx, [rcx+20h]; psa
0x180008dff  call    cs:__imp_SafeArrayGetElement
0x180008e05  movzx   ecx, byte ptr [rbp+57h+pv]
0x180008e09  mov     r14d, 11h
0x180008e0f  mov     dword ptr [rsp+100h+var_E0], r14d
0x180008e14  mov     byte ptr [rsp+100h+var_E0+8], cl
0x180008e18  movzx   r8d, word ptr [rsp+100h+var_E0+8]
0x180008e1e  mov     edx, dword ptr [rsp+100h+var_E0+8]
0x180008e22  movsd   xmm6, [rsp+100h+var_E0+8]
0x180008e28  movd    xmm0, edx
0x180008e2c  movq    r15, xmm6
0x180008e31  mov     eax, [rbx]
0x180008e33  cmp     eax, 11h
0x180008e36  jnz     loc_180008F63
0x180008e3c  mov     [rbp+57h+rgIndices], 0
0x180008e44  mov     byte ptr [rbp+57h+rgIndices], cl
0x180008e47  mov     rax, [rbp+57h+rgIndices]
0x180008e4b  mov     [rbp+57h+rgIndices], rax
0x180008e4f  lea     rdx, [rsi+18h]; psaboundNew
0x180008e53  mov     ecx, [rdx]
0x180008e55  lea     eax, [rcx-1]
0x180008e58  cmp     [rsi], eax
0x180008e5a  jz      loc_1800090E3
0x180008e60  inc     dword ptr [rsi]
0x180008e62  lea     r8, [rbp+57h+rgIndices]; pv
0x180008e66  mov     rdx, rsi; rgIndices
0x180008e69  mov     rcx, [rsi+20h]; psa
0x180008e6d  call    cs:__imp_SafeArrayPutElement
0x180008e73  cmp     eax, 8007000Eh
0x180008e78  jz      loc_180009162
0x180008e7e  test    eax, eax
0x180008e80  jnz     loc_180009415
0x180008e86  lea     rcx, [rsp+100h+var_E0]; this
0x180008e8b  call    ??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180008e90  inc     edi
0x180008e92  jmp     loc_180008D8E
0x180008e97  cmp     r8d, 8
0x180008e9b  jnz     loc_18000936D
0x180008ea1  movsxd  rax, edi
0x180008ea4  lea     rdx, [rdx+rax*8]; Src
0x180008ea8  cmp     qword ptr [rdx], 0
0x180008eac  jz      loc_1800093CD
0x180008eb2  mov     r9d, 8
0x180008eb8  mov     dword ptr [rsp+100h+var_E0], r8d; jumptable 000000018000938A default case, cases 6-10,12,14-16
0x180008ebd  mov     r8, r9; Size
0x180008ec0  lea     rcx, [rsp+100h+var_E0+8]; void *
0x180008ec5  call    memcpy_0
0x180008eca  xor     eax, eax
0x180008ecc  mov     [rbp+57h+var_C8], eax
0x180008ecf  mov     [rbp+57h+var_C4], 1
0x180008ed6  mov     [rbp+57h+var_C4], eax
0x180008ed9  mov     r14d, dword ptr [rsp+100h+var_E0]
0x180008ede  movsd   xmm6, [rsp+100h+var_E0+8]; jumptable 0000000180008F0F default case, cases 6,7,9,10,12
0x180008ee4  mov     edx, dword ptr [rsp+100h+var_E0+8]
0x180008ee8  movzx   r8d, word ptr [rsp+100h+var_E0+8]
0x180008eee  movzx   ecx, r8b
0x180008ef2  jmp     loc_180008E28
0x180008ef7  add     r8d, 0FFFFFFFEh; switch 12 cases
0x180008efb  cmp     r8d, 0Bh
0x180008eff  ja      short def_180008F0F; jumptable 0000000180008F0F default case, cases 6,7,9,10,12
0x180008f01  movsxd  rax, r8d
0x180008f04  mov     edx, ds:(jpt_180008F0F - 180000000h)[r10+rax*4]
0x180008f0c  add     rdx, r10
0x180008f0f  jmp     rdx; switch jump
0x180008f11  mov     edx, edi; jumptable 0000000180008F0F case 8
0x180008f13  call    ?GetBSTRAtThrow@CSafeArray@@QEAAPEAGH@Z; CSafeArray::GetBSTRAtThrow(int)
0x180008f18  mov     [rbp+57h+bstrString], rax
0x180008f1c  lea     rax, [rbp+57h+bstrString]
0x180008f20  mov     [rbp+57h+var_68], rax
0x180008f24  mov     r14d, 8
0x180008f2a  mov     dword ptr [rsp+100h+var_E0], r14d
0x180008f2f  mov     r15, [rbp+57h+bstrString]
0x180008f33  mov     [rbp+57h+bstrString], 0
0x180008f3b  mov     [rsp+100h+var_E0+8], r15
0x180008f40  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180008f44  call    cs:__imp_SysFreeString
0x180008f4a  movzx   r8d, r15w
0x180008f4e  mov     rdx, r15
0x180008f51  movd    xmm0, edx
0x180008f55  movq    xmm6, r15
0x180008f5a  movzx   ecx, r15b
0x180008f5e  jmp     loc_180008E31
0x180008f63  add     eax, 0FFFFFFFEh; switch 12 cases
0x180008f66  cmp     eax, 0Bh
0x180008f69  ja      def_180008F83; jumptable 0000000180008F83 default case, cases 6,7,10,12
0x180008f6f  cdqe
0x180008f71  lea     r9, __ImageBase
0x180008f78  mov     ecx, ds:(jpt_180008F83 - 180000000h)[r9+rax*4]
0x180008f80  add     rcx, r9
0x180008f83  jmp     rcx; switch jump
0x180008f85  cmp     r14d, 8; jumptable 0000000180008F83 case 8
0x180008f89  jnz     loc_18000940D
0x180008f8f  mov     rcx, r15; unsigned __int16 *
0x180008f92  call    ?_SysAllocString@COleAuto@@SAPEAGPEBG@Z; COleAuto::_SysAllocString(ushort const *)
0x180008f97  mov     r14, rax
0x180008f9a  mov     [rbp+57h+var_60], r14
0x180008f9e  mov     rdx, r14; psz
0x180008fa1  mov     rcx, rsi; rgIndices
0x180008fa4  call    ?AddBSTR@CSafeArray@@QEAAHPEAG@Z; CSafeArray::AddBSTR(ushort *)
0x180008fa9  nop
0x180008faa  test    r14, r14
0x180008fad  jz      loc_180008E86
0x180008fb3  mov     rcx, r14; bstrString
0x180008fb6  call    cs:__imp_SysFreeString
0x180008fbc  jmp     loc_180008E86
0x180008fc1  mov     rcx, rsi; this
0x180008fc4  call    ?Trim@CSafeArray@@QEAAHXZ; CSafeArray::Trim(void)
0x180008fc9  mov     rbx, [rsi+20h]
0x180008fcd  mov     rcx, rsi; this
0x180008fd0  call    ??_GCSafeArray@@QEAAPEAXI@Z; CSafeArray::`scalar deleting destructor'(uint)
0x180008fd5  mov     rax, rbx
0x180008fd8  lea     r11, [rsp+100h+var_30]
0x180008fe0  mov     rbx, [r11+40h]
0x180008fe4  movaps  xmm6, xmmword ptr [r11-10h]
0x180008fe9  movaps  xmm7, xmmword ptr [r11-20h]
0x180008fee  mov     rsp, r11
0x180008ff1  pop     r15
0x180008ff3  pop     r14
0x180008ff5  pop     r13
0x180008ff7  pop     r12
0x180008ff9  pop     rdi
0x180008ffa  pop     rsi
0x180008ffb  pop     rbp
0x180008ffc  retn
0x180008ffd  mov     edx, edi
0x180008fff  lea     rcx, [rbx+8]
0x180009003  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180009008  mov     rdx, [rax]; struct CVar *
0x18000900b  lea     rcx, [rbp+57h+var_C0]; this
0x18000900f  call    ??0CVar@@QEAA@AEBV0@@Z; CVar::CVar(CVar const &)
0x180009014  nop
0x180009015  movsd   xmm6, [rbp+57h+var_B8]
0x18000901a  movsd   [rsp+100h+var_E0+8], xmm6
0x180009020  mov     rax, [rbp+57h+var_B0]
0x180009024  mov     [rbp+57h+var_D0], rax
0x180009028  movsd   [rbp+57h+var_B8], xmm7
0x18000902d  mov     [rbp+57h+var_B0], 0
0x180009035  mov     eax, r14d
0x180009038  mov     r14d, [rbp+57h+var_C0]
0x18000903c  mov     dword ptr [rsp+100h+var_E0], r14d
0x180009041  mov     [rbp+57h+var_C0], eax
0x180009044  mov     eax, [rbp+57h+var_A8]
0x180009047  mov     [rbp+57h+var_C8], eax
0x18000904a  mov     [rbp+57h+var_A8], r15d
0x18000904e  mov     eax, [rbp+57h+var_A4]
0x180009051  mov     [rbp+57h+var_C4], eax
0x180009054  mov     [rbp+57h+var_A4], 1
0x18000905b  lea     rcx, [rbp+57h+var_C0]; this
0x18000905f  call    ??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180009064  movd    edx, xmm6
0x180009068  movzx   r8d, word ptr [rsp+100h+var_E0+8]
0x18000906e  movzx   ecx, r8b
0x180009072  jmp     loc_180008E28
0x180009077  mov     dword ptr [rbp+57h+rgIndices], edi; jumptable 0000000180008F0F case 3
0x18000907a  movsd   [rbp+57h+pv], xmm7
0x18000907f  mov     eax, [rcx]
0x180009081  inc     eax
0x180009083  cmp     edi, eax
0x180009085  jg      short loc_180009099
0x180009087  lea     r8, [rbp+57h+pv]; pv
0x18000908b  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18000908f  mov     rcx, [rcx+20h]; psa
0x180009093  call    cs:__imp_SafeArrayGetElement
0x180009099  mov     edx, dword ptr [rbp+57h+pv]
0x18000909c  mov     dword ptr [rsp+100h+var_E0+8], edx
0x1800090a0  mov     r14d, 3
0x1800090a6  mov     dword ptr [rsp+100h+var_E0], r14d
0x1800090ab  mov     r8d, edx
0x1800090ae  movsd   xmm6, [rsp+100h+var_E0+8]
0x1800090b4  movzx   ecx, dl
0x1800090b7  jmp     loc_180008E28
0x1800090bc  mov     r12d, [rbx+8]
0x1800090c0  jmp     loc_180008D89
0x1800090c5  mov     [rbp+57h+rgIndices], 0; jumptable 0000000180008F83 cases 2,11
0x1800090cd  mov     word ptr [rbp+57h+rgIndices], r8w
0x1800090d2  mov     rdx, [rbp+57h+rgIndices]
0x1800090d6  mov     rcx, rsi
0x1800090d9  call    ?AddScalar@CSafeArray@@AEAAHTSA_ArrayScalar@@@Z; CSafeArray::AddScalar(SA_ArrayScalar)
0x1800090de  jmp     loc_180008E86
0x1800090e3  mov     eax, [rsi+8]
0x1800090e6  test    eax, eax
0x1800090e8  jz      loc_180008E86
0x1800090ee  add     eax, ecx
0x1800090f0  mov     [rdx], eax
0x1800090f2  mov     rcx, [rsi+20h]; psa
0x1800090f6  call    cs:__imp_SafeArrayRedim
0x1800090fc  cmp     eax, 8007000Eh
0x180009101  jz      short loc_180009162
0x180009103  test    eax, eax
0x180009105  jz      loc_180008E60
0x18000910b  mov     dword ptr [rsi+0Ch], 1
0x180009112  jmp     loc_180008E60
0x180009117  mov     dword ptr [rbp+57h+rgIndices], edi; jumptable 0000000180008F0F case 2
0x18000911a  movsd   [rbp+57h+pv], xmm7
0x18000911f  mov     eax, [rcx]
0x180009121  inc     eax
0x180009123  cmp     edi, eax
0x180009125  jg      short loc_180009139
0x180009127  lea     r8, [rbp+57h+pv]; pv
0x18000912b  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18000912f  mov     rcx, [rcx+20h]; psa
0x180009133  call    cs:__imp_SafeArrayGetElement
0x180009139  movzx   r8d, word ptr [rbp+57h+pv]
0x18000913e  mov     r14d, 2
0x180009144  mov     dword ptr [rsp+100h+var_E0], r14d
0x180009149  mov     word ptr [rsp+100h+var_E0+8], r8w
0x18000914f  mov     edx, dword ptr [rsp+100h+var_E0+8]
0x180009153  movsd   xmm6, [rsp+100h+var_E0+8]
0x180009159  movzx   ecx, r8b
0x18000915d  jmp     loc_180008E28
0x180009162  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x180009168  mov     [rbp+57h+rgIndices], 0; jumptable 0000000180008F83 case 3
0x180009170  mov     dword ptr [rbp+57h+rgIndices], edx
0x180009173  mov     rdx, [rbp+57h+rgIndices]
0x180009177  mov     rcx, rsi
0x18000917a  call    ?AddScalar@CSafeArray@@AEAAHTSA_ArrayScalar@@@Z; CSafeArray::AddScalar(SA_ArrayScalar)
0x18000917f  jmp     loc_180008E86
0x180009184  test    r15, r15; jumptable 0000000180008F83 case 13
0x180009187  jz      short loc_180009198
0x180009189  mov     rax, [r15]
0x18000918c  mov     rcx, r15
0x18000918f  mov     rax, [rax+8]
  ... truncated ...
```
