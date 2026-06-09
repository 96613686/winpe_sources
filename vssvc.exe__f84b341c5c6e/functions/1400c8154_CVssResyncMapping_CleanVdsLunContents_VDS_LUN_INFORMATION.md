# CVssResyncMapping::CleanVdsLunContents(_VDS_LUN_INFORMATION *)

- ea: `0x1400c8154`
- end: `0x1400c822f`
- name: `?CleanVdsLunContents@CVssResyncMapping@@AEAAXPEAU_VDS_LUN_INFORMATION@@@Z`
- size: `219`
- prototype: `void __fastcall(CVssResyncMapping *__hidden this, struct _VDS_LUN_INFORMATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400c8238`

## callees

- `0x1400c8154`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c818f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c819e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c818f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c819e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c81f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c8220`

## pseudocode

```c
void __fastcall CVssResyncMapping::CleanVdsLunContents(CVssResyncMapping *this, struct _VDS_LUN_INFORMATION *a2)
{
  char *m_szVendorId; // rcx
  char *m_szProductId; // rcx
  char *m_szProductRevision; // rcx
  char *m_szSerialNumber; // rcx
  ULONG m_cIdentifiers; // ebp
  ULONG v8; // esi
  VDS_STORAGE_IDENTIFIER *i; // rdi
  BYTE *m_rgbIdentifier; // rcx
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // rcx
  VDS_INTERCONNECT *m_rgInterconnects; // rdi
  ULONG j; // esi
  BYTE *m_pbAddress; // rcx
  BYTE *m_pbPort; // rcx
  VDS_INTERCONNECT *v16; // rcx

  if ( a2 )
  {
    m_szVendorId = a2->m_szVendorId;
    if ( m_szVendorId )
      CoTaskMemFree(m_szVendorId);
    m_szProductId = a2->m_szProductId;
    if ( m_szProductId )
      CoTaskMemFree(m_szProductId);
    m_szProductRevision = a2->m_szProductRevision;
    if ( m_szProductRevision )
      CoTaskMemFree(m_szProductRevision);
    m_szSerialNumber = a2->m_szSerialNumber;
    if ( m_szSerialNumber )
      CoTaskMemFree(m_szSerialNumber);
    m_cIdentifiers = a2->m_deviceIdDescriptor.m_cIdentifiers;
    v8 = 0;
    for ( i = a2->m_deviceIdDescriptor.m_rgIdentifiers; v8 < m_cIdentifiers; ++i )
    {
      if ( !i )
        break;
      m_rgbIdentifier = i->m_rgbIdentifier;
      if ( m_rgbIdentifier )
        CoTaskMemFree(m_rgbIdentifier);
      ++v8;
    }
    m_rgIdentifiers = a2->m_deviceIdDescriptor.m_rgIdentifiers;
    if ( m_rgIdentifiers )
      CoTaskMemFree(m_rgIdentifiers);
    m_rgInterconnects = a2->m_rgInterconnects;
    for ( j = 0; j < a2->m_cInterconnects; ++m_rgInterconnects )
    {
      if ( !m_rgInterconnects )
        break;
      m_pbAddress = m_rgInterconnects->m_pbAddress;
      if ( m_pbAddress )
        CoTaskMemFree(m_pbAddress);
      m_pbPort = m_rgInterconnects->m_pbPort;
      if ( m_pbPort )
        CoTaskMemFree(m_pbPort);
      ++j;
    }
    v16 = a2->m_rgInterconnects;
    if ( v16 )
      CoTaskMemFree(v16);
  }
}

```

## disassembly

```asm
0x1400c8154  test    rdx, rdx
0x1400c8157  jz      locret_1400C822E
0x1400c815d  push    rbx
0x1400c815e  push    rbp
0x1400c815f  push    rsi
0x1400c8160  push    rdi
0x1400c8161  sub     rsp, 28h
0x1400c8165  mov     rcx, [rdx+10h]; pv
0x1400c8169  mov     rbx, rdx
0x1400c816c  test    rcx, rcx
0x1400c816f  jz      short loc_1400C8177
0x1400c8171  call    cs:__imp_CoTaskMemFree
0x1400c8177  mov     rcx, [rbx+18h]; pv
0x1400c817b  test    rcx, rcx
0x1400c817e  jz      short loc_1400C8186
0x1400c8180  call    cs:__imp_CoTaskMemFree
0x1400c8186  mov     rcx, [rbx+20h]; pv
0x1400c818a  test    rcx, rcx
0x1400c818d  jz      short loc_1400C8195
0x1400c818f  call    cs:__imp_CoTaskMemFree
0x1400c8195  mov     rcx, [rbx+28h]; pv
0x1400c8199  test    rcx, rcx
0x1400c819c  jz      short loc_1400C81A4
0x1400c819e  call    cs:__imp_CoTaskMemFree
0x1400c81a4  mov     ebp, [rbx+44h]
0x1400c81a7  xor     esi, esi
0x1400c81a9  mov     rdi, [rbx+48h]
0x1400c81ad  test    ebp, ebp
0x1400c81af  jz      short loc_1400C81CF
0x1400c81b1  test    rdi, rdi
0x1400c81b4  jz      short loc_1400C81CF
0x1400c81b6  mov     rcx, [rdi+10h]; pv
0x1400c81ba  test    rcx, rcx
0x1400c81bd  jz      short loc_1400C81C5
0x1400c81bf  call    cs:__imp_CoTaskMemFree
0x1400c81c5  inc     esi
0x1400c81c7  add     rdi, 18h
0x1400c81cb  cmp     esi, ebp
0x1400c81cd  jb      short loc_1400C81B1
0x1400c81cf  mov     rcx, [rbx+48h]; pv
0x1400c81d3  test    rcx, rcx
0x1400c81d6  jz      short loc_1400C81DE
0x1400c81d8  call    cs:__imp_CoTaskMemFree
0x1400c81de  mov     rdi, [rbx+58h]
0x1400c81e2  xor     esi, esi
0x1400c81e4  cmp     [rbx+50h], esi
0x1400c81e7  jbe     short loc_1400C8217
0x1400c81e9  test    rdi, rdi
0x1400c81ec  jz      short loc_1400C8217
0x1400c81ee  mov     rcx, [rdi+18h]; pv
0x1400c81f2  test    rcx, rcx
0x1400c81f5  jz      short loc_1400C81FD
0x1400c81f7  call    cs:__imp_CoTaskMemFree
0x1400c81fd  mov     rcx, [rdi+8]; pv
0x1400c8201  test    rcx, rcx
0x1400c8204  jz      short loc_1400C820C
0x1400c8206  call    cs:__imp_CoTaskMemFree
0x1400c820c  inc     esi
0x1400c820e  add     rdi, 20h ; ' '
0x1400c8212  cmp     esi, [rbx+50h]
0x1400c8215  jb      short loc_1400C81E9
0x1400c8217  mov     rcx, [rbx+58h]; pv
0x1400c821b  test    rcx, rcx
0x1400c821e  jz      short loc_1400C8226
0x1400c8220  call    cs:__imp_CoTaskMemFree
0x1400c8226  add     rsp, 28h
0x1400c822a  pop     rdi
0x1400c822b  pop     rsi
0x1400c822c  pop     rbp
0x1400c822d  pop     rbx
0x1400c822e  retn
```
