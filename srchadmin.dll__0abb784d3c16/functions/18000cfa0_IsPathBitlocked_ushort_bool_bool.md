# IsPathBitlocked(ushort,bool *,bool *)

- ea: `0x18000cfa0`
- end: `0x18000d41b`
- name: `?IsPathBitlocked@@YAJGPEA_N0@Z`
- size: `1147`
- prototype: `__int64 __fastcall(unsigned __int16, bool *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001908c`
- `0x1800198d4`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18000687c`
- `0x18000cd60`
- `0x18000cdbc`
- `0x18000cfa0`
- `0x18000d4dc`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d236`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d236`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000d088`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000d088`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d148`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d148`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d0cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d0cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3db`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3db`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3f1`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1ad`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1f1`
- `OLEAUT32!__imp_VariantInit` at `0x18000d296`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1ad`
- `OLEAUT32!__imp_VariantInit` at `0x18000d1f1`
- `OLEAUT32!__imp_VariantInit` at `0x18000d296`
- `OLEAUT32!__imp_VariantClear` at `0x18000d261`
- `OLEAUT32!__imp_VariantClear` at `0x18000d271`
- `OLEAUT32!__imp_VariantClear` at `0x18000d38f`
- `OLEAUT32!__imp_VariantClear` at `0x18000d261`
- `OLEAUT32!__imp_VariantClear` at `0x18000d271`
- `OLEAUT32!__imp_VariantClear` at `0x18000d38f`

## string_xrefs

- `0x18000cfdf`: `\\.\root\CIMV2\Security\MicrosoftVolumeEncryption`
- `0x18000d012`: `__Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IsPathBitlocked(unsigned __int16 a1, bool *a2, bool *a3)
{
  unsigned __int16 v4; // r15
  int Error; // r12d
  unsigned int v6; // r15d
  LPVOID v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+78h] [rbp-88h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  BSTR v16; // [rsp+90h] [rbp-70h] BYREF
  BSTR v17; // [rsp+98h] [rbp-68h] BYREF
  BSTR v18; // [rsp+A0h] [rbp-60h] BYREF
  bool *v19; // [rsp+A8h] [rbp-58h]
  _BYTE szVolumeMountPoint[16]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szVolumeName; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v22[110]; // [rsp+C2h] [rbp-3Eh] BYREF

  v19 = a3;
  *a2 = 0;
  *a3 = 0;
  v4 = a1 - 32;
  if ( a1 <= 0x5Au )
    v4 = a1;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v18, L"\\\\.\\root\\CIMV2\\Security\\MicrosoftVolumeEncryption");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v17, L"Win32_EncryptableVolume");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v16, L"DeviceID");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"__Path");
  if ( !v18 || !v17 || !v16 || (Error = 0, !bstrString) )
    Error = -2147024882;
  szVolumeName = 0;
  memset_0(v22, 0, 0x62u);
  if ( Error < 0 )
  {
    v6 = 0;
  }
  else
  {
    wcscpy((wchar_t *)&szVolumeMountPoint[2], L":\\");
    *(_WORD *)szVolumeMountPoint = v4;
    v6 = 0;
    if ( !GetVolumeNameForVolumeMountPointW((LPCWSTR)szVolumeMountPoint, &szVolumeName, 0x32u) )
      Error = ResultFromKnownLastError();
  }
  v7 = 0;
  ppv = 0;
  if ( Error >= 0 )
  {
    Error = CoCreateInstance(&CLSID_WbemAdministrativeLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
    v7 = ppv;
  }
  pProxy = 0;
  if ( Error >= 0 )
  {
    Error = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v7 + 24LL))(
              v7,
              v18,
              0,
              0,
              0,
              128,
              0,
              0,
              &pProxy);
    if ( Error >= 0 )
      Error = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, 0, 6u, 3u, 0, 0);
  }
  v13 = 0;
  if ( Error >= 0 )
    Error = ((__int64 (__fastcall *)(IUnknown *, BSTR, __int64))pProxy->lpVtbl[6].QueryInterface)(pProxy, v17, 33);
  v10 = 0;
  if ( Error >= 0 )
  {
    *(_DWORD *)szVolumeMountPoint = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    while ( Error >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, _BYTE *))(*(_QWORD *)v13 + 32LL))(
             v13,
             0xFFFFFFFFLL,
             1,
             &v10,
             szVolumeMountPoint) )
      {
        goto LABEL_30;
      }
      VariantInit(&pvarg);
      Error = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v10 + 32LL))(
                v10,
                v16,
                0,
                &pvarg,
                0,
                0);
      if ( Error >= 0 && pvarg.vt == 8 && !(unsigned int)_o__wcsicmp(&szVolumeName, pvarg.llVal) )
      {
        VariantClear(&pvarg);
LABEL_30:
        if ( v10 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          Error = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v10 + 32LL))(
                    v10,
                    bstrString,
                    0,
                    &pvarg,
                    0,
                    0);
          *(_DWORD *)szVolumeMountPoint = 0;
          if ( Error >= 0 )
          {
            Error = CallWbemServicesMethod(
                      (struct IWbemServices *)pProxy,
                      pvarg.bstrVal,
                      L"GetLockStatus",
                      L"LockStatus",
                      (int *)szVolumeMountPoint);
            if ( Error >= 0 )
            {
              if ( *(_DWORD *)szVolumeMountPoint == 1 )
              {
                *a2 = 1;
                *v19 = 1;
              }
              else
              {
                *(_DWORD *)szVolumeMountPoint = 0;
                Error = CallWbemServicesMethod(
                          (struct IWbemServices *)pProxy,
                          pvarg.bstrVal,
                          L"GetEncryptionMethod",
                          L"EncryptionMethod",
                          (int *)szVolumeMountPoint);
                if ( Error >= 0 )
                {
                  if ( *(_DWORD *)szVolumeMountPoint )
                  {
                    *(_DWORD *)szVolumeMountPoint = 0;
                    Error = CallWbemServicesMethod(
                              (struct IWbemServices *)pProxy,
                              pvarg.bstrVal,
                              L"GetProtectionStatus",
                              L"ProtectionStatus",
                              (int *)szVolumeMountPoint);
                    if ( Error >= 0 && *(_DWORD *)szVolumeMountPoint == 1 )
                      *a2 = 1;
                  }
                }
              }
            }
          }
          VariantClear(&pvarg);
        }
        break;
      }
      v8 = v10;
      if ( v10 )
      {
        v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      VariantClear(&pvarg);
    }
  }
  if ( Error != -2147217394 )
    v6 = Error;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  SysFreeString(bstrString);
  SysFreeString(v16);
  SysFreeString(v17);
  SysFreeString(v18);
  return v6;
}

```

## disassembly

```asm
0x18000cfa0  mov     [rsp-8+arg_0], r12
0x18000cfa5  push    rbp
0x18000cfa6  push    r13
0x18000cfa8  push    r15
0x18000cfaa  lea     rbp, [rsp-40h]
0x18000cfaf  sub     rsp, 140h
0x18000cfb6  mov     rax, cs:__security_cookie
0x18000cfbd  xor     rax, rsp
0x18000cfc0  mov     [rbp+50h+var_20], rax
0x18000cfc4  mov     [rbp+50h+var_A8], r8
0x18000cfc8  mov     r13, rdx
0x18000cfcb  mov     byte ptr [rdx], 0
0x18000cfce  mov     byte ptr [r8], 0
0x18000cfd2  lea     r15d, [rcx-20h]
0x18000cfd6  cmp     cx, 5Ah ; 'Z'
0x18000cfda  cmovbe  r15w, cx
0x18000cfdf  lea     rdx, aRootCimv2Secur; "\\\\.\\root\\CIMV2\\Security\\Microsoft"...
0x18000cfe6  lea     rcx, [rbp+50h+var_B0]; this
0x18000cfea  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000cfef  nop
0x18000cff0  lea     rdx, aWin32Encryptab; "Win32_EncryptableVolume"
0x18000cff7  lea     rcx, [rbp+50h+var_B8]; this
0x18000cffb  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000d000  nop
0x18000d001  lea     rdx, aDeviceid; "DeviceID"
0x18000d008  lea     rcx, [rbp+50h+var_C0]; this
0x18000d00c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000d011  nop
0x18000d012  lea     rdx, aPath; "__Path"
0x18000d019  lea     rcx, [rbp+50h+bstrString]; this
0x18000d01d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000d022  nop
0x18000d023  cmp     [rbp+50h+var_B0], 0
0x18000d028  jz      short loc_18000D041
0x18000d02a  cmp     [rbp+50h+var_B8], 0
0x18000d02f  jz      short loc_18000D041
0x18000d031  cmp     [rbp+50h+var_C0], 0
0x18000d036  jz      short loc_18000D041
0x18000d038  xor     r12d, r12d
0x18000d03b  cmp     [rbp+50h+bstrString], r12
0x18000d03f  jnz     short loc_18000D047
0x18000d041  mov     r12d, 8007000Eh
0x18000d047  xor     eax, eax
0x18000d049  mov     [rbp+50h+szVolumeName], ax
0x18000d04d  xor     edx, edx; Val
0x18000d04f  lea     r8d, [rax+62h]; Size
0x18000d053  lea     rcx, [rbp+50h+var_8E]; void *
0x18000d057  call    memset_0
0x18000d05c  test    r12d, r12d
0x18000d05f  js      short loc_18000D09F
0x18000d061  mov     eax, dword ptr cs:asc_180036550+2; ":\\"
0x18000d067  mov     dword ptr [rbp+50h+szVolumeMountPoint+2], eax
0x18000d06a  movzx   eax, word ptr cs:asc_180036550+6; ""
0x18000d071  mov     [rbp+50h+var_9A], ax
0x18000d075  mov     [rbp+50h+szVolumeMountPoint], r15w
0x18000d07a  mov     r8d, 32h ; '2'; cchBufferLength
0x18000d080  lea     rdx, [rbp+50h+szVolumeName]; lpszVolumeName
0x18000d084  lea     rcx, [rbp+50h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18000d088  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000d08e  xor     r15d, r15d
0x18000d091  test    eax, eax
0x18000d093  jnz     short loc_18000D0A2
0x18000d095  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000d09a  mov     r12d, eax
0x18000d09d  jmp     short loc_18000D0A2
0x18000d09f  xor     r15d, r15d
0x18000d0a2  mov     rcx, r15
0x18000d0a5  mov     [rbp+50h+var_D0], rcx
0x18000d0a9  test    r12d, r12d
0x18000d0ac  js      short loc_18000D0D8
0x18000d0ae  lea     rax, [rbp+50h+var_D0]
0x18000d0b2  mov     [rsp+150h+ppv], rax; ppv
0x18000d0b7  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18000d0be  xor     edx, edx; pUnkOuter
0x18000d0c0  lea     r8d, [rdx+1]; dwClsContext
0x18000d0c4  lea     rcx, CLSID_WbemAdministrativeLocator; rclsid
0x18000d0cb  call    cs:__imp_CoCreateInstance
0x18000d0d1  mov     r12d, eax
0x18000d0d4  mov     rcx, [rbp+50h+var_D0]
0x18000d0d8  mov     [rsp+150h+pProxy], r15
0x18000d0dd  test    r12d, r12d
0x18000d0e0  js      short loc_18000D151
0x18000d0e2  mov     rax, [rcx]
0x18000d0e5  lea     rdx, [rsp+150h+pProxy]
0x18000d0ea  mov     [rsp+150h+var_110], rdx
0x18000d0ef  mov     qword ptr [rsp+150h+dwCapabilities], r15
0x18000d0f4  mov     [rsp+150h+pAuthInfo], r15
0x18000d0f9  mov     [rsp+150h+dwImpLevel], 80h
0x18000d101  mov     [rsp+150h+ppv], r15
0x18000d106  xor     r9d, r9d
0x18000d109  xor     r8d, r8d
0x18000d10c  mov     rdx, [rbp+50h+var_B0]
0x18000d110  mov     rax, [rax+18h]
0x18000d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d119  mov     r12d, eax
0x18000d11c  test    eax, eax
0x18000d11e  js      short loc_18000D151
0x18000d120  mov     [rsp+150h+dwCapabilities], r15d; dwCapabilities
0x18000d125  mov     [rsp+150h+pAuthInfo], r15; pAuthInfo
0x18000d12a  mov     [rsp+150h+dwImpLevel], 3; dwImpLevel
0x18000d132  mov     dword ptr [rsp+150h+ppv], 6; dwAuthnLevel
0x18000d13a  xor     r9d, r9d; pServerPrincName
0x18000d13d  xor     r8d, r8d; dwAuthzSvc
0x18000d140  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000d143  mov     rcx, [rsp+150h+pProxy]; pProxy
0x18000d148  call    cs:__imp_CoSetProxyBlanket
0x18000d14e  mov     r12d, eax
0x18000d151  mov     [rsp+150h+var_D8], r15
0x18000d156  test    r12d, r12d
0x18000d159  js      short loc_18000D187
0x18000d15b  mov     rcx, [rsp+150h+pProxy]
0x18000d160  mov     rax, [rcx]
0x18000d163  lea     rdx, [rsp+150h+var_D8]
0x18000d168  mov     [rsp+150h+ppv], rdx
0x18000d16d  xor     r9d, r9d
0x18000d170  lea     r8d, [r9+21h]
0x18000d174  mov     rdx, [rbp+50h+var_B8]
0x18000d178  mov     rax, [rax+90h]
0x18000d17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d184  mov     r12d, eax
0x18000d187  mov     [rsp+150h+var_100], r15
0x18000d18c  test    r12d, r12d
0x18000d18f  js      loc_18000D396
0x18000d195  mov     dword ptr [rbp+50h+szVolumeMountPoint], r15d
0x18000d199  xorps   xmm0, xmm0
0x18000d19c  xor     eax, eax
0x18000d19e  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x18000d1a3  mov     qword ptr [rsp+150h+pvarg+10h], rax
0x18000d1a8  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d1ad  call    cs:__imp_VariantInit
0x18000d1b3  test    r12d, r12d
0x18000d1b6  js      loc_18000D396
0x18000d1bc  mov     rcx, [rsp+150h+var_D8]
0x18000d1c1  mov     rax, [rcx]
0x18000d1c4  lea     rdx, [rbp+50h+szVolumeMountPoint]
0x18000d1c8  mov     [rsp+150h+ppv], rdx
0x18000d1cd  lea     r9, [rsp+150h+var_100]
0x18000d1d2  mov     r8d, 1
0x18000d1d8  or      edx, 0FFFFFFFFh
0x18000d1db  mov     rax, [rax+20h]
0x18000d1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1e4  test    eax, eax
0x18000d1e6  jnz     loc_18000D277
0x18000d1ec  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d1f1  call    cs:__imp_VariantInit
0x18000d1f7  mov     rcx, [rsp+150h+var_100]
0x18000d1fc  mov     rax, [rcx]
0x18000d1ff  mov     qword ptr [rsp+150h+dwImpLevel], r15
0x18000d204  mov     [rsp+150h+ppv], r15
0x18000d209  lea     r9, [rsp+150h+pvarg]
0x18000d20e  xor     r8d, r8d
0x18000d211  mov     rdx, [rbp+50h+var_C0]
0x18000d215  mov     rax, [rax+20h]
0x18000d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21e  mov     r12d, eax
0x18000d221  test    eax, eax
0x18000d223  js      short loc_18000D240
0x18000d225  cmp     word ptr [rsp+150h+pvarg], 8
0x18000d22b  jnz     short loc_18000D240
0x18000d22d  mov     rdx, qword ptr [rsp+150h+pvarg+8]
0x18000d232  lea     rcx, [rbp+50h+szVolumeName]
0x18000d236  call    cs:__imp__o__wcsicmp
0x18000d23c  test    eax, eax
0x18000d23e  jz      short loc_18000D26C
0x18000d240  mov     rcx, [rsp+150h+var_100]
0x18000d245  test    rcx, rcx
0x18000d248  jz      short loc_18000D25C
0x18000d24a  mov     [rsp+150h+var_100], r15
0x18000d24f  mov     rax, [rcx]
0x18000d252  mov     rax, [rax+10h]
0x18000d256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d25b  nop
0x18000d25c  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d261  call    cs:__imp_VariantClear
0x18000d267  jmp     loc_18000D1B3
0x18000d26c  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d271  call    cs:__imp_VariantClear
0x18000d277  cmp     [rsp+150h+var_100], r15
0x18000d27c  jz      loc_18000D396
0x18000d282  xorps   xmm0, xmm0
0x18000d285  xor     eax, eax
0x18000d287  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x18000d28c  mov     qword ptr [rsp+150h+pvarg+10h], rax
0x18000d291  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d296  call    cs:__imp_VariantInit
0x18000d29c  mov     rcx, [rsp+150h+var_100]
0x18000d2a1  mov     rax, [rcx]
0x18000d2a4  mov     qword ptr [rsp+150h+dwImpLevel], r15
0x18000d2a9  mov     [rsp+150h+ppv], r15
0x18000d2ae  lea     r9, [rsp+150h+pvarg]
0x18000d2b3  xor     r8d, r8d
0x18000d2b6  mov     rdx, [rbp+50h+bstrString]
0x18000d2ba  mov     rax, [rax+20h]
0x18000d2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c3  mov     r12d, eax
0x18000d2c6  mov     dword ptr [rbp+50h+szVolumeMountPoint], r15d
0x18000d2ca  test    eax, eax
0x18000d2cc  js      loc_18000D38A
0x18000d2d2  lea     rax, [rbp+50h+szVolumeMountPoint]
0x18000d2d6  mov     [rsp+150h+ppv], rax; int *
0x18000d2db  lea     r9, aLockstatus; "LockStatus"
0x18000d2e2  lea     r8, aGetlockstatus; "GetLockStatus"
0x18000d2e9  mov     rdx, qword ptr [rsp+150h+pvarg+8]; unsigned __int16 *
0x18000d2ee  mov     rcx, [rsp+150h+pProxy]; struct IWbemServices *
0x18000d2f3  call    ?CallWbemServicesMethod@@YAJPEAUIWbemServices@@PEAGPEBG2PEAJ@Z; CallWbemServicesMethod(IWbemServices *,ushort *,ushort const *,ushort const *,long *)
0x18000d2f8  mov     r12d, eax
0x18000d2fb  test    eax, eax
0x18000d2fd  js      loc_18000D38A
0x18000d303  cmp     dword ptr [rbp+50h+szVolumeMountPoint], 1
0x18000d307  jnz     short loc_18000D317
0x18000d309  mov     byte ptr [r13+0], 1
0x18000d30e  mov     rax, [rbp+50h+var_A8]
0x18000d312  mov     byte ptr [rax], 1
0x18000d315  jmp     short loc_18000D38A
0x18000d317  mov     dword ptr [rbp+50h+szVolumeMountPoint], r15d
0x18000d31b  lea     rax, [rbp+50h+szVolumeMountPoint]
0x18000d31f  mov     [rsp+150h+ppv], rax; int *
0x18000d324  lea     r9, aEncryptionmeth; "EncryptionMethod"
0x18000d32b  lea     r8, aGetencryptionm; "GetEncryptionMethod"
0x18000d332  mov     rdx, qword ptr [rsp+150h+pvarg+8]; unsigned __int16 *
0x18000d337  mov     rcx, [rsp+150h+pProxy]; struct IWbemServices *
0x18000d33c  call    ?CallWbemServicesMethod@@YAJPEAUIWbemServices@@PEAGPEBG2PEAJ@Z; CallWbemServicesMethod(IWbemServices *,ushort *,ushort const *,ushort const *,long *)
0x18000d341  mov     r12d, eax
0x18000d344  test    eax, eax
0x18000d346  js      short loc_18000D38A
0x18000d348  cmp     dword ptr [rbp+50h+szVolumeMountPoint], r15d
0x18000d34c  jz      short loc_18000D38A
0x18000d34e  mov     dword ptr [rbp+50h+szVolumeMountPoint], r15d
0x18000d352  lea     rax, [rbp+50h+szVolumeMountPoint]
0x18000d356  mov     [rsp+150h+ppv], rax; int *
0x18000d35b  lea     r9, aProtectionstat; "ProtectionStatus"
0x18000d362  lea     r8, aGetprotections; "GetProtectionStatus"
0x18000d369  mov     rdx, qword ptr [rsp+150h+pvarg+8]; unsigned __int16 *
0x18000d36e  mov     rcx, [rsp+150h+pProxy]; struct IWbemServices *
0x18000d373  call    ?CallWbemServicesMethod@@YAJPEAUIWbemServices@@PEAGPEBG2PEAJ@Z; CallWbemServicesMethod(IWbemServices *,ushort *,ushort const *,ushort const *,long *)
0x18000d378  mov     r12d, eax
0x18000d37b  test    eax, eax
0x18000d37d  js      short loc_18000D38A
0x18000d37f  cmp     dword ptr [rbp+50h+szVolumeMountPoint], 1
0x18000d383  jnz     short loc_18000D38A
0x18000d385  mov     byte ptr [r13+0], 1
0x18000d38a  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000d38f  call    cs:__imp_VariantClear
0x18000d395  nop
0x18000d396  cmp     r12d, 8004100Eh
0x18000d39d  cmovnz  r15d, r12d
0x18000d3a1  lea     rcx, [rsp+150h+var_100]
0x18000d3a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3ab  nop
0x18000d3ac  lea     rcx, [rsp+150h+var_D8]
0x18000d3b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3b6  nop
0x18000d3b7  lea     rcx, [rsp+150h+pProxy]
0x18000d3bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3c1  nop
0x18000d3c2  lea     rcx, [rbp+50h+var_D0]
0x18000d3c6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3cb  nop
0x18000d3cc  mov     rcx, [rbp+50h+bstrString]; bstrString
0x18000d3d0  call    cs:__imp_SysFreeString
0x18000d3d6  nop
0x18000d3d7  mov     rcx, [rbp+50h+var_C0]; bstrString
0x18000d3db  call    cs:__imp_SysFreeString
0x18000d3e1  nop
0x18000d3e2  mov     rcx, [rbp+50h+var_B8]; bstrString
0x18000d3e6  call    cs:__imp_SysFreeString
0x18000d3ec  nop
0x18000d3ed  mov     rcx, [rbp+50h+var_B0]; bstrString
0x18000d3f1  call    cs:__imp_SysFreeString
0x18000d3f7  mov     eax, r15d
0x18000d3fa  mov     rcx, [rbp+50h+var_20]
0x18000d3fe  xor     rcx, rsp; StackCookie
0x18000d401  call    __security_check_cookie
0x18000d406  mov     r12, [rsp+150h+arg_0]
0x18000d40e  add     rsp, 140h
0x18000d415  pop     r15
0x18000d417  pop     r13
0x18000d419  pop     rbp
0x18000d41a  retn
```
