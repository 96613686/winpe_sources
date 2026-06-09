# CUpdateInstaller::Install(tagDSDeploymentOperation,int,wchar_t const *,IInstallationResult * *)

- ea: `0x18006b3dc`
- end: `0x18006b9f5`
- name: `?Install@CUpdateInstaller@@AEAAJW4tagDSDeploymentOperation@@HPEB_WPEAPEAUIInstallationResult@@@Z`
- size: `1561`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, wchar_t *, struct IInstallationResult **)`
- caller_count: `4`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006a2f0`
- `0x18006a320`
- `0x18006a390`
- `0x18006ca70`

## callees

- `0x180006ac4`
- `0x18000ed90`
- `0x1800170ec`
- `0x180019c9c`
- `0x18002c290`
- `0x18002c888`
- `0x18002d41c`
- `0x18006b3dc`
- `0x18006cafc`
- `0x18008d4d4`
- `0x180090bc8`
- `0x180096b10`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b4af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b4af`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b53f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b964`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b53f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b964`
- `OLEAUT32!__imp_VariantInit` at `0x18006b749`
- `OLEAUT32!__imp_VariantInit` at `0x18006b754`
- `OLEAUT32!__imp_VariantInit` at `0x18006b749`
- `OLEAUT32!__imp_VariantInit` at `0x18006b754`
- `OLEAUT32!__imp_VariantClear` at `0x18006b93b`
- `OLEAUT32!__imp_VariantClear` at `0x18006b947`
- `OLEAUT32!__imp_VariantClear` at `0x18006b93b`
- `OLEAUT32!__imp_VariantClear` at `0x18006b947`

## string_xrefs

- `0x18006b485`: `C:\__w\1\s\src\Client\comapi\UpdateInstaller.cpp`
- `0x18006b56d`: `C:\__w\1\s\src\Client\comapi\UpdateInstaller.cpp`
- `0x18006b712`: `C:\__w\1\s\src\Client\comapi\UpdateInstaller.cpp`
- `0x18006b8ce`: `C:\__w\1\s\src\Client\comapi\UpdateInstaller.cpp`
- `0x18006b923`: `C:\__w\1\s\src\Client\comapi\UpdateInstaller.cpp`
- `0x18006b89e`: `Failure encountered in Install.`
- `0x18006b8eb`: `Failure encountered in Install.`
- `0x18006b8bd`: `CUpdateInstaller::Install`
- `0x18006b90d`: `CUpdateInstaller::Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUpdateInstaller::Install(
        __int64 a1,
        unsigned int a2,
        int a3,
        wchar_t *a4,
        struct IInstallationResult **a5)
{
  __int64 v7; // rdi
  __int64 *v8; // rbx
  int v9; // esi
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // r15
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(__int64, struct IUpdateCollection **); // r12
  unsigned __int64 v16; // r9
  int v17; // eax
  int v18; // r12d
  int v19; // esi
  TraceLoggingCorrelationVector *v20; // rcx
  const wchar_t *v21; // r8
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // r15
  __int64 v26; // rdx
  unsigned int v27; // r14d
  __int64 (__fastcall *v28)(__int64, _QWORD, struct IInstallationResult **); // rsi
  int v29; // r14d
  struct IInstallationResult *v30; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  HWND v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  int v37; // [rsp+6Ch] [rbp-94h]
  unsigned int DeploymentFlags; // [rsp+70h] [rbp-90h]
  unsigned int v39; // [rsp+74h] [rbp-8Ch]
  __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  HWND v41; // [rsp+80h] [rbp-80h]
  __int64 *v42; // [rsp+88h] [rbp-78h]
  wchar_t *v43; // [rsp+90h] [rbp-70h]
  struct IInstallationResult **v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  struct IInstallationResult *v49; // [rsp+C8h] [rbp-38h] BYREF
  struct IUpdateCollection *v50; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  char v52[144]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v43 = a4;
  v39 = a2;
  v44 = a5;
  v7 = 0;
  v40 = 0;
  v8 = 0;
  v42 = 0;
  v50 = 0;
  v49 = 0;
  bstrString = 0;
  v48 = 0;
  DeploymentFlags = CUpdateInstaller::GetDeploymentFlags((CUpdateInstaller *)a1);
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 853;
LABEL_6:
    v11 = (unsigned int)v9;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstaller.cpp",
      (const char *)v11,
      v32);
    goto LABEL_57;
  }
  *a5 = 0;
  if ( !a3 && *(_DWORD *)(a1 + 16) == 1 )
  {
    v9 = -2145124298;
    v10 = 858;
    goto LABEL_6;
  }
  v12 = (a1 + 240) & -(__int64)(a1 != 0);
  if ( v12 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
  v41 = (HWND)((a1 + 240) & -(__int64)(a1 != 0));
  v8 = &qword_1800EF060;
  if ( *(_QWORD *)(a1 + 336) )
    v8 = *(__int64 **)(a1 + 336);
  v42 = v8;
  (*(void (__fastcall **)(__int64 *))(v8[3] + 8))(v8 + 3);
  v13 = *(_QWORD *)(a1 + 344);
  if ( !v13 )
  {
    v9 = -2145124348;
    v14 = 868;
LABEL_18:
    v16 = (unsigned int)v9;
    goto LABEL_21;
  }
  v15 = *(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v13 + 112LL);
  if ( v50 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v50->lpVtbl->Release)(v50);
    v50 = 0;
  }
  v9 = v15(v13, &v50);
  if ( v9 < 0 )
  {
    v14 = 870;
    goto LABEL_18;
  }
  SysFreeString(0);
  bstrString = 0;
  v17 = SusCopyBSTR(*(wchar_t **)(a1 + 328), &bstrString);
  v9 = v17;
  if ( v17 >= 0 )
  {
    v18 = *(_DWORD *)(a1 + 304);
    v19 = *(_DWORD *)(a1 + 308);
    v36 = v19;
    v37 = *(_DWORD *)(a1 + 364);
    v41 = *(HWND *)(a1 + 312);
    if ( v12 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    v20 = *(TraceLoggingCorrelationVector **)(a1 + 392);
    v52[0] = 0;
    if ( v20 )
    {
      if ( !TraceLoggingCorrelationVector::Increment(v20, v52) )
      {
        v9 = -2147418113;
        v10 = 884;
        goto LABEL_6;
      }
    }
    else if ( v8 != (__int64 *)-176LL
           && !TraceLoggingCorrelationVector::Increment((TraceLoggingCorrelationVector *)(v8 + 22), v52) )
    {
      v9 = -2147418113;
      v10 = 888;
      goto LABEL_6;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
    {
      v22 = COMAPIHelper::ValidateSessionData((COMAPIHelper *)v50, *(struct IUpdateCollection **)(a1 + 400), v21);
      v9 = v22;
      if ( v22 < 0 )
      {
        v11 = (unsigned int)v22;
        v10 = 893;
        goto LABEL_7;
      }
      v19 = v36;
    }
    if ( a3 )
    {
      if ( v49 )
      {
        ((void (__fastcall *)(struct IInstallationResult *))v49->lpVtbl->Release)(v49);
        v49 = 0;
      }
      v23 = RunInstallationWizard(
              (struct IUpdateSession2 *)(-(__int64)(v8 != 0) & (unsigned __int64)(v8 + 6)),
              v18,
              v19,
              v37,
              v41,
              v50,
              bstrString,
              v43,
              *(_DWORD *)(a1 + 360),
              v52,
              &v49);
      v9 = v23;
      if ( v23 < 0 )
      {
        v11 = (unsigned int)v23;
        v10 = 912;
        goto LABEL_7;
      }
      goto LABEL_56;
    }
    v24 = ATL::CComObject<FederatedInstallJob>::CreateInstance(&v40);
    v9 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x394,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstaller.cpp",
        (const char *)(unsigned int)v24,
        v32);
      v7 = v40;
      goto LABEL_57;
    }
    v7 = v40;
    v25 = v40 + 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v40 + 8) + 8LL))(v40 + 8);
    VariantInit(&pvarg);
    VariantInit(&pvarg);
    pvarg.vt = 10;
    pvarg.lVal = -2147352572;
    v33 = (HWND)v52;
    v9 = CXxxJob<ATL::IDispatchImpl<IInstallationJob,&_GUID const IID_IInstallationJob,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>,IInstallationCompletedCallback,CInstallationCompletedCallbackArgs,4294967295>::Initialize(
           v7 + 24,
           0,
           0,
           &pvarg);
    if ( v9 >= 0 )
    {
      v45 = *(_QWORD *)(a1 + 448);
      v46 = *(_QWORD *)(a1 + 440);
      v47 = *(_QWORD *)(a1 + 456);
      v33 = v41;
      v27 = v39;
      v9 = FederatedInstallJob::BeginInstall(
             v7,
             (unsigned __int64)(v8 + 6) & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64),
             v39,
             DeploymentFlags);
      if ( v9 >= 0 )
      {
        v28 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IInstallationResult **))(*(_QWORD *)v25 + 32LL);
        if ( v49 )
        {
          ((void (__fastcall *)(struct IInstallationResult *))v49->lpVtbl->Release)(v49);
          v49 = 0;
        }
        v9 = v28(v25, v27, &v49);
        v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v7 + 24) + 80LL))(v7 + 24);
        if ( v9 >= 0 )
        {
          if ( v29 >= 0 )
          {
            VariantClear(&pvarg);
LABEL_56:
            v30 = v49;
            v49 = 0;
            *v44 = v30;
            v9 = 0;
            goto LABEL_57;
          }
          LODWORD(v33) = v29;
          WUTrace("CUpdateInstaller::Install", 958, 0x10000, 3, v33, L"Failure encountered in Install.");
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C0,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstaller.cpp",
            (const char *)(unsigned int)v29,
            v34);
          v9 = v29;
LABEL_54:
          VariantClear(&pvarg);
          goto LABEL_57;
        }
        LODWORD(v33) = v9;
        WUTrace("CUpdateInstaller::Install", 951, 0x10000, 3, v33, L"Failure encountered in Install.");
        v26 = 953;
      }
      else
      {
        v26 = 944;
      }
    }
    else
    {
      v26 = 927;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstaller.cpp",
      (const char *)(unsigned int)v9,
      (int)v33);
    goto LABEL_54;
  }
  v16 = (unsigned int)v17;
  v14 = 871;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateInstaller.cpp",
    (const char *)v16,
    v32);
  if ( v12 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
LABEL_57:
  SysFreeString(bstrString);
  if ( v49 )
  {
    ((void (__fastcall *)(struct IInstallationResult *))v49->lpVtbl->Release)(v49);
    v49 = 0;
  }
  if ( v50 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v50->lpVtbl->Release)(v50);
    v50 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64 *))(v8[3] + 16))(v8 + 3);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v7 + 8) + 16LL))(v7 + 8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006b3dc  mov     [rsp-8+arg_10], rbx
0x18006b3e1  push    rbp
0x18006b3e2  push    rsi
0x18006b3e3  push    rdi
0x18006b3e4  push    r12
0x18006b3e6  push    r13
0x18006b3e8  push    r14
0x18006b3ea  push    r15
0x18006b3ec  lea     rbp, [rsp-90h]
0x18006b3f4  sub     rsp, 190h
0x18006b3fb  mov     rax, cs:__security_cookie
0x18006b402  xor     rax, rsp
0x18006b405  mov     [rbp+0C0h+var_40], rax
0x18006b40c  mov     [rbp+0C0h+var_130], r9
0x18006b410  mov     r13d, r8d
0x18006b413  mov     [rsp+1C0h+var_14C], edx
0x18006b417  mov     r14, rcx
0x18006b41a  mov     rsi, [rbp+0C0h+arg_20]
0x18006b421  mov     [rbp+0C0h+var_128], rsi
0x18006b425  xor     r15d, r15d
0x18006b428  mov     edi, r15d
0x18006b42b  mov     [rsp+1C0h+var_148], r15
0x18006b430  mov     ebx, r15d
0x18006b433  mov     [rbp+0C0h+var_138], rbx
0x18006b437  mov     [rbp+0C0h+var_F0], r15
0x18006b43b  mov     [rbp+0C0h+var_F8], r15
0x18006b43f  mov     [rsp+1C0h+bstrString], r15
0x18006b444  mov     [rbp+0C0h+var_100], r15
0x18006b448  call    ?GetDeploymentFlags@CUpdateInstaller@@AEAAKXZ; CUpdateInstaller::GetDeploymentFlags(void)
0x18006b44d  mov     [rsp+1C0h+var_150], eax
0x18006b451  test    rsi, rsi
0x18006b454  jnz     short loc_18006B462
0x18006b456  mov     esi, 80004003h
0x18006b45b  mov     edx, 355h
0x18006b460  jmp     short loc_18006B47B
0x18006b462  mov     [rsi], r15
0x18006b465  test    r13d, r13d
0x18006b468  jnz     short loc_18006B496
0x18006b46a  cmp     dword ptr [r14+10h], 1
0x18006b46f  jnz     short loc_18006B496
0x18006b471  mov     esi, 80240036h
0x18006b476  mov     edx, 35Ah; void *
0x18006b47b  mov     r9d, esi; char *
0x18006b47e  mov     rcx, [rbp+0C8h]; this
0x18006b485  lea     r8, aCW1SSrcClientC_49; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006b48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b491  jmp     loc_18006B95F
0x18006b496  mov     rax, r14
0x18006b499  lea     rcx, [r14+0F0h]
0x18006b4a0  neg     rax
0x18006b4a3  sbb     r15, r15
0x18006b4a6  and     r15, rcx
0x18006b4a9  jz      short loc_18006B4B5
0x18006b4ab  lea     rcx, [r15+8]; lpCriticalSection
0x18006b4af  call    cs:__imp_EnterCriticalSection
0x18006b4b5  mov     [rbp+0C0h+var_140], r15
0x18006b4b9  mov     rax, [r14+150h]
0x18006b4c0  lea     rbx, qword_1800EF060
0x18006b4c7  test    rax, rax
0x18006b4ca  cmovnz  rbx, rax
0x18006b4ce  mov     [rbp+0C0h+var_138], rbx
0x18006b4d2  lea     rcx, [rbx+18h]
0x18006b4d6  mov     rax, [rcx]
0x18006b4d9  mov     rax, [rax+8]
0x18006b4dd  call    _guard_dispatch_icall
0x18006b4e2  mov     rsi, [r14+158h]
0x18006b4e9  test    rsi, rsi
0x18006b4ec  jnz     short loc_18006B4FA
0x18006b4ee  mov     esi, 80240004h
0x18006b4f3  mov     edx, 364h
0x18006b4f8  jmp     short loc_18006B538
0x18006b4fa  mov     rax, [rsi]
0x18006b4fd  mov     r12, [rax+70h]
0x18006b501  mov     rcx, [rbp+0C0h+var_F0]
0x18006b505  test    rcx, rcx
0x18006b508  jz      short loc_18006B51E
0x18006b50a  mov     rdx, [rcx]
0x18006b50d  mov     rax, [rdx+10h]
0x18006b511  call    _guard_dispatch_icall
0x18006b516  mov     [rbp+0C0h+var_F0], 0
0x18006b51e  lea     rdx, [rbp+0C0h+var_F0]
0x18006b522  mov     rcx, rsi
0x18006b525  mov     rax, r12
0x18006b528  call    _guard_dispatch_icall
0x18006b52d  mov     esi, eax
0x18006b52f  test    eax, eax
0x18006b531  jns     short loc_18006B53D
0x18006b533  mov     edx, 366h
0x18006b538  mov     r9d, esi
0x18006b53b  jmp     short loc_18006B56D
0x18006b53d  xor     ecx, ecx; bstrString
0x18006b53f  call    cs:__imp_SysFreeString
0x18006b545  mov     [rsp+1C0h+bstrString], 0
0x18006b54e  lea     rdx, [rsp+1C0h+bstrString]; wchar_t **
0x18006b553  mov     rcx, [r14+148h]; strIn
0x18006b55a  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x18006b55f  mov     esi, eax
0x18006b561  test    eax, eax
0x18006b563  jns     short loc_18006B598
0x18006b565  mov     r9d, eax; char *
0x18006b568  mov     edx, 367h; void *
0x18006b56d  lea     r8, aCW1SSrcClientC_49; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006b574  mov     rcx, [rbp+0C8h]; this
0x18006b57b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b580  nop
0x18006b581  test    r15, r15
0x18006b584  jz      short loc_18006B590
0x18006b586  lea     rcx, [r15+8]; lpCriticalSection
0x18006b58a  call    cs:__imp_LeaveCriticalSection
0x18006b590  xor     r15d, r15d
0x18006b593  jmp     loc_18006B95F
0x18006b598  mov     r12d, [r14+130h]
0x18006b59f  mov     esi, [r14+134h]
0x18006b5a6  mov     [rsp+1C0h+var_158], esi
0x18006b5aa  mov     eax, [r14+16Ch]
0x18006b5b1  mov     [rsp+1C0h+var_154], eax
0x18006b5b5  mov     rax, [r14+138h]
0x18006b5bc  mov     [rbp+0C0h+var_140], rax
0x18006b5c0  test    r15, r15
0x18006b5c3  jz      short loc_18006B5CF
0x18006b5c5  lea     rcx, [r15+8]; lpCriticalSection
0x18006b5c9  call    cs:__imp_LeaveCriticalSection
0x18006b5cf  mov     rcx, [r14+188h]; this
0x18006b5d6  xor     r15d, r15d
0x18006b5d9  mov     [rbp+0C0h+var_D0], r15b
0x18006b5dd  test    rcx, rcx
0x18006b5e0  jz      short loc_18006B5FE
0x18006b5e2  lea     rdx, [rbp+0C0h+var_D0]; char *
0x18006b5e6  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18006b5eb  test    al, al
0x18006b5ed  jnz     short loc_18006B626
0x18006b5ef  mov     esi, 8000FFFFh
0x18006b5f4  mov     edx, 374h
0x18006b5f9  jmp     loc_18006B47B
0x18006b5fe  lea     rcx, [rbx+0B0h]; this
0x18006b605  test    rcx, rcx
0x18006b608  jz      short loc_18006B626
0x18006b60a  lea     rdx, [rbp+0C0h+var_D0]; char *
0x18006b60e  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18006b613  test    al, al
0x18006b615  jnz     short loc_18006B626
0x18006b617  mov     esi, 8000FFFFh
0x18006b61c  mov     edx, 378h
0x18006b621  jmp     loc_18006B47B
0x18006b626  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x18006b62d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x18006b632  test    al, al
0x18006b634  jz      short loc_18006B65D
0x18006b636  mov     rdx, [r14+190h]; struct IUpdateCollection *
0x18006b63d  mov     rcx, [rbp+0C0h+var_F0]; this
0x18006b641  call    ?ValidateSessionData@COMAPIHelper@@YAJPEAUIUpdateCollection@@PEB_W@Z; COMAPIHelper::ValidateSessionData(IUpdateCollection *,wchar_t const *)
0x18006b646  mov     esi, eax
0x18006b648  test    eax, eax
0x18006b64a  jns     short loc_18006B659
0x18006b64c  mov     r9d, eax
0x18006b64f  mov     edx, 37Dh
0x18006b654  jmp     loc_18006B47E
0x18006b659  mov     esi, [rsp+1C0h+var_158]
0x18006b65d  test    r13d, r13d
0x18006b660  jz      loc_18006B6F8
0x18006b666  mov     rcx, [rbp+0C0h+var_F8]
0x18006b66a  test    rcx, rcx
0x18006b66d  jz      short loc_18006B67F
0x18006b66f  mov     rax, [rcx]
0x18006b672  mov     rax, [rax+10h]
0x18006b676  call    _guard_dispatch_icall
0x18006b67b  mov     [rbp+0C0h+var_F8], r15
0x18006b67f  mov     rdx, [rbp+0C0h+var_F0]
0x18006b683  mov     rax, rbx
0x18006b686  lea     rcx, [rbx+30h]
0x18006b68a  neg     rax
0x18006b68d  sbb     r10, r10
0x18006b690  and     rcx, r10; struct IUpdateSession2 *
0x18006b693  lea     rax, [rbp+0C0h+var_F8]
0x18006b697  mov     [rsp+1C0h+var_170], rax; struct IInstallationResult **
0x18006b69c  lea     rax, [rbp+0C0h+var_D0]
0x18006b6a0  mov     [rsp+1C0h+var_178], rax; char *
0x18006b6a5  mov     eax, [r14+168h]
0x18006b6ac  mov     [rsp+1C0h+var_180], eax; int
0x18006b6b0  mov     rax, [rbp+0C0h+var_130]
0x18006b6b4  mov     [rsp+1C0h+var_188], rax; wchar_t *
0x18006b6b9  mov     rax, [rsp+1C0h+bstrString]
0x18006b6be  mov     [rsp+1C0h+var_190], rax; wchar_t *
0x18006b6c3  mov     [rsp+1C0h+var_198], rdx; struct IUpdateCollection *
0x18006b6c8  mov     rax, [rbp+0C0h+var_140]
0x18006b6cc  mov     [rsp+1C0h+var_1A0], rax; HWND
0x18006b6d1  mov     r9d, [rsp+1C0h+var_154]; int
0x18006b6d6  mov     r8d, esi; int
0x18006b6d9  mov     edx, r12d; int
0x18006b6dc  call    ?RunInstallationWizard@@YAJPEAUIUpdateSession2@@HHHPEAUHWND__@@PEAUIUpdateCollection@@PEB_W3HPEBDPEAPEAUIInstallationResult@@@Z; RunInstallationWizard(IUpdateSession2 *,int,int,int,HWND__ *,IUpdateCollection *,wchar_t const *,wchar_t const *,int,char const *,IInstallationResult * *)
0x18006b6e1  mov     esi, eax
0x18006b6e3  test    eax, eax
0x18006b6e5  jns     loc_18006B94D
0x18006b6eb  mov     r9d, eax
0x18006b6ee  mov     edx, 390h
0x18006b6f3  jmp     loc_18006B47E
0x18006b6f8  lea     rcx, [rsp+1C0h+var_148]
0x18006b6fd  call    ?CreateInstance@?$CComObject@VFederatedInstallJob@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FederatedInstallJob>::CreateInstance(ATL::CComObject<FederatedInstallJob> * *)
0x18006b702  mov     esi, eax
0x18006b704  test    eax, eax
0x18006b706  jns     short loc_18006B72D
0x18006b708  mov     rcx, [rbp+0C8h]; this
0x18006b70f  mov     r9d, eax; char *
0x18006b712  lea     r8, aCW1SSrcClientC_49; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006b719  mov     edx, 394h; void *
0x18006b71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b723  mov     rdi, [rsp+1C0h+var_148]
0x18006b728  jmp     loc_18006B95F
0x18006b72d  mov     rdi, [rsp+1C0h+var_148]
0x18006b732  lea     r15, [rdi+8]
0x18006b736  mov     rax, [r15]
0x18006b739  mov     rcx, r15
0x18006b73c  mov     rax, [rax+8]
0x18006b740  call    _guard_dispatch_icall
0x18006b745  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18006b749  call    cs:__imp_VariantInit
0x18006b74f  nop
0x18006b750  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18006b754  call    cs:__imp_VariantInit
0x18006b75a  mov     eax, 0Ah
0x18006b75f  mov     word ptr [rbp+0C0h+pvarg], ax
0x18006b763  mov     dword ptr [rbp+0C0h+pvarg+8], 80020004h
0x18006b76a  lea     r12, [rdi+18h]
0x18006b76e  xor     r13d, r13d
0x18006b771  mov     [rsp+1C0h+var_190], r13
0x18006b776  mov     [rsp+1C0h+var_198], r13
0x18006b77b  lea     rax, [rbp+0C0h+var_D0]
0x18006b77f  mov     [rsp+1C0h+var_1A0], rax
0x18006b784  lea     r9, [rbp+0C0h+pvarg]
0x18006b788  xor     r8d, r8d
0x18006b78b  xor     edx, edx
0x18006b78d  mov     rcx, r12
0x18006b790  call    ?Initialize@?$CXxxJob@V?$IDispatchImpl@UIInstallationJob@@$1?IID_IInstallationJob@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UIInstallationCompletedCallback@@VCInstallationCompletedCallbackArgs@@$0PPPPPPPP@@@QEAAJPEAUIUnknown@@0AEAUtagVARIANT@@PEBDPEAPEAUISusInternal@@PEAUHWND__@@@Z; CXxxJob<ATL::IDispatchImpl<IInstallationJob,&_GUID const IID_IInstallationJob,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>,IInstallationCompletedCallback,CInstallationCompletedCallbackArgs,4294967295>::Initialize(IUnknown *,IUnknown *,tagVARIANT &,char const *,ISusInternal * *,HWND__ *)
0x18006b795  mov     esi, eax
0x18006b797  test    eax, eax
0x18006b799  jns     short loc_18006B7A5
0x18006b79b  mov     edx, 39Fh
0x18006b7a0  jmp     loc_18006B84B
0x18006b7a5  mov     r8, [rbp+0C0h+var_F0]
0x18006b7a9  mov     rax, [r14+1C0h]
0x18006b7b0  mov     [rbp+0C0h+var_120], rax
0x18006b7b4  mov     rax, [r14+1B8h]
0x18006b7bb  mov     [rbp+0C0h+var_118], rax
0x18006b7bf  mov     rax, [r14+1C8h]
0x18006b7c6  mov     [rbp+0C0h+var_110], rax
0x18006b7ca  mov     rax, rbx
0x18006b7cd  lea     rcx, [rbx+30h]
0x18006b7d1  neg     rax
0x18006b7d4  sbb     rdx, rdx
0x18006b7d7  and     rdx, rcx
0x18006b7da  lea     rax, [rbp+0C0h+var_120]
0x18006b7de  mov     [rsp+1C0h+var_168], rax
0x18006b7e3  mov     rax, [r14+198h]
0x18006b7ea  mov     [rsp+1C0h+var_170], rax
0x18006b7ef  mov     rax, [r14+190h]
0x18006b7f6  mov     [rsp+1C0h+var_178], rax
0x18006b7fb  mov     rax, [r14+180h]
0x18006b802  mov     qword ptr [rsp+1C0h+var_180], rax
0x18006b807  mov     rax, [rsp+1C0h+bstrString]
0x18006b80c  mov     [rsp+1C0h+var_188], rax
0x18006b811  mov     rax, [r14+1A8h]
0x18006b818  mov     [rsp+1C0h+var_190], rax
0x18006b81d  mov     [rsp+1C0h+var_198], r8
0x18006b822  mov     rax, [rbp+0C0h+var_140]
0x18006b826  mov     [rsp+1C0h+var_1A0], rax
0x18006b82b  mov     r9d, [rsp+1C0h+var_150]
0x18006b830  mov     r14d, [rsp+1C0h+var_14C]
0x18006b835  mov     r8d, r14d
0x18006b838  mov     rcx, rdi
0x18006b83b  call    ?BeginInstall@FederatedInstallJob@@QEAAJPEAUIUpdateSession2@@W4tagDSDeploymentOperation@@KPEAUHWND__@@PEAUIUpdateCollection@@_KPEB_WPEAX55UtagAttributeTargeting@@@Z; FederatedInstallJob::BeginInstall(IUpdateSession2 *,tagDSDeploymentOperation,ulong,HWND__ *,IUpdateCollection *,unsigned __int64,wchar_t const *,void *,wchar_t const *,wchar_t const *,tagAttributeTargeting)
0x18006b840  mov     esi, eax
0x18006b842  test    eax, eax
0x18006b844  jns     short loc_18006B850
0x18006b846  mov     edx, 3B0h
0x18006b84b  xor     r15d, r15d
0x18006b84e  jmp     short loc_18006B8CE
0x18006b850  mov     rax, [r15]
0x18006b853  mov     rsi, [rax+20h]
0x18006b857  mov     rcx, [rbp+0C0h+var_F8]
0x18006b85b  test    rcx, rcx
0x18006b85e  jz      short loc_18006B870
0x18006b860  mov     r8, [rcx]
0x18006b863  mov     rax, [r8+10h]
0x18006b867  call    _guard_dispatch_icall
0x18006b86c  mov     [rbp+0C0h+var_F8], r13
0x18006b870  lea     r8, [rbp+0C0h+var_F8]
0x18006b874  mov     edx, r14d
0x18006b877  mov     rcx, r15
0x18006b87a  mov     rax, rsi
0x18006b87d  call    _guard_dispatch_icall
0x18006b882  mov     esi, eax
0x18006b884  mov     rax, [r12]
0x18006b888  mov     rcx, r12
0x18006b88b  mov     rax, [rax+50h]
0x18006b88f  call    _guard_dispatch_icall
0x18006b894  mov     r14d, eax
0x18006b897  xor     r15d, r15d
0x18006b89a  test    esi, esi
0x18006b89c  jns     short loc_18006B8E6
0x18006b89e  lea     rax, aFailureEncount_0; "Failure encountered in Install."
  ... truncated ...
```
