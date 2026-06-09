# SstpSvcRemoveTenantGatewayMapping

- ea: `0x180015500`
- end: `0x1800158b1`
- name: `SstpSvcRemoveTenantGatewayMapping`
- size: `945`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006f00`
- `0x180008404`
- `0x180008514`
- `0x1800089dc`
- `0x180008b90`
- `0x180010358`
- `0x180010394`
- `0x18001052c`
- `0x18001056c`
- `0x1800106b4`
- `0x1800108d0`
- `0x180010d80`
- `0x180011444`
- `0x1800119a8`
- `0x180011b5c`
- `0x180011cd4`
- `0x1800122fc`
- `0x180012648`
- `0x1800132b8`
- `0x1800134bc`
- `0x180013824`
- `0x1800138dc`
- `0x180013ed8`
- `0x180015500`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015597`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015597`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155f5`

## string_xrefs

- `0x180015660`: `SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d`
- `0x1800155b9`: `SstpSvcRemoveTenantGatewayMapping: xml file is not opened`
- `0x1800156ed`: `SstpSvcRemoveTenantGatewayMapping: Tenant(%ws) entry does not exist`
- `0x18001578f`: `SstpSvcRemoveTenantGatewayMapping: ReplaceGatewayList failed with error %d`
- `0x1800157d6`: `SstpSvcRemoveTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d`
- `0x180015809`: `SstpSvcRemoveTenantGatewayMapping: FlushXmlWriter failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcRemoveTenantGatewayMapping(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  struct TenantGatewayMap *Instance; // r13
  FileStream *FileStream; // rbx
  unsigned int v7; // r14d
  const wchar_t *v8; // r8
  unsigned int v10; // eax
  __int64 i; // rsi
  _QWORD *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  _QWORD *v19; // rsi
  __int64 v20; // rbx
  _QWORD *v21; // rax
  _QWORD *v22; // rdi
  __int64 j; // rax
  _QWORD *v24; // r8
  struct IXmlWriter *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v26; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v30; // [rsp+48h] [rbp-B8h]
  _BYTE v31[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[40]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[40]; // [rsp+A8h] [rbp-58h] BYREF
  int v34; // [rsp+D0h] [rbp-30h] BYREF
  char v35[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v26 = a4;
  ppvObject = 0;
  Instance = TenantGatewayMap::GetInstance();
  FileStream = (FileStream *)TenantGatewayMap::GetFileStream(Instance);
  std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(v29);
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
  {
    v7 = 50;
    goto LABEL_12;
  }
  if ( !CheckClientAccessToXmlFile() )
  {
    v7 = 5;
    goto LABEL_12;
  }
  AcquireSRWLockExclusive((PSRWLOCK)Instance);
  if ( FileStream )
  {
    FileStream::DeleteExistingContent(FileStream);
    v10 = OpenXmlWriter(&ppvObject, (struct IStream *)FileStream);
    v7 = v10;
    if ( v10 )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_9;
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v34, L"SstpSvcCreateUpdateTenantGatewayMapping: OpenXmlWriter failed with error %d", v10);
    }
    else
    {
      for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      {
        v12 = &v26[5 * i];
        std::wstring::wstring(v33, v12[1]);
        std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
          (char *)Instance + 8,
          &v28,
          v33);
        v13 = v28;
        LOBYTE(v14) = 1;
        std::wstring::_Tidy(v33, v14, 0);
        if ( v13 == *((_QWORD *)Instance + 2) )
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            v15 = v12[1];
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"SstpSvcRemoveTenantGatewayMapping: Tenant(%ws) entry does not exist", v15);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v34);
          }
          *((_DWORD *)v12 + 8) = 1168;
        }
        else
        {
          v16 = std::wstring::wstring(v32, v12[1]);
          std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(
            v29,
            v31,
            v16);
          LOBYTE(v17) = 1;
          std::wstring::_Tidy(v32, v17, 0);
          v18 = std::vector<std::wstring>::vector<std::wstring>(v32, v13 + 56);
          v7 = ReplaceGatewayList(v18, v12);
          if ( v7 )
          {
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_9;
            LOWORD(v34) = 0;
            FormatRRASErrorString(
              &v34,
              L"SstpSvcRemoveTenantGatewayMapping: ReplaceGatewayList failed with error %d",
              v7);
            goto LABEL_16;
          }
        }
      }
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(
        v31,
        v29);
      v7 = AddExistingEntryToXmlWriter(ppvObject, v31);
      if ( v7 )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_9;
        LOWORD(v34) = 0;
        FormatRRASErrorString(
          &v34,
          L"SstpSvcRemoveTenantGatewayMapping: AddExistingEntryToXmlWriter function failed with error %d",
          v7);
      }
      else
      {
        v7 = FlushXmlWriter(ppvObject);
        if ( !v7 )
        {
          v19 = v30;
          v20 = *v30;
          while ( (_QWORD *)v20 != v19 )
          {
            std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::equal_range(
              (char *)Instance + 8,
              &v26,
              v20 + 24);
            v21 = (_QWORD *)*((_QWORD *)Instance + 2);
            v22 = v26;
            if ( v26 == (_QWORD *)*v21 && v27 == v21 )
            {
              std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear((char *)Instance + 8);
            }
            else
            {
              while ( v22 != v27 )
              {
                v24 = v22;
                v22 = (_QWORD *)*v22;
                std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::erase(
                  (char *)Instance + 8,
                  &v28,
                  v24);
              }
            }
            if ( !*(_BYTE *)(v20 + 65) )
            {
              if ( *(_BYTE *)(*(_QWORD *)(v20 + 16) + 65LL) )
              {
                for ( j = *(_QWORD *)(v20 + 8); !*(_BYTE *)(j + 65) && v20 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
                  v20 = j;
              }
              else
              {
                j = std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Min();
              }
              v20 = j;
            }
          }
          goto LABEL_9;
        }
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_9;
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"SstpSvcRemoveTenantGatewayMapping: FlushXmlWriter failed with error %d", v7);
      }
    }
LABEL_16:
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_9;
    v8 = (const wchar_t *)&v34;
    goto LABEL_8;
  }
  v7 = 2;
  if ( (byte_18002E903 & 8) != 0 )
  {
    v8 = L"SstpSvcRemoveTenantGatewayMapping: xml file is not opened";
LABEL_8:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v8);
  }
LABEL_9:
  if ( ppvObject )
    ((void (__fastcall *)(struct IXmlWriter *))ppvObject->lpVtbl->Release)(ppvObject);
  ppvObject = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)Instance);
LABEL_12:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(v29);
  return v7;
}

```

## disassembly

```asm
0x180015500  push    rbp
0x180015502  push    rbx
0x180015503  push    rsi
0x180015504  push    rdi
0x180015505  push    r12
0x180015507  push    r13
0x180015509  push    r14
0x18001550b  push    r15
0x18001550d  lea     rbp, [rsp-7E8h]
0x180015515  sub     rsp, 8E8h
0x18001551c  mov     rax, cs:__security_cookie
0x180015523  xor     rax, rsp
0x180015526  mov     [rbp+820h+var_50], rax
0x18001552d  mov     [rsp+920h+var_8F8], r9
0x180015532  mov     r12d, r8d
0x180015535  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x18001553a  mov     rcx, rax; this
0x18001553d  mov     [rsp+920h+ppvObject], 0
0x180015546  mov     r13, rax
0x180015549  call    ?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ; TenantGatewayMap::GetFileStream(void)
0x18001554e  lea     rcx, [rsp+920h+var_8E0]
0x180015553  mov     rbx, rax
0x180015556  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
0x18001555b  xor     ecx, ecx
0x18001555d  xor     edx, edx; Val
0x18001555f  mov     [rbp+820h+var_850], ecx
0x180015562  mov     r8d, 7FCh; Size
0x180015568  lea     rcx, [rbp+820h+var_84C]; void *
0x18001556c  call    memset_0
0x180015571  mov     ecx, 1
0x180015576  call    GetSstpConfigFlag
0x18001557b  test    eax, eax
0x18001557d  jnz     short loc_180015585
0x18001557f  lea     r14d, [rax+32h]
0x180015583  jmp     short loc_180015601
0x180015585  call    ?CheckClientAccessToXmlFile@@YAHK@Z; CheckClientAccessToXmlFile(ulong)
0x18001558a  test    eax, eax
0x18001558c  jnz     short loc_180015594
0x18001558e  lea     r14d, [rax+5]
0x180015592  jmp     short loc_180015601
0x180015594  mov     rcx, r13; SRWLock
0x180015597  call    cs:__imp_AcquireSRWLockExclusive
0x18001559e  nop     dword ptr [rax+rax+00h]
0x1800155a3  test    rbx, rbx
0x1800155a6  jnz     loc_180015632
0x1800155ac  test    cs:byte_18002E903, 8
0x1800155b3  lea     r14d, [rbx+2]
0x1800155b7  jz      short loc_1800155D3
0x1800155b9  lea     r8, aSstpsvcremovet; "SstpSvcRemoveTenantGatewayMapping: xml "...
0x1800155c0  lea     rdx, RasSSTPSvcTraceError
0x1800155c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800155ce  call    McTemplateU0z_EventWriteTransfer
0x1800155d3  mov     rcx, [rsp+920h+ppvObject]
0x1800155d8  test    rcx, rcx
0x1800155db  jz      short loc_1800155E9
0x1800155dd  mov     rax, [rcx]
0x1800155e0  mov     rax, [rax+10h]
0x1800155e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e9  mov     rcx, r13; SRWLock
0x1800155ec  mov     [rsp+920h+ppvObject], 0
0x1800155f5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800155fc  nop     dword ptr [rax+rax+00h]
0x180015601  lea     rcx, [rsp+920h+var_8E0]
0x180015606  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(void)
0x18001560b  mov     eax, r14d
0x18001560e  mov     rcx, [rbp+820h+var_50]
0x180015615  xor     rcx, rsp; StackCookie
0x180015618  call    __security_check_cookie
0x18001561d  add     rsp, 8E8h
0x180015624  pop     r15
0x180015626  pop     r14
0x180015628  pop     r13
0x18001562a  pop     r12
0x18001562c  pop     rdi
0x18001562d  pop     rsi
0x18001562e  pop     rbx
0x18001562f  pop     rbp
0x180015630  retn
0x180015632  mov     rcx, rbx; this
0x180015635  call    ?DeleteExistingContent@FileStream@@QEAAJXZ; FileStream::DeleteExistingContent(void)
0x18001563a  mov     rdx, rbx; struct IStream *
0x18001563d  lea     rcx, [rsp+920h+ppvObject]; ppvObject
0x180015642  call    ?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z; OpenXmlWriter(IXmlWriter * *,IStream *)
0x180015647  mov     r14d, eax
0x18001564a  mov     dil, 8
0x18001564d  test    eax, eax
0x18001564f  jz      short loc_18001568D
0x180015651  test    cs:byte_18002E903, dil
0x180015658  jz      loc_1800155D3
0x18001565e  xor     ecx, ecx
0x180015660  lea     rdx, aSstpsvccreateu_2; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x180015667  mov     word ptr [rbp+820h+var_850], cx
0x18001566b  mov     r8d, eax
0x18001566e  lea     rcx, [rbp+820h+var_850]
0x180015672  call    FormatRRASErrorString
0x180015677  test    cs:byte_18002E903, dil
0x18001567e  jz      loc_1800155D3
0x180015684  lea     r8, [rbp+820h+var_850]
0x180015688  jmp     loc_1800155C0
0x18001568d  lea     r15, [r13+8]
0x180015691  xor     esi, esi
0x180015693  cmp     esi, r12d
0x180015696  jnb     loc_1800157A2
0x18001569c  mov     rax, [rsp+920h+var_8F8]
0x1800156a1  lea     rcx, [rsi+rsi*4]
0x1800156a5  lea     r14, [rax+rcx*8]
0x1800156a9  mov     rdx, [r14+8]
0x1800156ad  lea     rcx, [rbp+820h+var_878]
0x1800156b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800156b6  lea     r8, [rbp+820h+var_878]
0x1800156ba  mov     rcx, r15
0x1800156bd  lea     rdx, [rsp+920h+var_8E8]
0x1800156c2  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x1800156c7  mov     rbx, [rsp+920h+var_8E8]
0x1800156cc  lea     rcx, [rbp+820h+var_878]
0x1800156d0  xor     r8d, r8d
0x1800156d3  mov     dl, 1
0x1800156d5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800156da  cmp     rbx, [r15+8]
0x1800156de  jnz     short loc_18001572D
0x1800156e0  test    cs:byte_18002E903, dil
0x1800156e7  jz      short loc_180015723
0x1800156e9  mov     r8, [r14+8]
0x1800156ed  lea     rdx, aSstpsvcremovet_2; "SstpSvcRemoveTenantGatewayMapping: Tena"...
0x1800156f4  xor     eax, eax
0x1800156f6  lea     rcx, [rbp+820h+var_850]
0x1800156fa  mov     word ptr [rbp+820h+var_850], ax
0x1800156fe  call    FormatRRASErrorString
0x180015703  test    cs:byte_18002E903, dil
0x18001570a  jz      short loc_180015723
0x18001570c  lea     r8, [rbp+820h+var_850]
0x180015710  lea     rdx, RasSSTPSvcTraceError
0x180015717  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001571e  call    McTemplateU0z_EventWriteTransfer
0x180015723  mov     dword ptr [r14+20h], 490h
0x18001572b  jmp     short loc_180015779
0x18001572d  mov     rdx, [r14+8]
0x180015731  lea     rcx, [rbp+820h+var_8A0]
0x180015735  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001573a  mov     r8, rax
0x18001573d  lea     rdx, [rsp+920h+var_8C0]
0x180015742  lea     rcx, [rsp+920h+var_8E0]
0x180015747  call    ??$insert@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::insert<std::wstring>(std::wstring &&)
0x18001574c  xor     r8d, r8d
0x18001574f  lea     rcx, [rbp+820h+var_8A0]
0x180015753  mov     dl, 1
0x180015755  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001575a  lea     rdx, [rbx+38h]
0x18001575e  lea     rcx, [rbp+820h+var_8A0]
0x180015762  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180015767  mov     rcx, rax
0x18001576a  mov     rdx, r14
0x18001576d  call    ?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; ReplaceGatewayList(std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180015772  mov     r14d, eax
0x180015775  test    eax, eax
0x180015777  jnz     short loc_180015780
0x180015779  inc     esi
0x18001577b  jmp     loc_180015693
0x180015780  test    cs:byte_18002E903, dil
0x180015787  jz      loc_1800155D3
0x18001578d  xor     eax, eax
0x18001578f  lea     rdx, aSstpsvcremovet_3; "SstpSvcRemoveTenantGatewayMapping: Repl"...
0x180015796  mov     word ptr [rbp+820h+var_850], ax
0x18001579a  mov     r8d, r14d
0x18001579d  jmp     loc_18001566E
0x1800157a2  lea     rdx, [rsp+920h+var_8E0]
0x1800157a7  lea     rcx, [rsp+920h+var_8C0]
0x1800157ac  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>> const &)
0x1800157b1  mov     rcx, [rsp+920h+ppvObject]
0x1800157b6  lea     rdx, [rsp+920h+var_8C0]
0x1800157bb  call    ?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::wstring,_lessstr,std::allocator<std::wstring>>)
0x1800157c0  mov     r14d, eax
0x1800157c3  test    eax, eax
0x1800157c5  jz      short loc_1800157E9
0x1800157c7  test    cs:byte_18002E903, dil
0x1800157ce  jz      loc_1800155D3
0x1800157d4  xor     eax, eax
0x1800157d6  lea     rdx, aSstpsvcremovet_1; "SstpSvcRemoveTenantGatewayMapping: AddE"...
0x1800157dd  mov     word ptr [rbp+820h+var_850], ax
0x1800157e1  mov     r8d, r14d
0x1800157e4  jmp     loc_18001566E
0x1800157e9  mov     rcx, [rsp+920h+ppvObject]; struct IXmlWriter *
0x1800157ee  call    ?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z; FlushXmlWriter(IXmlWriter *)
0x1800157f3  mov     r14d, eax
0x1800157f6  test    eax, eax
0x1800157f8  jz      short loc_18001581C
0x1800157fa  test    cs:byte_18002E903, dil
0x180015801  jz      loc_1800155D3
0x180015807  xor     eax, eax
0x180015809  lea     rdx, aSstpsvcremovet_0; "SstpSvcRemoveTenantGatewayMapping: Flus"...
0x180015810  mov     word ptr [rbp+820h+var_850], ax
0x180015814  mov     r8d, r14d
0x180015817  jmp     loc_18001566E
0x18001581c  mov     rsi, [rsp+920h+var_8D8]
0x180015821  mov     rbx, [rsi]
0x180015824  cmp     rbx, rsi
0x180015827  jz      loc_1800155D3
0x18001582d  lea     r8, [rbx+18h]
0x180015831  mov     rcx, r15
0x180015834  lea     rdx, [rsp+920h+var_8F8]
0x180015839  call    ?equal_range@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::equal_range(std::wstring const &)
0x18001583e  mov     rax, [r15+8]
0x180015842  mov     rdi, [rsp+920h+var_8F8]
0x180015847  cmp     rdi, [rax]
0x18001584a  jnz     short loc_180015874
0x18001584c  cmp     [rsp+920h+var_8F0], rax
0x180015851  jnz     short loc_180015874
0x180015853  mov     rcx, r15
0x180015856  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(void)
0x18001585b  xor     edi, edi
0x18001585d  cmp     [rbx+41h], dil
0x180015861  jnz     short loc_180015824
0x180015863  mov     rcx, [rbx+10h]
0x180015867  cmp     [rcx+41h], dil
0x18001586b  jnz     short loc_180015890
0x18001586d  call    ?_Min@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Min(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *)
0x180015872  jmp     short loc_1800158A9
0x180015874  cmp     rdi, [rsp+920h+var_8F0]
0x180015879  jz      short loc_18001585B
0x18001587b  mov     r8, rdi
0x18001587e  lea     rdx, [rsp+920h+var_8E8]
0x180015883  mov     rdi, [rdi]
0x180015886  mov     rcx, r15
0x180015889  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z
0x18001588e  jmp     short loc_180015874
0x180015890  mov     rax, [rbx+8]
0x180015894  jmp     short loc_1800158A3
0x180015896  cmp     rbx, [rax+10h]
0x18001589a  jnz     short loc_1800158A9
0x18001589c  mov     rbx, rax
0x18001589f  mov     rax, [rax+8]
0x1800158a3  cmp     [rax+41h], dil
0x1800158a7  jz      short loc_180015896
0x1800158a9  mov     rbx, rax
0x1800158ac  jmp     loc_180015824
```
