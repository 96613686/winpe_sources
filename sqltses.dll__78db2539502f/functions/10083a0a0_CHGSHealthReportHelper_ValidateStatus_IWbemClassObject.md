# CHGSHealthReportHelper::ValidateStatus(IWbemClassObject *)

- ea: `0x10083a0a0`
- end: `0x10083a4d4`
- name: `?ValidateStatus@CHGSHealthReportHelper@@CAJPEAUIWbemClassObject@@@Z`
- size: `1076`
- prototype: `__int64 __fastcall(struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100839db0`

## callees

- `0x100836e60`
- `0x10083a0a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x10083a0c7`
- `OLEAUT32!__imp_SysAllocString` at `0x10083a1e8`
- `OLEAUT32!__imp_SysAllocString` at `0x10083a0c7`
- `OLEAUT32!__imp_SysAllocString` at `0x10083a1e8`
- `OLEAUT32!__imp_SysFreeString` at `0x10083a182`
- `OLEAUT32!__imp_SysFreeString` at `0x10083a29d`
- `OLEAUT32!__imp_SysFreeString` at `0x10083a182`
- `OLEAUT32!__imp_SysFreeString` at `0x10083a29d`
- `OLEAUT32!__imp_VariantInit` at `0x10083a0f5`
- `OLEAUT32!__imp_VariantInit` at `0x10083a216`
- `OLEAUT32!__imp_VariantInit` at `0x10083a0f5`
- `OLEAUT32!__imp_VariantInit` at `0x10083a216`
- `OLEAUT32!__imp_VariantClear` at `0x10083a169`
- `OLEAUT32!__imp_VariantClear` at `0x10083a1d9`
- `OLEAUT32!__imp_VariantClear` at `0x10083a284`
- `OLEAUT32!__imp_VariantClear` at `0x10083a2e5`
- `OLEAUT32!__imp_VariantClear` at `0x10083a169`
- `OLEAUT32!__imp_VariantClear` at `0x10083a1d9`
- `OLEAUT32!__imp_VariantClear` at `0x10083a284`
- `OLEAUT32!__imp_VariantClear` at `0x10083a2e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a15d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a1b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a278`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a467`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a15d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a1b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a278`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10083a467`
- `api-ms-win-crt-convert-l1-1-0!_wcstoui64` at `0x10083a2d7`
- `api-ms-win-crt-convert-l1-1-0!_wcstoui64` at `0x10083a2d7`

## string_xrefs

- `0x10083a41c`: `NotConfigured`
- `0x10083a43b`: `InsecureHostConfiguration`
- `0x10083a36b`: `ServiceUnavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHGSHealthReportHelper::ValidateStatus(struct IWbemClassObject *a1)
{
  OLECHAR *v2; // rbx
  int v3; // edi
  unsigned __int16 uiVal; // bp
  OLECHAR *v6; // rbx
  unsigned __int64 v7; // rsi
  const wchar_t *v8; // r8
  const wchar_t *v9; // rcx
  __int64 v10; // [rsp+28h] [rbp-70h]
  __int64 v11; // [rsp+28h] [rbp-70h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-60h] BYREF
  VARIANTARG v13; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int16 v14; // [rsp+A8h] [rbp+10h]
  BSTR v15; // [rsp+A8h] [rbp+10h]

  v2 = SysAllocString(L"AttestationStatus");
  if ( !v2 )
    goto LABEL_57;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD, __int64))a1->lpVtbl->Get)(
         a1,
         v2,
         0,
         &pvarg,
         0,
         0,
         -2);
  if ( v3 < 0 )
    goto LABEL_5;
  if ( pvarg.vt != 3 )
  {
    v3 = -2147467259;
LABEL_5:
    _mm_lfence();
    LODWORD(v10) = v3;
    ex_raise(373, 14, 16, 24, L"WmiGetVariantFromInstance", v10);
    VariantClear(&pvarg);
    uiVal = v14;
    goto LABEL_6;
  }
  uiVal = pvarg.uiVal;
  VariantClear(&pvarg);
LABEL_6:
  SysFreeString(v2);
  if ( v3 < 0 )
  {
    _mm_lfence();
    LODWORD(v10) = v3;
    ex_raise(373, 14, 16, 21, L"WmiGetUShortFromInstance", v10);
    return (unsigned int)v3;
  }
  v15 = SysAllocString(L"AttestationSubstatus");
  if ( !v15 )
LABEL_57:
    ATL::AtlThrowImpl(-2147024882);
  _mm_lfence();
  memset(&v13, 0, sizeof(v13));
  VariantInit(&v13);
  v6 = v15;
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         v15,
         0,
         &v13,
         0,
         0);
  if ( v3 < 0 )
  {
LABEL_14:
    _mm_lfence();
    LODWORD(v11) = v3;
    ex_raise(373, 14, 16, 25, L"WmiGetVariantFromInstance", v11);
    VariantClear(&v13);
    v7 = (unsigned __int64)v15;
    v6 = v15;
    goto LABEL_15;
  }
  if ( v13.vt != 8 )
  {
    v3 = -2147467259;
    goto LABEL_14;
  }
  v7 = _wcstoui64(v13.bstrVal, 0, 0);
  VariantClear(&v13);
LABEL_15:
  SysFreeString(v6);
  if ( v3 < 0 )
  {
    _mm_lfence();
    LODWORD(v11) = v3;
    ex_raise(373, 14, 16, 22, L"WmiGetULonglongFromInstance", v11);
    return (unsigned int)v3;
  }
  if ( uiVal == 100 && !v7 )
    return 0;
  v8 = L"Unknown";
  switch ( v7 )
  {
    case 0uLL:
      v9 = L"NoInformation";
      break;
    case 1uLL:
      v9 = L"SecureBoot";
      break;
    case 2uLL:
      v9 = L"DebugMode";
      break;
    case 3uLL:
      v9 = L"CodeIntegrityPolicy";
      break;
    case 4uLL:
      v9 = L"FullBoot";
      break;
    case 5uLL:
      v9 = L"HostUnreachable";
      break;
    case 6uLL:
      v9 = L"ServiceUnavailable";
      break;
    case 7uLL:
      v9 = L"AuthenticationFailure";
      break;
    case 8uLL:
      v9 = L"TcgLogVerification";
      break;
    case 9uLL:
      v9 = L"VirtualSecureMode";
      break;
    case 0xAuLL:
      v9 = L"SecureBootSettings";
      break;
    case 0xBuLL:
      v9 = L"BitLocker";
      break;
    case 0xCuLL:
      v9 = L"Iommu";
      break;
    case 0xDuLL:
      v9 = L"PagefileEncryption";
      break;
    case 0xEuLL:
      v9 = L"HypervisorEnforcedCodeIntegrityPolicy";
      break;
    case 0xFuLL:
      v9 = L"UnsupportedHardware";
      break;
    case 0x10uLL:
      v9 = L"HibernationEnabled";
      break;
    case 0x11uLL:
      v9 = L"DumpsEnabled";
      break;
    case 0x12uLL:
      v9 = L"DumpEncryption";
      break;
    case 0x13uLL:
      v9 = L"DumpEncryptionKey";
      break;
    default:
      v9 = L"Unknown";
      break;
  }
  if ( uiVal > 0x12Du )
  {
    if ( uiVal == 302 )
    {
      v8 = L"TpmError";
    }
    else if ( uiVal == 303 )
    {
      v8 = L"InsecureHostConfiguration";
    }
  }
  else if ( uiVal == 301 )
  {
    v8 = L"UnauthorizedHost";
  }
  else if ( uiVal )
  {
    if ( uiVal == 100 )
    {
      v8 = L"Passed";
    }
    else if ( uiVal == 300 )
    {
      v8 = L"TransientError";
    }
  }
  else
  {
    v8 = L"NotConfigured";
  }
  ex_raise(335, 36, 16, 1, v8, v9);
  return 2147500037LL;
}

```

## disassembly

```asm
0x10083a0a0  push    rbp
0x10083a0a2  push    rsi
0x10083a0a3  push    rdi
0x10083a0a4  push    r14
0x10083a0a6  push    r15
0x10083a0a8  sub     rsp, 70h
0x10083a0ac  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x10083a0b5  mov     [rsp+98h+arg_0], rbx
0x10083a0bd  mov     rsi, rcx
0x10083a0c0  lea     rcx, aAttestationsta; "AttestationStatus"
0x10083a0c7  call    cs:__imp_SysAllocString
0x10083a0cd  mov     rbx, rax
0x10083a0d0  mov     [rsp+98h+bstrString], rax
0x10083a0d8  test    rax, rax
0x10083a0db  jz      loc_10083A477
0x10083a0e1  xorps   xmm0, xmm0
0x10083a0e4  xor     eax, eax
0x10083a0e6  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x10083a0eb  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x10083a0f0  lea     rcx, [rsp+98h+pvarg]; pvarg
0x10083a0f5  call    cs:__imp_VariantInit
0x10083a0fb  nop
0x10083a0fc  mov     rax, [rsi]
0x10083a0ff  xor     r14d, r14d
0x10083a102  mov     [rsp+98h+var_70], r14
0x10083a107  mov     [rsp+98h+var_78], r14
0x10083a10c  lea     r9, [rsp+98h+pvarg]
0x10083a111  xor     r8d, r8d
0x10083a114  mov     rdx, rbx
0x10083a117  mov     rcx, rsi
0x10083a11a  call    qword ptr [rax+20h]
0x10083a11d  mov     edi, eax
0x10083a11f  lea     r15, aWmigetvariantf; "WmiGetVariantFromInstance"
0x10083a126  test    eax, eax
0x10083a128  js      short loc_10083A13F
0x10083a12a  mov     eax, 3
0x10083a12f  cmp     ax, word ptr [rsp+98h+pvarg]
0x10083a134  jz      loc_10083A1CF
0x10083a13a  mov     edi, 80004005h
0x10083a13f  lfence
0x10083a142  mov     dword ptr [rsp+98h+var_70], edi
0x10083a146  mov     [rsp+98h+var_78], r15
0x10083a14b  mov     edx, 0Eh
0x10083a150  mov     ecx, 175h
0x10083a155  lea     r9d, [rdx+0Ah]
0x10083a159  lea     r8d, [rdx+2]
0x10083a15d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10083a163  nop
0x10083a164  lea     rcx, [rsp+98h+pvarg]; pvarg
0x10083a169  call    cs:__imp_VariantClear
0x10083a16f  movzx   ebp, word ptr [rsp+98h+arg_8]
0x10083a177  mov     rbx, [rsp+98h+bstrString]
0x10083a17f  mov     rcx, rbx; bstrString
0x10083a182  call    cs:__imp_SysFreeString
0x10083a188  test    edi, edi
0x10083a18a  jns     short loc_10083A1E1
0x10083a18c  lfence
0x10083a18f  mov     dword ptr [rsp+98h+var_70], edi
0x10083a193  lea     rax, aWmigetushortfr; "WmiGetUShortFromInstance"
0x10083a19a  mov     [rsp+98h+var_78], rax
0x10083a19f  mov     edx, 0Eh
0x10083a1a4  mov     ecx, 175h
0x10083a1a9  lea     r9d, [rdx+7]
0x10083a1ad  mov     r8d, 10h
0x10083a1b3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10083a1b9  mov     eax, edi
0x10083a1bb  mov     rbx, [rsp+98h+arg_0]
0x10083a1c3  add     rsp, 70h
0x10083a1c7  pop     r15
0x10083a1c9  pop     r14
0x10083a1cb  pop     rdi
0x10083a1cc  pop     rsi
0x10083a1cd  pop     rbp
0x10083a1ce  retn
0x10083a1cf  movzx   ebp, word ptr [rsp+98h+pvarg+8]
0x10083a1d4  lea     rcx, [rsp+98h+pvarg]; pvarg
0x10083a1d9  call    cs:__imp_VariantClear
0x10083a1df  jmp     short loc_10083A17F
0x10083a1e1  lea     rcx, aAttestationsub; "AttestationSubstatus"
0x10083a1e8  call    cs:__imp_SysAllocString
0x10083a1ee  mov     [rsp+98h+arg_8], rax
0x10083a1f6  test    rax, rax
0x10083a1f9  jz      loc_10083A477
0x10083a1ff  lfence
0x10083a202  xorps   xmm0, xmm0
0x10083a205  xor     eax, eax
0x10083a207  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x10083a20c  mov     qword ptr [rsp+98h+var_48+10h], rax
0x10083a211  lea     rcx, [rsp+98h+var_48]; pvarg
0x10083a216  call    cs:__imp_VariantInit
0x10083a21c  nop
0x10083a21d  mov     rax, [rsi]
0x10083a220  mov     [rsp+98h+var_70], r14
0x10083a225  mov     [rsp+98h+var_78], r14
0x10083a22a  lea     r9, [rsp+98h+var_48]
0x10083a22f  xor     r8d, r8d
0x10083a232  mov     rbx, [rsp+98h+arg_8]
0x10083a23a  mov     rdx, rbx
0x10083a23d  mov     rcx, rsi
0x10083a240  call    qword ptr [rax+20h]
0x10083a243  mov     edi, eax
0x10083a245  test    eax, eax
0x10083a247  js      short loc_10083A25A
0x10083a249  mov     eax, 8
0x10083a24e  cmp     ax, word ptr [rsp+98h+var_48]
0x10083a253  jz      short loc_10083A2CD
0x10083a255  mov     edi, 80004005h
0x10083a25a  lfence
0x10083a25d  mov     dword ptr [rsp+98h+var_70], edi
0x10083a261  mov     [rsp+98h+var_78], r15
0x10083a266  mov     edx, 0Eh
0x10083a26b  mov     ecx, 175h
0x10083a270  lea     r9d, [rdx+0Bh]
0x10083a274  lea     r8d, [rdx+2]
0x10083a278  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10083a27e  nop
0x10083a27f  lea     rcx, [rsp+98h+var_48]; pvarg
0x10083a284  call    cs:__imp_VariantClear
0x10083a28a  mov     rsi, [rsp+98h+arg_8]
0x10083a292  mov     rbx, [rsp+98h+arg_8]
0x10083a29a  mov     rcx, rbx; bstrString
0x10083a29d  call    cs:__imp_SysFreeString
0x10083a2a3  test    edi, edi
0x10083a2a5  jns     short loc_10083A2ED
0x10083a2a7  lfence
0x10083a2aa  mov     dword ptr [rsp+98h+var_70], edi
0x10083a2ae  lea     rax, aWmigetulonglon; "WmiGetULonglongFromInstance"
0x10083a2b5  mov     [rsp+98h+var_78], rax
0x10083a2ba  mov     edx, 0Eh
0x10083a2bf  mov     ecx, 175h
0x10083a2c4  lea     r9d, [rdx+8]
0x10083a2c8  jmp     loc_10083A1AD
0x10083a2cd  xor     r8d, r8d; Radix
0x10083a2d0  xor     edx, edx; EndPtr
0x10083a2d2  mov     rcx, qword ptr [rsp+98h+var_48+8]; String
0x10083a2d7  call    cs:__imp__wcstoui64
0x10083a2dd  mov     rsi, rax
0x10083a2e0  lea     rcx, [rsp+98h+var_48]; pvarg
0x10083a2e5  call    cs:__imp_VariantClear
0x10083a2eb  jmp     short loc_10083A29A
0x10083a2ed  cmp     bp, 64h ; 'd'
0x10083a2f1  jnz     short loc_10083A2FF
0x10083a2f3  test    rsi, rsi
0x10083a2f6  jnz     short loc_10083A2FF
0x10083a2f8  xor     eax, eax
0x10083a2fa  jmp     loc_10083A1BB
0x10083a2ff  lea     r8, aUnknown_0; "Unknown"
0x10083a306  cmp     rsi, 13h; switch 20 cases
0x10083a30a  ja      def_10083A321; jumptable 000000010083A321 default case
0x10083a310  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10083a317  mov     eax, ds:(jpt_10083A321 - 100400000h)[rcx+rsi*4]
0x10083a31e  add     rax, rcx
0x10083a321  jmp     rax; switch jump
0x10083a323  lea     rcx, aNoinformation; jumptable 000000010083A321 case 0
0x10083a32a  jmp     loc_10083A3EC
0x10083a32f  lea     rcx, aSecureboot; jumptable 000000010083A321 case 1
0x10083a336  jmp     loc_10083A3EC
0x10083a33b  lea     rcx, aDebugmode; jumptable 000000010083A321 case 2
0x10083a342  jmp     loc_10083A3EC
0x10083a347  lea     rcx, aCodeintegrityp; jumptable 000000010083A321 case 3
0x10083a34e  jmp     loc_10083A3EC
0x10083a353  lea     rcx, aFullboot; jumptable 000000010083A321 case 4
0x10083a35a  jmp     loc_10083A3EC
0x10083a35f  lea     rcx, aHostunreachabl; jumptable 000000010083A321 case 5
0x10083a366  jmp     loc_10083A3EC
0x10083a36b  lea     rcx, aServiceunavail; jumptable 000000010083A321 case 6
0x10083a372  jmp     short loc_10083A3EC
0x10083a374  lea     rcx, aAuthentication; jumptable 000000010083A321 case 7
0x10083a37b  jmp     short loc_10083A3EC
0x10083a37d  lea     rcx, aTcglogverifica; jumptable 000000010083A321 case 8
0x10083a384  jmp     short loc_10083A3EC
0x10083a386  lea     rcx, aVirtualsecurem; jumptable 000000010083A321 case 9
0x10083a38d  jmp     short loc_10083A3EC
0x10083a38f  lea     rcx, aSecurebootsett; jumptable 000000010083A321 case 10
0x10083a396  jmp     short loc_10083A3EC
0x10083a398  lea     rcx, aBitlocker; jumptable 000000010083A321 case 11
0x10083a39f  jmp     short loc_10083A3EC
0x10083a3a1  lea     rcx, aIommu; jumptable 000000010083A321 case 12
0x10083a3a8  jmp     short loc_10083A3EC
0x10083a3aa  lea     rcx, aPagefileencryp; jumptable 000000010083A321 case 13
0x10083a3b1  jmp     short loc_10083A3EC
0x10083a3b3  lea     rcx, aHypervisorenfo; jumptable 000000010083A321 case 14
0x10083a3ba  jmp     short loc_10083A3EC
0x10083a3bc  lea     rcx, aUnsupportedhar; jumptable 000000010083A321 case 15
0x10083a3c3  jmp     short loc_10083A3EC
0x10083a3c5  lea     rcx, aHibernationena; jumptable 000000010083A321 case 16
0x10083a3cc  jmp     short loc_10083A3EC
0x10083a3ce  lea     rcx, aDumpsenabled; jumptable 000000010083A321 case 17
0x10083a3d5  jmp     short loc_10083A3EC
0x10083a3d7  lea     rcx, aDumpencryption; jumptable 000000010083A321 case 18
0x10083a3de  jmp     short loc_10083A3EC
0x10083a3e0  lea     rcx, aDumpencryption_0; jumptable 000000010083A321 case 19
0x10083a3e7  jmp     short loc_10083A3EC
0x10083a3e9  mov     rcx, r8; jumptable 000000010083A321 default case
0x10083a3ec  movzx   edx, bp
0x10083a3ef  cmp     edx, 12Dh
0x10083a3f5  ja      short loc_10083A42E
0x10083a3f7  jz      short loc_10083A425
0x10083a3f9  test    edx, edx
0x10083a3fb  jz      short loc_10083A41C
0x10083a3fd  cmp     edx, 64h ; 'd'
0x10083a400  jz      short loc_10083A413
0x10083a402  cmp     edx, 12Ch
0x10083a408  jnz     short loc_10083A44B
0x10083a40a  lea     r8, aTransienterror; "TransientError"
0x10083a411  jmp     short loc_10083A44B
0x10083a413  lea     r8, aPassed; "Passed"
0x10083a41a  jmp     short loc_10083A44B
0x10083a41c  lea     r8, aNotconfigured; "NotConfigured"
0x10083a423  jmp     short loc_10083A44B
0x10083a425  lea     r8, aUnauthorizedho; "UnauthorizedHost"
0x10083a42c  jmp     short loc_10083A44B
0x10083a42e  sub     edx, 12Eh
0x10083a434  jz      short loc_10083A444
0x10083a436  cmp     edx, 1
0x10083a439  jnz     short loc_10083A44B
0x10083a43b  lea     r8, aInsecurehostco; "InsecureHostConfiguration"
0x10083a442  jmp     short loc_10083A44B
0x10083a444  lea     r8, aTpmerror; "TpmError"
0x10083a44b  mov     [rsp+98h+var_70], rcx
0x10083a450  mov     [rsp+98h+var_78], r8
0x10083a455  mov     edx, 24h ; '$'
0x10083a45a  mov     ecx, 14Fh
0x10083a45f  lea     r9d, [rdx-23h]
0x10083a463  lea     r8d, [rdx-14h]
0x10083a467  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10083a46d  mov     eax, 80004005h
0x10083a472  jmp     loc_10083A1BB
0x10083a477  mov     ecx, 8007000Eh; int
0x10083a47c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
