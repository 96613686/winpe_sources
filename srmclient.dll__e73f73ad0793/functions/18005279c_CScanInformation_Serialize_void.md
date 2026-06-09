# CScanInformation::Serialize(void)

- ea: `0x18005279c`
- end: `0x180052d2b`
- name: `?Serialize@CScanInformation@@AEAAXXZ`
- size: `1423`
- prototype: `void __fastcall(CScanInformation *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800501b0`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x180012210`
- `0x180016540`
- `0x18005279c`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180052b77`
- `ole32!CoTaskMemFree` at `0x180052b89`
- `ole32!CoTaskMemFree` at `0x180052b9b`
- `ole32!CoTaskMemFree` at `0x180052bad`
- `ole32!CoTaskMemFree` at `0x180052bbf`
- `ole32!CoTaskMemFree` at `0x180052bd1`
- `ole32!CoTaskMemFree` at `0x180052c12`
- `ole32!CoTaskMemFree` at `0x180052c43`
- `ole32!CoTaskMemFree` at `0x180052b77`
- `ole32!CoTaskMemFree` at `0x180052b89`
- `ole32!CoTaskMemFree` at `0x180052b9b`
- `ole32!CoTaskMemFree` at `0x180052bad`
- `ole32!CoTaskMemFree` at `0x180052bbf`
- `ole32!CoTaskMemFree` at `0x180052bd1`
- `ole32!CoTaskMemFree` at `0x180052c12`
- `ole32!CoTaskMemFree` at `0x180052c43`
- `ole32!CoTaskMemAlloc` at `0x18005285e`
- `ole32!CoTaskMemAlloc` at `0x1800528f9`
- `ole32!CoTaskMemAlloc` at `0x1800529c4`
- `ole32!CoTaskMemAlloc` at `0x18005285e`
- `ole32!CoTaskMemAlloc` at `0x1800528f9`
- `ole32!CoTaskMemAlloc` at `0x1800529c4`

## string_xrefs

- `0x1800527d8`: `base\fs\fsrm\service\pipeline\namespace.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CScanInformation::Serialize(CScanInformation *this)
{
  CScanInformation *v1; // rdi
  __int64 v2; // rax
  size_t v3; // rbx
  void *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rsi
  _QWORD *v7; // r14
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 v11; // rax
  size_t v12; // rbx
  unsigned int v13; // r13d
  __int64 v14; // r12
  __int64 v15; // rsi
  __int64 v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  size_t v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rbx
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  char v35; // al
  char Hr; // al
  char v37; // al
  int i; // [rsp+20h] [rbp-E0h]
  __int64 v39; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+78h] [rbp-88h]
  _QWORD *v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+90h] [rbp-70h]
  CScanInformation *v53; // [rsp+98h] [rbp-68h]
  __int64 v54; // [rsp+A0h] [rbp-60h]
  CScanInformation *v55; // [rsp+A8h] [rbp-58h] BYREF
  char v56; // [rsp+B0h] [rbp-50h]
  _QWORD v57[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D4h] [rbp-2Ch]
  int v60; // [rsp+D8h] [rbp-28h]
  _BYTE v61[96]; // [rsp+E0h] [rbp-20h] BYREF
  int v62; // [rsp+140h] [rbp+40h]
  void **v63; // [rsp+150h] [rbp+50h] BYREF
  int v64; // [rsp+158h] [rbp+58h]

  v1 = this;
  v53 = this;
  v50 = v57;
  v57[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
  v57[1] = L"CScanInformation::Serialize";
  v57[2] = L"NAMESPCC";
  v58 = 1059;
  v59 = 22;
  v60 = 255;
  v62 = 0x1000000;
  memset_0(v61, 0, sizeof(v61));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v63, (const struct CSrmDebugInfo *)v57, 0);
  v55 = (CScanInformation *)((char *)v1 + 72);
  CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)v1 + 72));
  v56 = 1;
  v2 = *((unsigned int *)v1 + 7);
  *((_DWORD *)v1 + 30) = v2;
  v3 = 24 * v2;
  v4 = CoTaskMemAlloc(24 * v2);
  *((_QWORD *)v1 + 16) = v4;
  if ( !v4 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x430u, Hr, 0);
  }
  v64 = 0;
  memset_0(v4, 0, v3);
  v5 = 0;
  for ( i = 0; (unsigned int)v5 < *((_DWORD *)v1 + 7); i = v5 )
  {
    v6 = 3 * v5;
    v54 = 3 * v5;
    v50 = (_QWORD *)*((_QWORD *)v1 + 16);
    v7 = v50;
    v8 = 56 * v5;
    v48 = 56 * v5;
    v49 = *((_QWORD *)v1 + 5);
    v9 = v49;
    v46 = 0;
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v46, *(const unsigned __int16 **)(*((_QWORD *)v1 + 4) + 8 * v5));
    v10 = v46;
    v46 = 0;
    v7[v6] = v10;
    v11 = *(unsigned int *)(v8 + v9);
    LODWORD(v7[v6 + 1]) = v11;
    v12 = 40 * v11;
    v7[v6 + 2] = CoTaskMemAlloc(40 * v11);
    if ( !v7[v6 + 2] )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, -2147024882);
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x440u, v35, 0);
    }
    v64 = 0;
    memset_0((void *)v7[v6 + 2], 0, v12);
    v13 = 0;
    if ( *(_DWORD *)(v8 + v9) )
    {
      do
      {
        v14 = v7[v6 + 2];
        v15 = 88LL * v13;
        v16 = *(_QWORD *)(v48 + v49 + 16);
        v45 = 0;
        v17 = v15 + v16 + 8;
        if ( *(_QWORD *)(v17 + 24) >= 8u )
          v17 = *(_QWORD *)v17;
        CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v45, (const unsigned __int16 *)v17);
        *(_DWORD *)(v14 + 40LL * v13) = *(_DWORD *)(v15 + v16);
        v18 = v45;
        v45 = 0;
        *(_QWORD *)(v14 + 40LL * v13 + 8) = v18;
        *(_QWORD *)(v14 + 40LL * v13 + 16) = *(_QWORD *)(v15 + v16 + 48);
        v19 = -1030792151 * (unsigned int)((__int64)(*(_QWORD *)(v15 + v16 + 64) - *(_QWORD *)(v15 + v16 + 56)) >> 3);
        *(_DWORD *)(v14 + 40LL * v13 + 24) = v19;
        v20 = 88 * v19;
        *(_QWORD *)(v14 + 40LL * v13 + 32) = CoTaskMemAlloc(88 * v19);
        if ( !*(_QWORD *)(v14 + 40LL * v13 + 32) )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, -2147024882);
          v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x455u, v37, 0);
        }
        v64 = 0;
        memset_0(*(void **)(v14 + 40LL * v13 + 32), 0, v20);
        v21 = *(_QWORD *)(v15 + v16 + 56);
        if ( 0x8F5C28F5C28F5C29uLL * ((*(_QWORD *)(v15 + v16 + 64) - v21) >> 3) )
        {
          v22 = 0;
          v47 = 0;
          do
          {
            v51 = 88LL * (unsigned int)v22;
            v52 = *(_QWORD *)(v14 + 40LL * v13 + 32);
            v23 = v21 + 200 * v22;
            v44 = 0;
            v43 = 0;
            v42 = 0;
            v41 = 0;
            v40 = 0;
            v39 = 0;
            if ( *(_QWORD *)(v23 + 24) < 8u )
              v24 = (const unsigned __int16 *)(v21 + 200 * v22);
            else
              v24 = *(const unsigned __int16 **)v23;
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v44, v24);
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v43, *(const unsigned __int16 **)(v23 + 40));
            v25 = (const unsigned __int16 *)(v23 + 56);
            if ( *(_QWORD *)(v23 + 80) >= 8u )
              v25 = *(const unsigned __int16 **)v25;
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v42, v25);
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v41, *(const unsigned __int16 **)(v23 + 96));
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v40, *(const unsigned __int16 **)(v23 + 104));
            v26 = (const unsigned __int16 *)(v23 + 152);
            if ( *(_QWORD *)(v23 + 176) >= 8u )
              v26 = *(const unsigned __int16 **)v26;
            CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v39, v26);
            v27 = v44;
            v44 = 0;
            v28 = v51;
            v29 = v52;
            *(_QWORD *)(v51 + v52) = v27;
            v30 = v43;
            v43 = 0;
            *(_QWORD *)(v28 + v29 + 8) = v30;
            v31 = v42;
            v42 = 0;
            *(_QWORD *)(v28 + v29 + 16) = v31;
            v32 = v41;
            v41 = 0;
            *(_QWORD *)(v28 + v29 + 24) = v32;
            v33 = v40;
            v40 = 0;
            *(_QWORD *)(v28 + v29 + 32) = v33;
            *(_OWORD *)(v28 + v29 + 40) = *(_OWORD *)(v23 + 112);
            *(_OWORD *)(v28 + v29 + 56) = *(_OWORD *)(v23 + 128);
            *(_DWORD *)(v28 + v29 + 72) = *(_DWORD *)(v23 + 144);
            *(_DWORD *)(v28 + v29 + 76) = *(_DWORD *)(v23 + 192);
            v34 = v39;
            v39 = 0;
            *(_QWORD *)(v28 + v29 + 80) = v34;
            CoTaskMemFree(0);
            v39 = 0;
            CoTaskMemFree(0);
            v40 = 0;
            CoTaskMemFree(0);
            v41 = 0;
            CoTaskMemFree(0);
            v42 = 0;
            CoTaskMemFree(0);
            v43 = 0;
            CoTaskMemFree(0);
            v44 = 0;
            v22 = v47 + 1;
            v47 = v22;
            v21 = *(_QWORD *)(v15 + v16 + 56);
          }
          while ( v22 < 0x8F5C28F5C28F5C29uLL * ((*(_QWORD *)(v15 + v16 + 64) - v21) >> 3) );
          v1 = v53;
        }
        CoTaskMemFree(0);
        v45 = 0;
        ++v13;
        v6 = v54;
        v7 = v50;
      }
      while ( v13 < *(_DWORD *)(v48 + v49) );
    }
    CoTaskMemFree(0);
    v46 = 0;
    v5 = (unsigned int)(i + 1);
  }
  CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v55);
  v63 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v63);
}

```

## disassembly

```asm
0x18005279c  push    rbp
0x18005279e  push    rbx
0x18005279f  push    rsi
0x1800527a0  push    rdi
0x1800527a1  push    r12
0x1800527a3  push    r13
0x1800527a5  push    r14
0x1800527a7  push    r15
0x1800527a9  lea     rbp, [rsp-118h]
0x1800527b1  sub     rsp, 218h
0x1800527b8  mov     rax, cs:__security_cookie
0x1800527bf  xor     rax, rsp
0x1800527c2  mov     [rbp+150h+var_50], rax
0x1800527c9  mov     rdi, rcx
0x1800527cc  mov     [rbp+150h+var_1B8], rcx
0x1800527d0  lea     rax, [rbp+150h+var_198]
0x1800527d4  mov     [rbp+150h+var_1D0], rax
0x1800527d8  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x1800527df  mov     [rbp+150h+var_198], rax
0x1800527e3  lea     rax, aCscaninformati_2; "CScanInformation::Serialize"
0x1800527ea  mov     [rbp+150h+var_190], rax
0x1800527ee  lea     rax, aNamespcc; "NAMESPCC"
0x1800527f5  mov     [rbp+150h+var_188], rax
0x1800527f9  mov     [rbp+150h+var_180], 423h
0x180052800  mov     [rbp+150h+var_17C], 16h
0x180052807  mov     [rbp+150h+var_178], 0FFh
0x18005280e  xor     esi, esi
0x180052810  mov     [rbp+150h+var_110], 1000000h
0x180052817  xor     edx, edx; Val
0x180052819  lea     r8d, [rsi+60h]; Size
0x18005281d  lea     rcx, [rbp+150h+var_170]; void *
0x180052821  call    memset_0
0x180052826  nop
0x180052827  xor     r8d, r8d
0x18005282a  lea     rdx, [rbp+150h+var_198]
0x18005282e  lea     rcx, [rbp+150h+var_100]
0x180052832  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180052837  nop
0x180052838  lea     rcx, [rdi+48h]; lpCriticalSection
0x18005283c  mov     [rbp+150h+var_1A8], rcx
0x180052840  mov     [rbp+150h+var_1A0], sil
0x180052844  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x180052849  mov     [rbp+150h+var_1A0], 1
0x18005284d  mov     eax, [rdi+1Ch]
0x180052850  mov     [rdi+78h], eax
0x180052853  lea     rbx, [rax+rax*2]
0x180052857  shl     rbx, 3
0x18005285b  mov     rcx, rbx; cb
0x18005285e  call    cs:__imp_CoTaskMemAlloc
0x180052864  mov     [rdi+80h], rax
0x18005286b  mov     ecx, [rbp+150h+var_F8]
0x18005286e  mov     [rbp+150h+var_F8], ecx
0x180052871  test    rax, rax
0x180052874  jz      loc_180052CD3
0x18005287a  mov     [rbp+150h+var_F8], esi
0x18005287d  mov     r8, rbx; Size
0x180052880  xor     edx, edx; Val
0x180052882  mov     rcx, rax; void *
0x180052885  call    memset_0
0x18005288a  xor     ebx, ebx
0x18005288c  mov     eax, ebx
0x18005288e  mov     [rsp+250h+var_230], eax
0x180052892  cmp     [rdi+1Ch], ebx
0x180052895  jbe     loc_180052C66
0x18005289b  lea     rsi, [rax+rax*2]
0x18005289f  mov     [rbp+150h+var_1B0], rsi
0x1800528a3  mov     r14, [rdi+80h]
0x1800528aa  mov     [rbp+150h+var_1D0], r14
0x1800528ae  imul    r15, rax, 38h ; '8'
0x1800528b2  mov     [rsp+250h+var_1E0], r15
0x1800528b7  mov     r12, [rdi+28h]
0x1800528bb  mov     [rsp+250h+var_1D8], r12
0x1800528c0  mov     [rsp+250h+var_1F0], rbx
0x1800528c5  mov     rdx, [rdi+20h]
0x1800528c9  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x1800528cd  lea     rcx, [rsp+250h+var_1F0]; this
0x1800528d2  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x1800528d7  mov     rax, [rsp+250h+var_1F0]
0x1800528dc  mov     [rsp+250h+var_1F0], rbx
0x1800528e1  mov     [r14+rsi*8], rax
0x1800528e5  mov     eax, [r15+r12]
0x1800528e9  mov     [r14+rsi*8+8], eax
0x1800528ee  lea     rbx, [rax+rax*4]
0x1800528f2  shl     rbx, 3
0x1800528f6  mov     rcx, rbx; cb
0x1800528f9  call    cs:__imp_CoTaskMemAlloc
0x1800528ff  mov     [r14+rsi*8+10h], rax
0x180052904  mov     eax, [rbp+150h+var_F8]
0x180052907  mov     [rbp+150h+var_F8], eax
0x18005290a  xor     r8d, r8d
0x18005290d  cmp     [r14+rsi*8+10h], r8
0x180052912  jz      loc_180052CA7
0x180052918  mov     [rbp+150h+var_F8], r8d
0x18005291c  mov     r8, rbx; Size
0x18005291f  xor     edx, edx; Val
0x180052921  mov     rcx, [r14+rsi*8+10h]; void *
0x180052926  call    memset_0
0x18005292b  xor     ebx, ebx
0x18005292d  mov     r13d, ebx
0x180052930  cmp     [r15+r12], ebx
0x180052934  jbe     loc_180052C41
0x18005293a  mov     eax, r13d
0x18005293d  lea     r15, [rax+rax*4]
0x180052941  mov     r12, [r14+rsi*8+10h]
0x180052946  imul    rsi, rax, 58h ; 'X'
0x18005294a  mov     r14, [rsp+250h+var_1E0]
0x18005294f  mov     rax, [rsp+250h+var_1D8]
0x180052954  mov     r14, [r14+rax+10h]
0x180052959  mov     [rsp+250h+var_1F8], rbx
0x18005295e  lea     rdx, [r14+8]
0x180052962  add     rdx, rsi
0x180052965  cmp     qword ptr [rdx+18h], 8
0x18005296a  jb      short loc_18005296F
0x18005296c  mov     rdx, [rdx]; unsigned __int16 *
0x18005296f  lea     rcx, [rsp+250h+var_1F8]; this
0x180052974  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052979  mov     eax, [rsi+r14]
0x18005297d  mov     [r12+r15*8], eax
0x180052981  mov     rax, [rsp+250h+var_1F8]
0x180052986  mov     [rsp+250h+var_1F8], rbx
0x18005298b  mov     [r12+r15*8+8], rax
0x180052990  mov     rax, [rsi+r14+30h]
0x180052995  mov     [r12+r15*8+10h], rax
0x18005299a  mov     rax, [rsi+r14+40h]
0x18005299f  sub     rax, [rsi+r14+38h]
0x1800529a4  sar     rax, 3
0x1800529a8  mov     rcx, 8F5C28F5C28F5C29h
0x1800529b2  imul    rax, rcx
0x1800529b6  mov     eax, eax
0x1800529b8  mov     [r12+r15*8+18h], eax
0x1800529bd  imul    rbx, rax, 58h ; 'X'
0x1800529c1  mov     rcx, rbx; cb
0x1800529c4  call    cs:__imp_CoTaskMemAlloc
0x1800529ca  mov     [r12+r15*8+20h], rax
0x1800529cf  mov     eax, [rbp+150h+var_F8]
0x1800529d2  mov     [rbp+150h+var_F8], eax
0x1800529d5  xor     r8d, r8d
0x1800529d8  cmp     [r12+r15*8+20h], r8
0x1800529dd  jz      loc_180052CFF
0x1800529e3  mov     [rbp+150h+var_F8], r8d
0x1800529e7  mov     r8, rbx; Size
0x1800529ea  xor     edx, edx; Val
0x1800529ec  mov     rcx, [r12+r15*8+20h]; void *
0x1800529f1  call    memset_0
0x1800529f6  mov     rcx, [rsi+r14+38h]
0x1800529fb  mov     rax, [rsi+r14+40h]
0x180052a00  sub     rax, rcx
0x180052a03  sar     rax, 3
0x180052a07  mov     rdx, 8F5C28F5C28F5C29h
0x180052a11  imul    rax, rdx
0x180052a15  xor     ebx, ebx
0x180052a17  test    rax, rax
0x180052a1a  jz      loc_180052C10
0x180052a20  mov     edx, ebx
0x180052a22  mov     [rsp+250h+var_1E8], rbx
0x180052a27  mov     rdi, 8F5C28F5C28F5C29h
0x180052a31  mov     eax, edx
0x180052a33  imul    r8, rax, 58h ; 'X'
0x180052a37  mov     [rbp+150h+var_1C8], r8
0x180052a3b  mov     rax, [r12+r15*8+20h]
0x180052a40  mov     [rbp+150h+var_1C0], rax
0x180052a44  imul    rbx, rdx, 0C8h
0x180052a4b  add     rbx, rcx
0x180052a4e  xor     eax, eax
0x180052a50  mov     [rsp+250h+var_200], rax
0x180052a55  mov     [rsp+250h+var_208], rax
0x180052a5a  mov     [rsp+250h+var_210], rax
0x180052a5f  mov     [rsp+250h+var_218], rax
0x180052a64  mov     [rsp+250h+var_220], rax
0x180052a69  mov     [rsp+250h+var_228], rax
0x180052a6e  cmp     qword ptr [rbx+18h], 8
0x180052a73  jb      short loc_180052A7A
0x180052a75  mov     rdx, [rbx]
0x180052a78  jmp     short loc_180052A7D
0x180052a7a  mov     rdx, rbx; unsigned __int16 *
0x180052a7d  lea     rcx, [rsp+250h+var_200]; this
0x180052a82  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052a87  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180052a8b  lea     rcx, [rsp+250h+var_208]; this
0x180052a90  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052a95  lea     rdx, [rbx+38h]
0x180052a99  cmp     qword ptr [rdx+18h], 8
0x180052a9e  jb      short loc_180052AA3
0x180052aa0  mov     rdx, [rdx]; unsigned __int16 *
0x180052aa3  lea     rcx, [rsp+250h+var_210]; this
0x180052aa8  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052aad  mov     rdx, [rbx+60h]; unsigned __int16 *
0x180052ab1  lea     rcx, [rsp+250h+var_218]; this
0x180052ab6  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052abb  mov     rdx, [rbx+68h]; unsigned __int16 *
0x180052abf  lea     rcx, [rsp+250h+var_220]; this
0x180052ac4  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052ac9  lea     rdx, [rbx+98h]
0x180052ad0  cmp     qword ptr [rdx+18h], 8
0x180052ad5  jb      short loc_180052ADA
0x180052ad7  mov     rdx, [rdx]; unsigned __int16 *
0x180052ada  lea     rcx, [rsp+250h+var_228]; this
0x180052adf  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180052ae4  mov     rax, [rsp+250h+var_200]
0x180052ae9  xor     r8d, r8d
0x180052aec  mov     [rsp+250h+var_200], r8
0x180052af1  mov     rcx, [rbp+150h+var_1C8]
0x180052af5  mov     rdx, [rbp+150h+var_1C0]
0x180052af9  mov     [rcx+rdx], rax
0x180052afd  mov     rax, [rsp+250h+var_208]
0x180052b02  mov     [rsp+250h+var_208], r8
0x180052b07  mov     [rcx+rdx+8], rax
0x180052b0c  mov     rax, [rsp+250h+var_210]
0x180052b11  mov     [rsp+250h+var_210], r8
0x180052b16  mov     [rcx+rdx+10h], rax
0x180052b1b  mov     rax, [rsp+250h+var_218]
0x180052b20  mov     [rsp+250h+var_218], r8
0x180052b25  mov     [rcx+rdx+18h], rax
0x180052b2a  mov     rax, [rsp+250h+var_220]
0x180052b2f  mov     [rsp+250h+var_220], r8
0x180052b34  mov     [rcx+rdx+20h], rax
0x180052b39  movups  xmm0, xmmword ptr [rbx+70h]
0x180052b3d  movdqu  xmmword ptr [rcx+rdx+28h], xmm0
0x180052b43  movups  xmm1, xmmword ptr [rbx+80h]
0x180052b4a  movdqu  xmmword ptr [rcx+rdx+38h], xmm1
0x180052b50  mov     eax, [rbx+90h]
0x180052b56  mov     [rcx+rdx+48h], eax
0x180052b5a  mov     eax, [rbx+0C0h]
0x180052b60  mov     [rcx+rdx+4Ch], eax
0x180052b64  mov     rax, [rsp+250h+var_228]
0x180052b69  xor     ebx, ebx
0x180052b6b  mov     [rsp+250h+var_228], rbx
0x180052b70  mov     [rcx+rdx+50h], rax
0x180052b75  xor     ecx, ecx; pv
0x180052b77  call    cs:__imp_CoTaskMemFree
0x180052b7d  mov     [rsp+250h+var_228], rbx
0x180052b82  mov     [rsp+250h+var_228], rbx
0x180052b87  xor     ecx, ecx; pv
0x180052b89  call    cs:__imp_CoTaskMemFree
0x180052b8f  mov     [rsp+250h+var_220], rbx
0x180052b94  mov     [rsp+250h+var_220], rbx
0x180052b99  xor     ecx, ecx; pv
0x180052b9b  call    cs:__imp_CoTaskMemFree
0x180052ba1  mov     [rsp+250h+var_218], rbx
0x180052ba6  mov     [rsp+250h+var_218], rbx
0x180052bab  xor     ecx, ecx; pv
0x180052bad  call    cs:__imp_CoTaskMemFree
0x180052bb3  mov     [rsp+250h+var_210], rbx
0x180052bb8  mov     [rsp+250h+var_210], rbx
0x180052bbd  xor     ecx, ecx; pv
0x180052bbf  call    cs:__imp_CoTaskMemFree
0x180052bc5  mov     [rsp+250h+var_208], rbx
0x180052bca  mov     [rsp+250h+var_208], rbx
0x180052bcf  xor     ecx, ecx; pv
0x180052bd1  call    cs:__imp_CoTaskMemFree
0x180052bd7  mov     [rsp+250h+var_200], rbx
0x180052bdc  mov     [rsp+250h+var_200], rbx
0x180052be1  mov     rdx, [rsp+250h+var_1E8]
0x180052be6  inc     rdx
0x180052be9  mov     [rsp+250h+var_1E8], rdx
0x180052bee  mov     rcx, [rsi+r14+38h]
0x180052bf3  mov     rax, [rsi+r14+40h]
0x180052bf8  sub     rax, rcx
0x180052bfb  sar     rax, 3
0x180052bff  imul    rax, rdi
0x180052c03  cmp     rdx, rax
0x180052c06  jb      loc_180052A31
0x180052c0c  mov     rdi, [rbp+150h+var_1B8]
0x180052c10  xor     ecx, ecx; pv
0x180052c12  call    cs:__imp_CoTaskMemFree
0x180052c18  mov     [rsp+250h+var_1F8], rbx
0x180052c1d  mov     [rsp+250h+var_1F8], rbx
0x180052c22  inc     r13d
0x180052c25  mov     rax, [rsp+250h+var_1E0]
0x180052c2a  mov     rcx, [rsp+250h+var_1D8]
0x180052c2f  cmp     r13d, [rax+rcx]
0x180052c33  mov     rsi, [rbp+150h+var_1B0]
0x180052c37  mov     r14, [rbp+150h+var_1D0]
0x180052c3b  jb      loc_18005293A
0x180052c41  xor     ecx, ecx; pv
0x180052c43  call    cs:__imp_CoTaskMemFree
0x180052c49  mov     [rsp+250h+var_1F0], rbx
0x180052c4e  mov     [rsp+250h+var_1F0], rbx
0x180052c53  mov     eax, [rsp+250h+var_230]
0x180052c57  inc     eax
0x180052c59  mov     [rsp+250h+var_230], eax
0x180052c5d  cmp     eax, [rdi+1Ch]
0x180052c60  jb      loc_18005289B
0x180052c66  lea     rcx, [rbp+150h+var_1A8]; this
0x180052c6a  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x180052c6f  nop
0x180052c70  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180052c77  mov     [rbp+150h+var_100], rax
0x180052c7b  lea     rcx, [rbp+150h+var_100]; this
0x180052c7f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180052c84  mov     rcx, [rbp+150h+var_50]
0x180052c8b  xor     rcx, rsp; StackCookie
0x180052c8e  call    __security_check_cookie
0x180052c93  add     rsp, 218h
0x180052c9a  pop     r15
0x180052c9c  pop     r14
0x180052c9e  pop     r13
0x180052ca0  pop     r12
0x180052ca2  pop     rdi
0x180052ca3  pop     rsi
  ... truncated ...
```
