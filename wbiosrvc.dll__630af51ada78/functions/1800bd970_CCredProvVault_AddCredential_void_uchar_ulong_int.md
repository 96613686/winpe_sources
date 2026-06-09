# CCredProvVault::AddCredential(void *,uchar *,ulong,int)

- ea: `0x1800bd970`
- end: `0x1800bdc5d`
- name: `?AddCredential@CCredProvVault@@QEAAKPEAXPEAEKH@Z`
- size: `749`
- prototype: `unsigned int(CCredProvVault *__hidden this, void *, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bcd80`

## callees

- `0x180068f60`
- `0x180069cc8`
- `0x1800bd970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdb36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bdadb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bdadb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdb41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdb41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800bdbb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800bdbb9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800bdbc7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800bdbc7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bda1a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bda1a`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800bdbf5`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800bdbf5`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800bdc1b`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800bdc1b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bdaac`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bdb2c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bdaac`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bdb2c`

## pseudocode

```c
__int64 __fastcall CCredProvVault::AddCredential(CCredProvVault *this, void *a2, WCHAR *a3, unsigned int a4)
{
  DWORD LastError; // edi
  DWORD v9; // edi
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  WCHAR *v12; // rcx
  int v13; // edi
  DWORD cchName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+3Ch] [rbp-C4h] BYREF
  _DWORD v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 LengthSid; // [rsp+50h] [rbp-B0h]
  void *v22; // [rsp+58h] [rbp-A8h]
  _DWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  WCHAR *v26; // [rsp+78h] [rbp-88h]
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  const wchar_t *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  __int128 v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+D8h] [rbp-28h]
  __int128 v36; // [rsp+F0h] [rbp-10h]
  __int128 v37; // [rsp+108h] [rbp+8h]
  GUID v38; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v39; // [rsp+130h] [rbp+30h]
  __int64 *v40; // [rsp+138h] [rbp+38h]
  _DWORD *v41; // [rsp+140h] [rbp+40h]
  _DWORD *v42; // [rsp+148h] [rbp+48h]
  struct _FILETIME FileTime; // [rsp+158h] [rbp+58h] BYREF
  int v44; // [rsp+160h] [rbp+60h]
  int v45; // [rsp+164h] [rbp+64h]
  __int128 *v46; // [rsp+168h] [rbp+68h]
  struct _SYSTEMTIME SystemTime; // [rsp+170h] [rbp+70h] BYREF

  v38.Data1 = 0;
  memset_0(&v38.Data2, 0, 0x4Cu);
  v29 = 1;
  v30 = 7;
  v37 = 0;
  v31 = 0;
  v32 = L"WinBio CredProv Resource";
  v19[1] = 0;
  v33 = 0;
  v23[1] = 0;
  v27 = 0;
  v28 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  SystemTime = 0;
  LengthSid = GetLengthSid(a2);
  v20 = 8;
  v24 = 8;
  v19[0] = 2;
  v22 = a2;
  pProtectionType = CredUnprotected;
  v23[0] = 3;
  v25 = a4;
  v26 = a3;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidLocalW(a2, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v11 = 0;
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
LABEL_5:
      v12 = 0;
      goto LABEL_8;
    }
    v9 = 2 * (cchReferencedDomainName + cchName) + 12;
    v10 = (WCHAR *)LocalAlloc(0x40u, v9);
    v11 = v10;
    if ( !v10 )
    {
      LastError = 14;
      goto LABEL_5;
    }
    *(_DWORD *)v10 = 12;
    *((_DWORD *)v10 + 1) = cchName;
    *((_DWORD *)v10 + 2) = cchReferencedDomainName;
    if ( !LookupAccountSidLocalW(a2, v10 + 6, &cchName, &v10[cchName + 6], &cchReferencedDomainName, &peUse) )
    {
LABEL_7:
      LastError = GetLastError();
      v12 = v11;
      goto LABEL_8;
    }
  }
  HIDWORD(v27) = DWORD1(v36);
  v38 = CCredProvVault::_guidSchema;
  v39 = L"WinBio CredProv Credential";
  v40 = &v29;
  v41 = v19;
  v42 = v23;
  LODWORD(v27) = 100;
  DWORD2(v27) = 8;
  *(_QWORD *)&v28 = __PAIR64__(HIDWORD(v36), v9);
  *((_QWORD *)&v28 + 1) = v11;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    goto LABEL_7;
  v44 = 0;
  v46 = &v27;
  v45 = 1;
  v13 = 0;
  if ( CredIsProtectedW(a3, &pProtectionType) && pProtectionType == CredTrustedProtection )
    v13 = 32;
  LastError = VaultAddItem(*(_QWORD *)this, &v38, 0, 0, v13);
  v12 = v11;
  if ( !LastError )
  {
    LocalFree(v11);
    goto LABEL_16;
  }
LABEL_8:
  LocalFree(v12);
LABEL_16:
  LocalFree(0);
  return LastError;
}

```

## disassembly

```asm
0x1800bd970  push    rbp
0x1800bd972  push    rbx
0x1800bd973  push    rsi
0x1800bd974  push    rdi
0x1800bd975  push    r14
0x1800bd977  push    r15
0x1800bd979  lea     rbp, [rsp-98h]
0x1800bd981  sub     rsp, 198h
0x1800bd988  mov     rax, cs:__security_cookie
0x1800bd98f  xor     rax, rsp
0x1800bd992  mov     [rbp+0C0h+var_40], rax
0x1800bd999  mov     rsi, rdx
0x1800bd99c  mov     [rbp+0C0h+var_A0], 0
0x1800bd9a3  xor     edx, edx; Val
0x1800bd9a5  mov     r14, r8
0x1800bd9a8  mov     r15, rcx
0x1800bd9ab  mov     ebx, r9d
0x1800bd9ae  lea     rcx, [rbp+0C0h+var_9C]; void *
0x1800bd9b2  lea     r8d, [rdx+4Ch]; Size
0x1800bd9b6  call    memset_0
0x1800bd9bb  xorps   xmm0, xmm0
0x1800bd9be  mov     [rbp+0C0h+var_120], 1
0x1800bd9c6  xorps   xmm1, xmm1
0x1800bd9c9  mov     [rbp+0C0h+var_118], 7
0x1800bd9d0  movups  [rbp+0C0h+var_B8], xmm1
0x1800bd9d4  mov     ecx, dword ptr [rbp+0C0h+var_B8+4]
0x1800bd9d7  xor     eax, eax
0x1800bd9d9  mov     [rbp+0C0h+var_114], ecx
0x1800bd9dc  lea     rcx, aWinbioCredprov; "WinBio CredProv Resource"
0x1800bd9e3  mov     [rbp+0C0h+var_110], rcx
0x1800bd9e7  mov     rcx, rsi; pSid
0x1800bd9ea  movups  [rsp+1C0h+var_180], xmm0
0x1800bd9ef  mov     [rbp+0C0h+var_108], rax
0x1800bd9f3  movups  [rsp+1C0h+var_170], xmm0
0x1800bd9f8  movups  [rsp+1C0h+var_160], xmm1
0x1800bd9fd  movups  [rsp+1C0h+var_150], xmm1
0x1800bda02  movups  [rbp+0C0h+var_140], xmm0
0x1800bda06  movups  [rbp+0C0h+var_130], xmm0
0x1800bda0a  movups  [rbp+0C0h+var_100], xmm0
0x1800bda0e  movups  [rbp+0C0h+var_E8], xmm1
0x1800bda12  movups  [rbp+0C0h+var_D0], xmm0
0x1800bda16  movups  xmmword ptr [rbp+0C0h+SystemTime.wYear], xmm0
0x1800bda1a  call    cs:__imp_GetLengthSid
0x1800bda20  mov     ecx, dword ptr [rbp+0C0h+var_100+4]
0x1800bda23  lea     r8, [rsp+1C0h+cchName]; cchName
0x1800bda28  mov     dword ptr [rsp+1C0h+var_170], eax
0x1800bda2c  mov     edx, 8
0x1800bda31  mov     eax, dword ptr [rbp+0C0h+var_100+0Ch]
0x1800bda34  xor     r9d, r9d; ReferencedDomainName
0x1800bda37  mov     dword ptr [rsp+1C0h+var_170+4], eax
0x1800bda3b  mov     eax, dword ptr [rbp+0C0h+var_E8+4]
0x1800bda3e  mov     dword ptr [rsp+1C0h+var_160+0Ch], eax
0x1800bda42  mov     eax, dword ptr [rbp+0C0h+var_E8+0Ch]
0x1800bda45  mov     dword ptr [rsp+1C0h+var_150+4], eax
0x1800bda49  lea     rax, [rsp+1C0h+var_188]
0x1800bda4e  mov     [rsp+1C0h+peUse], rax; peUse
0x1800bda53  lea     rax, [rsp+1C0h+var_18C]
0x1800bda58  mov     dword ptr [rsp+1C0h+var_180+8], edx
0x1800bda5c  mov     dword ptr [rsp+1C0h+var_180+0Ch], ecx
0x1800bda60  mov     rcx, rsi; Sid
0x1800bda63  mov     dword ptr [rsp+1C0h+var_160+8], edx
0x1800bda67  xor     edx, edx; Name
0x1800bda69  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800bda6e  mov     dword ptr [rsp+1C0h+var_180], 2
0x1800bda76  mov     qword ptr [rsp+1C0h+var_170+8], rsi
0x1800bda7b  mov     [rsp+1C0h+pProtectionType], 0
0x1800bda83  mov     dword ptr [rsp+1C0h+var_160], 3
0x1800bda8b  mov     dword ptr [rsp+1C0h+var_150], ebx
0x1800bda8f  mov     qword ptr [rsp+1C0h+var_150+8], r14
0x1800bda94  mov     [rsp+1C0h+cchName], 0
0x1800bda9c  mov     [rsp+1C0h+var_18C], 0
0x1800bdaa4  mov     [rsp+1C0h+var_188], 0
0x1800bdaac  call    cs:__imp_LookupAccountSidLocalW
0x1800bdab2  test    eax, eax
0x1800bdab4  jnz     loc_1800BDB4C
0x1800bdaba  call    cs:__imp_GetLastError
0x1800bdac0  mov     edi, eax
0x1800bdac2  cmp     eax, 7Ah ; 'z'
0x1800bdac5  jnz     short loc_1800BDAEC
0x1800bdac7  mov     ecx, [rsp+1C0h+cchName]
0x1800bdacb  add     ecx, [rsp+1C0h+var_18C]
0x1800bdacf  lea     edi, ds:0Ch[rcx*2]
0x1800bdad6  mov     edx, edi; uBytes
0x1800bdad8  lea     ecx, [rax-3Ah]; uFlags
0x1800bdadb  call    cs:__imp_LocalAlloc
0x1800bdae1  mov     rbx, rax
0x1800bdae4  test    rax, rax
0x1800bdae7  jnz     short loc_1800BDAF0
0x1800bdae9  lea     edi, [rax+0Eh]
0x1800bdaec  xor     ecx, ecx
0x1800bdaee  jmp     short loc_1800BDB41
0x1800bdaf0  mov     dword ptr [rax], 0Ch
0x1800bdaf6  lea     rdx, [rbx+0Ch]; Name
0x1800bdafa  mov     eax, [rsp+1C0h+cchName]
0x1800bdafe  lea     r8, [rsp+1C0h+cchName]; cchName
0x1800bdb03  mov     [rbx+4], eax
0x1800bdb06  mov     rcx, rsi; Sid
0x1800bdb09  mov     eax, [rsp+1C0h+var_18C]
0x1800bdb0d  mov     [rbx+8], eax
0x1800bdb10  mov     eax, [rsp+1C0h+cchName]
0x1800bdb14  lea     r9, [rdx+rax*2]; ReferencedDomainName
0x1800bdb18  lea     rax, [rsp+1C0h+var_188]
0x1800bdb1d  mov     [rsp+1C0h+peUse], rax; peUse
0x1800bdb22  lea     rax, [rsp+1C0h+var_18C]
0x1800bdb27  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800bdb2c  call    cs:__imp_LookupAccountSidLocalW
0x1800bdb32  test    eax, eax
0x1800bdb34  jnz     short loc_1800BDB50
0x1800bdb36  call    cs:__imp_GetLastError
0x1800bdb3c  mov     edi, eax
0x1800bdb3e  mov     rcx, rbx; hMem
0x1800bdb41  call    cs:__imp_LocalFree
0x1800bdb47  jmp     loc_1800BDC34
0x1800bdb4c  xor     ebx, ebx
0x1800bdb4e  xor     edi, edi
0x1800bdb50  mov     eax, dword ptr [rbp+0C0h+var_D0+4]
0x1800bdb53  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x1800bdb57  movsd   xmm0, qword ptr cs:?_guidSchema@CCredProvVault@@0U_GUID@@A.Data2; _GUID CCredProvVault::_guidSchema ...
0x1800bdb5f  mov     dword ptr [rbp+0C0h+var_140+0Ch], eax
0x1800bdb62  mov     eax, dword ptr [rbp+0C0h+var_D0+0Ch]
0x1800bdb65  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x1800bdb68  mov     eax, cs:?_guidSchema@CCredProvVault@@0U_GUID@@A.Data1; _GUID CCredProvVault::_guidSchema ...
0x1800bdb6e  mov     [rbp+0C0h+var_A0], eax
0x1800bdb71  mov     eax, dword ptr cs:?_guidSchema@CCredProvVault@@0U_GUID@@A.Data4+4; _GUID CCredProvVault::_guidSchema ...
0x1800bdb77  mov     [rbp+0C0h+var_94], eax
0x1800bdb7a  lea     rax, aWinbioCredprov_0; "WinBio CredProv Credential"
0x1800bdb81  mov     [rbp+0C0h+var_90], rax
0x1800bdb85  lea     rax, [rbp+0C0h+var_120]
0x1800bdb89  mov     [rbp+0C0h+var_88], rax
0x1800bdb8d  lea     rax, [rsp+1C0h+var_180]
0x1800bdb92  mov     [rbp+0C0h+var_80], rax
0x1800bdb96  lea     rax, [rsp+1C0h+var_160]
0x1800bdb9b  mov     [rbp+0C0h+var_78], rax
0x1800bdb9f  mov     dword ptr [rbp+0C0h+var_140], 64h ; 'd'
0x1800bdba6  mov     dword ptr [rbp+0C0h+var_140+8], 8
0x1800bdbad  mov     dword ptr [rbp+0C0h+var_130], edi
0x1800bdbb0  mov     qword ptr [rbp+0C0h+var_130+8], rbx
0x1800bdbb4  movsd   [rbp+0C0h+var_9C], xmm0
0x1800bdbb9  call    cs:__imp_GetSystemTime
0x1800bdbbf  lea     rdx, [rbp+0C0h+FileTime]; lpFileTime
0x1800bdbc3  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x1800bdbc7  call    cs:__imp_SystemTimeToFileTime
0x1800bdbcd  test    eax, eax
0x1800bdbcf  jz      loc_1800BDB36
0x1800bdbd5  lea     rax, [rbp+0C0h+var_140]
0x1800bdbd9  mov     [rbp+0C0h+var_60], 0
0x1800bdbe0  lea     rdx, [rsp+1C0h+pProtectionType]; pProtectionType
0x1800bdbe5  mov     [rbp+0C0h+var_58], rax
0x1800bdbe9  mov     rcx, r14; pszProtectedCredentials
0x1800bdbec  mov     [rbp+0C0h+var_5C], 1
0x1800bdbf3  xor     edi, edi
0x1800bdbf5  call    cs:__imp_CredIsProtectedW
0x1800bdbfb  test    eax, eax
0x1800bdbfd  jz      short loc_1800BDC0A
0x1800bdbff  cmp     [rsp+1C0h+pProtectionType], 2
0x1800bdc04  lea     eax, [rdi+20h]
0x1800bdc07  cmovz   edi, eax
0x1800bdc0a  mov     rcx, [r15]
0x1800bdc0d  lea     rdx, [rbp+0C0h+var_A0]
0x1800bdc11  xor     r9d, r9d
0x1800bdc14  mov     dword ptr [rsp+1C0h+cchReferencedDomainName], edi
0x1800bdc18  xor     r8d, r8d
0x1800bdc1b  call    cs:__imp_VaultAddItem
0x1800bdc21  mov     edi, eax
0x1800bdc23  mov     rcx, rbx; hMem
0x1800bdc26  test    eax, eax
0x1800bdc28  jnz     loc_1800BDB41
0x1800bdc2e  call    cs:__imp_LocalFree
0x1800bdc34  xor     ecx, ecx; hMem
0x1800bdc36  call    cs:__imp_LocalFree
0x1800bdc3c  mov     eax, edi
0x1800bdc3e  mov     rcx, [rbp+0C0h+var_40]
0x1800bdc45  xor     rcx, rsp; StackCookie
0x1800bdc48  call    __security_check_cookie
0x1800bdc4d  add     rsp, 198h
0x1800bdc54  pop     r15
0x1800bdc56  pop     r14
0x1800bdc58  pop     rdi
0x1800bdc59  pop     rsi
0x1800bdc5a  pop     rbx
0x1800bdc5b  pop     rbp
0x1800bdc5c  retn
```
