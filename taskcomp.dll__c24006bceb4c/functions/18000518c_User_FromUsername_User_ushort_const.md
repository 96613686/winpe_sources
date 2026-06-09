# User::FromUsername(User &,ushort const *)

- ea: `0x18000518c`
- end: `0x1800053af`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `547`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004820`
- `0x1800157e0`
- `0x1800177d0`
- `0x180018108`
- `0x18001ad80`
- `0x1800214c0`
- `0x180021c90`

## callees

- `0x180004eec`
- `0x18000518c`
- `0x18000878c`
- `0x18000fbb8`
- `0x180019a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000530c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000530c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005242`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005392`
- `OLEAUT32!__imp_SysFreeString` at `0x180005325`
- `OLEAUT32!__imp_SysFreeString` at `0x180005331`
- `OLEAUT32!__imp_SysFreeString` at `0x180005325`
- `OLEAUT32!__imp_SysFreeString` at `0x180005331`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800051cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800051cb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000520c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180005302`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000520c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180005302`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall User::FromUsername(struct User *this, LPCWSTR lpAccountName)
{
  enum _SID_NAME_USE v4; // r8d
  unsigned int v5; // edi
  signed int v6; // eax
  UINT v7; // edx
  signed int LastError; // eax
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-50h] BYREF
  PSID Sid; // [rsp+38h] [rbp-48h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+40h] [rbp-40h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-38h] BYREF
  char v14; // [rsp+50h] [rbp-30h]
  char *v15; // [rsp+58h] [rbp-28h]
  __int64 v16; // [rsp+60h] [rbp-20h]
  __int64 v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+70h] [rbp-10h]
  __int64 v19; // [rsp+74h] [rbp-Ch]
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp+20h] BYREF
  DWORD cbSid; // [rsp+A8h] [rbp+28h] BYREF

  cchReferencedDomainName = 0;
  cbSid = 0;
  Sid = 0;
  peUse = SidTypeUnknown;
  if ( ConvertStringSidToSidW(lpAccountName, &Sid) )
  {
    v4 = SidTypeUnknown;
LABEL_3:
    v5 = User::FromSid(this, Sid, v4);
    goto LABEL_25;
  }
  LookupAccountNameLocalW(lpAccountName, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
  if ( GetLastError() == 122 )
  {
    Sid = LocalAlloc(0, cbSid + 1);
    if ( !Sid )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v14 = 0;
      v15 = byte_1800505F8;
      v16 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v17 = 0;
      v18 = 14;
      v19 = -1;
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v7 = cchReferencedDomainName++;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&ReferencedDomainName, v7);
    if ( LookupAccountNameLocalW(lpAccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      SysFreeString(ReferencedDomainName);
      v4 = peUse;
      if ( peUse != SidTypeDomain && peUse > 0 && peUse < SidTypeDeletedAccount )
        goto LABEL_3;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v5 = -2147024809;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      SysFreeString(ReferencedDomainName);
    }
  }
  else
  {
    v6 = GetLastError();
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
  }
LABEL_25:
  if ( Sid )
    LocalFree(Sid);
  return v5;
}

```

## disassembly

```asm
0x18000518c  mov     [rsp-8+arg_0], rsi
0x180005191  mov     [rsp-8+arg_8], rdi
0x180005196  push    rbp
0x180005197  mov     rbp, rsp
0x18000519a  sub     rsp, 80h
0x1800051a1  mov     rdi, rdx
0x1800051a4  mov     [rbp+arg_10], 0
0x1800051ab  mov     rsi, rcx
0x1800051ae  mov     [rbp+cbSid], 0
0x1800051b5  mov     rcx, rdi; StringSid
0x1800051b8  mov     [rbp+Sid], 0
0x1800051c0  lea     rdx, [rbp+Sid]; Sid
0x1800051c4  mov     [rbp+var_50], 8
0x1800051cb  call    cs:__imp_ConvertStringSidToSidW
0x1800051d1  test    eax, eax
0x1800051d3  jz      short loc_1800051EE
0x1800051d5  mov     r8d, 8; enum _SID_NAME_USE
0x1800051db  mov     rdx, [rbp+Sid]; void *
0x1800051df  mov     rcx, rsi; this
0x1800051e2  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x1800051e7  mov     edi, eax
0x1800051e9  jmp     loc_180005389
0x1800051ee  lea     rax, [rbp+var_50]
0x1800051f2  xor     r9d, r9d; ReferencedDomainName
0x1800051f5  mov     [rsp+80h+peUse], rax; peUse
0x1800051fa  lea     r8, [rbp+cbSid]; cbSid
0x1800051fe  lea     rax, [rbp+arg_10]
0x180005202  xor     edx, edx; Sid
0x180005204  mov     rcx, rdi; lpAccountName
0x180005207  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000520c  call    cs:__imp_LookupAccountNameLocalW
0x180005212  call    cs:__imp_GetLastError
0x180005218  cmp     eax, 7Ah ; 'z'
0x18000521b  jz      short loc_18000523B
0x18000521d  call    cs:__imp_GetLastError
0x180005223  mov     edi, eax
0x180005225  test    eax, eax
0x180005227  jle     loc_180005389
0x18000522d  movzx   edi, ax
0x180005230  or      edi, 80070000h
0x180005236  jmp     loc_180005389
0x18000523b  mov     edx, [rbp+cbSid]
0x18000523e  xor     ecx, ecx; uFlags
0x180005240  inc     edx; uBytes
0x180005242  call    cs:__imp_LocalAlloc
0x180005248  mov     [rbp+Sid], rax
0x18000524c  test    rax, rax
0x18000524f  jnz     short loc_1800052CF
0x180005251  mov     rcx, cs:WPP_GLOBAL_Control
0x180005258  lea     rax, WPP_GLOBAL_Control
0x18000525f  cmp     rcx, rax
0x180005262  jz      short loc_180005285
0x180005264  test    byte ptr [rcx+1Ch], 80h
0x180005268  jz      short loc_180005285
0x18000526a  cmp     byte ptr [rcx+19h], 2
0x18000526e  jb      short loc_180005285
0x180005270  mov     rcx, [rcx+10h]
0x180005274  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18000527b  mov     edx, 15h
0x180005280  call    WPP_SF_
0x180005285  lea     rax, byte_1800505F8
0x18000528c  mov     [rbp+var_30], 0
0x180005290  mov     [rbp+var_28], rax
0x180005294  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000529b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800052a2  mov     [rbp+var_20], 0
0x1800052aa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800052ae  mov     [rbp+pExceptionObject], rax
0x1800052b2  mov     [rbp+var_18], 0
0x1800052ba  mov     [rbp+var_10], 0Eh
0x1800052c1  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x1800052c9  call    _CxxThrowException_0
0x1800052cf  mov     edx, [rbp+arg_10]; int
0x1800052d2  lea     rcx, [rbp+ReferencedDomainName]; this
0x1800052d6  lea     eax, [rdx+1]
0x1800052d9  mov     [rbp+arg_10], eax
0x1800052dc  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x1800052e1  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x1800052e5  lea     rax, [rbp+var_50]
0x1800052e9  mov     rdx, [rbp+Sid]; Sid
0x1800052ed  lea     r8, [rbp+cbSid]; cbSid
0x1800052f1  mov     [rsp+80h+peUse], rax; peUse
0x1800052f6  mov     rcx, rdi; lpAccountName
0x1800052f9  lea     rax, [rbp+arg_10]
0x1800052fd  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180005302  call    cs:__imp_LookupAccountNameLocalW
0x180005308  test    eax, eax
0x18000530a  jnz     short loc_18000532D
0x18000530c  call    cs:__imp_GetLastError
0x180005312  mov     edi, eax
0x180005314  test    eax, eax
0x180005316  jle     short loc_180005321
0x180005318  movzx   edi, ax
0x18000531b  or      edi, 80070000h
0x180005321  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x180005325  call    cs:__imp_SysFreeString
0x18000532b  jmp     short loc_180005389
0x18000532d  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x180005331  call    cs:__imp_SysFreeString
0x180005337  mov     r8d, [rbp+var_50]
0x18000533b  cmp     r8d, 3
0x18000533f  jz      short loc_180005350
0x180005341  test    r8d, r8d
0x180005344  jle     short loc_180005350
0x180005346  cmp     r8d, 6
0x18000534a  jl      loc_1800051DB
0x180005350  mov     rcx, cs:WPP_GLOBAL_Control
0x180005357  lea     rax, WPP_GLOBAL_Control
0x18000535e  cmp     rcx, rax
0x180005361  jz      short loc_180005384
0x180005363  test    byte ptr [rcx+1Ch], 80h
0x180005367  jz      short loc_180005384
0x180005369  cmp     byte ptr [rcx+19h], 2
0x18000536d  jb      short loc_180005384
0x18000536f  mov     rcx, [rcx+10h]
0x180005373  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18000537a  mov     edx, 16h
0x18000537f  call    WPP_SF_
0x180005384  mov     edi, 80070057h
0x180005389  mov     rcx, [rbp+Sid]; hMem
0x18000538d  test    rcx, rcx
0x180005390  jz      short loc_180005398
0x180005392  call    cs:__imp_LocalFree
0x180005398  lea     r11, [rsp+80h+var_s0]
0x1800053a0  mov     eax, edi
0x1800053a2  mov     rsi, [r11+10h]
0x1800053a6  mov     rdi, [r11+18h]
0x1800053aa  mov     rsp, r11
0x1800053ad  pop     rbp
0x1800053ae  retn
```
