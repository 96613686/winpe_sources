# CRegAccount::GrantAccessToWmiNamespace(void *,ulong,ushort const *)

- ea: `0x1800251a8`
- end: `0x180025841`
- name: `?GrantAccessToWmiNamespace@CRegAccount@@SAJPEAXKPEBG@Z`
- size: `1689`
- prototype: `__int64 __fastcall(void *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023838`

## callees

- `0x180015050`
- `0x180021730`
- `0x180023a58`
- `0x1800251a8`
- `0x18003abe4`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x180065b60`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800256af`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800256af`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180025539`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180025539`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180025453`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800256fe`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180025453`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800256fe`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800255ef`
- `ADVAPI32!MakeAbsoluteSD` at `0x180025693`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800255ef`
- `ADVAPI32!MakeAbsoluteSD` at `0x180025693`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800256c9`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800256ed`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800256c9`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800256ed`
- `ole32!CoCreateInstance` at `0x18002527f`
- `ole32!CoCreateInstance` at `0x18002527f`
- `OLEAUT32!__imp_SysAllocString` at `0x180025293`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252f7`
- `OLEAUT32!__imp_SysAllocString` at `0x180025358`
- `OLEAUT32!__imp_SysAllocString` at `0x1800253e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025788`
- `OLEAUT32!__imp_SysAllocString` at `0x180025293`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252f7`
- `OLEAUT32!__imp_SysAllocString` at `0x180025358`
- `OLEAUT32!__imp_SysAllocString` at `0x1800253e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025788`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800254f3`
- `OLEAUT32!__imp_VariantInit` at `0x18002521d`
- `OLEAUT32!__imp_VariantInit` at `0x180025227`
- `OLEAUT32!__imp_VariantInit` at `0x18002521d`
- `OLEAUT32!__imp_VariantInit` at `0x180025227`
- `OLEAUT32!__imp_VariantClear` at `0x180025505`
- `OLEAUT32!__imp_VariantClear` at `0x180025505`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025430`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025734`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025430`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025734`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025444`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025764`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025444`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025764`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002571b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002571b`

## string_xrefs

- `0x180025243`: `Grant access to WMI namespace: `
- `0x180025479`: `Grant access to WMI namespace: `
- `0x180025252`: `GrantAccessToWmiNamespace`
- `0x180025488`: `GrantAccessToWmiNamespace`
- `0x1800252f0`: `__SystemSecurity`

## pseudocode

```c
__int64 __fastcall CRegAccount::GrantAccessToWmiNamespace(void *a1, unsigned int a2, OLECHAR *a3)
{
  OLECHAR *v4; // rsi
  OLECHAR *v5; // r12
  OLECHAR *v6; // r13
  OLECHAR *v7; // r15
  OLECHAR *v8; // rdi
  void *v9; // r14
  unsigned int Instance; // ebx
  BSTR v11; // rax
  BSTR v12; // rax
  void *v13; // rdi
  char *v15; // rax
  void *v16; // rbx
  void *v17; // rax
  DWORD SecurityDescriptorLength; // eax
  DWORD v19; // edi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r8
  BSTR v24; // rax
  BSTR v25; // [rsp+68h] [rbp-A0h]
  BSTR v26; // [rsp+70h] [rbp-98h]
  DWORD dwOwnerSize; // [rsp+78h] [rbp-90h] BYREF
  DWORD dwSaclSize; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD dwDaclSize; // [rsp+80h] [rbp-88h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+84h] [rbp-84h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+88h] [rbp-80h] BYREF
  WINBOOL bDaclPresent; // [rsp+8Ch] [rbp-7Ch] BYREF
  struct IUnknown *v33; // [rsp+90h] [rbp-78h] BYREF
  struct IUnknown *v34; // [rsp+98h] [rbp-70h] BYREF
  struct IUnknown *v35; // [rsp+A0h] [rbp-68h] BYREF
  struct IUnknown *v36; // [rsp+A8h] [rbp-60h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp-58h] BYREF
  struct IUnknown *ppv; // [rsp+B8h] [rbp-50h] BYREF
  PACL v39; // [rsp+C0h] [rbp-48h] BYREF
  void *v40; // [rsp+C8h] [rbp-40h] BYREF
  struct IUnknown *v41; // [rsp+D0h] [rbp-38h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+D8h] [rbp-30h] BYREF
  void *ppvData; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v44; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  void *v46; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v47; // [rsp+170h] [rbp+68h]
  OLECHAR *psz; // [rsp+178h] [rbp+70h]
  DWORD dwBufferLength; // [rsp+180h] [rbp+78h] BYREF

  psz = a3;
  v47 = a2;
  v46 = a1;
  ppv = 0;
  v33 = 0;
  v4 = 0;
  v34 = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v41 = 0;
  v7 = 0;
  v36 = 0;
  v8 = 0;
  v9 = 0;
  pDacl = 0;
  v39 = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  v40 = 0;
  VariantInit(&pvarg);
  VariantInit(&v44);
  if ( !a1 || !psz )
  {
    Instance = -2147024809;
    goto LABEL_24;
  }
  CSetupLogging::Log(1, "GrantAccessToWmiNamespace", 0, "Grant access to WMI namespace: ", psz);
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)&ppv);
  if ( !Instance )
  {
    v25 = SysAllocString(psz);
    if ( !v25 )
    {
      Instance = -2147024882;
      v4 = 0;
      goto LABEL_24;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IUnknown **))ppv->lpVtbl[1].QueryInterface)(
                 ppv,
                 v25,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 &v33);
    if ( Instance )
    {
LABEL_23:
      v4 = v25;
      goto LABEL_24;
    }
    v11 = SysAllocString(L"__SystemSecurity");
    v7 = v11;
    if ( !v11 )
    {
LABEL_8:
      Instance = -2147024882;
      goto LABEL_23;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, _QWORD, struct IUnknown **, _QWORD))v33->lpVtbl[2].QueryInterface)(
                 v33,
                 v11,
                 0,
                 0,
                 &v34,
                 0);
    if ( Instance )
      goto LABEL_23;
    if ( !v34 )
      goto LABEL_11;
    v12 = SysAllocString(L"GetSD");
    v6 = v12;
    if ( !v12 )
      goto LABEL_8;
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, struct IUnknown **, _QWORD))v34->lpVtbl[6].AddRef)(
                 v34,
                 v12,
                 0,
                 &v41,
                 0);
    if ( Instance )
      goto LABEL_23;
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, OLECHAR *, _QWORD, _QWORD, _QWORD, struct IUnknown **, _QWORD))v33->lpVtbl[8].QueryInterface)(
                 v33,
                 v7,
                 v6,
                 0,
                 0,
                 0,
                 &v36,
                 0);
    if ( Instance )
      goto LABEL_23;
    if ( !v36 )
    {
LABEL_11:
      Instance = -2147467261;
      goto LABEL_23;
    }
    v26 = SysAllocString(L"SD");
    if ( !v26 )
    {
      Instance = -2147024882;
      v8 = 0;
      goto LABEL_23;
    }
    ((void (__fastcall *)(struct IUnknown *, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))v36->lpVtbl[1].AddRef)(
      v36,
      v26,
      0,
      &pvarg,
      0,
      0);
    dwBufferLength = *(_DWORD *)(pvarg.llVal + 24);
    Instance = SafeArrayAccessData(pvarg.parray, &ppvData);
    if ( !Instance )
    {
      v13 = ppvData;
      Instance = SafeArrayUnaccessData(pvarg.parray);
      if ( !Instance )
      {
        dwBufferLength = GetSecurityDescriptorLength(v13);
        if ( dwBufferLength && GetSecurityDescriptorDacl(v13, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          Instance = CRegAccount::DoesAccessExist(pDacl, &v46, 1, 0x20u, &bDaclPresent);
          if ( Instance )
            goto LABEL_22;
          if ( bDaclPresent )
            goto LABEL_22;
          Instance = CRegAccount::AddAccess(&pDacl, &v46, 1, v47, 0, 2, &v39);
          if ( Instance )
            goto LABEL_22;
          MakeAbsoluteSD(
            v13,
            0,
            &dwAbsoluteSecurityDescriptorSize,
            0,
            &dwDaclSize,
            0,
            &dwSaclSize,
            0,
            &dwOwnerSize,
            0,
            &dwPrimaryGroupSize);
          v15 = (char *)MemAllocClear(dwAbsoluteSecurityDescriptorSize + dwDaclSize
                                                                       + dwSaclSize
                                                                       + dwPrimaryGroupSize
                                                                       + dwOwnerSize);
          v16 = v15;
          if ( !v15 )
            goto LABEL_30;
          if ( MakeAbsoluteSD(
                 v13,
                 v15,
                 &dwAbsoluteSecurityDescriptorSize,
                 (PACL)&v15[dwAbsoluteSecurityDescriptorSize],
                 &dwDaclSize,
                 (PACL)&v15[dwDaclSize + dwAbsoluteSecurityDescriptorSize],
                 &dwSaclSize,
                 &v15[dwAbsoluteSecurityDescriptorSize + dwSaclSize + dwDaclSize],
                 &dwOwnerSize,
                 &v15[dwAbsoluteSecurityDescriptorSize + dwDaclSize + dwSaclSize + dwOwnerSize],
                 &dwPrimaryGroupSize)
            && SetSecurityDescriptorDacl(v16, 1, v39, 0) )
          {
            dwBufferLength = 0;
            MakeSelfRelativeSD(v16, 0, &dwBufferLength);
            v17 = MemAllocClear(dwBufferLength);
            v9 = v17;
            if ( !v17 )
            {
LABEL_30:
              Instance = -2147024882;
              goto LABEL_22;
            }
            if ( MakeSelfRelativeSD(v16, v17, &dwBufferLength) )
            {
              SecurityDescriptorLength = GetSecurityDescriptorLength(v9);
              v19 = SecurityDescriptorLength;
              dwBufferLength = SecurityDescriptorLength;
              if ( SecurityDescriptorLength )
              {
                Vector = SafeArrayCreateVector(0x11u, 0, SecurityDescriptorLength);
                v21 = Vector;
                if ( Vector )
                {
                  Instance = SafeArrayAccessData(Vector, &v40);
                  if ( Instance )
                    goto LABEL_22;
                  if ( v19 )
                  {
                    v22 = 0;
                    v23 = v19;
                    do
                    {
                      *((_BYTE *)v40 + v22) = *((_BYTE *)v9 + v22);
                      ++v22;
                      --v23;
                    }
                    while ( v23 );
                  }
                  Instance = SafeArrayUnaccessData(v21);
                  if ( Instance )
                    goto LABEL_22;
                  v44.llVal = (LONGLONG)v21;
                  v44.vt = 8209;
                  v24 = SysAllocString(L"SetSD");
                  v5 = v24;
                  if ( v24 )
                  {
                    v8 = v26;
                    Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, struct IUnknown **, _QWORD))v34->lpVtbl[6].AddRef)(
                                 v34,
                                 v24,
                                 0,
                                 &v35,
                                 0);
                    if ( !Instance )
                    {
                      Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, VARIANTARG *, _DWORD))v35->lpVtbl[1].Release)(
                                   v35,
                                   v26,
                                   0,
                                   &v44,
                                   v44.vt);
                      if ( !Instance )
                        Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, OLECHAR *, _QWORD, _QWORD, struct IUnknown *, _QWORD, _QWORD))v33->lpVtbl[8].QueryInterface)(
                                     v33,
                                     v7,
                                     v5,
                                     0,
                                     0,
                                     v35,
                                     0,
                                     0);
                    }
                    goto LABEL_23;
                  }
                }
                goto LABEL_30;
              }
            }
          }
        }
        Instance = GetLastWin32Error();
      }
    }
LABEL_22:
    v8 = v26;
    goto LABEL_23;
  }
LABEL_24:
  CSetupLogging::Log(Instance, "GrantAccessToWmiNamespace", 0, "Grant access to WMI namespace: ", psz);
  ReleaseInterface(v33);
  ReleaseInterface(ppv);
  ReleaseInterface(v34);
  ReleaseInterface(v35);
  ReleaseInterface(v41);
  ReleaseInterface(v36);
  SysFreeString(v4);
  SysFreeString(v7);
  SysFreeString(v5);
  SysFreeString(v6);
  SysFreeString(v8);
  MemFree(v9);
  VariantClear(&pvarg);
  MemFree(v39);
  return Instance;
}

```

## disassembly

```asm
0x1800251a8  mov     rax, rsp
0x1800251ab  mov     [rax+18h], r8
0x1800251af  mov     [rax+10h], edx
0x1800251b2  mov     [rax+8], rcx
0x1800251b6  push    rbp
0x1800251b7  push    rbx
0x1800251b8  push    rsi
0x1800251b9  push    rdi
0x1800251ba  push    r12
0x1800251bc  push    r13
0x1800251be  push    r14
0x1800251c0  push    r15
0x1800251c2  lea     rbp, [rax-58h]
0x1800251c6  sub     rsp, 118h
0x1800251cd  xor     eax, eax
0x1800251cf  mov     rbx, rcx
0x1800251d2  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1800251d6  mov     [rbp+50h+var_A0], rax
0x1800251da  mov     [rbp+50h+var_C8], rax
0x1800251de  mov     esi, eax
0x1800251e0  mov     [rbp+50h+var_C0], rax
0x1800251e4  mov     r12d, eax
0x1800251e7  mov     [rbp+50h+var_B8], rax
0x1800251eb  mov     r13d, eax
0x1800251ee  mov     [rbp+50h+var_88], rax
0x1800251f2  mov     r15d, eax
0x1800251f5  mov     [rbp+50h+var_B0], rax
0x1800251f9  mov     edi, eax
0x1800251fb  mov     r14d, eax
0x1800251fe  mov     [rbp+50h+pDacl], rax
0x180025202  mov     [rbp+50h+var_98], rax
0x180025206  mov     [rsp+150h+dwAbsoluteSecurityDescriptorSize], eax
0x18002520a  mov     [rsp+150h+dwDaclSize], eax
0x18002520e  mov     [rsp+150h+dwSaclSize], eax
0x180025212  mov     [rsp+150h+dwOwnerSize], eax
0x180025216  mov     [rbp+50h+dwPrimaryGroupSize], eax
0x180025219  mov     [rbp+50h+var_90], rax
0x18002521d  call    cs:__imp_VariantInit
0x180025223  lea     rcx, [rbp+50h+var_70]; pvarg
0x180025227  call    cs:__imp_VariantInit
0x18002522d  test    rbx, rbx
0x180025230  jz      loc_180025837
0x180025236  mov     rax, [rbp+50h+psz]
0x18002523a  test    rax, rax
0x18002523d  jz      loc_180025837
0x180025243  lea     r9, aGrantAccessToW; "Grant access to WMI namespace: "
0x18002524a  mov     [rsp+150h+ppv], rax; unsigned __int16 *
0x18002524f  xor     r8d, r8d; unsigned int
0x180025252  lea     rdx, aGrantaccesstow; "GrantAccessToWmiNamespace"
0x180025259  lea     ecx, [r14+1]; int
0x18002525d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180025262  lea     rax, [rbp+50h+var_A0]
0x180025266  xor     edx, edx; pUnkOuter
0x180025268  lea     r9, IID_IWbemLocator; riid
0x18002526f  mov     [rsp+150h+ppv], rax; ppv
0x180025274  lea     r8d, [r14+1]; dwClsContext
0x180025278  lea     rcx, CLSID_WbemLocator; rclsid
0x18002527f  call    cs:__imp_CoCreateInstance
0x180025285  mov     ebx, eax
0x180025287  test    eax, eax
0x180025289  jnz     loc_180025475
0x18002528f  mov     rcx, [rbp+50h+psz]; psz
0x180025293  call    cs:__imp_SysAllocString
0x180025299  mov     [rsp+150h+var_F0], rax
0x18002529e  mov     rdx, rax
0x1800252a1  test    rax, rax
0x1800252a4  jnz     short loc_1800252B3
0x1800252a6  mov     ebx, 8007000Eh
0x1800252ab  mov     rsi, rax
0x1800252ae  jmp     loc_180025475
0x1800252b3  mov     rcx, [rbp+50h+var_A0]
0x1800252b7  lea     r8, [rbp+50h+var_C8]
0x1800252bb  mov     [rsp+150h+lpdwOwnerSize], r8
0x1800252c0  xor     r9d, r9d
0x1800252c3  mov     [rsp+150h+pOwner], rsi
0x1800252c8  xor     r8d, r8d
0x1800252cb  mov     [rsp+150h+lpdwSaclSize], rsi
0x1800252d0  mov     rax, [rcx]
0x1800252d3  mov     dword ptr [rsp+150h+pSacl], esi
0x1800252d7  mov     [rsp+150h+ppv], rsi
0x1800252dc  mov     rax, [rax+18h]
0x1800252e0  call    cs:__guard_dispatch_icall_fptr
0x1800252e6  mov     ebx, eax
0x1800252e8  test    eax, eax
0x1800252ea  jnz     loc_180025470
0x1800252f0  lea     rcx, psz; "__SystemSecurity"
0x1800252f7  call    cs:__imp_SysAllocString
0x1800252fd  mov     r15, rax
0x180025300  test    rax, rax
0x180025303  jnz     short loc_18002530F
0x180025305  mov     ebx, 8007000Eh
0x18002530a  jmp     loc_180025470
0x18002530f  mov     rcx, [rbp+50h+var_C8]
0x180025313  lea     rdx, [rbp+50h+var_C0]
0x180025317  mov     [rsp+150h+pSacl], rsi
0x18002531c  xor     r9d, r9d
0x18002531f  mov     [rsp+150h+ppv], rdx
0x180025324  xor     r8d, r8d
0x180025327  mov     rdx, r15
0x18002532a  mov     rax, [rcx]
0x18002532d  mov     rax, [rax+30h]
0x180025331  call    cs:__guard_dispatch_icall_fptr
0x180025337  mov     ebx, eax
0x180025339  test    eax, eax
0x18002533b  jnz     loc_180025470
0x180025341  cmp     [rbp+50h+var_C0], rsi
0x180025345  jnz     short loc_180025351
0x180025347  mov     ebx, 80004003h
0x18002534c  jmp     loc_180025470
0x180025351  lea     rcx, aGetsd; "GetSD"
0x180025358  call    cs:__imp_SysAllocString
0x18002535e  mov     r13, rax
0x180025361  test    rax, rax
0x180025364  jz      short loc_180025305
0x180025366  mov     rcx, [rbp+50h+var_C0]
0x18002536a  lea     r9, [rbp+50h+var_88]
0x18002536e  xor     r8d, r8d
0x180025371  mov     [rsp+150h+ppv], rsi
0x180025376  mov     rdx, r13
0x180025379  mov     rax, [rcx]
0x18002537c  mov     rax, [rax+98h]
0x180025383  call    cs:__guard_dispatch_icall_fptr
0x180025389  mov     ebx, eax
0x18002538b  test    eax, eax
0x18002538d  jnz     loc_180025470
0x180025393  mov     rcx, [rbp+50h+var_C8]
0x180025397  lea     rdx, [rbp+50h+var_B0]
0x18002539b  mov     [rsp+150h+pOwner], rsi
0x1800253a0  xor     r9d, r9d
0x1800253a3  mov     [rsp+150h+lpdwSaclSize], rdx
0x1800253a8  mov     r8, r13
0x1800253ab  mov     [rsp+150h+pSacl], rsi
0x1800253b0  mov     rdx, r15
0x1800253b3  mov     rax, [rcx]
0x1800253b6  mov     [rsp+150h+ppv], rsi
0x1800253bb  mov     rax, [rax+0C0h]
0x1800253c2  call    cs:__guard_dispatch_icall_fptr
0x1800253c8  mov     ebx, eax
0x1800253ca  test    eax, eax
0x1800253cc  jnz     loc_180025470
0x1800253d2  cmp     [rbp+50h+var_B0], rsi
0x1800253d6  jz      loc_180025347
0x1800253dc  lea     rcx, aSd_0; "SD"
0x1800253e3  call    cs:__imp_SysAllocString
0x1800253e9  mov     qword ptr [rsp+150h+var_E8], rax
0x1800253ee  mov     rdx, rax
0x1800253f1  test    rax, rax
0x1800253f4  jnz     short loc_180025400
0x1800253f6  mov     ebx, 8007000Eh
0x1800253fb  mov     rdi, rax
0x1800253fe  jmp     short loc_180025470
0x180025400  mov     rcx, [rbp+50h+var_B0]
0x180025404  lea     r9, [rbp+50h+pvarg]
0x180025408  mov     [rsp+150h+pSacl], rsi
0x18002540d  xor     r8d, r8d
0x180025410  mov     [rsp+150h+ppv], rsi
0x180025415  mov     rax, [rcx]
0x180025418  mov     rax, [rax+20h]
0x18002541c  call    cs:__guard_dispatch_icall_fptr
0x180025422  mov     rcx, qword ptr [rbp+50h+pvarg+8]; psa
0x180025426  lea     rdx, [rbp+50h+ppvData]; ppvData
0x18002542a  mov     eax, [rcx+18h]
0x18002542d  mov     [rbp+50h+dwBufferLength], eax
0x180025430  call    cs:__imp_SafeArrayAccessData
0x180025436  mov     ebx, eax
0x180025438  test    eax, eax
0x18002543a  jnz     short loc_18002546B
0x18002543c  mov     rcx, qword ptr [rbp+50h+pvarg+8]; psa
0x180025440  mov     rdi, [rbp+50h+ppvData]
0x180025444  call    cs:__imp_SafeArrayUnaccessData
0x18002544a  mov     ebx, eax
0x18002544c  test    eax, eax
0x18002544e  jnz     short loc_18002546B
0x180025450  mov     rcx, rdi; pSecurityDescriptor
0x180025453  call    cs:__imp_GetSecurityDescriptorLength
0x180025459  mov     [rbp+50h+dwBufferLength], eax
0x18002545c  test    eax, eax
0x18002545e  jnz     loc_18002552A
0x180025464  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180025469  mov     ebx, eax
0x18002546b  mov     rdi, qword ptr [rsp+150h+var_E8]
0x180025470  mov     rsi, [rsp+150h+var_F0]
0x180025475  mov     rax, [rbp+50h+psz]
0x180025479  lea     r9, aGrantAccessToW; "Grant access to WMI namespace: "
0x180025480  xor     r8d, r8d; unsigned int
0x180025483  mov     [rsp+150h+ppv], rax; unsigned __int16 *
0x180025488  lea     rdx, aGrantaccesstow; "GrantAccessToWmiNamespace"
0x18002548f  mov     ecx, ebx; int
0x180025491  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180025496  mov     rcx, [rbp+50h+var_C8]; struct IUnknown *
0x18002549a  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18002549f  mov     rcx, [rbp+50h+var_A0]; struct IUnknown *
0x1800254a3  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800254a8  mov     rcx, [rbp+50h+var_C0]; struct IUnknown *
0x1800254ac  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800254b1  mov     rcx, [rbp+50h+var_B8]; struct IUnknown *
0x1800254b5  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800254ba  mov     rcx, [rbp+50h+var_88]; struct IUnknown *
0x1800254be  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800254c3  mov     rcx, [rbp+50h+var_B0]; struct IUnknown *
0x1800254c7  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800254cc  mov     rcx, rsi; bstrString
0x1800254cf  call    cs:__imp_SysFreeString
0x1800254d5  mov     rcx, r15; bstrString
0x1800254d8  call    cs:__imp_SysFreeString
0x1800254de  mov     rcx, r12; bstrString
0x1800254e1  call    cs:__imp_SysFreeString
0x1800254e7  mov     rcx, r13; bstrString
0x1800254ea  call    cs:__imp_SysFreeString
0x1800254f0  mov     rcx, rdi; bstrString
0x1800254f3  call    cs:__imp_SysFreeString
0x1800254f9  mov     rcx, r14; lpMem
0x1800254fc  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180025501  lea     rcx, [rbp+50h+pvarg]; pvarg
0x180025505  call    cs:__imp_VariantClear
0x18002550b  mov     rcx, [rbp+50h+var_98]; lpMem
0x18002550f  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180025514  mov     eax, ebx
0x180025516  add     rsp, 118h
0x18002551d  pop     r15
0x18002551f  pop     r14
0x180025521  pop     r13
0x180025523  pop     r12
0x180025525  pop     rdi
0x180025526  pop     rsi
0x180025527  pop     rbx
0x180025528  pop     rbp
0x180025529  retn
0x18002552a  lea     r9, [rbp+50h+bDaclDefaulted]; lpbDaclDefaulted
0x18002552e  mov     rcx, rdi; pSecurityDescriptor
0x180025531  lea     r8, [rbp+50h+pDacl]; pDacl
0x180025535  lea     rdx, [rbp+50h+bDaclPresent]; lpbDaclPresent
0x180025539  call    cs:__imp_GetSecurityDescriptorDacl
0x18002553f  test    eax, eax
0x180025541  jz      loc_180025464
0x180025547  mov     rcx, [rbp+50h+pDacl]; pAcl
0x18002554b  lea     rax, [rbp+50h+bDaclPresent]
0x18002554f  mov     r9d, 20h ; ' '; unsigned int
0x180025555  mov     [rsp+150h+ppv], rax; int *
0x18002555a  lea     rdx, [rbp+50h+arg_0]; void **
0x18002555e  lea     r8d, [r9-1Fh]; int
0x180025562  call    ?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z; CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)
0x180025567  mov     ebx, eax
0x180025569  test    eax, eax
0x18002556b  jnz     loc_18002546B
0x180025571  cmp     [rbp+50h+bDaclPresent], esi
0x180025574  jnz     loc_18002546B
0x18002557a  mov     r9d, [rbp+50h+arg_8]; unsigned int
0x18002557e  lea     rax, [rbp+50h+var_98]
0x180025582  mov     [rsp+150h+lpdwSaclSize], rax; struct _ACL **
0x180025587  lea     r8d, [rbx+1]; int
0x18002558b  mov     byte ptr [rsp+150h+pSacl], 2; char
0x180025590  lea     rdx, [rbp+50h+arg_0]; void **
0x180025594  lea     rcx, [rbp+50h+pDacl]; struct _ACL **
0x180025598  mov     [rsp+150h+ppv], rsi; int *
0x18002559d  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)
0x1800255a2  mov     ebx, eax
0x1800255a4  test    eax, eax
0x1800255a6  jnz     loc_18002546B
0x1800255ac  lea     rax, [rbp+50h+dwPrimaryGroupSize]
0x1800255b0  xor     r9d, r9d; pDacl
0x1800255b3  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x1800255b8  lea     r8, [rsp+150h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800255bd  mov     [rsp+150h+pPrimaryGroup], rsi; pPrimaryGroup
0x1800255c2  lea     rax, [rsp+150h+dwOwnerSize]
0x1800255c7  mov     [rsp+150h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800255cc  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800255ce  mov     [rsp+150h+pOwner], rsi; pOwner
0x1800255d3  lea     rax, [rsp+150h+dwSaclSize]
0x1800255d8  mov     [rsp+150h+lpdwSaclSize], rax; lpdwSaclSize
0x1800255dd  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x1800255e0  lea     rax, [rsp+150h+dwDaclSize]
0x1800255e5  mov     [rsp+150h+pSacl], rsi; pSacl
0x1800255ea  mov     [rsp+150h+ppv], rax; lpdwDaclSize
0x1800255ef  call    cs:__imp_MakeAbsoluteSD
0x1800255f5  mov     ecx, [rsp+150h+dwOwnerSize]
0x1800255f9  add     ecx, [rbp+50h+dwPrimaryGroupSize]
0x1800255fc  add     ecx, [rsp+150h+dwSaclSize]
0x180025600  add     ecx, [rsp+150h+dwDaclSize]
0x180025604  add     ecx, [rsp+150h+dwAbsoluteSecurityDescriptorSize]; unsigned __int64
0x180025608  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18002560d  mov     rbx, rax
0x180025610  test    rax, rax
0x180025613  jnz     short loc_18002561F
0x180025615  mov     ebx, 8007000Eh
0x18002561a  jmp     loc_18002546B
0x18002561f  mov     r9d, [rsp+150h+dwAbsoluteSecurityDescriptorSize]
0x180025624  mov     edx, [rsp+150h+dwDaclSize]
0x180025628  mov     ecx, [rsp+150h+dwSaclSize]
0x18002562c  lea     r11, [rax+r9]
0x180025630  mov     eax, [rsp+150h+dwOwnerSize]
0x180025634  add     eax, ecx
0x180025636  lea     r10d, [rdx+r9]
0x18002563a  add     eax, edx
0x18002563c  lea     r8d, [rcx+rdx]
0x180025640  add     eax, r9d
0x180025643  lea     rcx, [rbp+50h+dwPrimaryGroupSize]
0x180025647  mov     [rsp+50h], rcx; lpdwPrimaryGroupSize
0x18002564c  add     rax, rbx
0x18002564f  mov     [rsp+150h+pPrimaryGroup], rax; pPrimaryGroup
  ... truncated ...
```
