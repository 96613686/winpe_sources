# LdapInitSecurity

- ea: `0x180018560`
- end: `0x1800188c7`
- name: `LdapInitSecurity`
- size: `871`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800164a0`
- `0x180026b50`

## callees

- `0x1800037a8`
- `0x180018560`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018581`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800185ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800185ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800186e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018721`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001875c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018797`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800187d2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001880d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800186e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018721`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001875c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018797`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800187d2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001880d`
- `SspiCli!InitSecurityInterfaceW` at `0x1800185a3`
- `SspiCli!InitSecurityInterfaceW` at `0x1800185a3`

## string_xrefs

- `0x180018656`: `LDAP client failed EnumSecurityPackages, error = 0x%x.\n`
- `0x1800188af`: `LDAP client failed InitSecurityInterface, error = 0x%x.\n`

## pseudocode

```c
char LdapInitSecurity()
{
  unsigned int v1; // edi
  PSecurityFunctionTableW inited; // rax
  unsigned int v3; // eax
  __int64 v4; // rbx
  const WCHAR *v5; // r8
  const WCHAR *v6; // r8
  const WCHAR *v7; // r8
  const WCHAR *v8; // r8
  const WCHAR *v9; // r8
  const WCHAR *v10; // r8
  DWORD LastError; // eax

  if ( dword_180066278 == 1 )
    return 1;
  EnterCriticalSection(&LoadLibLock);
  v1 = 0;
  NumberSecurityPackagesInstalled = 0;
  SecurityPackagesInstalled = 0;
  SspiFunctionTableW = 0;
  inited = InitSecurityInterfaceW();
  SspiFunctionTableW = inited;
  if ( !inited )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    {
      LastError = GetLastError();
      LDAPClientPrint(0x10000000, "LDAP client failed InitSecurityInterface, error = 0x%x.\n", LastError);
    }
LABEL_5:
    LeaveCriticalSection(&LoadLibLock);
    return 0;
  }
  v3 = ((__int64 (__fastcall *)(int *, __int64 *))inited->EnumerateSecurityPackagesW)(
         &NumberSecurityPackagesInstalled,
         &SecurityPackagesInstalled);
  if ( v3 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(0x10000000, "LDAP client failed EnumSecurityPackages, error = 0x%x.\n", v3);
    goto LABEL_5;
  }
  v4 = SecurityPackagesInstalled;
  if ( SecurityPackagesInstalled && NumberSecurityPackagesInstalled )
  {
    do
    {
      v5 = *(const WCHAR **)(v4 + 16);
      if ( !v5 || CompareStringW(0x400u, 1u, v5, -1, L"Kerberos", -1) != 2 )
      {
        v6 = *(const WCHAR **)(v4 + 16);
        if ( v6 && CompareStringW(0x400u, 1u, v6, -1, L"MSN", -1) == 2 )
        {
          SspiPackageSicily = v4;
        }
        else
        {
          v7 = *(const WCHAR **)(v4 + 16);
          if ( v7 && CompareStringW(0x400u, 1u, v7, -1, L"NTLM", -1) == 2 )
          {
            SspiPackageNtlm = v4;
          }
          else
          {
            v8 = *(const WCHAR **)(v4 + 16);
            if ( v8 && CompareStringW(0x400u, 1u, v8, -1, L"DPA", -1) == 2 )
            {
              SspiPackageDpa = v4;
            }
            else
            {
              v9 = *(const WCHAR **)(v4 + 16);
              if ( v9 && CompareStringW(0x400u, 1u, v9, -1, L"wDigest", -1) == 2 )
              {
                SspiPackageDigest = v4;
              }
              else
              {
                v10 = *(const WCHAR **)(v4 + 16);
                if ( v10 && CompareStringW(0x400u, 1u, v10, -1, L"Negotiate", -1) == 2 )
                  SspiPackageNegotiate = v4;
              }
            }
          }
        }
      }
      if ( *(_DWORD *)(v4 + 8) > SspiMaxTokenSize )
        SspiMaxTokenSize = *(_DWORD *)(v4 + 8);
      v4 += 32;
      ++v1;
    }
    while ( v1 < NumberSecurityPackagesInstalled );
  }
  dword_180066278 = 1;
  LeaveCriticalSection(&LoadLibLock);
  return 1;
}

```

## disassembly

```asm
0x180018560  sub     rsp, 58h
0x180018564  cmp     cs:dword_180066278, 1
0x18001856b  jnz     short loc_180018575
0x18001856d  mov     al, 1
0x18001856f  add     rsp, 58h
0x180018573  retn
0x180018575  lea     rcx, LoadLibLock; lpCriticalSection
0x18001857c  mov     [rsp+58h+var_8], rdi
0x180018581  call    cs:__imp_EnterCriticalSection
0x180018588  nop     dword ptr [rax+rax+00h]
0x18001858d  xor     edi, edi
0x18001858f  mov     cs:NumberSecurityPackagesInstalled, edi
0x180018595  mov     cs:SecurityPackagesInstalled, rdi
0x18001859c  mov     cs:SspiFunctionTableW, rdi
0x1800185a3  call    cs:__imp_InitSecurityInterfaceW
0x1800185aa  nop     dword ptr [rax+rax+00h]
0x1800185af  mov     cs:SspiFunctionTableW, rax
0x1800185b6  test    rax, rax
0x1800185b9  jnz     short loc_1800185E3
0x1800185bb  cmp     cs:g_fTracingOn, edi
0x1800185c1  jnz     loc_180018886
0x1800185c7  lea     rcx, LoadLibLock; lpCriticalSection
0x1800185ce  call    cs:__imp_LeaveCriticalSection
0x1800185d5  nop     dword ptr [rax+rax+00h]
0x1800185da  xor     al, al
0x1800185dc  mov     rdi, [rsp+58h+var_8]
0x1800185e1  jmp     short loc_18001856F
0x1800185e3  mov     rax, [rax+8]
0x1800185e7  lea     rdx, SecurityPackagesInstalled
0x1800185ee  lea     rcx, NumberSecurityPackagesInstalled
0x1800185f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fa  test    eax, eax
0x1800185fc  jnz     short loc_180018635
0x1800185fe  mov     [rsp+58h+arg_0], rbx
0x180018603  mov     rbx, cs:SecurityPackagesInstalled
0x18001860a  test    rbx, rbx
0x18001860d  jnz     short loc_18001866F
0x18001860f  lea     rcx, LoadLibLock; lpCriticalSection
0x180018616  mov     cs:dword_180066278, 1
0x180018620  call    cs:__imp_LeaveCriticalSection
0x180018627  nop     dword ptr [rax+rax+00h]
0x18001862c  mov     rbx, [rsp+58h+arg_0]
0x180018631  mov     al, 1
0x180018633  jmp     short loc_1800185DC
0x180018635  cmp     cs:g_fTracingOn, edi
0x18001863b  jz      short loc_1800185C7
0x18001863d  cmp     cs:g_fProviderEnabled, edi
0x180018643  jz      short loc_1800185C7
0x180018645  test    cs:g_ulTraceFlags, 10000000h
0x180018650  jz      loc_1800185C7
0x180018656  lea     rdx, aLdapClientFail_5; "LDAP client failed EnumSecurityPackages"...
0x18001865d  mov     r8d, eax
0x180018660  mov     ecx, 10000000h
0x180018665  call    LDAPClientPrint
0x18001866a  jmp     loc_1800185C7
0x18001866f  cmp     cs:NumberSecurityPackagesInstalled, edi
0x180018675  jbe     short loc_18001860F
0x180018677  mov     [rsp+58h+arg_8], rbp
0x18001867c  lea     rbp, aMsn; "MSN"
0x180018683  mov     [rsp+58h+arg_10], rsi
0x180018688  lea     rsi, String2; "Kerberos"
0x18001868f  mov     [rsp+58h+var_10], r12
0x180018694  lea     r12, aWdigest; "wDigest"
0x18001869b  mov     [rsp+58h+var_18], r13
0x1800186a0  lea     r13, aNegotiate; "Negotiate"
0x1800186a7  mov     [rsp+58h+var_20], r14
0x1800186ac  lea     r14, aNtlm; "NTLM"
0x1800186b3  mov     [rsp+58h+var_28], r15
0x1800186b8  lea     r15, aDpa; "DPA"
0x1800186bf  nop
0x1800186c0  mov     r8, [rbx+10h]; lpString1
0x1800186c4  test    r8, r8
0x1800186c7  jz      short loc_1800186FB
0x1800186c9  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800186d1  mov     edx, 1; dwCmpFlags
0x1800186d6  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800186dc  mov     [rsp+58h+lpString2], rsi; lpString2
0x1800186e1  mov     ecx, 400h; Locale
0x1800186e6  call    cs:__imp_CompareStringW
0x1800186ed  nop     dword ptr [rax+rax+00h]
0x1800186f2  cmp     eax, 2
0x1800186f5  jz      loc_18001882E
0x1800186fb  mov     r8, [rbx+10h]; lpString1
0x1800186ff  test    r8, r8
0x180018702  jz      short loc_180018736
0x180018704  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001870c  mov     edx, 1; dwCmpFlags
0x180018711  mov     r9d, 0FFFFFFFFh; cchCount1
0x180018717  mov     [rsp+58h+lpString2], rbp; lpString2
0x18001871c  mov     ecx, 400h; Locale
0x180018721  call    cs:__imp_CompareStringW
0x180018728  nop     dword ptr [rax+rax+00h]
0x18001872d  cmp     eax, 2
0x180018730  jz      loc_180018827
0x180018736  mov     r8, [rbx+10h]; lpString1
0x18001873a  test    r8, r8
0x18001873d  jz      short loc_180018771
0x18001873f  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180018747  mov     edx, 1; dwCmpFlags
0x18001874c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180018752  mov     [rsp+58h+lpString2], r14; lpString2
0x180018757  mov     ecx, 400h; Locale
0x18001875c  call    cs:__imp_CompareStringW
0x180018763  nop     dword ptr [rax+rax+00h]
0x180018768  cmp     eax, 2
0x18001876b  jz      loc_180018874
0x180018771  mov     r8, [rbx+10h]; lpString1
0x180018775  test    r8, r8
0x180018778  jz      short loc_1800187AC
0x18001877a  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180018782  mov     edx, 1; dwCmpFlags
0x180018787  mov     r9d, 0FFFFFFFFh; cchCount1
0x18001878d  mov     [rsp+58h+lpString2], r15; lpString2
0x180018792  mov     ecx, 400h; Locale
0x180018797  call    cs:__imp_CompareStringW
0x18001879e  nop     dword ptr [rax+rax+00h]
0x1800187a3  cmp     eax, 2
0x1800187a6  jz      loc_1800188BB
0x1800187ac  mov     r8, [rbx+10h]; lpString1
0x1800187b0  test    r8, r8
0x1800187b3  jz      short loc_1800187E7
0x1800187b5  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800187bd  mov     edx, 1; dwCmpFlags
0x1800187c2  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800187c8  mov     [rsp+58h+lpString2], r12; lpString2
0x1800187cd  mov     ecx, 400h; Locale
0x1800187d2  call    cs:__imp_CompareStringW
0x1800187d9  nop     dword ptr [rax+rax+00h]
0x1800187de  cmp     eax, 2
0x1800187e1  jz      loc_18001887D
0x1800187e7  mov     r8, [rbx+10h]; lpString1
0x1800187eb  test    r8, r8
0x1800187ee  jz      short loc_18001882E
0x1800187f0  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800187f8  mov     edx, 1; dwCmpFlags
0x1800187fd  mov     r9d, 0FFFFFFFFh; cchCount1
0x180018803  mov     [rsp+58h+lpString2], r13; lpString2
0x180018808  mov     ecx, 400h; Locale
0x18001880d  call    cs:__imp_CompareStringW
0x180018814  nop     dword ptr [rax+rax+00h]
0x180018819  cmp     eax, 2
0x18001881c  jnz     short loc_18001882E
0x18001881e  mov     cs:SspiPackageNegotiate, rbx
0x180018825  jmp     short loc_18001882E
0x180018827  mov     cs:SspiPackageSicily, rbx
0x18001882e  mov     eax, [rbx+8]
0x180018831  cmp     eax, cs:SspiMaxTokenSize
0x180018837  jbe     short loc_18001883F
0x180018839  mov     cs:SspiMaxTokenSize, eax
0x18001883f  add     rbx, 20h ; ' '
0x180018843  inc     edi
0x180018845  cmp     edi, cs:NumberSecurityPackagesInstalled
0x18001884b  jb      loc_1800186C0
0x180018851  mov     r15, [rsp+58h+var_28]
0x180018856  mov     r14, [rsp+58h+var_20]
0x18001885b  mov     r13, [rsp+58h+var_18]
0x180018860  mov     r12, [rsp+58h+var_10]
0x180018865  mov     rsi, [rsp+58h+arg_10]
0x18001886a  mov     rbp, [rsp+58h+arg_8]
0x18001886f  jmp     loc_18001860F
0x180018874  mov     cs:SspiPackageNtlm, rbx
0x18001887b  jmp     short loc_18001882E
0x18001887d  mov     cs:SspiPackageDigest, rbx
0x180018884  jmp     short loc_18001882E
0x180018886  cmp     cs:g_fProviderEnabled, edi
0x18001888c  jz      loc_1800185C7
0x180018892  test    cs:g_ulTraceFlags, 10000000h
0x18001889d  jz      loc_1800185C7
0x1800188a3  call    cs:__imp_GetLastError
0x1800188aa  nop     dword ptr [rax+rax+00h]
0x1800188af  lea     rdx, aLdapClientFail_2; "LDAP client failed InitSecurityInterfac"...
0x1800188b6  jmp     loc_18001865D
0x1800188bb  mov     cs:SspiPackageDpa, rbx
0x1800188c2  jmp     loc_18001882E
```
