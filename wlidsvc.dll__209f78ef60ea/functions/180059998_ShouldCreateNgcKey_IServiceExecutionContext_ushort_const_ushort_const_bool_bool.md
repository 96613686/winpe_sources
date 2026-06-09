# ShouldCreateNgcKey(IServiceExecutionContext *,ushort const *,ushort const *,bool,bool &)

- ea: `0x180059998`
- end: `0x180059dee`
- name: `?ShouldCreateNgcKey@@YAJPEAVIServiceExecutionContext@@PEBG1_NAEA_N@Z`
- size: `1110`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, bool, DWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800563d0`

## callees

- `0x180001678`
- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180054fb4`
- `0x18005538c`
- `0x180055edc`
- `0x180055f18`
- `0x180059998`
- `0x180128010`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180059ae6`
- `ncrypt!NCryptOpenStorageProvider` at `0x180059ae6`
- `ncrypt!NCryptGetProperty` at `0x180059b22`
- `ncrypt!NCryptGetProperty` at `0x180059b22`

## string_xrefs

- `0x1800599f0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059b47`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059be9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059c0e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059c40`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059cd6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059bb2`: `login.live.com`
- `0x1800599c8`: `ShouldCreateNgcKey`
- `0x180059c39`: `ShouldCreateNgcKey`
- `0x180059ccf`: `ShouldCreateNgcKey`
- `0x180059d7f`: `ShouldCreateNgcKey`
- `0x180059da3`: `No usable NGC containers found for SID %ls.`
- `0x180059c01`: `createNgcKey is true but UI is disallowed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ShouldCreateNgcKey(
        struct IServiceExecutionContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        char *a5)
{
  SECURITY_STATUS Property; // edi
  __int64 v9; // rsi
  char *v10; // r14
  int v11; // r9d
  int v12; // eax
  char v13; // r15
  int v14; // r9d
  unsigned int v15; // ebx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  DWORD *pcbResult; // [rsp+20h] [rbp-E0h]
  DWORD *pcbResulta; // [rsp+20h] [rbp-E0h]
  DWORD *pcbResultb; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  BYTE pbOutput[4]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch] BYREF
  SECURITY_STATUS v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[3]; // [rsp+70h] [rbp-90h] BYREF
  NCRYPT_PROV_HANDLE phProvider[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v31[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v32[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v33[6]; // [rsp+D0h] [rbp-30h] BYREF
  char v34; // [rsp+100h] [rbp+0h]
  char v35; // [rsp+150h] [rbp+50h] BYREF
  char v36; // [rsp+168h] [rbp+68h]

  v36 = a4;
  Property = 0;
  v23 = 0;
  v33[0] = "ShouldCreateNgcKey";
  v33[1] = &v23;
  v33[2] = 0;
  v33[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "ShouldCreateNgcKey",
    (const char *)0xF0B,
    0,
    (const unsigned __int16 *)pcbResult);
  v9 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 48LL))(a1);
  v10 = a5;
  *a5 = 0;
  v25 = 0;
  v32[0] = 0;
  v32[2] = v9;
  v32[1] = 0;
  memset(v31, 0, sizeof(v31));
  *(_DWORD *)pbOutput = 0;
  v33[4] = &v25;
  v33[5] = v9;
  v34 = 1;
  while ( 1 )
  {
    memset(v29, 0, sizeof(v29));
    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *, __int64 *))(*(_QWORD *)v9 + 56LL))(
            v9,
            a2,
            v29,
            &v25);
    v23 = v11;
    if ( v11 == -2146893782 || v29[0] && *(_DWORD *)(v29[0] + 16LL) != 2 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0xF3Bu,
        L"No usable NGC containers found for SID %ls.",
        a2);
      if ( v29[0] )
      {
        LODWORD(pcbResultb) = *(_DWORD *)(v29[0] + 16LL);
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0xF3Eu,
          L"ContainerStatus = %d",
          pcbResultb);
      }
      v23 = 0;
      goto LABEL_29;
    }
    if ( v11 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "ShouldCreateNgcKey",
        0xF46u,
        v11,
        "hr");
LABEL_29:
      Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v29);
      goto LABEL_19;
    }
    if ( v29[0] )
    {
      v12 = *(_DWORD *)(v29[0] + 56LL);
      if ( (v12 & 1) != 0 )
        break;
    }
    Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v29);
  }
  if ( (v12 & 2) == 0 )
  {
    v13 = 0;
LABEL_16:
    Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v29);
    v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD *, _QWORD *))(*(_QWORD *)v9 + 72LL))(
            v9,
            L"login.live.com",
            0,
            a3,
            a2,
            v31,
            v32);
    v23 = v14;
    if ( v14 == -2146893782 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0xF79u,
        L"No NGC keys found for CID %ls.",
        a3);
      if ( v36 == 1 )
      {
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0xF7Fu,
          L"createNgcKey is true but UI is disallowed.");
        v23 = -2138701812;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "ShouldCreateNgcKey",
          0xF80u,
          -2138701812,
          "hr = ONL_E_ACTION_REQUIRED");
        goto LABEL_19;
      }
      *v10 = 1;
      v23 = 0;
    }
    else
    {
      if ( v14 >= 0 )
        goto LABEL_19;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "ShouldCreateNgcKey",
        0xF89u,
        v14,
        "hr");
    }
    goto LABEL_25;
  }
  v13 = 1;
  memset(phProvider, 0, sizeof(phProvider));
  Property = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( Property < 0
    || (LODWORD(a5) = 0,
        Property = NCryptGetProperty(
                     phProvider[0],
                     L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY",
                     pbOutput,
                     4u,
                     (DWORD *)&a5,
                     0),
        Property < 0)
    || !*(_DWORD *)pbOutput )
  {
    Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>(phProvider);
    goto LABEL_16;
  }
  LODWORD(pcbResulta) = *(_DWORD *)pbOutput;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0xF63u,
    L"TPM is vulnerable, do not upsell NGC %d.",
    pcbResulta);
  *v10 = 0;
  v23 = 0;
  Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>(phProvider);
  Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v29);
LABEL_25:
  if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
  {
    v26 = v23;
    v27 = *(_DWORD *)pbOutput;
    v28 = Property;
    LOBYTE(a5) = v13;
    v35 = *v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (__int64)byte_180198479,
      v18,
      v19,
      (__int64)&v35,
      (__int64)&a5,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26);
  }
LABEL_19:
  v15 = v23;
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 80LL))(v9);
    v25 = 0;
  }
  Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v31);
  Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(v32);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
  return v15;
}

```

## disassembly

```asm
0x180059998  mov     [rsp-8+arg_8], rbx
0x18005999d  mov     [rsp-8+arg_18], r9b
0x1800599a2  push    rbp
0x1800599a3  push    rsi
0x1800599a4  push    rdi
0x1800599a5  push    r12
0x1800599a7  push    r13
0x1800599a9  push    r14
0x1800599ab  push    r15
0x1800599ad  lea     rbp, [rsp-10h]
0x1800599b2  sub     rsp, 110h
0x1800599b9  mov     r13, r8
0x1800599bc  mov     r12, rdx
0x1800599bf  mov     rbx, rcx
0x1800599c2  xor     edi, edi
0x1800599c4  mov     [rsp+140h+var_F0], edi
0x1800599c8  lea     rcx, aShouldcreateng; "ShouldCreateNgcKey"
0x1800599cf  mov     [rbp+40h+var_70], rcx
0x1800599d3  lea     rax, [rsp+140h+var_F0]
0x1800599d8  mov     [rbp+40h+var_68], rax
0x1800599dc  mov     [rbp+40h+var_60], rdi
0x1800599e0  mov     [rbp+40h+var_58], rdi
0x1800599e4  xor     r9d, r9d; unsigned int
0x1800599e7  mov     r8d, 0F0Bh; char *
0x1800599ed  mov     rdx, rcx; char *
0x1800599f0  lea     r15, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800599f7  mov     rcx, r15; this
0x1800599fa  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800599ff  nop
0x180059a00  mov     rax, [rbx]
0x180059a03  mov     rcx, rbx
0x180059a06  mov     rax, [rax+30h]
0x180059a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a0f  mov     rsi, rax
0x180059a12  mov     r14, [rbp+40h+arg_20]
0x180059a16  mov     [r14], dil
0x180059a19  mov     [rsp+140h+var_E8], rdi
0x180059a1e  mov     [rbp+40h+var_88], rdi
0x180059a22  mov     [rbp+40h+var_78], rax
0x180059a26  mov     [rbp+40h+var_80], rdi
0x180059a2a  mov     [rbp+40h+var_A0], rdi
0x180059a2e  mov     [rbp+40h+var_90], rdi
0x180059a32  mov     [rbp+40h+var_98], rdi
0x180059a36  mov     dword ptr [rsp+140h+pbOutput], edi
0x180059a3a  lea     rax, [rsp+140h+var_E8]
0x180059a3f  mov     [rbp+40h+var_50], rax
0x180059a43  mov     [rbp+40h+var_48], rsi
0x180059a47  mov     [rbp+40h+var_40], 1
0x180059a4b  mov     [rsp+140h+var_D0], rdi
0x180059a50  mov     [rbp+40h+var_C0], rdi
0x180059a54  mov     [rsp+140h+var_C8], rdi
0x180059a59  mov     rax, [rsi]
0x180059a5c  lea     r9, [rsp+140h+var_E8]
0x180059a61  lea     r8, [rsp+140h+var_D0]
0x180059a66  mov     rdx, r12
0x180059a69  mov     rcx, rsi
0x180059a6c  mov     rax, [rax+38h]
0x180059a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a75  mov     r9d, eax; int
0x180059a78  mov     [rsp+140h+var_F0], eax
0x180059a7c  cmp     eax, 8009002Ah
0x180059a81  jz      loc_180059D9E
0x180059a87  mov     rcx, [rsp+140h+var_D0]
0x180059a8c  test    rcx, rcx
0x180059a8f  jz      short loc_180059A9B
0x180059a91  cmp     dword ptr [rcx+10h], 2
0x180059a95  jnz     loc_180059D9E
0x180059a9b  test    r9d, r9d
0x180059a9e  js      loc_180059D6D
0x180059aa4  test    rcx, rcx
0x180059aa7  jz      short loc_180059AB0
0x180059aa9  mov     eax, [rcx+38h]
0x180059aac  test    al, 1
0x180059aae  jnz     short loc_180059ABC
0x180059ab0  lea     rcx, [rsp+140h+var_D0]
0x180059ab5  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180059aba  jmp     short loc_180059A4B
0x180059abc  mov     ebx, 5
0x180059ac1  test    al, 2
0x180059ac3  jz      loc_180059B85
0x180059ac9  mov     r15b, 1
0x180059acc  mov     [rbp+40h+phProvider], rdi
0x180059ad0  mov     [rbp+40h+var_A8], rdi
0x180059ad4  mov     [rbp+40h+var_B0], rdi
0x180059ad8  xor     r8d, r8d; dwFlags
0x180059adb  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180059ae2  lea     rcx, [rbp+40h+phProvider]; phProvider
0x180059ae6  call    cs:__imp_NCryptOpenStorageProvider
0x180059aec  mov     edi, eax
0x180059aee  test    eax, eax
0x180059af0  js      loc_180059B7A
0x180059af6  mov     dword ptr [rbp+40h+arg_20], 0
0x180059afd  mov     [rsp+140h+dwFlags], 0; dwFlags
0x180059b05  lea     rax, [rbp+40h+arg_20]
0x180059b09  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180059b0e  lea     r9d, [rbx-1]; cbOutput
0x180059b12  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x180059b17  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x180059b1e  mov     rcx, [rbp+40h+phProvider]; hObject
0x180059b22  call    cs:__imp_NCryptGetProperty
0x180059b28  mov     edi, eax
0x180059b2a  test    eax, eax
0x180059b2c  js      short loc_180059B7A
0x180059b2e  mov     eax, dword ptr [rsp+140h+pbOutput]
0x180059b32  test    eax, eax
0x180059b34  jz      short loc_180059B7A
0x180059b36  mov     dword ptr [rsp+140h+pcbResult], eax
0x180059b3a  lea     r9, aTpmIsVulnerabl; "TPM is vulnerable, do not upsell NGC %d"...
0x180059b41  mov     r8d, 0F63h; unsigned int
0x180059b47  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059b4e  mov     ecx, ebx; unsigned __int8
0x180059b50  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059b55  mov     byte ptr [r14], 0
0x180059b59  mov     [rsp+140h+var_F0], 0
0x180059b61  lea     rcx, [rbp+40h+phProvider]
0x180059b65  call    ??1?$Auto@_KV?$NCryptKeyFunctor@_K@@VDummyContext@@@@QEAA@XZ; Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>(void)
0x180059b6a  nop
0x180059b6b  lea     rcx, [rsp+140h+var_D0]
0x180059b70  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180059b75  jmp     loc_180059CE2
0x180059b7a  lea     rcx, [rbp+40h+phProvider]
0x180059b7e  call    ??1?$Auto@_KV?$NCryptKeyFunctor@_K@@VDummyContext@@@@QEAA@XZ; Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,NCryptKeyFunctor<unsigned __int64>,DummyContext>(void)
0x180059b83  jmp     short loc_180059B88
0x180059b85  xor     r15b, r15b
0x180059b88  lea     rcx, [rsp+140h+var_D0]
0x180059b8d  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180059b92  mov     rax, [rsi]
0x180059b95  lea     rcx, [rbp+40h+var_88]
0x180059b99  mov     [rsp+140h+var_110], rcx
0x180059b9e  lea     rcx, [rbp+40h+var_A0]
0x180059ba2  mov     qword ptr [rsp+140h+dwFlags], rcx
0x180059ba7  mov     [rsp+140h+pcbResult], r12
0x180059bac  mov     r9, r13
0x180059baf  xor     r8d, r8d
0x180059bb2  lea     rdx, aLoginLiveCom; "login.live.com"
0x180059bb9  mov     rcx, rsi
0x180059bbc  mov     rax, [rax+48h]
0x180059bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bc5  mov     r9d, eax; int
0x180059bc8  mov     [rsp+140h+var_F0], eax
0x180059bcc  cmp     eax, 8009002Ah
0x180059bd1  jnz     loc_180059CB8
0x180059bd7  mov     [rsp+140h+pcbResult], r13
0x180059bdc  lea     r9, aNoNgcKeysFound; "No NGC keys found for CID %ls."
0x180059be3  mov     r8d, 0F79h; unsigned int
0x180059be9  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059bf0  mov     ecx, ebx; unsigned __int8
0x180059bf2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059bf7  cmp     [rbp+40h+arg_18], 1
0x180059bfb  jnz     loc_180059CAA
0x180059c01  lea     r9, aCreatengckeyIs; "createNgcKey is true but UI is disallow"...
0x180059c08  mov     r8d, 0F7Fh; unsigned int
0x180059c0e  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059c15  mov     ecx, ebx; unsigned __int8
0x180059c17  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059c1c  mov     r9d, 8086000Ch; int
0x180059c22  mov     [rsp+140h+var_F0], r9d
0x180059c27  lea     rax, aHrOnlEActionRe; "hr = ONL_E_ACTION_REQUIRED"
0x180059c2e  mov     [rsp+140h+pcbResult], rax; char *
0x180059c33  mov     r8d, 0F80h; unsigned int
0x180059c39  lea     rdx, aShouldcreateng; "ShouldCreateNgcKey"
0x180059c40  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059c47  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180059c4c  xor     edi, edi
0x180059c4e  mov     ebx, [rsp+140h+var_F0]
0x180059c52  mov     rdx, [rsp+140h+var_E8]
0x180059c57  test    rdx, rdx
0x180059c5a  jz      short loc_180059C70
0x180059c5c  mov     rax, [rsi]
0x180059c5f  mov     rcx, rsi
0x180059c62  mov     rax, [rax+50h]
0x180059c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c6b  mov     [rsp+140h+var_E8], rdi
0x180059c70  lea     rcx, [rbp+40h+var_A0]
0x180059c74  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180059c79  nop
0x180059c7a  lea     rcx, [rbp+40h+var_88]
0x180059c7e  call    ??1?$Auto@PEAXV?$NgcKeyEnumStateFunctor@PEAX@@VINgcFunctions@@@@QEAA@XZ; Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(void)
0x180059c83  nop
0x180059c84  lea     rcx, [rbp+40h+var_70]
0x180059c88  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180059c8d  mov     eax, ebx
0x180059c8f  mov     rbx, [rsp+140h+arg_8]
0x180059c97  add     rsp, 110h
0x180059c9e  pop     r15
0x180059ca0  pop     r14
0x180059ca2  pop     r13
0x180059ca4  pop     r12
0x180059ca6  pop     rdi
0x180059ca7  pop     rsi
0x180059ca8  pop     rbp
0x180059ca9  retn
0x180059caa  mov     byte ptr [r14], 1
0x180059cae  mov     [rsp+140h+var_F0], 0
0x180059cb6  jmp     short loc_180059CE2
0x180059cb8  test    r9d, r9d
0x180059cbb  jns     short loc_180059C4C
0x180059cbd  lea     rax, aHr; "hr"
0x180059cc4  mov     [rsp+140h+pcbResult], rax; char *
0x180059cc9  mov     r8d, 0F89h; unsigned int
0x180059ccf  lea     rdx, aShouldcreateng; "ShouldCreateNgcKey"
0x180059cd6  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059cdd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180059ce2  mov     eax, cs:dword_1801C2080
0x180059ce8  cmp     eax, ebx
0x180059cea  jbe     loc_180059C4C
0x180059cf0  mov     rdx, 400000000000h
0x180059cfa  lea     rcx, dword_1801C2080
0x180059d01  call    _tlgKeywordOn
0x180059d06  test    al, al
0x180059d08  jz      loc_180059C4C
0x180059d0e  mov     eax, [rsp+140h+var_F0]
0x180059d12  mov     [rsp+140h+var_E0], eax
0x180059d16  mov     eax, dword ptr [rsp+140h+pbOutput]
0x180059d1a  mov     [rsp+140h+var_DC], eax
0x180059d1e  mov     [rsp+140h+var_D8], edi
0x180059d22  mov     byte ptr [rbp+40h+arg_20], r15b
0x180059d26  mov     al, [r14]
0x180059d29  mov     [rbp+40h+arg_0], al
0x180059d2c  lea     rax, [rsp+140h+var_E0]
0x180059d31  mov     [rsp+140h+var_100], rax
0x180059d36  lea     rax, [rsp+140h+var_DC]
0x180059d3b  mov     [rsp+140h+var_108], rax
0x180059d40  lea     rax, [rsp+140h+var_D8]
0x180059d45  mov     [rsp+140h+var_110], rax
0x180059d4a  lea     rax, [rbp+40h+arg_20]
0x180059d4e  mov     qword ptr [rsp+140h+dwFlags], rax
0x180059d53  lea     rax, [rbp+40h+arg_0]
0x180059d57  mov     [rsp+140h+pcbResult], rax
0x180059d5c  lea     rdx, byte_180198479
0x180059d63  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059d68  jmp     loc_180059C4C
0x180059d6d  lea     rax, aHr; "hr"
0x180059d74  mov     [rsp+140h+pcbResult], rax; char *
0x180059d79  mov     r8d, 0F46h; unsigned int
0x180059d7f  lea     rdx, aShouldcreateng; "ShouldCreateNgcKey"
0x180059d86  mov     rcx, r15; char *
0x180059d89  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180059d8e  nop
0x180059d8f  lea     rcx, [rsp+140h+var_D0]
0x180059d94  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180059d99  jmp     loc_180059C4E
0x180059d9e  mov     [rsp+140h+pcbResult], r12
0x180059da3  lea     r9, aNoUsableNgcCon; "No usable NGC containers found for SID "...
0x180059daa  mov     r8d, 0F3Bh; unsigned int
0x180059db0  mov     rdx, r15; char *
0x180059db3  mov     ebx, 5
0x180059db8  mov     ecx, ebx; unsigned __int8
0x180059dba  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059dbf  mov     rax, [rsp+140h+var_D0]
0x180059dc4  test    rax, rax
0x180059dc7  jz      short loc_180059DE7
0x180059dc9  mov     eax, [rax+10h]
0x180059dcc  mov     dword ptr [rsp+140h+pcbResult], eax
0x180059dd0  lea     r9, aContainerstatu; "ContainerStatus = %d"
0x180059dd7  mov     r8d, 0F3Eh; unsigned int
0x180059ddd  mov     rdx, r15; char *
0x180059de0  mov     ecx, ebx; unsigned __int8
0x180059de2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059de7  mov     [rsp+140h+var_F0], edi
0x180059deb  jmp     short loc_180059D8F
```
