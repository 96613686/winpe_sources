# GetPrincipalSID(ushort const *,void * *)

- ea: `0x18004eaa8`
- end: `0x18004ef84`
- name: `?GetPrincipalSID@@YAJPEBGPEAPEAX@Z`
- size: `1244`
- prototype: `__int64 __fastcall(char *, void **)`
- caller_count: `25`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000c030`
- `0x18000c0c4`
- `0x18001b018`
- `0x18001ce48`
- `0x1800229d4`
- `0x180022c1c`
- `0x180023044`
- `0x180023164`
- `0x1800234b4`
- `0x180023838`
- `0x180023e5c`
- `0x180024468`
- `0x1800248e4`
- `0x1800260d4`
- `0x1800269c8`
- `0x180037f54`
- `0x180038f7c`
- `0x1800396b4`
- `0x18003a3c8`
- `0x180040550`
- `0x1800405c0`
- `0x180040650`
- `0x180044ea0`
- `0x180046f70`
- `0x180047280`

## callees

- `0x18004c0c7`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004e8c4`
- `0x18004eaa8`
- `0x1800653b4`
- `0x1800653c0`
- `0x18006541c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004ef42`
- `KERNEL32!LocalFree` at `0x18004ef42`
- `ucrtbase_clr0400!_wcslwr` at `0x18004eb7a`
- `ucrtbase_clr0400!_wcslwr` at `0x18004eb7a`
- `ADVAPI32!CopySid` at `0x18004ef1f`
- `ADVAPI32!CopySid` at `0x18004ef1f`
- `ADVAPI32!GetLengthSid` at `0x18004eef7`
- `ADVAPI32!GetLengthSid` at `0x18004eef7`
- `ADVAPI32!IsValidSid` at `0x18004eea4`
- `ADVAPI32!IsValidSid` at `0x18004eea4`
- `ADVAPI32!LookupAccountSidW` at `0x18004eee1`
- `ADVAPI32!LookupAccountSidW` at `0x18004eee1`

## string_xrefs

- `0x18004ecb6`: `local service`
- `0x18004eccd`: `localservice`
- `0x18004ece4`: `nt authority\local service`
- `0x18004ecfb`: `nt authority\localservice`
- `0x18004ed12`: `network service`
- `0x18004ed29`: `networkservice`
- `0x18004ed40`: `nt authority\network service`
- `0x18004ed57`: `nt authority\networkservice`
- `0x18004ee09`: `service`

## pseudocode

```c
__int64 __fastcall GetPrincipalSID(char *a1, void **a2)
{
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  signed __int64 v6; // rbx
  wchar_t v7; // ax
  wchar_t *v8; // rax
  unsigned int v9; // edi
  wchar_t *v10; // rax
  int v11; // eax
  wchar_t *p_String1; // rbx
  const WCHAR *v13; // rcx
  unsigned int LastWin32Error; // eax
  DWORD LengthSid; // ebx
  void *v16; // rax
  PSID Sid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  enum _SID_NAME_USE peUse[4]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String[7]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+6Eh] [rbp-92h]
  wchar_t String1; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Name[256]; // [rsp+460h] [rbp+360h] BYREF

  Sid = 0;
  memset_0(ReferencedDomainName, 0, sizeof(ReferencedDomainName));
  memset_0(Name, 0, sizeof(Name));
  *a2 = 0;
  cchReferencedDomainName = 255;
  v4 = String;
  cchName = 255;
  v5 = 256;
  v6 = a1 - (char *)String;
  do
  {
    if ( v5 == -2147483390 )
      break;
    v7 = *(wchar_t *)((char *)v4 + v6);
    if ( !v7 )
      break;
    *v4++ = v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  v9 = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
  {
    _wcslwr(String);
    v10 = wcschr_0(String, 0x5Cu);
    if ( v10 && (unsigned int)(v10 - String) == 7 )
    {
      v23 = 0;
      v11 = wcscmp_0(String, L"builtin");
      if ( v11 )
        v23 = 92;
      p_String1 = String;
      if ( !v11 )
        p_String1 = &String1;
    }
    else
    {
      p_String1 = String;
    }
    if ( !wcscmp_0(p_String1, L"administrators") )
    {
      v13 = L"S-1-5-32-544";
    }
    else if ( !wcscmp_0(p_String1, L"system") )
    {
      v13 = L"S-1-5-18";
    }
    else if ( !wcscmp_0(p_String1, L"interactive") )
    {
      v13 = L"S-1-5-4";
    }
    else if ( !wcscmp_0(p_String1, L"everyone") )
    {
      v13 = L"S-1-1-0";
    }
    else if ( !wcscmp_0(p_String1, L"creator owner") )
    {
      v13 = L"S-1-3-0";
    }
    else if ( !wcscmp_0(p_String1, L"authenticated users") )
    {
      v13 = L"S-1-5-11";
    }
    else if ( !wcscmp_0(p_String1, L"performance monitor users") )
    {
      v13 = L"S-1-5-32-558";
    }
    else if ( !wcscmp_0(p_String1, L"local service")
           || !wcscmp_0(p_String1, L"localservice")
           || !wcscmp_0(p_String1, L"nt authority\\local service")
           || !wcscmp_0(p_String1, L"nt authority\\localservice") )
    {
      v13 = L"S-1-5-19";
    }
    else if ( !wcscmp_0(p_String1, L"network service")
           || !wcscmp_0(p_String1, L"networkservice")
           || !wcscmp_0(p_String1, L"nt authority\\network service")
           || !wcscmp_0(p_String1, L"nt authority\\networkservice") )
    {
      v13 = L"S-1-5-20";
    }
    else if ( !wcscmp_0(p_String1, L"iis_iusrs") )
    {
      v13 = L"S-1-5-32-568";
    }
    else if ( !wcscmp_0(p_String1, L"users") )
    {
      v13 = L"S-1-5-32-545";
    }
    else if ( !wcscmp_0(p_String1, L"guests") )
    {
      v13 = L"S-1-5-32-546";
    }
    else if ( !wcscmp_0(p_String1, L"power users") )
    {
      v13 = L"S-1-5-32-547";
    }
    else if ( !wcscmp_0(p_String1, L"batch") )
    {
      v13 = L"S-1-5-3";
    }
    else if ( !wcscmp_0(p_String1, L"service") )
    {
      v13 = L"S-1-5-6";
    }
    else if ( !wcscmp_0(p_String1, L"anonymous") )
    {
      v13 = L"S-1-5-7";
    }
    else if ( !wcscmp_0(p_String1, L"terminal server users") )
    {
      v13 = L"S-1-5-13";
    }
    else
    {
      if ( wcscmp_0(p_String1, L"performance log users") )
        goto LABEL_66;
      v13 = L"S-1-5-32-559";
    }
    if ( ConvertStringSidToSidW_0(v13, &Sid) && IsValidSid(Sid) )
    {
      if ( !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, peUse) )
      {
LABEL_61:
        LastWin32Error = GetLastWin32Error();
LABEL_67:
        v9 = LastWin32Error;
        goto LABEL_68;
      }
      LengthSid = GetLengthSid(Sid);
      v16 = MemAlloc(LengthSid);
      *a2 = v16;
      if ( v16 )
      {
        if ( !CopySid(LengthSid, v16, Sid) )
          goto LABEL_61;
      }
      else
      {
        v9 = -2147024882;
      }
LABEL_68:
      if ( Sid )
        LocalFree(Sid);
      if ( v9 && *a2 )
      {
        *a2 = 0;
        MemFree(0);
      }
      return v9;
    }
LABEL_66:
    LastWin32Error = GetNonSpecialPrincipalSID(p_String1, a2);
    goto LABEL_67;
  }
  return v9;
}

```

## disassembly

```asm
0x18004eaa8  mov     [rsp-8+arg_0], rbx
0x18004eaad  mov     [rsp-8+arg_10], rsi
0x18004eab2  push    rbp
0x18004eab3  push    rdi
0x18004eab4  push    r14
0x18004eab6  lea     rbp, [rsp-570h]
0x18004eabe  sub     rsp, 670h
0x18004eac5  mov     rax, cs:__security_cookie
0x18004eacc  xor     rax, rsp
0x18004eacf  mov     [rbp+580h+var_20], rax
0x18004ead6  mov     rsi, rdx
0x18004ead9  mov     rbx, rcx
0x18004eadc  mov     edi, 200h
0x18004eae1  lea     rcx, [rbp+580h+var_420]; void *
0x18004eae8  xor     r14d, r14d
0x18004eaeb  mov     r8d, edi; Size
0x18004eaee  xor     edx, edx; Val
0x18004eaf0  mov     [rsp+680h+Sid], r14
0x18004eaf5  call    memset_0
0x18004eafa  mov     r8d, edi; Size
0x18004eafd  lea     rcx, [rbp+580h+Name]; void *
0x18004eb04  xor     edx, edx; Val
0x18004eb06  call    memset_0
0x18004eb0b  mov     eax, 0FFh
0x18004eb10  mov     [rsi], r14
0x18004eb13  mov     [rsp+680h+var_638], eax
0x18004eb17  lea     rcx, [rsp+680h+String]
0x18004eb1c  mov     [rsp+680h+cchName], eax
0x18004eb20  lea     edx, [rax+1]
0x18004eb23  lea     rax, [rsp+680h+String]
0x18004eb28  sub     rbx, rax
0x18004eb2b  lea     rax, [rdx+7FFFFEFEh]
0x18004eb32  test    rax, rax
0x18004eb35  jz      short loc_18004EB4D
0x18004eb37  movzx   eax, word ptr [rbx+rcx]
0x18004eb3b  test    ax, ax
0x18004eb3e  jz      short loc_18004EB4D
0x18004eb40  mov     [rcx], ax
0x18004eb43  add     rcx, 2
0x18004eb47  sub     rdx, 1
0x18004eb4b  jnz     short loc_18004EB2B
0x18004eb4d  test    rdx, rdx
0x18004eb50  lea     rax, [rcx-2]
0x18004eb54  cmovnz  rax, rcx
0x18004eb58  mov     [rax], r14w
0x18004eb5c  mov     rax, rdx
0x18004eb5f  neg     rax
0x18004eb62  sbb     edi, edi
0x18004eb64  not     edi
0x18004eb66  and     edi, 8007007Ah
0x18004eb6c  test    rdx, rdx
0x18004eb6f  jz      loc_18004EF5B
0x18004eb75  lea     rcx, [rsp+680h+String]; String
0x18004eb7a  call    cs:__imp__wcslwr
0x18004eb80  mov     ebx, 5Ch ; '\'
0x18004eb85  lea     rcx, [rsp+680h+String]; Str
0x18004eb8a  mov     edx, ebx; Ch
0x18004eb8c  call    wcschr_0
0x18004eb91  test    rax, rax
0x18004eb94  jz      short loc_18004EBD8
0x18004eb96  lea     rcx, [rsp+680h+String]
0x18004eb9b  sub     rax, rcx
0x18004eb9e  sar     rax, 1
0x18004eba1  cmp     eax, 7
0x18004eba4  jnz     short loc_18004EBD8
0x18004eba6  lea     rdx, aBuiltin; "builtin"
0x18004ebad  mov     [rsp+680h+var_612], r14w
0x18004ebb3  lea     rcx, [rsp+680h+String]; String1
0x18004ebb8  call    wcscmp_0
0x18004ebbd  test    eax, eax
0x18004ebbf  jz      short loc_18004EBC6
0x18004ebc1  mov     [rsp+680h+var_612], bx
0x18004ebc6  test    eax, eax
0x18004ebc8  lea     rbx, [rsp+680h+String]
0x18004ebcd  lea     rcx, [rsp+680h+String1]
0x18004ebd2  cmovz   rbx, rcx
0x18004ebd6  jmp     short loc_18004EBDD
0x18004ebd8  lea     rbx, [rsp+680h+String]
0x18004ebdd  lea     rdx, aAdministrators; "administrators"
0x18004ebe4  mov     rcx, rbx; String1
0x18004ebe7  call    wcscmp_0
0x18004ebec  test    eax, eax
0x18004ebee  jnz     short loc_18004EBFC
0x18004ebf0  lea     rcx, aS1532544; "S-1-5-32-544"
0x18004ebf7  jmp     loc_18004EE8D
0x18004ebfc  lea     rdx, aSystem_0; "system"
0x18004ec03  mov     rcx, rbx; String1
0x18004ec06  call    wcscmp_0
0x18004ec0b  test    eax, eax
0x18004ec0d  jnz     short loc_18004EC1B
0x18004ec0f  lea     rcx, aS1518; "S-1-5-18"
0x18004ec16  jmp     loc_18004EE8D
0x18004ec1b  lea     rdx, aInteractive; "interactive"
0x18004ec22  mov     rcx, rbx; String1
0x18004ec25  call    wcscmp_0
0x18004ec2a  test    eax, eax
0x18004ec2c  jnz     short loc_18004EC3A
0x18004ec2e  lea     rcx, aS154; "S-1-5-4"
0x18004ec35  jmp     loc_18004EE8D
0x18004ec3a  lea     rdx, aEveryone; "everyone"
0x18004ec41  mov     rcx, rbx; String1
0x18004ec44  call    wcscmp_0
0x18004ec49  test    eax, eax
0x18004ec4b  jnz     short loc_18004EC59
0x18004ec4d  lea     rcx, aS110; "S-1-1-0"
0x18004ec54  jmp     loc_18004EE8D
0x18004ec59  lea     rdx, aCreatorOwner; "creator owner"
0x18004ec60  mov     rcx, rbx; String1
0x18004ec63  call    wcscmp_0
0x18004ec68  test    eax, eax
0x18004ec6a  jnz     short loc_18004EC78
0x18004ec6c  lea     rcx, aS130; "S-1-3-0"
0x18004ec73  jmp     loc_18004EE8D
0x18004ec78  lea     rdx, aAuthenticatedU; "authenticated users"
0x18004ec7f  mov     rcx, rbx; String1
0x18004ec82  call    wcscmp_0
0x18004ec87  test    eax, eax
0x18004ec89  jnz     short loc_18004EC97
0x18004ec8b  lea     rcx, aS1511; "S-1-5-11"
0x18004ec92  jmp     loc_18004EE8D
0x18004ec97  lea     rdx, aPerformanceMon_0; "performance monitor users"
0x18004ec9e  mov     rcx, rbx; String1
0x18004eca1  call    wcscmp_0
0x18004eca6  test    eax, eax
0x18004eca8  jnz     short loc_18004ECB6
0x18004ecaa  lea     rcx, aS1532558; "S-1-5-32-558"
0x18004ecb1  jmp     loc_18004EE8D
0x18004ecb6  lea     rdx, aLocalService; "local service"
0x18004ecbd  mov     rcx, rbx; String1
0x18004ecc0  call    wcscmp_0
0x18004ecc5  test    eax, eax
0x18004ecc7  jz      loc_18004EE86
0x18004eccd  lea     rdx, aLocalservice_0; "localservice"
0x18004ecd4  mov     rcx, rbx; String1
0x18004ecd7  call    wcscmp_0
0x18004ecdc  test    eax, eax
0x18004ecde  jz      loc_18004EE86
0x18004ece4  lea     rdx, aNtAuthorityLoc; "nt authority\\local service"
0x18004eceb  mov     rcx, rbx; String1
0x18004ecee  call    wcscmp_0
0x18004ecf3  test    eax, eax
0x18004ecf5  jz      loc_18004EE86
0x18004ecfb  lea     rdx, aNtAuthorityLoc_0; "nt authority\\localservice"
0x18004ed02  mov     rcx, rbx; String1
0x18004ed05  call    wcscmp_0
0x18004ed0a  test    eax, eax
0x18004ed0c  jz      loc_18004EE86
0x18004ed12  lea     rdx, aNetworkService; "network service"
0x18004ed19  mov     rcx, rbx; String1
0x18004ed1c  call    wcscmp_0
0x18004ed21  test    eax, eax
0x18004ed23  jz      loc_18004EE7D
0x18004ed29  lea     rdx, aNetworkservice_0; "networkservice"
0x18004ed30  mov     rcx, rbx; String1
0x18004ed33  call    wcscmp_0
0x18004ed38  test    eax, eax
0x18004ed3a  jz      loc_18004EE7D
0x18004ed40  lea     rdx, aNtAuthorityNet; "nt authority\\network service"
0x18004ed47  mov     rcx, rbx; String1
0x18004ed4a  call    wcscmp_0
0x18004ed4f  test    eax, eax
0x18004ed51  jz      loc_18004EE7D
0x18004ed57  lea     rdx, aNtAuthorityNet_0; "nt authority\\networkservice"
0x18004ed5e  mov     rcx, rbx; String1
0x18004ed61  call    wcscmp_0
0x18004ed66  test    eax, eax
0x18004ed68  jz      loc_18004EE7D
0x18004ed6e  lea     rdx, aIisIusrs; "iis_iusrs"
0x18004ed75  mov     rcx, rbx; String1
0x18004ed78  call    wcscmp_0
0x18004ed7d  test    eax, eax
0x18004ed7f  jnz     short loc_18004ED8D
0x18004ed81  lea     rcx, aS1532568; "S-1-5-32-568"
0x18004ed88  jmp     loc_18004EE8D
0x18004ed8d  lea     rdx, aUsers; "users"
0x18004ed94  mov     rcx, rbx; String1
0x18004ed97  call    wcscmp_0
0x18004ed9c  test    eax, eax
0x18004ed9e  jnz     short loc_18004EDAC
0x18004eda0  lea     rcx, aS1532545; "S-1-5-32-545"
0x18004eda7  jmp     loc_18004EE8D
0x18004edac  lea     rdx, aGuests_0; "guests"
0x18004edb3  mov     rcx, rbx; String1
0x18004edb6  call    wcscmp_0
0x18004edbb  test    eax, eax
0x18004edbd  jnz     short loc_18004EDCB
0x18004edbf  lea     rcx, aS1532546; "S-1-5-32-546"
0x18004edc6  jmp     loc_18004EE8D
0x18004edcb  lea     rdx, aPowerUsers; "power users"
0x18004edd2  mov     rcx, rbx; String1
0x18004edd5  call    wcscmp_0
0x18004edda  test    eax, eax
0x18004eddc  jnz     short loc_18004EDEA
0x18004edde  lea     rcx, aS1532547; "S-1-5-32-547"
0x18004ede5  jmp     loc_18004EE8D
0x18004edea  lea     rdx, aBatch; "batch"
0x18004edf1  mov     rcx, rbx; String1
0x18004edf4  call    wcscmp_0
0x18004edf9  test    eax, eax
0x18004edfb  jnz     short loc_18004EE09
0x18004edfd  lea     rcx, aS153; "S-1-5-3"
0x18004ee04  jmp     loc_18004EE8D
0x18004ee09  lea     rdx, aService; "service"
0x18004ee10  mov     rcx, rbx; String1
0x18004ee13  call    wcscmp_0
0x18004ee18  test    eax, eax
0x18004ee1a  jnz     short loc_18004EE25
0x18004ee1c  lea     rcx, aS156; "S-1-5-6"
0x18004ee23  jmp     short loc_18004EE8D
0x18004ee25  lea     rdx, aAnonymous_0; "anonymous"
0x18004ee2c  mov     rcx, rbx; String1
0x18004ee2f  call    wcscmp_0
0x18004ee34  test    eax, eax
0x18004ee36  jnz     short loc_18004EE41
0x18004ee38  lea     rcx, aS157; "S-1-5-7"
0x18004ee3f  jmp     short loc_18004EE8D
0x18004ee41  lea     rdx, aTerminalServer; "terminal server users"
0x18004ee48  mov     rcx, rbx; String1
0x18004ee4b  call    wcscmp_0
0x18004ee50  test    eax, eax
0x18004ee52  jnz     short loc_18004EE5D
0x18004ee54  lea     rcx, aS1513; "S-1-5-13"
0x18004ee5b  jmp     short loc_18004EE8D
0x18004ee5d  lea     rdx, aPerformanceLog_0; "performance log users"
0x18004ee64  mov     rcx, rbx; String1
0x18004ee67  call    wcscmp_0
0x18004ee6c  test    eax, eax
0x18004ee6e  jnz     loc_18004EF2B
0x18004ee74  lea     rcx, aS1532559; "S-1-5-32-559"
0x18004ee7b  jmp     short loc_18004EE8D
0x18004ee7d  lea     rcx, aS1520; "S-1-5-20"
0x18004ee84  jmp     short loc_18004EE8D
0x18004ee86  lea     rcx, StringSid; "S-1-5-19"
0x18004ee8d  lea     rdx, [rsp+680h+Sid]; Sid
0x18004ee92  call    ConvertStringSidToSidW_0
0x18004ee97  test    eax, eax
0x18004ee99  jz      loc_18004EF2B
0x18004ee9f  mov     rcx, [rsp+680h+Sid]; pSid
0x18004eea4  call    cs:__imp_IsValidSid
0x18004eeaa  test    eax, eax
0x18004eeac  jz      short loc_18004EF2B
0x18004eeae  mov     rdx, [rsp+680h+Sid]; Sid
0x18004eeb3  lea     rax, [rsp+680h+var_630]
0x18004eeb8  mov     [rsp+680h+peUse], rax; peUse
0x18004eebd  lea     r9, [rsp+680h+cchName]; cchName
0x18004eec2  lea     rax, [rsp+680h+var_638]
0x18004eec7  xor     ecx, ecx; lpSystemName
0x18004eec9  mov     [rsp+680h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004eece  lea     r8, [rbp+580h+Name]; Name
0x18004eed5  lea     rax, [rbp+580h+var_420]
0x18004eedc  mov     [rsp+680h+ReferencedDomainName], rax; ReferencedDomainName
0x18004eee1  call    cs:__imp_LookupAccountSidW
0x18004eee7  test    eax, eax
0x18004eee9  jnz     short loc_18004EEF2
0x18004eeeb  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004eef0  jmp     short loc_18004EF36
0x18004eef2  mov     rcx, [rsp+680h+Sid]; pSid
0x18004eef7  call    cs:__imp_GetLengthSid
0x18004eefd  mov     ecx, eax; unsigned __int64
0x18004eeff  mov     ebx, eax
0x18004ef01  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18004ef06  mov     [rsi], rax
0x18004ef09  test    rax, rax
0x18004ef0c  jnz     short loc_18004EF15
0x18004ef0e  mov     edi, 8007000Eh
0x18004ef13  jmp     short loc_18004EF38
0x18004ef15  mov     r8, [rsp+680h+Sid]; pSourceSid
0x18004ef1a  mov     rdx, rax; pDestinationSid
0x18004ef1d  mov     ecx, ebx; nDestinationSidLength
0x18004ef1f  call    cs:__imp_CopySid
0x18004ef25  test    eax, eax
0x18004ef27  jnz     short loc_18004EF38
0x18004ef29  jmp     short loc_18004EEEB
0x18004ef2b  mov     rdx, rsi; void **
0x18004ef2e  mov     rcx, rbx; Str
0x18004ef31  call    ?GetNonSpecialPrincipalSID@@YAJPEAGPEAPEAX@Z; GetNonSpecialPrincipalSID(ushort *,void * *)
0x18004ef36  mov     edi, eax
0x18004ef38  mov     rcx, [rsp+680h+Sid]; hMem
0x18004ef3d  test    rcx, rcx
0x18004ef40  jz      short loc_18004EF48
0x18004ef42  call    cs:__imp_LocalFree
0x18004ef48  test    edi, edi
0x18004ef4a  jz      short loc_18004EF5B
0x18004ef4c  cmp     [rsi], r14
0x18004ef4f  jz      short loc_18004EF5B
0x18004ef51  xor     ecx, ecx; lpMem
0x18004ef53  mov     [rsi], r14
0x18004ef56  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004ef5b  mov     eax, edi
0x18004ef5d  mov     rcx, [rbp+580h+var_20]
0x18004ef64  xor     rcx, rsp; StackCookie
0x18004ef67  call    __security_check_cookie
0x18004ef6c  lea     r11, [rsp+680h+var_10]
0x18004ef74  mov     rbx, [r11+20h]
0x18004ef78  mov     rsi, [r11+30h]
0x18004ef7c  mov     rsp, r11
0x18004ef7f  pop     r14
0x18004ef81  pop     rdi
0x18004ef82  pop     rbp
0x18004ef83  retn
  ... truncated ...
```
