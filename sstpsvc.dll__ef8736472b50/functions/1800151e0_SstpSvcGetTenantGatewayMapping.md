# SstpSvcGetTenantGatewayMapping

- ea: `0x1800151e0`
- end: `0x1800154fa`
- name: `SstpSvcGetTenantGatewayMapping`
- size: `794`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006f00`
- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x1800104f4`
- `0x18001052c`
- `0x1800106b4`
- `0x180010998`
- `0x180011820`
- `0x1800134bc`
- `0x180013524`
- `0x180013ed8`
- `0x1800151e0`
- `0x18001cd60`
- `0x18001cda0`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015262`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015262`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800154c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800154c1`

## string_xrefs

- `0x1800153ae`: `SstpSvcGetTenantGatewayMapping: CreateTenantGatewayEntryStruct failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcGetTenantGatewayMapping(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, void **a5)
{
  struct TenantGatewayMap *Instance; // rbx
  char *v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rdx
  unsigned int TenantGatewayEntryStruct; // edi
  void *v13; // rax
  __int64 v14; // rdi
  const wchar_t *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rbx
  wchar_t *v19; // rax
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r15
  void *v23; // rax
  _QWORD *v24; // rbx
  __int64 i; // rsi
  __int64 v26; // rsi
  _QWORD *v27; // rdi
  wchar_t *v28; // rax
  __int64 v29; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h]
  _BYTE v33[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[40]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[40]; // [rsp+98h] [rbp-68h] BYREF
  int v36; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v37[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  Instance = TenantGatewayMap::GetInstance();
  SRWLock = (PSRWLOCK)Instance;
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
    return 50;
  v9 = (char *)Instance + 8;
  AcquireSRWLockShared((PSRWLOCK)Instance);
  *a4 = 0;
  *a5 = 0;
  if ( !a3 )
  {
    v22 = *((unsigned int *)Instance + 6);
    v31 = 0;
    v30 = 0;
    if ( (_DWORD)v22 )
    {
      v23 = MIDL_user_allocate(40 * v22);
      *a5 = v23;
      if ( !v23 )
      {
LABEL_10:
        TenantGatewayEntryStruct = 14;
        if ( (byte_18002E903 & 8) == 0 )
        {
LABEL_13:
          std::vector<std::wstring>::_Tidy(&v30);
LABEL_29:
          MIDL_user_free(*a5);
          *a4 = 0;
          goto LABEL_30;
        }
        v15 = L"SstpSvcGetTenantGatewayMapping: Failed to allocate memory for SSTP_TENANT_GATEWAY_ENTRY structure.";
LABEL_12:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v15);
        goto LABEL_13;
      }
    }
    v24 = (_QWORD *)*((_QWORD *)Instance + 2);
    TenantGatewayEntryStruct = 0;
    for ( i = 0; ; i = (unsigned int)(v29 + 1) )
    {
      v24 = (_QWORD *)*v24;
      LODWORD(v29) = i;
      if ( v24 == *((_QWORD **)v9 + 1) )
      {
        *a4 = v22;
        std::vector<std::wstring>::_Tidy(&v30);
        goto LABEL_30;
      }
      std::vector<std::wstring>::operator=(&v30, v24 + 7);
      v26 = (__int64)*a5 + 40 * i;
      v27 = (_QWORD *)std::vector<std::wstring>::vector<std::wstring>(v33, &v30);
      v28 = (wchar_t *)std::wstring::wstring(v34, v24 + 2);
      TenantGatewayEntryStruct = CreateTenantGatewayEntryStruct(v28, v27, v26);
      if ( TenantGatewayEntryStruct )
        break;
    }
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_13;
    v21 = TenantGatewayEntryStruct;
    LOWORD(v36) = 0;
LABEL_17:
    FormatRRASErrorString(
      &v36,
      L"SstpSvcGetTenantGatewayMapping: CreateTenantGatewayEntryStruct failed with error %d",
      v21);
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_13;
    v15 = (const wchar_t *)&v36;
    goto LABEL_12;
  }
  std::wstring::wstring(v35, a3);
  std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
    (char *)Instance + 8,
    &v29,
    v35);
  v10 = v29;
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v35, v11, 0);
  if ( v10 == *((_QWORD *)v9 + 1) )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v36, L"SstpSvcGetTenantGatewayMapping: Tenant(%ws) entry does not exist", a3);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v36);
    }
    TenantGatewayEntryStruct = 1168;
    goto LABEL_29;
  }
  std::vector<std::wstring>::vector<std::wstring>(&v30, v10 + 56);
  v13 = MIDL_user_allocate(0x28u);
  *a5 = v13;
  v14 = (__int64)v13;
  if ( !v13 )
    goto LABEL_10;
  v16 = std::vector<std::wstring>::vector<std::wstring>(v33, &v30);
  v17 = v10 + 16;
  v18 = (_QWORD *)v16;
  v19 = (wchar_t *)std::wstring::wstring(v34, v17);
  v20 = CreateTenantGatewayEntryStruct(v19, v18, v14);
  TenantGatewayEntryStruct = v20;
  if ( v20 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_13;
    v21 = v20;
    LOWORD(v36) = 0;
    goto LABEL_17;
  }
  *a4 = 1;
  std::vector<std::wstring>::_Tidy(&v30);
LABEL_30:
  ReleaseSRWLockShared(SRWLock);
  return TenantGatewayEntryStruct;
}

```

## disassembly

```asm
0x1800151e0  mov     [rsp-8+arg_0], rbx
0x1800151e5  push    rbp
0x1800151e6  push    rsi
0x1800151e7  push    rdi
0x1800151e8  push    r12
0x1800151ea  push    r13
0x1800151ec  push    r14
0x1800151ee  push    r15
0x1800151f0  lea     rbp, [rsp-7D0h]
0x1800151f8  sub     rsp, 8D0h
0x1800151ff  mov     rax, cs:__security_cookie
0x180015206  xor     rax, rsp
0x180015209  mov     [rbp+800h+var_40], rax
0x180015210  mov     r13, [rbp+800h+arg_20]
0x180015217  mov     r12, r9
0x18001521a  mov     rdi, r8
0x18001521d  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180015222  mov     rbx, rax
0x180015225  mov     [rsp+900h+SRWLock], rax
0x18001522a  xor     eax, eax
0x18001522c  lea     rcx, [rbp+800h+var_83C]; void *
0x180015230  xor     edx, edx; Val
0x180015232  mov     [rbp+800h+var_840], eax
0x180015235  mov     r8d, 7FCh; Size
0x18001523b  call    memset_0
0x180015240  mov     r15d, 1
0x180015246  mov     ecx, r15d
0x180015249  call    GetSstpConfigFlag
0x18001524e  test    eax, eax
0x180015250  jnz     short loc_18001525B
0x180015252  lea     eax, [r15+31h]
0x180015256  jmp     loc_1800154CF
0x18001525b  mov     rcx, rbx; SRWLock
0x18001525e  lea     r14, [rbx+8]
0x180015262  call    cs:__imp_AcquireSRWLockShared
0x180015269  nop     dword ptr [rax+rax+00h]
0x18001526e  mov     dword ptr [r12], 0
0x180015276  mov     qword ptr [r13+0], 0
0x18001527e  test    rdi, rdi
0x180015281  jz      loc_1800153E3
0x180015287  mov     rdx, rdi
0x18001528a  lea     rcx, [rbp+800h+var_868]
0x18001528e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180015293  lea     r8, [rbp+800h+var_868]
0x180015297  mov     rcx, r14
0x18001529a  lea     rdx, [rsp+900h+var_8E0]
0x18001529f  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x1800152a4  mov     rbx, [rsp+900h+var_8E0]
0x1800152a9  lea     rcx, [rbp+800h+var_868]
0x1800152ad  xor     r8d, r8d
0x1800152b0  mov     dl, r15b
0x1800152b3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800152b8  cmp     rbx, [r14+8]
0x1800152bc  jnz     short loc_18001530A
0x1800152be  test    cs:byte_18002E903, 8
0x1800152c5  jz      short loc_180015300
0x1800152c7  xor     eax, eax
0x1800152c9  lea     rdx, aSstpsvcgettena_0; "SstpSvcGetTenantGatewayMapping: Tenant("...
0x1800152d0  mov     r8, rdi
0x1800152d3  mov     word ptr [rbp+800h+var_840], ax
0x1800152d7  lea     rcx, [rbp+800h+var_840]
0x1800152db  call    FormatRRASErrorString
0x1800152e0  test    cs:byte_18002E903, 8
0x1800152e7  jz      short loc_180015300
0x1800152e9  lea     r8, [rbp+800h+var_840]
0x1800152ed  lea     rdx, RasSSTPSvcTraceError
0x1800152f4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800152fb  call    McTemplateU0z_EventWriteTransfer
0x180015300  mov     edi, 490h
0x180015305  jmp     loc_1800154AB
0x18001530a  lea     rsi, [rbx+10h]
0x18001530e  lea     rdx, [rsi+28h]
0x180015312  lea     rcx, [rsp+900h+var_8D8]
0x180015317  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18001531c  mov     ecx, 28h ; '('; size
0x180015321  call    MIDL_user_allocate
0x180015326  mov     [r13+0], rax
0x18001532a  mov     rdi, rax
0x18001532d  test    rax, rax
0x180015330  jnz     short loc_180015369
0x180015332  test    cs:byte_18002E903, 8
0x180015339  mov     edi, 0Eh
0x18001533e  jz      short loc_18001535A
0x180015340  lea     r8, aSstpsvcgettena; "SstpSvcGetTenantGatewayMapping: Failed "...
0x180015347  lea     rdx, RasSSTPSvcTraceError
0x18001534e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015355  call    McTemplateU0z_EventWriteTransfer
0x18001535a  lea     rcx, [rsp+900h+var_8D8]
0x18001535f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180015364  jmp     loc_1800154AB
0x180015369  lea     rdx, [rsp+900h+var_8D8]
0x18001536e  lea     rcx, [rsp+900h+var_8B0]
0x180015373  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180015378  mov     rdx, rsi
0x18001537b  lea     rcx, [rsp+900h+var_890]
0x180015380  mov     rbx, rax
0x180015383  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015388  mov     r8, rdi
0x18001538b  mov     rdx, rbx
0x18001538e  mov     rcx, rax; Source
0x180015391  call    ?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; CreateTenantGatewayEntryStruct(std::wstring,std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180015396  mov     edi, eax
0x180015398  test    eax, eax
0x18001539a  jz      short loc_1800153D0
0x18001539c  test    cs:byte_18002E903, 8
0x1800153a3  jz      short loc_18001535A
0x1800153a5  xor     ecx, ecx
0x1800153a7  mov     r8d, eax
0x1800153aa  mov     word ptr [rbp+800h+var_840], cx
0x1800153ae  lea     rdx, aSstpsvcgettena_1; "SstpSvcGetTenantGatewayMapping: CreateT"...
0x1800153b5  lea     rcx, [rbp+800h+var_840]
0x1800153b9  call    FormatRRASErrorString
0x1800153be  test    cs:byte_18002E903, 8
0x1800153c5  jz      short loc_18001535A
0x1800153c7  lea     r8, [rbp+800h+var_840]
0x1800153cb  jmp     loc_180015347
0x1800153d0  lea     rcx, [rsp+900h+var_8D8]
0x1800153d5  mov     [r12], r15d
0x1800153d9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800153de  jmp     loc_1800154BC
0x1800153e3  mov     r15d, [r14+10h]
0x1800153e7  xorps   xmm0, xmm0
0x1800153ea  mov     [rsp+900h+var_8C8], 0
0x1800153f3  movdqu  [rsp+900h+var_8D8], xmm0
0x1800153f9  test    r15d, r15d
0x1800153fc  jz      short loc_180015418
0x1800153fe  lea     rcx, [r15+r15*4]
0x180015402  shl     rcx, 3; size
0x180015406  call    MIDL_user_allocate
0x18001540b  mov     [r13+0], rax
0x18001540f  test    rax, rax
0x180015412  jz      loc_180015332
0x180015418  mov     rbx, [r14+8]
0x18001541c  xor     edi, edi
0x18001541e  xor     esi, esi
0x180015420  mov     rbx, [rbx]
0x180015423  lea     rcx, [rsp+900h+var_8D8]
0x180015428  mov     dword ptr [rsp+900h+var_8E0], esi
0x18001542c  cmp     rbx, [r14+8]
0x180015430  jz      short loc_18001549E
0x180015432  lea     rdx, [rbx+38h]
0x180015436  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x18001543b  mov     rax, [r13+0]
0x18001543f  lea     rcx, [rsi+rsi*4]
0x180015443  lea     rdx, [rsp+900h+var_8D8]
0x180015448  lea     rsi, [rax+rcx*8]
0x18001544c  lea     rcx, [rsp+900h+var_8B0]
0x180015451  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180015456  lea     rdx, [rbx+10h]
0x18001545a  mov     rdi, rax
0x18001545d  lea     rcx, [rsp+900h+var_890]
0x180015462  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015467  mov     r8, rsi
0x18001546a  mov     rdx, rdi
0x18001546d  mov     rcx, rax; Source
0x180015470  call    ?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; CreateTenantGatewayEntryStruct(std::wstring,std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180015475  mov     edi, eax
0x180015477  test    eax, eax
0x180015479  jnz     short loc_180015483
0x18001547b  mov     esi, dword ptr [rsp+900h+var_8E0]
0x18001547f  inc     esi
0x180015481  jmp     short loc_180015420
0x180015483  test    cs:byte_18002E903, 8
0x18001548a  jz      loc_18001535A
0x180015490  xor     eax, eax
0x180015492  mov     r8d, edi
0x180015495  mov     word ptr [rbp+800h+var_840], ax
0x180015499  jmp     loc_1800153AE
0x18001549e  mov     [r12], r15d
0x1800154a2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800154a7  test    edi, edi
0x1800154a9  jz      short loc_1800154BC
0x1800154ab  mov     rcx, [r13+0]; void *
0x1800154af  call    MIDL_user_free
0x1800154b4  mov     dword ptr [r12], 0
0x1800154bc  mov     rcx, [rsp+900h+SRWLock]; SRWLock
0x1800154c1  call    cs:__imp_ReleaseSRWLockShared
0x1800154c8  nop     dword ptr [rax+rax+00h]
0x1800154cd  mov     eax, edi
0x1800154cf  mov     rcx, [rbp+800h+var_40]
0x1800154d6  xor     rcx, rsp; StackCookie
0x1800154d9  call    __security_check_cookie
0x1800154de  mov     rbx, [rsp+900h+arg_0]
0x1800154e6  add     rsp, 8D0h
0x1800154ed  pop     r15
0x1800154ef  pop     r14
0x1800154f1  pop     r13
0x1800154f3  pop     r12
0x1800154f5  pop     rdi
0x1800154f6  pop     rsi
0x1800154f7  pop     rbp
0x1800154f8  retn
```
