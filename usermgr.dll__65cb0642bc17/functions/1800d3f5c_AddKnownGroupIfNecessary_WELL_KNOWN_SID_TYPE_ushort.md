# AddKnownGroupIfNecessary(WELL_KNOWN_SID_TYPE,ushort *)

- ea: `0x1800d3f5c`
- end: `0x1800d4090`
- name: `?AddKnownGroupIfNecessary@@YAKW4WELL_KNOWN_SID_TYPE@@PEAG@Z`
- size: `308`
- prototype: `unsigned int(enum WELL_KNOWN_SID_TYPE, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d40bc`

## callees

- `0x1800d3f5c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d3fc0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d3fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3fca`
- `samcli!NetLocalGroupAddMembers` at `0x1800d405b`
- `samcli!NetLocalGroupAddMembers` at `0x1800d405b`
- `samcli!NetLocalGroupAdd` at `0x1800d401f`
- `samcli!NetLocalGroupAdd` at `0x1800d401f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d4000`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800d4000`

## pseudocode

```c
__int64 __fastcall AddKnownGroupIfNecessary(enum WELL_KNOWN_SID_TYPE a1, unsigned __int16 *a2)
{
  DWORD v3; // ecx
  DWORD v4; // eax
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE buf[8]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v11[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  cbSid = 68;
  cchReferencedDomainName = 260;
  cchName = 260;
  *(_QWORD *)buf = 0;
  *(_QWORD *)v11 = 0;
  peUse = 0;
  if ( CreateWellKnownSid(a1, 0, pSid, &cbSid)
    && LookupAccountSidLocalW(pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    *(_QWORD *)buf = Name;
    v4 = NetLocalGroupAdd(0, 0, buf, 0);
    v3 = v4;
    if ( v4 == 1379 || !v4 || v4 - 2223 <= 1 )
    {
      *(_QWORD *)v11 = pSid;
      v3 = NetLocalGroupAddMembers(0, a2, 0, v11, 1u);
      if ( v3 == 1378 )
        return 0;
    }
  }
  else
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x1800d3f5c  mov     [rsp-8+arg_10], rbx
0x1800d3f61  push    rbp
0x1800d3f62  lea     rbp, [rsp-3D0h]
0x1800d3f6a  sub     rsp, 4D0h
0x1800d3f71  mov     rax, cs:__security_cookie
0x1800d3f78  xor     rax, rsp
0x1800d3f7b  mov     [rbp+3D0h+var_10], rax
0x1800d3f82  mov     eax, 104h
0x1800d3f87  mov     [rsp+4D0h+cbSid], 44h ; 'D'
0x1800d3f8f  mov     rbx, rdx
0x1800d3f92  mov     [rsp+4D0h+var_498], eax
0x1800d3f96  xor     edx, edx; DomainSid
0x1800d3f98  mov     [rsp+4D0h+cchName], eax
0x1800d3f9c  lea     r9, [rsp+4D0h+cbSid]; cbSid
0x1800d3fa1  mov     qword ptr [rsp+4D0h+buf], 0
0x1800d3faa  lea     r8, [rsp+4D0h+pSid]; pSid
0x1800d3faf  mov     qword ptr [rsp+4D0h+var_488], 0
0x1800d3fb8  mov     [rsp+4D0h+var_49C], 0
0x1800d3fc0  call    cs:__imp_CreateWellKnownSid
0x1800d3fc6  test    eax, eax
0x1800d3fc8  jnz     short loc_1800D3FD7
0x1800d3fca  call    cs:__imp_GetLastError
0x1800d3fd0  mov     ecx, eax
0x1800d3fd2  jmp     loc_1800D406E
0x1800d3fd7  lea     rax, [rsp+4D0h+var_49C]
0x1800d3fdc  mov     [rsp+4D0h+peUse], rax; peUse
0x1800d3fe1  lea     r9, [rbp+3D0h+ReferencedDomainName]; ReferencedDomainName
0x1800d3fe8  lea     rax, [rsp+4D0h+var_498]
0x1800d3fed  lea     r8, [rsp+4D0h+cchName]; cchName
0x1800d3ff2  mov     [rsp+4D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800d3ff7  lea     rdx, [rbp+3D0h+Name]; Name
0x1800d3ffb  lea     rcx, [rsp+4D0h+pSid]; Sid
0x1800d4000  call    cs:__imp_LookupAccountSidLocalW
0x1800d4006  test    eax, eax
0x1800d4008  jz      short loc_1800D3FCA
0x1800d400a  lea     rax, [rbp+3D0h+Name]
0x1800d400e  xor     r9d, r9d; parm_err
0x1800d4011  lea     r8, [rsp+4D0h+buf]; buf
0x1800d4016  mov     qword ptr [rsp+4D0h+buf], rax
0x1800d401b  xor     edx, edx; level
0x1800d401d  xor     ecx, ecx; servername
0x1800d401f  call    cs:__imp_NetLocalGroupAdd
0x1800d4025  mov     ecx, eax
0x1800d4027  cmp     eax, 563h
0x1800d402c  jz      short loc_1800D403C
0x1800d402e  test    eax, eax
0x1800d4030  jz      short loc_1800D403C
0x1800d4032  add     eax, 0FFFFF751h
0x1800d4037  cmp     eax, 1
0x1800d403a  ja      short loc_1800D406E
0x1800d403c  lea     rax, [rsp+4D0h+pSid]
0x1800d4041  mov     dword ptr [rsp+4D0h+cchReferencedDomainName], 1; totalentries
0x1800d4049  lea     r9, [rsp+4D0h+var_488]; buf
0x1800d404e  mov     qword ptr [rsp+4D0h+var_488], rax
0x1800d4053  xor     r8d, r8d; level
0x1800d4056  mov     rdx, rbx; groupname
0x1800d4059  xor     ecx, ecx; servername
0x1800d405b  call    cs:__imp_NetLocalGroupAddMembers
0x1800d4061  mov     ecx, eax
0x1800d4063  xor     eax, eax
0x1800d4065  cmp     ecx, 562h
0x1800d406b  cmovz   ecx, eax
0x1800d406e  mov     eax, ecx
0x1800d4070  mov     rcx, [rbp+3D0h+var_10]
0x1800d4077  xor     rcx, rsp; StackCookie
0x1800d407a  call    __security_check_cookie
0x1800d407f  mov     rbx, [rsp+4D0h+arg_10]
0x1800d4087  add     rsp, 4D0h
0x1800d408e  pop     rbp
0x1800d408f  retn
```
