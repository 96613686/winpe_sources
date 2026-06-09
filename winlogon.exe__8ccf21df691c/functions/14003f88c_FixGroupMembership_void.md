# FixGroupMembership(void)

- ea: `0x14003f88c`
- end: `0x14003faba`
- name: `?FixGroupMembership@@YAKXZ`
- size: `558`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016284`

## callees

- `0x14003f88c`
- `0x140053720`
- `0x1400544e0`
- `0x140055158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f912`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f908`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f962`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f98a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003fa53`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f908`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f962`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003f98a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14003fa53`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14003fa32`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14003fa32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x14003f9d5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x14003f9d5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003f8e0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003f9b6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003f8e0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003f9b6`
- `samcli!NetLocalGroupAddMembers` at `0x14003fa83`
- `samcli!NetLocalGroupAddMembers` at `0x14003fa83`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x14003f946`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x14003f946`

## pseudocode

```c
unsigned int FixGroupMembership(void)
{
  unsigned int result; // eax
  DWORD v1; // ebx
  DWORD v2; // ecx
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD nSize; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE v8; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v9; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v10; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE buf[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v12; // [rsp+68h] [rbp-98h]
  _BYTE *v13; // [rsp+70h] [rbp-90h]
  WCHAR ReferencedDomainName[16]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[20]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE Sid[80]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pSid[80]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v18[80]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v19[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v20[80]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR Name[256]; // [rsp+250h] [rbp+150h] BYREF

  cbSid = 0;
  cchName = 256;
  cchReferencedDomainName = 15;
  peUse = 0;
  if ( (unsigned __int8)IsWinLogonExtPresent() && !(unsigned __int8)RtlIsStateSeparationEnabled() )
    return 0;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, pSid, &cbSid) )
    return GetLastError();
  if ( !LookupAccountSidLocalW(pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    return GetLastError();
  cbSid = 68;
  if ( !CreateWellKnownSid(WinInteractiveSid, 0, v18, &cbSid) )
    return GetLastError();
  cbSid = 68;
  *(_QWORD *)buf = v18;
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, v19, &cbSid) )
    return GetLastError();
  v1 = 2;
  v12 = v19;
  if ( (unsigned __int8)IsWinLogonExtPresent() )
  {
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
    {
      nSize = 16;
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        memset_0(Sid, 0, 0x44u);
        v10 = 68;
        v9 = 15;
        v8 = 0;
        if ( LookupAccountNameW(0, Buffer, Sid, &v10, ReferencedDomainName, &v9, &v8) )
        {
          cbSid = 68;
          if ( CreateWellKnownSid(WinAccountAdministratorSid, Sid, v20, &cbSid) )
          {
            v1 = 3;
            v13 = v20;
          }
        }
      }
    }
  }
  v2 = NetLocalGroupAddMembers(0, Name, 0, buf, v1);
  result = 0;
  if ( v2 != 1378 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x14003f88c  mov     [rsp-8+arg_0], rbx
0x14003f891  mov     [rsp-8+arg_8], rsi
0x14003f896  push    rbp
0x14003f897  lea     rbp, [rsp-360h]
0x14003f89f  sub     rsp, 460h
0x14003f8a6  mov     rax, cs:__security_cookie
0x14003f8ad  xor     rax, rsp
0x14003f8b0  mov     [rbp+360h+var_10], rax
0x14003f8b7  mov     [rsp+460h+cbSid], 0
0x14003f8bf  mov     [rsp+460h+cchName], 100h
0x14003f8c7  mov     [rsp+460h+var_418], 0Fh
0x14003f8cf  mov     [rsp+460h+var_41C], 0
0x14003f8d7  call    IsWinLogonExtPresent
0x14003f8dc  test    al, al
0x14003f8de  jz      short loc_14003F8F1
0x14003f8e0  call    cs:__imp_RtlIsStateSeparationEnabled
0x14003f8e6  test    al, al
0x14003f8e8  jnz     short loc_14003F8F1
0x14003f8ea  xor     eax, eax
0x14003f8ec  jmp     loc_14003FA96
0x14003f8f1  mov     esi, 44h ; 'D'
0x14003f8f6  lea     r9, [rsp+460h+cbSid]; cbSid
0x14003f8fb  lea     r8, [rbp+360h+pSid]; pSid
0x14003f8ff  mov     [rsp+460h+cbSid], esi
0x14003f903  xor     edx, edx; DomainSid
0x14003f905  lea     ecx, [rsi-29h]; WellKnownSidType
0x14003f908  call    cs:__imp_CreateWellKnownSid
0x14003f90e  test    eax, eax
0x14003f910  jnz     short loc_14003F91D
0x14003f912  call    cs:__imp_GetLastError
0x14003f918  jmp     loc_14003FA96
0x14003f91d  lea     rax, [rsp+460h+var_41C]
0x14003f922  mov     [rsp+460h+peUse], rax; peUse
0x14003f927  lea     r9, [rsp+460h+ReferencedDomainName]; ReferencedDomainName
0x14003f92c  lea     rax, [rsp+460h+var_418]
0x14003f931  lea     r8, [rsp+460h+cchName]; cchName
0x14003f936  mov     [rsp+460h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14003f93b  lea     rdx, [rbp+360h+Name]; Name
0x14003f942  lea     rcx, [rbp+360h+pSid]; Sid
0x14003f946  call    cs:__imp_LookupAccountSidLocalW
0x14003f94c  test    eax, eax
0x14003f94e  jz      short loc_14003F912
0x14003f950  xor     edx, edx; DomainSid
0x14003f952  mov     [rsp+460h+cbSid], esi
0x14003f956  lea     r9, [rsp+460h+cbSid]; cbSid
0x14003f95b  lea     r8, [rbp+360h+var_300]; pSid
0x14003f95f  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x14003f962  call    cs:__imp_CreateWellKnownSid
0x14003f968  test    eax, eax
0x14003f96a  jz      short loc_14003F912
0x14003f96c  xor     edx, edx; DomainSid
0x14003f96e  mov     [rsp+460h+cbSid], esi
0x14003f972  lea     rax, [rbp+360h+var_300]
0x14003f976  lea     r9, [rsp+460h+cbSid]; cbSid
0x14003f97b  mov     qword ptr [rsp+460h+buf], rax
0x14003f980  lea     r8, [rbp+360h+var_2B0]; pSid
0x14003f987  lea     ecx, [rdx+11h]; WellKnownSidType
0x14003f98a  call    cs:__imp_CreateWellKnownSid
0x14003f990  test    eax, eax
0x14003f992  jz      loc_14003F912
0x14003f998  lea     rax, [rbp+360h+var_2B0]
0x14003f99f  mov     ebx, 2
0x14003f9a4  mov     [rsp+460h+var_3F8], rax
0x14003f9a9  call    IsWinLogonExtPresent
0x14003f9ae  test    al, al
0x14003f9b0  jz      loc_14003FA6E
0x14003f9b6  call    cs:__imp_RtlIsStateSeparationEnabled
0x14003f9bc  test    al, al
0x14003f9be  jz      loc_14003FA6E
0x14003f9c4  lea     rdx, [rsp+460h+nSize]; nSize
0x14003f9c9  mov     [rsp+460h+nSize], 10h
0x14003f9d1  lea     rcx, [rbp+360h+Buffer]; lpBuffer
0x14003f9d5  call    cs:__imp_GetComputerNameW
0x14003f9db  test    eax, eax
0x14003f9dd  jz      loc_14003FA6E
0x14003f9e3  mov     r8, rsi; Size
0x14003f9e6  lea     rcx, [rbp+360h+Sid]; void *
0x14003f9ea  xor     edx, edx; Val
0x14003f9ec  call    memset_0
0x14003f9f1  lea     rax, [rsp+460h+var_40C]
0x14003f9f6  mov     [rsp+460h+var_404], esi
0x14003f9fa  mov     [rsp+460h+var_430], rax; peUse
0x14003f9ff  lea     r9, [rsp+460h+var_404]; cbSid
0x14003fa04  lea     rax, [rsp+460h+var_408]
0x14003fa09  mov     [rsp+460h+var_408], 0Fh
0x14003fa11  mov     [rsp+460h+peUse], rax; cchReferencedDomainName
0x14003fa16  lea     r8, [rbp+360h+Sid]; Sid
0x14003fa1a  lea     rax, [rsp+460h+ReferencedDomainName]
0x14003fa1f  mov     [rsp+460h+var_40C], 0
0x14003fa27  lea     rdx, [rbp+360h+Buffer]; lpAccountName
0x14003fa2b  mov     [rsp+460h+cchReferencedDomainName], rax; ReferencedDomainName
0x14003fa30  xor     ecx, ecx; lpSystemName
0x14003fa32  call    cs:__imp_LookupAccountNameW
0x14003fa38  test    eax, eax
0x14003fa3a  jz      short loc_14003FA6E
0x14003fa3c  lea     r9, [rsp+460h+cbSid]; cbSid
0x14003fa41  mov     [rsp+460h+cbSid], esi
0x14003fa45  lea     r8, [rbp+360h+var_260]; pSid
0x14003fa4c  lea     rdx, [rbp+360h+Sid]; DomainSid
0x14003fa50  lea     ecx, [rbx+24h]; WellKnownSidType
0x14003fa53  call    cs:__imp_CreateWellKnownSid
0x14003fa59  test    eax, eax
0x14003fa5b  jz      short loc_14003FA6E
0x14003fa5d  lea     rax, [rbp+360h+var_260]
0x14003fa64  mov     ebx, 3
0x14003fa69  mov     [rsp+460h+var_3F0], rax
0x14003fa6e  lea     r9, [rsp+460h+buf]; buf
0x14003fa73  mov     dword ptr [rsp+460h+cchReferencedDomainName], ebx; totalentries
0x14003fa77  xor     r8d, r8d; level
0x14003fa7a  lea     rdx, [rbp+360h+Name]; groupname
0x14003fa81  xor     ecx, ecx; servername
0x14003fa83  call    cs:__imp_NetLocalGroupAddMembers
0x14003fa89  mov     ecx, eax
0x14003fa8b  xor     eax, eax
0x14003fa8d  cmp     ecx, 562h
0x14003fa93  cmovnz  eax, ecx
0x14003fa96  mov     rcx, [rbp+360h+var_10]
0x14003fa9d  xor     rcx, rsp; StackCookie
0x14003faa0  call    __security_check_cookie
0x14003faa5  lea     r11, [rsp+460h+var_s0]
0x14003faad  mov     rbx, [r11+10h]
0x14003fab1  mov     rsi, [r11+18h]
0x14003fab5  mov     rsp, r11
0x14003fab8  pop     rbp
0x14003fab9  retn
```
