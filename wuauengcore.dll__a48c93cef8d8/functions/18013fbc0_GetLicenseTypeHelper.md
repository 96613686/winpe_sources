# GetLicenseTypeHelper

- ea: `0x18013fbc0`
- end: `0x18013ff18`
- name: `GetLicenseTypeHelper`
- size: `856`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18013d6b0`
- `0x18013ff20`

## callees

- `0x18013fbc0`
- `0x1801f2a88`
- `0x1801f2cf0`
- `0x180238920`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fce2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd5c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fea3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fce2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fd5c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18013fea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013fee1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013fee1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18013fc3b`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18013fc3b`
- `SLC!SLGetWindowsInformation` at `0x18013fc58`
- `SLC!SLGetWindowsInformation` at `0x18013fc58`

## string_xrefs

- `0x18013fc34`: `ext-ms-win-security-slc-l1-1-0`
- `0x18013fc26`: `Security-SPP-Action-StateData`
- `0x18013fc51`: `Security-SPP-Action-StateData`

## pseudocode

```c
__int64 __fastcall GetLicenseTypeHelper(WUSystemInterfaceHelper *a1, unsigned int a2)
{
  int v2; // r14d
  char v3; // di
  HRESULT v4; // eax
  PBYTE v5; // rcx
  wchar_t *i; // rax
  wchar_t *v7; // rbx
  PCNZWCH *v8; // rsi
  unsigned int v9; // ebx
  unsigned __int8 **lpString2; // [rsp+28h] [rbp-E0h]
  const wchar_t *v12; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-C8h]
  __int64 v14; // [rsp+50h] [rbp-B8h]
  const wchar_t *v15; // [rsp+58h] [rbp-B0h]
  __int64 v16; // [rsp+60h] [rbp-A8h]
  const wchar_t *v17; // [rsp+68h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-98h]
  const wchar_t *v19; // [rsp+78h] [rbp-90h]
  int v20; // [rsp+80h] [rbp-88h]
  const wchar_t *v21; // [rsp+88h] [rbp-80h]
  int v22; // [rsp+90h] [rbp-78h]
  const wchar_t *v23; // [rsp+98h] [rbp-70h]
  int v24; // [rsp+A0h] [rbp-68h]
  const wchar_t *v25; // [rsp+A8h] [rbp-60h]
  int v26; // [rsp+B0h] [rbp-58h]
  const wchar_t *v27; // [rsp+B8h] [rbp-50h]
  int v28; // [rsp+C0h] [rbp-48h]
  const wchar_t *v29; // [rsp+C8h] [rbp-40h]
  int v30; // [rsp+D0h] [rbp-38h]
  const wchar_t *v31; // [rsp+D8h] [rbp-30h]
  int v32; // [rsp+E0h] [rbp-28h]
  const wchar_t *v33; // [rsp+E8h] [rbp-20h]
  int v34; // [rsp+F0h] [rbp-18h]
  const wchar_t *v35; // [rsp+F8h] [rbp-10h]
  int v36; // [rsp+100h] [rbp-8h]
  const wchar_t *v37; // [rsp+108h] [rbp+0h]
  int v38; // [rsp+110h] [rbp+8h]
  const wchar_t *v39; // [rsp+118h] [rbp+10h]
  int v40; // [rsp+120h] [rbp+18h]
  PCNZWCH lpString1; // [rsp+128h] [rbp+20h] BYREF
  PBYTE ppbValue; // [rsp+130h] [rbp+28h] BYREF
  wchar_t *Context; // [rsp+138h] [rbp+30h] BYREF
  UINT pcbValue; // [rsp+140h] [rbp+38h] BYREF
  SLDATATYPE peDataType; // [rsp+144h] [rbp+3Ch] BYREF
  wchar_t Delimiter[2]; // [rsp+148h] [rbp+40h] BYREF
  wchar_t v47[2]; // [rsp+14Ch] [rbp+44h] BYREF

  v2 = 0;
  wcscpy(Delimiter, L";");
  peDataType = SL_DATA_NONE;
  v3 = 0;
  pcbValue = 0;
  ppbValue = 0;
  Context = 0;
  wcscpy(v47, L"=");
  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported(a1, a2) < 0 )
  {
    if ( !IsApiSetImplemented("ext-ms-win-security-slc-l1-1-0") )
      goto LABEL_6;
    v4 = SLGetWindowsInformation(L"Security-SPP-Action-StateData", &peDataType, &pcbValue, &ppbValue);
  }
  else
  {
    v4 = WUSystemInterfaceHelper::SLGetWindowsInformation(
           (WUSystemInterfaceHelper *)L"Security-SPP-Action-StateData",
           (const wchar_t *)&peDataType,
           &pcbValue,
           (unsigned int *)&ppbValue,
           lpString2);
  }
  if ( v4 < 0 )
  {
LABEL_22:
    v5 = ppbValue;
    goto LABEL_23;
  }
LABEL_6:
  v5 = ppbValue;
  if ( ppbValue && pcbValue > 2 )
  {
    for ( i = o_wcstok_s_0((wchar_t *)ppbValue, Delimiter, &Context); i; i = o_wcstok_s_0(0, Delimiter, &Context) )
    {
      lpString1 = 0;
      v7 = o_wcstok_s_0(i, v47, (wchar_t **)&lpString1);
      if ( v7 && lpString1 )
      {
        if ( CompareStringW(0x7Fu, 0, v7, -1, L"LastNotificationId", -1) == 2
          && (CompareStringW(0x7Fu, 0, lpString1, -1, L"Cleanup", -1) == 2
           || CompareStringW(0x7Fu, 0, lpString1, -1, L"KernelExpiration", -1) == 2) )
        {
          v3 = 1;
        }
        if ( CompareStringW(0x7Fu, 0, v7, -1, L"ProductKeyType", -1) == 2 )
        {
          LODWORD(v13[0]) = 1;
          v12 = L"Retail";
          v8 = &v12;
          LODWORD(v14) = 2;
          v13[1] = L"Retail:TB";
          v9 = 0;
          LODWORD(v16) = 3;
          v15 = L"Retail:TB:Eval";
          v17 = L"Retail:TB:Trial";
          v19 = L"Retail:TB:Promo";
          v21 = L"Retail:TB:Sub";
          v23 = L"OEM:SLP";
          v25 = L"OEM:COA";
          v27 = L"OEM:DM";
          v29 = L"OEM:NONSLP";
          v31 = L"Volume";
          v33 = L"Volume:CSVLK";
          v35 = L"Volume:GVLK";
          v37 = L"Volume:MAK";
          v39 = L"VT:IA";
          LODWORD(v18) = 4;
          v20 = 5;
          v22 = 6;
          v24 = 7;
          v26 = 8;
          v28 = 9;
          v30 = 7;
          v32 = 11;
          v34 = 12;
          v36 = 13;
          v38 = 14;
          v40 = 15;
          while ( CompareStringW(0x7Fu, 0, lpString1, -1, *v8, -1) != 2 )
          {
            ++v9;
            v8 += 2;
            if ( v9 >= 0xF )
              goto LABEL_21;
          }
          v2 = v13[2 * v9];
        }
      }
LABEL_21:
      ;
    }
    goto LABEL_22;
  }
LABEL_23:
  LocalFree(v5);
  return v2 & (unsigned int)-(v3 != 0);
}

```

## disassembly

```asm
0x18013fbc0  mov     rax, rsp
0x18013fbc3  mov     [rax+8], rbx
0x18013fbc7  mov     [rax+10h], rsi
0x18013fbcb  mov     [rax+18h], rdi
0x18013fbcf  push    rbp
0x18013fbd0  push    r12
0x18013fbd2  push    r14
0x18013fbd4  lea     rbp, [rax-68h]
0x18013fbd8  sub     rsp, 150h
0x18013fbdf  mov     rax, cs:__security_cookie
0x18013fbe6  xor     rax, rsp
0x18013fbe9  mov     [rbp+60h+var_18], rax
0x18013fbed  xor     r14d, r14d
0x18013fbf0  mov     dword ptr [rbp+60h+Delimiter], 3Bh ; ';'
0x18013fbf7  mov     [rbp+60h+peDataType], r14d
0x18013fbfb  xor     dil, dil
0x18013fbfe  mov     [rbp+60h+pcbValue], r14d
0x18013fc02  mov     [rbp+60h+ppbValue], r14
0x18013fc06  mov     [rbp+60h+Context], r14
0x18013fc0a  mov     dword ptr [rbp+60h+var_1C], 3Dh ; '='
0x18013fc11  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x18013fc16  test    eax, eax
0x18013fc18  js      short loc_18013FC34
0x18013fc1a  lea     r9, [rbp+60h+ppbValue]; unsigned int *
0x18013fc1e  lea     r8, [rbp+60h+pcbValue]; unsigned int *
0x18013fc22  lea     rdx, [rbp+60h+peDataType]; wchar_t *
0x18013fc26  lea     rcx, aSecuritySppAct; "Security-SPP-Action-StateData"
0x18013fc2d  call    ?SLGetWindowsInformation@WUSystemInterfaceHelper@@YAJPEB_WPEAKPEAIPEAPEAE@Z; WUSystemInterfaceHelper::SLGetWindowsInformation(wchar_t const *,ulong *,uint *,uchar * *)
0x18013fc32  jmp     short loc_18013FC5E
0x18013fc34  lea     rcx, aExtMsWinSecuri; "ext-ms-win-security-slc-l1-1-0"
0x18013fc3b  call    cs:__imp_IsApiSetImplemented
0x18013fc41  test    eax, eax
0x18013fc43  jz      short loc_18013FC66
0x18013fc45  lea     r9, [rbp+60h+ppbValue]; ppbValue
0x18013fc49  lea     r8, [rbp+60h+pcbValue]; pcbValue
0x18013fc4d  lea     rdx, [rbp+60h+peDataType]; peDataType
0x18013fc51  lea     rcx, aSecuritySppAct; "Security-SPP-Action-StateData"
0x18013fc58  call    cs:__imp_SLGetWindowsInformation
0x18013fc5e  test    eax, eax
0x18013fc60  js      loc_18013FEDD
0x18013fc66  mov     rcx, [rbp+60h+ppbValue]; String
0x18013fc6a  test    rcx, rcx
0x18013fc6d  jz      loc_18013FEE1
0x18013fc73  cmp     [rbp+60h+pcbValue], 2
0x18013fc77  jbe     loc_18013FEE1
0x18013fc7d  lea     r8, [rbp+60h+Context]; Context
0x18013fc81  lea     rdx, [rbp+60h+Delimiter]; Delimiter
0x18013fc85  call    _o_wcstok_s_0
0x18013fc8a  test    rax, rax
0x18013fc8d  jz      loc_18013FEDD
0x18013fc93  or      r12d, 0FFFFFFFFh
0x18013fc97  lea     r8, [rbp+60h+lpString1]; Context
0x18013fc9b  mov     [rbp+60h+lpString1], 0
0x18013fca3  lea     rdx, [rbp+60h+var_1C]; Delimiter
0x18013fca7  mov     rcx, rax; String
0x18013fcaa  call    _o_wcstok_s_0
0x18013fcaf  mov     rbx, rax
0x18013fcb2  test    rax, rax
0x18013fcb5  jz      loc_18013FEC5
0x18013fcbb  cmp     [rbp+60h+lpString1], 0
0x18013fcc0  jz      loc_18013FEC5
0x18013fcc6  xor     edx, edx; dwCmpFlags
0x18013fcc8  mov     [rsp+160h+cchCount2], r12d; cchCount2
0x18013fccd  lea     rax, aLastnotificati; "LastNotificationId"
0x18013fcd4  mov     r9d, r12d; cchCount1
0x18013fcd7  mov     r8, rbx; lpString1
0x18013fcda  mov     [rsp+160h+lpString2], rax; lpString2
0x18013fcdf  lea     ecx, [rdx+7Fh]; Locale
0x18013fce2  call    cs:__imp_CompareStringW
0x18013fce8  cmp     eax, 2
0x18013fceb  jnz     short loc_18013FD40
0x18013fced  mov     r8, [rbp+60h+lpString1]; lpString1
0x18013fcf1  lea     rax, aCleanup; "Cleanup"
0x18013fcf8  xor     edx, edx; dwCmpFlags
0x18013fcfa  mov     [rsp+160h+cchCount2], r12d; cchCount2
0x18013fcff  mov     r9d, r12d; cchCount1
0x18013fd02  mov     [rsp+160h+lpString2], rax; lpString2
0x18013fd07  lea     ecx, [rdx+7Fh]; Locale
0x18013fd0a  call    cs:__imp_CompareStringW
0x18013fd10  cmp     eax, 2
0x18013fd13  jz      short loc_18013FD3D
0x18013fd15  mov     r8, [rbp+60h+lpString1]; lpString1
0x18013fd19  lea     rax, aKernelexpirati; "KernelExpiration"
0x18013fd20  xor     edx, edx; dwCmpFlags
0x18013fd22  mov     [rsp+160h+cchCount2], r12d; cchCount2
0x18013fd27  mov     r9d, r12d; cchCount1
0x18013fd2a  mov     [rsp+160h+lpString2], rax; lpString2
0x18013fd2f  lea     ecx, [rdx+7Fh]; Locale
0x18013fd32  call    cs:__imp_CompareStringW
0x18013fd38  cmp     eax, 2
0x18013fd3b  jnz     short loc_18013FD40
0x18013fd3d  mov     dil, 1
0x18013fd40  xor     edx, edx; dwCmpFlags
0x18013fd42  mov     [rsp+160h+cchCount2], r12d; cchCount2
0x18013fd47  lea     rax, aProductkeytype; "ProductKeyType"
0x18013fd4e  mov     r9d, r12d; cchCount1
0x18013fd51  mov     r8, rbx; lpString1
0x18013fd54  mov     [rsp+160h+lpString2], rax; lpString2
0x18013fd59  lea     ecx, [rdx+7Fh]; Locale
0x18013fd5c  call    cs:__imp_CompareStringW
0x18013fd62  cmp     eax, 2
0x18013fd65  jnz     loc_18013FEC5
0x18013fd6b  lea     rax, aRetail; "Retail"
0x18013fd72  mov     dword ptr [rsp+160h+var_128], 1
0x18013fd7a  mov     [rsp+160h+var_130], rax
0x18013fd7f  lea     rsi, [rsp+160h+var_130]
0x18013fd84  lea     rax, aRetailTb; "Retail:TB"
0x18013fd8b  mov     dword ptr [rsp+160h+var_118], 2
0x18013fd93  mov     qword ptr [rsp+160h+var_120], rax
0x18013fd98  xor     ebx, ebx
0x18013fd9a  lea     rax, aRetailTbEval; "Retail:TB:Eval"
0x18013fda1  mov     dword ptr [rsp+160h+var_108], 3
0x18013fda9  mov     [rsp+160h+var_110], rax
0x18013fdae  lea     rax, aRetailTbTrial; "Retail:TB:Trial"
0x18013fdb5  mov     [rsp+160h+var_100], rax
0x18013fdba  lea     rax, aRetailTbPromo; "Retail:TB:Promo"
0x18013fdc1  mov     [rsp+160h+var_F0], rax
0x18013fdc6  lea     rax, aRetailTbSub; "Retail:TB:Sub"
0x18013fdcd  mov     [rbp+60h+var_E0], rax
0x18013fdd1  lea     rax, aOemSlp; "OEM:SLP"
0x18013fdd8  mov     [rbp+60h+var_D0], rax
0x18013fddc  lea     rax, aOemCoa; "OEM:COA"
0x18013fde3  mov     [rbp+60h+var_C0], rax
0x18013fde7  lea     rax, aOemDm; "OEM:DM"
0x18013fdee  mov     [rbp+60h+var_B0], rax
0x18013fdf2  lea     rax, aOemNonslp; "OEM:NONSLP"
0x18013fdf9  mov     [rbp+60h+var_A0], rax
0x18013fdfd  lea     rax, aVolume; "Volume"
0x18013fe04  mov     [rbp+60h+var_90], rax
0x18013fe08  lea     rax, aVolumeCsvlk; "Volume:CSVLK"
0x18013fe0f  mov     [rbp+60h+var_80], rax
0x18013fe13  lea     rax, aVolumeGvlk; "Volume:GVLK"
0x18013fe1a  mov     [rbp+60h+var_70], rax
0x18013fe1e  lea     rax, aVolumeMak; "Volume:MAK"
0x18013fe25  mov     [rbp+60h+var_60], rax
0x18013fe29  lea     rax, aVtIa; "VT:IA"
0x18013fe30  mov     [rbp+60h+var_50], rax
0x18013fe34  mov     dword ptr [rsp+160h+var_F8], 4
0x18013fe3c  mov     [rsp+160h+var_E8], 5
0x18013fe44  mov     [rbp+60h+var_D8], 6
0x18013fe4b  mov     [rbp+60h+var_C8], 7
0x18013fe52  mov     [rbp+60h+var_B8], 8
0x18013fe59  mov     [rbp+60h+var_A8], 9
0x18013fe60  mov     [rbp+60h+var_98], 7
0x18013fe67  mov     [rbp+60h+var_88], 0Bh
0x18013fe6e  mov     [rbp+60h+var_78], 0Ch
0x18013fe75  mov     [rbp+60h+var_68], 0Dh
0x18013fe7c  mov     [rbp+60h+var_58], 0Eh
0x18013fe83  mov     [rbp+60h+var_48], 0Fh
0x18013fe8a  mov     rax, [rsi]
0x18013fe8d  xor     edx, edx; dwCmpFlags
0x18013fe8f  mov     r8, [rbp+60h+lpString1]; lpString1
0x18013fe93  mov     r9d, r12d; cchCount1
0x18013fe96  mov     [rsp+160h+cchCount2], r12d; cchCount2
0x18013fe9b  mov     [rsp+160h+lpString2], rax; lpString2
0x18013fea0  lea     ecx, [rdx+7Fh]; Locale
0x18013fea3  call    cs:__imp_CompareStringW
0x18013fea9  cmp     eax, 2
0x18013feac  jz      short loc_18013FEBB
0x18013feae  inc     ebx
0x18013feb0  add     rsi, 10h
0x18013feb4  cmp     ebx, 0Fh
0x18013feb7  jb      short loc_18013FE8A
0x18013feb9  jmp     short loc_18013FEC5
0x18013febb  mov     eax, ebx
0x18013febd  add     rax, rax
0x18013fec0  mov     r14d, dword ptr [rsp+rax*8+160h+var_128]
0x18013fec5  lea     r8, [rbp+60h+Context]; Context
0x18013fec9  xor     ecx, ecx; String
0x18013fecb  lea     rdx, [rbp+60h+Delimiter]; Delimiter
0x18013fecf  call    _o_wcstok_s_0
0x18013fed4  test    rax, rax
0x18013fed7  jnz     loc_18013FC97
0x18013fedd  mov     rcx, [rbp+60h+ppbValue]; hMem
0x18013fee1  call    cs:__imp_LocalFree
0x18013fee7  neg     dil
0x18013feea  sbb     eax, eax
0x18013feec  and     eax, r14d
0x18013feef  mov     rcx, [rbp+60h+var_18]
0x18013fef3  xor     rcx, rsp; StackCookie
0x18013fef6  call    __security_check_cookie
0x18013fefb  lea     r11, [rsp+160h+var_10]
0x18013ff03  mov     rbx, [r11+20h]
0x18013ff07  mov     rsi, [r11+28h]
0x18013ff0b  mov     rdi, [r11+30h]
0x18013ff0f  mov     rsp, r11
0x18013ff12  pop     r14
0x18013ff14  pop     r12
0x18013ff16  pop     rbp
0x18013ff17  retn
```
