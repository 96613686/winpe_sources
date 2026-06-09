# SstpSvcRemoveTenantGatewayMapping

- ea: `0x180014490`
- end: `0x18001482c`
- name: `SstpSvcRemoveTenantGatewayMapping`
- size: `924`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007c34`
- `0x180007d34`
- `0x18000827c`
- `0x180008360`
- `0x18000f5ac`
- `0x18000f5e8`
- `0x18000f77c`
- `0x18000f7bc`
- `0x18000f8fc`
- `0x18000fb00`
- `0x18000ff74`
- `0x180010634`
- `0x180010b24`
- `0x180010cb8`
- `0x180010e30`
- `0x1800113dc`
- `0x180011700`
- `0x1800122fc`
- `0x1800124fc`
- `0x180012858`
- `0x180012910`
- `0x180012ef8`
- `0x180014490`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014527`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014527`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001457b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001457b`

## string_xrefs

- `0x1800145db`: `SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d`
- `0x18001453f`: `SstpSvcRemoveTenantGatewayMapping: xml file is not opened`
- `0x180014668`: `SstpSvcRemoveTenantGatewayMapping: Tenant(%ws) entry does not exist`
- `0x18001470a`: `SstpSvcRemoveTenantGatewayMapping: ReplaceGatewayList failed with error %d`
- `0x180014751`: `SstpSvcRemoveTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d`
- `0x180014784`: `SstpSvcRemoveTenantGatewayMapping: FlushXmlWriter failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcRemoveTenantGatewayMapping(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  struct TenantGatewayMap *Instance; // r13
  FileStream *FileStream; // rbx
  unsigned int v7; // ecx
  unsigned int v8; // r14d
  const wchar_t *v9; // r8
  unsigned int v11; // eax
  __int64 i; // rsi
  _QWORD *v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rsi
  __int64 v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  __int64 j; // rax
  _QWORD *v25; // r8
  struct IXmlWriter *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v27; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v28; // [rsp+30h] [rbp-D0h]
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  char v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v31; // [rsp+48h] [rbp-B8h]
  _BYTE v32[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[40]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[40]; // [rsp+A8h] [rbp-58h] BYREF
  int v35; // [rsp+D0h] [rbp-30h] BYREF
  char v36[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v27 = a4;
  ppvObject = 0;
  Instance = TenantGatewayMap::GetInstance();
  FileStream = (FileStream *)TenantGatewayMap::GetFileStream(Instance);
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v30);
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
  {
    v8 = 50;
    goto LABEL_12;
  }
  if ( !(unsigned int)CheckClientAccessToXmlFile(v7) )
  {
    v8 = 5;
    goto LABEL_12;
  }
  AcquireSRWLockExclusive((PSRWLOCK)Instance);
  if ( FileStream )
  {
    FileStream::DeleteExistingContent(FileStream);
    v11 = OpenXmlWriter(&ppvObject, (struct IStream *)FileStream);
    v8 = v11;
    if ( v11 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_9;
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d", v11);
    }
    else
    {
      for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      {
        v13 = &v27[5 * i];
        std::wstring::wstring(v34, v13[1]);
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          (char *)Instance + 8,
          &v29,
          v34);
        v14 = v29;
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v34, v15, 0);
        if ( v14 == *((_QWORD *)Instance + 2) )
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            v16 = v13[1];
            LOWORD(v35) = 0;
            FormatRRASErrorString(&v35, L"SstpSvcRemoveTenantGatewayMapping: Tenant(%ws) entry does not exist", v16);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v35);
          }
          *((_DWORD *)v13 + 8) = 1168;
        }
        else
        {
          v17 = std::wstring::wstring(v33, v13[1]);
          std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(
            v30,
            v32,
            v17);
          LOBYTE(v18) = 1;
          std::wstring::_Tidy(v33, v18, 0);
          v19 = std::vector<std::wstring>::vector<std::wstring>(v33, v14 + 56);
          v8 = ReplaceGatewayList(v19, v13);
          if ( v8 )
          {
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_9;
            LOWORD(v35) = 0;
            FormatRRASErrorString(
              &v35,
              L"SstpSvcRemoveTenantGatewayMapping: ReplaceGatewayList failed with error %d",
              v8);
            goto LABEL_16;
          }
        }
      }
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v32,
        v30);
      v8 = AddExistingEntryToXmlWriter(ppvObject, v32);
      if ( v8 )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_9;
        LOWORD(v35) = 0;
        FormatRRASErrorString(
          &v35,
          L"SstpSvcRemoveTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d",
          v8);
      }
      else
      {
        v8 = FlushXmlWriter(ppvObject);
        if ( !v8 )
        {
          v20 = v31;
          v21 = *v31;
          while ( (_QWORD *)v21 != v20 )
          {
            std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::equal_range(
              (char *)Instance + 8,
              &v27,
              v21 + 24);
            v22 = (_QWORD *)*((_QWORD *)Instance + 2);
            v23 = v27;
            if ( v27 == (_QWORD *)*v22 && v28 == v22 )
            {
              std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear((char *)Instance + 8);
            }
            else
            {
              while ( v23 != v28 )
              {
                v25 = v23;
                v23 = (_QWORD *)*v23;
                std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::erase(
                  (char *)Instance + 8,
                  &v29,
                  v25);
              }
            }
            if ( !*(_BYTE *)(v21 + 65) )
            {
              if ( *(_BYTE *)(*(_QWORD *)(v21 + 16) + 65LL) )
              {
                for ( j = *(_QWORD *)(v21 + 8); !*(_BYTE *)(j + 65) && v21 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
                  v21 = j;
              }
              else
              {
                j = std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Min();
              }
              v21 = j;
            }
          }
          goto LABEL_9;
        }
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_9;
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"SstpSvcRemoveTenantGatewayMapping: FlushXmlWriter failed with error %d", v8);
      }
    }
LABEL_16:
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_9;
    v9 = (const wchar_t *)&v35;
    goto LABEL_8;
  }
  v8 = 2;
  if ( (byte_18002D803 & 8) != 0 )
  {
    v9 = L"SstpSvcRemoveTenantGatewayMapping: xml file is not opened";
LABEL_8:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v9);
  }
LABEL_9:
  if ( ppvObject )
    ((void (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Release)(ppvObject);
  ppvObject = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)Instance);
LABEL_12:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v30);
  return v8;
}

```

## disassembly

```asm
0x180014490  push    rbp
0x180014492  push    rbx
0x180014493  push    rsi
0x180014494  push    rdi
0x180014495  push    r12
0x180014497  push    r13
0x180014499  push    r14
0x18001449b  push    r15
0x18001449d  lea     rbp, [rsp-7E8h]
0x1800144a5  sub     rsp, 8E8h
0x1800144ac  mov     rax, cs:__security_cookie
0x1800144b3  xor     rax, rsp
0x1800144b6  mov     [rbp+820h+var_50], rax
0x1800144bd  mov     [rsp+920h+var_8F8], r9
0x1800144c2  mov     r12d, r8d
0x1800144c5  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x1800144ca  mov     rcx, rax; this
0x1800144cd  mov     [rsp+920h+ppvObject], 0
0x1800144d6  mov     r13, rax
0x1800144d9  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x1800144de  lea     rcx, [rsp+920h+var_8E0]
0x1800144e3  mov     rbx, rax
0x1800144e6  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x1800144eb  xor     ecx, ecx
0x1800144ed  xor     edx, edx; Val
0x1800144ef  mov     [rbp+820h+var_850], ecx
0x1800144f2  mov     r8d, 7FCh; Size
0x1800144f8  lea     rcx, [rbp+820h+var_84C]; void *
0x1800144fc  call    memset_0
0x180014501  mov     ecx, 1
0x180014506  call    GetSstpConfigFlag
0x18001450b  test    eax, eax
0x18001450d  jnz     short loc_180014515
0x18001450f  lea     r14d, [rax+32h]
0x180014513  jmp     short loc_180014581
0x180014515  call    ?CheckClientAccessToXmlFile@@YAHK@Z; CheckClientAccessToXmlFile(ulong)
0x18001451a  test    eax, eax
0x18001451c  jnz     short loc_180014524
0x18001451e  lea     r14d, [rax+5]
0x180014522  jmp     short loc_180014581
0x180014524  mov     rcx, r13; SRWLock
0x180014527  call    cs:__imp_AcquireSRWLockExclusive
0x18001452d  test    rbx, rbx
0x180014530  jnz     short loc_1800145B1
0x180014532  test    cs:byte_18002D803, 8
0x180014539  lea     r14d, [rbx+2]
0x18001453d  jz      short loc_180014559
0x18001453f  lea     r8, aSstpsvcremovet; "SstpSvcRemoveTenantGatewayMapping: xml "...
0x180014546  lea     rdx, RasSSTPSvcTraceError
0x18001454d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014554  call    McTemplateU0z_EventWriteTransfer
0x180014559  mov     rcx, [rsp+920h+ppvObject]
0x18001455e  test    rcx, rcx
0x180014561  jz      short loc_18001456F
0x180014563  mov     rax, [rcx]
0x180014566  mov     rax, [rax+10h]
0x18001456a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001456f  mov     rcx, r13; SRWLock
0x180014572  mov     [rsp+920h+ppvObject], 0
0x18001457b  call    cs:__imp_ReleaseSRWLockExclusive
0x180014581  lea     rcx, [rsp+920h+var_8E0]
0x180014586  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(void)
0x18001458b  mov     eax, r14d
0x18001458e  mov     rcx, [rbp+820h+var_50]
0x180014595  xor     rcx, rsp; StackCookie
0x180014598  call    __security_check_cookie
0x18001459d  add     rsp, 8E8h
0x1800145a4  pop     r15
0x1800145a6  pop     r14
0x1800145a8  pop     r13
0x1800145aa  pop     r12
0x1800145ac  pop     rdi
0x1800145ad  pop     rsi
0x1800145ae  pop     rbx
0x1800145af  pop     rbp
0x1800145b0  retn
0x1800145b1  mov     rcx, rbx; this
0x1800145b4  call    ?DeleteExistingContent@FileStream@@QEAAJXZ; FileStream::DeleteExistingContent(void)
0x1800145b9  mov     rdx, rbx; struct IStream *
0x1800145bc  lea     rcx, [rsp+920h+ppvObject]; ppvObject
0x1800145c1  call    ?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z; OpenXmlWriter(IXmlWriter * *,IStream *)
0x1800145c6  mov     r14d, eax
0x1800145c9  mov     dil, 8
0x1800145cc  test    eax, eax
0x1800145ce  jz      short loc_180014608
0x1800145d0  test    cs:byte_18002D803, dil
0x1800145d7  jz      short loc_180014559
0x1800145d9  xor     ecx, ecx
0x1800145db  lea     rdx, aSstpsvccreateu_2; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800145e2  mov     word ptr [rbp+820h+var_850], cx
0x1800145e6  mov     r8d, eax
0x1800145e9  lea     rcx, [rbp+820h+var_850]
0x1800145ed  call    FormatRRASErrorString
0x1800145f2  test    cs:byte_18002D803, dil
0x1800145f9  jz      loc_180014559
0x1800145ff  lea     r8, [rbp+820h+var_850]
0x180014603  jmp     loc_180014546
0x180014608  lea     r15, [r13+8]
0x18001460c  xor     esi, esi
0x18001460e  cmp     esi, r12d
0x180014611  jnb     loc_18001471D
0x180014617  mov     rax, [rsp+920h+var_8F8]
0x18001461c  lea     rcx, [rsi+rsi*4]
0x180014620  lea     r14, [rax+rcx*8]
0x180014624  mov     rdx, [r14+8]
0x180014628  lea     rcx, [rbp+820h+var_878]
0x18001462c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014631  lea     r8, [rbp+820h+var_878]
0x180014635  mov     rcx, r15
0x180014638  lea     rdx, [rsp+920h+var_8E8]
0x18001463d  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x180014642  mov     rbx, [rsp+920h+var_8E8]
0x180014647  lea     rcx, [rbp+820h+var_878]
0x18001464b  xor     r8d, r8d
0x18001464e  mov     dl, 1
0x180014650  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014655  cmp     rbx, [r15+8]
0x180014659  jnz     short loc_1800146A8
0x18001465b  test    cs:byte_18002D803, dil
0x180014662  jz      short loc_18001469E
0x180014664  mov     r8, [r14+8]
0x180014668  lea     rdx, aSstpsvcremovet_2; "SstpSvcRemoveTenantGatewayMapping: Tena"...
0x18001466f  xor     eax, eax
0x180014671  lea     rcx, [rbp+820h+var_850]
0x180014675  mov     word ptr [rbp+820h+var_850], ax
0x180014679  call    FormatRRASErrorString
0x18001467e  test    cs:byte_18002D803, dil
0x180014685  jz      short loc_18001469E
0x180014687  lea     r8, [rbp+820h+var_850]
0x18001468b  lea     rdx, RasSSTPSvcTraceError
0x180014692  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014699  call    McTemplateU0z_EventWriteTransfer
0x18001469e  mov     dword ptr [r14+20h], 490h
0x1800146a6  jmp     short loc_1800146F4
0x1800146a8  mov     rdx, [r14+8]
0x1800146ac  lea     rcx, [rbp+820h+var_8A0]
0x1800146b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800146b5  mov     r8, rax
0x1800146b8  lea     rdx, [rsp+920h+var_8C0]
0x1800146bd  lea     rcx, [rsp+920h+var_8E0]
0x1800146c2  call    ??$insert@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(std::wstring &&)
0x1800146c7  xor     r8d, r8d
0x1800146ca  lea     rcx, [rbp+820h+var_8A0]
0x1800146ce  mov     dl, 1
0x1800146d0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800146d5  lea     rdx, [rbx+38h]
0x1800146d9  lea     rcx, [rbp+820h+var_8A0]
0x1800146dd  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800146e2  mov     rcx, rax
0x1800146e5  mov     rdx, r14
0x1800146e8  call    ?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; ReplaceGatewayList(std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x1800146ed  mov     r14d, eax
0x1800146f0  test    eax, eax
0x1800146f2  jnz     short loc_1800146FB
0x1800146f4  inc     esi
0x1800146f6  jmp     loc_18001460E
0x1800146fb  test    cs:byte_18002D803, dil
0x180014702  jz      loc_180014559
0x180014708  xor     eax, eax
0x18001470a  lea     rdx, aSstpsvcremovet_3; "SstpSvcRemoveTenantGatewayMapping: Repl"...
0x180014711  mov     word ptr [rbp+820h+var_850], ax
0x180014715  mov     r8d, r14d
0x180014718  jmp     loc_1800145E9
0x18001471d  lea     rdx, [rsp+920h+var_8E0]
0x180014722  lea     rcx, [rsp+920h+var_8C0]
0x180014727  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>> const &)
0x18001472c  mov     rcx, [rsp+920h+ppvObject]
0x180014731  lea     rdx, [rsp+920h+var_8C0]
0x180014736  call    ?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::wstring,_lessstr,std::allocator<std::wstring>>)
0x18001473b  mov     r14d, eax
0x18001473e  test    eax, eax
0x180014740  jz      short loc_180014764
0x180014742  test    cs:byte_18002D803, dil
0x180014749  jz      loc_180014559
0x18001474f  xor     eax, eax
0x180014751  lea     rdx, aSstpsvcremovet_1; "SstpSvcRemoveTenantGatewayMapping: AddE"...
0x180014758  mov     word ptr [rbp+820h+var_850], ax
0x18001475c  mov     r8d, r14d
0x18001475f  jmp     loc_1800145E9
0x180014764  mov     rcx, [rsp+920h+ppvObject]; struct IXmlWriter *
0x180014769  call    ?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z; FlushXmlWriter(IXmlWriter *)
0x18001476e  mov     r14d, eax
0x180014771  test    eax, eax
0x180014773  jz      short loc_180014797
0x180014775  test    cs:byte_18002D803, dil
0x18001477c  jz      loc_180014559
0x180014782  xor     eax, eax
0x180014784  lea     rdx, aSstpsvcremovet_0; "SstpSvcRemoveTenantGatewayMapping: Flus"...
0x18001478b  mov     word ptr [rbp+820h+var_850], ax
0x18001478f  mov     r8d, r14d
0x180014792  jmp     loc_1800145E9
0x180014797  mov     rsi, [rsp+920h+var_8D8]
0x18001479c  mov     rbx, [rsi]
0x18001479f  cmp     rbx, rsi
0x1800147a2  jz      loc_180014559
0x1800147a8  lea     r8, [rbx+18h]
0x1800147ac  mov     rcx, r15
0x1800147af  lea     rdx, [rsp+920h+var_8F8]
0x1800147b4  call    ?equal_range@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::equal_range(std::wstring const &)
0x1800147b9  mov     rax, [r15+8]
0x1800147bd  mov     rdi, [rsp+920h+var_8F8]
0x1800147c2  cmp     rdi, [rax]
0x1800147c5  jnz     short loc_1800147EF
0x1800147c7  cmp     [rsp+920h+var_8F0], rax
0x1800147cc  jnz     short loc_1800147EF
0x1800147ce  mov     rcx, r15
0x1800147d1  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(void)
0x1800147d6  xor     edi, edi
0x1800147d8  cmp     [rbx+41h], dil
0x1800147dc  jnz     short loc_18001479F
0x1800147de  mov     rcx, [rbx+10h]
0x1800147e2  cmp     [rcx+41h], dil
0x1800147e6  jnz     short loc_18001480B
0x1800147e8  call    ?_Min@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Min(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *)
0x1800147ed  jmp     short loc_180014824
0x1800147ef  cmp     rdi, [rsp+920h+var_8F0]
0x1800147f4  jz      short loc_1800147D6
0x1800147f6  mov     r8, rdi
0x1800147f9  lea     rdx, [rsp+920h+var_8E8]
0x1800147fe  mov     rdi, [rdi]
0x180014801  mov     rcx, r15
0x180014804  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z
0x180014809  jmp     short loc_1800147EF
0x18001480b  mov     rax, [rbx+8]
0x18001480f  jmp     short loc_18001481E
0x180014811  cmp     rbx, [rax+10h]
0x180014815  jnz     short loc_180014824
0x180014817  mov     rbx, rax
0x18001481a  mov     rax, [rax+8]
0x18001481e  cmp     [rax+41h], dil
0x180014822  jz      short loc_180014811
0x180014824  mov     rbx, rax
0x180014827  jmp     loc_18001479F
```
