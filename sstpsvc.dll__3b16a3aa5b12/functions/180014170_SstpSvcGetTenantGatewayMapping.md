# SstpSvcGetTenantGatewayMapping

- ea: `0x180014170`
- end: `0x18001447d`
- name: `SstpSvcGetTenantGatewayMapping`
- size: `781`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x18000f744`
- `0x18000f77c`
- `0x18000f8fc`
- `0x18000fbb0`
- `0x1800109ac`
- `0x1800124fc`
- `0x180012560`
- `0x180012ef8`
- `0x180014170`
- `0x18001b880`
- `0x18001b8b0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800141f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800141f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001444b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001444b`

## string_xrefs

- `0x180014338`: `SstpSvcGetTenantGatewayMapping: CreateTenantGatewayEntryStruct failed with error %d`

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
  const wchar_t *v14; // r8
  wchar_t *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r15
  void *v19; // rax
  _QWORD *v20; // rbx
  int i; // esi
  wchar_t *v22; // rax
  __int64 v23; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h]
  _BYTE v27[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[40]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[40]; // [rsp+98h] [rbp-68h] BYREF
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  Instance = TenantGatewayMap::GetInstance();
  SRWLock = (PSRWLOCK)Instance;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( !(unsigned int)GetSstpConfigFlag(1) )
    return 50;
  v9 = (char *)Instance + 8;
  AcquireSRWLockShared((PSRWLOCK)Instance);
  *a4 = 0;
  *a5 = 0;
  if ( !a3 )
  {
    v18 = *((unsigned int *)Instance + 6);
    v25 = 0;
    v24 = 0;
    if ( (_DWORD)v18 )
    {
      v19 = MIDL_user_allocate(40 * v18);
      *a5 = v19;
      if ( !v19 )
      {
LABEL_10:
        TenantGatewayEntryStruct = 14;
        if ( (byte_18002D803 & 8) == 0 )
        {
LABEL_13:
          std::vector<std::wstring>::_Tidy(&v24);
LABEL_29:
          MIDL_user_free(*a5);
          *a4 = 0;
          goto LABEL_30;
        }
        v14 = L"SstpSvcGetTenantGatewayMapping: Failed to allocate memory for SSTP_TENANT_GATEWAY_ENTRY structure.";
LABEL_12:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v14);
        goto LABEL_13;
      }
    }
    v20 = (_QWORD *)*((_QWORD *)Instance + 2);
    TenantGatewayEntryStruct = 0;
    for ( i = 0; ; i = v23 + 1 )
    {
      v20 = (_QWORD *)*v20;
      LODWORD(v23) = i;
      if ( v20 == *((_QWORD **)v9 + 1) )
      {
        *a4 = v18;
        std::vector<std::wstring>::_Tidy(&v24);
        goto LABEL_30;
      }
      std::vector<std::wstring>::operator=(&v24, v20 + 7);
      std::vector<std::wstring>::vector<std::wstring>(v27, &v24);
      v22 = (wchar_t *)std::wstring::wstring(v28, v20 + 2);
      TenantGatewayEntryStruct = CreateTenantGatewayEntryStruct(v22);
      if ( TenantGatewayEntryStruct )
        break;
    }
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_13;
    v17 = TenantGatewayEntryStruct;
    LOWORD(v30) = 0;
LABEL_17:
    FormatRRASErrorString(
      &v30,
      L"SstpSvcGetTenantGatewayMapping: CreateTenantGatewayEntryStruct failed with error %d",
      v17);
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_13;
    v14 = (const wchar_t *)&v30;
    goto LABEL_12;
  }
  std::wstring::wstring(v29, a3);
  std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(
    (char *)Instance + 8,
    &v23,
    v29);
  v10 = v23;
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v29, v11, 0);
  if ( v10 == *((_QWORD *)v9 + 1) )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"SstpSvcGetTenantGatewayMapping: Tenant(%ws) entry does not exist", a3);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
    }
    TenantGatewayEntryStruct = 1168;
    goto LABEL_29;
  }
  std::vector<std::wstring>::vector<std::wstring>(&v24, v10 + 56);
  v13 = MIDL_user_allocate(0x28u);
  *a5 = v13;
  if ( !v13 )
    goto LABEL_10;
  std::vector<std::wstring>::vector<std::wstring>(v27, &v24);
  v15 = (wchar_t *)std::wstring::wstring(v28, v10 + 16);
  v16 = CreateTenantGatewayEntryStruct(v15);
  TenantGatewayEntryStruct = v16;
  if ( v16 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_13;
    v17 = v16;
    LOWORD(v30) = 0;
    goto LABEL_17;
  }
  *a4 = 1;
  std::vector<std::wstring>::_Tidy(&v24);
LABEL_30:
  ReleaseSRWLockShared(SRWLock);
  return TenantGatewayEntryStruct;
}

```

## disassembly

```asm
0x180014170  mov     [rsp-8+arg_0], rbx
0x180014175  push    rbp
0x180014176  push    rsi
0x180014177  push    rdi
0x180014178  push    r12
0x18001417a  push    r13
0x18001417c  push    r14
0x18001417e  push    r15
0x180014180  lea     rbp, [rsp-7D0h]
0x180014188  sub     rsp, 8D0h
0x18001418f  mov     rax, cs:__security_cookie
0x180014196  xor     rax, rsp
0x180014199  mov     [rbp+800h+var_40], rax
0x1800141a0  mov     r13, [rbp+800h+arg_20]
0x1800141a7  mov     r12, r9
0x1800141aa  mov     rdi, r8
0x1800141ad  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x1800141b2  mov     rbx, rax
0x1800141b5  mov     [rsp+900h+SRWLock], rax
0x1800141ba  xor     eax, eax
0x1800141bc  lea     rcx, [rbp+800h+var_83C]; void *
0x1800141c0  xor     edx, edx; Val
0x1800141c2  mov     [rbp+800h+var_840], eax
0x1800141c5  mov     r8d, 7FCh; Size
0x1800141cb  call    memset_0
0x1800141d0  mov     r15d, 1
0x1800141d6  mov     ecx, r15d
0x1800141d9  call    GetSstpConfigFlag
0x1800141de  test    eax, eax
0x1800141e0  jnz     short loc_1800141EB
0x1800141e2  lea     eax, [r15+31h]
0x1800141e6  jmp     loc_180014453
0x1800141eb  mov     rcx, rbx; SRWLock
0x1800141ee  lea     r14, [rbx+8]
0x1800141f2  call    cs:__imp_AcquireSRWLockShared
0x1800141f8  mov     dword ptr [r12], 0
0x180014200  mov     qword ptr [r13+0], 0
0x180014208  test    rdi, rdi
0x18001420b  jz      loc_18001436D
0x180014211  mov     rdx, rdi
0x180014214  lea     rcx, [rbp+800h+var_868]
0x180014218  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001421d  lea     r8, [rbp+800h+var_868]
0x180014221  mov     rcx, r14
0x180014224  lea     rdx, [rsp+900h+var_8E0]
0x180014229  call    ?lower_bound@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::lower_bound(std::wstring const &)
0x18001422e  mov     rbx, [rsp+900h+var_8E0]
0x180014233  lea     rcx, [rbp+800h+var_868]
0x180014237  xor     r8d, r8d
0x18001423a  mov     dl, r15b
0x18001423d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014242  cmp     rbx, [r14+8]
0x180014246  jnz     short loc_180014294
0x180014248  test    cs:byte_18002D803, 8
0x18001424f  jz      short loc_18001428A
0x180014251  xor     eax, eax
0x180014253  lea     rdx, aSstpsvcgettena_0; "SstpSvcGetTenantGatewayMapping: Tenant("...
0x18001425a  mov     r8, rdi
0x18001425d  mov     word ptr [rbp+800h+var_840], ax
0x180014261  lea     rcx, [rbp+800h+var_840]
0x180014265  call    FormatRRASErrorString
0x18001426a  test    cs:byte_18002D803, 8
0x180014271  jz      short loc_18001428A
0x180014273  lea     r8, [rbp+800h+var_840]
0x180014277  lea     rdx, RasSSTPSvcTraceError
0x18001427e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014285  call    McTemplateU0z_EventWriteTransfer
0x18001428a  mov     edi, 490h
0x18001428f  jmp     loc_180014435
0x180014294  lea     rsi, [rbx+10h]
0x180014298  lea     rdx, [rsi+28h]
0x18001429c  lea     rcx, [rsp+900h+var_8D8]
0x1800142a1  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800142a6  mov     ecx, 28h ; '('; size
0x1800142ab  call    MIDL_user_allocate
0x1800142b0  mov     [r13+0], rax
0x1800142b4  mov     rdi, rax
0x1800142b7  test    rax, rax
0x1800142ba  jnz     short loc_1800142F3
0x1800142bc  test    cs:byte_18002D803, 8
0x1800142c3  mov     edi, 0Eh
0x1800142c8  jz      short loc_1800142E4
0x1800142ca  lea     r8, aSstpsvcgettena; "SstpSvcGetTenantGatewayMapping: Failed "...
0x1800142d1  lea     rdx, RasSSTPSvcTraceError
0x1800142d8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800142df  call    McTemplateU0z_EventWriteTransfer
0x1800142e4  lea     rcx, [rsp+900h+var_8D8]
0x1800142e9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800142ee  jmp     loc_180014435
0x1800142f3  lea     rdx, [rsp+900h+var_8D8]
0x1800142f8  lea     rcx, [rsp+900h+var_8B0]
0x1800142fd  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180014302  mov     rdx, rsi
0x180014305  lea     rcx, [rsp+900h+var_890]
0x18001430a  mov     rbx, rax
0x18001430d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180014312  mov     r8, rdi
0x180014315  mov     rdx, rbx
0x180014318  mov     rcx, rax; Source
0x18001431b  call    ?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; CreateTenantGatewayEntryStruct(std::wstring,std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x180014320  mov     edi, eax
0x180014322  test    eax, eax
0x180014324  jz      short loc_18001435A
0x180014326  test    cs:byte_18002D803, 8
0x18001432d  jz      short loc_1800142E4
0x18001432f  xor     ecx, ecx
0x180014331  mov     r8d, eax
0x180014334  mov     word ptr [rbp+800h+var_840], cx
0x180014338  lea     rdx, aSstpsvcgettena_1; "SstpSvcGetTenantGatewayMapping: CreateT"...
0x18001433f  lea     rcx, [rbp+800h+var_840]
0x180014343  call    FormatRRASErrorString
0x180014348  test    cs:byte_18002D803, 8
0x18001434f  jz      short loc_1800142E4
0x180014351  lea     r8, [rbp+800h+var_840]
0x180014355  jmp     loc_1800142D1
0x18001435a  lea     rcx, [rsp+900h+var_8D8]
0x18001435f  mov     [r12], r15d
0x180014363  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014368  jmp     loc_180014446
0x18001436d  mov     r15d, [r14+10h]
0x180014371  xorps   xmm0, xmm0
0x180014374  mov     [rsp+900h+var_8C8], 0
0x18001437d  movdqu  [rsp+900h+var_8D8], xmm0
0x180014383  test    r15d, r15d
0x180014386  jz      short loc_1800143A2
0x180014388  lea     rcx, [r15+r15*4]
0x18001438c  shl     rcx, 3; size
0x180014390  call    MIDL_user_allocate
0x180014395  mov     [r13+0], rax
0x180014399  test    rax, rax
0x18001439c  jz      loc_1800142BC
0x1800143a2  mov     rbx, [r14+8]
0x1800143a6  xor     edi, edi
0x1800143a8  xor     esi, esi
0x1800143aa  mov     rbx, [rbx]
0x1800143ad  lea     rcx, [rsp+900h+var_8D8]
0x1800143b2  mov     dword ptr [rsp+900h+var_8E0], esi
0x1800143b6  cmp     rbx, [r14+8]
0x1800143ba  jz      short loc_180014428
0x1800143bc  lea     rdx, [rbx+38h]
0x1800143c0  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x1800143c5  mov     rax, [r13+0]
0x1800143c9  lea     rcx, [rsi+rsi*4]
0x1800143cd  lea     rdx, [rsp+900h+var_8D8]
0x1800143d2  lea     rsi, [rax+rcx*8]
0x1800143d6  lea     rcx, [rsp+900h+var_8B0]
0x1800143db  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800143e0  lea     rdx, [rbx+10h]
0x1800143e4  mov     rdi, rax
0x1800143e7  lea     rcx, [rsp+900h+var_890]
0x1800143ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800143f1  mov     r8, rsi
0x1800143f4  mov     rdx, rdi
0x1800143f7  mov     rcx, rax; Source
0x1800143fa  call    ?CreateTenantGatewayEntryStruct@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z; CreateTenantGatewayEntryStruct(std::wstring,std::vector<std::wstring>,_SSTP_TENANT_GATEWAY_ENTRY *)
0x1800143ff  mov     edi, eax
0x180014401  test    eax, eax
0x180014403  jnz     short loc_18001440D
0x180014405  mov     esi, dword ptr [rsp+900h+var_8E0]
0x180014409  inc     esi
0x18001440b  jmp     short loc_1800143AA
0x18001440d  test    cs:byte_18002D803, 8
0x180014414  jz      loc_1800142E4
0x18001441a  xor     eax, eax
0x18001441c  mov     r8d, edi
0x18001441f  mov     word ptr [rbp+800h+var_840], ax
0x180014423  jmp     loc_180014338
0x180014428  mov     [r12], r15d
0x18001442c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014431  test    edi, edi
0x180014433  jz      short loc_180014446
0x180014435  mov     rcx, [r13+0]; void *
0x180014439  call    MIDL_user_free
0x18001443e  mov     dword ptr [r12], 0
0x180014446  mov     rcx, [rsp+900h+SRWLock]; SRWLock
0x18001444b  call    cs:__imp_ReleaseSRWLockShared
0x180014451  mov     eax, edi
0x180014453  mov     rcx, [rbp+800h+var_40]
0x18001445a  xor     rcx, rsp; StackCookie
0x18001445d  call    __security_check_cookie
0x180014462  mov     rbx, [rsp+900h+arg_0]
0x18001446a  add     rsp, 8D0h
0x180014471  pop     r15
0x180014473  pop     r14
0x180014475  pop     r13
0x180014477  pop     r12
0x180014479  pop     rdi
0x18001447a  pop     rsi
0x18001447b  pop     rbp
0x18001447c  retn
```
