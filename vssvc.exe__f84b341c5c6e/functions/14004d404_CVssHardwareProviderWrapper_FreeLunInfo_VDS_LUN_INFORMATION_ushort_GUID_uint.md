# CVssHardwareProviderWrapper::FreeLunInfo(_VDS_LUN_INFORMATION *,ushort * *,_GUID *,uint)

- ea: `0x14004d404`
- end: `0x14004d5ed`
- name: `?FreeLunInfo@CVssHardwareProviderWrapper@@CAXPEAU_VDS_LUN_INFORMATION@@PEAPEAGPEAU_GUID@@I@Z`
- size: `489`
- prototype: `void __fastcall(struct _VDS_LUN_INFORMATION *pv, unsigned __int16 **, struct _GUID *, unsigned int)`
- caller_count: `17`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c618`
- `0x14004ca84`
- `0x14004ceb0`
- `0x14004d814`
- `0x1400514c0`
- `0x140051a40`
- `0x1400b6804`
- `0x1400b93e4`
- `0x1400ba328`
- `0x1400bac8c`
- `0x1400bb520`
- `0x1400be544`
- `0x1400c5ef0`
- `0x1400c98c0`
- `0x1400c9d34`
- `0x1400ca888`
- `0x1400cb0f0`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x14004d404`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d5c3`

## pseudocode

```c
void __fastcall CVssHardwareProviderWrapper::FreeLunInfo(
        struct _VDS_LUN_INFORMATION *pv,
        unsigned __int16 **a2,
        struct _GUID *a3,
        unsigned int a4)
{
  struct _GUID *v5; // rbx
  __int64 v8; // r14
  struct _VDS_LUN_INFORMATION *v9; // rbx
  char *m_szVendorId; // rcx
  char *m_szProductId; // rcx
  char *m_szProductRevision; // rcx
  char *m_szSerialNumber; // rcx
  ULONG m_cIdentifiers; // r13d
  ULONG v15; // esi
  VDS_STORAGE_IDENTIFIER *i; // rdi
  BYTE *m_rgbIdentifier; // rcx
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // rcx
  VDS_INTERCONNECT *m_rgInterconnects; // rdi
  ULONG j; // esi
  BYTE *m_pbAddress; // rcx
  BYTE *m_pbPort; // rcx
  VDS_INTERCONNECT *v23; // rcx
  _QWORD v24[3]; // [rsp+28h] [rbp-E0h] BYREF
  int v25; // [rsp+40h] [rbp-C8h]
  int v26; // [rsp+44h] [rbp-C4h]
  int v27; // [rsp+48h] [rbp-C0h]
  char v28[120]; // [rsp+50h] [rbp-B8h] BYREF
  int v29; // [rsp+C8h] [rbp-40h]
  LPVOID v30[20]; // [rsp+D8h] [rbp-30h] BYREF

  v25 = 1564;
  v24[0] = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v26 = 1;
  v27 = 255;
  v24[1] = L"CVssHardwareProviderWrapper::FreeLunInfo";
  v5 = a3;
  v29 = 0x1000000;
  v24[2] = L"CORHWUTC";
  memset_0(v28, 0, sizeof(v28));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v30, (__int64)v24, 0);
  if ( a4 )
  {
    v8 = 0;
    if ( !pv )
      goto LABEL_32;
    do
    {
      v9 = &pv[v8];
      if ( a2 )
        CoTaskMemFree(a2[v8]);
      if ( v9 )
      {
        m_szVendorId = v9->m_szVendorId;
        if ( m_szVendorId )
          CoTaskMemFree(m_szVendorId);
        m_szProductId = v9->m_szProductId;
        if ( m_szProductId )
          CoTaskMemFree(m_szProductId);
        m_szProductRevision = v9->m_szProductRevision;
        if ( m_szProductRevision )
          CoTaskMemFree(m_szProductRevision);
        m_szSerialNumber = v9->m_szSerialNumber;
        if ( m_szSerialNumber )
          CoTaskMemFree(m_szSerialNumber);
        m_cIdentifiers = v9->m_deviceIdDescriptor.m_cIdentifiers;
        v15 = 0;
        for ( i = v9->m_deviceIdDescriptor.m_rgIdentifiers; v15 < m_cIdentifiers; ++i )
        {
          m_rgbIdentifier = i->m_rgbIdentifier;
          if ( m_rgbIdentifier )
            CoTaskMemFree(m_rgbIdentifier);
          ++v15;
        }
        m_rgIdentifiers = v9->m_deviceIdDescriptor.m_rgIdentifiers;
        if ( m_rgIdentifiers )
          CoTaskMemFree(m_rgIdentifiers);
        m_rgInterconnects = v9->m_rgInterconnects;
        for ( j = 0; j < v9->m_cInterconnects; ++m_rgInterconnects )
        {
          m_pbAddress = m_rgInterconnects->m_pbAddress;
          if ( m_pbAddress )
            CoTaskMemFree(m_pbAddress);
          m_pbPort = m_rgInterconnects->m_pbPort;
          if ( m_pbPort )
            CoTaskMemFree(m_pbPort);
          ++j;
        }
        v23 = v9->m_rgInterconnects;
        if ( v23 )
          CoTaskMemFree(v23);
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < a4 );
    v5 = a3;
  }
  if ( pv )
    CoTaskMemFree(pv);
LABEL_32:
  if ( a2 )
    CoTaskMemFree(a2);
  if ( v5 )
    CoTaskMemFree(v5);
  CVssFunctionTracer::~CVssFunctionTracer(v30);
}

```

## disassembly

```asm
0x14004d404  mov     rax, rsp
0x14004d407  mov     [rax+8], rbx
0x14004d40b  mov     [rax+20h], r9d
0x14004d40f  mov     [rax+18h], r8
0x14004d413  push    rbp
0x14004d414  push    rsi
0x14004d415  push    rdi
0x14004d416  push    r12
0x14004d418  push    r13
0x14004d41a  push    r14
0x14004d41c  push    r15
0x14004d41e  lea     rbp, [rax-78h]
0x14004d422  sub     rsp, 140h
0x14004d429  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004d430  mov     [rsp+170h+var_138], 61Ch
0x14004d438  mov     [rsp+170h+var_150], rax
0x14004d43d  mov     r12, rdx
0x14004d440  xor     edx, edx; Val
0x14004d442  mov     [rsp+170h+var_134], 1
0x14004d44a  lea     rax, aCvsshardwarepr_190; "CVssHardwareProviderWrapper::FreeLunInf"...
0x14004d451  mov     [rsp+170h+var_130], 0FFh
0x14004d459  mov     [rsp+170h+var_148], rax
0x14004d45e  mov     rbx, r8
0x14004d461  lea     rax, aCorhwutc; "CORHWUTC"
0x14004d468  mov     [rbp+70h+var_B0], 1000000h
0x14004d46f  mov     r15, rcx
0x14004d472  mov     qword ptr [rsp+170h+var_140], rax
0x14004d477  lea     r8d, [rdx+78h]; Size
0x14004d47b  mov     r14d, r9d
0x14004d47e  lea     rcx, [rsp+170h+var_128]; void *
0x14004d483  call    memset_0
0x14004d488  xor     r8d, r8d
0x14004d48b  lea     rdx, [rsp+170h+var_150]
0x14004d490  lea     rcx, [rbp+70h+var_A0]
0x14004d494  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14004d499  test    r14d, r14d
0x14004d49c  jz      loc_14004D59F
0x14004d4a2  xor     r14d, r14d
0x14004d4a5  test    r15, r15
0x14004d4a8  jz      loc_14004D5AD
0x14004d4ae  lea     rbx, [r14+r14*2]
0x14004d4b2  shl     rbx, 5
0x14004d4b6  add     rbx, r15
0x14004d4b9  test    r12, r12
0x14004d4bc  jz      short loc_14004D4C8
0x14004d4be  mov     rcx, [r12+r14*8]; pv
0x14004d4c2  call    cs:__imp_CoTaskMemFree
0x14004d4c8  test    rbx, rbx
0x14004d4cb  jz      loc_14004D588
0x14004d4d1  mov     rcx, [rbx+10h]; pv
0x14004d4d5  test    rcx, rcx
0x14004d4d8  jz      short loc_14004D4E0
0x14004d4da  call    cs:__imp_CoTaskMemFree
0x14004d4e0  mov     rcx, [rbx+18h]; pv
0x14004d4e4  test    rcx, rcx
0x14004d4e7  jz      short loc_14004D4EF
0x14004d4e9  call    cs:__imp_CoTaskMemFree
0x14004d4ef  mov     rcx, [rbx+20h]; pv
0x14004d4f3  test    rcx, rcx
0x14004d4f6  jz      short loc_14004D4FE
0x14004d4f8  call    cs:__imp_CoTaskMemFree
0x14004d4fe  mov     rcx, [rbx+28h]; pv
0x14004d502  test    rcx, rcx
0x14004d505  jz      short loc_14004D50D
0x14004d507  call    cs:__imp_CoTaskMemFree
0x14004d50d  mov     r13d, [rbx+44h]
0x14004d511  xor     esi, esi
0x14004d513  mov     rdi, [rbx+48h]
0x14004d517  test    r13d, r13d
0x14004d51a  jz      short loc_14004D536
0x14004d51c  mov     rcx, [rdi+10h]; pv
0x14004d520  test    rcx, rcx
0x14004d523  jz      short loc_14004D52B
0x14004d525  call    cs:__imp_CoTaskMemFree
0x14004d52b  inc     esi
0x14004d52d  add     rdi, 18h
0x14004d531  cmp     esi, r13d
0x14004d534  jb      short loc_14004D51C
0x14004d536  mov     rcx, [rbx+48h]; pv
0x14004d53a  test    rcx, rcx
0x14004d53d  jz      short loc_14004D545
0x14004d53f  call    cs:__imp_CoTaskMemFree
0x14004d545  mov     rdi, [rbx+58h]
0x14004d549  xor     esi, esi
0x14004d54b  cmp     [rbx+50h], esi
0x14004d54e  jbe     short loc_14004D579
0x14004d550  mov     rcx, [rdi+18h]; pv
0x14004d554  test    rcx, rcx
0x14004d557  jz      short loc_14004D55F
0x14004d559  call    cs:__imp_CoTaskMemFree
0x14004d55f  mov     rcx, [rdi+8]; pv
0x14004d563  test    rcx, rcx
0x14004d566  jz      short loc_14004D56E
0x14004d568  call    cs:__imp_CoTaskMemFree
0x14004d56e  inc     esi
0x14004d570  add     rdi, 20h ; ' '
0x14004d574  cmp     esi, [rbx+50h]
0x14004d577  jb      short loc_14004D550
0x14004d579  mov     rcx, [rbx+58h]; pv
0x14004d57d  test    rcx, rcx
0x14004d580  jz      short loc_14004D588
0x14004d582  call    cs:__imp_CoTaskMemFree
0x14004d588  inc     r14d
0x14004d58b  cmp     r14d, [rbp+70h+arg_18]
0x14004d592  jb      loc_14004D4AE
0x14004d598  mov     rbx, [rbp+70h+arg_10]
0x14004d59f  test    r15, r15
0x14004d5a2  jz      short loc_14004D5AD
0x14004d5a4  mov     rcx, r15; pv
0x14004d5a7  call    cs:__imp_CoTaskMemFree
0x14004d5ad  test    r12, r12
0x14004d5b0  jz      short loc_14004D5BB
0x14004d5b2  mov     rcx, r12; pv
0x14004d5b5  call    cs:__imp_CoTaskMemFree
0x14004d5bb  test    rbx, rbx
0x14004d5be  jz      short loc_14004D5C9
0x14004d5c0  mov     rcx, rbx; pv
0x14004d5c3  call    cs:__imp_CoTaskMemFree
0x14004d5c9  lea     rcx, [rbp+70h+var_A0]; this
0x14004d5cd  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14004d5d2  mov     rbx, [rsp+170h+arg_0]
0x14004d5da  add     rsp, 140h
0x14004d5e1  pop     r15
0x14004d5e3  pop     r14
0x14004d5e5  pop     r13
0x14004d5e7  pop     r12
0x14004d5e9  pop     rdi
0x14004d5ea  pop     rsi
0x14004d5eb  pop     rbp
0x14004d5ec  retn
```
