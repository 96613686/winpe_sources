# UnregisterInactiveAppContainerRegistration(HKEY__ *,ushort *,int *)

- ea: `0x1800c3c00`
- end: `0x1800c3ef7`
- name: `?UnregisterInactiveAppContainerRegistration@@YAJPEAUHKEY__@@PEAGPEAH@Z`
- size: `759`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180082080`

## callees

- `0x1800193a0`
- `0x180019ac0`
- `0x180091764`
- `0x1800a1d10`
- `0x1800c3b08`
- `0x1800c3c00`
- `0x1800cdd70`
- `0x1800d06fc`
- `0x1800d5448`
- `0x1800da398`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c3cd1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c3cd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3d30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3d30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3d0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3d0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3ecc`
- `KERNELBASE!AppContainerUnregisterSid` at `0x1800c3e52`
- `KERNELBASE!AppContainerUnregisterSid` at `0x1800c3e52`
- `RPCRT4!UuidFromStringW` at `0x1800c3df6`
- `RPCRT4!UuidFromStringW` at `0x1800c3e0c`
- `RPCRT4!UuidFromStringW` at `0x1800c3df6`
- `RPCRT4!UuidFromStringW` at `0x1800c3e0c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c3cb7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c3cb7`

## pseudocode

```c
__int64 __fastcall UnregisterInactiveAppContainerRegistration(HKEY hKey, LPCWSTR lpSubKey, int *a3)
{
  unsigned int v6; // ebx
  int active; // eax
  unsigned int v8; // eax
  int RegistryString; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-39h]
  int v18; // [rsp+30h] [rbp-29h] BYREF
  int v19; // [rsp+34h] [rbp-25h]
  PSID Sid; // [rsp+38h] [rbp-21h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-19h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+48h] [rbp-11h] BYREF
  RPC_WSTR v23[2]; // [rsp+58h] [rbp-1h] BYREF
  UUID Buf2; // [rsp+68h] [rbp+Fh] BYREF
  UUID Uuid; // [rsp+78h] [rbp+1Fh] BYREF

  v19 = 0;
  hKeya = 0;
  Sid = 0;
  v23[0] = (RPC_WSTR)qword_1800E7D10;
  StringUuid[0] = (RPC_WSTR)qword_1800E7D10;
  v23[1] = 0;
  StringUuid[1] = 0;
  Buf2 = 0;
  v18 = 0;
  Uuid = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qS(1029, 22, (unsigned int)WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, (_DWORD)hKey, (__int64)lpSubKey);
  *a3 = 0;
  if ( !ConvertStringSidToSidW(lpSubKey, &Sid) || GetLengthSid(Sid) != 40 )
    goto LABEL_4;
  active = IsActiveAppContainerSid(Sid, &v18);
  if ( active < 0 )
  {
    v19 = 397;
    v6 = active;
    goto LABEL_33;
  }
  if ( v18 )
    goto LABEL_4;
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0xBu, &hKeya);
  if ( v8 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 23, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, v8, phkResult);
    goto LABEL_4;
  }
  RegistryString = WxGetRegistryString(hKeya, L"DisplayName", (struct CWxString *)v23);
  if ( RegistryString < 0 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
    {
      v10 = 24;
LABEL_17:
      WPP_SF_d(1029, v10, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, (unsigned int)RegistryString, phkResult);
    }
LABEL_4:
    v6 = 1;
    active = 1;
    goto LABEL_33;
  }
  RegistryString = WxGetRegistryString(hKeya, L"Moniker", (struct CWxString *)StringUuid);
  if ( RegistryString < 0 )
  {
    if ( (xmmword_180107A60 & 0x20) == 0 )
      goto LABEL_4;
    v10 = 25;
    goto LABEL_17;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_SS(1029, 26, (unsigned int)WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, v23[0], (__int64)StringUuid[0]);
  if ( UuidFromStringW(StringUuid[0], &Uuid) || UuidFromStringW(v23[0], &Buf2) || memcmp_0(&Uuid, &Buf2, 0x10u) )
    goto LABEL_4;
  v11 = *(_QWORD *)((char *)Sid + 12) - *(_QWORD *)&Buf2.Data1;
  if ( !v11 )
    v11 = *(_QWORD *)((char *)Sid + 20) - *(_QWORD *)Buf2.Data4;
  if ( v11 )
    goto LABEL_4;
  v12 = AppContainerUnregisterSid(Sid);
  if ( v12 < 0 )
  {
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      LODWORD(phkResult) = v12;
      WPP_SF__sid_d(v14, v13, v15, Sid);
    }
    goto LABEL_4;
  }
  active = 0;
  *a3 = 1;
  v6 = 0;
LABEL_33:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 28, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, (unsigned int)active, phkResult);
  CWxString::_Release((CWxString *)StringUuid);
  CWxString::_Release((CWxString *)v23);
  if ( Sid )
    WxLocalAllocator::Free(&Sid);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v6;
}

```

## disassembly

```asm
0x1800c3c00  mov     [rsp-8+arg_18], rbx
0x1800c3c05  push    rbp
0x1800c3c06  push    rsi
0x1800c3c07  push    rdi
0x1800c3c08  push    r12
0x1800c3c0a  push    r13
0x1800c3c0c  lea     rbp, [rsp-37h]
0x1800c3c11  sub     rsp, 90h
0x1800c3c18  mov     rax, cs:__security_cookie
0x1800c3c1f  xor     rax, rsp
0x1800c3c22  mov     [rbp+57h+var_28], rax
0x1800c3c26  xor     eax, eax
0x1800c3c28  mov     [rbp+57h+var_7C], 0
0x1800c3c2f  mov     rdi, rcx
0x1800c3c32  mov     [rbp+57h+hKey], 0
0x1800c3c3a  lea     rcx, qword_1800E7D10
0x1800c3c41  mov     [rbp+57h+Sid], rax
0x1800c3c45  xorps   xmm0, xmm0
0x1800c3c48  mov     [rbp+57h+var_58], rcx
0x1800c3c4c  xorps   xmm1, xmm1
0x1800c3c4f  mov     [rbp+57h+StringUuid], rcx
0x1800c3c53  mov     rsi, r8
0x1800c3c56  mov     [rbp+57h+var_50], rax
0x1800c3c5a  mov     rbx, rdx
0x1800c3c5d  mov     [rbp+57h+var_60], rax
0x1800c3c61  movups  xmmword ptr [rbp+57h+Buf2.Data1], xmm0
0x1800c3c65  mov     [rbp+57h+var_80], eax
0x1800c3c68  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm1
0x1800c3c6c  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3c73  lea     r13, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids
0x1800c3c7a  mov     r12d, 405h
0x1800c3c80  jz      short loc_1800C3C9C
0x1800c3c82  lea     edx, [rax+16h]
0x1800c3c85  mov     [rsp+0B0h+phkResult], rbx
0x1800c3c8a  mov     ecx, r12d
0x1800c3c8d  mov     r9, rdi
0x1800c3c90  mov     r8, r13
0x1800c3c93  call    WPP_SF_qS
0x1800c3c98  mov     rax, [rbp+57h+Sid]
0x1800c3c9c  mov     dword ptr [rsi], 0
0x1800c3ca2  test    rax, rax
0x1800c3ca5  jz      short loc_1800C3CB0
0x1800c3ca7  lea     rcx, [rbp+57h+Sid]; void **
0x1800c3cab  call    ?Free@WxLocalAllocator@@SAXPEAPEAX@Z; WxLocalAllocator::Free(void * *)
0x1800c3cb0  lea     rdx, [rbp+57h+Sid]; Sid
0x1800c3cb4  mov     rcx, rbx; StringSid
0x1800c3cb7  call    cs:__imp_ConvertStringSidToSidW
0x1800c3cbd  test    eax, eax
0x1800c3cbf  jnz     short loc_1800C3CCD
0x1800c3cc1  mov     ebx, 1
0x1800c3cc6  mov     eax, ebx
0x1800c3cc8  jmp     loc_1800C3E85
0x1800c3ccd  mov     rcx, [rbp+57h+Sid]; pSid
0x1800c3cd1  call    cs:__imp_GetLengthSid
0x1800c3cd7  cmp     eax, 28h ; '('
0x1800c3cda  jnz     short loc_1800C3CC1
0x1800c3cdc  mov     rcx, [rbp+57h+Sid]; pSid2
0x1800c3ce0  lea     rdx, [rbp+57h+var_80]; int *
0x1800c3ce4  call    ?IsActiveAppContainerSid@@YAJQEAEPEAH@Z; IsActiveAppContainerSid(uchar * const,int *)
0x1800c3ce9  test    eax, eax
0x1800c3ceb  jns     short loc_1800C3CFB
0x1800c3ced  mov     [rbp+57h+var_7C], 18Dh
0x1800c3cf4  mov     ebx, eax
0x1800c3cf6  jmp     loc_1800C3E85
0x1800c3cfb  cmp     [rbp+57h+var_80], 0
0x1800c3cff  jnz     short loc_1800C3CC1
0x1800c3d01  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c3d05  test    rcx, rcx
0x1800c3d08  jz      short loc_1800C3D18
0x1800c3d0a  call    cs:__imp_RegCloseKey
0x1800c3d10  mov     [rbp+57h+hKey], 0
0x1800c3d18  lea     rax, [rbp+57h+hKey]
0x1800c3d1c  mov     r9d, 0Bh; samDesired
0x1800c3d22  xor     r8d, r8d; ulOptions
0x1800c3d25  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800c3d2a  mov     rdx, rbx; lpSubKey
0x1800c3d2d  mov     rcx, rdi; hKey
0x1800c3d30  call    cs:__imp_RegOpenKeyExW
0x1800c3d36  test    eax, eax
0x1800c3d38  jz      short loc_1800C3D5F
0x1800c3d3a  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3d41  jz      loc_1800C3CC1
0x1800c3d47  mov     edx, 17h
0x1800c3d4c  mov     ecx, r12d
0x1800c3d4f  mov     r9d, eax
0x1800c3d52  mov     r8, r13
0x1800c3d55  call    WPP_SF_d
0x1800c3d5a  jmp     loc_1800C3CC1
0x1800c3d5f  mov     rcx, [rbp+57h+hKey]; hkey
0x1800c3d63  lea     r8, [rbp+57h+var_58]; struct CWxString *
0x1800c3d67  lea     rdx, aDisplayname; "DisplayName"
0x1800c3d6e  call    ?WxGetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z; WxGetRegistryString(HKEY__ *,ushort const *,CWxString *)
0x1800c3d73  test    eax, eax
0x1800c3d75  jns     short loc_1800C3D9C
0x1800c3d77  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3d7e  jz      loc_1800C3CC1
0x1800c3d84  mov     edx, 18h
0x1800c3d89  mov     ecx, r12d
0x1800c3d8c  mov     r9d, eax
0x1800c3d8f  mov     r8, r13
0x1800c3d92  call    WPP_SF_d
0x1800c3d97  jmp     loc_1800C3CC1
0x1800c3d9c  mov     rcx, [rbp+57h+hKey]; hkey
0x1800c3da0  lea     r8, [rbp+57h+StringUuid]; struct CWxString *
0x1800c3da4  lea     rdx, aMoniker; "Moniker"
0x1800c3dab  call    ?WxGetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z; WxGetRegistryString(HKEY__ *,ushort const *,CWxString *)
0x1800c3db0  test    eax, eax
0x1800c3db2  jns     short loc_1800C3DC8
0x1800c3db4  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3dbb  jz      loc_1800C3CC1
0x1800c3dc1  mov     edx, 19h
0x1800c3dc6  jmp     short loc_1800C3D89
0x1800c3dc8  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3dcf  jz      short loc_1800C3DEE
0x1800c3dd1  mov     rax, [rbp+57h+StringUuid]
0x1800c3dd5  mov     edx, 1Ah
0x1800c3dda  mov     r9, [rbp+57h+var_58]
0x1800c3dde  mov     ecx, r12d
0x1800c3de1  mov     r8, r13
0x1800c3de4  mov     [rsp+0B0h+phkResult], rax
0x1800c3de9  call    WPP_SF_SS
0x1800c3dee  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x1800c3df2  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800c3df6  call    cs:__imp_UuidFromStringW
0x1800c3dfc  test    eax, eax
0x1800c3dfe  jnz     loc_1800C3CC1
0x1800c3e04  mov     rcx, [rbp+57h+var_58]; StringUuid
0x1800c3e08  lea     rdx, [rbp+57h+Buf2]; Uuid
0x1800c3e0c  call    cs:__imp_UuidFromStringW
0x1800c3e12  test    eax, eax
0x1800c3e14  jnz     loc_1800C3CC1
0x1800c3e1a  lea     r8d, [rax+10h]; Size
0x1800c3e1e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800c3e22  lea     rcx, [rbp+57h+Uuid]; Buf1
0x1800c3e26  call    memcmp_0
0x1800c3e2b  test    eax, eax
0x1800c3e2d  jnz     loc_1800C3CC1
0x1800c3e33  mov     rcx, [rbp+57h+Sid]
0x1800c3e37  mov     rax, [rcx+0Ch]
0x1800c3e3b  sub     rax, qword ptr [rbp+57h+Buf2.Data1]
0x1800c3e3f  jnz     short loc_1800C3E49
0x1800c3e41  mov     rax, [rcx+14h]
0x1800c3e45  sub     rax, qword ptr [rbp+57h+Buf2.Data4]
0x1800c3e49  test    rax, rax
0x1800c3e4c  jnz     loc_1800C3CC1
0x1800c3e52  call    cs:__imp_AppContainerUnregisterSid
0x1800c3e58  test    eax, eax
0x1800c3e5a  jns     short loc_1800C3E7B
0x1800c3e5c  test    byte ptr cs:xmmword_180107A50, 20h
0x1800c3e63  jz      loc_1800C3CC1
0x1800c3e69  mov     r9, [rbp+57h+Sid]
0x1800c3e6d  mov     dword ptr [rsp+0B0h+phkResult], eax
0x1800c3e71  call    WPP_SF__sid_d
0x1800c3e76  jmp     loc_1800C3CC1
0x1800c3e7b  xor     eax, eax
0x1800c3e7d  mov     dword ptr [rsi], 1
0x1800c3e83  xor     ebx, ebx
0x1800c3e85  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c3e8c  jz      short loc_1800C3EA1
0x1800c3e8e  mov     edx, 1Ch
0x1800c3e93  mov     ecx, r12d
0x1800c3e96  mov     r9d, eax
0x1800c3e99  mov     r8, r13
0x1800c3e9c  call    WPP_SF_d
0x1800c3ea1  lea     rcx, [rbp+57h+StringUuid]; this
0x1800c3ea5  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800c3eaa  lea     rcx, [rbp+57h+var_58]; this
0x1800c3eae  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800c3eb3  cmp     [rbp+57h+Sid], 0
0x1800c3eb8  jz      short loc_1800C3EC3
0x1800c3eba  lea     rcx, [rbp+57h+Sid]; void **
0x1800c3ebe  call    ?Free@WxLocalAllocator@@SAXPEAPEAX@Z; WxLocalAllocator::Free(void * *)
0x1800c3ec3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c3ec7  test    rcx, rcx
0x1800c3eca  jz      short loc_1800C3ED2
0x1800c3ecc  call    cs:__imp_RegCloseKey
0x1800c3ed2  mov     eax, ebx
0x1800c3ed4  mov     rcx, [rbp+57h+var_28]
0x1800c3ed8  xor     rcx, rsp; StackCookie
0x1800c3edb  call    __security_check_cookie
0x1800c3ee0  mov     rbx, [rsp+0B0h+arg_18]
0x1800c3ee8  add     rsp, 90h
0x1800c3eef  pop     r13
0x1800c3ef1  pop     r12
0x1800c3ef3  pop     rdi
0x1800c3ef4  pop     rsi
0x1800c3ef5  pop     rbp
0x1800c3ef6  retn
```
