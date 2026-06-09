# CSpp::_GetEnvironmentVariables(ulong *,_SPP_ENVIRONMENT_PROP * *)

- ea: `0x180018f10`
- end: `0x1800192a0`
- name: `?_GetEnvironmentVariables@CSpp@@AEAAJPEAKPEAPEAU_SPP_ENVIRONMENT_PROP@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int *, struct _SPP_ENVIRONMENT_PROP **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001176c`

## callees

- `0x180003b24`
- `0x18000702c`
- `0x18000de80`
- `0x180018f10`
- `0x1800192a8`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002be5c`
- `0x18002e6e0`
- `0x180034804`
- `0x180035b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001904d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001904d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019273`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019077`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001916b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019077`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001916b`

## pseudocode

```c
__int64 __fastcall CSpp::_GetEnvironmentVariables(CSpp *this, unsigned int *a2, struct _SPP_ENVIRONMENT_PROP **a3)
{
  __int64 v5; // rbx
  __int16 v6; // ax
  int v7; // eax
  __int64 v8; // rcx
  bool v9; // sf
  __int16 v10; // ax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  struct _SPP_ENVIRONMENT_PROP *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // r8
  char *v18; // rdx
  unsigned __int16 *v20[2]; // [rsp+38h] [rbp-19h] BYREF
  unsigned __int16 *Src[2]; // [rsp+48h] [rbp-9h] BYREF
  int EnvironmentVariablesForRegKey; // [rsp+58h] [rbp+7h] BYREF
  __int16 v23; // [rsp+5Ch] [rbp+Bh]
  __int16 v24; // [rsp+5Eh] [rbp+Dh]
  HKEY hKey; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v26; // [rsp+C0h] [rbp+6Fh] BYREF

  hKey = (HKEY)this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&EnvironmentVariablesForRegKey,
    "CSpp::_GetEnvironmentVariables",
    4159,
    1);
  Src[0] = (unsigned __int16 *)&FileName;
  v5 = 0;
  v26 = 0;
  hKey = 0;
  v6 = 4166;
  Src[1] = 0;
  *(_OWORD *)v20 = 0;
  if ( !a2 || (v23 = 4166, v6 = 4167, !a3) )
  {
    EnvironmentVariablesForRegKey = -2147024809;
    v24 = v6;
    goto LABEL_33;
  }
  EnvironmentVariablesForRegKey = 0;
  v23 = 4167;
  *a2 = 0;
  *a3 = 0;
  v7 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v26);
  v5 = v26;
  v9 = v7 < 0;
  EnvironmentVariablesForRegKey = v7;
  v10 = 4172;
  if ( v9 )
    goto LABEL_8;
  v23 = 4172;
  EnvironmentVariablesForRegKey = CSpp::_GetEnvironmentVariablesForRegKey(
                                    v8,
                                    L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Environment",
                                    v26);
  v10 = 4175;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4175;
  EnvironmentVariablesForRegKey = CSpp::_GetEnvironmentVariablesForRegKey(
                                    v11,
                                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                                    v5);
  v10 = 4178;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4178;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  EnvironmentVariablesForRegKey = v12;
  v9 = v12 < 0;
  v10 = 4181;
  if ( v9 )
    goto LABEL_8;
  v23 = 4181;
  EnvironmentVariablesForRegKey = SxRegReadString(hKey, L"ProgramFilesDir", (struct CBsString *)Src);
  v10 = 4182;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4182;
  EnvironmentVariablesForRegKey = SxCopyString(L"ProgramFiles", v20);
  v10 = 4183;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4183;
  EnvironmentVariablesForRegKey = SxCopyString(Src[0], &v20[1]);
  v10 = 4184;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4184;
  EnvironmentVariablesForRegKey = CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(
                                    v5,
                                    v20);
  v10 = 4185;
  if ( EnvironmentVariablesForRegKey < 0 )
    goto LABEL_8;
  v23 = 4185;
  Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)v20);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  EnvironmentVariablesForRegKey = v13;
  v9 = v13 < 0;
  v10 = 4189;
  if ( v9 )
    goto LABEL_8;
  v23 = 4189;
  if ( (int)SxRegReadString(hKey, L"ProgramFilesDir (x86)", (struct CBsString *)Src) >= 0 )
  {
    EnvironmentVariablesForRegKey = SxCopyString(L"ProgramFiles(x86)", v20);
    v10 = 4192;
    if ( EnvironmentVariablesForRegKey >= 0 )
    {
      v23 = 4192;
      EnvironmentVariablesForRegKey = SxCopyString(Src[0], &v20[1]);
      v10 = 4193;
      if ( EnvironmentVariablesForRegKey >= 0 )
      {
        v23 = 4193;
        EnvironmentVariablesForRegKey = CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(
                                          v5,
                                          v20);
        v10 = 4194;
        if ( EnvironmentVariablesForRegKey >= 0 )
        {
          v23 = 4194;
          Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)v20);
          goto LABEL_30;
        }
      }
    }
LABEL_8:
    v24 = v10;
    goto LABEL_31;
  }
LABEL_30:
  v14 = *(struct _SPP_ENVIRONMENT_PROP **)(v5 + 8);
  v15 = *(_DWORD *)(v5 + 16);
  *(_QWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *a3 = v14;
  *a2 = v15;
LABEL_31:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_33:
  Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)v20);
  v16 = EnvironmentVariablesForRegKey;
  if ( v5 )
    CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Release((void *)v5);
  CBsString::_Release((CBsString *)Src);
  v18 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&EnvironmentVariablesForRegKey, (__int64)v18, v17);
  return v16;
}

```

## disassembly

```asm
0x180018f10  mov     rax, rsp
0x180018f13  mov     [rax+18h], rbx
0x180018f17  mov     [rax+20h], rsi
0x180018f1b  mov     [rax+8], rcx
0x180018f1f  push    rbp
0x180018f20  push    rdi
0x180018f21  push    r14
0x180018f23  lea     rbp, [rax-5Fh]
0x180018f27  sub     rsp, 90h
0x180018f2e  mov     rdi, r8
0x180018f31  mov     rsi, rdx
0x180018f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f3b  lea     rax, WPP_GLOBAL_Control
0x180018f42  cmp     rcx, rax
0x180018f45  jz      short loc_180018F65
0x180018f47  test    dword ptr [rcx+1Ch], 20000000h
0x180018f4e  jz      short loc_180018F65
0x180018f50  mov     rcx, [rcx+10h]
0x180018f54  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180018f5b  mov     edx, 35h ; '5'
0x180018f60  call    WPP_SF_
0x180018f65  mov     r9d, 1; unsigned __int16
0x180018f6b  lea     rdx, aCsppGetenviron; "CSpp::_GetEnvironmentVariables"
0x180018f72  mov     r8d, 103Fh; unsigned __int16
0x180018f78  lea     rcx, [rbp+57h+var_50]; this
0x180018f7c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018f81  xor     r14d, r14d
0x180018f84  lea     rax, FileName
0x180018f8b  mov     [rbp+57h+Src], rax
0x180018f8f  mov     ebx, r14d
0x180018f92  mov     [rbp+57h+arg_8], rbx
0x180018f96  xorps   xmm0, xmm0
0x180018f99  mov     [rbp+57h+hKey], r14
0x180018f9d  mov     eax, 1046h
0x180018fa2  mov     [rbp+57h+var_58], r14
0x180018fa6  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180018faa  test    rsi, rsi
0x180018fad  jnz     short loc_180018FBF
0x180018faf  mov     [rbp+57h+var_50], 80070057h
0x180018fb6  mov     [rbp+57h+var_4A], ax
0x180018fba  jmp     loc_180019243
0x180018fbf  mov     [rbp+57h+var_4C], ax
0x180018fc3  mov     eax, 1047h
0x180018fc8  test    rdi, rdi
0x180018fcb  jz      short loc_180018FAF
0x180018fcd  mov     [rbp+57h+var_50], r14d
0x180018fd1  lea     rcx, [rbp+57h+arg_8]
0x180018fd5  mov     [rbp+57h+var_4C], ax
0x180018fd9  mov     [rsi], r14d
0x180018fdc  mov     [rdi], r14
0x180018fdf  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x180018fe4  mov     rbx, [rbp+57h+arg_8]
0x180018fe8  test    eax, eax
0x180018fea  mov     [rbp+57h+var_50], eax
0x180018fed  mov     eax, 104Ch
0x180018ff2  jns     short loc_180018FFD
0x180018ff4  mov     [rbp+57h+var_4A], ax
0x180018ff8  jmp     loc_18001922B
0x180018ffd  mov     r8, rbx
0x180019000  mov     [rbp+57h+var_4C], ax
0x180019004  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x18001900b  call    ?_GetEnvironmentVariablesForRegKey@CSpp@@AEAAJPEBGPEAV?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@@Z; CSpp::_GetEnvironmentVariablesForRegKey(ushort const *,CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)> *)
0x180019010  mov     [rbp+57h+var_50], eax
0x180019013  test    eax, eax
0x180019015  mov     eax, 104Fh
0x18001901a  js      short loc_180018FF4
0x18001901c  mov     r8, rbx
0x18001901f  mov     [rbp+57h+var_4C], ax
0x180019023  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001902a  call    ?_GetEnvironmentVariablesForRegKey@CSpp@@AEAAJPEBGPEAV?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@@Z; CSpp::_GetEnvironmentVariablesForRegKey(ushort const *,CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)> *)
0x18001902f  mov     [rbp+57h+var_50], eax
0x180019032  test    eax, eax
0x180019034  mov     eax, 1052h
0x180019039  js      short loc_180018FF4
0x18001903b  mov     rcx, [rbp+57h+hKey]; hKey
0x18001903f  mov     [rbp+57h+var_4C], ax
0x180019043  lea     rax, [rcx-1]
0x180019047  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001904b  ja      short loc_180019057
0x18001904d  call    cs:__imp_RegCloseKey
0x180019053  mov     [rbp+57h+hKey], r14
0x180019057  lea     rax, [rbp+57h+hKey]
0x18001905b  mov     r9d, 20019h; samDesired
0x180019061  xor     r8d, r8d; ulOptions
0x180019064  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180019069  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019070  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019077  call    cs:__imp_RegOpenKeyExW
0x18001907d  test    eax, eax
0x18001907f  jle     short loc_180019089
0x180019081  movzx   eax, ax
0x180019084  or      eax, 80070000h
0x180019089  mov     [rbp+57h+var_50], eax
0x18001908c  test    eax, eax
0x18001908e  mov     eax, 1055h
0x180019093  js      loc_180018FF4
0x180019099  mov     rcx, [rbp+57h+hKey]; hKey
0x18001909d  lea     r8, [rbp+57h+Src]; this
0x1800190a1  lea     rdx, aProgramfilesdi; "ProgramFilesDir"
0x1800190a8  mov     [rbp+57h+var_4C], ax
0x1800190ac  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x1800190b1  mov     [rbp+57h+var_50], eax
0x1800190b4  test    eax, eax
0x1800190b6  mov     eax, 1056h
0x1800190bb  js      loc_180018FF4
0x1800190c1  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x1800190c5  mov     [rbp+57h+var_4C], ax
0x1800190c9  lea     rcx, aProgramfiles; "ProgramFiles"
0x1800190d0  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x1800190d5  mov     [rbp+57h+var_50], eax
0x1800190d8  test    eax, eax
0x1800190da  mov     eax, 1057h
0x1800190df  js      loc_180018FF4
0x1800190e5  mov     rcx, [rbp+57h+Src]; Src
0x1800190e9  lea     rdx, [rbp+57h+var_70+8]; unsigned __int16 **
0x1800190ed  mov     [rbp+57h+var_4C], ax
0x1800190f1  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x1800190f6  mov     [rbp+57h+var_50], eax
0x1800190f9  test    eax, eax
0x1800190fb  mov     eax, 1058h
0x180019100  js      loc_180018FF4
0x180019106  lea     rdx, [rbp+57h+var_70]
0x18001910a  mov     [rbp+57h+var_4C], ax
0x18001910e  mov     rcx, rbx
0x180019111  call    ?Append@?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_ENVIRONMENT_PROP@@@Z; CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(_SPP_ENVIRONMENT_PROP *)
0x180019116  mov     [rbp+57h+var_50], eax
0x180019119  test    eax, eax
0x18001911b  mov     eax, 1059h
0x180019120  js      loc_180018FF4
0x180019126  lea     rcx, [rbp+57h+var_70]; struct _SPP_ENVIRONMENT_PROP *
0x18001912a  mov     [rbp+57h+var_4C], ax
0x18001912e  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x180019133  mov     rcx, [rbp+57h+hKey]; hKey
0x180019137  lea     rax, [rcx-1]
0x18001913b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001913f  ja      short loc_18001914B
0x180019141  call    cs:__imp_RegCloseKey
0x180019147  mov     [rbp+57h+hKey], r14
0x18001914b  lea     rax, [rbp+57h+hKey]
0x18001914f  mov     r9d, 20019h; samDesired
0x180019155  xor     r8d, r8d; ulOptions
0x180019158  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18001915d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019164  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001916b  call    cs:__imp_RegOpenKeyExW
0x180019171  test    eax, eax
0x180019173  jle     short loc_18001917D
0x180019175  movzx   eax, ax
0x180019178  or      eax, 80070000h
0x18001917d  mov     [rbp+57h+var_50], eax
0x180019180  test    eax, eax
0x180019182  mov     eax, 105Dh
0x180019187  js      loc_180018FF4
0x18001918d  mov     rcx, [rbp+57h+hKey]; hKey
0x180019191  lea     r8, [rbp+57h+Src]; this
0x180019195  lea     rdx, aProgramfilesdi_0; "ProgramFilesDir (x86)"
0x18001919c  mov     [rbp+57h+var_4C], ax
0x1800191a0  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x1800191a5  test    eax, eax
0x1800191a7  js      short loc_180019217
0x1800191a9  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x1800191ad  lea     rcx, aProgramfilesX8; "ProgramFiles(x86)"
0x1800191b4  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x1800191b9  mov     [rbp+57h+var_50], eax
0x1800191bc  test    eax, eax
0x1800191be  mov     eax, 1060h
0x1800191c3  js      loc_180018FF4
0x1800191c9  mov     rcx, [rbp+57h+Src]; Src
0x1800191cd  lea     rdx, [rbp+57h+var_70+8]; unsigned __int16 **
0x1800191d1  mov     [rbp+57h+var_4C], ax
0x1800191d5  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x1800191da  mov     [rbp+57h+var_50], eax
0x1800191dd  test    eax, eax
0x1800191df  mov     eax, 1061h
0x1800191e4  js      loc_180018FF4
0x1800191ea  lea     rdx, [rbp+57h+var_70]
0x1800191ee  mov     [rbp+57h+var_4C], ax
0x1800191f2  mov     rcx, rbx
0x1800191f5  call    ?Append@?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_ENVIRONMENT_PROP@@@Z; CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(_SPP_ENVIRONMENT_PROP *)
0x1800191fa  mov     [rbp+57h+var_50], eax
0x1800191fd  test    eax, eax
0x1800191ff  mov     eax, 1062h
0x180019204  js      loc_180018FF4
0x18001920a  lea     rcx, [rbp+57h+var_70]; struct _SPP_ENVIRONMENT_PROP *
0x18001920e  mov     [rbp+57h+var_4C], ax
0x180019212  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x180019217  mov     rcx, [rbx+8]
0x18001921b  mov     eax, [rbx+10h]
0x18001921e  mov     [rbx+8], r14
0x180019222  mov     [rbx+10h], r14
0x180019226  mov     [rdi], rcx
0x180019229  mov     [rsi], eax
0x18001922b  mov     rcx, [rbp+57h+hKey]; hKey
0x18001922f  lea     rax, [rcx-1]
0x180019233  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019237  ja      short loc_180019243
0x180019239  call    cs:__imp_RegCloseKey
0x18001923f  mov     [rbp+57h+hKey], r14
0x180019243  lea     rcx, [rbp+57h+var_70]; struct _SPP_ENVIRONMENT_PROP *
0x180019247  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x18001924c  mov     edi, [rbp+57h+var_50]
0x18001924f  test    rbx, rbx
0x180019252  jz      short loc_18001925C
0x180019254  mov     rcx, rbx; Block
0x180019257  call    ?Release@?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@QEAAKXZ; CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Release(void)
0x18001925c  lea     rcx, [rbp+57h+Src]; this
0x180019260  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180019265  mov     rcx, [rbp+57h+hKey]; hKey
0x180019269  lea     rdx, [rcx-1]
0x18001926d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019271  ja      short loc_18001927D
0x180019273  call    cs:__imp_RegCloseKey
0x180019279  mov     [rbp+57h+hKey], r14
0x18001927d  lea     rcx, [rbp+57h+var_50]; this
0x180019281  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019286  lea     r11, [rsp+0A0h+var_10]
0x18001928e  mov     eax, edi
0x180019290  mov     rbx, [r11+30h]
0x180019294  mov     rsi, [r11+38h]
0x180019298  mov     rsp, r11
0x18001929b  pop     r14
0x18001929d  pop     rdi
0x18001929e  pop     rbp
0x18001929f  retn
```
