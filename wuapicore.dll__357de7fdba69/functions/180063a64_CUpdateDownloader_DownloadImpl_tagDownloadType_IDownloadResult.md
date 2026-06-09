# CUpdateDownloader::DownloadImpl(tagDownloadType,IDownloadResult * *)

- ea: `0x180063a64`
- end: `0x180063f55`
- name: `?DownloadImpl@CUpdateDownloader@@AEAAJW4tagDownloadType@@PEAPEAUIDownloadResult@@@Z`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800639a0`
- `0x1800639f0`

## callees

- `0x180006ac4`
- `0x18000ed90`
- `0x18002d41c`
- `0x180063a64`
- `0x18006508c`
- `0x18006526c`
- `0x180065434`
- `0x180065934`
- `0x18007f824`
- `0x18008d4d4`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b6c`
- `OLEAUT32!__imp_VariantInit` at `0x180063b41`
- `OLEAUT32!__imp_VariantInit` at `0x180063b41`

## string_xrefs

- `0x180063aac`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180063b0a`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180063bf4`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180063dc9`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180063ea3`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180063edf`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CUpdateDownloader::DownloadImpl(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // eax
  int v10; // edi
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 *v13; // r15
  TraceLoggingCorrelationVector *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  unsigned __int64 v18; // r9
  __int64 v19; // rdi
  unsigned int DownloadFlags; // r8d
  __int64 *v21; // rdx
  int v22; // eax
  __int64 (__fastcall *v23)(__int64, __int64 *); // rsi
  int v24; // eax
  int v25; // esi
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+74h] [rbp-8Ch]
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v38)(__int64, __int64 *, COMAPIHelper *, _QWORD); // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  COMAPIHelper *v43; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v44; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-8h] BYREF
  char v46[144]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 296;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)v6,
      v29);
    return v6;
  }
  if ( *(_DWORD *)(a1 + 16) == 1 )
  {
    v6 = -2145124298;
    v7 = 297;
    goto LABEL_3;
  }
  *a3 = 0;
  v31 = 0;
  v9 = ATL::CComObject<FederatedDownloadJob>::CreateInstance(&v31);
  v10 = v9;
  v11 = v31;
  if ( v9 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v31 + 8) + 8LL))(v31 + 8);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.lVal = -2147352572;
    pvarg.vt = 10;
    v44 = 0;
    if ( a1 != -56 )
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    v42 = a1 + 56;
    if ( !*(_QWORD *)(a1 + 136) )
    {
      v10 = -2145124348;
      v12 = 316;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)(unsigned int)v10,
        v29);
LABEL_39:
      if ( a1 != -56 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
      goto LABEL_55;
    }
    v13 = &qword_1800EF060;
    if ( *(_QWORD *)(a1 + 128) )
      v13 = *(__int64 **)(a1 + 128);
    v14 = *(TraceLoggingCorrelationVector **)(a1 + 256);
    v46[0] = 0;
    if ( v14 )
    {
      if ( !TraceLoggingCorrelationVector::Increment(v14, v46) )
      {
        v12 = 324;
LABEL_20:
        v10 = -2147418113;
        goto LABEL_21;
      }
    }
    else if ( v13 != (__int64 *)-176LL
           && !TraceLoggingCorrelationVector::Increment((TraceLoggingCorrelationVector *)(v13 + 22), v46) )
    {
      v12 = 328;
      goto LABEL_20;
    }
    v43 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, COMAPIHelper **))(**(_QWORD **)(a1 + 136) + 112LL))(
            *(_QWORD *)(a1 + 136),
            &v43);
    if ( v10 < 0 )
    {
      v16 = 332;
LABEL_31:
      v18 = (unsigned int)v10;
      goto LABEL_37;
    }
    v10 = CUpdateDownloader::ValidateDownloadTypeCompatibility(v15, a2, (__int64)v43);
    if ( v10 < 0 )
    {
      v16 = 335;
      goto LABEL_31;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
    {
      v10 = COMAPIHelper::ValidateSessionData(v43, *(struct IUpdateCollection **)(a1 + 192), v17);
      if ( v10 < 0 )
      {
        v16 = 339;
        goto LABEL_31;
      }
    }
    v10 = CXxxJobImpl::Initialize((void **)(v11 + 24), 0, 0, &pvarg, v46, 0, 0);
    if ( v10 < 0 )
    {
      v16 = 342;
      goto LABEL_31;
    }
    v19 = *(_QWORD *)(a1 + 208);
    v32 = *(_QWORD *)(a1 + 216);
    v33 = *(_QWORD *)(a1 + 224);
    *(_BYTE *)(a1 + 177) = a2 == 1;
    v38 = *(__int64 (__fastcall **)(__int64, __int64 *, COMAPIHelper *, _QWORD))(*(_QWORD *)v11 + 24LL);
    v34 = *(_QWORD *)(a1 + 192);
    v35 = *(_QWORD *)(a1 + 120);
    v36 = *(_QWORD *)(a1 + 184);
    v37 = *(_QWORD *)(a1 + 232);
    CUpdateDownloader::SelectNetworkCostPolicy(a1);
    v30 = *(_DWORD *)(a1 + 144);
    DownloadFlags = CUpdateDownloader::GetDownloadFlags((CUpdateDownloader *)a1);
    if ( v13 )
      v21 = v13 + 6;
    else
      v21 = 0;
    v39 = v32;
    v40 = v19;
    v41 = v33;
    v29 = v30;
    v22 = v38(v11, v21, v43, DownloadFlags);
    v10 = v22;
    if ( v22 < 0 )
    {
      v18 = (unsigned int)v22;
      v16 = 363;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)v18,
        v29);
      if ( v43 )
      {
        (*(void (__fastcall **)(COMAPIHelper *))(*(_QWORD *)v43 + 16LL))(v43);
        v43 = 0;
      }
      goto LABEL_39;
    }
    if ( v43 )
    {
      (*(void (__fastcall **)(COMAPIHelper *))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    if ( a1 != -56 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v11 + 16) + 24LL);
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    v10 = v23(v11 + 16, &v44);
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v11 + 8) + 80LL))(v11 + 8);
    v25 = v24;
    if ( v10 >= 0 )
    {
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
          (const char *)(unsigned int)v24,
          v30);
        v10 = v25;
        goto LABEL_55;
      }
      v28 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v44)(
              v44,
              &GUID_daa4fdd0_4727_4dbe_a1e7_745dca317144,
              a3);
      v10 = v28;
      if ( v28 >= 0 )
      {
        v10 = 0;
LABEL_55:
        if ( v44 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          v44 = 0;
        }
        goto LABEL_57;
      }
      v26 = (unsigned int)v28;
      v27 = 372;
    }
    else
    {
      v26 = (unsigned int)v10;
      v27 = 369;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)v26,
      v30);
    goto LABEL_55;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12E,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
    (const char *)(unsigned int)v9,
    v29);
LABEL_57:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 8) + 16LL))(v11 + 8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180063a64  mov     [rsp-8+arg_18], rbx
0x180063a69  push    rbp
0x180063a6a  push    rsi
0x180063a6b  push    rdi
0x180063a6c  push    r12
0x180063a6e  push    r13
0x180063a70  push    r14
0x180063a72  push    r15
0x180063a74  lea     rbp, [rsp-0B0h]
0x180063a7c  sub     rsp, 1B0h
0x180063a83  mov     rax, cs:__security_cookie
0x180063a8a  xor     rax, rsp
0x180063a8d  mov     [rbp+0E0h+var_40], rax
0x180063a94  mov     r12, r8
0x180063a97  mov     r13d, edx
0x180063a9a  mov     rsi, rcx
0x180063a9d  test    r8, r8
0x180063aa0  jnz     short loc_180063AC9
0x180063aa2  mov     ebx, 80004003h
0x180063aa7  mov     edx, 128h; void *
0x180063aac  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063ab3  mov     r9d, ebx; char *
0x180063ab6  mov     rcx, [rbp+0E8h]; this
0x180063abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ac2  mov     eax, ebx
0x180063ac4  jmp     loc_180063F2B
0x180063ac9  cmp     dword ptr [rcx+10h], 1
0x180063acd  jnz     short loc_180063ADB
0x180063acf  mov     ebx, 80240036h
0x180063ad4  mov     edx, 129h
0x180063ad9  jmp     short loc_180063AAC
0x180063adb  mov     qword ptr [r8], 0
0x180063ae2  mov     [rsp+1E0h+var_168], 0
0x180063aeb  lea     rcx, [rsp+1E0h+var_168]
0x180063af0  call    ?CreateInstance@?$CComObject@VFederatedDownloadJob@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FederatedDownloadJob>::CreateInstance(ATL::CComObject<FederatedDownloadJob> * *)
0x180063af5  mov     edi, eax
0x180063af7  mov     rbx, [rsp+1E0h+var_168]
0x180063afc  test    eax, eax
0x180063afe  jns     short loc_180063B20
0x180063b00  mov     rcx, [rbp+0E8h]; this
0x180063b07  mov     r9d, eax; char *
0x180063b0a  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063b11  mov     edx, 12Eh; void *
0x180063b16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063b1b  jmp     loc_180063F13
0x180063b20  lea     rcx, [rbx+8]
0x180063b24  mov     rax, [rcx]
0x180063b27  mov     rax, [rax+8]
0x180063b2b  call    _guard_dispatch_icall
0x180063b30  xorps   xmm0, xmm0
0x180063b33  xor     eax, eax
0x180063b35  movups  xmmword ptr [rbp+0E0h+pvarg], xmm0
0x180063b39  mov     qword ptr [rbp+0E0h+pvarg+10h], rax
0x180063b3d  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180063b41  call    cs:__imp_VariantInit
0x180063b47  mov     dword ptr [rbp+0E0h+pvarg+8], 80020004h
0x180063b4e  mov     eax, 0Ah
0x180063b53  mov     word ptr [rbp+0E0h+pvarg], ax
0x180063b57  mov     [rbp+0E0h+var_F0], 0
0x180063b5f  lea     r14, [rsi+38h]
0x180063b63  test    r14, r14
0x180063b66  jz      short loc_180063B72
0x180063b68  lea     rcx, [r14+8]; lpCriticalSection
0x180063b6c  call    cs:__imp_EnterCriticalSection
0x180063b72  mov     [rbp+0E0h+var_100], r14
0x180063b76  cmp     qword ptr [rsi+88h], 0
0x180063b7e  jnz     short loc_180063B8C
0x180063b80  mov     edi, 80240004h
0x180063b85  mov     edx, 13Ch
0x180063b8a  jmp     short loc_180063BEA
0x180063b8c  mov     rax, [rsi+80h]
0x180063b93  lea     r15, qword_1800EF060
0x180063b9a  xor     edi, edi
0x180063b9c  test    rax, rax
0x180063b9f  cmovnz  r15, rax
0x180063ba3  mov     rcx, [rsi+100h]; this
0x180063baa  mov     [rbp+0E0h+var_D0], dil
0x180063bae  test    rcx, rcx
0x180063bb1  jz      short loc_180063BC7
0x180063bb3  lea     rdx, [rbp+0E0h+var_D0]; char *
0x180063bb7  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180063bbc  test    al, al
0x180063bbe  jnz     short loc_180063C05
0x180063bc0  mov     edx, 144h
0x180063bc5  jmp     short loc_180063BE5
0x180063bc7  lea     rcx, [r15+0B0h]; this
0x180063bce  test    rcx, rcx
0x180063bd1  jz      short loc_180063C05
0x180063bd3  lea     rdx, [rbp+0E0h+var_D0]; char *
0x180063bd7  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180063bdc  test    al, al
0x180063bde  jnz     short loc_180063C05
0x180063be0  mov     edx, 148h; void *
0x180063be5  mov     edi, 8000FFFFh
0x180063bea  mov     rcx, [rbp+0E8h]; this
0x180063bf1  mov     r9d, edi; char *
0x180063bf4  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063c00  jmp     loc_180063DFA
0x180063c05  mov     [rbp+0E0h+var_F8], rdi
0x180063c09  mov     rcx, [rsi+88h]
0x180063c10  mov     rax, [rcx]
0x180063c13  lea     rdx, [rbp+0E0h+var_F8]
0x180063c17  mov     rax, [rax+70h]
0x180063c1b  call    _guard_dispatch_icall
0x180063c20  mov     edi, eax
0x180063c22  test    eax, eax
0x180063c24  jns     short loc_180063C2D
0x180063c26  mov     edx, 14Ch
0x180063c2b  jmp     short loc_180063CAB
0x180063c2d  mov     r8, [rbp+0E0h+var_F8]
0x180063c31  mov     edx, r13d
0x180063c34  call    ?ValidateDownloadTypeCompatibility@CUpdateDownloader@@AEAAJW4tagDownloadType@@PEAUIUpdateCollection@@@Z; CUpdateDownloader::ValidateDownloadTypeCompatibility(tagDownloadType,IUpdateCollection *)
0x180063c39  mov     edi, eax
0x180063c3b  test    eax, eax
0x180063c3d  jns     short loc_180063C46
0x180063c3f  mov     edx, 14Fh
0x180063c44  jmp     short loc_180063CAB
0x180063c46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x180063c4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x180063c52  test    al, al
0x180063c54  jz      short loc_180063C73
0x180063c56  mov     rdx, [rsi+0C0h]; struct IUpdateCollection *
0x180063c5d  mov     rcx, [rbp+0E0h+var_F8]; this
0x180063c61  call    ?ValidateSessionData@COMAPIHelper@@YAJPEAUIUpdateCollection@@PEB_W@Z; COMAPIHelper::ValidateSessionData(IUpdateCollection *,wchar_t const *)
0x180063c66  mov     edi, eax
0x180063c68  test    eax, eax
0x180063c6a  jns     short loc_180063C73
0x180063c6c  mov     edx, 153h
0x180063c71  jmp     short loc_180063CAB
0x180063c73  lea     rcx, [rbx+18h]; this
0x180063c77  mov     [rsp+1E0h+var_1B0], 0; HWND
0x180063c80  mov     [rsp+1E0h+var_1B8], 0; struct ISusInternal **
0x180063c89  lea     rax, [rbp+0E0h+var_D0]
0x180063c8d  mov     [rsp+1E0h+var_1C0], rax; char *
0x180063c92  lea     r9, [rbp+0E0h+pvarg]; struct tagVARIANT *
0x180063c96  xor     r8d, r8d; struct IUnknown *
0x180063c99  xor     edx, edx; struct IUnknown *
0x180063c9b  call    ?Initialize@CXxxJobImpl@@QEAAJPEAUIUnknown@@0AEAUtagVARIANT@@PEBDPEAPEAUISusInternal@@PEAUHWND__@@@Z; CXxxJobImpl::Initialize(IUnknown *,IUnknown *,tagVARIANT &,char const *,ISusInternal * *,HWND__ *)
0x180063ca0  mov     edi, eax
0x180063ca2  test    eax, eax
0x180063ca4  jns     short loc_180063CB3
0x180063ca6  mov     edx, 156h
0x180063cab  mov     r9d, edi
0x180063cae  jmp     loc_180063DC9
0x180063cb3  mov     rdi, [rsi+0D0h]
0x180063cba  mov     rax, [rsi+0D8h]
0x180063cc1  mov     [rbp+0E0h+var_160], rax
0x180063cc5  mov     rax, [rsi+0E0h]
0x180063ccc  mov     [rbp+0E0h+var_158], rax
0x180063cd0  cmp     r13d, 1
0x180063cd4  setz    al
0x180063cd7  mov     [rsi+0B1h], al
0x180063cdd  mov     rax, [rbx]
0x180063ce0  mov     rax, [rax+18h]
0x180063ce4  mov     [rbp+0E0h+var_130], rax
0x180063ce8  mov     r13, [rsi+0C8h]
0x180063cef  mov     rax, [rsi+0C0h]
0x180063cf6  mov     [rbp+0E0h+var_150], rax
0x180063cfa  mov     rax, [rsi+78h]
0x180063cfe  mov     [rbp+0E0h+var_148], rax
0x180063d02  mov     rax, [rsi+0B8h]
0x180063d09  mov     [rbp+0E0h+var_140], rax
0x180063d0d  mov     rax, [rsi+0E8h]
0x180063d14  mov     [rbp+0E0h+var_138], rax
0x180063d18  mov     rcx, rsi
0x180063d1b  call    ?SelectNetworkCostPolicy@CUpdateDownloader@@AEAA?AW4tagNetworkCostPolicy@@XZ; CUpdateDownloader::SelectNetworkCostPolicy(void)
0x180063d20  mov     [rsp+1E0h+var_170], eax
0x180063d24  mov     eax, [rsi+90h]
0x180063d2a  mov     [rsp+1E0h+var_16C], eax
0x180063d2e  mov     rcx, rsi; this
0x180063d31  call    ?GetDownloadFlags@CUpdateDownloader@@QEAAKXZ; CUpdateDownloader::GetDownloadFlags(void)
0x180063d36  mov     r8d, eax
0x180063d39  test    r15, r15
0x180063d3c  jz      short loc_180063D44
0x180063d3e  lea     rdx, [r15+30h]
0x180063d42  jmp     short loc_180063D46
0x180063d44  xor     edx, edx
0x180063d46  mov     rax, [rbp+0E0h+var_160]
0x180063d4a  mov     [rbp+0E0h+var_120], rax
0x180063d4e  mov     [rbp+0E0h+var_118], rdi
0x180063d52  mov     rax, [rbp+0E0h+var_158]
0x180063d56  mov     [rbp+0E0h+var_110], rax
0x180063d5a  lea     rcx, [rsi+108h]
0x180063d61  lea     rax, [rbp+0E0h+var_120]
0x180063d65  mov     [rsp+1E0h+var_180], rax
0x180063d6a  mov     [rsp+1E0h+var_188], r13
0x180063d6f  mov     r9, [rbp+0E0h+var_150]
0x180063d73  mov     [rsp+1E0h+var_190], r9
0x180063d78  mov     r9, [rbp+0E0h+var_148]
0x180063d7c  mov     [rsp+1E0h+var_198], r9
0x180063d81  mov     r9, [rbp+0E0h+var_140]
0x180063d85  mov     [rsp+1E0h+var_1A0], r9
0x180063d8a  mov     r9, [rbp+0E0h+var_138]
0x180063d8e  mov     [rsp+1E0h+var_1A8], r9
0x180063d93  mov     [rsp+1E0h+var_1B0], rcx
0x180063d98  mov     eax, [rsp+1E0h+var_170]
0x180063d9c  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180063da0  mov     ecx, [rsp+1E0h+var_16C]
0x180063da4  mov     dword ptr [rsp+1E0h+var_1C0], ecx; int
0x180063da8  mov     r9d, r8d
0x180063dab  mov     r8, [rbp+0E0h+var_F8]
0x180063daf  mov     rcx, rbx
0x180063db2  mov     rax, [rbp+0E0h+var_130]
0x180063db6  call    _guard_dispatch_icall
0x180063dbb  mov     edi, eax
0x180063dbd  test    eax, eax
0x180063dbf  jns     short loc_180063E12
0x180063dc1  mov     r9d, eax; char *
0x180063dc4  mov     edx, 16Bh; void *
0x180063dc9  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063dd0  mov     rcx, [rbp+0E8h]; this
0x180063dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ddc  nop
0x180063ddd  mov     rcx, [rbp+0E0h+var_F8]
0x180063de1  test    rcx, rcx
0x180063de4  jz      short loc_180063DFA
0x180063de6  mov     rax, [rcx]
0x180063de9  mov     rax, [rax+10h]
0x180063ded  call    _guard_dispatch_icall
0x180063df2  mov     [rbp+0E0h+var_F8], 0
0x180063dfa  test    r14, r14
0x180063dfd  jz      loc_180063EF6
0x180063e03  lea     rcx, [r14+8]; lpCriticalSection
0x180063e07  call    cs:__imp_LeaveCriticalSection
0x180063e0d  jmp     loc_180063EF6
0x180063e12  mov     rcx, [rbp+0E0h+var_F8]
0x180063e16  test    rcx, rcx
0x180063e19  jz      short loc_180063E2F
0x180063e1b  mov     rax, [rcx]
0x180063e1e  mov     rax, [rax+10h]
0x180063e22  call    _guard_dispatch_icall
0x180063e27  mov     [rbp+0E0h+var_F8], 0
0x180063e2f  test    r14, r14
0x180063e32  jz      short loc_180063E3E
0x180063e34  lea     rcx, [r14+8]; lpCriticalSection
0x180063e38  call    cs:__imp_LeaveCriticalSection
0x180063e3e  mov     rax, [rbx+10h]
0x180063e42  mov     rsi, [rax+18h]
0x180063e46  mov     rcx, [rbp+0E0h+var_F0]
0x180063e4a  test    rcx, rcx
0x180063e4d  jz      short loc_180063E63
0x180063e4f  mov     rdx, [rcx]
0x180063e52  mov     rax, [rdx+10h]
0x180063e56  call    _guard_dispatch_icall
0x180063e5b  mov     [rbp+0E0h+var_F0], 0
0x180063e63  lea     rdx, [rbp+0E0h+var_F0]
0x180063e67  lea     rcx, [rbx+10h]
0x180063e6b  mov     rax, rsi
0x180063e6e  call    _guard_dispatch_icall
0x180063e73  mov     edi, eax
0x180063e75  lea     rcx, [rbx+8]
0x180063e79  mov     rax, [rcx]
0x180063e7c  mov     rax, [rax+50h]
0x180063e80  call    _guard_dispatch_icall
0x180063e85  mov     esi, eax
0x180063e87  test    edi, edi
0x180063e89  jns     short loc_180063E95
0x180063e8b  mov     r9d, edi
0x180063e8e  mov     edx, 171h
0x180063e93  jmp     short loc_180063EDF
0x180063e95  test    esi, esi
0x180063e97  jns     short loc_180063EB8
0x180063e99  mov     rcx, [rbp+0E8h]; this
0x180063ea0  mov     r9d, esi; char *
0x180063ea3  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063eaa  mov     edx, 172h; void *
0x180063eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063eb4  mov     edi, esi
0x180063eb6  jmp     short loc_180063EF6
0x180063eb8  mov     rcx, [rbp+0E0h+var_F0]
0x180063ebc  mov     rax, [rcx]
0x180063ebf  mov     r8, r12
0x180063ec2  lea     rdx, _GUID_daa4fdd0_4727_4dbe_a1e7_745dca317144
0x180063ec9  mov     rax, [rax]
0x180063ecc  call    _guard_dispatch_icall
0x180063ed1  mov     edi, eax
0x180063ed3  test    eax, eax
0x180063ed5  jns     short loc_180063EF4
0x180063ed7  mov     r9d, eax; char *
0x180063eda  mov     edx, 174h; void *
0x180063edf  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180063ee6  mov     rcx, [rbp+0E8h]; this
0x180063eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ef2  jmp     short loc_180063EF6
0x180063ef4  xor     edi, edi
0x180063ef6  mov     rcx, [rbp+0E0h+var_F0]
0x180063efa  test    rcx, rcx
0x180063efd  jz      short loc_180063F13
0x180063eff  mov     rax, [rcx]
0x180063f02  mov     rax, [rax+10h]
0x180063f06  call    _guard_dispatch_icall
0x180063f0b  mov     [rbp+0E0h+var_F0], 0
0x180063f13  test    rbx, rbx
0x180063f16  jz      short loc_180063F29
0x180063f18  lea     rcx, [rbx+8]
0x180063f1c  mov     rdx, [rcx]
0x180063f1f  mov     rax, [rdx+10h]
0x180063f23  call    _guard_dispatch_icall
0x180063f28  nop
  ... truncated ...
```
