# SstpSvcCreateUpdateTenantGatewayMapping

- ea: `0x1800138c0`
- end: `0x180013ff6`
- name: `SstpSvcCreateUpdateTenantGatewayMapping`
- size: `1846`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007c34`
- `0x180007cd4`
- `0x18000827c`
- `0x180008360`
- `0x18000f234`
- `0x18000f5ac`
- `0x18000f5e8`
- `0x18000f77c`
- `0x18000f7bc`
- `0x18000f8fc`
- `0x18000fb00`
- `0x18000ff74`
- `0x1800101dc`
- `0x1800103e8`
- `0x180010634`
- `0x180010b24`
- `0x180010cb8`
- `0x180010e30`
- `0x1800113dc`
- `0x180011700`
- `0x18001211c`
- `0x1800124fc`
- `0x180012e20`
- `0x180012ef8`
- `0x180012f88`
- `0x1800138c0`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013981`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013981`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013faf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013faf`

## string_xrefs

- `0x18001399c`: `SstpSvcCreateUpdateTenantGatewayMapping: xml file is not opened`
- `0x1800139e5`: `SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d`
- `0x180013a4d`: `SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter failed with error %d`
- `0x180013b08`: `SstpSvcCreateUpdateTenantGatewayMapping: Trying to create a Tenant(%ws) entry that already exists`
- `0x180013b54`: `SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero`
- `0x180013daa`: `SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero`
- `0x180013bac`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d`
- `0x180013e03`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d`
- `0x180013c3c`: `SstpSvcCreateUpdateTenantGatewayMapping: FlushXmlWriter failed with error %d`
- `0x180013f57`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewTenantEntry function failed with error %d`
- `0x180013cd3`: `SstpSvcCreateUpdateTenantGatewayMapping: ReplaceGatewayList function failed with error %d`
- `0x180013d5d`: `SstpSvcCreateUpdateTenantGatewayMapping: Trying to update a Tenant(%ws) entry that does not exist`
- `0x180013eb0`: `SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcCreateUpdateTenantGatewayMapping(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // r15d
  RTL_SRWLOCK *v6; // r14
  FileStream *FileStream; // rbx
  unsigned int v8; // ecx
  unsigned int v9; // edi
  const wchar_t *v10; // r8
  unsigned int v11; // eax
  char *v12; // r13
  __int64 k; // r12
  __int64 v14; // rdi
  __int64 *v15; // r15
  __int64 v16; // rdx
  bool v17; // bl
  _QWORD *v18; // rax
  __int64 v19; // rdx
  bool v20; // bl
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // rax
  const wchar_t *v27; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY **m; // rbx
  __int64 v29; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY *v30; // rdi
  __int64 v31; // rax
  unsigned int v32; // r12d
  __int64 i; // r15
  __int64 v34; // rdi
  __int64 v35; // rdx
  bool v36; // bl
  __int64 v37; // r8
  __int64 v38; // r8
  unsigned int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY **j; // rbx
  __int64 v45; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY *v46; // rdi
  __int64 v47; // rax
  struct TenantGatewayMap *Instance; // [rsp+20h] [rbp-E0h]
  struct IXmlWriter *ppvObject; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v51; // [rsp+30h] [rbp-D0h]
  __int64 v52; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+48h] [rbp-B8h]
  __int128 v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h]
  _BYTE v57[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v58[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h]
  _BYTE v60[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v61[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v62[40]; // [rsp+D8h] [rbp-28h] BYREF
  int v63; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v64[2044]; // [rsp+104h] [rbp+4h] BYREF

  v54 = a4;
  v4 = a3;
  v51 = a3;
  Instance = TenantGatewayMap::GetInstance();
  v6 = (RTL_SRWLOCK *)Instance;
  ppvObject = 0;
  FileStream = (FileStream *)TenantGatewayMap::GetFileStream(Instance);
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v60);
  v56 = 0;
  v55 = 0;
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v58);
  v63 = 0;
  memset_0(v64, 0, sizeof(v64));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
  {
    v9 = 50;
    goto LABEL_83;
  }
  if ( !(unsigned int)CheckClientAccessToXmlFile(v8) )
  {
    v9 = 5;
    goto LABEL_83;
  }
  AcquireSRWLockExclusive((PSRWLOCK)Instance);
  if ( FileStream )
  {
    FileStream::DeleteExistingContent(FileStream);
    v11 = OpenXmlWriter(&ppvObject, (struct IStream *)FileStream);
    v9 = v11;
    if ( v11 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_80;
      LOWORD(v63) = 0;
      FormatRRASErrorString(&v63, L"SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d", v11);
      goto LABEL_12;
    }
    v12 = (char *)Instance + 8;
    if ( a2 )
    {
      if ( a2 != 1 )
        goto LABEL_80;
      v32 = v51;
      for ( i = 0; (unsigned int)i < v32; i = (unsigned int)(i + 1) )
      {
        v34 = v54 + 40 * i;
        std::wstring::wstring(v62, *(_QWORD *)(v34 + 8));
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          v12,
          &v52,
          v62);
        LOBYTE(v35) = 1;
        v36 = v52 == *((_QWORD *)Instance + 2);
        std::wstring::_Tidy(v62, v35, 0);
        if ( v36 )
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            v37 = *(_QWORD *)(v34 + 8);
            LOWORD(v63) = 0;
            FormatRRASErrorString(
              &v63,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Trying to update a Tenant(%ws) entry that does not exist",
              v37);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
          }
          *(_DWORD *)(v34 + 32) = 1168;
        }
        else if ( *(_DWORD *)(v34 + 16) )
        {
          v39 = AddNewEntryToXmlWriter(ppvObject, (struct _SSTP_TENANT_GATEWAY_ENTRY *)v34);
          *(_DWORD *)(v34 + 32) = v39;
          v40 = v39;
          if ( (byte_18002D803 & 8) != 0 )
          {
            v41 = *(_QWORD *)(v34 + 8);
            LOWORD(v63) = 0;
            FormatRRASErrorString(
              &v63,
              L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d",
              v41,
              v39);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
          }
          if ( !v40 )
          {
            v53 = v34;
            std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(&v55, &v53);
            v42 = std::wstring::wstring(v62, *(_QWORD *)(v34 + 8));
            std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(
              v60,
              v57,
              v42);
            LOBYTE(v43) = 1;
            std::wstring::_Tidy(v62, v43, 0);
          }
        }
        else
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            v38 = *(_QWORD *)(v34 + 8);
            LOWORD(v63) = 0;
            FormatRRASErrorString(
              &v63,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero",
              v38);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
          }
          *(_DWORD *)(v34 + 32) = 87;
        }
      }
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v57,
        v60);
      v9 = AddExistingEntryToXmlWriter(ppvObject, v57);
      if ( v9 )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          v27 = L"SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d";
LABEL_77:
          LOWORD(v63) = 0;
          FormatRRASErrorString(&v63, v27, v9);
          if ( (byte_18002D803 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
        }
LABEL_79:
        v6 = (RTL_SRWLOCK *)Instance;
        goto LABEL_80;
      }
      v9 = FlushXmlWriter(ppvObject);
      if ( !v9 )
      {
        for ( j = (struct _SSTP_TENANT_GATEWAY_ENTRY **)v55; j != *((struct _SSTP_TENANT_GATEWAY_ENTRY ***)&v55 + 1); ++j )
        {
          v9 = AddNewTenantEntry(*j);
          if ( v9 )
          {
LABEL_75:
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_79;
            v27 = L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewTenantEntry function failed with error %d";
            goto LABEL_77;
          }
          std::wstring::wstring(v62, *((_QWORD *)*j + 1));
          std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
            v12,
            &v52,
            v62);
          LOBYTE(v45) = 1;
          std::wstring::_Tidy(v62, v45, 0);
          v46 = *j;
          v47 = std::vector<std::wstring>::vector<std::wstring>(v57, v52 + 56);
          v9 = ReplaceGatewayList(v47, v46);
          if ( v9 )
          {
LABEL_45:
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_79;
            v27 = L"SstpSvcCreateUpdateTenantGatewayMapping: ReplaceGatewayList function failed with error %d";
            goto LABEL_77;
          }
        }
        goto LABEL_79;
      }
    }
    else
    {
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v57,
        v60);
      v9 = AddExistingEntryToXmlWriter(ppvObject, v57);
      if ( v9 )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_80;
        LOWORD(v63) = 0;
        FormatRRASErrorString(
          &v63,
          L"SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter failed with error %d",
          v9);
LABEL_12:
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_80;
        v10 = (const wchar_t *)&v63;
        goto LABEL_8;
      }
      for ( k = 0; (unsigned int)k < v4; k = (unsigned int)(k + 1) )
      {
        v14 = v54 + 40 * k;
        v15 = (__int64 *)(v14 + 8);
        std::wstring::wstring(v62, *(_QWORD *)(v14 + 8));
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          v12,
          &v53,
          v62);
        LOBYTE(v16) = 1;
        v17 = v53 == *((_QWORD *)Instance + 2);
        std::wstring::_Tidy(v62, v16, 0);
        if ( v17
          && (std::wstring::wstring(v62, *v15),
              v18 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(
                                v58,
                                v61,
                                v62),
              LOBYTE(v19) = 1,
              v20 = *v18 == v59,
              std::wstring::_Tidy(v62, v19, 0),
              v20) )
        {
          if ( *(_DWORD *)(v14 + 16) )
          {
            v23 = AddNewEntryToXmlWriter(ppvObject, (struct _SSTP_TENANT_GATEWAY_ENTRY *)v14);
            *(_DWORD *)(v14 + 32) = v23;
            v24 = v23;
            if ( (byte_18002D803 & 8) != 0 )
            {
              v25 = *v15;
              LOWORD(v63) = 0;
              FormatRRASErrorString(
                &v63,
                L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d",
                v25,
                v23);
              if ( (byte_18002D803 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
            }
            if ( !v24 )
            {
              v52 = v14;
              std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(&v55, &v52);
              v26 = std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<unsigned short * &>(
                      v58,
                      v14 + 8);
              std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Linsert(
                v58,
                v57,
                v26);
            }
          }
          else
          {
            if ( (byte_18002D803 & 8) != 0 )
            {
              v22 = *v15;
              LOWORD(v63) = 0;
              FormatRRASErrorString(
                &v63,
                L"SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero",
                v22);
              if ( (byte_18002D803 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
            }
            *(_DWORD *)(v14 + 32) = 87;
          }
        }
        else
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            v21 = *v15;
            LOWORD(v63) = 0;
            FormatRRASErrorString(
              &v63,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Trying to create a Tenant(%ws) entry that already exists",
              v21);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v63);
          }
          *(_DWORD *)(v14 + 32) = 183;
        }
        v4 = v51;
      }
      v9 = FlushXmlWriter(ppvObject);
      if ( !v9 )
      {
        for ( m = (struct _SSTP_TENANT_GATEWAY_ENTRY **)v55; m != *((struct _SSTP_TENANT_GATEWAY_ENTRY ***)&v55 + 1); ++m )
        {
          v9 = AddNewTenantEntry(*m);
          if ( v9 )
            goto LABEL_75;
          std::wstring::wstring(v62, *((_QWORD *)*m + 1));
          std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
            v12,
            &v52,
            v62);
          LOBYTE(v29) = 1;
          std::wstring::_Tidy(v62, v29, 0);
          v30 = *m;
          v31 = std::vector<std::wstring>::vector<std::wstring>(v57, v52 + 56);
          v9 = ReplaceGatewayList(v31, v30);
          if ( v9 )
            goto LABEL_45;
        }
        goto LABEL_79;
      }
    }
    if ( (byte_18002D803 & 8) != 0 )
    {
      v27 = L"SstpSvcCreateUpdateTenantGatewayMapping: FlushXmlWriter failed with error %d";
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  v9 = 2;
  if ( (byte_18002D803 & 8) != 0 )
  {
    v10 = L"SstpSvcCreateUpdateTenantGatewayMapping: xml file is not opened";
LABEL_8:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v10);
  }
LABEL_80:
  if ( ppvObject )
    ((void (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Release)(ppvObject);
  ppvObject = 0;
  ReleaseSRWLockExclusive(v6);
LABEL_83:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v58);
  std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::~vector<_SSTP_TENANT_GATEWAY_ENTRY *>(&v55);
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v60);
  return v9;
}

```

## disassembly

```asm
0x1800138c0  push    rbp
0x1800138c2  push    rbx
0x1800138c3  push    rsi
0x1800138c4  push    rdi
0x1800138c5  push    r12
0x1800138c7  push    r13
0x1800138c9  push    r14
0x1800138cb  push    r15
0x1800138cd  lea     rbp, [rsp-818h]
0x1800138d5  sub     rsp, 918h
0x1800138dc  mov     rax, cs:__security_cookie
0x1800138e3  xor     rax, rsp
0x1800138e6  mov     [rbp+850h+var_50], rax
0x1800138ed  mov     [rsp+950h+var_908], r9
0x1800138f2  mov     r15d, r8d
0x1800138f5  mov     [rsp+950h+var_920], r8d
0x1800138fa  mov     esi, edx
0x1800138fc  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180013901  mov     rcx, rax; this
0x180013904  mov     [rsp+950h+var_930], rax
0x180013909  mov     r14, rax
0x18001390c  mov     [rsp+950h+ppvObject], 0
0x180013915  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x18001391a  lea     rcx, [rbp+850h+var_8A0]
0x18001391e  mov     rbx, rax
0x180013921  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x180013926  xorps   xmm0, xmm0
0x180013929  mov     [rsp+950h+var_8F0], 0
0x180013932  lea     rcx, [rbp+850h+var_8C0]
0x180013936  movdqu  [rsp+950h+var_900], xmm0
0x18001393c  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x180013941  xor     ecx, ecx
0x180013943  xor     edx, edx; Val
0x180013945  mov     [rbp+850h+var_850], ecx
0x180013948  mov     r8d, 7FCh; Size
0x18001394e  lea     rcx, [rbp+850h+var_84C]; void *
0x180013952  call    memset_0
0x180013957  mov     ecx, 1
0x18001395c  call    GetSstpConfigFlag
0x180013961  test    eax, eax
0x180013963  jnz     short loc_18001396D
0x180013965  lea     edi, [rax+32h]
0x180013968  jmp     loc_180013FB5
0x18001396d  call    ?CheckClientAccessToXmlFile@@YAHK@Z; CheckClientAccessToXmlFile(ulong)
0x180013972  test    eax, eax
0x180013974  jnz     short loc_18001397E
0x180013976  lea     edi, [rax+5]
0x180013979  jmp     loc_180013FB5
0x18001397e  mov     rcx, r14; SRWLock
0x180013981  call    cs:__imp_AcquireSRWLockExclusive
0x180013987  test    rbx, rbx
0x18001398a  jnz     short loc_1800139BB
0x18001398c  test    cs:byte_18002D803, 8
0x180013993  lea     edi, [rbx+2]
0x180013996  jz      loc_180013F8D
0x18001399c  lea     r8, aSstpsvccreateu_1; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800139a3  lea     rdx, RasSSTPSvcTraceError
0x1800139aa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800139b1  call    McTemplateU0z_EventWriteTransfer
0x1800139b6  jmp     loc_180013F8D
0x1800139bb  mov     rcx, rbx; this
0x1800139be  call    ?DeleteExistingContent@FileStream@@QEAAJXZ; FileStream::DeleteExistingContent(void)
0x1800139c3  mov     rdx, rbx; struct IStream *
0x1800139c6  lea     rcx, [rsp+950h+ppvObject]; ppvObject
0x1800139cb  call    ?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z; OpenXmlWriter(IXmlWriter * *,IStream *)
0x1800139d0  mov     edi, eax
0x1800139d2  test    eax, eax
0x1800139d4  jz      short loc_180013A0F
0x1800139d6  test    cs:byte_18002D803, 8
0x1800139dd  jz      loc_180013F8D
0x1800139e3  xor     ecx, ecx
0x1800139e5  lea     rdx, aSstpsvccreateu_2; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800139ec  mov     word ptr [rbp+850h+var_850], cx
0x1800139f0  mov     r8d, eax
0x1800139f3  lea     rcx, [rbp+850h+var_850]
0x1800139f7  call    FormatRRASErrorString
0x1800139fc  test    cs:byte_18002D803, 8
0x180013a03  jz      loc_180013F8D
0x180013a09  lea     r8, [rbp+850h+var_850]
0x180013a0d  jmp     short loc_1800139A3
0x180013a0f  lea     r13, [r14+8]
0x180013a13  test    esi, esi
0x180013a15  jnz     loc_180013CDF
0x180013a1b  lea     rdx, [rbp+850h+var_8A0]
0x180013a1f  lea     rcx, [rsp+950h+var_8E0]
0x180013a24  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>> const &)
0x180013a29  mov     rcx, [rsp+950h+ppvObject]
0x180013a2e  lea     rdx, [rsp+950h+var_8E0]
0x180013a33  call    ?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::wstring,_lessstr,std::allocator<std::wstring>>)
0x180013a38  mov     edi, eax
0x180013a3a  test    eax, eax
0x180013a3c  jz      short loc_180013A5D
0x180013a3e  test    cs:byte_18002D803, 8
0x180013a45  jz      loc_180013F8D
0x180013a4b  xor     eax, eax
0x180013a4d  lea     rdx, aSstpsvccreateu_7; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013a54  mov     word ptr [rbp+850h+var_850], ax
0x180013a58  mov     r8d, edi
0x180013a5b  jmp     short loc_1800139F3
0x180013a5d  xor     r12d, r12d
0x180013a60  lea     rsi, RasSSTPSvcTraceError
0x180013a67  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013a6e  cmp     r12d, r15d
0x180013a71  jnb     loc_180013C1F
0x180013a77  mov     rax, [rsp+950h+var_908]
0x180013a7c  lea     rcx, [r12+r12*4]
0x180013a80  lea     rdi, [rax+rcx*8]
0x180013a84  lea     r15, [rdi+8]
0x180013a88  mov     rdx, [r15]
0x180013a8b  lea     rcx, [rbp+850h+var_878]
0x180013a8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013a94  lea     r8, [rbp+850h+var_878]
0x180013a98  mov     rcx, r13
0x180013a9b  lea     rdx, [rsp+950h+var_910]
0x180013aa0  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180013aa5  mov     rax, [r13+8]
0x180013aa9  lea     rcx, [rbp+850h+var_878]
0x180013aad  cmp     [rsp+950h+var_910], rax
0x180013ab2  mov     dl, 1
0x180013ab4  setz    bl
0x180013ab7  xor     r8d, r8d
0x180013aba  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013abf  test    bl, bl
0x180013ac1  jz      short loc_180013AFC
0x180013ac3  mov     rdx, [r15]
0x180013ac6  lea     rcx, [rbp+850h+var_878]
0x180013aca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013acf  lea     r8, [rbp+850h+var_878]
0x180013ad3  lea     rdx, [rbp+850h+var_880]
0x180013ad7  lea     rcx, [rbp+850h+var_8C0]
0x180013adb  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180013ae0  mov     rcx, [rbp+850h+var_8B8]
0x180013ae4  mov     dl, 1
0x180013ae6  cmp     [rax], rcx
0x180013ae9  lea     rcx, [rbp+850h+var_878]
0x180013aed  setz    bl
0x180013af0  xor     r8d, r8d
0x180013af3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013af8  test    bl, bl
0x180013afa  jnz     short loc_180013B42
0x180013afc  test    cs:byte_18002D803, 8
0x180013b03  jz      short loc_180013B36
0x180013b05  mov     r8, [r15]
0x180013b08  lea     rdx, aSstpsvccreateu_6; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013b0f  xor     eax, eax
0x180013b11  lea     rcx, [rbp+850h+var_850]
0x180013b15  mov     word ptr [rbp+850h+var_850], ax
0x180013b19  call    FormatRRASErrorString
0x180013b1e  test    cs:byte_18002D803, 8
0x180013b25  jz      short loc_180013B36
0x180013b27  lea     r8, [rbp+850h+var_850]
0x180013b2b  mov     rdx, rsi
0x180013b2e  mov     rcx, r14
0x180013b31  call    McTemplateU0z_EventWriteTransfer
0x180013b36  mov     dword ptr [rdi+20h], 0B7h
0x180013b3d  jmp     loc_180013C12
0x180013b42  cmp     dword ptr [rdi+10h], 0
0x180013b46  jnz     short loc_180013B8E
0x180013b48  test    cs:byte_18002D803, 8
0x180013b4f  jz      short loc_180013B82
0x180013b51  mov     r8, [r15]
0x180013b54  lea     rdx, aSstpsvccreateu_10; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013b5b  xor     eax, eax
0x180013b5d  lea     rcx, [rbp+850h+var_850]
0x180013b61  mov     word ptr [rbp+850h+var_850], ax
0x180013b65  call    FormatRRASErrorString
0x180013b6a  test    cs:byte_18002D803, 8
0x180013b71  jz      short loc_180013B82
0x180013b73  lea     r8, [rbp+850h+var_850]
0x180013b77  mov     rdx, rsi
0x180013b7a  mov     rcx, r14
0x180013b7d  call    McTemplateU0z_EventWriteTransfer
0x180013b82  mov     dword ptr [rdi+20h], 57h ; 'W'
0x180013b89  jmp     loc_180013C12
0x180013b8e  mov     rcx, [rsp+950h+ppvObject]; struct IXmlWriter *
0x180013b93  mov     rdx, rdi; struct _SSTP_TENANT_GATEWAY_ENTRY *
0x180013b96  call    ?AddNewEntryToXmlWriter@@YAKPEAUIXmlWriter@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; AddNewEntryToXmlWriter(IXmlWriter *,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180013b9b  mov     [rdi+20h], eax
0x180013b9e  mov     ebx, eax
0x180013ba0  test    cs:byte_18002D803, 8
0x180013ba7  jz      short loc_180013BDD
0x180013ba9  mov     r8, [r15]
0x180013bac  lea     rdx, aSstpsvccreateu; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013bb3  xor     ecx, ecx
0x180013bb5  mov     r9d, eax
0x180013bb8  mov     word ptr [rbp+850h+var_850], cx
0x180013bbc  lea     rcx, [rbp+850h+var_850]
0x180013bc0  call    FormatRRASErrorString
0x180013bc5  test    cs:byte_18002D803, 8
0x180013bcc  jz      short loc_180013BDD
0x180013bce  lea     r8, [rbp+850h+var_850]
0x180013bd2  mov     rdx, rsi
0x180013bd5  mov     rcx, r14
0x180013bd8  call    McTemplateU0z_EventWriteTransfer
0x180013bdd  test    ebx, ebx
0x180013bdf  jnz     short loc_180013C12
0x180013be1  lea     rdx, [rsp+950h+var_918]
0x180013be6  mov     [rsp+950h+var_918], rdi
0x180013beb  lea     rcx, [rsp+950h+var_900]
0x180013bf0  call    ?push_back@?$vector@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@V?$allocator@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@std@@@std@@QEAAX$$QEAPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(_SSTP_TENANT_GATEWAY_ENTRY * &&)
0x180013bf5  mov     rdx, r15
0x180013bf8  lea     rcx, [rbp+850h+var_8C0]
0x180013bfc  call    ??$_Buynode@AEAPEAG@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@AEAPEAG@Z; std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<ushort * &>(ushort * &)
0x180013c01  mov     r8, rax
0x180013c04  lea     rdx, [rsp+950h+var_8E0]
0x180013c09  lea     rcx, [rbp+850h+var_8C0]
0x180013c0d  call    ?_Linsert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *,bool)
0x180013c12  mov     r15d, [rsp+950h+var_920]
0x180013c17  inc     r12d
0x180013c1a  jmp     loc_180013A6E
0x180013c1f  mov     rcx, [rsp+950h+ppvObject]; struct IXmlWriter *
0x180013c24  call    ?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z; FlushXmlWriter(IXmlWriter *)
0x180013c29  mov     edi, eax
0x180013c2b  test    eax, eax
0x180013c2d  jz      short loc_180013C48
0x180013c2f  test    cs:byte_18002D803, 8
0x180013c36  jz      loc_180013F88
0x180013c3c  lea     rdx, aSstpsvccreateu_8; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013c43  jmp     loc_180013F5E
0x180013c48  mov     rbx, qword ptr [rsp+950h+var_900]
0x180013c4d  cmp     rbx, qword ptr [rsp+950h+var_900+8]
0x180013c52  jz      loc_180013F88
0x180013c58  mov     rcx, [rbx]; struct _SSTP_TENANT_GATEWAY_ENTRY *
0x180013c5b  call    ?AddNewTenantEntry@@YAKPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; AddNewTenantEntry(_SSTP_TENANT_GATEWAY_ENTRY *)
0x180013c60  mov     edi, eax
0x180013c62  test    eax, eax
0x180013c64  jnz     loc_180013F4E
0x180013c6a  mov     rdx, [rbx]
0x180013c6d  lea     rcx, [rbp+850h+var_878]
0x180013c71  mov     rdx, [rdx+8]
0x180013c75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013c7a  lea     r8, [rbp+850h+var_878]
0x180013c7e  mov     rcx, r13
0x180013c81  lea     rdx, [rsp+950h+var_918]
0x180013c86  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180013c8b  xor     r8d, r8d
0x180013c8e  lea     rcx, [rbp+850h+var_878]
0x180013c92  mov     dl, 1
0x180013c94  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013c99  mov     rdx, [rsp+950h+var_918]
0x180013c9e  lea     rcx, [rsp+950h+var_8E0]
0x180013ca3  mov     rdi, [rbx]
0x180013ca6  add     rdx, 38h ; '8'
0x180013caa  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180013caf  mov     rdx, rdi
0x180013cb2  mov     rcx, rax
0x180013cb5  call    ?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; ReplaceGatewayList(std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180013cba  mov     edi, eax
0x180013cbc  test    eax, eax
0x180013cbe  jnz     short loc_180013CC6
0x180013cc0  add     rbx, 8
0x180013cc4  jmp     short loc_180013C4D
0x180013cc6  test    cs:byte_18002D803, 8
0x180013ccd  jz      loc_180013F88
0x180013cd3  lea     rdx, aSstpsvccreateu_4; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013cda  jmp     loc_180013F5E
0x180013cdf  cmp     esi, 1
0x180013ce2  jnz     loc_180013F8D
0x180013ce8  mov     r12d, [rsp+950h+var_920]
0x180013ced  lea     rsi, RasSSTPSvcTraceError
0x180013cf4  xor     r15d, r15d
0x180013cf7  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013cfe  cmp     r15d, r12d
0x180013d01  jnb     loc_180013E80
0x180013d07  mov     rax, [rsp+950h+var_908]
0x180013d0c  lea     rcx, [r15+r15*4]
0x180013d10  lea     rdi, [rax+rcx*8]
0x180013d14  mov     rdx, [rdi+8]
0x180013d18  lea     rcx, [rbp+850h+var_878]
0x180013d1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013d21  lea     r8, [rbp+850h+var_878]
0x180013d25  mov     rcx, r13
0x180013d28  lea     rdx, [rsp+950h+var_918]
0x180013d2d  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180013d32  mov     rax, [r13+8]
0x180013d36  lea     rcx, [rbp+850h+var_878]
0x180013d3a  cmp     [rsp+950h+var_918], rax
0x180013d3f  mov     dl, 1
0x180013d41  setz    bl
0x180013d44  xor     r8d, r8d
0x180013d47  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013d4c  test    bl, bl
0x180013d4e  jz      short loc_180013D97
0x180013d50  test    cs:byte_18002D803, 8
0x180013d57  jz      short loc_180013D8B
0x180013d59  mov     r8, [rdi+8]
0x180013d5d  lea     rdx, aSstpsvccreateu_0; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180013d64  xor     eax, eax
0x180013d66  lea     rcx, [rbp+850h+var_850]
0x180013d6a  mov     word ptr [rbp+850h+var_850], ax
0x180013d6e  call    FormatRRASErrorString
0x180013d73  test    cs:byte_18002D803, 8
0x180013d7a  jz      short loc_180013D8B
0x180013d7c  lea     r8, [rbp+850h+var_850]
0x180013d80  mov     rdx, rsi
0x180013d83  mov     rcx, r14
0x180013d86  call    McTemplateU0z_EventWriteTransfer
0x180013d8b  mov     dword ptr [rdi+20h], 490h
0x180013d92  jmp     loc_180013E78
0x180013d97  cmp     dword ptr [rdi+10h], 0
  ... truncated ...
```
