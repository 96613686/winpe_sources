# CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)

- ea: `0x1800ce3cc`
- end: `0x1800ce587`
- name: `?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z`
- size: `443`
- prototype: `int(CUserTileStore *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ce1ec`

## callees

- `0x18003d244`
- `0x180054130`
- `0x180054ad4`
- `0x1800ce3cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce42a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce42a`
- `ntdll!RtlNtStatusToDosError` at `0x1800ce4f3`
- `ntdll!RtlNtStatusToDosError` at `0x1800ce4f3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ce543`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ce543`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ce48c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ce48c`
- `netutils!NetApiBufferFree` at `0x1800ce556`
- `netutils!NetApiBufferFree` at `0x1800ce556`
- `samcli!NetUserGetInfo` at `0x1800ce4c1`
- `samcli!NetUserGetInfo` at `0x1800ce4c1`

## pseudocode

```c
__int64 __fastcall CUserTileStore::_GetInternetPrincipalNameFromUserToken(
        CUserTileStore *this,
        void *a2,
        unsigned __int16 **a3)
{
  signed int Error; // ebx
  DWORD Info; // eax
  unsigned int i; // ecx
  NTSTATUS v8; // ecx
  signed int v9; // eax
  LPBYTE v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  HRESULT v13; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 88;
  if ( GetTokenInformation(a2, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    peUse = 0;
    cchName = 260;
    cchReferencedDomainName = 260;
    if ( LookupAccountSidW(
           0,
           TokenInformation[0],
           Name,
           &cchName,
           ReferencedDomainName,
           &cchReferencedDomainName,
           &peUse)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      bufptr = 0;
      Info = NetUserGetInfo(0, Name, 0x18u, &bufptr);
      for ( i = 0; i < 0x7A; ++i )
      {
        if ( LODWORD(ErrorMap[i]) == Info )
        {
          v8 = HIDWORD(ErrorMap[i]);
          goto LABEL_11;
        }
      }
      v8 = -1073741595;
LABEL_11:
      v9 = RtlNtStatusToDosError(v8);
      Error = v9;
      if ( v9 > 0 )
        Error = (unsigned __int16)v9 | 0x80070000;
      if ( Error >= 0 )
      {
        v10 = bufptr;
        Error = -2147467259;
        if ( *(_DWORD *)bufptr == 1 )
        {
          v11 = *((_QWORD *)bufptr + 2);
          if ( v11 )
          {
            v12 = -1;
            do
              ++v12;
            while ( *(_WORD *)(v11 + 2 * v12) );
            if ( v12 )
            {
              v13 = SHStrDupW(*((LPCWSTR *)bufptr + 2), a3);
              v10 = bufptr;
              Error = v13;
            }
          }
        }
        NetApiBufferFree(v10);
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800ce3cc  mov     [rsp-8+arg_0], rbx
0x1800ce3d1  push    rbp
0x1800ce3d2  push    rsi
0x1800ce3d3  push    rdi
0x1800ce3d4  lea     rbp, [rsp-3F0h]
0x1800ce3dc  sub     rsp, 4F0h
0x1800ce3e3  mov     rax, cs:__security_cookie
0x1800ce3ea  xor     rax, rsp
0x1800ce3ed  mov     [rbp+400h+var_20], rax
0x1800ce3f4  mov     rdi, r8
0x1800ce3f7  lea     rcx, [rsp+500h+TokenInformation]; void *
0x1800ce3fc  mov     rbx, rdx
0x1800ce3ff  mov     esi, 58h ; 'X'
0x1800ce404  mov     r8d, esi; Size
0x1800ce407  xor     edx, edx; Val
0x1800ce409  call    memset_0
0x1800ce40e  lea     rax, [rsp+500h+var_4C0]
0x1800ce413  mov     [rsp+500h+var_4C0], esi
0x1800ce417  mov     r9d, esi; TokenInformationLength
0x1800ce41a  mov     [rsp+500h+ReturnLength], rax; ReturnLength
0x1800ce41f  lea     r8, [rsp+500h+TokenInformation]; TokenInformation
0x1800ce424  mov     rcx, rbx; TokenHandle
0x1800ce427  lea     edx, [rsi-57h]; TokenInformationClass
0x1800ce42a  call    cs:__imp_GetTokenInformation
0x1800ce431  nop     dword ptr [rax+rax+00h]
0x1800ce436  xor     esi, esi
0x1800ce438  test    eax, eax
0x1800ce43a  jnz     short loc_1800CE44B
0x1800ce43c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce441  mov     ebx, eax
0x1800ce443  test    eax, eax
0x1800ce445  js      loc_1800CE562
0x1800ce44b  mov     rdx, [rsp+500h+TokenInformation]; Sid
0x1800ce450  lea     r9, [rsp+500h+cchName]; cchName
0x1800ce455  mov     eax, 104h
0x1800ce45a  mov     [rsp+500h+var_4BC], esi
0x1800ce45e  mov     [rsp+500h+cchName], eax
0x1800ce462  lea     r8, [rbp+400h+Name]; Name
0x1800ce466  mov     [rsp+500h+var_4B8], eax
0x1800ce46a  xor     ecx, ecx; lpSystemName
0x1800ce46c  lea     rax, [rsp+500h+var_4BC]
0x1800ce471  mov     [rsp+500h+peUse], rax; peUse
0x1800ce476  lea     rax, [rsp+500h+var_4B8]
0x1800ce47b  mov     [rsp+500h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800ce480  lea     rax, [rbp+400h+ReferencedDomainName]
0x1800ce487  mov     [rsp+500h+ReturnLength], rax; ReferencedDomainName
0x1800ce48c  call    cs:__imp_LookupAccountSidW
0x1800ce493  nop     dword ptr [rax+rax+00h]
0x1800ce498  test    eax, eax
0x1800ce49a  jnz     short loc_1800CE4AB
0x1800ce49c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce4a1  mov     ebx, eax
0x1800ce4a3  test    eax, eax
0x1800ce4a5  js      loc_1800CE562
0x1800ce4ab  lea     r9, [rsp+500h+bufptr]; bufptr
0x1800ce4b0  mov     [rsp+500h+bufptr], rsi
0x1800ce4b5  mov     r8d, 18h; level
0x1800ce4bb  lea     rdx, [rbp+400h+Name]; username
0x1800ce4bf  xor     ecx, ecx; servername
0x1800ce4c1  call    cs:__imp_NetUserGetInfo
0x1800ce4c8  nop     dword ptr [rax+rax+00h]
0x1800ce4cd  mov     ecx, esi
0x1800ce4cf  lea     r8, ErrorMap
0x1800ce4d6  cmp     ecx, 7Ah ; 'z'
0x1800ce4d9  jnb     short loc_1800CE4EE
0x1800ce4db  mov     edx, ecx
0x1800ce4dd  cmp     [r8+rdx*8], eax
0x1800ce4e1  jz      short loc_1800CE4E7
0x1800ce4e3  inc     ecx
0x1800ce4e5  jmp     short loc_1800CE4D6
0x1800ce4e7  mov     ecx, [r8+rdx*8+4]
0x1800ce4ec  jmp     short loc_1800CE4F3
0x1800ce4ee  mov     ecx, 0C00000E5h; Status
0x1800ce4f3  call    cs:__imp_RtlNtStatusToDosError
0x1800ce4fa  nop     dword ptr [rax+rax+00h]
0x1800ce4ff  mov     ebx, eax
0x1800ce501  test    eax, eax
0x1800ce503  jle     short loc_1800CE50E
0x1800ce505  movzx   ebx, ax
0x1800ce508  or      ebx, 80070000h
0x1800ce50e  test    ebx, ebx
0x1800ce510  js      short loc_1800CE562
0x1800ce512  mov     rcx, [rsp+500h+bufptr]
0x1800ce517  mov     ebx, 80004005h
0x1800ce51c  cmp     dword ptr [rcx], 1
0x1800ce51f  jnz     short loc_1800CE556
0x1800ce521  mov     r8, [rcx+10h]
0x1800ce525  test    r8, r8
0x1800ce528  jz      short loc_1800CE556
0x1800ce52a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ce52e  inc     rax
0x1800ce531  cmp     [r8+rax*2], si
0x1800ce536  jnz     short loc_1800CE52E
0x1800ce538  test    rax, rax
0x1800ce53b  jz      short loc_1800CE556
0x1800ce53d  mov     rdx, rdi; ppwsz
0x1800ce540  mov     rcx, r8; psz
0x1800ce543  call    cs:__imp_SHStrDupW
0x1800ce54a  nop     dword ptr [rax+rax+00h]
0x1800ce54f  mov     rcx, [rsp+500h+bufptr]; Buffer
0x1800ce554  mov     ebx, eax
0x1800ce556  call    cs:__imp_NetApiBufferFree
0x1800ce55d  nop     dword ptr [rax+rax+00h]
0x1800ce562  mov     eax, ebx
0x1800ce564  mov     rcx, [rbp+400h+var_20]
0x1800ce56b  xor     rcx, rsp; StackCookie
0x1800ce56e  call    __security_check_cookie
0x1800ce573  mov     rbx, [rsp+500h+arg_0]
0x1800ce57b  add     rsp, 4F0h
0x1800ce582  pop     rdi
0x1800ce583  pop     rsi
0x1800ce584  pop     rbp
0x1800ce585  retn
```
