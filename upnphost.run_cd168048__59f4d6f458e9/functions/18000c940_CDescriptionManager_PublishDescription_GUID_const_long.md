# CDescriptionManager::PublishDescription(_GUID const &,long)

- ea: `0x18000c940`
- end: `0x18000d04f`
- name: `?PublishDescription@CDescriptionManager@@UEAAJAEBU_GUID@@J@Z`
- size: `1807`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800055a8`
- `0x1800056d8`
- `0x1800056f0`
- `0x1800071c0`
- `0x180008688`
- `0x180009d50`
- `0x18000a060`
- `0x18000ae60`
- `0x18000b0d0`
- `0x18000c940`
- `0x18000d058`
- `0x18000d564`
- `0x18000e6a0`
- `0x180010780`
- `0x180011a48`
- `0x18001248c`
- `0x18001252c`
- `0x18002c3fc`
- `0x18002c534`
- `0x180032220`
- `0x180032e88`
- `0x180032f10`
- `0x1800373d8`
- `0x18003a30c`
- `0x18003b1cc`
- `0x18003b47c`
- `0x18003c018`
- `0x18003cb60`
- `0x18003cb84`
- `0x18003d4b0`
- `0x180042774`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cb5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cba2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cbb3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cb5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cba2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cbb3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cca2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000cd22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000cd22`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ce40`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ce40`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ca22`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ca22`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca7b`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::PublishDescription(CDescriptionManager *this, struct _GUID *a2, int a3)
{
  CDescriptionManager *v3; // r14
  _QWORD *v6; // rsi
  int v7; // r13d
  int IsAllowedCOMCallLocality; // edi
  CDescriptionManager *v9; // rcx
  OLECHAR *v10; // rbx
  __int64 v11; // rax
  CDescriptionManager *v12; // rcx
  CDescriptionManager *v13; // rcx
  unsigned int v14; // r8d
  _QWORD *v16; // rax
  struct _GUID v17; // xmm0
  struct _TP_WORK *ThreadpoolWork; // r12
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  int v20; // edx
  _QWORD *v21; // r13
  char *v22; // r14
  struct _TP_WORK **v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r11
  __int64 v28; // rax
  signed int LastError; // eax
  STRSAFE_PCNZWCH v30; // rcx
  int v31; // edx
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v33[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h]
  CDescriptionManager *v37; // [rsp+58h] [rbp-A8h]
  _BYTE v38[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v40[5]; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+9Ch] [rbp-64h]
  const char *v42; // [rsp+B8h] [rbp-48h]
  char v43[256]; // [rsp+F0h] [rbp-10h] BYREF
  char v44[256]; // [rsp+1F0h] [rbp+F0h] BYREF

  v3 = this;
  v37 = this;
  v35 = a3;
  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  memset_0(v40, 0, 0x78u);
  v6 = 0;
  v7 = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    v16 = malloc(0x50u);
    v6 = v16;
    if ( v16 )
    {
      v16[1] = v16;
      *v16 = v16;
      v16[2] = 0;
      v16[3] = 0;
      v16[5] = 0;
      v16[4] = 0;
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
    }
  }
  v41 = a3;
  v34 = 0;
  v39 = 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = HrGetContentURL(a2, (struct CUString *)&v39);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = HrGetURLBase((struct CUString *)&v34);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&v34, v39);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = StringCbPrintfA(v43, 0x100u, "%S", (const wchar_t *)v34);
          v40[1] = v43;
        }
      }
    }
  }
  v42 = "0bd2834d-d10e-46e9-84ba-34e538bea2d3";
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v33);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v38);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_18;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v32);
  IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(v3, a2, &v32);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    v10 = SysAllocString(L"//ddd:device");
    if ( v10 )
    {
      ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(v33);
      v11 = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(&v32);
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _BYTE *))(*(_QWORD *)v11 + 288LL))(
                                   v11,
                                   v10,
                                   v33);
      if ( IsAllowedCOMCallLocality == 1 )
        IsAllowedCOMCallLocality = -2147467259;
      SysFreeString(v10);
      if ( !IsAllowedCOMCallLocality )
      {
LABEL_9:
        IsAllowedCOMCallLocality = HrSelectNode(L"/ddd:root/ddd:device", &v32, v38);
        if ( IsAllowedCOMCallLocality >= 0 )
          IsAllowedCOMCallLocality = CDescriptionManager::Hr_DoStartUrlListening(v12, a2);
        goto LABEL_11;
      }
      v30 = WPP_GLOBAL_Control;
    }
    else
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids,
            (unsigned int)L"//ddd:device",
            14);
          v30 = WPP_GLOBAL_Control;
        }
        if ( v30 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v30[14] & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v30 + 2), 15, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, 2147942414LL);
          v30 = WPP_GLOBAL_Control;
        }
      }
      IsAllowedCOMCallLocality = -2147024882;
    }
    if ( v30 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v30[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)v30 + 2),
        16,
        WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_11;
    goto LABEL_9;
  }
LABEL_11:
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v32);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_18;
  v7 = 1;
  v32 = 1;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  Block = 0;
  IsAllowedCOMCallLocality = HrSelectNodeText((OLECHAR *)L"ddd:UDN");
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = StringCbPrintfA(v44, 0x100u, "%S::upnp:rootdevice", (const wchar_t *)Block);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      v40[3] = v44;
      v40[0] = "upnp:rootdevice";
      IsAllowedCOMCallLocality = CDescriptionManager::AddRegistrationParams(
                                   v13,
                                   (struct _SSDP_MESSAGE_EX *)v40,
                                   v14,
                                   (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
    }
  }
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  free(Block);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_18;
  IsAllowedCOMCallLocality = CDescriptionManager::HrPD_DoDevicePublication(
                               (int)v3,
                               (int)a2,
                               (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_18;
  v17 = *a2;
  *((_DWORD *)v6 + 12) = a3;
  v6[9] = v3;
  *(struct _GUID *)((char *)v6 + 52) = v17;
  ThreadpoolWork = CreateThreadpoolWork(
                     CDescriptionManager::BeginRegistration,
                     v6,
                     (PTP_CALLBACK_ENVIRON)((char *)v3 + 392));
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    IsAllowedCOMCallLocality = LastError;
    if ( LastError > 0 )
      IsAllowedCOMCallLocality = (unsigned __int16)LastError | 0x80070000;
    v9 = (CDescriptionManager *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_18;
  }
  v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 488);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 488));
  v20 = 0;
  v21 = (_QWORD *)((char *)v3 + 320);
  while ( 1 )
  {
    if ( v20 >= *((_DWORD *)v3 + 82) )
    {
      v22 = (char *)v3 + 336;
      goto LABEL_37;
    }
    v24 = (_QWORD *)(*v21 + 16LL * v20);
    v25 = *(_QWORD *)&a2->Data1 - *v24;
    if ( *(_QWORD *)&a2->Data1 == *v24 )
      v25 = *(_QWORD *)a2->Data4 - v24[1];
    if ( !v25 )
      break;
    ++v20;
  }
  v22 = (char *)v3 + 336;
  if ( v21[2] + 8LL * v20 )
  {
    IsAllowedCOMCallLocality = -2147024809;
    goto LABEL_45;
  }
LABEL_37:
  v23 = (struct _TP_WORK **)CTable<_GUID,_TP_WORK *>::Lookup(v21, a2);
  if ( v23 )
  {
    *v23 = ThreadpoolWork;
  }
  else
  {
    if ( (int)CUArray<_GUID>::HrPushBack(v21) < 0 )
    {
LABEL_39:
      IsAllowedCOMCallLocality = -2147467259;
LABEL_45:
      v3 = v37;
      goto LABEL_46;
    }
    v31 = *((_DWORD *)v22 + 3);
    if ( *((_DWORD *)v22 + 2) == v31 && (int)CUArray<_TP_WORK *>::HrSetReserve(v22, (unsigned int)(v31 + 50)) < 0 )
    {
      CUArray<_GUID>::HrPopBack(v21);
      goto LABEL_39;
    }
    *(_QWORD *)(*(_QWORD *)v22 + 8LL * (int)(*((_DWORD *)v22 + 2))++) = ThreadpoolWork;
  }
  v3 = v37;
  if ( !CTable<_GUID,long>::Lookup((char *)v37 + 352, a2) )
    CTable<_GUID,long>::HrInsert(v27, v26, &v35);
  v28 = *((_QWORD *)v3 + 76);
  v6[1] = (char *)v3 + 608;
  *v6 = v28;
  *(_QWORD *)(v28 + 8) = v6;
  *((_QWORD *)v3 + 76) = v6;
  SubmitThreadpoolWork(ThreadpoolWork);
  v6 = 0;
LABEL_46:
  LeaveCriticalSection(v19);
  v7 = v32;
LABEL_18:
  if ( v6 )
  {
    CDescriptionManager::PurgeRegistrationParams(v9, (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v6);
    operator delete(v6, 0x50u);
  }
  if ( IsAllowedCOMCallLocality < 0 )
  {
    if ( v7 )
      CDescriptionManager::Hr_DoStopUrlListening(v9, a2);
    CDescriptionManager::HrRD_RemoveFromEventing(v3, a2);
  }
  else if ( !IsAllowedCOMCallLocality )
  {
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
LABEL_22:
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v38);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v33);
  free(v39);
  free(v34);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 24));
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18000c940  mov     [rsp-8+arg_18], rbx
0x18000c945  push    rbp
0x18000c946  push    rsi
0x18000c947  push    rdi
0x18000c948  push    r12
0x18000c94a  push    r13
0x18000c94c  push    r14
0x18000c94e  push    r15
0x18000c950  lea     rbp, [rsp-200h]
0x18000c958  sub     rsp, 300h
0x18000c95f  mov     rax, cs:__security_cookie
0x18000c966  xor     rax, rsp
0x18000c969  mov     [rbp+230h+var_40], rax
0x18000c970  mov     r14, rcx
0x18000c973  mov     [rsp+330h+var_2D8], rcx
0x18000c978  add     rcx, 18h; this
0x18000c97c  mov     [rsp+330h+var_2E8], r8d
0x18000c981  mov     r12d, r8d
0x18000c984  mov     r15, rdx
0x18000c987  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18000c98c  xor     edx, edx; Val
0x18000c98e  lea     rcx, [rsp+330h+var_2C0]; void *
0x18000c993  lea     r8d, [rdx+78h]; Size
0x18000c997  call    memset_0
0x18000c99c  xor     esi, esi
0x18000c99e  xor     r13d, r13d
0x18000c9a1  lea     ecx, [rsi+1]
0x18000c9a4  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18000c9a9  mov     edi, eax
0x18000c9ab  test    eax, eax
0x18000c9ad  jns     loc_18000CC9D
0x18000c9b3  mov     [rbp+230h+var_294], r12d
0x18000c9b7  mov     [rsp+330h+var_2F0], r13
0x18000c9bc  mov     [rsp+330h+var_2C8], r13
0x18000c9c1  test    edi, edi
0x18000c9c3  jns     loc_18000CC2F
0x18000c9c9  lea     rax, a0bd2834dD10e46; "0bd2834d-d10e-46e9-84ba-34e538bea2d3"
0x18000c9d0  lea     rcx, [rsp+330h+var_2F8]; void *
0x18000c9d5  mov     [rbp+230h+var_278], rax
0x18000c9d9  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000c9de  lea     rcx, [rsp+330h+var_2D0]; void *
0x18000c9e3  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000c9e8  lea     rbx, WPP_GLOBAL_Control
0x18000c9ef  test    edi, edi
0x18000c9f1  js      loc_18000CB72
0x18000c9f7  lea     rcx, [rsp+330h+var_300]; void *
0x18000c9fc  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000ca01  lea     r8, [rsp+330h+var_300]
0x18000ca06  mov     rdx, r15
0x18000ca09  mov     rcx, r14
0x18000ca0c  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x18000ca11  mov     edi, eax
0x18000ca13  test    eax, eax
0x18000ca15  js      loc_18000CAB6
0x18000ca1b  lea     rcx, aDddDevice; "//ddd:device"
0x18000ca22  call    cs:__imp_SysAllocString
0x18000ca29  nop     dword ptr [rax+rax+00h]
0x18000ca2e  mov     rbx, rax
0x18000ca31  test    rax, rax
0x18000ca34  jz      loc_18000CEA5
0x18000ca3a  lea     rcx, [rsp+330h+var_2F8]
0x18000ca3f  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x18000ca44  lea     rcx, [rsp+330h+var_300]
0x18000ca49  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000ca4e  mov     r9, rax
0x18000ca51  lea     r8, [rsp+330h+var_2F8]
0x18000ca56  mov     rdx, rbx
0x18000ca59  mov     rcx, [rax]
0x18000ca5c  mov     rax, [rcx+120h]
0x18000ca63  mov     rcx, r9
0x18000ca66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6b  mov     edi, eax
0x18000ca6d  cmp     eax, 1
0x18000ca70  mov     eax, 80004005h
0x18000ca75  mov     rcx, rbx; bstrString
0x18000ca78  cmovz   edi, eax
0x18000ca7b  call    cs:__imp_SysFreeString
0x18000ca82  nop     dword ptr [rax+rax+00h]
0x18000ca87  lea     rbx, WPP_GLOBAL_Control
0x18000ca8e  test    edi, edi
0x18000ca90  jnz     loc_18000CF1D
0x18000ca96  lea     r8, [rsp+330h+var_2D0]
0x18000ca9b  lea     rdx, [rsp+330h+var_300]
0x18000caa0  lea     rcx, aDddRootDddDevi_0; "/ddd:root/ddd:device"
0x18000caa7  call    ?HrSelectNode@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@1@Z; HrSelectNode(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNode> &)
0x18000caac  mov     edi, eax
0x18000caae  test    eax, eax
0x18000cab0  jns     loc_18000CC20
0x18000cab6  lea     rcx, [rsp+330h+var_300]
0x18000cabb  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000cac0  test    edi, edi
0x18000cac2  js      loc_18000CB72
0x18000cac8  mov     r13d, 1
0x18000cace  mov     [rsp+330h+var_300], r13d
0x18000cad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cada  cmp     rcx, rbx
0x18000cadd  jnz     loc_18000CBFC
0x18000cae3  lea     r8, [rsp+330h+Block]
0x18000cae8  mov     [rsp+330h+Block], 0
0x18000caf1  lea     rdx, [rsp+330h+var_2D0]
0x18000caf6  lea     rcx, aDddUdn_0; "ddd:UDN"
0x18000cafd  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000cb02  mov     edi, eax
0x18000cb04  test    eax, eax
0x18000cb06  js      short loc_18000CB51
0x18000cb08  mov     r9, [rsp+330h+Block]
0x18000cb0d  lea     r8, aSUpnpRootdevic; "%S::upnp:rootdevice"
0x18000cb14  mov     edx, 100h; unsigned __int64
0x18000cb19  lea     rcx, [rbp+230h+var_140]; char *
0x18000cb20  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000cb25  mov     edi, eax
0x18000cb27  test    eax, eax
0x18000cb29  js      short loc_18000CB51
0x18000cb2b  lea     rax, [rbp+230h+var_140]
0x18000cb32  mov     r9, rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18000cb35  mov     [rbp+230h+var_2A8], rax
0x18000cb39  lea     rdx, [rsp+330h+var_2C0]; struct _SSDP_MESSAGE_EX *
0x18000cb3e  lea     rax, aUpnpRootdevice; "upnp:rootdevice"
0x18000cb45  mov     [rsp+330h+var_2C0], rax
0x18000cb4a  call    ?AddRegistrationParams@CDescriptionManager@@AEAAJPEAU_SSDP_MESSAGE_EX@@KPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::AddRegistrationParams(_SSDP_MESSAGE_EX *,ulong,SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18000cb4f  mov     edi, eax
0x18000cb51  test    edi, edi
0x18000cb53  jnz     loc_18000CF54
0x18000cb59  mov     rcx, [rsp+330h+Block]; Block
0x18000cb5e  call    cs:__imp_free
0x18000cb65  nop     dword ptr [rax+rax+00h]
0x18000cb6a  test    edi, edi
0x18000cb6c  jns     loc_18000CCDC
0x18000cb72  test    rsi, rsi
0x18000cb75  jnz     loc_18000CFDF
0x18000cb7b  test    edi, edi
0x18000cb7d  js      loc_18000CFF9
0x18000cb83  jnz     loc_18000D011
0x18000cb89  lea     rcx, [rsp+330h+var_2D0]
0x18000cb8e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000cb93  lea     rcx, [rsp+330h+var_2F8]
0x18000cb98  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000cb9d  mov     rcx, [rsp+330h+var_2C8]; Block
0x18000cba2  call    cs:__imp_free
0x18000cba9  nop     dword ptr [rax+rax+00h]
0x18000cbae  mov     rcx, [rsp+330h+var_2F0]; Block
0x18000cbb3  call    cs:__imp_free
0x18000cbba  nop     dword ptr [rax+rax+00h]
0x18000cbbf  lea     rcx, [r14+18h]; lpCriticalSection
0x18000cbc3  call    cs:__imp_LeaveCriticalSection
0x18000cbca  nop     dword ptr [rax+rax+00h]
0x18000cbcf  mov     eax, edi
0x18000cbd1  mov     rcx, [rbp+230h+var_40]
0x18000cbd8  xor     rcx, rsp; StackCookie
0x18000cbdb  call    __security_check_cookie
0x18000cbe0  mov     rbx, [rsp+330h+arg_18]
0x18000cbe8  add     rsp, 300h
0x18000cbef  pop     r15
0x18000cbf1  pop     r14
0x18000cbf3  pop     r13
0x18000cbf5  pop     r12
0x18000cbf7  pop     rdi
0x18000cbf8  pop     rsi
0x18000cbf9  pop     rbp
0x18000cbfa  retn
0x18000cbfc  test    byte ptr [rcx+1Ch], 40h
0x18000cc00  jz      loc_18000CAE3
0x18000cc06  mov     rcx, [rcx+10h]
0x18000cc0a  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000cc11  mov     edx, 3Eh ; '>'
0x18000cc16  call    WPP_SF_
0x18000cc1b  jmp     loc_18000CAE3
0x18000cc20  mov     rdx, r15; struct _GUID *
0x18000cc23  call    ?Hr_DoStartUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStartUrlListening(_GUID const &)
0x18000cc28  mov     edi, eax
0x18000cc2a  jmp     loc_18000CAB6
0x18000cc2f  lea     rdx, [rsp+330h+var_2C8]; this
0x18000cc34  mov     rcx, r15; Uuid
0x18000cc37  call    ?HrGetContentURL@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetContentURL(_GUID const &,CUString &)
0x18000cc3c  mov     edi, eax
0x18000cc3e  test    eax, eax
0x18000cc40  js      loc_18000C9C9
0x18000cc46  lea     rcx, [rsp+330h+var_2F0]; this
0x18000cc4b  call    ?HrGetURLBase@@YAJAEAVCUString@@@Z; HrGetURLBase(CUString &)
0x18000cc50  mov     edi, eax
0x18000cc52  test    eax, eax
0x18000cc54  js      loc_18000C9C9
0x18000cc5a  mov     rdx, [rsp+330h+var_2C8]; unsigned __int16 *
0x18000cc5f  lea     rcx, [rsp+330h+var_2F0]; this
0x18000cc64  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000cc69  mov     edi, eax
0x18000cc6b  test    eax, eax
0x18000cc6d  js      loc_18000C9C9
0x18000cc73  mov     r9, [rsp+330h+var_2F0]
0x18000cc78  lea     r8, aS_0; "%S"
0x18000cc7f  mov     edx, 100h; unsigned __int64
0x18000cc84  lea     rcx, [rbp+230h+var_240]; char *
0x18000cc88  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000cc8d  mov     edi, eax
0x18000cc8f  lea     rax, [rbp+230h+var_240]
0x18000cc93  mov     [rsp+330h+var_2B8], rax
0x18000cc98  jmp     loc_18000C9C9
0x18000cc9d  mov     ecx, 50h ; 'P'; Size
0x18000cca2  call    cs:__imp_malloc
0x18000cca9  nop     dword ptr [rax+rax+00h]
0x18000ccae  mov     rsi, rax
0x18000ccb1  test    rax, rax
0x18000ccb4  jnz     short loc_18000CCC0
0x18000ccb6  mov     edi, 8007000Eh
0x18000ccbb  jmp     loc_18000C9B3
0x18000ccc0  mov     [rax+8], rax
0x18000ccc4  mov     [rax], rax
0x18000ccc7  mov     [rax+10h], r13
0x18000cccb  mov     [rax+18h], r13
0x18000cccf  mov     [rax+28h], r13
0x18000ccd3  mov     [rax+20h], r13
0x18000ccd7  jmp     loc_18000C9B3
0x18000ccdc  lea     r9, [rsp+330h+var_2C0]
0x18000cce1  mov     [rsp+330h+var_310], rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18000cce6  lea     r8, [rsp+330h+var_2F8]
0x18000cceb  mov     rdx, r15; int
0x18000ccee  mov     rcx, r14; int
0x18000ccf1  call    ?HrPD_DoDevicePublication@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@PEAU_SSDP_MESSAGE_EX@@PEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::HrPD_DoDevicePublication(_GUID const &,SmartComPtr<IXMLDOMNodeList> &,_SSDP_MESSAGE_EX *,SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18000ccf6  mov     edi, eax
0x18000ccf8  test    eax, eax
0x18000ccfa  js      loc_18000CB72
0x18000cd00  movups  xmm0, xmmword ptr [r15]
0x18000cd04  lea     r8, [r14+188h]; pcbe
0x18000cd0b  mov     [rsi+30h], r12d
0x18000cd0f  mov     rdx, rsi; pv
0x18000cd12  mov     [rsi+48h], r14
0x18000cd16  lea     rcx, ?BeginRegistration@CDescriptionManager@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000cd1d  movdqu  xmmword ptr [rsi+34h], xmm0
0x18000cd22  call    cs:__imp_CreateThreadpoolWork
0x18000cd29  nop     dword ptr [rax+rax+00h]
0x18000cd2e  mov     r12, rax
0x18000cd31  test    rax, rax
0x18000cd34  jz      loc_18000CE53
0x18000cd3a  lea     rbx, [r14+1E8h]
0x18000cd41  mov     rcx, rbx; lpCriticalSection
0x18000cd44  call    cs:__imp_EnterCriticalSection
0x18000cd4b  nop     dword ptr [rax+rax+00h]
0x18000cd50  xor     edx, edx
0x18000cd52  lea     r13, [r14+140h]
0x18000cd59  cmp     edx, [r13+8]
0x18000cd5d  jl      short loc_18000CD8E
0x18000cd5f  lea     r14, [r13+10h]
0x18000cd63  mov     rdx, r15
0x18000cd66  mov     rcx, r13
0x18000cd69  call    ?Lookup@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAPEAPEAU_TP_WORK@@AEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::Lookup(_GUID const &)
0x18000cd6e  test    rax, rax
0x18000cd71  jnz     loc_18000CF8B
0x18000cd77  mov     rcx, r13
0x18000cd7a  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x18000cd7f  test    eax, eax
0x18000cd81  jns     loc_18000CF93
0x18000cd87  mov     edi, 80004005h
0x18000cd8c  jmp     short loc_18000CDC6
0x18000cd8e  mov     rax, [r15]
0x18000cd91  movsxd  r8, edx
0x18000cd94  mov     rcx, r8
0x18000cd97  shl     rcx, 4
0x18000cd9b  add     rcx, [r13+0]
0x18000cd9f  sub     rax, [rcx]
0x18000cda2  jnz     short loc_18000CDAC
0x18000cda4  mov     rax, [r15+8]
0x18000cda8  sub     rax, [rcx+8]
0x18000cdac  test    rax, rax
0x18000cdaf  jnz     short loc_18000CDE4
0x18000cdb1  lea     r14, [r13+10h]
0x18000cdb5  mov     rax, [r14]
0x18000cdb8  lea     rcx, [rax+r8*8]
0x18000cdbc  test    rcx, rcx
0x18000cdbf  jz      short loc_18000CD63
0x18000cdc1  mov     edi, 80070057h
0x18000cdc6  mov     r14, [rsp+330h+var_2D8]
0x18000cdcb  mov     rcx, rbx; lpCriticalSection
0x18000cdce  call    cs:__imp_LeaveCriticalSection
0x18000cdd5  nop     dword ptr [rax+rax+00h]
0x18000cdda  mov     r13d, [rsp+330h+var_300]
0x18000cddf  jmp     loc_18000CB72
0x18000cde4  inc     edx
0x18000cde6  jmp     loc_18000CD59
0x18000cdeb  test    edi, edi
0x18000cded  jns     loc_18000CA96
0x18000cdf3  jmp     loc_18000CAB6
0x18000cdf8  test    edi, edi
0x18000cdfa  jns     loc_18000CD3A
0x18000ce00  jmp     loc_18000CB72
0x18000ce05  mov     r14, [rsp+330h+var_2D8]
0x18000ce0a  mov     rdx, r15
0x18000ce0d  lea     r11, [r14+160h]
0x18000ce14  mov     rcx, r11
0x18000ce17  call    ?Lookup@?$CTable@U_GUID@@J@@QEAAPEAJAEBU_GUID@@@Z; CTable<_GUID,long>::Lookup(_GUID const &)
0x18000ce1c  test    rax, rax
0x18000ce1f  jz      loc_18000CFCD
0x18000ce25  lea     rcx, [r14+260h]
0x18000ce2c  mov     rax, [rcx]
0x18000ce2f  mov     [rsi+8], rcx
0x18000ce33  mov     [rsi], rax
0x18000ce36  mov     [rax+8], rsi
0x18000ce3a  mov     [rcx], rsi
0x18000ce3d  mov     rcx, r12; pwk
0x18000ce40  call    cs:__imp_SubmitThreadpoolWork
0x18000ce47  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
