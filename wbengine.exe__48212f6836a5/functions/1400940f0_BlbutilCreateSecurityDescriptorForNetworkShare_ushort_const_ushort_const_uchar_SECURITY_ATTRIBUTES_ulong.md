# BlbutilCreateSecurityDescriptorForNetworkShare(ushort const *,ushort const *,uchar,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400940f0`
- end: `0x1400945c8`
- name: `?BlbutilCreateSecurityDescriptorForNetworkShare@@YAJPEBG0EPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `1240`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, LPCWSTR lpAccountName@<rdx>, unsigned __int8@<r8b>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14008e584`
- `0x1400efa40`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014384`
- `0x140014448`
- `0x140087bf4`
- `0x1400940f0`
- `0x140094600`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x14009422b`
- `ADVAPI32!LookupAccountNameW` at `0x140094329`
- `ADVAPI32!LookupAccountNameW` at `0x14009422b`
- `ADVAPI32!LookupAccountNameW` at `0x140094329`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14009442c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14009442c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140094514`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140094514`
- `KERNEL32!LocalFree` at `0x140094596`
- `KERNEL32!LocalFree` at `0x140094596`
- `KERNEL32!GetLastError` at `0x140094235`
- `KERNEL32!GetLastError` at `0x140094240`
- `KERNEL32!GetLastError` at `0x140094333`
- `KERNEL32!GetLastError` at `0x140094436`
- `KERNEL32!GetLastError` at `0x14009451e`
- `KERNEL32!GetLastError` at `0x140094235`
- `KERNEL32!GetLastError` at `0x140094240`
- `KERNEL32!GetLastError` at `0x140094333`
- `KERNEL32!GetLastError` at `0x140094436`
- `KERNEL32!GetLastError` at `0x14009451e`
- `ole32!CoTaskMemAlloc` at `0x1400942af`
- `ole32!CoTaskMemAlloc` at `0x1400942dd`
- `ole32!CoTaskMemAlloc` at `0x1400942af`
- `ole32!CoTaskMemAlloc` at `0x1400942dd`
- `ole32!CoTaskMemFree` at `0x140094577`
- `ole32!CoTaskMemFree` at `0x140094582`
- `ole32!CoTaskMemFree` at `0x14009458b`
- `ole32!CoTaskMemFree` at `0x140094577`
- `ole32!CoTaskMemFree` at `0x140094582`
- `ole32!CoTaskMemFree` at `0x14009458b`

## string_xrefs

- `0x14009414b`: `wszFilePath`
- `0x140094144`: `base\stor\blb\util\securityutils.cpp`
- `0x140094166`: `base\stor\blb\util\securityutils.cpp`

## pseudocode

```c
__int64 __fastcall BlbutilCreateSecurityDescriptorForNetworkShare(
        const unsigned __int16 *a1,
        LPCWSTR lpAccountName,
        char a3,
        struct _SECURITY_ATTRIBUTES *a4,
        unsigned int *a5)
{
  void *v8; // r13
  int MachineNameFromSharePath; // eax
  WCHAR *v10; // r12
  int IsDomainUser; // ebx
  signed int LastError; // eax
  _QWORD *v13; // rcx
  int v14; // edx
  void *v15; // rax
  void *v16; // rax
  WCHAR *ReferencedDomainName; // rbx
  signed int v18; // eax
  signed int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  signed int v22; // eax
  unsigned __int8 v24; // [rsp+40h] [rbp-C0h] BYREF
  char v25; // [rsp+41h] [rbp-BFh]
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSystemName; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h]
  unsigned int *v34; // [rsp+78h] [rbp-88h]
  WCHAR StringSecurityDescriptor[1024]; // [rsp+80h] [rbp-80h] BYREF

  v25 = a3;
  v34 = a5;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\util\\securityutils.cpp", 0x5Du, "wszFilePath");
  if ( !lpAccountName )
    BlbAssert("base\\stor\\blb\\util\\securityutils.cpp", 0x5Eu, "wszUserName");
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  StringSid = 0;
  v8 = 0;
  lpSystemName = 0;
  pv = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  cbSid = 0;
  v24 = 0;
  *a5 = 0;
  MachineNameFromSharePath = BlbutilGetMachineNameFromSharePath(a1, (unsigned __int16 **)&lpSystemName);
  v10 = (WCHAR *)lpSystemName;
  IsDomainUser = MachineNameFromSharePath;
  if ( MachineNameFromSharePath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids,
        (_DWORD)a1,
        MachineNameFromSharePath);
    }
    goto LABEL_63;
  }
  if ( !LookupAccountNameW(lpSystemName, lpAccountName, 0, &cbSid, 0, &cchReferencedDomainName, &peUse)
    && GetLastError() != 122 )
  {
    LastError = GetLastError();
    IsDomainUser = LastError;
    if ( LastError > 0 )
      IsDomainUser = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 11;
LABEL_18:
      WPP_SF_SSD(
        v13[2],
        v14,
        (unsigned int)WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids,
        (_DWORD)v10,
        (__int64)lpAccountName,
        IsDomainUser);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  v15 = CoTaskMemAlloc(cbSid);
  v8 = v15;
  if ( !v15
    || (memset_0(v15, 0, cbSid),
        v16 = CoTaskMemAlloc(2LL * cchReferencedDomainName),
        pv = v16,
        (ReferencedDomainName = (WCHAR *)v16) == 0) )
  {
    IsDomainUser = -2147024882;
    goto LABEL_63;
  }
  memset_0(v16, 0, 2LL * cchReferencedDomainName);
  if ( !LookupAccountNameW(v10, lpAccountName, v8, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v18 = GetLastError();
    IsDomainUser = v18;
    if ( v18 > 0 )
      IsDomainUser = (unsigned __int16)v18 | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 12;
      goto LABEL_18;
    }
LABEL_19:
    if ( IsDomainUser != -2147023564 )
      goto LABEL_63;
LABEL_20:
    IsDomainUser = -2139619189;
    goto LABEL_63;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids,
      (_DWORD)lpAccountName,
      (__int64)ReferencedDomainName);
  }
  if ( !v25 )
  {
    IsDomainUser = BlbutilIsDomainUser(lpAccountName, v10, (bool *)&v24);
    if ( IsDomainUser < 0 )
      goto LABEL_63;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids,
          lpAccountName);
      }
      goto LABEL_20;
    }
  }
  if ( ConvertSidToStringSidW(v8, &StringSid) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v10, (__int64)StringSid);
    }
    memset_0(StringSecurityDescriptor, 0, sizeof(StringSecurityDescriptor));
    IsDomainUser = StringCchPrintfW(
                     StringSecurityDescriptor,
                     0x400u,
                     L"O:%wsD:AR(A;OICI;FA;;;BA)(A;OICI;FA;;;BO)(A;OICI;FA;;;CO)(A;OICI;FA;;;%ws)");
    if ( IsDomainUser >= 0 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             StringSecurityDescriptor,
             1u,
             &SecurityDescriptor,
             &SecurityDescriptorSize) )
      {
        *v34 = SecurityDescriptorSize;
        a4->lpSecurityDescriptor = SecurityDescriptor;
        a4->bInheritHandle = 0;
        a4->nLength = 24;
        goto LABEL_63;
      }
      v22 = GetLastError();
      IsDomainUser = v22;
      if ( v22 > 0 )
        IsDomainUser = (unsigned __int16)v22 | 0x80070000;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 17;
        goto LABEL_49;
      }
    }
  }
  else
  {
    v19 = GetLastError();
    IsDomainUser = v19;
    if ( v19 > 0 )
      IsDomainUser = (unsigned __int16)v19 | 0x80070000;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 15;
LABEL_49:
      WPP_SF_d(v20[2], v21, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids);
    }
  }
LABEL_63:
  CoTaskMemFree(v10);
  CoTaskMemFree(pv);
  CoTaskMemFree(v8);
  LocalFree(StringSid);
  return (unsigned int)IsDomainUser;
}

```

## disassembly

```asm
0x1400940f0  mov     [rsp-8+arg_10], rbx
0x1400940f5  push    rbp
0x1400940f6  push    rsi
0x1400940f7  push    rdi
0x1400940f8  push    r12
0x1400940fa  push    r13
0x1400940fc  push    r14
0x1400940fe  push    r15
0x140094100  lea     rbp, [rsp-790h]
0x140094108  sub     rsp, 890h
0x14009410f  mov     rax, cs:__security_cookie
0x140094116  xor     rax, rsp
0x140094119  mov     [rbp+7C0h+var_40], rax
0x140094120  mov     rbx, [rbp+7C0h+arg_20]
0x140094127  xor     edi, edi
0x140094129  mov     [rsp+8C0h+var_87F], r8b
0x14009412e  mov     r15, r9
0x140094131  mov     [rsp+8C0h+var_848], rbx
0x140094136  mov     rsi, rdx
0x140094139  mov     r14, rcx
0x14009413c  test    rcx, rcx
0x14009413f  jnz     short loc_140094157
0x140094141  lea     edx, [rcx+5Dh]; unsigned int
0x140094144  lea     rcx, aBaseStorBlbUti_2; "base\\stor\\blb\\util\\securityutils.cp"...
0x14009414b  lea     r8, aWszfilepath; "wszFilePath"
0x140094152  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140094157  test    rsi, rsi
0x14009415a  jnz     short loc_140094172
0x14009415c  lea     r8, aWszusername; "wszUserName"
0x140094163  lea     edx, [rsi+5Eh]; unsigned int
0x140094166  lea     rcx, aBaseStorBlbUti_2; "base\\stor\\blb\\util\\securityutils.cp"...
0x14009416d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140094172  lea     rdx, [rsp+8C0h+lpSystemName]; unsigned __int16 **
0x140094177  mov     [rsp+8C0h+SecurityDescriptor], rdi
0x14009417c  mov     rcx, r14; unsigned __int16 *
0x14009417f  mov     [rsp+8C0h+SecurityDescriptorSize], edi
0x140094183  mov     [rsp+8C0h+StringSid], rdi
0x140094188  mov     r13, rdi
0x14009418b  mov     [rsp+8C0h+lpSystemName], rdi
0x140094190  mov     [rsp+8C0h+pv], rdi
0x140094195  mov     [rsp+8C0h+var_87C], edi
0x140094199  mov     [rsp+8C0h+var_874], edi
0x14009419d  mov     [rsp+8C0h+cbSid], edi
0x1400941a1  mov     [rsp+8C0h+var_880], dil
0x1400941a6  mov     [rbx], edi
0x1400941a8  call    ?BlbutilGetMachineNameFromSharePath@@YAJPEBGPEAPEAG@Z; BlbutilGetMachineNameFromSharePath(ushort const *,ushort * *)
0x1400941ad  mov     r12, [rsp+8C0h+lpSystemName]
0x1400941b2  mov     ebx, eax
0x1400941b4  test    eax, eax
0x1400941b6  jns     short loc_140094204
0x1400941b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400941bf  lea     rdi, WPP_GLOBAL_Control
0x1400941c6  cmp     rcx, rdi
0x1400941c9  jz      loc_140094574
0x1400941cf  test    byte ptr [rcx+1Ch], 1
0x1400941d3  jz      loc_140094574
0x1400941d9  cmp     byte ptr [rcx+19h], 2
0x1400941dd  jb      loc_140094574
0x1400941e3  mov     rcx, [rcx+10h]
0x1400941e7  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x1400941ee  mov     edx, 0Ah
0x1400941f3  mov     dword ptr [rsp+8C0h+ReferencedDomainName], eax
0x1400941f7  mov     r9, r14
0x1400941fa  call    WPP_SF_Sd
0x1400941ff  jmp     loc_140094574
0x140094204  lea     rax, [rsp+8C0h+var_874]
0x140094209  xor     r8d, r8d; Sid
0x14009420c  mov     [rsp+8C0h+peUse], rax; peUse
0x140094211  lea     r9, [rsp+8C0h+cbSid]; cbSid
0x140094216  lea     rax, [rsp+8C0h+var_87C]
0x14009421b  mov     rdx, rsi; lpAccountName
0x14009421e  mov     [rsp+8C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140094223  mov     rcx, r12; lpSystemName
0x140094226  mov     [rsp+8C0h+ReferencedDomainName], rdi; ReferencedDomainName
0x14009422b  call    cs:__imp_LookupAccountNameW
0x140094231  test    eax, eax
0x140094233  jnz     short loc_1400942AB
0x140094235  call    cs:__imp_GetLastError
0x14009423b  cmp     eax, 7Ah ; 'z'
0x14009423e  jz      short loc_1400942AB
0x140094240  call    cs:__imp_GetLastError
0x140094246  mov     ebx, eax
0x140094248  test    eax, eax
0x14009424a  jle     short loc_140094255
0x14009424c  movzx   ebx, ax
0x14009424f  or      ebx, 80070000h
0x140094255  mov     rcx, cs:WPP_GLOBAL_Control
0x14009425c  lea     rdi, WPP_GLOBAL_Control
0x140094263  cmp     rcx, rdi
0x140094266  jz      short loc_140094295
0x140094268  test    byte ptr [rcx+1Ch], 1
0x14009426c  jz      short loc_140094295
0x14009426e  cmp     byte ptr [rcx+19h], 2
0x140094272  jb      short loc_140094295
0x140094274  mov     edx, 0Bh
0x140094279  mov     rcx, [rcx+10h]
0x14009427d  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x140094284  mov     dword ptr [rsp+8C0h+cchReferencedDomainName], ebx
0x140094288  mov     r9, r12
0x14009428b  mov     [rsp+8C0h+ReferencedDomainName], rsi
0x140094290  call    WPP_SF_SSD
0x140094295  cmp     ebx, 80070534h
0x14009429b  jnz     loc_140094574
0x1400942a1  mov     ebx, 8078008Bh
0x1400942a6  jmp     loc_140094574
0x1400942ab  mov     ecx, [rsp+8C0h+cbSid]; cb
0x1400942af  call    cs:__imp_CoTaskMemAlloc
0x1400942b5  mov     r13, rax
0x1400942b8  test    rax, rax
0x1400942bb  jnz     short loc_1400942C7
0x1400942bd  mov     ebx, 8007000Eh
0x1400942c2  jmp     loc_140094574
0x1400942c7  mov     r8d, [rsp+8C0h+cbSid]; Size
0x1400942cc  xor     edx, edx; Val
0x1400942ce  mov     rcx, r13; void *
0x1400942d1  call    memset_0
0x1400942d6  mov     ecx, [rsp+8C0h+var_87C]
0x1400942da  add     rcx, rcx; cb
0x1400942dd  call    cs:__imp_CoTaskMemAlloc
0x1400942e3  mov     [rsp+8C0h+pv], rax
0x1400942e8  mov     rbx, rax
0x1400942eb  test    rax, rax
0x1400942ee  jz      short loc_1400942BD
0x1400942f0  mov     r8d, [rsp+8C0h+var_87C]
0x1400942f5  xor     edx, edx; Val
0x1400942f7  add     r8, r8; Size
0x1400942fa  mov     rcx, rax; void *
0x1400942fd  call    memset_0
0x140094302  lea     rax, [rsp+8C0h+var_874]
0x140094307  mov     r8, r13; Sid
0x14009430a  mov     [rsp+8C0h+peUse], rax; peUse
0x14009430f  lea     r9, [rsp+8C0h+cbSid]; cbSid
0x140094314  lea     rax, [rsp+8C0h+var_87C]
0x140094319  mov     rdx, rsi; lpAccountName
0x14009431c  mov     [rsp+8C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140094321  mov     rcx, r12; lpSystemName
0x140094324  mov     [rsp+8C0h+ReferencedDomainName], rbx; ReferencedDomainName
0x140094329  call    cs:__imp_LookupAccountNameW
0x14009432f  test    eax, eax
0x140094331  jnz     short loc_14009437D
0x140094333  call    cs:__imp_GetLastError
0x140094339  mov     ebx, eax
0x14009433b  test    eax, eax
0x14009433d  jle     short loc_140094348
0x14009433f  movzx   ebx, ax
0x140094342  or      ebx, 80070000h
0x140094348  mov     rcx, cs:WPP_GLOBAL_Control
0x14009434f  lea     rdi, WPP_GLOBAL_Control
0x140094356  cmp     rcx, rdi
0x140094359  jz      loc_140094295
0x14009435f  test    byte ptr [rcx+1Ch], 1
0x140094363  jz      loc_140094295
0x140094369  cmp     byte ptr [rcx+19h], 2
0x14009436d  jb      loc_140094295
0x140094373  mov     edx, 0Ch
0x140094378  jmp     loc_140094279
0x14009437d  mov     rcx, cs:WPP_GLOBAL_Control
0x140094384  lea     rdi, WPP_GLOBAL_Control
0x14009438b  cmp     rcx, rdi
0x14009438e  jz      short loc_1400943B9
0x140094390  test    byte ptr [rcx+1Ch], 1
0x140094394  jz      short loc_1400943B9
0x140094396  cmp     byte ptr [rcx+19h], 4
0x14009439a  jb      short loc_1400943B9
0x14009439c  mov     rcx, [rcx+10h]
0x1400943a0  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x1400943a7  mov     edx, 0Dh
0x1400943ac  mov     [rsp+8C0h+ReferencedDomainName], rbx
0x1400943b1  mov     r9, rsi
0x1400943b4  call    WPP_SF_SS
0x1400943b9  xor     r14d, r14d
0x1400943bc  cmp     [rsp+8C0h+var_87F], r14b
0x1400943c1  jnz     short loc_140094424
0x1400943c3  lea     r8, [rsp+8C0h+var_880]; unsigned __int8 *
0x1400943c8  mov     rdx, r12; lpSystemName
0x1400943cb  mov     rcx, rsi; lpAccountName
0x1400943ce  call    ?BlbutilIsDomainUser@@YAJPEBG0PEAE@Z; BlbutilIsDomainUser(ushort const *,ushort const *,uchar *)
0x1400943d3  mov     ebx, eax
0x1400943d5  test    eax, eax
0x1400943d7  js      loc_140094574
0x1400943dd  cmp     [rsp+8C0h+var_880], r14b
0x1400943e2  jz      short loc_140094424
0x1400943e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400943eb  cmp     rcx, rdi
0x1400943ee  jz      loc_1400942A1
0x1400943f4  test    byte ptr [rcx+1Ch], 1
0x1400943f8  jz      loc_1400942A1
0x1400943fe  cmp     byte ptr [rcx+19h], 2
0x140094402  jb      loc_1400942A1
0x140094408  mov     rcx, [rcx+10h]
0x14009440c  lea     edx, [r14+0Eh]
0x140094410  mov     r9, rsi
0x140094413  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x14009441a  call    WPP_SF_S
0x14009441f  jmp     loc_1400942A1
0x140094424  lea     rdx, [rsp+8C0h+StringSid]; StringSid
0x140094429  mov     rcx, r13; Sid
0x14009442c  call    cs:__imp_ConvertSidToStringSidW
0x140094432  test    eax, eax
0x140094434  jnz     short loc_14009448C
0x140094436  call    cs:__imp_GetLastError
0x14009443c  mov     ebx, eax
0x14009443e  test    eax, eax
0x140094440  jle     short loc_14009444B
0x140094442  movzx   ebx, ax
0x140094445  or      ebx, 80070000h
0x14009444b  mov     rcx, cs:WPP_GLOBAL_Control
0x140094452  cmp     rcx, rdi
0x140094455  jz      loc_140094574
0x14009445b  test    byte ptr [rcx+1Ch], 1
0x14009445f  jz      loc_140094574
0x140094465  cmp     byte ptr [rcx+19h], 2
0x140094469  jb      loc_140094574
0x14009446f  mov     edx, 0Fh
0x140094474  mov     rcx, [rcx+10h]
0x140094478  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x14009447f  mov     r9d, ebx
0x140094482  call    WPP_SF_d
0x140094487  jmp     loc_140094574
0x14009448c  mov     rcx, cs:WPP_GLOBAL_Control
0x140094493  cmp     rcx, rdi
0x140094496  jz      short loc_1400944CB
0x140094498  test    byte ptr [rcx+1Ch], 1
0x14009449c  jz      short loc_1400944CB
0x14009449e  cmp     byte ptr [rcx+19h], 4
0x1400944a2  jb      short loc_1400944CB
0x1400944a4  mov     rax, [rsp+8C0h+StringSid]
0x1400944a9  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x1400944b0  mov     rcx, [rcx+10h]; LoggerHandle
0x1400944b4  mov     edx, 10h
0x1400944b9  mov     [rsp+8C0h+cchReferencedDomainName], rax; __int64
0x1400944be  mov     r9, rsi
0x1400944c1  mov     [rsp+8C0h+ReferencedDomainName], r12; __int64
0x1400944c6  call    WPP_SF_SSS
0x1400944cb  xor     edx, edx; Val
0x1400944cd  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; void *
0x1400944d1  mov     r8d, 800h; Size
0x1400944d7  call    memset_0
0x1400944dc  mov     r9, [rsp+8C0h+StringSid]
0x1400944e1  lea     r8, aOWsdArAOiciFaB; "O:%wsD:AR(A;OICI;FA;;;BA)(A;OICI;FA;;;B"...
0x1400944e8  mov     edx, 400h; unsigned __int64
0x1400944ed  mov     [rsp+8C0h+ReferencedDomainName], r9
0x1400944f2  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; unsigned __int16 *
0x1400944f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400944fb  mov     ebx, eax
0x1400944fd  test    eax, eax
0x1400944ff  js      short loc_140094574
0x140094501  lea     r9, [rsp+8C0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x140094506  mov     edx, 1; StringSDRevision
0x14009450b  lea     r8, [rsp+8C0h+SecurityDescriptor]; SecurityDescriptor
0x140094510  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140094514  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14009451a  test    eax, eax
0x14009451c  jnz     short loc_140094555
0x14009451e  call    cs:__imp_GetLastError
0x140094524  mov     ebx, eax
0x140094526  test    eax, eax
0x140094528  jle     short loc_140094533
0x14009452a  movzx   ebx, ax
0x14009452d  or      ebx, 80070000h
0x140094533  mov     rcx, cs:WPP_GLOBAL_Control
0x14009453a  cmp     rcx, rdi
0x14009453d  jz      short loc_140094574
0x14009453f  test    byte ptr [rcx+1Ch], 1
0x140094543  jz      short loc_140094574
0x140094545  cmp     byte ptr [rcx+19h], 2
0x140094549  jb      short loc_140094574
0x14009454b  mov     edx, 11h
0x140094550  jmp     loc_140094474
0x140094555  mov     eax, [rsp+8C0h+SecurityDescriptorSize]
0x140094559  mov     rcx, [rsp+8C0h+var_848]
0x14009455e  mov     [rcx], eax
0x140094560  mov     rax, [rsp+8C0h+SecurityDescriptor]
0x140094565  mov     [r15+8], rax
0x140094569  mov     [r15+10h], r14d
0x14009456d  mov     dword ptr [r15], 18h
0x140094574  mov     rcx, r12; pv
0x140094577  call    cs:__imp_CoTaskMemFree
0x14009457d  mov     rcx, [rsp+8C0h+pv]; pv
0x140094582  call    cs:__imp_CoTaskMemFree
0x140094588  mov     rcx, r13; pv
0x14009458b  call    cs:__imp_CoTaskMemFree
0x140094591  mov     rcx, [rsp+8C0h+StringSid]; hMem
0x140094596  call    cs:__imp_LocalFree
0x14009459c  mov     eax, ebx
0x14009459e  mov     rcx, [rbp+7C0h+var_40]
0x1400945a5  xor     rcx, rsp; StackCookie
0x1400945a8  call    __security_check_cookie
0x1400945ad  mov     rbx, [rsp+8C0h+arg_10]
0x1400945b5  add     rsp, 890h
0x1400945bc  pop     r15
0x1400945be  pop     r14
0x1400945c0  pop     r13
0x1400945c2  pop     r12
0x1400945c4  pop     rdi
0x1400945c5  pop     rsi
0x1400945c6  pop     rbp
0x1400945c7  retn
```
