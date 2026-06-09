# CRegAccount::CreateAutoGenRegKeyForSid(void *)

- ea: `0x1800229d4`
- end: `0x180022c1a`
- name: `?CreateAutoGenRegKeyForSid@CRegAccount@@SAJPEAX@Z`
- size: `582`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023838`
- `0x180039628`
- `0x1800396b4`

## callees

- `0x18000d56c`
- `0x180021730`
- `0x1800229d4`
- `0x18004bfdd`
- `0x18004d030`
- `0x18004d350`
- `0x18004d754`
- `0x18004eaa8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180022bca`
- `KERNEL32!LocalFree` at `0x180022bca`
- `ADVAPI32!RegCloseKey` at `0x180022b9d`
- `ADVAPI32!RegCloseKey` at `0x180022bac`
- `ADVAPI32!RegCloseKey` at `0x180022bbb`
- `ADVAPI32!RegCloseKey` at `0x180022b9d`
- `ADVAPI32!RegCloseKey` at `0x180022bac`
- `ADVAPI32!RegCloseKey` at `0x180022bbb`
- `ADVAPI32!RegCreateKeyExW` at `0x180022a75`
- `ADVAPI32!RegCreateKeyExW` at `0x180022add`
- `ADVAPI32!RegCreateKeyExW` at `0x180022a75`
- `ADVAPI32!RegCreateKeyExW` at `0x180022add`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180022b40`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180022b40`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022b67`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022b67`
- `ADVAPI32!RegSetKeySecurity` at `0x180022b7e`
- `ADVAPI32!RegSetKeySecurity` at `0x180022b7e`

## pseudocode

```c
__int64 __fastcall CRegAccount::CreateAutoGenRegKeyForSid(PSID Sid)
{
  PACL v2; // rdi
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  unsigned int LastWin32Error; // eax
  PACL pDacl; // [rsp+50h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-21h] BYREF
  HKEY v9; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-9h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+78h] [rbp-1h] BYREF
  void *lpMem[2]; // [rsp+A0h] [rbp+27h] BYREF
  PSID v14; // [rsp+B0h] [rbp+37h]

  phkResult = 0;
  hKey = 0;
  v9 = 0;
  StringSid = 0;
  pDacl = 0;
  v2 = 0;
  v14 = 0;
  *(_OWORD *)lpMem = 0;
  v3 = CRegInfo::OpenCurrentVersionKey((DWORD)&hKey, 0x20019u, 1, 1);
  if ( v3 )
    goto LABEL_16;
  v4 = RegCreateKeyExW(hKey, L"AutoGenKeys", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  if ( !v4 )
  {
    if ( ConvertSidToStringSidW_0(Sid, &StringSid) && StringSid )
    {
      v4 = RegCreateKeyExW(phkResult, StringSid, 0, 0, 0, 0x40000u, 0, &v9, 0);
      if ( v4 )
        goto LABEL_3;
      GetPrincipalSID((char *)L"system", lpMem);
      GetPrincipalSID((char *)L"administrators", &lpMem[1]);
      v14 = Sid;
      v3 = CRegAccount::AddAccess(0, lpMem, 3, 0xF003Fu, 0, 3, &pDacl);
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        LastWin32Error = GetLastWin32Error();
        v2 = pDacl;
LABEL_15:
        v3 = LastWin32Error;
        goto LABEL_16;
      }
      v2 = pDacl;
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
      {
        v4 = RegSetKeySecurity(v9, 4u, pSecurityDescriptor);
        if ( !v4 )
          goto LABEL_16;
        goto LABEL_3;
      }
    }
    LastWin32Error = GetLastWin32Error();
    goto LABEL_15;
  }
LABEL_3:
  v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 <= 0 )
    v3 = v4;
LABEL_16:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v9 )
    RegCloseKey(v9);
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringSid )
    LocalFree(StringSid);
  if ( lpMem[0] )
    MemFree(lpMem[0]);
  if ( lpMem[1] )
    MemFree(lpMem[1]);
  MemFree(v2);
  return v3;
}

```

## disassembly

```asm
0x1800229d4  mov     [rsp-8+arg_8], rbx
0x1800229d9  mov     [rsp-8+arg_10], rsi
0x1800229de  push    rbp
0x1800229df  push    rdi
0x1800229e0  push    r14
0x1800229e2  lea     rbp, [rsp-47h]
0x1800229e7  sub     rsp, 0C0h
0x1800229ee  mov     rax, cs:__security_cookie
0x1800229f5  xor     rax, rsp
0x1800229f8  mov     [rbp+57h+var_18], rax
0x1800229fc  xor     r14d, r14d
0x1800229ff  mov     rsi, rcx
0x180022a02  xorps   xmm0, xmm0
0x180022a05  mov     [rbp+57h+var_78], r14
0x180022a09  mov     edx, 20019h; samDesired
0x180022a0e  mov     [rbp+57h+hKey], r14
0x180022a12  lea     rcx, [rbp+57h+hKey]; dwOptions
0x180022a16  mov     [rbp+57h+var_70], r14
0x180022a1a  lea     r9d, [r14+1]; int
0x180022a1e  mov     [rbp+57h+StringSid], r14
0x180022a22  mov     r8d, r9d; int
0x180022a25  mov     [rbp+57h+pDacl], r14
0x180022a29  mov     edi, r14d
0x180022a2c  mov     [rbp+57h+var_20], r14
0x180022a30  movdqu  xmmword ptr [rbp+57h+lpMem], xmm0
0x180022a35  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z
0x180022a3a  mov     ebx, eax
0x180022a3c  test    eax, eax
0x180022a3e  jnz     loc_180022B94
0x180022a44  mov     rcx, [rbp+57h+hKey]; hKey
0x180022a48  lea     rax, [rbp+57h+var_78]
0x180022a4c  mov     [rsp+0D0h+lpdwDisposition], r14; lpdwDisposition
0x180022a51  lea     rdx, aAutogenkeys_0
0x180022a58  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180022a5d  xor     r9d, r9d; lpClass
0x180022a60  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180022a65  xor     r8d, r8d; Reserved
0x180022a68  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x180022a70  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x180022a75  call    cs:__imp_RegCreateKeyExW
0x180022a7b  test    eax, eax
0x180022a7d  jz      short loc_180022A92
0x180022a7f  movzx   ebx, ax
0x180022a82  or      ebx, 80070000h
0x180022a88  test    eax, eax
0x180022a8a  cmovle  ebx, eax
0x180022a8d  jmp     loc_180022B94
0x180022a92  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180022a96  mov     rcx, rsi; Sid
0x180022a99  call    ConvertSidToStringSidW_0
0x180022a9e  test    eax, eax
0x180022aa0  jz      loc_180022B8D
0x180022aa6  mov     rdx, [rbp+57h+StringSid]; lpSubKey
0x180022aaa  test    rdx, rdx
0x180022aad  jz      loc_180022B8D
0x180022ab3  mov     rcx, [rbp+57h+var_78]; hKey
0x180022ab7  lea     rax, [rbp+57h+var_70]
0x180022abb  mov     [rsp+0D0h+lpdwDisposition], r14; lpdwDisposition
0x180022ac0  xor     r9d, r9d; lpClass
0x180022ac3  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180022ac8  xor     r8d, r8d; Reserved
0x180022acb  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180022ad0  mov     [rsp+0D0h+samDesired], 40000h; samDesired
0x180022ad8  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x180022add  call    cs:__imp_RegCreateKeyExW
0x180022ae3  test    eax, eax
0x180022ae5  jnz     short loc_180022A7F
0x180022ae7  lea     rdx, [rbp+57h+lpMem]; void **
0x180022aeb  lea     rcx, aSystem_0
0x180022af2  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z
0x180022af7  lea     rdx, [rbp+57h+lpMem+8]; void **
0x180022afb  lea     rcx, aAdministrators
0x180022b02  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z
0x180022b07  lea     rax, [rbp+57h+pDacl]
0x180022b0b  mov     [rbp+57h+var_20], rsi
0x180022b0f  mov     [rsp+0D0h+lpSecurityAttributes], rax; struct _ACL **
0x180022b14  lea     rdx, [rbp+57h+lpMem]; void **
0x180022b18  mov     byte ptr [rsp+0D0h+samDesired], 3; char
0x180022b1d  mov     r9d, 0F003Fh; unsigned int
0x180022b23  mov     r8d, 3; int
0x180022b29  mov     qword ptr [rsp+0D0h+dwOptions], r14; int *
0x180022b2e  xor     ecx, ecx; struct _ACL **
0x180022b30  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z
0x180022b35  mov     edx, 1; dwRevision
0x180022b3a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180022b3e  mov     ebx, eax
0x180022b40  call    cs:__imp_InitializeSecurityDescriptor
0x180022b46  test    eax, eax
0x180022b48  jnz     short loc_180022B55
0x180022b4a  call    ?GetLastWin32Error@@YAJXZ
0x180022b4f  mov     rdi, [rbp+57h+pDacl]
0x180022b53  jmp     short loc_180022B92
0x180022b55  mov     rdi, [rbp+57h+pDacl]
0x180022b59  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180022b5d  xor     r9d, r9d; bDaclDefaulted
0x180022b60  mov     r8, rdi; pDacl
0x180022b63  lea     edx, [r9+1]; bDaclPresent
0x180022b67  call    cs:__imp_SetSecurityDescriptorDacl
0x180022b6d  test    eax, eax
0x180022b6f  jz      short loc_180022B8D
0x180022b71  mov     rcx, [rbp+57h+var_70]; hKey
0x180022b75  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180022b79  mov     edx, 4; SecurityInformation
0x180022b7e  call    cs:__imp_RegSetKeySecurity
0x180022b84  test    eax, eax
0x180022b86  jz      short loc_180022B94
0x180022b88  jmp     loc_180022A7F
0x180022b8d  call    ?GetLastWin32Error@@YAJXZ
0x180022b92  mov     ebx, eax
0x180022b94  mov     rcx, [rbp+57h+var_78]; hKey
0x180022b98  test    rcx, rcx
0x180022b9b  jz      short loc_180022BA3
0x180022b9d  call    cs:__imp_RegCloseKey
0x180022ba3  mov     rcx, [rbp+57h+var_70]; hKey
0x180022ba7  test    rcx, rcx
0x180022baa  jz      short loc_180022BB2
0x180022bac  call    cs:__imp_RegCloseKey
0x180022bb2  mov     rcx, [rbp+57h+hKey]; hKey
0x180022bb6  test    rcx, rcx
0x180022bb9  jz      short loc_180022BC1
0x180022bbb  call    cs:__imp_RegCloseKey
0x180022bc1  mov     rcx, [rbp+57h+StringSid]; hMem
0x180022bc5  test    rcx, rcx
0x180022bc8  jz      short loc_180022BD0
0x180022bca  call    cs:__imp_LocalFree
0x180022bd0  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180022bd4  test    rcx, rcx
0x180022bd7  jz      short loc_180022BDE
0x180022bd9  call    ?MemFree@@YAXPEAX@Z
0x180022bde  mov     rcx, [rbp+57h+lpMem+8]; lpMem
0x180022be2  test    rcx, rcx
0x180022be5  jz      short loc_180022BEC
0x180022be7  call    ?MemFree@@YAXPEAX@Z
0x180022bec  mov     rcx, rdi; lpMem
0x180022bef  call    ?MemFree@@YAXPEAX@Z
0x180022bf4  mov     eax, ebx
0x180022bf6  mov     rcx, [rbp+57h+var_18]
0x180022bfa  xor     rcx, rsp; StackCookie
0x180022bfd  call    __security_check_cookie
0x180022c02  lea     r11, [rsp+0D0h+var_10]
0x180022c0a  mov     rbx, [r11+28h]
0x180022c0e  mov     rsi, [r11+30h]
0x180022c12  mov     rsp, r11
0x180022c15  pop     r14
0x180022c17  pop     rdi
0x180022c18  pop     rbp
0x180022c19  retn
```
