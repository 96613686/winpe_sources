# ClearAutologon(Microsoft::WRL::ComPtr<IUserData>)

- ea: `0x18005f594`
- end: `0x18005f804`
- name: `?ClearAutologon@@YAXV?$ComPtr@UIUserData@@@WRL@Microsoft@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800574f0`
- `0x18005a0d0`
- `0x18005ce90`
- `0x18005df50`
- `0x18005f3e8`

## callees

- `0x180024980`
- `0x1800256d8`
- `0x18005f594`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005f7b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f7b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005f767`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005f767`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18005f6a5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18005f70b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18005f6a5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18005f70b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f6c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f6c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f5e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f5e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f7cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f7cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f652`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f652`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005f755`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005f755`

## pseudocode

```c
LSTATUS __fastcall ClearAutologon(__int64 *a1)
{
  LSTATUS result; // eax
  LSTATUS ValueW; // eax
  bool v4; // sf
  HLOCAL v5; // rax
  void *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR StringSid[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR AccountName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+290h] [rbp+190h] BYREF

  hkey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             0,
             0x20019u,
             &hkey);
  if ( !result )
  {
    cbSid = 0;
    if ( (int)SHRegGetBOOL(hkey, 0, L"AutoAdminLogon", (int *)&cbSid) >= 0 && cbSid )
    {
      pcbData = 520;
      ValueW = RegGetValueW(hkey, 0, L"DefaultUserName", 2u, 0, AccountName, &pcbData);
      v4 = ValueW < 0;
      if ( ValueW )
      {
        AccountName[0] = 0;
        if ( ValueW > 0 )
          v4 = 1;
      }
      if ( !v4 )
      {
        cbSid = 0;
        cchReferencedDomainName = 0;
        pcbData = 0;
        if ( !LookupAccountNameW(0, AccountName, 0, &cbSid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&pcbData) )
        {
          if ( cbSid )
          {
            v5 = LocalAlloc(0, cbSid);
            v6 = v5;
            if ( v5 )
            {
              cchReferencedDomainName = 260;
              if ( LookupAccountNameW(
                     0,
                     AccountName,
                     v5,
                     &cbSid,
                     ReferencedDomainName,
                     &cchReferencedDomainName,
                     (PSID_NAME_USE)&pcbData) )
              {
                v7 = *a1;
                StringSid[0] = 0;
                v13 = 0;
                if ( (*(int (__fastcall **)(__int64, const WCHAR *, LPCWSTR *, int *))(*(_QWORD *)v7 + 88LL))(
                       v7,
                       L"SID",
                       StringSid,
                       &v13) >= 0 )
                {
                  Sid = 0;
                  if ( ConvertStringSidToSidW(StringSid[0], &Sid) )
                  {
                    if ( EqualSid(v6, Sid) )
                    {
                      v14 = 1;
                      _RegSetKeyValue(
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\ClearAutologon",
                        L"Enabled",
                        4u,
                        &v14,
                        4u);
                    }
                    LocalFree(Sid);
                  }
                  SysFreeString((BSTR)StringSid[0]);
                }
              }
              LocalFree(v6);
            }
          }
        }
      }
    }
    result = RegCloseKey(hkey);
  }
  v8 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return result;
}

```

## disassembly

```asm
0x18005f594  push    rbp
0x18005f596  push    rbx
0x18005f597  push    rsi
0x18005f598  push    rdi
0x18005f599  lea     rbp, [rsp-3B8h]
0x18005f5a1  sub     rsp, 4B8h
0x18005f5a8  mov     rax, cs:__security_cookie
0x18005f5af  xor     rax, rsp
0x18005f5b2  mov     [rbp+3D0h+var_30], rax
0x18005f5b9  mov     rdi, rcx
0x18005f5bc  lea     rax, [rsp+4D0h+hkey]
0x18005f5c1  xor     esi, esi
0x18005f5c3  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18005f5c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f5cf  mov     [rsp+4D0h+hkey], rsi
0x18005f5d4  mov     r9d, 20019h; samDesired
0x18005f5da  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005f5e1  xor     r8d, r8d; ulOptions
0x18005f5e4  call    cs:__imp_RegOpenKeyExW
0x18005f5ea  test    eax, eax
0x18005f5ec  jnz     loc_18005F7D2
0x18005f5f2  mov     rcx, [rsp+4D0h+hkey]; HKEY
0x18005f5f7  lea     r9, [rsp+4D0h+cbSid]; int *
0x18005f5fc  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x18005f603  mov     [rsp+4D0h+cbSid], esi
0x18005f607  xor     edx, edx; unsigned __int16 *
0x18005f609  call    ?SHRegGetBOOL@@YAJPEAUHKEY__@@PEBG1PEAH@Z; SHRegGetBOOL(HKEY__ *,ushort const *,ushort const *,int *)
0x18005f60e  test    eax, eax
0x18005f610  js      loc_18005F7C7
0x18005f616  cmp     [rsp+4D0h+cbSid], esi
0x18005f61a  jz      loc_18005F7C7
0x18005f620  mov     rcx, [rsp+4D0h+hkey]; hkey
0x18005f625  lea     rax, [rsp+4D0h+var_48C]
0x18005f62a  mov     [rsp+4D0h+pcbData], rax; pcbData
0x18005f62f  lea     r9d, [rsi+2]; dwFlags
0x18005f633  lea     rax, [rbp+3D0h+AccountName]
0x18005f637  mov     [rsp+4D0h+var_48C], 208h
0x18005f63f  mov     [rsp+4D0h+pvData], rax; pvData
0x18005f644  lea     r8, aDefaultusernam; "DefaultUserName"
0x18005f64b  xor     edx, edx; lpSubKey
0x18005f64d  mov     [rsp+4D0h+phkResult], rsi; pdwType
0x18005f652  call    cs:__imp_RegGetValueW
0x18005f658  test    eax, eax
0x18005f65a  jz      short loc_18005F66C
0x18005f65c  mov     [rbp+3D0h+AccountName], si
0x18005f660  jle     short loc_18005F66C
0x18005f662  movzx   eax, ax
0x18005f665  or      eax, 80070000h
0x18005f66a  test    eax, eax
0x18005f66c  js      loc_18005F7C7
0x18005f672  lea     rax, [rsp+4D0h+var_48C]
0x18005f677  mov     [rsp+4D0h+cbSid], esi
0x18005f67b  mov     [rsp+4D0h+pcbData], rax; peUse
0x18005f680  lea     r9, [rsp+4D0h+cbSid]; cbSid
0x18005f685  lea     rax, [rsp+4D0h+cchReferencedDomainName]
0x18005f68a  mov     [rsp+4D0h+cchReferencedDomainName], esi
0x18005f68e  mov     [rsp+4D0h+pvData], rax; cchReferencedDomainName
0x18005f693  lea     rdx, [rbp+3D0h+AccountName]; lpAccountName
0x18005f697  xor     r8d, r8d; Sid
0x18005f69a  mov     [rsp+4D0h+phkResult], rsi; ReferencedDomainName
0x18005f69f  xor     ecx, ecx; lpSystemName
0x18005f6a1  mov     [rsp+4D0h+var_48C], esi
0x18005f6a5  call    cs:__imp_LookupAccountNameW
0x18005f6ab  test    eax, eax
0x18005f6ad  jnz     loc_18005F7C7
0x18005f6b3  mov     eax, [rsp+4D0h+cbSid]
0x18005f6b7  test    eax, eax
0x18005f6b9  jz      loc_18005F7C7
0x18005f6bf  mov     edx, eax; uBytes
0x18005f6c1  xor     ecx, ecx; uFlags
0x18005f6c3  call    cs:__imp_LocalAlloc
0x18005f6c9  mov     rbx, rax
0x18005f6cc  test    rax, rax
0x18005f6cf  jz      loc_18005F7C7
0x18005f6d5  lea     rax, [rsp+4D0h+var_48C]
0x18005f6da  mov     [rsp+4D0h+cchReferencedDomainName], 104h
0x18005f6e2  mov     [rsp+4D0h+pcbData], rax; peUse
0x18005f6e7  lea     r9, [rsp+4D0h+cbSid]; cbSid
0x18005f6ec  lea     rax, [rsp+4D0h+cchReferencedDomainName]
0x18005f6f1  mov     r8, rbx; Sid
0x18005f6f4  mov     [rsp+4D0h+pvData], rax; cchReferencedDomainName
0x18005f6f9  lea     rdx, [rbp+3D0h+AccountName]; lpAccountName
0x18005f6fd  lea     rax, [rbp+3D0h+ReferencedDomainName]
0x18005f704  xor     ecx, ecx; lpSystemName
0x18005f706  mov     [rsp+4D0h+phkResult], rax; ReferencedDomainName
0x18005f70b  call    cs:__imp_LookupAccountNameW
0x18005f711  test    eax, eax
0x18005f713  jz      loc_18005F7BE
0x18005f719  mov     rcx, [rdi]
0x18005f71c  lea     r9, [rsp+4D0h+var_478]
0x18005f721  mov     [rsp+4D0h+StringSid], rsi
0x18005f726  lea     r8, [rsp+4D0h+StringSid]
0x18005f72b  mov     [rsp+4D0h+var_478], esi
0x18005f72f  lea     rdx, aSid_0; "SID"
0x18005f736  mov     rax, [rcx]
0x18005f739  mov     rax, [rax+58h]
0x18005f73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f742  test    eax, eax
0x18005f744  js      short loc_18005F7BE
0x18005f746  mov     rcx, [rsp+4D0h+StringSid]; StringSid
0x18005f74b  lea     rdx, [rsp+4D0h+Sid]; Sid
0x18005f750  mov     [rsp+4D0h+Sid], rsi
0x18005f755  call    cs:__imp_ConvertStringSidToSidW
0x18005f75b  test    eax, eax
0x18005f75d  jz      short loc_18005F7B3
0x18005f75f  mov     rdx, [rsp+4D0h+Sid]; pSid2
0x18005f764  mov     rcx, rbx; pSid1
0x18005f767  call    cs:__imp_EqualSid
0x18005f76d  test    eax, eax
0x18005f76f  jz      short loc_18005F7A8
0x18005f771  mov     r9d, 4; unsigned int
0x18005f777  mov     [rsp+4D0h+var_470], 1
0x18005f77f  lea     rax, [rsp+4D0h+var_470]
0x18005f784  mov     dword ptr [rsp+4D0h+pvData], r9d; unsigned int
0x18005f789  lea     r8, aEnabled; "Enabled"
0x18005f790  mov     [rsp+4D0h+phkResult], rax; void *
0x18005f795  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005f79c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18005f7a3  call    ?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z; _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18005f7a8  mov     rcx, [rsp+4D0h+Sid]; hMem
0x18005f7ad  call    cs:__imp_LocalFree
0x18005f7b3  mov     rcx, [rsp+4D0h+StringSid]; bstrString
0x18005f7b8  call    cs:__imp_SysFreeString
0x18005f7be  mov     rcx, rbx; hMem
0x18005f7c1  call    cs:__imp_LocalFree
0x18005f7c7  mov     rcx, [rsp+4D0h+hkey]; hKey
0x18005f7cc  call    cs:__imp_RegCloseKey
0x18005f7d2  mov     rcx, [rdi]
0x18005f7d5  test    rcx, rcx
0x18005f7d8  jz      short loc_18005F7E9
0x18005f7da  mov     [rdi], rsi
0x18005f7dd  mov     rax, [rcx]
0x18005f7e0  mov     rax, [rax+10h]
0x18005f7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7e9  mov     rcx, [rbp+3D0h+var_30]
0x18005f7f0  xor     rcx, rsp; StackCookie
0x18005f7f3  call    __security_check_cookie
0x18005f7f8  add     rsp, 4B8h
0x18005f7ff  pop     rdi
0x18005f800  pop     rsi
0x18005f801  pop     rbx
0x18005f802  pop     rbp
0x18005f803  retn
```
