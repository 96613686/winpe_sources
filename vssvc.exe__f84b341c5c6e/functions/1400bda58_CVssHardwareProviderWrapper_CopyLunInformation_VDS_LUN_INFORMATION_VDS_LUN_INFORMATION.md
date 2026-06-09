# CVssHardwareProviderWrapper::CopyLunInformation(_VDS_LUN_INFORMATION * *,_VDS_LUN_INFORMATION *)

- ea: `0x1400bda58`
- end: `0x1400bdeec`
- name: `?CopyLunInformation@CVssHardwareProviderWrapper@@AEAAXPEAPEAU_VDS_LUN_INFORMATION@@PEAU2@@Z`
- size: `1172`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this, struct _VDS_LUN_INFORMATION **, struct _VDS_LUN_INFORMATION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400b93e4`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x1400921dc`
- `0x1400bd8b8`
- `0x1400bda58`
- `0x1400cdee8`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdbb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdc52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdcf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdd92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bddc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdbb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdc52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdcf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bdd92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400bddc9`

## string_xrefs

- `0x1400bda88`: `CVssHardwareProviderWrapper::CopyLunInformation`
- `0x1400bdc8e`: `CVssHardwareProviderWrapper::CopyLunInformation`
- `0x1400bdd10`: `CVssHardwareProviderWrapper::CopyLunInformation`
- `0x1400bde03`: `CVssHardwareProviderWrapper::CopyLunInformation`
- `0x1400bde65`: `CVssHardwareProviderWrapper::CopyLunInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssHardwareProviderWrapper::CopyLunInformation(
        CVssHardwareProviderWrapper *this,
        struct _VDS_LUN_INFORMATION **a2,
        struct _VDS_LUN_INFORMATION *a3)
{
  struct _VDS_LUN_INFORMATION *v5; // rax
  CVssHardwareProviderWrapper *v6; // rcx
  struct _VDS_LUN_INFORMATION *v7; // rbx
  CVssHardwareProviderWrapper *v8; // rcx
  CVssHardwareProviderWrapper *v9; // rcx
  CVssHardwareProviderWrapper *v10; // rcx
  __int64 m_cIdentifiers; // rax
  VDS_STORAGE_IDENTIFIER *v12; // rax
  __int64 i; // r14
  __int64 v14; // rdi
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // r15
  SIZE_T m_cbIdentifier; // rcx
  BYTE *v17; // rax
  VDS_INTERCONNECT *v18; // rax
  ULONG j; // r15d
  unsigned __int64 v20; // rdi
  VDS_INTERCONNECT *m_rgInterconnects; // r14
  SIZE_T m_cbPort; // rcx
  BYTE *v23; // rax
  SIZE_T m_cbAddress; // rcx
  BYTE *v25; // rax
  const unsigned __int16 *v26; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v27; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  int v30; // [rsp+3Ch] [rbp-C4h]
  int v31; // [rsp+40h] [rbp-C0h]
  _BYTE v32[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+C0h] [rbp-40h]
  LPVOID v34[14]; // [rsp+D0h] [rbp-30h] BYREF

  v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
  v28 = L"CORHWUTC";
  v29 = 1640;
  v30 = 1;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v34, (__int64)&v26, 0);
  v5 = (struct _VDS_LUN_INFORMATION *)CoTaskMemAlloc(0x60u);
  v7 = v5;
  if ( !v5 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
    v28 = L"CORHWUTC";
    v29 = 1648;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
  }
  *(_OWORD *)&v5->m_version = *(_OWORD *)&a3->m_version;
  *(_OWORD *)&v5->m_szVendorId = *(_OWORD *)&a3->m_szVendorId;
  *(_OWORD *)&v5->m_szProductRevision = *(_OWORD *)&a3->m_szProductRevision;
  v5->m_diskSignature = a3->m_diskSignature;
  v5->m_deviceIdDescriptor = a3->m_deviceIdDescriptor;
  *(_OWORD *)&v5->m_cInterconnects = *(_OWORD *)&a3->m_cInterconnects;
  CVssHardwareProviderWrapper::CopyLunInfoString(v6, &v5->m_szVendorId, a3->m_szVendorId);
  CVssHardwareProviderWrapper::CopyLunInfoString(v8, &v7->m_szProductId, a3->m_szProductId);
  CVssHardwareProviderWrapper::CopyLunInfoString(v9, &v7->m_szProductRevision, a3->m_szProductRevision);
  CVssHardwareProviderWrapper::CopyLunInfoString(v10, &v7->m_szSerialNumber, a3->m_szSerialNumber);
  v7->m_deviceIdDescriptor.m_version = a3->m_deviceIdDescriptor.m_version;
  m_cIdentifiers = a3->m_deviceIdDescriptor.m_cIdentifiers;
  v7->m_deviceIdDescriptor.m_cIdentifiers = m_cIdentifiers;
  v12 = (VDS_STORAGE_IDENTIFIER *)CoTaskMemAlloc(24 * m_cIdentifiers);
  v7->m_deviceIdDescriptor.m_rgIdentifiers = v12;
  if ( !v12 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
    v28 = L"CORHWUTC";
    v29 = 1668;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
  }
  for ( i = 0; (unsigned int)i < v7->m_deviceIdDescriptor.m_cIdentifiers; i = (unsigned int)(i + 1) )
  {
    v14 = i;
    m_rgIdentifiers = v7->m_deviceIdDescriptor.m_rgIdentifiers;
    m_rgIdentifiers[v14].m_CodeSet = a3->m_deviceIdDescriptor.m_rgIdentifiers[i].m_CodeSet;
    m_rgIdentifiers[v14].m_Type = a3->m_deviceIdDescriptor.m_rgIdentifiers[i].m_Type;
    m_cbIdentifier = a3->m_deviceIdDescriptor.m_rgIdentifiers[i].m_cbIdentifier;
    m_rgIdentifiers[v14].m_cbIdentifier = m_cbIdentifier;
    v17 = (BYTE *)CoTaskMemAlloc(m_cbIdentifier);
    m_rgIdentifiers[i].m_rgbIdentifier = v17;
    if ( !v17 )
    {
      v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
      v28 = L"CORHWUTC";
      v29 = 1683;
      v30 = 1;
      v31 = 255;
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
    }
    memcpy_0(v17, a3->m_deviceIdDescriptor.m_rgIdentifiers[i].m_rgbIdentifier, m_rgIdentifiers[i].m_cbIdentifier);
  }
  if ( v7->m_cInterconnects )
  {
    v18 = (VDS_INTERCONNECT *)CoTaskMemAlloc(32LL * v7->m_cInterconnects);
    v7->m_rgInterconnects = v18;
    if ( !v18 )
    {
      v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
      v28 = L"CORHWUTC";
      v29 = 1700;
      v30 = 1;
      v31 = 255;
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
    }
    for ( j = 0; j < v7->m_cInterconnects; ++j )
    {
      v20 = j;
      m_rgInterconnects = v7->m_rgInterconnects;
      m_rgInterconnects[v20].m_addressType = a3->m_rgInterconnects[v20].m_addressType;
      m_cbPort = a3->m_rgInterconnects[v20].m_cbPort;
      m_rgInterconnects[v20].m_cbPort = m_cbPort;
      v23 = (BYTE *)CoTaskMemAlloc(m_cbPort);
      m_rgInterconnects[v20].m_pbPort = v23;
      if ( !v23 )
      {
        v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
        v28 = L"CORHWUTC";
        v29 = 1714;
        v30 = 1;
        v31 = 255;
        v33 = 0x1000000;
        memset_0(v32, 0, sizeof(v32));
        CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
      }
      memcpy_0(v23, a3->m_rgInterconnects[v20].m_pbPort, m_rgInterconnects[v20].m_cbPort);
      m_cbAddress = a3->m_rgInterconnects[v20].m_cbAddress;
      m_rgInterconnects[v20].m_cbAddress = m_cbAddress;
      v25 = (BYTE *)CoTaskMemAlloc(m_cbAddress);
      m_rgInterconnects[v20].m_pbAddress = v25;
      if ( !v25 )
      {
        v26 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v27 = L"CVssHardwareProviderWrapper::CopyLunInformation";
        v28 = L"CORHWUTC";
        v29 = 1728;
        v30 = 1;
        v31 = 255;
        v33 = 0x1000000;
        memset_0(v32, 0, sizeof(v32));
        CVssFunctionTracer::ThrowOutOfMemory(v34, &v26);
      }
      memcpy_0(v25, a3->m_rgInterconnects[v20].m_pbAddress, m_rgInterconnects[v20].m_cbAddress);
    }
  }
  else
  {
    v7->m_rgInterconnects = 0;
  }
  *a2 = v7;
  CVssFunctionTracer::~CVssFunctionTracer(v34);
}

```

## disassembly

```asm
0x1400bda58  mov     [rsp-8+arg_8], rbx
0x1400bda5d  mov     [rsp-8+arg_10], rsi
0x1400bda62  push    rbp
0x1400bda63  push    rdi
0x1400bda64  push    r12
0x1400bda66  push    r14
0x1400bda68  push    r15
0x1400bda6a  lea     rbp, [rsp-40h]
0x1400bda6f  sub     rsp, 140h
0x1400bda76  mov     rsi, r8
0x1400bda79  mov     r12, rdx
0x1400bda7c  lea     r15, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bda83  mov     [rsp+160h+var_140], r15
0x1400bda88  lea     r14, aCvsshardwarepr_129; "CVssHardwareProviderWrapper::CopyLunInf"...
0x1400bda8f  mov     [rsp+160h+var_138], r14
0x1400bda94  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bda9b  mov     [rsp+160h+var_130], rax
0x1400bdaa0  mov     [rsp+160h+var_128], 668h
0x1400bdaa8  mov     edi, 1
0x1400bdaad  mov     [rsp+160h+var_124], edi
0x1400bdab1  mov     [rsp+160h+var_120], 0FFh
0x1400bdab9  mov     [rbp+60h+var_A0], 1000000h
0x1400bdac0  xor     edx, edx; Val
0x1400bdac2  lea     r8d, [rdi+77h]; Size
0x1400bdac6  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdacb  call    memset_0
0x1400bdad0  xor     r8d, r8d
0x1400bdad3  lea     rdx, [rsp+160h+var_140]
0x1400bdad8  lea     rcx, [rbp+60h+var_90]
0x1400bdadc  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400bdae1  nop
0x1400bdae2  lea     ecx, [rdi+5Fh]; cb
0x1400bdae5  call    cs:__imp_CoTaskMemAlloc
0x1400bdaeb  mov     rbx, rax
0x1400bdaee  test    rax, rax
0x1400bdaf1  jnz     short loc_1400BDB43
0x1400bdaf3  mov     [rsp+160h+var_140], r15
0x1400bdaf8  mov     [rsp+160h+var_138], r14
0x1400bdafd  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bdb04  mov     [rsp+160h+var_130], rax
0x1400bdb09  mov     [rsp+160h+var_128], 670h
0x1400bdb11  mov     [rsp+160h+var_124], edi
0x1400bdb15  mov     [rsp+160h+var_120], 0FFh
0x1400bdb1d  mov     [rbp+60h+var_A0], 1000000h
0x1400bdb24  xor     edx, edx; Val
0x1400bdb26  lea     r8d, [rdi+77h]; Size
0x1400bdb2a  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdb2f  call    memset_0
0x1400bdb34  lea     rdx, [rsp+160h+var_140]
0x1400bdb39  lea     rcx, [rbp+60h+var_90]
0x1400bdb3d  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bdb43  movups  xmm0, xmmword ptr [rsi]
0x1400bdb46  movups  xmmword ptr [rax], xmm0
0x1400bdb49  movups  xmm1, xmmword ptr [rsi+10h]
0x1400bdb4d  movups  xmmword ptr [rax+10h], xmm1
0x1400bdb51  movups  xmm0, xmmword ptr [rsi+20h]
0x1400bdb55  movups  xmmword ptr [rax+20h], xmm0
0x1400bdb59  movups  xmm1, xmmword ptr [rsi+30h]
0x1400bdb5d  movups  xmmword ptr [rax+30h], xmm1
0x1400bdb61  movups  xmm0, xmmword ptr [rsi+40h]
0x1400bdb65  movups  xmmword ptr [rax+40h], xmm0
0x1400bdb69  movups  xmm1, xmmword ptr [rsi+50h]
0x1400bdb6d  movups  xmmword ptr [rax+50h], xmm1
0x1400bdb71  lea     rdx, [rax+10h]; char **
0x1400bdb75  mov     r8, [rsi+10h]; char *
0x1400bdb79  call    ?CopyLunInfoString@CVssHardwareProviderWrapper@@AEAAXPEAPEADPEBD@Z; CVssHardwareProviderWrapper::CopyLunInfoString(char * *,char const *)
0x1400bdb7e  lea     rdx, [rbx+18h]; char **
0x1400bdb82  mov     r8, [rsi+18h]; char *
0x1400bdb86  call    ?CopyLunInfoString@CVssHardwareProviderWrapper@@AEAAXPEAPEADPEBD@Z; CVssHardwareProviderWrapper::CopyLunInfoString(char * *,char const *)
0x1400bdb8b  lea     rdx, [rbx+20h]; char **
0x1400bdb8f  mov     r8, [rsi+20h]; char *
0x1400bdb93  call    ?CopyLunInfoString@CVssHardwareProviderWrapper@@AEAAXPEAPEADPEBD@Z; CVssHardwareProviderWrapper::CopyLunInfoString(char * *,char const *)
0x1400bdb98  lea     rdx, [rbx+28h]; char **
0x1400bdb9c  mov     r8, [rsi+28h]; char *
0x1400bdba0  call    ?CopyLunInfoString@CVssHardwareProviderWrapper@@AEAAXPEAPEADPEBD@Z; CVssHardwareProviderWrapper::CopyLunInfoString(char * *,char const *)
0x1400bdba5  mov     eax, [rsi+40h]
0x1400bdba8  mov     [rbx+40h], eax
0x1400bdbab  mov     eax, [rsi+44h]
0x1400bdbae  mov     [rbx+44h], eax
0x1400bdbb1  lea     rcx, [rax+rax*2]
0x1400bdbb5  shl     rcx, 3; cb
0x1400bdbb9  call    cs:__imp_CoTaskMemAlloc
0x1400bdbbf  mov     [rbx+48h], rax
0x1400bdbc3  test    rax, rax
0x1400bdbc6  jnz     short loc_1400BDC18
0x1400bdbc8  mov     [rsp+160h+var_140], r15
0x1400bdbcd  mov     [rsp+160h+var_138], r14
0x1400bdbd2  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bdbd9  mov     [rsp+160h+var_130], rax
0x1400bdbde  mov     [rsp+160h+var_128], 684h
0x1400bdbe6  mov     [rsp+160h+var_124], edi
0x1400bdbea  mov     [rsp+160h+var_120], 0FFh
0x1400bdbf2  mov     [rbp+60h+var_A0], 1000000h
0x1400bdbf9  xor     edx, edx; Val
0x1400bdbfb  lea     r8d, [rdx+78h]; Size
0x1400bdbff  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdc04  call    memset_0
0x1400bdc09  lea     rdx, [rsp+160h+var_140]
0x1400bdc0e  lea     rcx, [rbp+60h+var_90]
0x1400bdc12  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bdc18  xor     r14d, r14d
0x1400bdc1b  cmp     r14d, [rbx+44h]
0x1400bdc1f  jnb     loc_1400BDCE4
0x1400bdc25  lea     rdi, [r14+r14*2]
0x1400bdc29  mov     r15, [rbx+48h]
0x1400bdc2d  mov     rax, [rsi+48h]
0x1400bdc31  mov     ecx, [rax+rdi*8]
0x1400bdc34  mov     [r15+rdi*8], ecx
0x1400bdc38  mov     rax, [rsi+48h]
0x1400bdc3c  mov     ecx, [rax+rdi*8+4]
0x1400bdc40  mov     [r15+rdi*8+4], ecx
0x1400bdc45  mov     rax, [rsi+48h]
0x1400bdc49  mov     ecx, [rax+rdi*8+8]; cb
0x1400bdc4d  mov     [r15+rdi*8+8], ecx
0x1400bdc52  call    cs:__imp_CoTaskMemAlloc
0x1400bdc58  mov     [r15+rdi*8+10h], rax
0x1400bdc5d  test    rax, rax
0x1400bdc60  jz      short loc_1400BDC82
0x1400bdc62  mov     r8d, [r15+rdi*8+8]; Size
0x1400bdc67  mov     rdx, [rsi+48h]
0x1400bdc6b  mov     rdx, [rdx+rdi*8+10h]; Src
0x1400bdc70  mov     rcx, rax; void *
0x1400bdc73  call    memcpy_0
0x1400bdc78  mov     edi, 1
0x1400bdc7d  add     r14d, edi
0x1400bdc80  jmp     short loc_1400BDC1B
0x1400bdc82  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bdc89  mov     [rsp+160h+var_140], rax
0x1400bdc8e  lea     rax, aCvsshardwarepr_129; "CVssHardwareProviderWrapper::CopyLunInf"...
0x1400bdc95  mov     [rsp+160h+var_138], rax
0x1400bdc9a  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bdca1  mov     [rsp+160h+var_130], rax
0x1400bdca6  mov     [rsp+160h+var_128], 693h
0x1400bdcae  mov     [rsp+160h+var_124], 1
0x1400bdcb6  mov     [rsp+160h+var_120], 0FFh
0x1400bdcbe  mov     [rbp+60h+var_A0], 1000000h
0x1400bdcc5  xor     edx, edx; Val
0x1400bdcc7  lea     r8d, [rdx+78h]; Size
0x1400bdccb  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdcd0  call    memset_0
0x1400bdcd5  lea     rdx, [rsp+160h+var_140]
0x1400bdcda  lea     rcx, [rbp+60h+var_90]
0x1400bdcde  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bdce4  cmp     dword ptr [rbx+50h], 0
0x1400bdce8  jbe     loc_1400BDEBB
0x1400bdcee  mov     ecx, [rbx+50h]
0x1400bdcf1  shl     rcx, 5; cb
0x1400bdcf5  call    cs:__imp_CoTaskMemAlloc
0x1400bdcfb  mov     [rbx+58h], rax
0x1400bdcff  test    rax, rax
0x1400bdd02  jnz     short loc_1400BDD62
0x1400bdd04  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bdd0b  mov     [rsp+160h+var_140], rax
0x1400bdd10  lea     rax, aCvsshardwarepr_129; "CVssHardwareProviderWrapper::CopyLunInf"...
0x1400bdd17  mov     [rsp+160h+var_138], rax
0x1400bdd1c  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bdd23  mov     [rsp+160h+var_130], rax
0x1400bdd28  mov     [rsp+160h+var_128], 6A4h
0x1400bdd30  mov     [rsp+160h+var_124], edi
0x1400bdd34  mov     [rsp+160h+var_120], 0FFh
0x1400bdd3c  mov     [rbp+60h+var_A0], 1000000h
0x1400bdd43  xor     edx, edx; Val
0x1400bdd45  lea     r8d, [rdx+78h]; Size
0x1400bdd49  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdd4e  call    memset_0
0x1400bdd53  lea     rdx, [rsp+160h+var_140]
0x1400bdd58  lea     rcx, [rbp+60h+var_90]
0x1400bdd5c  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bdd62  xor     r15d, r15d
0x1400bdd65  cmp     r15d, [rbx+50h]
0x1400bdd69  jnb     loc_1400BDEC3
0x1400bdd6f  mov     edi, r15d
0x1400bdd72  shl     rdi, 5
0x1400bdd76  mov     r14, [rbx+58h]
0x1400bdd7a  mov     rax, [rsi+58h]
0x1400bdd7e  mov     ecx, [rdi+rax]
0x1400bdd81  mov     [r14+rdi], ecx
0x1400bdd85  mov     rax, [rsi+58h]
0x1400bdd89  mov     ecx, [rax+rdi+4]; cb
0x1400bdd8d  mov     [r14+rdi+4], ecx
0x1400bdd92  call    cs:__imp_CoTaskMemAlloc
0x1400bdd98  mov     [r14+rdi+8], rax
0x1400bdd9d  test    rax, rax
0x1400bdda0  jz      loc_1400BDE59
0x1400bdda6  mov     r8d, [r14+rdi+4]; Size
0x1400bddab  mov     rdx, [rsi+58h]
0x1400bddaf  mov     rdx, [rdx+rdi+8]; Src
0x1400bddb4  mov     rcx, rax; void *
0x1400bddb7  call    memcpy_0
0x1400bddbc  mov     rax, [rsi+58h]
0x1400bddc0  mov     ecx, [rax+rdi+10h]; cb
0x1400bddc4  mov     [r14+rdi+10h], ecx
0x1400bddc9  call    cs:__imp_CoTaskMemAlloc
0x1400bddcf  mov     [r14+rdi+18h], rax
0x1400bddd4  test    rax, rax
0x1400bddd7  jz      short loc_1400BDDF7
0x1400bddd9  mov     r8d, [r14+rdi+10h]; Size
0x1400bddde  mov     rdx, [rsi+58h]
0x1400bdde2  mov     rdx, [rdx+rdi+18h]; Src
0x1400bdde7  mov     rcx, rax; void *
0x1400bddea  call    memcpy_0
0x1400bddef  inc     r15d
0x1400bddf2  jmp     loc_1400BDD65
0x1400bddf7  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bddfe  mov     [rsp+160h+var_140], rax
0x1400bde03  lea     rax, aCvsshardwarepr_129; "CVssHardwareProviderWrapper::CopyLunInf"...
0x1400bde0a  mov     [rsp+160h+var_138], rax
0x1400bde0f  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bde16  mov     [rsp+160h+var_130], rax
0x1400bde1b  mov     [rsp+160h+var_128], 6C0h
0x1400bde23  mov     [rsp+160h+var_124], 1
0x1400bde2b  mov     [rsp+160h+var_120], 0FFh
0x1400bde33  mov     [rbp+60h+var_A0], 1000000h
0x1400bde3a  xor     edx, edx; Val
0x1400bde3c  lea     r8d, [rdx+78h]; Size
0x1400bde40  lea     rcx, [rsp+160h+var_118]; void *
0x1400bde45  call    memset_0
0x1400bde4a  lea     rdx, [rsp+160h+var_140]
0x1400bde4f  lea     rcx, [rbp+60h+var_90]
0x1400bde53  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bde59  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400bde60  mov     [rsp+160h+var_140], rax
0x1400bde65  lea     rax, aCvsshardwarepr_129; "CVssHardwareProviderWrapper::CopyLunInf"...
0x1400bde6c  mov     [rsp+160h+var_138], rax
0x1400bde71  lea     rax, aCorhwutc; "CORHWUTC"
0x1400bde78  mov     [rsp+160h+var_130], rax
0x1400bde7d  mov     [rsp+160h+var_128], 6B2h
0x1400bde85  mov     [rsp+160h+var_124], 1
0x1400bde8d  mov     [rsp+160h+var_120], 0FFh
0x1400bde95  mov     [rbp+60h+var_A0], 1000000h
0x1400bde9c  xor     edx, edx; Val
0x1400bde9e  lea     r8d, [rdx+78h]; Size
0x1400bdea2  lea     rcx, [rsp+160h+var_118]; void *
0x1400bdea7  call    memset_0
0x1400bdeac  lea     rdx, [rsp+160h+var_140]
0x1400bdeb1  lea     rcx, [rbp+60h+var_90]
0x1400bdeb5  call    ?ThrowOutOfMemory@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ThrowOutOfMemory(CVssDebugInfo)
0x1400bdebb  mov     qword ptr [rbx+58h], 0
0x1400bdec3  mov     [r12], rbx
0x1400bdec7  lea     rcx, [rbp+60h+var_90]; this
0x1400bdecb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400bded0  lea     r11, [rsp+160h+var_20]
0x1400bded8  mov     rbx, [r11+38h]
0x1400bdedc  mov     rsi, [r11+40h]
0x1400bdee0  mov     rsp, r11
0x1400bdee3  pop     r15
0x1400bdee5  pop     r14
0x1400bdee7  pop     r12
0x1400bdee9  pop     rdi
0x1400bdeea  pop     rbp
0x1400bdeeb  retn
```
