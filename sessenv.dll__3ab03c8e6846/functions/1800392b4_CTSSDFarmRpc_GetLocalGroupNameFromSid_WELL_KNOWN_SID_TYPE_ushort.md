# CTSSDFarmRpc::GetLocalGroupNameFromSid(WELL_KNOWN_SID_TYPE,ushort * *)

- ea: `0x1800392b4`
- end: `0x1800394ab`
- name: `?GetLocalGroupNameFromSid@CTSSDFarmRpc@@AEAAJW4WELL_KNOWN_SID_TYPE@@PEAPEAG@Z`
- size: `503`
- prototype: `int(CTSSDFarmRpc *__hidden this, enum WELL_KNOWN_SID_TYPE, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003984c`
- `0x1800399a4`

## callees

- `0x180003f30`
- `0x1800392b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003933b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003938e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003941e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003933b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003938e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003941e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180039331`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180039331`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800392f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800393cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800393dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800392f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800393cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800393dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003948f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003948f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180039384`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180039414`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180039384`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180039414`

## string_xrefs

- `0x180039354`: `CreateWellKnownSid failed: 0x%x in %s`
- `0x1800393b7`: `LookupAccountSid failed: 0x%x in %s`
- `0x180039441`: `LookupAccountSid failed: 0x%x in %s`
- `0x18003930d`: `CTSSDFarmRpc::GetLocalGroupNameFromSid`
- `0x180039437`: `CTSSDFarmRpc::GetLocalGroupNameFromSid`
- `0x18003945e`: `CTSSDFarmRpc::GetLocalGroupNameFromSid`
- `0x180039306`: `LocalAlloc on pGroupSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::GetLocalGroupNameFromSid(
        CTSSDFarmRpc *this,
        enum WELL_KNOWN_SID_TYPE a2,
        unsigned __int16 **a3)
{
  HLOCAL v5; // rax
  void *v6; // r14
  unsigned int v7; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  WCHAR *v10; // rdi
  WCHAR *ReferencedDomainName; // rax
  WCHAR *v12; // rsi
  signed int v13; // eax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp+30h] BYREF
  int v18; // [rsp+84h] [rbp+34h]
  DWORD cchName; // [rsp+98h] [rbp+48h] BYREF

  v18 = HIDWORD(this);
  peUse = 0;
  cchName = 0;
  cbSid[0] = 68;
  cchReferencedDomainName = 0;
  v5 = LocalAlloc(0x40u, 0x44u);
  v6 = v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    _DbgPrintMessage(
      8,
      "LocalAlloc on pGroupSid failed: 0x%x in %s",
      2147942414LL,
      "CTSSDFarmRpc::GetLocalGroupNameFromSid");
    return v7;
  }
  if ( CreateWellKnownSid(a2, 0, v5, cbSid) )
    goto LABEL_13;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_13:
    if ( !LookupAccountSidW(0, v6, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024774 )
      {
        _DbgPrintMessage(8, "LookupAccountSid failed: 0x%x in %s", v7, "CTSSDFarmRpc::GetLocalGroupNameFromSid");
        return v7;
      }
    }
    v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchName);
    ReferencedDomainName = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
    v12 = ReferencedDomainName;
    if ( v10 && ReferencedDomainName )
    {
      v7 = 0;
      if ( LookupAccountSidW(0, v6, v10, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        goto LABEL_22;
      v13 = GetLastError();
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
      {
LABEL_22:
        *a3 = v10;
        goto LABEL_26;
      }
      _DbgPrintMessage(8, "LookupAccountSid failed: 0x%x in %s", v7, "CTSSDFarmRpc::GetLocalGroupNameFromSid");
    }
    else
    {
      v7 = -2147024882;
      _DbgPrintMessage(8, "LocalAlloc failed: 0x%x in %s", -2147024882, "CTSSDFarmRpc::GetLocalGroupNameFromSid");
      if ( !v10 )
        goto LABEL_25;
    }
    LocalFree(v10);
LABEL_25:
    if ( !v12 )
      return v7;
LABEL_26:
    LocalFree(v12);
    return v7;
  }
  _DbgPrintMessage(8, "CreateWellKnownSid failed: 0x%x in %s", v7, "CTSSDFarmRpc::GetLocalGroupNameFromSid");
  return v7;
}

```

## disassembly

```asm
0x1800392b4  mov     [rsp-28h+arg_8], rbx
0x1800392b9  mov     qword ptr [rsp-28h+arg_0], rcx
0x1800392be  push    rbp
0x1800392bf  push    rsi
0x1800392c0  push    rdi
0x1800392c1  push    r14
0x1800392c3  push    r15
0x1800392c5  mov     rbp, rsp
0x1800392c8  sub     rsp, 50h
0x1800392cc  mov     ebx, edx
0x1800392ce  mov     [rbp+var_10], 0
0x1800392d5  mov     edx, 44h ; 'D'; uBytes
0x1800392da  mov     [rbp+cchName], 0
0x1800392e1  mov     r15, r8
0x1800392e4  mov     [rbp+cbSid], edx
0x1800392e7  mov     [rbp+arg_0], 0
0x1800392ee  lea     esi, [rdx-4]
0x1800392f1  mov     ecx, esi; uFlags
0x1800392f3  call    cs:__imp_LocalAlloc
0x1800392f9  mov     r14, rax
0x1800392fc  test    rax, rax
0x1800392ff  jnz     short loc_180039326
0x180039301  mov     ebx, 8007000Eh
0x180039306  lea     rdx, aLocalallocOnPg; "LocalAlloc on pGroupSid failed: 0x%x in"...
0x18003930d  lea     r9, aCtssdfarmrpcGe_0; "CTSSDFarmRpc::GetLocalGroupNameFromSid"
0x180039314  mov     r8d, ebx
0x180039317  mov     ecx, 8; int
0x18003931c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039321  jmp     loc_180039495
0x180039326  lea     r9, [rbp+cbSid]; cbSid
0x18003932a  mov     r8, r14; pSid
0x18003932d  xor     edx, edx; DomainSid
0x18003932f  mov     ecx, ebx; WellKnownSidType
0x180039331  call    cs:__imp_CreateWellKnownSid
0x180039337  test    eax, eax
0x180039339  jnz     short loc_18003935D
0x18003933b  call    cs:__imp_GetLastError
0x180039341  mov     ebx, eax
0x180039343  test    eax, eax
0x180039345  jle     short loc_180039350
0x180039347  movzx   ebx, ax
0x18003934a  or      ebx, 80070000h
0x180039350  test    ebx, ebx
0x180039352  jns     short loc_18003935D
0x180039354  lea     rdx, aCreatewellknow; "CreateWellKnownSid failed: 0x%x in %s"
0x18003935b  jmp     short loc_18003930D
0x18003935d  lea     rax, [rbp+var_10]
0x180039361  xor     r8d, r8d; Name
0x180039364  mov     [rsp+50h+peUse], rax; peUse
0x180039369  lea     r9, [rbp+cchName]; cchName
0x18003936d  lea     rax, [rbp+arg_0]
0x180039371  mov     rdx, r14; Sid
0x180039374  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180039379  xor     ecx, ecx; lpSystemName
0x18003937b  mov     [rsp+50h+ReferencedDomainName], 0; ReferencedDomainName
0x180039384  call    cs:__imp_LookupAccountSidW
0x18003938a  test    eax, eax
0x18003938c  jnz     short loc_1800393C3
0x18003938e  call    cs:__imp_GetLastError
0x180039394  mov     ebx, eax
0x180039396  test    eax, eax
0x180039398  jle     short loc_1800393A3
0x18003939a  movzx   ebx, ax
0x18003939d  or      ebx, 80070000h
0x1800393a3  mov     ecx, 80000000h
0x1800393a8  lea     eax, [rbx+rcx]
0x1800393ab  test    ecx, eax
0x1800393ad  jnz     short loc_1800393C3
0x1800393af  cmp     ebx, 8007007Ah
0x1800393b5  jz      short loc_1800393C3
0x1800393b7  lea     rdx, aLookupaccounts_2; "LookupAccountSid failed: 0x%x in %s"
0x1800393be  jmp     loc_18003930D
0x1800393c3  mov     edx, [rbp+cchName]
0x1800393c6  mov     ecx, esi; uFlags
0x1800393c8  add     rdx, rdx; uBytes
0x1800393cb  call    cs:__imp_LocalAlloc
0x1800393d1  mov     edx, [rbp+arg_0]
0x1800393d4  mov     ecx, esi; uFlags
0x1800393d6  add     rdx, rdx; uBytes
0x1800393d9  mov     rdi, rax
0x1800393dc  call    cs:__imp_LocalAlloc
0x1800393e2  mov     rsi, rax
0x1800393e5  test    rdi, rdi
0x1800393e8  jz      short loc_180039459
0x1800393ea  test    rax, rax
0x1800393ed  jz      short loc_180039459
0x1800393ef  lea     rax, [rbp+var_10]
0x1800393f3  mov     r8, rdi; Name
0x1800393f6  mov     [rsp+50h+peUse], rax; peUse
0x1800393fb  lea     r9, [rbp+cchName]; cchName
0x1800393ff  lea     rax, [rbp+arg_0]
0x180039403  mov     rdx, r14; Sid
0x180039406  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003940b  xor     ecx, ecx; lpSystemName
0x18003940d  mov     [rsp+50h+ReferencedDomainName], rsi; ReferencedDomainName
0x180039412  xor     ebx, ebx
0x180039414  call    cs:__imp_LookupAccountSidW
0x18003941a  test    eax, eax
0x18003941c  jnz     short loc_180039454
0x18003941e  call    cs:__imp_GetLastError
0x180039424  mov     ebx, eax
0x180039426  test    eax, eax
0x180039428  jle     short loc_180039433
0x18003942a  movzx   ebx, ax
0x18003942d  or      ebx, 80070000h
0x180039433  test    ebx, ebx
0x180039435  jns     short loc_180039454
0x180039437  lea     r9, aCtssdfarmrpcGe_0; "CTSSDFarmRpc::GetLocalGroupNameFromSid"
0x18003943e  mov     r8d, ebx
0x180039441  lea     rdx, aLookupaccounts_2; "LookupAccountSid failed: 0x%x in %s"
0x180039448  mov     ecx, 8; int
0x18003944d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039452  jmp     short loc_18003947E
0x180039454  mov     [r15], rdi
0x180039457  jmp     short loc_18003948C
0x180039459  mov     ebx, 8007000Eh
0x18003945e  lea     r9, aCtssdfarmrpcGe_0; "CTSSDFarmRpc::GetLocalGroupNameFromSid"
0x180039465  mov     r8d, ebx
0x180039468  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x18003946f  mov     ecx, 8; int
0x180039474  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039479  test    rdi, rdi
0x18003947c  jz      short loc_180039487
0x18003947e  mov     rcx, rdi; hMem
0x180039481  call    cs:__imp_LocalFree
0x180039487  test    rsi, rsi
0x18003948a  jz      short loc_180039495
0x18003948c  mov     rcx, rsi; hMem
0x18003948f  call    cs:__imp_LocalFree
0x180039495  mov     eax, ebx
0x180039497  mov     rbx, [rsp+50h+arg_8]
0x18003949f  add     rsp, 50h
0x1800394a3  pop     r15
0x1800394a5  pop     r14
0x1800394a7  pop     rdi
0x1800394a8  pop     rsi
0x1800394a9  pop     rbp
0x1800394aa  retn
```
