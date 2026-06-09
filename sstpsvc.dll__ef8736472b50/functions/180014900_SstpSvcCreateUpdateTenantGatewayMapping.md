# SstpSvcCreateUpdateTenantGatewayMapping

- ea: `0x180014900`
- end: `0x180015043`
- name: `SstpSvcCreateUpdateTenantGatewayMapping`
- size: `1859`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006f00`
- `0x180008404`
- `0x1800084a8`
- `0x1800089dc`
- `0x180008b90`
- `0x18000ffd4`
- `0x180010358`
- `0x180010394`
- `0x18001052c`
- `0x18001056c`
- `0x1800106b4`
- `0x1800108d0`
- `0x180010d80`
- `0x180010fe8`
- `0x1800111f4`
- `0x180011444`
- `0x1800119a8`
- `0x180011b5c`
- `0x180011cd4`
- `0x1800122fc`
- `0x180012648`
- `0x1800130d0`
- `0x1800134bc`
- `0x180013e00`
- `0x180013ed8`
- `0x180013f68`
- `0x180014900`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014ff5`

## string_xrefs

- `0x1800149e2`: `SstpSvcCreateUpdateTenantGatewayMapping: xml file is not opened`
- `0x180014a2b`: `SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d`
- `0x180014a93`: `SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter failed with error %d`
- `0x180014b4e`: `SstpSvcCreateUpdateTenantGatewayMapping: Trying to create a Tenant(%ws) entry that already exists`
- `0x180014b9a`: `SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero`
- `0x180014df0`: `SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero`
- `0x180014bf2`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d`
- `0x180014e49`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d`
- `0x180014c82`: `SstpSvcCreateUpdateTenantGatewayMapping: FlushXmlWriter failed with error %d`
- `0x180014f9d`: `SstpSvcCreateUpdateTenantGatewayMapping: AddNewTenantEntry function failed with error %d`
- `0x180014d19`: `SstpSvcCreateUpdateTenantGatewayMapping: ReplaceGatewayList function failed with error %d`
- `0x180014da3`: `SstpSvcCreateUpdateTenantGatewayMapping: Trying to update a Tenant(%ws) entry that does not exist`
- `0x180014ef6`: `SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcCreateUpdateTenantGatewayMapping(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // r15d
  RTL_SRWLOCK *v6; // r14
  FileStream *FileStream; // rbx
  unsigned int v8; // edi
  const wchar_t *v9; // r8
  unsigned int v10; // eax
  char *v11; // r13
  __int64 k; // r12
  __int64 v13; // rdi
  __int64 *v14; // r15
  __int64 v15; // rdx
  bool v16; // bl
  _QWORD *v17; // rax
  __int64 v18; // rdx
  bool v19; // bl
  __int64 v20; // r8
  __int64 v21; // r8
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // r8
  __int64 v25; // rax
  const wchar_t *v26; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY **m; // rbx
  __int64 v28; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY *v29; // rdi
  __int64 v30; // rax
  unsigned int v31; // r12d
  __int64 i; // r15
  __int64 v33; // rdi
  __int64 v34; // rdx
  bool v35; // bl
  __int64 v36; // r8
  __int64 v37; // r8
  unsigned int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY **j; // rbx
  __int64 v44; // rdx
  struct _SSTP_TENANT_GATEWAY_ENTRY *v45; // rdi
  __int64 v46; // rax
  struct TenantGatewayMap *Instance; // [rsp+20h] [rbp-E0h]
  struct IXmlWriter *ppvObject; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v50; // [rsp+30h] [rbp-D0h]
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+48h] [rbp-B8h]
  __int128 v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h]
  _BYTE v56[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v57[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h]
  _BYTE v59[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v60[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v61[40]; // [rsp+D8h] [rbp-28h] BYREF
  int v62; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v63[2044]; // [rsp+104h] [rbp+4h] BYREF

  v53 = a4;
  v4 = a3;
  v50 = a3;
  Instance = TenantGatewayMap::GetInstance();
  v6 = (RTL_SRWLOCK *)Instance;
  ppvObject = 0;
  FileStream = (FileStream *)TenantGatewayMap::GetFileStream(Instance);
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v59);
  v55 = 0;
  v54 = 0;
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v57);
  v62 = 0;
  memset_0(v63, 0, sizeof(v63));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
  {
    v8 = 50;
    goto LABEL_83;
  }
  if ( !CheckClientAccessToXmlFile() )
  {
    v8 = 5;
    goto LABEL_83;
  }
  AcquireSRWLockExclusive((PSRWLOCK)Instance);
  if ( FileStream )
  {
    FileStream::DeleteExistingContent(FileStream);
    v10 = OpenXmlWriter(&ppvObject, (struct IStream *)FileStream);
    v8 = v10;
    if ( v10 )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_80;
      LOWORD(v62) = 0;
      FormatRRASErrorString(&v62, L"SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d", v10);
      goto LABEL_12;
    }
    v11 = (char *)Instance + 8;
    if ( a2 )
    {
      if ( a2 != 1 )
        goto LABEL_80;
      v31 = v50;
      for ( i = 0; (unsigned int)i < v31; i = (unsigned int)(i + 1) )
      {
        v33 = v53 + 40 * i;
        std::wstring::wstring(v61, *(_QWORD *)(v33 + 8));
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          v11,
          &v51,
          v61);
        LOBYTE(v34) = 1;
        v35 = v51 == *((_QWORD *)Instance + 2);
        std::wstring::_Tidy(v61, v34, 0);
        if ( v35 )
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            v36 = *(_QWORD *)(v33 + 8);
            LOWORD(v62) = 0;
            FormatRRASErrorString(
              &v62,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Trying to update a Tenant(%ws) entry that does not exist",
              v36);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
          }
          *(_DWORD *)(v33 + 32) = 1168;
        }
        else if ( *(_DWORD *)(v33 + 16) )
        {
          v38 = AddNewEntryToXmlWriter(ppvObject, (struct _SSTP_TENANT_GATEWAY_ENTRY *)v33);
          *(_DWORD *)(v33 + 32) = v38;
          v39 = v38;
          if ( (byte_18002E903 & 8) != 0 )
          {
            v40 = *(_QWORD *)(v33 + 8);
            LOWORD(v62) = 0;
            FormatRRASErrorString(
              &v62,
              L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d",
              v40,
              v38);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
          }
          if ( !v39 )
          {
            v52 = v33;
            std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(&v54, &v52);
            v41 = std::wstring::wstring(v61, *(_QWORD *)(v33 + 8));
            std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(
              v59,
              v56,
              v41);
            LOBYTE(v42) = 1;
            std::wstring::_Tidy(v61, v42, 0);
          }
        }
        else
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            v37 = *(_QWORD *)(v33 + 8);
            LOWORD(v62) = 0;
            FormatRRASErrorString(
              &v62,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero",
              v37);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
          }
          *(_DWORD *)(v33 + 32) = 87;
        }
      }
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v56,
        v59);
      v8 = AddExistingEntryToXmlWriter(ppvObject, v56);
      if ( v8 )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          v26 = L"SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d";
LABEL_77:
          LOWORD(v62) = 0;
          FormatRRASErrorString(&v62, v26, v8);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
        }
LABEL_79:
        v6 = (RTL_SRWLOCK *)Instance;
        goto LABEL_80;
      }
      v8 = FlushXmlWriter(ppvObject);
      if ( !v8 )
      {
        for ( j = (struct _SSTP_TENANT_GATEWAY_ENTRY **)v54; j != *((struct _SSTP_TENANT_GATEWAY_ENTRY ***)&v54 + 1); ++j )
        {
          v8 = AddNewTenantEntry(*j);
          if ( v8 )
          {
LABEL_75:
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_79;
            v26 = L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewTenantEntry function failed with error %d";
            goto LABEL_77;
          }
          std::wstring::wstring(v61, *((_QWORD *)*j + 1));
          std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
            v11,
            &v51,
            v61);
          LOBYTE(v44) = 1;
          std::wstring::_Tidy(v61, v44, 0);
          v45 = *j;
          v46 = std::vector<std::wstring>::vector<std::wstring>(v56, v51 + 56);
          v8 = ReplaceGatewayList(v46, v45);
          if ( v8 )
          {
LABEL_45:
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_79;
            v26 = L"SstpSvcCreateUpdateTenantGatewayMapping: ReplaceGatewayList function failed with error %d";
            goto LABEL_77;
          }
        }
        goto LABEL_79;
      }
    }
    else
    {
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v56,
        v59);
      v8 = AddExistingEntryToXmlWriter(ppvObject, v56);
      if ( v8 )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_80;
        LOWORD(v62) = 0;
        FormatRRASErrorString(
          &v62,
          L"SstpSvcCreateUpdateTenantGatewayMapping: AddExistingEntryToXmlWriter failed with error %d",
          v8);
LABEL_12:
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_80;
        v9 = (const wchar_t *)&v62;
        goto LABEL_8;
      }
      for ( k = 0; (unsigned int)k < v4; k = (unsigned int)(k + 1) )
      {
        v13 = v53 + 40 * k;
        v14 = (__int64 *)(v13 + 8);
        std::wstring::wstring(v61, *(_QWORD *)(v13 + 8));
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          v11,
          &v52,
          v61);
        LOBYTE(v15) = 1;
        v16 = v52 == *((_QWORD *)Instance + 2);
        std::wstring::_Tidy(v61, v15, 0);
        if ( v16
          && (std::wstring::wstring(v61, *v14),
              v17 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(
                                v57,
                                v60,
                                v61),
              LOBYTE(v18) = 1,
              v19 = *v17 == v58,
              std::wstring::_Tidy(v61, v18, 0),
              v19) )
        {
          if ( *(_DWORD *)(v13 + 16) )
          {
            v22 = AddNewEntryToXmlWriter(ppvObject, (struct _SSTP_TENANT_GATEWAY_ENTRY *)v13);
            *(_DWORD *)(v13 + 32) = v22;
            v23 = v22;
            if ( (byte_18002E903 & 8) != 0 )
            {
              v24 = *v14;
              LOWORD(v62) = 0;
              FormatRRASErrorString(
                &v62,
                L"SstpSvcCreateUpdateTenantGatewayMapping: AddNewEntryToXmlWriter failed to add entry(%ws). Error %d",
                v24,
                v22);
              if ( (byte_18002E903 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
            }
            if ( !v23 )
            {
              v51 = v13;
              std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(&v54, &v51);
              v25 = std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<unsigned short * &>(
                      v57,
                      v13 + 8);
              std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Linsert(
                v57,
                v56,
                v25);
            }
          }
          else
          {
            if ( (byte_18002E903 & 8) != 0 )
            {
              v21 = *v14;
              LOWORD(v62) = 0;
              FormatRRASErrorString(
                &v62,
                L"SstpSvcCreateUpdateTenantGatewayMapping: Number of gateway for this tenant(%ws) is zero",
                v21);
              if ( (byte_18002E903 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
            }
            *(_DWORD *)(v13 + 32) = 87;
          }
        }
        else
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            v20 = *v14;
            LOWORD(v62) = 0;
            FormatRRASErrorString(
              &v62,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Trying to create a Tenant(%ws) entry that already exists",
              v20);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v62);
          }
          *(_DWORD *)(v13 + 32) = 183;
        }
        v4 = v50;
      }
      v8 = FlushXmlWriter(ppvObject);
      if ( !v8 )
      {
        for ( m = (struct _SSTP_TENANT_GATEWAY_ENTRY **)v54; m != *((struct _SSTP_TENANT_GATEWAY_ENTRY ***)&v54 + 1); ++m )
        {
          v8 = AddNewTenantEntry(*m);
          if ( v8 )
            goto LABEL_75;
          std::wstring::wstring(v61, *((_QWORD *)*m + 1));
          std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
            v11,
            &v51,
            v61);
          LOBYTE(v28) = 1;
          std::wstring::_Tidy(v61, v28, 0);
          v29 = *m;
          v30 = std::vector<std::wstring>::vector<std::wstring>(v56, v51 + 56);
          v8 = ReplaceGatewayList(v30, v29);
          if ( v8 )
            goto LABEL_45;
        }
        goto LABEL_79;
      }
    }
    if ( (byte_18002E903 & 8) != 0 )
    {
      v26 = L"SstpSvcCreateUpdateTenantGatewayMapping: FlushXmlWriter failed with error %d";
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  v8 = 2;
  if ( (byte_18002E903 & 8) != 0 )
  {
    v9 = L"SstpSvcCreateUpdateTenantGatewayMapping: xml file is not opened";
LABEL_8:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v9);
  }
LABEL_80:
  if ( ppvObject )
    ((void (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Release)(ppvObject);
  ppvObject = 0;
  ReleaseSRWLockExclusive(v6);
LABEL_83:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v57);
  std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::~vector<_SSTP_TENANT_GATEWAY_ENTRY *>(&v54);
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v59);
  return v8;
}

```

## disassembly

```asm
0x180014900  push    rbp
0x180014902  push    rbx
0x180014903  push    rsi
0x180014904  push    rdi
0x180014905  push    r12
0x180014907  push    r13
0x180014909  push    r14
0x18001490b  push    r15
0x18001490d  lea     rbp, [rsp-818h]
0x180014915  sub     rsp, 918h
0x18001491c  mov     rax, cs:__security_cookie
0x180014923  xor     rax, rsp
0x180014926  mov     [rbp+850h+var_50], rax
0x18001492d  mov     [rsp+950h+var_908], r9
0x180014932  mov     r15d, r8d
0x180014935  mov     [rsp+950h+var_920], r8d
0x18001493a  mov     esi, edx
0x18001493c  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180014941  mov     rcx, rax; this
0x180014944  mov     [rsp+950h+var_930], rax
0x180014949  mov     r14, rax
0x18001494c  mov     [rsp+950h+ppvObject], 0
0x180014955  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x18001495a  lea     rcx, [rbp+850h+var_8A0]
0x18001495e  mov     rbx, rax
0x180014961  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x180014966  xorps   xmm0, xmm0
0x180014969  mov     [rsp+950h+var_8F0], 0
0x180014972  lea     rcx, [rbp+850h+var_8C0]
0x180014976  movdqu  [rsp+950h+var_900], xmm0
0x18001497c  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x180014981  xor     ecx, ecx
0x180014983  xor     edx, edx; Val
0x180014985  mov     [rbp+850h+var_850], ecx
0x180014988  mov     r8d, 7FCh; Size
0x18001498e  lea     rcx, [rbp+850h+var_84C]; void *
0x180014992  call    memset_0
0x180014997  mov     ecx, 1
0x18001499c  call    GetSstpConfigFlag
0x1800149a1  test    eax, eax
0x1800149a3  jnz     short loc_1800149AD
0x1800149a5  lea     edi, [rax+32h]
0x1800149a8  jmp     loc_180015001
0x1800149ad  call    ?CheckClientAccessToXmlFile@@YAHK@Z; CheckClientAccessToXmlFile(ulong)
0x1800149b2  test    eax, eax
0x1800149b4  jnz     short loc_1800149BE
0x1800149b6  lea     edi, [rax+5]
0x1800149b9  jmp     loc_180015001
0x1800149be  mov     rcx, r14; SRWLock
0x1800149c1  call    cs:__imp_AcquireSRWLockExclusive
0x1800149c8  nop     dword ptr [rax+rax+00h]
0x1800149cd  test    rbx, rbx
0x1800149d0  jnz     short loc_180014A01
0x1800149d2  test    cs:byte_18002E903, 8
0x1800149d9  lea     edi, [rbx+2]
0x1800149dc  jz      loc_180014FD3
0x1800149e2  lea     r8, aSstpsvccreateu_1; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800149e9  lea     rdx, RasSSTPSvcTraceError
0x1800149f0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800149f7  call    McTemplateU0z_EventWriteTransfer
0x1800149fc  jmp     loc_180014FD3
0x180014a01  mov     rcx, rbx; this
0x180014a04  call    ?DeleteExistingContent@FileStream@@QEAAJXZ; FileStream::DeleteExistingContent(void)
0x180014a09  mov     rdx, rbx; struct IStream *
0x180014a0c  lea     rcx, [rsp+950h+ppvObject]; ppvObject
0x180014a11  call    ?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z; OpenXmlWriter(IXmlWriter * *,IStream *)
0x180014a16  mov     edi, eax
0x180014a18  test    eax, eax
0x180014a1a  jz      short loc_180014A55
0x180014a1c  test    cs:byte_18002E903, 8
0x180014a23  jz      loc_180014FD3
0x180014a29  xor     ecx, ecx
0x180014a2b  lea     rdx, aSstpsvccreateu_2; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014a32  mov     word ptr [rbp+850h+var_850], cx
0x180014a36  mov     r8d, eax
0x180014a39  lea     rcx, [rbp+850h+var_850]
0x180014a3d  call    FormatRRASErrorString
0x180014a42  test    cs:byte_18002E903, 8
0x180014a49  jz      loc_180014FD3
0x180014a4f  lea     r8, [rbp+850h+var_850]
0x180014a53  jmp     short loc_1800149E9
0x180014a55  lea     r13, [r14+8]
0x180014a59  test    esi, esi
0x180014a5b  jnz     loc_180014D25
0x180014a61  lea     rdx, [rbp+850h+var_8A0]
0x180014a65  lea     rcx, [rsp+950h+var_8E0]
0x180014a6a  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>> const &)
0x180014a6f  mov     rcx, [rsp+950h+ppvObject]
0x180014a74  lea     rdx, [rsp+950h+var_8E0]
0x180014a79  call    ?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::wstring,_lessstr,std::allocator<std::wstring>>)
0x180014a7e  mov     edi, eax
0x180014a80  test    eax, eax
0x180014a82  jz      short loc_180014AA3
0x180014a84  test    cs:byte_18002E903, 8
0x180014a8b  jz      loc_180014FD3
0x180014a91  xor     eax, eax
0x180014a93  lea     rdx, aSstpsvccreateu_7; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014a9a  mov     word ptr [rbp+850h+var_850], ax
0x180014a9e  mov     r8d, edi
0x180014aa1  jmp     short loc_180014A39
0x180014aa3  xor     r12d, r12d
0x180014aa6  lea     rsi, RasSSTPSvcTraceError
0x180014aad  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014ab4  cmp     r12d, r15d
0x180014ab7  jnb     loc_180014C65
0x180014abd  mov     rax, [rsp+950h+var_908]
0x180014ac2  lea     rcx, [r12+r12*4]
0x180014ac6  lea     rdi, [rax+rcx*8]
0x180014aca  lea     r15, [rdi+8]
0x180014ace  mov     rdx, [r15]
0x180014ad1  lea     rcx, [rbp+850h+var_878]
0x180014ad5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014ada  lea     r8, [rbp+850h+var_878]
0x180014ade  mov     rcx, r13
0x180014ae1  lea     rdx, [rsp+950h+var_910]
0x180014ae6  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180014aeb  mov     rax, [r13+8]
0x180014aef  lea     rcx, [rbp+850h+var_878]
0x180014af3  cmp     [rsp+950h+var_910], rax
0x180014af8  mov     dl, 1
0x180014afa  setz    bl
0x180014afd  xor     r8d, r8d
0x180014b00  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014b05  test    bl, bl
0x180014b07  jz      short loc_180014B42
0x180014b09  mov     rdx, [r15]
0x180014b0c  lea     rcx, [rbp+850h+var_878]
0x180014b10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014b15  lea     r8, [rbp+850h+var_878]
0x180014b19  lea     rdx, [rbp+850h+var_880]
0x180014b1d  lea     rcx, [rbp+850h+var_8C0]
0x180014b21  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180014b26  mov     rcx, [rbp+850h+var_8B8]
0x180014b2a  mov     dl, 1
0x180014b2c  cmp     [rax], rcx
0x180014b2f  lea     rcx, [rbp+850h+var_878]
0x180014b33  setz    bl
0x180014b36  xor     r8d, r8d
0x180014b39  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014b3e  test    bl, bl
0x180014b40  jnz     short loc_180014B88
0x180014b42  test    cs:byte_18002E903, 8
0x180014b49  jz      short loc_180014B7C
0x180014b4b  mov     r8, [r15]
0x180014b4e  lea     rdx, aSstpsvccreateu_6; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014b55  xor     eax, eax
0x180014b57  lea     rcx, [rbp+850h+var_850]
0x180014b5b  mov     word ptr [rbp+850h+var_850], ax
0x180014b5f  call    FormatRRASErrorString
0x180014b64  test    cs:byte_18002E903, 8
0x180014b6b  jz      short loc_180014B7C
0x180014b6d  lea     r8, [rbp+850h+var_850]
0x180014b71  mov     rdx, rsi
0x180014b74  mov     rcx, r14
0x180014b77  call    McTemplateU0z_EventWriteTransfer
0x180014b7c  mov     dword ptr [rdi+20h], 0B7h
0x180014b83  jmp     loc_180014C58
0x180014b88  cmp     dword ptr [rdi+10h], 0
0x180014b8c  jnz     short loc_180014BD4
0x180014b8e  test    cs:byte_18002E903, 8
0x180014b95  jz      short loc_180014BC8
0x180014b97  mov     r8, [r15]
0x180014b9a  lea     rdx, aSstpsvccreateu_10; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014ba1  xor     eax, eax
0x180014ba3  lea     rcx, [rbp+850h+var_850]
0x180014ba7  mov     word ptr [rbp+850h+var_850], ax
0x180014bab  call    FormatRRASErrorString
0x180014bb0  test    cs:byte_18002E903, 8
0x180014bb7  jz      short loc_180014BC8
0x180014bb9  lea     r8, [rbp+850h+var_850]
0x180014bbd  mov     rdx, rsi
0x180014bc0  mov     rcx, r14
0x180014bc3  call    McTemplateU0z_EventWriteTransfer
0x180014bc8  mov     dword ptr [rdi+20h], 57h ; 'W'
0x180014bcf  jmp     loc_180014C58
0x180014bd4  mov     rcx, [rsp+950h+ppvObject]; struct IXmlWriter *
0x180014bd9  mov     rdx, rdi; struct _SSTP_TENANT_GATEWAY_ENTRY *
0x180014bdc  call    ?AddNewEntryToXmlWriter@@YAKPEAUIXmlWriter@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; AddNewEntryToXmlWriter(IXmlWriter *,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180014be1  mov     [rdi+20h], eax
0x180014be4  mov     ebx, eax
0x180014be6  test    cs:byte_18002E903, 8
0x180014bed  jz      short loc_180014C23
0x180014bef  mov     r8, [r15]
0x180014bf2  lea     rdx, aSstpsvccreateu; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014bf9  xor     ecx, ecx
0x180014bfb  mov     r9d, eax
0x180014bfe  mov     word ptr [rbp+850h+var_850], cx
0x180014c02  lea     rcx, [rbp+850h+var_850]
0x180014c06  call    FormatRRASErrorString
0x180014c0b  test    cs:byte_18002E903, 8
0x180014c12  jz      short loc_180014C23
0x180014c14  lea     r8, [rbp+850h+var_850]
0x180014c18  mov     rdx, rsi
0x180014c1b  mov     rcx, r14
0x180014c1e  call    McTemplateU0z_EventWriteTransfer
0x180014c23  test    ebx, ebx
0x180014c25  jnz     short loc_180014C58
0x180014c27  lea     rdx, [rsp+950h+var_918]
0x180014c2c  mov     [rsp+950h+var_918], rdi
0x180014c31  lea     rcx, [rsp+950h+var_900]
0x180014c36  call    ?push_back@?$vector@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@V?$allocator@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@std@@@std@@QEAAX$$QEAPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; std::vector<_SSTP_TENANT_GATEWAY_ENTRY *>::push_back(_SSTP_TENANT_GATEWAY_ENTRY * &&)
0x180014c3b  mov     rdx, r15
0x180014c3e  lea     rcx, [rbp+850h+var_8C0]
0x180014c42  call    ??$_Buynode@AEAPEAG@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@AEAPEAG@Z; std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<ushort * &>(ushort * &)
0x180014c47  mov     r8, rax
0x180014c4a  lea     rdx, [rsp+950h+var_8E0]
0x180014c4f  lea     rcx, [rbp+850h+var_8C0]
0x180014c53  call    ?_Linsert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *,bool)
0x180014c58  mov     r15d, [rsp+950h+var_920]
0x180014c5d  inc     r12d
0x180014c60  jmp     loc_180014AB4
0x180014c65  mov     rcx, [rsp+950h+ppvObject]; struct IXmlWriter *
0x180014c6a  call    ?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z; FlushXmlWriter(IXmlWriter *)
0x180014c6f  mov     edi, eax
0x180014c71  test    eax, eax
0x180014c73  jz      short loc_180014C8E
0x180014c75  test    cs:byte_18002E903, 8
0x180014c7c  jz      loc_180014FCE
0x180014c82  lea     rdx, aSstpsvccreateu_8; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014c89  jmp     loc_180014FA4
0x180014c8e  mov     rbx, qword ptr [rsp+950h+var_900]
0x180014c93  cmp     rbx, qword ptr [rsp+950h+var_900+8]
0x180014c98  jz      loc_180014FCE
0x180014c9e  mov     rcx, [rbx]; struct _SSTP_TENANT_GATEWAY_ENTRY *
0x180014ca1  call    ?AddNewTenantEntry@@YAKPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; AddNewTenantEntry(_SSTP_TENANT_GATEWAY_ENTRY *)
0x180014ca6  mov     edi, eax
0x180014ca8  test    eax, eax
0x180014caa  jnz     loc_180014F94
0x180014cb0  mov     rdx, [rbx]
0x180014cb3  lea     rcx, [rbp+850h+var_878]
0x180014cb7  mov     rdx, [rdx+8]
0x180014cbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014cc0  lea     r8, [rbp+850h+var_878]
0x180014cc4  mov     rcx, r13
0x180014cc7  lea     rdx, [rsp+950h+var_918]
0x180014ccc  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180014cd1  xor     r8d, r8d
0x180014cd4  lea     rcx, [rbp+850h+var_878]
0x180014cd8  mov     dl, 1
0x180014cda  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014cdf  mov     rdx, [rsp+950h+var_918]
0x180014ce4  lea     rcx, [rsp+950h+var_8E0]
0x180014ce9  mov     rdi, [rbx]
0x180014cec  add     rdx, 38h ; '8'
0x180014cf0  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180014cf5  mov     rdx, rdi
0x180014cf8  mov     rcx, rax
0x180014cfb  call    ?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; ReplaceGatewayList(std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180014d00  mov     edi, eax
0x180014d02  test    eax, eax
0x180014d04  jnz     short loc_180014D0C
0x180014d06  add     rbx, 8
0x180014d0a  jmp     short loc_180014C93
0x180014d0c  test    cs:byte_18002E903, 8
0x180014d13  jz      loc_180014FCE
0x180014d19  lea     rdx, aSstpsvccreateu_4; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014d20  jmp     loc_180014FA4
0x180014d25  cmp     esi, 1
0x180014d28  jnz     loc_180014FD3
0x180014d2e  mov     r12d, [rsp+950h+var_920]
0x180014d33  lea     rsi, RasSSTPSvcTraceError
0x180014d3a  xor     r15d, r15d
0x180014d3d  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014d44  cmp     r15d, r12d
0x180014d47  jnb     loc_180014EC6
0x180014d4d  mov     rax, [rsp+950h+var_908]
0x180014d52  lea     rcx, [r15+r15*4]
0x180014d56  lea     rdi, [rax+rcx*8]
0x180014d5a  mov     rdx, [rdi+8]
0x180014d5e  lea     rcx, [rbp+850h+var_878]
0x180014d62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014d67  lea     r8, [rbp+850h+var_878]
0x180014d6b  mov     rcx, r13
0x180014d6e  lea     rdx, [rsp+950h+var_918]
0x180014d73  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180014d78  mov     rax, [r13+8]
0x180014d7c  lea     rcx, [rbp+850h+var_878]
0x180014d80  cmp     [rsp+950h+var_918], rax
0x180014d85  mov     dl, 1
0x180014d87  setz    bl
0x180014d8a  xor     r8d, r8d
0x180014d8d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014d92  test    bl, bl
0x180014d94  jz      short loc_180014DDD
0x180014d96  test    cs:byte_18002E903, 8
0x180014d9d  jz      short loc_180014DD1
0x180014d9f  mov     r8, [rdi+8]
0x180014da3  lea     rdx, aSstpsvccreateu_0; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180014daa  xor     eax, eax
0x180014dac  lea     rcx, [rbp+850h+var_850]
0x180014db0  mov     word ptr [rbp+850h+var_850], ax
0x180014db4  call    FormatRRASErrorString
0x180014db9  test    cs:byte_18002E903, 8
0x180014dc0  jz      short loc_180014DD1
0x180014dc2  lea     r8, [rbp+850h+var_850]
0x180014dc6  mov     rdx, rsi
0x180014dc9  mov     rcx, r14
0x180014dcc  call    McTemplateU0z_EventWriteTransfer
0x180014dd1  mov     dword ptr [rdi+20h], 490h
0x180014dd8  jmp     loc_180014EBE
  ... truncated ...
```
