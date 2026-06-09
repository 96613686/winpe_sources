# User::FromUsername(User &,ushort const *)

- ea: `0x1800053e8`
- end: `0x180005648`
- name: `?FromUsername@User@@SAJAEAV1@PEBG@Z`
- size: `608`
- prototype: `__int64 __fastcall(struct User *this, LPCWSTR lpAccountName)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004a40`
- `0x180016620`
- `0x180018870`
- `0x180019214`
- `0x18001c21c`
- `0x180022ae0`
- `0x1800232b0`

## callees

- `0x180005184`
- `0x1800053e8`
- `0x180008c4c`
- `0x180010570`
- `0x18001acc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000548b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000558c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000548b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000558c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800054b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800054b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005624`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005624`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055bd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180005427`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180005427`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000546e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000557c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000546e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000557c`

## pseudocode

```c
__int64 __fastcall User::FromUsername(struct User *this, LPCWSTR lpAccountName)
{
  enum _SID_NAME_USE v4; // r8d
  unsigned int v5; // edi
  signed int v6; // eax
  int v7; // edx
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
      v15 = byte_180052608;
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
0x1800053e8  mov     [rsp-8+arg_0], rsi
0x1800053ed  mov     [rsp-8+arg_8], rdi
0x1800053f2  push    rbp
0x1800053f3  mov     rbp, rsp
0x1800053f6  sub     rsp, 80h
0x1800053fd  mov     rdi, rdx
0x180005400  mov     [rbp+arg_10], 0
0x180005407  mov     rsi, rcx
0x18000540a  mov     [rbp+cbSid], 0
0x180005411  mov     rcx, rdi; StringSid
0x180005414  mov     [rbp+Sid], 0
0x18000541c  lea     rdx, [rbp+Sid]; Sid
0x180005420  mov     [rbp+var_50], 8
0x180005427  call    cs:__imp_ConvertStringSidToSidW
0x18000542e  nop     dword ptr [rax+rax+00h]
0x180005433  test    eax, eax
0x180005435  jz      short loc_180005450
0x180005437  mov     r8d, 8; enum _SID_NAME_USE
0x18000543d  mov     rdx, [rbp+Sid]; void *
0x180005441  mov     rcx, rsi; this
0x180005444  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180005449  mov     edi, eax
0x18000544b  jmp     loc_18000561B
0x180005450  lea     rax, [rbp+var_50]
0x180005454  xor     r9d, r9d; ReferencedDomainName
0x180005457  mov     [rsp+80h+peUse], rax; peUse
0x18000545c  lea     r8, [rbp+cbSid]; cbSid
0x180005460  lea     rax, [rbp+arg_10]
0x180005464  xor     edx, edx; Sid
0x180005466  mov     rcx, rdi; lpAccountName
0x180005469  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000546e  call    cs:__imp_LookupAccountNameLocalW
0x180005475  nop     dword ptr [rax+rax+00h]
0x18000547a  call    cs:__imp_GetLastError
0x180005481  nop     dword ptr [rax+rax+00h]
0x180005486  cmp     eax, 7Ah ; 'z'
0x180005489  jz      short loc_1800054AF
0x18000548b  call    cs:__imp_GetLastError
0x180005492  nop     dword ptr [rax+rax+00h]
0x180005497  mov     edi, eax
0x180005499  test    eax, eax
0x18000549b  jle     loc_18000561B
0x1800054a1  movzx   edi, ax
0x1800054a4  or      edi, 80070000h
0x1800054aa  jmp     loc_18000561B
0x1800054af  mov     edx, [rbp+cbSid]
0x1800054b2  xor     ecx, ecx; uFlags
0x1800054b4  inc     edx; uBytes
0x1800054b6  call    cs:__imp_LocalAlloc
0x1800054bd  nop     dword ptr [rax+rax+00h]
0x1800054c2  mov     [rbp+Sid], rax
0x1800054c6  test    rax, rax
0x1800054c9  jnz     short loc_180005549
0x1800054cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054d2  lea     rax, WPP_GLOBAL_Control
0x1800054d9  cmp     rcx, rax
0x1800054dc  jz      short loc_1800054FF
0x1800054de  test    byte ptr [rcx+1Ch], 80h
0x1800054e2  jz      short loc_1800054FF
0x1800054e4  cmp     byte ptr [rcx+19h], 2
0x1800054e8  jb      short loc_1800054FF
0x1800054ea  mov     rcx, [rcx+10h]
0x1800054ee  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800054f5  mov     edx, 15h
0x1800054fa  call    WPP_SF_
0x1800054ff  lea     rax, byte_180052608
0x180005506  mov     [rbp+var_30], 0
0x18000550a  mov     [rbp+var_28], rax
0x18000550e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180005515  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000551c  mov     [rbp+var_20], 0
0x180005524  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005528  mov     [rbp+pExceptionObject], rax
0x18000552c  mov     [rbp+var_18], 0
0x180005534  mov     [rbp+var_10], 0Eh
0x18000553b  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180005543  call    _CxxThrowException_0
0x180005549  mov     edx, [rbp+arg_10]; int
0x18000554c  lea     rcx, [rbp+ReferencedDomainName]; this
0x180005550  lea     eax, [rdx+1]
0x180005553  mov     [rbp+arg_10], eax
0x180005556  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18000555b  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x18000555f  lea     rax, [rbp+var_50]
0x180005563  mov     rdx, [rbp+Sid]; Sid
0x180005567  lea     r8, [rbp+cbSid]; cbSid
0x18000556b  mov     [rsp+80h+peUse], rax; peUse
0x180005570  mov     rcx, rdi; lpAccountName
0x180005573  lea     rax, [rbp+arg_10]
0x180005577  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000557c  call    cs:__imp_LookupAccountNameLocalW
0x180005583  nop     dword ptr [rax+rax+00h]
0x180005588  test    eax, eax
0x18000558a  jnz     short loc_1800055B9
0x18000558c  call    cs:__imp_GetLastError
0x180005593  nop     dword ptr [rax+rax+00h]
0x180005598  mov     edi, eax
0x18000559a  test    eax, eax
0x18000559c  jle     short loc_1800055A7
0x18000559e  movzx   edi, ax
0x1800055a1  or      edi, 80070000h
0x1800055a7  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x1800055ab  call    cs:__imp_SysFreeString
0x1800055b2  nop     dword ptr [rax+rax+00h]
0x1800055b7  jmp     short loc_18000561B
0x1800055b9  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x1800055bd  call    cs:__imp_SysFreeString
0x1800055c4  nop     dword ptr [rax+rax+00h]
0x1800055c9  mov     r8d, [rbp+var_50]
0x1800055cd  cmp     r8d, 3
0x1800055d1  jz      short loc_1800055E2
0x1800055d3  test    r8d, r8d
0x1800055d6  jle     short loc_1800055E2
0x1800055d8  cmp     r8d, 6
0x1800055dc  jl      loc_18000543D
0x1800055e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e9  lea     rax, WPP_GLOBAL_Control
0x1800055f0  cmp     rcx, rax
0x1800055f3  jz      short loc_180005616
0x1800055f5  test    byte ptr [rcx+1Ch], 80h
0x1800055f9  jz      short loc_180005616
0x1800055fb  cmp     byte ptr [rcx+19h], 2
0x1800055ff  jb      short loc_180005616
0x180005601  mov     rcx, [rcx+10h]
0x180005605  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18000560c  mov     edx, 16h
0x180005611  call    WPP_SF_
0x180005616  mov     edi, 80070057h
0x18000561b  mov     rcx, [rbp+Sid]; hMem
0x18000561f  test    rcx, rcx
0x180005622  jz      short loc_180005630
0x180005624  call    cs:__imp_LocalFree
0x18000562b  nop     dword ptr [rax+rax+00h]
0x180005630  lea     r11, [rsp+80h+var_s0]
0x180005638  mov     eax, edi
0x18000563a  mov     rsi, [r11+10h]
0x18000563e  mov     rdi, [r11+18h]
0x180005642  mov     rsp, r11
0x180005645  pop     rbp
0x180005646  retn
```
