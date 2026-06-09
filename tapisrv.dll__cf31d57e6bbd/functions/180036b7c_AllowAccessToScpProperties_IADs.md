# AllowAccessToScpProperties(IADs *)

- ea: `0x180036b7c`
- end: `0x1800370df`
- name: `?AllowAccessToScpProperties@@YAJPEAUIADs@@@Z`
- size: `1379`
- prototype: `__int64 __fastcall(struct IADs *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180037344`

## callees

- `0x180001600`
- `0x180036b7c`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180037088`
- `KERNEL32!LocalFree` at `0x1800370a6`
- `KERNEL32!LocalFree` at `0x180037088`
- `KERNEL32!LocalFree` at `0x1800370a6`
- `KERNEL32!GetLastError` at `0x180036ff1`
- `KERNEL32!GetLastError` at `0x180036ff1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036d61`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036d8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036d61`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036d8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036c39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036c8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036c39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036c8a`
- `ADVAPI32!FreeSid` at `0x180037097`
- `ADVAPI32!FreeSid` at `0x1800370b5`
- `ADVAPI32!FreeSid` at `0x180037097`
- `ADVAPI32!FreeSid` at `0x1800370b5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180036c23`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180036c74`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180036c23`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180036c74`
- `OLEAUT32!__imp_VariantInit` at `0x180036baf`
- `OLEAUT32!__imp_VariantInit` at `0x180036baf`
- `OLEAUT32!__imp_VariantClear` at `0x180036c9c`
- `OLEAUT32!__imp_VariantClear` at `0x1800370bf`
- `OLEAUT32!__imp_VariantClear` at `0x180036c9c`
- `OLEAUT32!__imp_VariantClear` at `0x1800370bf`

## string_xrefs

- `0x180036cf1`: `Couldn't get IADsSecurityDescriptor: 0x%x\n`
- `0x180036fd2`: `Couldn't get DACL: 0x%x\n`
- `0x180036ca9`: `nTSecurityDescriptor`
- `0x180036f6e`: `nTSecurityDescriptor`
- `0x180036fdb`: `Get nTSecurityDescriptor failed: 0x%x\n`
- `0x180036fc6`: `Couldn't create ACEs: 0x%x\n`

## pseudocode

```c
__int64 __fastcall AllowAccessToScpProperties(struct IADs *a1)
{
  int v2; // eax
  int v3; // ebx
  const char *v4; // rdx
  HRESULT (__stdcall *Put)(IADs *, BSTR, VARIANT); // rax
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v8; // [rsp+68h] [rbp-98h] BYREF
  __int64 v9; // [rsp+70h] [rbp-90h] BYREF
  __int64 v10; // [rsp+78h] [rbp-88h] BYREF
  __int64 v11; // [rsp+80h] [rbp-80h] BYREF
  __int64 v12; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-70h] BYREF
  PSID Sid; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR v15; // [rsp+A0h] [rbp-60h] BYREF
  PSID pSid; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v18; // [rsp+D0h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+F0h] [rbp-10h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+F8h] [rbp-8h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  ppv = 0;
  v8 = 0;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Sid = 0;
  StringSid = 0;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 256;
  pSid = 0;
  v15 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, &Sid)
    || !ConvertSidToStringSidW(Sid, &StringSid)
    || !AllocateAndInitializeSid(&v20, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !ConvertSidToStringSidW(pSid, &v15) )
  {
    v3 = GetLastError() | 0x10000000;
    goto LABEL_30;
  }
  VariantClear(&pvarg);
  v2 = ((__int64 (__fastcall *)(struct IADs *, const wchar_t *, VARIANTARG *))a1->lpVtbl->Get)(
         a1,
         L"nTSecurityDescriptor",
         &pvarg);
  v3 = v2;
  if ( v2 < 0 || pvarg.vt != 9 )
  {
    v4 = "Get nTSecurityDescriptor failed: 0x%x\n";
    goto LABEL_27;
  }
  v2 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
         pvarg.llVal,
         &IID_IADsSecurityDescriptor,
         &v12);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "Couldn't get IADsSecurityDescriptor: 0x%x\n";
LABEL_27:
    TRACELogPrint(65538, v4, (unsigned int)v2);
    goto LABEL_30;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 152LL))(v12, &v11);
  if ( v3 < 0
    || (v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(v11, &IID_IADsAccessControlList, &v10), v3 < 0) )
  {
    TRACELogPrint(65538, "Couldn't get DACL: 0x%x\n", (unsigned int)v3);
  }
  else
  {
    v3 = CoCreateInstance(&CLSID_AccessControlEntry, 0, 1u, &IID_IADsAccessControlEntry, &ppv);
    if ( v3 < 0 || (v3 = CoCreateInstance(&CLSID_AccessControlEntry, 0, 1u, &IID_IADsAccessControlEntry, &v8), v3 < 0) )
    {
      TRACELogPrint(65538, "Couldn't create ACEs: 0x%x\n", (unsigned int)v3);
    }
    else
    {
      (*(void (__fastcall **)(LPVOID, LPWSTR))(*(_QWORD *)ppv + 160LL))(ppv, StringSid);
      (*(void (__fastcall **)(LPVOID, LPWSTR))(*(_QWORD *)v8 + 160LL))(v8, v15);
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 64LL))(ppv, 4045341183LL);
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v8 + 64LL))(v8, 2147614868LL);
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 80LL))(ppv, 5);
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v8 + 80LL))(v8, 5);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, 0);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 96LL))(v8, 0);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, 0);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 128LL))(ppv, 0);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 128LL))(v8, 0);
      v3 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IDispatch, &v9);
      if ( v3 < 0 || (v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 88LL))(v10, v9), v3 < 0) )
      {
        TRACELogPrint(65538, "Couldn't add first ACE: 0x%x\n", (unsigned int)v3);
      }
      else
      {
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v9 = 0;
        v3 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v8)(v8, &IID_IDispatch, &v9);
        if ( v3 < 0 || (v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 88LL))(v10, v9), v3 < 0) )
        {
          TRACELogPrint(65538, "Couldn't add second ACE: 0x%x\n", (unsigned int)v3);
        }
        else
        {
          v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 160LL))(v12, v11);
          if ( v3 >= 0 )
          {
            Put = a1->lpVtbl->Put;
            v18 = pvarg;
            v3 = ((__int64 (__fastcall *)(struct IADs *, const wchar_t *, VARIANTARG *))Put)(
                   a1,
                   L"nTSecurityDescriptor",
                   &v18);
            if ( v3 >= 0 )
              v3 = ((__int64 (__fastcall *)(struct IADs *))a1->lpVtbl->SetInfo)(a1);
          }
        }
      }
    }
  }
LABEL_30:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    FreeSid(Sid);
  if ( v15 )
    LocalFree(v15);
  if ( pSid )
    FreeSid(pSid);
  VariantClear(&pvarg);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180036b7c  push    rbp
0x180036b7e  push    rbx
0x180036b7f  push    rsi
0x180036b80  push    rdi
0x180036b81  lea     rbp, [rsp-18h]
0x180036b86  sub     rsp, 118h
0x180036b8d  mov     rax, cs:__security_cookie
0x180036b94  xor     rax, rsp
0x180036b97  mov     [rbp+30h+var_30], rax
0x180036b9b  mov     rdi, rcx
0x180036b9e  xorps   xmm0, xmm0
0x180036ba1  xor     eax, eax
0x180036ba3  lea     rcx, [rbp+30h+pvarg]; pvarg
0x180036ba7  movups  xmmword ptr [rbp+30h+pvarg], xmm0
0x180036bab  mov     qword ptr [rbp+30h+pvarg+10h], rax
0x180036baf  call    cs:__imp_VariantInit
0x180036bb5  xor     esi, esi
0x180036bb7  mov     word ptr [rbp+30h+pIdentifierAuthority.Value+4], 500h
0x180036bbd  lea     rax, [rbp+30h+Sid]
0x180036bc1  mov     [rbp+30h+var_A8], rsi
0x180036bc5  mov     [rsp+130h+pSid], rax; pSid
0x180036bca  lea     rcx, [rbp+30h+pIdentifierAuthority]; pIdentifierAuthority
0x180036bce  mov     [rsp+130h+nSubAuthority7], esi; nSubAuthority7
0x180036bd2  xor     r9d, r9d; nSubAuthority1
0x180036bd5  mov     [rsp+130h+nSubAuthority6], esi; nSubAuthority6
0x180036bd9  lea     r8d, [rsi+6]; nSubAuthority0
0x180036bdd  mov     [rsp+130h+nSubAuthority5], esi; nSubAuthority5
0x180036be1  mov     dl, 1; nSubAuthorityCount
0x180036be3  mov     [rsp+130h+nSubAuthority4], esi; nSubAuthority4
0x180036be7  mov     [rsp+130h+nSubAuthority3], esi; nSubAuthority3
0x180036beb  mov     [rsp+130h+nSubAuthority2], esi; nSubAuthority2
0x180036bef  mov     [rsp+130h+var_B8], rsi
0x180036bf4  mov     [rbp+30h+var_B0], rsi
0x180036bf8  mov     [rsp+130h+ppv], rsi
0x180036bfd  mov     [rsp+130h+var_C8], rsi
0x180036c02  mov     [rsp+130h+var_C0], rsi
0x180036c07  mov     dword ptr [rbp+30h+pIdentifierAuthority.Value], esi
0x180036c0a  mov     [rbp+30h+Sid], rsi
0x180036c0e  mov     [rbp+30h+StringSid], rsi
0x180036c12  mov     dword ptr [rbp+30h+var_38.Value], esi
0x180036c15  mov     word ptr [rbp+30h+var_38.Value+4], 100h
0x180036c1b  mov     [rbp+30h+var_88], rsi
0x180036c1f  mov     [rbp+30h+var_90], rsi
0x180036c23  call    cs:__imp_AllocateAndInitializeSid
0x180036c29  test    eax, eax
0x180036c2b  jz      loc_180036FF1
0x180036c31  mov     rcx, [rbp+30h+Sid]; Sid
0x180036c35  lea     rdx, [rbp+30h+StringSid]; StringSid
0x180036c39  call    cs:__imp_ConvertSidToStringSidW
0x180036c3f  test    eax, eax
0x180036c41  jz      loc_180036FF1
0x180036c47  lea     rax, [rbp+30h+var_88]
0x180036c4b  xor     r9d, r9d; nSubAuthority1
0x180036c4e  mov     [rsp+130h+pSid], rax; pSid
0x180036c53  lea     rcx, [rbp+30h+var_38]; pIdentifierAuthority
0x180036c57  mov     [rsp+130h+nSubAuthority7], esi; nSubAuthority7
0x180036c5b  xor     r8d, r8d; nSubAuthority0
0x180036c5e  mov     [rsp+130h+nSubAuthority6], esi; nSubAuthority6
0x180036c62  mov     dl, 1; nSubAuthorityCount
0x180036c64  mov     [rsp+130h+nSubAuthority5], esi; nSubAuthority5
0x180036c68  mov     [rsp+130h+nSubAuthority4], esi; nSubAuthority4
0x180036c6c  mov     [rsp+130h+nSubAuthority3], esi; nSubAuthority3
0x180036c70  mov     [rsp+130h+nSubAuthority2], esi; nSubAuthority2
0x180036c74  call    cs:__imp_AllocateAndInitializeSid
0x180036c7a  test    eax, eax
0x180036c7c  jz      loc_180036FF1
0x180036c82  mov     rcx, [rbp+30h+var_88]; Sid
0x180036c86  lea     rdx, [rbp+30h+var_90]; StringSid
0x180036c8a  call    cs:__imp_ConvertSidToStringSidW
0x180036c90  test    eax, eax
0x180036c92  jz      loc_180036FF1
0x180036c98  lea     rcx, [rbp+30h+pvarg]; pvarg
0x180036c9c  call    cs:__imp_VariantClear
0x180036ca2  mov     rax, [rdi]
0x180036ca5  lea     r8, [rbp+30h+pvarg]
0x180036ca9  lea     rdx, aNtsecuritydesc; "nTSecurityDescriptor"
0x180036cb0  mov     rcx, rdi
0x180036cb3  mov     rax, [rax+78h]
0x180036cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cbc  mov     ebx, eax
0x180036cbe  test    eax, eax
0x180036cc0  js      loc_180036FDB
0x180036cc6  cmp     word ptr [rbp+30h+pvarg], 9
0x180036ccb  jnz     loc_180036FDB
0x180036cd1  mov     rcx, qword ptr [rbp+30h+pvarg+8]
0x180036cd5  lea     r8, [rbp+30h+var_A8]
0x180036cd9  lea     rdx, IID_IADsSecurityDescriptor
0x180036ce0  mov     rax, [rcx]
0x180036ce3  mov     rax, [rax]
0x180036ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ceb  mov     ebx, eax
0x180036ced  test    eax, eax
0x180036cef  jns     short loc_180036CFD
0x180036cf1  lea     rdx, aCouldnTGetIads; "Couldn't get IADsSecurityDescriptor: 0x"...
0x180036cf8  jmp     loc_180036FE2
0x180036cfd  mov     rcx, [rbp+30h+var_A8]
0x180036d01  lea     rdx, [rbp+30h+var_B0]
0x180036d05  mov     rax, [rcx]
0x180036d08  mov     rax, [rax+98h]
0x180036d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d14  mov     ebx, eax
0x180036d16  test    eax, eax
0x180036d18  js      loc_180036FCF
0x180036d1e  mov     rcx, [rbp+30h+var_B0]
0x180036d22  lea     r8, [rsp+130h+var_B8]
0x180036d27  lea     rdx, IID_IADsAccessControlList
0x180036d2e  mov     rax, [rcx]
0x180036d31  mov     rax, [rax]
0x180036d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d39  mov     ebx, eax
0x180036d3b  test    eax, eax
0x180036d3d  js      loc_180036FCF
0x180036d43  xor     edx, edx; pUnkOuter
0x180036d45  lea     rax, [rsp+130h+ppv]
0x180036d4a  lea     r9, IID_IADsAccessControlEntry; riid
0x180036d51  mov     qword ptr [rsp+130h+nSubAuthority2], rax; ppv
0x180036d56  lea     rcx, CLSID_AccessControlEntry; rclsid
0x180036d5d  lea     r8d, [rdx+1]; dwClsContext
0x180036d61  call    cs:__imp_CoCreateInstance
0x180036d67  mov     ebx, eax
0x180036d69  test    eax, eax
0x180036d6b  js      loc_180036FC3
0x180036d71  xor     edx, edx; pUnkOuter
0x180036d73  lea     rax, [rsp+130h+var_C8]
0x180036d78  lea     r9, IID_IADsAccessControlEntry; riid
0x180036d7f  mov     qword ptr [rsp+130h+nSubAuthority2], rax; ppv
0x180036d84  lea     rcx, CLSID_AccessControlEntry; rclsid
0x180036d8b  lea     r8d, [rdx+1]; dwClsContext
0x180036d8f  call    cs:__imp_CoCreateInstance
0x180036d95  mov     ebx, eax
0x180036d97  test    eax, eax
0x180036d99  js      loc_180036FC3
0x180036d9f  mov     rcx, [rsp+130h+ppv]
0x180036da4  mov     rdx, [rbp+30h+StringSid]
0x180036da8  mov     rax, [rcx]
0x180036dab  mov     rax, [rax+0A0h]
0x180036db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036db7  mov     rcx, [rsp+130h+var_C8]
0x180036dbc  mov     rdx, [rbp+30h+var_90]
0x180036dc0  mov     rax, [rcx]
0x180036dc3  mov     rax, [rax+0A0h]
0x180036dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dcf  mov     rcx, [rsp+130h+ppv]
0x180036dd4  mov     edx, 0F11F01FFh
0x180036dd9  mov     rax, [rcx]
0x180036ddc  mov     rax, [rax+40h]
0x180036de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036de5  mov     rcx, [rsp+130h+var_C8]
0x180036dea  mov     edx, 80020094h
0x180036def  mov     rax, [rcx]
0x180036df2  mov     rax, [rax+40h]
0x180036df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dfb  mov     rcx, [rsp+130h+ppv]
0x180036e00  mov     edx, 5
0x180036e05  mov     rax, [rcx]
0x180036e08  mov     rax, [rax+50h]
0x180036e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e11  mov     rcx, [rsp+130h+var_C8]
0x180036e16  mov     edx, 5
0x180036e1b  mov     rax, [rcx]
0x180036e1e  mov     rax, [rax+50h]
0x180036e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e27  mov     rcx, [rsp+130h+ppv]
0x180036e2c  xor     edx, edx
0x180036e2e  mov     rax, [rcx]
0x180036e31  mov     rax, [rax+60h]
0x180036e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e3a  mov     rcx, [rsp+130h+var_C8]
0x180036e3f  xor     edx, edx
0x180036e41  mov     rax, [rcx]
0x180036e44  mov     rax, [rax+60h]
0x180036e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e4d  mov     rcx, [rsp+130h+ppv]
0x180036e52  xor     edx, edx
0x180036e54  mov     rax, [rcx]
0x180036e57  mov     rax, [rax+70h]
0x180036e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e60  mov     rcx, [rsp+130h+var_C8]
0x180036e65  xor     edx, edx
0x180036e67  mov     rax, [rcx]
0x180036e6a  mov     rax, [rax+70h]
0x180036e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e73  mov     rcx, [rsp+130h+ppv]
0x180036e78  xor     edx, edx
0x180036e7a  mov     rax, [rcx]
0x180036e7d  mov     rax, [rax+80h]
0x180036e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e89  mov     rcx, [rsp+130h+var_C8]
0x180036e8e  xor     edx, edx
0x180036e90  mov     rax, [rcx]
0x180036e93  mov     rax, [rax+80h]
0x180036e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e9f  mov     rcx, [rsp+130h+ppv]
0x180036ea4  lea     r8, [rsp+130h+var_C0]
0x180036ea9  lea     rdx, IID_IDispatch
0x180036eb0  mov     rax, [rcx]
0x180036eb3  mov     rax, [rax]
0x180036eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ebb  mov     ebx, eax
0x180036ebd  test    eax, eax
0x180036ebf  js      loc_180036FB7
0x180036ec5  mov     rcx, [rsp+130h+var_B8]
0x180036eca  mov     rdx, [rsp+130h+var_C0]
0x180036ecf  mov     rax, [rcx]
0x180036ed2  mov     rax, [rax+58h]
0x180036ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036edb  mov     ebx, eax
0x180036edd  test    eax, eax
0x180036edf  js      loc_180036FB7
0x180036ee5  mov     rcx, [rsp+130h+var_C0]
0x180036eea  test    rcx, rcx
0x180036eed  jz      short loc_180036EFB
0x180036eef  mov     rax, [rcx]
0x180036ef2  mov     rax, [rax+10h]
0x180036ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036efb  mov     rcx, [rsp+130h+var_C8]
0x180036f00  lea     r8, [rsp+130h+var_C0]
0x180036f05  mov     [rsp+130h+var_C0], rsi
0x180036f0a  lea     rdx, IID_IDispatch
0x180036f11  mov     rax, [rcx]
0x180036f14  mov     rax, [rax]
0x180036f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f1c  mov     ebx, eax
0x180036f1e  test    eax, eax
0x180036f20  js      loc_180036FAB
0x180036f26  mov     rcx, [rsp+130h+var_B8]
0x180036f2b  mov     rdx, [rsp+130h+var_C0]
0x180036f30  mov     rax, [rcx]
0x180036f33  mov     rax, [rax+58h]
0x180036f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f3c  mov     ebx, eax
0x180036f3e  test    eax, eax
0x180036f40  js      short loc_180036FAB
0x180036f42  mov     rcx, [rbp+30h+var_A8]
0x180036f46  mov     rdx, [rbp+30h+var_B0]
0x180036f4a  mov     rax, [rcx]
0x180036f4d  mov     rax, [rax+0A0h]
0x180036f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f59  mov     ebx, eax
0x180036f5b  test    eax, eax
0x180036f5d  js      loc_180036FFD
0x180036f63  mov     rax, [rdi]
0x180036f66  lea     r8, [rbp+30h+var_60]
0x180036f6a  movups  xmm0, xmmword ptr [rbp+30h+pvarg]
0x180036f6e  lea     rdx, aNtsecuritydesc; "nTSecurityDescriptor"
0x180036f75  mov     rcx, rdi
0x180036f78  movsd   xmm1, qword ptr [rbp+30h+pvarg+10h]
0x180036f7d  mov     rax, [rax+80h]
0x180036f84  movaps  [rbp+30h+var_60], xmm0
0x180036f88  movsd   [rbp+30h+var_50], xmm1
0x180036f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f92  mov     ebx, eax
0x180036f94  test    eax, eax
0x180036f96  js      short loc_180036FFD
0x180036f98  mov     rax, [rdi]
0x180036f9b  mov     rcx, rdi
0x180036f9e  mov     rax, [rax+70h]
0x180036fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fa7  mov     ebx, eax
0x180036fa9  jmp     short loc_180036FFD
0x180036fab  mov     r8d, ebx
0x180036fae  lea     rdx, aCouldnTAddSeco; "Couldn't add second ACE: 0x%x\n"
0x180036fb5  jmp     short loc_180036FE5
0x180036fb7  mov     r8d, ebx
0x180036fba  lea     rdx, aCouldnTAddFirs; "Couldn't add first ACE: 0x%x\n"
0x180036fc1  jmp     short loc_180036FE5
0x180036fc3  mov     r8d, ebx
0x180036fc6  lea     rdx, aCouldnTCreateA; "Couldn't create ACEs: 0x%x\n"
0x180036fcd  jmp     short loc_180036FE5
0x180036fcf  mov     r8d, ebx
0x180036fd2  lea     rdx, aCouldnTGetDacl; "Couldn't get DACL: 0x%x\n"
0x180036fd9  jmp     short loc_180036FE5
0x180036fdb  lea     rdx, aGetNtsecurityd; "Get nTSecurityDescriptor failed: 0x%x\n"
0x180036fe2  mov     r8d, eax
0x180036fe5  mov     ecx, 10002h
0x180036fea  call    TRACELogPrint
0x180036fef  jmp     short loc_180036FFD
0x180036ff1  call    cs:__imp_GetLastError
0x180036ff7  mov     ebx, eax
0x180036ff9  bts     ebx, 1Ch
0x180036ffd  mov     rcx, [rsp+130h+var_C0]
0x180037002  test    rcx, rcx
0x180037005  jz      short loc_180037013
0x180037007  mov     rax, [rcx]
0x18003700a  mov     rax, [rax+10h]
0x18003700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037013  mov     rcx, [rsp+130h+ppv]
0x180037018  test    rcx, rcx
0x18003701b  jz      short loc_180037029
0x18003701d  mov     rax, [rcx]
0x180037020  mov     rax, [rax+10h]
0x180037024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037029  mov     rcx, [rsp+130h+var_C8]
0x18003702e  test    rcx, rcx
0x180037031  jz      short loc_18003703F
0x180037033  mov     rax, [rcx]
0x180037036  mov     rax, [rax+10h]
0x18003703a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003703f  mov     rcx, [rsp+130h+var_B8]
0x180037044  test    rcx, rcx
  ... truncated ...
```
