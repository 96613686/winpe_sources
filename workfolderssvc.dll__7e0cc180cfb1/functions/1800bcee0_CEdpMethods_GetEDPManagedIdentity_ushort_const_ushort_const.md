# CEdpMethods::GetEDPManagedIdentity(ushort const *,ushort const * *)

- ea: `0x1800bcee0`
- end: `0x1800bd17b`
- name: `?GetEDPManagedIdentity@CEdpMethods@@UEAAJPEBGPEAPEBG@Z`
- size: `667`
- prototype: `int(CEdpMethods *__hidden this, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007e10`
- `0x180011314`
- `0x18001137c`
- `0x180059d50`
- `0x1800bbe18`
- `0x1800bc26c`
- `0x1800bc4c4`
- `0x1800bc894`
- `0x1800bcee0`
- `0x1800bd244`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bd142`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bd142`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bcf96`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bcf96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bd0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bd0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd135`

## pseudocode

```c
__int64 __fastcall CEdpMethods::GetEDPManagedIdentity(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  int v8; // ebx
  __int16 v9; // ax
  CEdpMethods *v10; // rcx
  HSTRING v11; // rcx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, struct Windows::Networking::IHostName *, __int64 *); // rdi
  __int64 v14; // rdi
  int v15; // eax
  bool v16; // sf
  _QWORD *v17; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v19; // edi
  __int64 v21; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+28h] [rbp-40h] BYREF
  struct Windows::Networking::IHostName *v23; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  int v25; // [rsp+40h] [rbp-28h] BYREF
  int v26; // [rsp+44h] [rbp-24h]
  char v27; // [rsp+48h] [rbp-20h]
  const char *v28; // [rsp+50h] [rbp-18h]
  __int64 v29; // [rsp+58h] [rbp-10h]
  UINT32 length; // [rsp+B8h] [rbp+50h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
    {
LABEL_8:
      v7 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 0x20) == 0 || v6[65] < 6u )
    goto LABEL_8;
  v7 = 1;
LABEL_9:
  v27 = v7;
  v28 = "CEdpMethods::GetEDPManagedIdentity";
  v26 = 214;
  v29 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  string = 0;
  length = 0;
  v8 = RoInitialize(1);
  v25 = v8;
  v9 = 227;
  if ( v8 < 0 )
    goto LABEL_27;
  LOWORD(v26) = 227;
  v9 = 230;
  if ( !a3 || (LOWORD(v26) = 230, v9 = 231, *a3 = 0, !a2) )
  {
    v25 = -2147024809;
    goto LABEL_27;
  }
  v25 = 0;
  LOWORD(v26) = 231;
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v23);
  v25 = CEdpMethods::CreateHostName(v10, a2, &v23);
  v9 = 233;
  if ( v25 < 0 )
    goto LABEL_27;
  LOWORD(v26) = 233;
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  v25 = GetActivationFactory<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>(v11, &v22);
  v9 = 236;
  if ( v25 < 0 )
    goto LABEL_27;
  v12 = v22;
  LOWORD(v26) = 236;
  v13 = *(__int64 (__fastcall **)(__int64, struct Windows::Networking::IHostName *, __int64 *))(*(_QWORD *)v22 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v21);
  v25 = v13(v12, v23, &v21);
  v9 = 239;
  if ( v25 < 0 )
    goto LABEL_27;
  v14 = v21;
  LOWORD(v26) = 239;
  v15 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v21);
  if ( v15 >= 0 )
    v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 64LL))(v14, &string);
  v25 = v15;
  v16 = v15 < 0;
  v9 = 240;
  if ( v16 )
    goto LABEL_27;
  v17 = this + 1;
  LOWORD(v26) = 240;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(this + 1);
  if ( !string )
    goto LABEL_21;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v25 = CSyncCoreStringUtils::StringCopyAlloc(StringRawBuffer, this + 1);
  v9 = 248;
  if ( v25 < 0 )
  {
LABEL_27:
    HIWORD(v26) = v9;
    goto LABEL_28;
  }
  LOWORD(v26) = 248;
LABEL_21:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids, *v17);
  }
  *a3 = (const unsigned __int16 *)*v17;
LABEL_28:
  WindowsDeleteString(string);
  WindowsDeleteString(0);
  v19 = v25;
  if ( v8 >= 0 )
    RoUninitialize();
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v23);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v25);
  return v19;
}

```

## disassembly

```asm
0x1800bcee0  push    rbp
0x1800bcee2  push    rbx
0x1800bcee3  push    rsi
0x1800bcee4  push    rdi
0x1800bcee5  push    r14
0x1800bcee7  push    r15
0x1800bcee9  mov     rbp, rsp
0x1800bceec  sub     rsp, 68h
0x1800bcef0  mov     r14, r8
0x1800bcef3  mov     rdi, rdx
0x1800bcef6  mov     r15, rcx
0x1800bcef9  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcf00  lea     rcx, WPP_GLOBAL_Control
0x1800bcf07  cmp     rax, rcx
0x1800bcf0a  jz      short loc_1800BCF34
0x1800bcf0c  test    byte ptr [rax+44h], 20h
0x1800bcf10  jz      short loc_1800BCF44
0x1800bcf12  cmp     byte ptr [rax+41h], 6
0x1800bcf16  jb      short loc_1800BCF34
0x1800bcf18  mov     rcx, [rax+38h]
0x1800bcf1c  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bcf23  mov     edx, 0Eh
0x1800bcf28  call    WPP_SF_
0x1800bcf2d  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcf34  test    byte ptr [rax+44h], 20h
0x1800bcf38  jz      short loc_1800BCF44
0x1800bcf3a  cmp     byte ptr [rax+41h], 6
0x1800bcf3e  jb      short loc_1800BCF44
0x1800bcf40  mov     cl, 1
0x1800bcf42  jmp     short loc_1800BCF46
0x1800bcf44  xor     cl, cl
0x1800bcf46  mov     [rbp+var_20], cl
0x1800bcf49  lea     rax, aCedpmethodsGet_0; "CEdpMethods::GetEDPManagedIdentity"
0x1800bcf50  mov     ecx, 1
0x1800bcf55  mov     [rbp+var_18], rax
0x1800bcf59  mov     [rbp+var_28], 0
0x1800bcf60  mov     [rbp+var_24], 0D6h
0x1800bcf67  mov     [rbp+var_10], 0
0x1800bcf6f  mov     [rbp+var_38], 0
0x1800bcf77  mov     [rbp+var_40], 0
0x1800bcf7f  mov     [rbp+var_48], 0
0x1800bcf87  mov     [rbp+string], 0
0x1800bcf8f  mov     [rbp+length], 0
0x1800bcf96  call    cs:__imp_RoInitialize
0x1800bcf9c  mov     ebx, eax
0x1800bcf9e  mov     [rbp+var_28], eax
0x1800bcfa1  test    eax, eax
0x1800bcfa3  mov     eax, 0E3h
0x1800bcfa8  js      loc_1800BD125
0x1800bcfae  mov     word ptr [rbp+var_24], ax
0x1800bcfb2  mov     eax, 0E6h
0x1800bcfb7  test    r14, r14
0x1800bcfba  jz      loc_1800BD11E
0x1800bcfc0  mov     word ptr [rbp+var_24], ax
0x1800bcfc4  mov     eax, 0E7h
0x1800bcfc9  mov     qword ptr [r14], 0
0x1800bcfd0  test    rdi, rdi
0x1800bcfd3  jz      loc_1800BD11E
0x1800bcfd9  lea     rcx, [rbp+var_38]
0x1800bcfdd  mov     [rbp+var_28], 0
0x1800bcfe4  mov     word ptr [rbp+var_24], ax
0x1800bcfe8  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bcfed  lea     r8, [rbp+var_38]; struct Windows::Networking::IHostName **
0x1800bcff1  mov     rdx, rdi; unsigned __int16 *
0x1800bcff4  call    ?CreateHostName@CEdpMethods@@AEAAJPEBGPEAPEAUIHostName@Networking@Windows@@@Z; CEdpMethods::CreateHostName(ushort const *,Windows::Networking::IHostName * *)
0x1800bcff9  mov     [rbp+var_28], eax
0x1800bcffc  test    eax, eax
0x1800bcffe  mov     eax, 0E9h
0x1800bd003  js      loc_1800BD125
0x1800bd009  lea     rcx, [rbp+var_40]
0x1800bd00d  mov     word ptr [rbp+var_24], ax
0x1800bd011  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bd016  lea     rdx, [rbp+var_40]
0x1800bd01a  call    ??$GetActivationFactory@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@@YAJPEBGPEAPEAUIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@Z; GetActivationFactory<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>(ushort const *,Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics * *)
0x1800bd01f  mov     [rbp+var_28], eax
0x1800bd022  test    eax, eax
0x1800bd024  mov     eax, 0ECh
0x1800bd029  js      loc_1800BD125
0x1800bd02f  mov     rsi, [rbp+var_40]
0x1800bd033  lea     rcx, [rbp+var_48]
0x1800bd037  mov     word ptr [rbp+var_24], ax
0x1800bd03b  mov     rax, [rsi]
0x1800bd03e  mov     rdi, [rax+50h]
0x1800bd042  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bd047  mov     rdx, [rbp+var_38]
0x1800bd04b  lea     r8, [rbp+var_48]
0x1800bd04f  mov     rcx, rsi
0x1800bd052  mov     rax, rdi
0x1800bd055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd05a  mov     [rbp+var_28], eax
0x1800bd05d  test    eax, eax
0x1800bd05f  mov     eax, 0EFh
0x1800bd064  js      loc_1800BD125
0x1800bd06a  mov     rdi, [rbp+var_48]
0x1800bd06e  mov     rcx, rdi
0x1800bd071  mov     word ptr [rbp+var_24], ax
0x1800bd075  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x1800bd07a  test    eax, eax
0x1800bd07c  js      short loc_1800BD091
0x1800bd07e  mov     rax, [rdi]
0x1800bd081  lea     rdx, [rbp+string]
0x1800bd085  mov     rcx, rdi
0x1800bd088  mov     rax, [rax+40h]
0x1800bd08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd091  mov     [rbp+var_28], eax
0x1800bd094  test    eax, eax
0x1800bd096  mov     eax, 0F0h
0x1800bd09b  js      loc_1800BD125
0x1800bd0a1  lea     rdi, [r15+8]
0x1800bd0a5  mov     word ptr [rbp+var_24], ax
0x1800bd0a9  mov     rcx, rdi
0x1800bd0ac  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x1800bd0b1  mov     rcx, [rbp+string]; string
0x1800bd0b5  test    rcx, rcx
0x1800bd0b8  jz      short loc_1800BD0DF
0x1800bd0ba  lea     rdx, [rbp+length]; length
0x1800bd0be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bd0c4  mov     rcx, rax; unsigned __int16 *
0x1800bd0c7  mov     rdx, rdi; unsigned __int16 **
0x1800bd0ca  call    ?StringCopyAlloc@CSyncCoreStringUtils@@SAJPEBGPEAPEAG@Z; CSyncCoreStringUtils::StringCopyAlloc(ushort const *,ushort * *)
0x1800bd0cf  mov     [rbp+var_28], eax
0x1800bd0d2  test    eax, eax
0x1800bd0d4  mov     eax, 0F8h
0x1800bd0d9  js      short loc_1800BD125
0x1800bd0db  mov     word ptr [rbp+var_24], ax
0x1800bd0df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd0e6  lea     rax, WPP_GLOBAL_Control
0x1800bd0ed  cmp     rcx, rax
0x1800bd0f0  jz      short loc_1800BD116
0x1800bd0f2  test    byte ptr [rcx+44h], 20h
0x1800bd0f6  jz      short loc_1800BD116
0x1800bd0f8  cmp     byte ptr [rcx+41h], 4
0x1800bd0fc  jb      short loc_1800BD116
0x1800bd0fe  mov     r9, [rdi]
0x1800bd101  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bd108  mov     rcx, [rcx+38h]
0x1800bd10c  mov     edx, 0Fh
0x1800bd111  call    WPP_SF_S
0x1800bd116  mov     rax, [rdi]
0x1800bd119  mov     [r14], rax
0x1800bd11c  jmp     short loc_1800BD129
0x1800bd11e  mov     [rbp+var_28], 80070057h
0x1800bd125  mov     word ptr [rbp+var_24+2], ax
0x1800bd129  mov     rcx, [rbp+string]; string
0x1800bd12d  call    cs:__imp_WindowsDeleteString
0x1800bd133  xor     ecx, ecx; string
0x1800bd135  call    cs:__imp_WindowsDeleteString
0x1800bd13b  mov     edi, [rbp+var_28]
0x1800bd13e  test    ebx, ebx
0x1800bd140  js      short loc_1800BD148
0x1800bd142  call    cs:__imp_RoUninitialize
0x1800bd148  lea     rcx, [rbp+var_48]
0x1800bd14c  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bd151  lea     rcx, [rbp+var_40]
0x1800bd155  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bd15a  lea     rcx, [rbp+var_38]
0x1800bd15e  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bd163  lea     rcx, [rbp+var_28]; this
0x1800bd167  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bd16c  mov     eax, edi
0x1800bd16e  add     rsp, 68h
0x1800bd172  pop     r15
0x1800bd174  pop     r14
0x1800bd176  pop     rdi
0x1800bd177  pop     rsi
0x1800bd178  pop     rbx
0x1800bd179  pop     rbp
0x1800bd17a  retn
```
