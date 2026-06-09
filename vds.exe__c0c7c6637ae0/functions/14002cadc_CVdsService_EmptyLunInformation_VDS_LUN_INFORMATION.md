# CVdsService::EmptyLunInformation(_VDS_LUN_INFORMATION *)

- ea: `0x14002cadc`
- end: `0x14002cbd3`
- name: `?EmptyLunInformation@CVdsService@@CAJPEAU_VDS_LUN_INFORMATION@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _VDS_LUN_INFORMATION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140027890`
- `0x14002c7a0`

## callees

- `0x14002cadc`
- `0x14002e123`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cba8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002caf9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002caf9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002cbc2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002cbc2`

## string_xrefs

- `0x14002cae8`: `CVdsService::EmptyLunInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::EmptyLunInformation(struct _VDS_LUN_INFORMATION *a1)
{
  ULONG m_cIdentifiers; // ebp
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // rdi
  ULONG i; // esi
  BYTE *m_rgbIdentifier; // rcx
  VDS_STORAGE_IDENTIFIER *v6; // rcx
  VDS_INTERCONNECT *m_rgInterconnects; // rdi
  ULONG j; // esi
  BYTE *m_pbAddress; // rcx
  BYTE *m_pbPort; // rcx
  VDS_INTERCONNECT *v11; // rcx
  _BYTE v13[56]; // [rsp+20h] [rbp-38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v13, 0x5Eu, "CVdsService::EmptyLunInformation");
  if ( a1 )
  {
    CoTaskMemFree(a1->m_szVendorId);
    CoTaskMemFree(a1->m_szProductId);
    CoTaskMemFree(a1->m_szProductRevision);
    CoTaskMemFree(a1->m_szSerialNumber);
    m_cIdentifiers = a1->m_deviceIdDescriptor.m_cIdentifiers;
    m_rgIdentifiers = a1->m_deviceIdDescriptor.m_rgIdentifiers;
    for ( i = 0; i < m_cIdentifiers; ++m_rgIdentifiers )
    {
      m_rgbIdentifier = m_rgIdentifiers->m_rgbIdentifier;
      if ( m_rgbIdentifier )
        CoTaskMemFree(m_rgbIdentifier);
      ++i;
    }
    v6 = a1->m_deviceIdDescriptor.m_rgIdentifiers;
    if ( v6 )
      CoTaskMemFree(v6);
    m_rgInterconnects = a1->m_rgInterconnects;
    if ( m_rgInterconnects )
    {
      for ( j = 0; j < a1->m_cInterconnects; ++m_rgInterconnects )
      {
        m_pbAddress = m_rgInterconnects->m_pbAddress;
        if ( m_pbAddress )
          CoTaskMemFree(m_pbAddress);
        m_pbPort = m_rgInterconnects->m_pbPort;
        if ( m_pbPort )
          CoTaskMemFree(m_pbPort);
        ++j;
      }
    }
    v11 = a1->m_rgInterconnects;
    if ( v11 )
      CoTaskMemFree(v11);
    memset_0(a1, 0, sizeof(struct _VDS_LUN_INFORMATION));
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v13);
  return 0;
}

```

## disassembly

```asm
0x14002cadc  push    rbx
0x14002cade  push    rbp
0x14002cadf  push    rsi
0x14002cae0  push    rdi
0x14002cae1  sub     rsp, 38h
0x14002cae5  mov     rbx, rcx
0x14002cae8  lea     r8, aCvdsserviceEmp; "CVdsService::EmptyLunInformation"
0x14002caef  mov     edx, 5Eh ; '^'
0x14002caf4  lea     rcx, [rsp+58h+var_38]
0x14002caf9  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002caff  nop
0x14002cb00  test    rbx, rbx
0x14002cb03  jz      loc_14002CBBD
0x14002cb09  mov     rcx, [rbx+10h]; pv
0x14002cb0d  call    cs:__imp_CoTaskMemFree
0x14002cb13  mov     rcx, [rbx+18h]; pv
0x14002cb17  call    cs:__imp_CoTaskMemFree
0x14002cb1d  mov     rcx, [rbx+20h]; pv
0x14002cb21  call    cs:__imp_CoTaskMemFree
0x14002cb27  mov     rcx, [rbx+28h]; pv
0x14002cb2b  call    cs:__imp_CoTaskMemFree
0x14002cb31  mov     ebp, [rbx+44h]
0x14002cb34  mov     rdi, [rbx+48h]
0x14002cb38  xor     esi, esi
0x14002cb3a  test    ebp, ebp
0x14002cb3c  jz      short loc_14002CB57
0x14002cb3e  mov     rcx, [rdi+10h]; pv
0x14002cb42  test    rcx, rcx
0x14002cb45  jz      short loc_14002CB4D
0x14002cb47  call    cs:__imp_CoTaskMemFree
0x14002cb4d  inc     esi
0x14002cb4f  add     rdi, 18h
0x14002cb53  cmp     esi, ebp
0x14002cb55  jb      short loc_14002CB3E
0x14002cb57  mov     rcx, [rbx+48h]; pv
0x14002cb5b  test    rcx, rcx
0x14002cb5e  jz      short loc_14002CB66
0x14002cb60  call    cs:__imp_CoTaskMemFree
0x14002cb66  mov     rdi, [rbx+58h]
0x14002cb6a  test    rdi, rdi
0x14002cb6d  jz      short loc_14002CB9F
0x14002cb6f  xor     esi, esi
0x14002cb71  cmp     [rbx+50h], esi
0x14002cb74  jbe     short loc_14002CB9F
0x14002cb76  mov     rcx, [rdi+18h]; pv
0x14002cb7a  test    rcx, rcx
0x14002cb7d  jz      short loc_14002CB85
0x14002cb7f  call    cs:__imp_CoTaskMemFree
0x14002cb85  mov     rcx, [rdi+8]; pv
0x14002cb89  test    rcx, rcx
0x14002cb8c  jz      short loc_14002CB94
0x14002cb8e  call    cs:__imp_CoTaskMemFree
0x14002cb94  inc     esi
0x14002cb96  add     rdi, 20h ; ' '
0x14002cb9a  cmp     esi, [rbx+50h]
0x14002cb9d  jb      short loc_14002CB76
0x14002cb9f  mov     rcx, [rbx+58h]; pv
0x14002cba3  test    rcx, rcx
0x14002cba6  jz      short loc_14002CBAE
0x14002cba8  call    cs:__imp_CoTaskMemFree
0x14002cbae  xor     edx, edx; Val
0x14002cbb0  lea     r8d, [rdx+60h]; Size
0x14002cbb4  mov     rcx, rbx; void *
0x14002cbb7  call    memset_0
0x14002cbbc  nop
0x14002cbbd  lea     rcx, [rsp+58h+var_38]
0x14002cbc2  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002cbc8  xor     eax, eax
0x14002cbca  add     rsp, 38h
0x14002cbce  pop     rdi
0x14002cbcf  pop     rsi
0x14002cbd0  pop     rbp
0x14002cbd1  pop     rbx
0x14002cbd2  retn
```
