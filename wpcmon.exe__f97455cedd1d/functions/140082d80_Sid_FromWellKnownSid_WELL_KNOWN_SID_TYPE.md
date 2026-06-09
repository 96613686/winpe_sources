# Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)

- ea: `0x140082d80`
- end: `0x140082fe1`
- name: `?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001f8b8`

## callees

- `0x140005530`
- `0x140006314`
- `0x140006338`
- `0x14001f6b4`
- `0x140060e60`
- `0x140060f58`
- `0x1400615c0`
- `0x14007aaf4`
- `0x1400829f4`
- `0x140082d80`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x140082e35`
- `ADVAPI32!LookupAccountNameW` at `0x140082e35`
- `ADVAPI32!CreateWellKnownSid` at `0x140082e69`
- `ADVAPI32!CreateWellKnownSid` at `0x140082e69`
- `KERNEL32!GetComputerNameW` at `0x140082ddc`
- `KERNEL32!GetComputerNameW` at `0x140082ddc`
- `KERNEL32!GetLastError` at `0x140082ea3`
- `KERNEL32!GetLastError` at `0x140082f0b`
- `KERNEL32!GetLastError` at `0x140082f6f`
- `KERNEL32!GetLastError` at `0x140082ea3`
- `KERNEL32!GetLastError` at `0x140082f0b`
- `KERNEL32!GetLastError` at `0x140082f6f`

## pseudocode

```c
void **__fastcall Sid::FromWellKnownSid(void **a1)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r10
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v15[6]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v18; // [rsp+A0h] [rbp-60h]
  WCHAR ReferencedDomainName[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v20; // [rsp+C0h] [rbp-40h]
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pSid[80]; // [rsp+120h] [rbp+20h] BYREF

  *(_QWORD *)v15 = a1;
  memset_0(Sid, 0, 0x44u);
  nSize = 16;
  *(_OWORD *)Buffer = 0;
  v18 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  cchReferencedDomainName = 16;
  cbSid = 68;
  peUse = 0;
  *(_OWORD *)ReferencedDomainName = 0;
  v20 = 0;
  if ( !LookupAccountNameW(0, Buffer, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = std::array<unsigned short,16>::data(Buffer);
      WPP_SF_Sd(*(_QWORD *)(v10 + 16), 18, (unsigned int)WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v9, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  memset_0(pSid, 0, 0x44u);
  v15[0] = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, Sid, pSid, v15) )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, 22, v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v4);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Sid::FromPSID(a1, pSid);
  return a1;
}

```

## disassembly

```asm
0x140082d80  mov     [rsp-8+arg_8], rbx
0x140082d85  mov     [rsp-8+arg_10], rdi
0x140082d8a  push    rbp
0x140082d8b  lea     rbp, [rsp-80h]
0x140082d90  sub     rsp, 180h
0x140082d97  mov     rax, cs:__security_cookie
0x140082d9e  xor     rax, rsp
0x140082da1  mov     [rbp+80h+var_10], rax
0x140082da5  mov     rbx, rcx
0x140082da8  mov     qword ptr [rsp+180h+var_130], rcx
0x140082dad  mov     edi, 44h ; 'D'
0x140082db2  lea     rcx, [rbp+80h+Sid]; void *
0x140082db6  mov     r8d, edi; Size
0x140082db9  xor     edx, edx; Val
0x140082dbb  call    memset_0
0x140082dc0  xorps   xmm0, xmm0
0x140082dc3  mov     [rsp+180h+nSize], 10h
0x140082dcb  lea     rdx, [rsp+180h+nSize]; nSize
0x140082dd0  lea     rcx, [rbp+80h+Buffer]; lpBuffer
0x140082dd4  movups  xmmword ptr [rbp+80h+Buffer], xmm0
0x140082dd8  movups  [rbp+80h+var_E0], xmm0
0x140082ddc  call    cs:__imp_GetComputerNameW
0x140082de2  test    eax, eax
0x140082de4  jz      loc_140082F0B
0x140082dea  xorps   xmm0, xmm0
0x140082ded  mov     [rsp+180h+var_138], 10h
0x140082df5  lea     rax, [rsp+180h+var_13C]
0x140082dfa  mov     [rsp+180h+cbSid], edi
0x140082dfe  mov     [rsp+180h+peUse], rax; peUse
0x140082e03  lea     r9, [rsp+180h+cbSid]; cbSid
0x140082e08  lea     rax, [rsp+180h+var_138]
0x140082e0d  mov     [rsp+180h+var_13C], 0
0x140082e15  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140082e1a  lea     r8, [rbp+80h+Sid]; Sid
0x140082e1e  lea     rax, [rbp+80h+var_D0]
0x140082e22  xor     ecx, ecx; lpSystemName
0x140082e24  lea     rdx, [rbp+80h+Buffer]; lpAccountName
0x140082e28  mov     [rsp+180h+ReferencedDomainName], rax; ReferencedDomainName
0x140082e2d  movups  xmmword ptr [rbp+80h+var_D0], xmm0
0x140082e31  movups  [rbp+80h+var_C0], xmm0
0x140082e35  call    cs:__imp_LookupAccountNameW
0x140082e3b  test    eax, eax
0x140082e3d  jz      loc_140082F6F
0x140082e43  mov     r8d, edi; Size
0x140082e46  lea     rcx, [rbp+80h+pSid]; void *
0x140082e4a  xor     edx, edx; Val
0x140082e4c  call    memset_0
0x140082e51  mov     [rsp+180h+var_130], edi
0x140082e55  lea     r9, [rsp+180h+var_130]; cbSid
0x140082e5a  mov     edi, 16h
0x140082e5f  lea     r8, [rbp+80h+pSid]; pSid
0x140082e63  mov     ecx, edi; WellKnownSidType
0x140082e65  lea     rdx, [rbp+80h+Sid]; DomainSid
0x140082e69  call    cs:__imp_CreateWellKnownSid
0x140082e6f  test    eax, eax
0x140082e71  jz      short loc_140082EA3
0x140082e73  lea     rdx, [rbp+80h+pSid]
0x140082e77  mov     rcx, rbx
0x140082e7a  call    ?FromPSID@Sid@@SA?AV1@PEAX@Z; Sid::FromPSID(void *)
0x140082e7f  mov     rax, rbx
0x140082e82  mov     rcx, [rbp+80h+var_10]
0x140082e86  xor     rcx, rsp; StackCookie
0x140082e89  call    __security_check_cookie
0x140082e8e  lea     r11, [rsp+180h+var_s0]
0x140082e96  mov     rbx, [r11+18h]
0x140082e9a  mov     rdi, [r11+20h]
0x140082e9e  mov     rsp, r11
0x140082ea1  pop     rbp
0x140082ea2  retn
0x140082ea3  call    cs:__imp_GetLastError
0x140082ea9  mov     ebx, eax
0x140082eab  test    eax, eax
0x140082ead  jle     short loc_140082EB8
0x140082eaf  movzx   ebx, ax
0x140082eb2  or      ebx, 80070000h
0x140082eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ebf  lea     rax, WPP_GLOBAL_Control
0x140082ec6  cmp     rcx, rax
0x140082ec9  jz      short loc_140082EED
0x140082ecb  test    byte ptr [rcx+1Ch], 1
0x140082ecf  jz      short loc_140082EED
0x140082ed1  mov     rcx, [rcx+10h]
0x140082ed5  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x140082edc  mov     edx, 13h
0x140082ee1  mov     dword ptr [rsp+180h+ReferencedDomainName], ebx
0x140082ee5  mov     r9d, edi
0x140082ee8  call    WPP_SF_dd
0x140082eed  mov     edx, ebx; int
0x140082eef  lea     rcx, [rsp+180h+pExceptionObject]; this
0x140082ef4  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140082ef9  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082f00  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x140082f05  call    _CxxThrowException_0
0x140082f0b  call    cs:__imp_GetLastError
0x140082f11  mov     ebx, eax
0x140082f13  test    eax, eax
0x140082f15  jle     short loc_140082F20
0x140082f17  movzx   ebx, ax
0x140082f1a  or      ebx, 80070000h
0x140082f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140082f27  lea     rax, WPP_GLOBAL_Control
0x140082f2e  cmp     rcx, rax
0x140082f31  jz      short loc_140082F51
0x140082f33  test    byte ptr [rcx+1Ch], 1
0x140082f37  jz      short loc_140082F51
0x140082f39  mov     rcx, [rcx+10h]
0x140082f3d  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x140082f44  mov     edx, 11h
0x140082f49  mov     r9d, ebx
0x140082f4c  call    WPP_SF_d
0x140082f51  mov     edx, ebx; int
0x140082f53  lea     rcx, [rsp+180h+pExceptionObject]; this
0x140082f58  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140082f5d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082f64  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x140082f69  call    _CxxThrowException_0
0x140082f6f  call    cs:__imp_GetLastError
0x140082f75  mov     ebx, eax
0x140082f77  test    eax, eax
0x140082f79  jle     short loc_140082F84
0x140082f7b  movzx   ebx, ax
0x140082f7e  or      ebx, 80070000h
0x140082f84  mov     r10, cs:WPP_GLOBAL_Control
0x140082f8b  lea     rax, WPP_GLOBAL_Control
0x140082f92  cmp     r10, rax
0x140082f95  jz      short loc_140082FC3
0x140082f97  test    byte ptr [r10+1Ch], 1
0x140082f9c  jz      short loc_140082FC3
0x140082f9e  lea     rcx, [rbp+80h+Buffer]
0x140082fa2  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x140082fa7  mov     rcx, [r10+10h]
0x140082fab  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x140082fb2  mov     r9, rax
0x140082fb5  mov     dword ptr [rsp+180h+ReferencedDomainName], ebx
0x140082fb9  mov     edx, 12h
0x140082fbe  call    WPP_SF_Sd
0x140082fc3  mov     edx, ebx; int
0x140082fc5  lea     rcx, [rsp+180h+pExceptionObject]; this
0x140082fca  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140082fcf  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082fd6  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x140082fdb  call    _CxxThrowException_0
```
