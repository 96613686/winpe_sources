# WdcGetProcessUserName(ulong,_FILETIME const *,ushort * *)

- ea: `0x18007ff4c`
- end: `0x1800801a0`
- name: `?WdcGetProcessUserName@@YAJKPEBU_FILETIME@@PEAPEAG@Z`
- size: `596`
- prototype: `__int64 __fastcall(unsigned int, const struct _FILETIME *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d4a0`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x18007ff4c`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x18007ffbc`
- `ADVAPI32!CreateWellKnownSid` at `0x18007ffbc`
- `ADVAPI32!IsValidSid` at `0x1800800d0`
- `ADVAPI32!IsValidSid` at `0x1800800d0`
- `KERNEL32!GetLastError` at `0x180080163`
- `KERNEL32!GetLastError` at `0x180080163`
- `OLEAUT32!__imp_SysAllocString` at `0x18008002c`
- `OLEAUT32!__imp_SysAllocString` at `0x180080124`
- `OLEAUT32!__imp_SysAllocString` at `0x18008002c`
- `OLEAUT32!__imp_SysAllocString` at `0x180080124`
- `OLEAUT32!__imp_SysFreeString` at `0x18008001c`
- `OLEAUT32!__imp_SysFreeString` at `0x180080116`
- `OLEAUT32!__imp_SysFreeString` at `0x18008001c`
- `OLEAUT32!__imp_SysFreeString` at `0x180080116`
- `WINSTA!WinStationGetProcessSid` at `0x180080087`
- `WINSTA!WinStationGetProcessSid` at `0x1800800bf`
- `WINSTA!WinStationGetProcessSid` at `0x180080087`
- `WINSTA!WinStationGetProcessSid` at `0x1800800bf`
- `UTILDLL!CachedGetUserFromSid` at `0x180080108`
- `UTILDLL!CachedGetUserFromSid` at `0x180080108`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180080003`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180080003`

## pseudocode

```c
__int64 __fastcall WdcGetProcessUserName(unsigned int a1, const struct _FILETIME *a2, unsigned __int16 **a3)
{
  unsigned int v3; // ebx
  unsigned __int16 *v7; // rax
  __int64 v9; // r8
  const char *v10; // rdx
  int v11; // r8d
  void *v12; // rsi
  const char *v13; // rdx
  int v14; // r8d
  unsigned __int16 *v15; // rax
  signed int LastError; // eax
  LPDWORD cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v22; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR ReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[526]; // [rsp+42h] [rbp-BEh] BYREF
  _BYTE pSid[256]; // [rsp+250h] [rbp+150h] BYREF

  v3 = 0;
  if ( (a1 & 0xFFFFFFFA) != 0 || a1 == 5 )
  {
    v9 = (__int64)*a2;
    cbSid = 0;
    if ( !(unsigned __int8)WinStationGetProcessSid(0, a1, v9, 0, &cbSid) )
    {
      v12 = WdcAlloc(cbSid, v10, v11);
      if ( v12 )
      {
        if ( (unsigned __int8)WinStationGetProcessSid(0, a1, *a2, v12, &cbSid) && IsValidSid(v12) )
        {
          ReferencedDomainName = 0;
          memset_0(v24, 0, 0x206u);
          cchName = 260;
          CachedGetUserFromSid(v12, &ReferencedDomainName, &cchName);
          if ( *a3 )
          {
            SysFreeString(*a3);
            *a3 = 0;
          }
          v15 = SysAllocString(&ReferencedDomainName);
          if ( v15 )
          {
            *a3 = v15;
          }
          else
          {
            LODWORD(cchReferencedDomainNamea) = -2147024882;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
              "WdcAssignString",
              0,
              L"FAILURE: 0x%08x",
              cchReferencedDomainNamea);
          }
        }
        WdcFree(v12, v13, v14);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    if ( !word_1800B5570 )
    {
      cbSid = 256;
      if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
      {
        peUse = 0;
        v22 = 128;
        cchName = 128;
        if ( !LookupAccountSidLocalW(pSid, &word_1800B5570, &cchName, &ReferencedDomainName, &v22, &peUse) )
          word_1800B5570 = 0;
      }
    }
    if ( *a3 )
    {
      SysFreeString(*a3);
      *a3 = 0;
    }
    v7 = SysAllocString(&word_1800B5570);
    if ( !v7 )
    {
      LODWORD(cchReferencedDomainName) = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        cchReferencedDomainName);
      return 2147942414LL;
    }
    *a3 = v7;
  }
  return v3;
}

```

## disassembly

```asm
0x18007ff4c  mov     [rsp-8+arg_18], rbx
0x18007ff51  push    rbp
0x18007ff52  push    rsi
0x18007ff53  push    rdi
0x18007ff54  push    r14
0x18007ff56  push    r15
0x18007ff58  lea     rbp, [rsp-260h]
0x18007ff60  sub     rsp, 360h
0x18007ff67  mov     rax, cs:__security_cookie
0x18007ff6e  xor     rax, rsp
0x18007ff71  mov     [rbp+280h+var_30], rax
0x18007ff78  xor     ebx, ebx
0x18007ff7a  mov     rdi, r8
0x18007ff7d  mov     r15, rdx
0x18007ff80  mov     r14d, ecx
0x18007ff83  test    ecx, 0FFFFFFFAh
0x18007ff89  jnz     loc_18008006E
0x18007ff8f  cmp     ecx, 5
0x18007ff92  jz      loc_18008006E
0x18007ff98  xor     eax, eax
0x18007ff9a  cmp     ax, cs:word_1800B5570
0x18007ffa1  jnz     short loc_180080014
0x18007ffa3  lea     r9, [rsp+380h+cbSid]; cbSid
0x18007ffa8  mov     [rsp+380h+cbSid], 100h
0x18007ffb0  lea     r8, [rbp+280h+pSid]; pSid
0x18007ffb7  xor     edx, edx; DomainSid
0x18007ffb9  lea     ecx, [rbx+16h]; WellKnownSidType
0x18007ffbc  call    cs:__imp_CreateWellKnownSid
0x18007ffc2  test    eax, eax
0x18007ffc4  jz      short loc_180080014
0x18007ffc6  mov     eax, 80h
0x18007ffcb  mov     [rsp+380h+var_348], ebx
0x18007ffcf  mov     [rsp+380h+var_344], eax
0x18007ffd3  lea     r9, [rsp+380h+ReferencedDomainName]; ReferencedDomainName
0x18007ffd8  mov     [rsp+380h+cchName], eax
0x18007ffdc  lea     r8, [rsp+380h+cchName]; cchName
0x18007ffe1  lea     rax, [rsp+380h+var_348]
0x18007ffe6  mov     [rsp+380h+peUse], rax; peUse
0x18007ffeb  lea     rdx, word_1800B5570; Name
0x18007fff2  lea     rax, [rsp+380h+var_344]
0x18007fff7  lea     rcx, [rbp+280h+pSid]; Sid
0x18007fffe  mov     [rsp+380h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180080003  call    cs:__imp_LookupAccountSidLocalW
0x180080009  test    eax, eax
0x18008000b  jnz     short loc_180080014
0x18008000d  mov     cs:word_1800B5570, ax
0x180080014  mov     rcx, [rdi]; bstrString
0x180080017  test    rcx, rcx
0x18008001a  jz      short loc_180080025
0x18008001c  call    cs:__imp_SysFreeString
0x180080022  mov     [rdi], rbx
0x180080025  lea     rcx, word_1800B5570; psz
0x18008002c  call    cs:__imp_SysAllocString
0x180080032  test    rax, rax
0x180080035  jnz     short loc_180080066
0x180080037  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18008003e  mov     dword ptr [rsp+380h+cchReferencedDomainName], 8007000Eh
0x180080046  xor     r8d, r8d; int
0x180080049  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180080050  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180080057  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18008005c  mov     eax, 8007000Eh
0x180080061  jmp     loc_18008017A
0x180080066  mov     [rdi], rax
0x180080069  jmp     loc_180080178
0x18008006e  mov     r8, [rdx]
0x180080071  lea     rax, [rsp+380h+cbSid]
0x180080076  mov     edx, r14d
0x180080079  mov     [rsp+380h+cchReferencedDomainName], rax
0x18008007e  xor     r9d, r9d
0x180080081  mov     [rsp+380h+cbSid], ebx
0x180080085  xor     ecx, ecx
0x180080087  call    cs:__imp_WinStationGetProcessSid
0x18008008d  test    al, al
0x18008008f  jnz     loc_180080178
0x180080095  mov     ecx, [rsp+380h+cbSid]; dwBytes
0x180080099  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18008009e  mov     rsi, rax
0x1800800a1  test    rax, rax
0x1800800a4  jz      loc_180080163
0x1800800aa  mov     r8, [r15]
0x1800800ad  lea     rax, [rsp+380h+cbSid]
0x1800800b2  mov     r9, rsi
0x1800800b5  mov     [rsp+380h+cchReferencedDomainName], rax
0x1800800ba  mov     edx, r14d
0x1800800bd  xor     ecx, ecx
0x1800800bf  call    cs:__imp_WinStationGetProcessSid
0x1800800c5  test    al, al
0x1800800c7  jz      loc_180080159
0x1800800cd  mov     rcx, rsi; pSid
0x1800800d0  call    cs:__imp_IsValidSid
0x1800800d6  test    eax, eax
0x1800800d8  jz      short loc_180080159
0x1800800da  xor     eax, eax
0x1800800dc  lea     rcx, [rsp+380h+var_33E]; void *
0x1800800e1  xor     edx, edx; Val
0x1800800e3  mov     [rsp+380h+ReferencedDomainName], ax
0x1800800e8  mov     r8d, 206h; Size
0x1800800ee  call    memset_0
0x1800800f3  lea     r8, [rsp+380h+cchName]
0x1800800f8  mov     [rsp+380h+cchName], 104h
0x180080100  lea     rdx, [rsp+380h+ReferencedDomainName]
0x180080105  mov     rcx, rsi
0x180080108  call    cs:__imp_CachedGetUserFromSid
0x18008010e  mov     rcx, [rdi]; bstrString
0x180080111  test    rcx, rcx
0x180080114  jz      short loc_18008011F
0x180080116  call    cs:__imp_SysFreeString
0x18008011c  mov     [rdi], rbx
0x18008011f  lea     rcx, [rsp+380h+ReferencedDomainName]; psz
0x180080124  call    cs:__imp_SysAllocString
0x18008012a  test    rax, rax
0x18008012d  jnz     short loc_180080156
0x18008012f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180080136  mov     dword ptr [rsp+380h+cchReferencedDomainName], 8007000Eh
0x18008013e  xor     r8d, r8d; int
0x180080141  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180080148  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18008014f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180080154  jmp     short loc_180080159
0x180080156  mov     [rdi], rax
0x180080159  mov     rcx, rsi; void *
0x18008015c  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180080161  jmp     short loc_180080178
0x180080163  call    cs:__imp_GetLastError
0x180080169  mov     ebx, eax
0x18008016b  test    eax, eax
0x18008016d  jle     short loc_180080178
0x18008016f  movzx   ebx, ax
0x180080172  or      ebx, 80070000h
0x180080178  mov     eax, ebx
0x18008017a  mov     rcx, [rbp+280h+var_30]
0x180080181  xor     rcx, rsp; StackCookie
0x180080184  call    __security_check_cookie
0x180080189  mov     rbx, [rsp+380h+arg_18]
0x180080191  add     rsp, 360h
0x180080198  pop     r15
0x18008019a  pop     r14
0x18008019c  pop     rdi
0x18008019d  pop     rsi
0x18008019e  pop     rbp
0x18008019f  retn
```
