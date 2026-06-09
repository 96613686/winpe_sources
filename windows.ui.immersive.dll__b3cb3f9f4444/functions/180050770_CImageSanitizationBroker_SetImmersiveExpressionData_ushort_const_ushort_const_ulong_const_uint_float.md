# CImageSanitizationBroker::SetImmersiveExpressionData(ushort const *,ushort const *,ulong const *,uint,float)

- ea: `0x180050770`
- end: `0x180050a8a`
- name: `?SetImmersiveExpressionData@CImageSanitizationBroker@@UEAAJPEBG0PEBKIM@Z`
- size: `794`
- prototype: `__int64 __fastcall(CImageSanitizationBroker *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned int *, unsigned int, float)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000da00`
- `0x18003039c`
- `0x180040b78`
- `0x180040e20`
- `0x180040ef0`
- `0x180040fe0`
- `0x180050770`
- `0x180054130`
- `0x18007d1b4`
- `0x18007d2c8`
- `0x18007d39c`
- `0x18007d740`
- `0x18007f15c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800509df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800509f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800509df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800509f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005089c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050907`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005089c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050907`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005096f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005096f`

## pseudocode

```c
__int64 __fastcall CImageSanitizationBroker::SetImmersiveExpressionData(
        CImageSanitizationBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned int *a4,
        unsigned int a5,
        float a6)
{
  CImageSanitizationBroker *v9; // rcx
  CImageSanitizationBroker *v10; // rcx
  signed int v11; // ebx
  int v12; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // eax
  LSTATUS v16; // eax
  unsigned int v18[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v21; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v22[42]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v23[20]; // [rsp+1C8h] [rbp+C0h] BYREF

  v21 = a2;
  wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "SetImmersiveExpressionData");
  v22[0] = &ImageSanitizationTelemetry::SetImmersiveExpressionData::`vftable';
  ImageSanitizationTelemetry::SetImmersiveExpressionData::StartActivity((ImageSanitizationTelemetry::SetImmersiveExpressionData *)v22);
  v18[0] = CImageSanitizationBroker::_ValidateExpressionId(v9, a2, 0);
  v11 = v18[0];
  if ( (v18[0] & 0x80000000) != 0 )
  {
    ImageSanitizationTelemetry::SetImmersiveExpressionData::InvalidExpressionId<long &>(v22, v18);
    v12 = v11;
    goto LABEL_29;
  }
  v18[0] = 0;
  v18[0] = CImageSanitizationBroker::_ValidateExpressionDataXML(v10, a3, v18);
  v11 = v18[0];
  if ( (v18[0] & 0x80000000) != 0 )
  {
    ImageSanitizationTelemetry::SetImmersiveExpressionData::ExpressionDataXMLValidationFailure<long &>(v22, v18);
    v12 = v11;
LABEL_27:
    ImageSanitizationTelemetry::SetImmersiveExpressionData::SetCustomColorsetInRegistryFailure<unsigned short const * &,long &>(
      v22,
      &v21,
      v18);
    goto LABEL_29;
  }
  v11 = -2147024809;
  v18[0] = -2147024809;
  v12 = -2147024809;
  if ( a5 == 210 && a6 >= 0.0 && a6 <= 1.0 )
  {
    hKey = 0;
    v13 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
            0,
            0,
            0,
            0x2001Fu,
            0,
            &hKey,
            0);
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    v18[0] = v11;
    if ( v11 >= 0 )
    {
      phkResult = 0;
      v14 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      v11 = v14;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      v18[0] = v11;
      if ( v11 < 0 )
      {
        v12 = v11;
        goto LABEL_22;
      }
      v15 = SHRegSetString(phkResult, 0, L"ExpressionData", a3);
      v18[0] = v15;
      v11 = v15;
      if ( v15 >= 0 )
      {
        v16 = RegSetKeyValueW(phkResult, 0, L"CustomColorSet_Version4", 3u, a4, 0x348u);
        v11 = v16;
        if ( v16 > 0 )
          v11 = (unsigned __int16)v16 | 0x80070000;
        v18[0] = v11;
        if ( v11 < 0 )
        {
          v12 = v11;
          goto LABEL_19;
        }
        v15 = StringCchPrintfW(v23, 0x14u, L"%.4f", a6);
        v18[0] = v15;
        v11 = v15;
        if ( v15 >= 0 )
        {
          v15 = SHRegSetString(phkResult, 0, L"TopRatio", v23);
          v11 = v15;
          v18[0] = v15;
        }
      }
      v12 = v15;
LABEL_19:
      RegCloseKey(phkResult);
LABEL_22:
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v12 = v11;
  }
LABEL_24:
  if ( v12 < 0 )
    goto LABEL_27;
LABEL_29:
  wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v22, (unsigned int)v11);
  ImageSanitizationTelemetry::SetImmersiveExpressionData::~SetImmersiveExpressionData((ImageSanitizationTelemetry::SetImmersiveExpressionData *)v22);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180050770  mov     rax, rsp
0x180050773  mov     [rax+8], rbx
0x180050777  push    rbp
0x180050778  push    rsi
0x180050779  push    rdi
0x18005077a  push    r14
0x18005077c  push    r15
0x18005077e  lea     rbp, [rax-128h]
0x180050785  sub     rsp, 200h
0x18005078c  movaps  xmmword ptr [rax-38h], xmm6
0x180050790  mov     rax, cs:__security_cookie
0x180050797  xor     rax, rsp
0x18005079a  mov     [rbp+120h+var_38], rax
0x1800507a1  mov     r14, rdx
0x1800507a4  mov     [rsp+220h+var_1B8], rdx
0x1800507a9  lea     rdx, aSetimmersiveex; "SetImmersiveExpressionData"
0x1800507b0  mov     r15, r9
0x1800507b3  lea     rcx, [rsp+220h+var_1B0]
0x1800507b8  mov     rsi, r8
0x1800507bb  call    ??0?$ActivityBase@VImageSanitizationLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800507c0  lea     rax, ??_7SetImmersiveExpressionData@ImageSanitizationTelemetry@@6B@; const ImageSanitizationTelemetry::SetImmersiveExpressionData::`vftable'
0x1800507c7  lea     rcx, [rsp+220h+var_1B0]; this
0x1800507cc  mov     [rsp+220h+var_1B0], rax
0x1800507d1  call    ?StartActivity@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXXZ; ImageSanitizationTelemetry::SetImmersiveExpressionData::StartActivity(void)
0x1800507d6  xor     r8d, r8d; unsigned int *
0x1800507d9  mov     rdx, r14; unsigned __int16 *
0x1800507dc  call    ?_ValidateExpressionId@CImageSanitizationBroker@@AEAAJPEBGPEAI@Z; CImageSanitizationBroker::_ValidateExpressionId(ushort const *,uint *)
0x1800507e1  mov     [rsp+220h+var_1D0], eax
0x1800507e5  mov     ebx, eax
0x1800507e7  test    eax, eax
0x1800507e9  js      loc_180050A35
0x1800507ef  lea     r8, [rsp+220h+var_1D0]; unsigned int *
0x1800507f4  mov     [rsp+220h+var_1D0], 0
0x1800507fc  mov     rdx, rsi; unsigned __int16 *
0x1800507ff  call    ?_ValidateExpressionDataXML@CImageSanitizationBroker@@AEAAJPEBGPEAI@Z; CImageSanitizationBroker::_ValidateExpressionDataXML(ushort const *,uint *)
0x180050804  mov     [rsp+220h+var_1D0], eax
0x180050808  mov     ebx, eax
0x18005080a  test    eax, eax
0x18005080c  js      loc_180050A0E
0x180050812  cmp     [rbp+120h+arg_20], 0D2h
0x18005081c  mov     ebx, 80070057h
0x180050821  mov     [rsp+220h+var_1D0], ebx
0x180050825  mov     edi, ebx
0x180050827  jnz     loc_180050A08
0x18005082d  movss   xmm6, [rbp+120h+arg_28]
0x180050835  comiss  xmm6, cs:__real@00000000
0x18005083c  jb      loc_180050A08
0x180050842  movss   xmm0, cs:__real@3f800000
0x18005084a  comiss  xmm0, xmm6
0x18005084d  jb      loc_180050A08
0x180050853  mov     [rsp+220h+lpdwDisposition], 0; lpdwDisposition
0x18005085c  lea     rax, [rsp+220h+hKey]
0x180050861  mov     [rsp+220h+phkResult], rax; phkResult
0x180050866  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005086d  mov     [rsp+220h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180050876  xor     r9d, r9d; lpClass
0x180050879  mov     [rsp+220h+samDesired], 2001Fh; samDesired
0x180050881  xor     r8d, r8d; Reserved
0x180050884  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005088b  mov     [rsp+220h+dwOptions], 0; dwOptions
0x180050893  mov     [rsp+220h+hKey], 0
0x18005089c  call    cs:__imp_RegCreateKeyExW
0x1800508a3  nop     dword ptr [rax+rax+00h]
0x1800508a8  mov     ebx, eax
0x1800508aa  mov     edi, 80070000h
0x1800508af  test    eax, eax
0x1800508b1  jle     short loc_1800508B8
0x1800508b3  movzx   ebx, ax
0x1800508b6  or      ebx, edi
0x1800508b8  mov     [rsp+220h+var_1D0], ebx
0x1800508bc  test    ebx, ebx
0x1800508be  js      loc_180050A06
0x1800508c4  mov     rcx, [rsp+220h+hKey]; hKey
0x1800508c9  lea     rax, [rsp+220h+var_1C8]
0x1800508ce  mov     [rsp+220h+lpdwDisposition], 0; lpdwDisposition
0x1800508d7  xor     r9d, r9d; lpClass
0x1800508da  mov     [rsp+220h+phkResult], rax; phkResult
0x1800508df  xor     r8d, r8d; Reserved
0x1800508e2  mov     [rsp+220h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800508eb  mov     rdx, r14; lpSubKey
0x1800508ee  mov     [rsp+220h+samDesired], 2001Fh; samDesired
0x1800508f6  mov     [rsp+220h+dwOptions], 0; dwOptions
0x1800508fe  mov     [rsp+220h+var_1C8], 0
0x180050907  call    cs:__imp_RegCreateKeyExW
0x18005090e  nop     dword ptr [rax+rax+00h]
0x180050913  mov     ebx, eax
0x180050915  test    eax, eax
0x180050917  jle     short loc_18005091E
0x180050919  movzx   ebx, ax
0x18005091c  or      ebx, edi
0x18005091e  mov     [rsp+220h+var_1D0], ebx
0x180050922  test    ebx, ebx
0x180050924  js      loc_1800509F1
0x18005092a  mov     rcx, [rsp+220h+var_1C8]; HKEY
0x18005092f  lea     r8, aExpressiondata; "ExpressionData"
0x180050936  mov     r9, rsi; unsigned __int16 *
0x180050939  xor     edx, edx; unsigned __int16 *
0x18005093b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180050940  mov     [rsp+220h+var_1D0], eax
0x180050944  mov     ebx, eax
0x180050946  test    eax, eax
0x180050948  js      loc_1800509D8
0x18005094e  mov     rcx, [rsp+220h+var_1C8]; hKey
0x180050953  lea     r8, aCustomcolorset; "CustomColorSet_Version4"
0x18005095a  mov     [rsp+220h+samDesired], 348h; cbData
0x180050962  mov     r9d, 3; dwType
0x180050968  xor     edx, edx; lpSubKey
0x18005096a  mov     qword ptr [rsp+220h+dwOptions], r15; lpData
0x18005096f  call    cs:__imp_RegSetKeyValueW
0x180050976  nop     dword ptr [rax+rax+00h]
0x18005097b  mov     ebx, eax
0x18005097d  test    eax, eax
0x18005097f  jle     short loc_180050986
0x180050981  movzx   ebx, ax
0x180050984  or      ebx, edi
0x180050986  mov     [rsp+220h+var_1D0], ebx
0x18005098a  test    ebx, ebx
0x18005098c  js      short loc_1800509ED
0x18005098e  cvtps2pd xmm3, xmm6
0x180050991  lea     r8, a4f; "%.4f"
0x180050998  mov     edx, 14h; unsigned __int64
0x18005099d  lea     rcx, [rbp+120h+var_60]; unsigned __int16 *
0x1800509a4  movq    r9, xmm3
0x1800509a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800509ae  mov     [rsp+220h+var_1D0], eax
0x1800509b2  mov     ebx, eax
0x1800509b4  test    eax, eax
0x1800509b6  js      short loc_1800509D8
0x1800509b8  mov     rcx, [rsp+220h+var_1C8]; HKEY
0x1800509bd  lea     r9, [rbp+120h+var_60]; unsigned __int16 *
0x1800509c4  lea     r8, aTopratio; "TopRatio"
0x1800509cb  xor     edx, edx; unsigned __int16 *
0x1800509cd  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800509d2  mov     ebx, eax
0x1800509d4  mov     [rsp+220h+var_1D0], eax
0x1800509d8  mov     edi, eax
0x1800509da  mov     rcx, [rsp+220h+var_1C8]; hKey
0x1800509df  call    cs:__imp_RegCloseKey
0x1800509e6  nop     dword ptr [rax+rax+00h]
0x1800509eb  jmp     short loc_1800509F3
0x1800509ed  mov     edi, ebx
0x1800509ef  jmp     short loc_1800509DA
0x1800509f1  mov     edi, ebx
0x1800509f3  mov     rcx, [rsp+220h+hKey]; hKey
0x1800509f8  call    cs:__imp_RegCloseKey
0x1800509ff  nop     dword ptr [rax+rax+00h]
0x180050a04  jmp     short loc_180050A08
0x180050a06  mov     edi, ebx
0x180050a08  test    edi, edi
0x180050a0a  jns     short loc_180050A46
0x180050a0c  jmp     short loc_180050A1F
0x180050a0e  lea     rdx, [rsp+220h+var_1D0]
0x180050a13  lea     rcx, [rsp+220h+var_1B0]
0x180050a18  call    ??$ExpressionDataXMLValidationFailure@AEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::ExpressionDataXMLValidationFailure<long &>(long &)
0x180050a1d  mov     edi, ebx
0x180050a1f  lea     r8, [rsp+220h+var_1D0]
0x180050a24  lea     rdx, [rsp+220h+var_1B8]
0x180050a29  lea     rcx, [rsp+220h+var_1B0]
0x180050a2e  call    ??$SetCustomColorsetInRegistryFailure@AEAPEBGAEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAPEBGAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::SetCustomColorsetInRegistryFailure<ushort const * &,long &>(ushort const * &,long &)
0x180050a33  jmp     short loc_180050A46
0x180050a35  lea     rdx, [rsp+220h+var_1D0]
0x180050a3a  lea     rcx, [rsp+220h+var_1B0]
0x180050a3f  call    ??$InvalidExpressionId@AEAJ@SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAAXAEAJ@Z; ImageSanitizationTelemetry::SetImmersiveExpressionData::InvalidExpressionId<long &>(long &)
0x180050a44  mov     edi, ebx
0x180050a46  mov     edx, ebx
0x180050a48  lea     rcx, [rsp+220h+var_1B0]
0x180050a4d  call    ?Stop@?$ActivityBase@VImageSanitizationLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ImageSanitizationLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180050a52  lea     rcx, [rsp+220h+var_1B0]; this
0x180050a57  call    ??1SetImmersiveExpressionData@ImageSanitizationTelemetry@@QEAA@XZ; ImageSanitizationTelemetry::SetImmersiveExpressionData::~SetImmersiveExpressionData(void)
0x180050a5c  mov     eax, edi
0x180050a5e  mov     rcx, [rbp+120h+var_38]
0x180050a65  xor     rcx, rsp; StackCookie
0x180050a68  call    __security_check_cookie
0x180050a6d  lea     r11, [rsp+220h+var_20]
0x180050a75  mov     rbx, [r11+30h]
0x180050a79  movaps  xmm6, xmmword ptr [r11-10h]
0x180050a7e  mov     rsp, r11
0x180050a81  pop     r15
0x180050a83  pop     r14
0x180050a85  pop     rdi
0x180050a86  pop     rsi
0x180050a87  pop     rbp
0x180050a88  retn
```
