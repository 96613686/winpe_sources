# DeleteDefenderWscInstance

- ea: `0x180001b88`
- end: `0x1800020ac`
- name: `DeleteDefenderWscInstance`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002368`

## callees

- `0x180001b24`
- `0x180001b50`
- `0x180001b88`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001c2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001c2e`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bae`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bf4`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bae`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180001bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x180001cdc`
- `OLEAUT32!__imp_SysFreeString` at `0x180001cec`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ddd`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ded`
- `OLEAUT32!__imp_SysFreeString` at `0x180001dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000202f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000203f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000204f`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x180001cdc`
- `OLEAUT32!__imp_SysFreeString` at `0x180001cec`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ddd`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ded`
- `OLEAUT32!__imp_SysFreeString` at `0x180001dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000202f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000203f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000204f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fab`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001cbc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001dcd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001ee1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001f9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000201f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001cbc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001dcd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001ee1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180001f9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000201f`
- `WDSCORE!CurrentIP` at `0x180001c51`
- `WDSCORE!CurrentIP` at `0x180001d61`
- `WDSCORE!CurrentIP` at `0x180001e6e`
- `WDSCORE!CurrentIP` at `0x180001f2c`
- `WDSCORE!CurrentIP` at `0x180001fba`
- `WDSCORE!CurrentIP` at `0x180001c51`
- `WDSCORE!CurrentIP` at `0x180001d61`
- `WDSCORE!CurrentIP` at `0x180001e6e`
- `WDSCORE!CurrentIP` at `0x180001f2c`
- `WDSCORE!CurrentIP` at `0x180001fba`

## string_xrefs

- `0x180001ba7`: `\\.\ROOT\SecurityCenter2`
- `0x180001c8a`: `DeleteDefenderWscInstance`
- `0x180001d9b`: `DeleteDefenderWscInstance`
- `0x180001e49`: `DeleteDefenderWscInstance`
- `0x180001c65`: `MRTGeneralize:%d - ERROR: Failed CoCreateInstance`
- `0x180001e91`: `MRTGeneralize:%d - WARNING: Failed DeleteInstance %ls hr=%u, this is probably because the value does not exist`
- `0x180001f4f`: `MRTGeneralize:%d - WARNING: Failed DeleteInstance %ls hr=%u, this is probably because the value does not exist`
- `0x180001fcf`: `MRTGeneralize:%d - INFO: Finished attempting to delete Defender WSC registration`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void DeleteDefenderWscInstance()
{
  int v0; // ecx
  OLECHAR *v1; // rbx
  int v2; // ecx
  OLECHAR *v3; // rdi
  int v4; // ecx
  OLECHAR *v5; // rsi
  DWORD v6; // r15d
  __int64 v7; // r14
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // r15d
  __int64 v10; // r14
  struct tagLOG_PARTIAL_MSG *v11; // rax
  DWORD LastError; // r15d
  __int64 v13; // r14
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // r15d
  __int64 v16; // r14
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // r15d
  __int64 v19; // r14
  struct tagLOG_PARTIAL_MSG *v20; // rax
  int v21; // [rsp+C0h] [rbp+48h]
  int v22; // [rsp+C0h] [rbp+48h]
  __int64 v23; // [rsp+C8h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp+58h] BYREF
  OLECHAR *v25; // [rsp+D8h] [rbp+60h]

  ppv = 0;
  v23 = 0;
  v1 = SysAllocString(L"\\\\.\\ROOT\\SecurityCenter2");
  v25 = v1;
  if ( !v1 )
    ATL::AtlThrowImpl(v0);
  v3 = SysAllocString(L"AntiSpywareProduct.instanceGuid=\"{D68DDC3A-831F-4FAE-9E44-DA132C1ACF46}\"");
  if ( !v3 )
    ATL::AtlThrowImpl(v2);
  v5 = SysAllocString(L"AntiVirusProduct.instanceGuid=\"{D68DDC3A-831F-4FAE-9E44-DA132C1ACF46}\"");
  if ( !v5 )
    ATL::AtlThrowImpl(v4);
  if ( CoCreateInstance(&CLSID_WbemLocator, 0, 0x17u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv) >= 0 )
  {
    if ( (*(int (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           v1,
           0,
           0,
           0,
           0,
           0,
           0,
           &v23) >= 0 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v23 + 128LL))(
              v23,
              v3,
              0,
              0,
              0);
      if ( v21 < 0 )
      {
        LastError = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(
                0x3000000u,
                "MRTGeneralize:%d - WARNING: Failed DeleteInstance %ls hr=%u, this is probably because the value does not exist",
                107,
                L"AntiSpywareProduct.instanceGuid=\"{D68DDC3A-831F-4FAE-9E44-DA132C1ACF46}\"",
                v21);
        WdsSetupLogMessageW(
          v14,
          983040,
          L"D",
          0,
          107,
          L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
          L"DeleteDefenderWscInstance",
          v13,
          LastError,
          0,
          0);
      }
      v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v23 + 128LL))(
              v23,
              v5,
              0,
              0,
              0);
      if ( v22 < 0 )
      {
        v15 = GetLastError();
        v16 = CurrentIP();
        v17 = ConstructPartialMsgW(
                0x3000000u,
                "MRTGeneralize:%d - WARNING: Failed DeleteInstance %ls hr=%u, this is probably because the value does not exist",
                116,
                L"AntiVirusProduct.instanceGuid=\"{D68DDC3A-831F-4FAE-9E44-DA132C1ACF46}\"",
                v22);
        WdsSetupLogMessageW(
          v17,
          983040,
          L"D",
          0,
          116,
          L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
          L"DeleteDefenderWscInstance",
          v16,
          v15,
          0,
          0);
      }
      v18 = GetLastError();
      v19 = CurrentIP();
      v20 = ConstructPartialMsgW(
              0x4000000u,
              "MRTGeneralize:%d - INFO: Finished attempting to delete Defender WSC registration",
              122);
      WdsSetupLogMessageW(
        v20,
        983040,
        L"D",
        0,
        122,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"DeleteDefenderWscInstance",
        v19,
        v18,
        0,
        0);
      SysFreeString(v5);
      SysFreeString(v3);
      SysFreeString(v1);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    else
    {
      v9 = GetLastError();
      v10 = CurrentIP();
      v11 = ConstructPartialMsgW(0x2000000u, "MRTGeneralize:%d - ERROR: Failed ConnectServer", 98);
      WdsSetupLogMessageW(
        v11,
        983040,
        L"D",
        0,
        98,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"DeleteDefenderWscInstance",
        v10,
        v9,
        0,
        0);
      SysFreeString(v5);
      SysFreeString(v3);
      SysFreeString(v1);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(0x2000000u, "MRTGeneralize:%d - ERROR: Failed CoCreateInstance", 82);
    WdsSetupLogMessageW(
      v8,
      983040,
      L"D",
      0,
      82,
      L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
      L"DeleteDefenderWscInstance",
      v7,
      v6,
      0,
      0);
    SysFreeString(v5);
    SysFreeString(v3);
    SysFreeString(v1);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180001b88  push    rbp
0x180001b8a  push    rbx
0x180001b8b  push    rsi
0x180001b8c  push    rdi
0x180001b8d  push    r12
0x180001b8f  push    r13
0x180001b91  push    r14
0x180001b93  push    r15
0x180001b95  mov     rbp, rsp
0x180001b98  sub     rsp, 78h
0x180001b9c  xor     r12d, r12d
0x180001b9f  mov     [rbp+arg_10], r12
0x180001ba3  mov     [rbp+arg_8], r12
0x180001ba7  lea     rcx, psz; "\\\\.\\ROOT\\SecurityCenter2"
0x180001bae  call    cs:__imp_SysAllocString
0x180001bb5  nop     dword ptr [rax+rax+00h]
0x180001bba  mov     rbx, rax
0x180001bbd  mov     [rbp+arg_18], rax
0x180001bc1  test    rax, rax
0x180001bc4  jz      loc_1800020A0
0x180001bca  lea     rcx, aAntispywarepro; "AntiSpywareProduct.instanceGuid=\"{D68D"...
0x180001bd1  call    cs:__imp_SysAllocString
0x180001bd8  nop     dword ptr [rax+rax+00h]
0x180001bdd  mov     rdi, rax
0x180001be0  mov     [rbp+var_18], rax
0x180001be4  test    rax, rax
0x180001be7  jz      loc_1800020A6
0x180001bed  lea     rcx, aAntivirusprodu; "AntiVirusProduct.instanceGuid=\"{D68DDC"...
0x180001bf4  call    cs:__imp_SysAllocString
0x180001bfb  nop     dword ptr [rax+rax+00h]
0x180001c00  mov     rsi, rax
0x180001c03  mov     [rbp+var_10], rax
0x180001c07  test    rax, rax
0x180001c0a  jz      loc_18000209A
0x180001c10  lea     rax, [rbp+arg_10]
0x180001c14  mov     [rsp+78h+ppv], rax; ppv
0x180001c19  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x180001c20  xor     edx, edx; pUnkOuter
0x180001c22  lea     r8d, [r12+17h]; dwClsContext
0x180001c27  lea     rcx, CLSID_WbemLocator; rclsid
0x180001c2e  call    cs:__imp_CoCreateInstance
0x180001c35  nop     dword ptr [rax+rax+00h]
0x180001c3a  test    eax, eax
0x180001c3c  jns     loc_180001D14
0x180001c42  call    cs:__imp_GetLastError
0x180001c49  nop     dword ptr [rax+rax+00h]
0x180001c4e  mov     r15d, eax
0x180001c51  call    cs:__imp_CurrentIP
0x180001c58  nop     dword ptr [rax+rax+00h]
0x180001c5d  mov     r14, rax
0x180001c60  lea     r8d, [r12+52h]
0x180001c65  lea     rdx, aMrtgeneralizeD_15; "MRTGeneralize:%d - ERROR: Failed CoCrea"...
0x180001c6c  mov     ecx, 2000000h; unsigned int
0x180001c71  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180001c76  mov     [rsp+78h+var_28], r12d
0x180001c7b  mov     [rsp+78h+var_30], r12
0x180001c80  mov     dword ptr [rsp+78h+var_38], r15d
0x180001c85  mov     [rsp+78h+var_40], r14
0x180001c8a  lea     r12, aDeletedefender; "DeleteDefenderWscInstance"
0x180001c91  mov     [rsp+78h+var_48], r12
0x180001c96  lea     r13, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180001c9d  mov     [rsp+78h+var_50], r13
0x180001ca2  mov     dword ptr [rsp+78h+ppv], 52h ; 'R'
0x180001caa  xor     r9d, r9d
0x180001cad  lea     r8, aD; "D"
0x180001cb4  mov     edx, 0F0000h
0x180001cb9  mov     rcx, rax
0x180001cbc  call    cs:__imp_WdsSetupLogMessageW
0x180001cc3  nop     dword ptr [rax+rax+00h]
0x180001cc8  nop
0x180001cc9  mov     rcx, rsi; bstrString
0x180001ccc  call    cs:__imp_SysFreeString
0x180001cd3  nop     dword ptr [rax+rax+00h]
0x180001cd8  nop
0x180001cd9  mov     rcx, rdi; bstrString
0x180001cdc  call    cs:__imp_SysFreeString
0x180001ce3  nop     dword ptr [rax+rax+00h]
0x180001ce8  nop
0x180001ce9  mov     rcx, rbx; bstrString
0x180001cec  call    cs:__imp_SysFreeString
0x180001cf3  nop     dword ptr [rax+rax+00h]
0x180001cf8  nop
0x180001cf9  mov     rcx, [rbp+arg_8]
0x180001cfd  test    rcx, rcx
0x180001d00  jz      short loc_180001D0F
0x180001d02  mov     rax, [rcx]
0x180001d05  mov     rax, [rax+10h]
0x180001d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0e  nop
0x180001d0f  jmp     loc_180002072
0x180001d14  mov     rcx, [rbp+arg_10]
0x180001d18  mov     rax, [rcx]
0x180001d1b  lea     rdx, [rbp+arg_8]
0x180001d1f  mov     [rsp+78h+var_38], rdx
0x180001d24  mov     [rsp+78h+var_40], r12
0x180001d29  mov     [rsp+78h+var_48], r12
0x180001d2e  mov     dword ptr [rsp+78h+var_50], r12d
0x180001d33  mov     [rsp+78h+ppv], r12
0x180001d38  xor     r9d, r9d
0x180001d3b  xor     r8d, r8d
0x180001d3e  mov     rdx, rbx
0x180001d41  mov     rax, [rax+18h]
0x180001d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4a  test    eax, eax
0x180001d4c  jns     loc_180001E25
0x180001d52  call    cs:__imp_GetLastError
0x180001d59  nop     dword ptr [rax+rax+00h]
0x180001d5e  mov     r15d, eax
0x180001d61  call    cs:__imp_CurrentIP
0x180001d68  nop     dword ptr [rax+rax+00h]
0x180001d6d  mov     r14, rax
0x180001d70  mov     r8d, 62h ; 'b'
0x180001d76  lea     rdx, aMrtgeneralizeD_5; "MRTGeneralize:%d - ERROR: Failed Connec"...
0x180001d7d  mov     ecx, 2000000h; unsigned int
0x180001d82  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180001d87  mov     [rsp+78h+var_28], r12d
0x180001d8c  mov     [rsp+78h+var_30], r12
0x180001d91  mov     dword ptr [rsp+78h+var_38], r15d
0x180001d96  mov     [rsp+78h+var_40], r14
0x180001d9b  lea     r12, aDeletedefender; "DeleteDefenderWscInstance"
0x180001da2  mov     [rsp+78h+var_48], r12
0x180001da7  lea     r13, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180001dae  mov     [rsp+78h+var_50], r13
0x180001db3  mov     dword ptr [rsp+78h+ppv], 62h ; 'b'
0x180001dbb  xor     r9d, r9d
0x180001dbe  lea     r8, aD; "D"
0x180001dc5  mov     edx, 0F0000h
0x180001dca  mov     rcx, rax
0x180001dcd  call    cs:__imp_WdsSetupLogMessageW
0x180001dd4  nop     dword ptr [rax+rax+00h]
0x180001dd9  nop
0x180001dda  mov     rcx, rsi; bstrString
0x180001ddd  call    cs:__imp_SysFreeString
0x180001de4  nop     dword ptr [rax+rax+00h]
0x180001de9  nop
0x180001dea  mov     rcx, rdi; bstrString
0x180001ded  call    cs:__imp_SysFreeString
0x180001df4  nop     dword ptr [rax+rax+00h]
0x180001df9  nop
0x180001dfa  mov     rcx, rbx; bstrString
0x180001dfd  call    cs:__imp_SysFreeString
0x180001e04  nop     dword ptr [rax+rax+00h]
0x180001e09  nop
0x180001e0a  mov     rcx, [rbp+arg_8]
0x180001e0e  test    rcx, rcx
0x180001e11  jz      short loc_180001E20
0x180001e13  mov     rax, [rcx]
0x180001e16  mov     rax, [rax+10h]
0x180001e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1f  nop
0x180001e20  jmp     loc_180002072
0x180001e25  mov     rcx, [rbp+arg_8]
0x180001e29  mov     rax, [rcx]
0x180001e2c  mov     [rsp+78h+ppv], r12
0x180001e31  xor     r9d, r9d
0x180001e34  xor     r8d, r8d
0x180001e37  mov     rdx, rdi
0x180001e3a  mov     rax, [rax+80h]
0x180001e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e46  mov     [rbp+arg_0], eax
0x180001e49  lea     r12, aDeletedefender; "DeleteDefenderWscInstance"
0x180001e50  lea     r13, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180001e57  test    eax, eax
0x180001e59  jns     loc_180001EED
0x180001e5f  call    cs:__imp_GetLastError
0x180001e66  nop     dword ptr [rax+rax+00h]
0x180001e6b  mov     r15d, eax
0x180001e6e  call    cs:__imp_CurrentIP
0x180001e75  nop     dword ptr [rax+rax+00h]
0x180001e7a  mov     r14, rax
0x180001e7d  mov     eax, [rbp+arg_0]
0x180001e80  mov     dword ptr [rsp+78h+ppv], eax
0x180001e84  lea     r9, aAntispywarepro; "AntiSpywareProduct.instanceGuid=\"{D68D"...
0x180001e8b  mov     r8d, 6Bh ; 'k'
0x180001e91  lea     rdx, aMrtgeneralizeD; "MRTGeneralize:%d - WARNING: Failed Dele"...
0x180001e98  mov     ecx, 3000000h; unsigned int
0x180001e9d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180001ea2  mov     [rsp+78h+var_28], 0
0x180001eaa  mov     [rsp+78h+var_30], 0
0x180001eb3  mov     dword ptr [rsp+78h+var_38], r15d
0x180001eb8  mov     [rsp+78h+var_40], r14
0x180001ebd  mov     [rsp+78h+var_48], r12
0x180001ec2  mov     [rsp+78h+var_50], r13
0x180001ec7  mov     dword ptr [rsp+78h+ppv], 6Bh ; 'k'
0x180001ecf  xor     r9d, r9d
0x180001ed2  lea     r8, aD; "D"
0x180001ed9  mov     edx, 0F0000h
0x180001ede  mov     rcx, rax
0x180001ee1  call    cs:__imp_WdsSetupLogMessageW
0x180001ee8  nop     dword ptr [rax+rax+00h]
0x180001eed  mov     rcx, [rbp+arg_8]
0x180001ef1  mov     rax, [rcx]
0x180001ef4  mov     [rsp+78h+ppv], 0
0x180001efd  xor     r9d, r9d
0x180001f00  xor     r8d, r8d
0x180001f03  mov     rdx, rsi
0x180001f06  mov     rax, [rax+80h]
0x180001f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f12  mov     [rbp+arg_0], eax
0x180001f15  test    eax, eax
0x180001f17  jns     loc_180001FAB
0x180001f1d  call    cs:__imp_GetLastError
0x180001f24  nop     dword ptr [rax+rax+00h]
0x180001f29  mov     r15d, eax
0x180001f2c  call    cs:__imp_CurrentIP
0x180001f33  nop     dword ptr [rax+rax+00h]
0x180001f38  mov     r14, rax
0x180001f3b  mov     eax, [rbp+arg_0]
0x180001f3e  mov     dword ptr [rsp+78h+ppv], eax
0x180001f42  lea     r9, aAntivirusprodu; "AntiVirusProduct.instanceGuid=\"{D68DDC"...
0x180001f49  mov     r8d, 74h ; 't'
0x180001f4f  lea     rdx, aMrtgeneralizeD; "MRTGeneralize:%d - WARNING: Failed Dele"...
0x180001f56  mov     ecx, 3000000h; unsigned int
0x180001f5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180001f60  mov     [rsp+78h+var_28], 0
0x180001f68  mov     [rsp+78h+var_30], 0
0x180001f71  mov     dword ptr [rsp+78h+var_38], r15d
0x180001f76  mov     [rsp+78h+var_40], r14
0x180001f7b  mov     [rsp+78h+var_48], r12
0x180001f80  mov     [rsp+78h+var_50], r13
0x180001f85  mov     dword ptr [rsp+78h+ppv], 74h ; 't'
0x180001f8d  xor     r9d, r9d
0x180001f90  lea     r8, aD; "D"
0x180001f97  mov     edx, 0F0000h
0x180001f9c  mov     rcx, rax
0x180001f9f  call    cs:__imp_WdsSetupLogMessageW
0x180001fa6  nop     dword ptr [rax+rax+00h]
0x180001fab  call    cs:__imp_GetLastError
0x180001fb2  nop     dword ptr [rax+rax+00h]
0x180001fb7  mov     r15d, eax
0x180001fba  call    cs:__imp_CurrentIP
0x180001fc1  nop     dword ptr [rax+rax+00h]
0x180001fc6  mov     r14, rax
0x180001fc9  mov     r8d, 7Ah ; 'z'
0x180001fcf  lea     rdx, aMrtgeneralizeD_2; "MRTGeneralize:%d - INFO: Finished attem"...
0x180001fd6  mov     ecx, 4000000h; unsigned int
0x180001fdb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180001fe0  mov     [rsp+78h+var_28], 0
0x180001fe8  mov     [rsp+78h+var_30], 0
0x180001ff1  mov     dword ptr [rsp+78h+var_38], r15d
0x180001ff6  mov     [rsp+78h+var_40], r14
0x180001ffb  mov     [rsp+78h+var_48], r12
0x180002000  mov     [rsp+78h+var_50], r13
0x180002005  mov     dword ptr [rsp+78h+ppv], 7Ah ; 'z'
0x18000200d  xor     r9d, r9d
0x180002010  lea     r8, aD; "D"
0x180002017  mov     edx, 0F0000h
0x18000201c  mov     rcx, rax
0x18000201f  call    cs:__imp_WdsSetupLogMessageW
0x180002026  nop     dword ptr [rax+rax+00h]
0x18000202b  nop
0x18000202c  mov     rcx, rsi; bstrString
0x18000202f  call    cs:__imp_SysFreeString
0x180002036  nop     dword ptr [rax+rax+00h]
0x18000203b  nop
0x18000203c  mov     rcx, rdi; bstrString
0x18000203f  call    cs:__imp_SysFreeString
0x180002046  nop     dword ptr [rax+rax+00h]
0x18000204b  nop
0x18000204c  mov     rcx, rbx; bstrString
0x18000204f  call    cs:__imp_SysFreeString
0x180002056  nop     dword ptr [rax+rax+00h]
0x18000205b  nop
0x18000205c  mov     rcx, [rbp+arg_8]
0x180002060  test    rcx, rcx
0x180002063  jz      short loc_180002072
0x180002065  mov     rax, [rcx]
0x180002068  mov     rax, [rax+10h]
0x18000206c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002071  nop
0x180002072  mov     rcx, [rbp+arg_10]
0x180002076  test    rcx, rcx
0x180002079  jz      short loc_180002088
0x18000207b  mov     rax, [rcx]
0x18000207e  mov     rax, [rax+10h]
0x180002082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002087  nop
0x180002088  add     rsp, 78h
0x18000208c  pop     r15
0x18000208e  pop     r14
0x180002090  pop     r13
0x180002092  pop     r12
0x180002094  pop     rdi
0x180002095  pop     rsi
0x180002096  pop     rbx
0x180002097  pop     rbp
0x180002098  retn
0x18000209a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800020a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800020a6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
