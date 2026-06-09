# SpAcceptCredentials(_SECURITY_LOGON_TYPE,_UNICODE_STRING *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED *)

- ea: `0x180002570`
- end: `0x1800029a4`
- name: `?SpAcceptCredentials@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_UNICODE_STRING@@PEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED@@@Z`
- size: `1076`
- prototype: `int(enum _SECURITY_LOGON_TYPE, struct _UNICODE_STRING *, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002570`
- `0x1800029b0`
- `0x180002e50`
- `0x180013c64`
- `0x180013e00`
- `0x180014100`
- `0x1800161a0`
- `0x18001627c`
- `0x1800162a4`
- `0x1800162e4`
- `0x18001658c`
- `0x18001680c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002809`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002809`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000267b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000270d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000267b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000270d`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800026c4`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800027e9`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800028ae`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800026c4`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800027e9`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x1800028ae`

## pseudocode

```c
__int64 __fastcall SpAcceptCredentials(
        enum _SECURITY_LOGON_TYPE a1,
        struct _UNICODE_STRING *a2,
        struct _SECPKG_PRIMARY_CRED *a3,
        struct _SECPKG_SUPPLEMENTAL_CRED *a4)
{
  _QWORD *v6; // rcx
  DWORD LowPart; // eax
  __int64 Flags; // r9
  unsigned int v10; // edi
  int v11; // r14d
  LSTATUS v12; // eax
  signed int v13; // esi
  struct _TS_CREDENTIAL *v14; // rsi
  int v15; // [rsp+50h] [rbp+7h] BYREF
  struct _TS_CREDENTIAL *v16; // [rsp+58h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+1Fh] BYREF
  _QWORD v19[2]; // [rsp+70h] [rbp+27h] BYREF
  unsigned __int8 v20; // [rsp+C0h] [rbp+77h] BYREF

  v20 = 0;
  v16 = 0;
  v19[0] = 1048590;
  v19[1] = L"CREDSSP";
  if ( !a3 )
    return 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_dZDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      a1,
      (__int64)a2,
      a3->LogonId.HighPart,
      a3->LogonId.LowPart);
    v6 = WPP_GLOBAL_Control;
  }
  LowPart = a3->LogonId.LowPart;
  if ( a3->LogonId.LowPart == 999 )
  {
    if ( a3->LogonId.HighPart )
      goto LABEL_8;
    return 0;
  }
  if ( LowPart == 996 )
  {
    if ( a3->LogonId.HighPart )
      goto LABEL_8;
    return 0;
  }
  if ( LowPart == 997 && !a3->LogonId.HighPart )
    return 0;
LABEL_8:
  Flags = a3->Flags;
  if ( (a3->Flags & 0x201) == 0 || (((a3->Flags & 0x201) - 1) & a3->Flags & 0x201) != 0 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_d(v6[2], 29, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, Flags);
    return 0;
  }
  v10 = 0;
  if ( !TSGlobalIsCredGuardEnabled )
  {
    if ( (Flags & 0x800) != 0 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_(v6[2], 31, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids);
      LsaIEventWritePackageNotCacheLogonUser(v19, &a3->DownlevelName, &a3->DomainName, 1);
      return v10;
    }
    hKey = 0;
    phkResult = 0;
    v11 = 0;
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Windows\\CredentialsDelegation",
            0,
            0x20019u,
            &phkResult);
    v13 = v12;
    if ( v12 == 2 )
    {
      v13 = 0;
    }
    else if ( v12 > 0 )
    {
      v13 = (unsigned __int16)v12 | 0x80070000;
    }
    if ( v13 >= 0 )
    {
      hKey = 0;
      RegOpenKeyExW(
        HKEY_LOCAL_MACHINE,
        L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults",
        0,
        0x20019u,
        &hKey);
      v15 = 0;
      v13 = CheckValue(
              phkResult,
              hKey,
              L"AllowDefaultCredentials",
              0,
              0,
              L"ConcatenateDefaults_AllowDefault",
              0,
              0,
              &v15);
      if ( v13 >= 0 )
      {
        if ( v15 )
          v11 = 1;
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v13 < 0 )
    {
      v10 = (unsigned __int16)v13;
      if ( (_WORD)v13 )
        v10 = (unsigned __int16)v13 | 0xC0070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids,
          (unsigned int)v13,
          v10);
      return v10;
    }
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids);
      LsaIEventWritePackageNotCacheLogonUser(v19, &a3->DownlevelName, &a3->DomainName, 0);
      return v10;
    }
    v10 = TSCreateNewCredential(a3, &v16);
    if ( (v10 & 0x80000000) == 0 )
    {
      v10 = TSCredTableLocate(&v16, &v20);
      if ( (v10 & 0x80000000) == 0 )
      {
        if ( v20 )
        {
          v14 = v16;
          v10 = TSUpdateCredentialsPassword(a3, v16);
          goto LABEL_36;
        }
        v10 = TSCredTableInsertOrLocate(&v16);
      }
    }
    v14 = v16;
LABEL_36:
    if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) <= 1 )
      TSFreeCredential(v14);
    return v10;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_s(v6[2], 30, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, "SpAcceptCredentials");
  LsaIEventWritePackageNotCacheLogonUser(v19, &a3->DownlevelName, &a3->DomainName, 0);
  return 0;
}

```

## disassembly

```asm
0x180002570  push    rbp
0x180002572  push    rbx
0x180002573  push    r12
0x180002575  push    r15
0x180002577  lea     rbp, [rsp-3Fh]
0x18000257c  sub     rsp, 88h
0x180002583  xor     r12d, r12d
0x180002586  mov     [rbp+57h+arg_10], 0
0x18000258a  mov     [rbp+57h+var_48], r12
0x18000258e  lea     rax, aCredssp; "CREDSSP"
0x180002595  mov     [rbp+57h+var_30], 10000Eh
0x18000259d  mov     rbx, r8
0x1800025a0  mov     [rbp+57h+var_28], rax
0x1800025a4  mov     r9d, ecx
0x1800025a7  test    r8, r8
0x1800025aa  jz      short loc_18000260A
0x1800025ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025b3  lea     r15, WPP_GLOBAL_Control
0x1800025ba  cmp     rcx, r15
0x1800025bd  jz      short loc_1800025C9
0x1800025bf  test    byte ptr [rcx+1Ch], 20h
0x1800025c3  jnz     loc_180002814
0x1800025c9  mov     eax, [rbx]
0x1800025cb  cmp     eax, 3E7h
0x1800025d0  jz      loc_180002697
0x1800025d6  cmp     eax, 3E4h
0x1800025db  jz      loc_18000283D
0x1800025e1  cmp     eax, 3E5h
0x1800025e6  jz      loc_18000284C
0x1800025ec  mov     r9d, [rbx+50h]
0x1800025f0  mov     edx, r9d
0x1800025f3  and     edx, 201h
0x1800025f9  jnz     short loc_18000261A
0x1800025fb  cmp     rcx, r15
0x1800025fe  jz      short loc_18000260A
0x180002600  test    byte ptr [rcx+1Ch], 2
0x180002604  jnz     loc_18000298A
0x18000260a  xor     eax, eax
0x18000260c  add     rsp, 88h
0x180002613  pop     r15
0x180002615  pop     r12
0x180002617  pop     rbx
0x180002618  pop     rbp
0x180002619  retn
0x18000261a  lea     eax, [rdx-1]
0x18000261d  test    edx, eax
0x18000261f  jnz     short loc_1800025FB
0x180002621  cmp     cs:?TSGlobalIsCredGuardEnabled@@3HA, r12d; int TSGlobalIsCredGuardEnabled
0x180002628  mov     [rsp+0A0h+arg_8], rdi
0x180002630  mov     edi, r12d
0x180002633  jnz     short loc_1800026A6
0x180002635  mov     [rsp+0A0h+var_20], r14
0x18000263d  bt      r9d, 0Bh
0x180002642  jb      loc_18000287C
0x180002648  lea     rax, [rbp+57h+var_38]
0x18000264c  mov     [rsp+0A0h+arg_0], rsi
0x180002654  mov     r9d, 20019h; samDesired
0x18000265a  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18000265f  xor     r8d, r8d; ulOptions
0x180002662  mov     [rbp+57h+hKey], r12
0x180002666  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000266d  mov     [rbp+57h+var_38], r12
0x180002671  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002678  mov     r14d, r12d
0x18000267b  call    cs:__imp_RegOpenKeyExW
0x180002681  mov     esi, eax
0x180002683  cmp     eax, 2
0x180002686  jz      short loc_1800026E2
0x180002688  test    eax, eax
0x18000268a  jle     short loc_1800026E5
0x18000268c  movzx   esi, ax
0x18000268f  or      esi, 80070000h
0x180002695  jmp     short loc_1800026E5
0x180002697  cmp     [rbx+4], r12d
0x18000269b  jz      loc_18000260A
0x1800026a1  jmp     loc_1800025EC
0x1800026a6  cmp     rcx, r15
0x1800026a9  jz      short loc_1800026B5
0x1800026ab  test    byte ptr [rcx+1Ch], 8
0x1800026af  jnz     loc_18000285B
0x1800026b5  lea     r8, [rbx+18h]
0x1800026b9  xor     r9d, r9d
0x1800026bc  lea     rdx, [rbx+8]
0x1800026c0  lea     rcx, [rbp+57h+var_30]
0x1800026c4  call    cs:__imp_LsaIEventWritePackageNotCacheLogonUser
0x1800026ca  mov     eax, edi
0x1800026cc  mov     rdi, [rsp+0A0h+arg_8]
0x1800026d4  add     rsp, 88h
0x1800026db  pop     r15
0x1800026dd  pop     r12
0x1800026df  pop     rbx
0x1800026e0  pop     rbp
0x1800026e1  retn
0x1800026e2  mov     esi, r12d
0x1800026e5  test    esi, esi
0x1800026e7  js      short loc_18000275C
0x1800026e9  lea     rax, [rbp+57h+hKey]
0x1800026ed  mov     [rbp+57h+hKey], r12
0x1800026f1  mov     r9d, 20019h; samDesired
0x1800026f7  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800026fc  xor     r8d, r8d; ulOptions
0x1800026ff  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180002706  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000270d  call    cs:__imp_RegOpenKeyExW
0x180002713  mov     [rbp+57h+var_50], r12d
0x180002717  mov     r8, cs:off_18001E000; unsigned __int16 *
0x18000271e  lea     rax, [rbp+57h+var_50]
0x180002722  mov     rdx, [rbp+57h+hKey]; hKey
0x180002726  xor     r9d, r9d; unsigned __int16 *
0x180002729  mov     rcx, [rbp+57h+var_38]; HKEY
0x18000272d  mov     [rsp+0A0h+var_60], rax; int *
0x180002732  mov     rax, cs:off_18001E030; "ConcatenateDefaults_AllowDefault"
0x180002739  mov     [rsp+0A0h+var_68], r12; unsigned __int64
0x18000273e  mov     [rsp+0A0h+var_70], r12; unsigned __int16 *
0x180002743  mov     [rsp+0A0h+var_78], rax; unsigned __int16 *
0x180002748  mov     [rsp+0A0h+phkResult], r12; unsigned __int16 *
0x18000274d  call    ?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z; CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)
0x180002752  mov     esi, eax
0x180002754  test    eax, eax
0x180002756  jns     loc_1800028B9
0x18000275c  mov     rcx, [rbp+57h+var_38]; hKey
0x180002760  test    rcx, rcx
0x180002763  jnz     loc_1800028CE
0x180002769  mov     rcx, [rbp+57h+hKey]; hKey
0x18000276d  test    rcx, rcx
0x180002770  jnz     loc_180002809
0x180002776  test    esi, esi
0x180002778  js      loc_1800028D9
0x18000277e  test    r14d, r14d
0x180002781  jz      short loc_1800027CA
0x180002783  lea     rdx, [rbp+57h+var_48]; struct _TS_CREDENTIAL **
0x180002787  mov     rcx, rbx; struct _SECPKG_PRIMARY_CRED *
0x18000278a  call    ?TSCreateNewCredential@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_TS_CREDENTIAL@@@Z; TSCreateNewCredential(_SECPKG_PRIMARY_CRED *,_TS_CREDENTIAL * *)
0x18000278f  mov     edi, eax
0x180002791  test    eax, eax
0x180002793  jns     loc_180002947
0x180002799  mov     rsi, [rbp+57h+var_48]
0x18000279d  test    rsi, rsi
0x1800027a0  jnz     short loc_1800027F1
0x1800027a2  mov     rsi, [rsp+0A0h+arg_0]
0x1800027aa  mov     r14, [rsp+0A0h+var_20]
0x1800027b2  mov     eax, edi
0x1800027b4  mov     rdi, [rsp+0A0h+arg_8]
0x1800027bc  add     rsp, 88h
0x1800027c3  pop     r15
0x1800027c5  pop     r12
0x1800027c7  pop     rbx
0x1800027c8  pop     rbp
0x1800027c9  retn
0x1800027ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027d1  cmp     rcx, r15
0x1800027d4  jnz     loc_180002923
0x1800027da  lea     r8, [rbx+18h]
0x1800027de  xor     r9d, r9d
0x1800027e1  lea     rdx, [rbx+8]
0x1800027e5  lea     rcx, [rbp+57h+var_30]
0x1800027e9  call    cs:__imp_LsaIEventWritePackageNotCacheLogonUser
0x1800027ef  jmp     short loc_1800027A2
0x1800027f1  mov     eax, 0FFFFFFFFh
0x1800027f6  lock xadd [rsi], eax
0x1800027fa  sub     eax, 1
0x1800027fd  jg      short loc_1800027A2
0x1800027ff  mov     rcx, rsi; struct _TS_CREDENTIAL *
0x180002802  call    ?TSFreeCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSFreeCredential(_TS_CREDENTIAL *)
0x180002807  jmp     short loc_1800027A2
0x180002809  call    cs:__imp_RegCloseKey
0x18000280f  jmp     loc_180002776
0x180002814  mov     eax, [r8]
0x180002817  mov     rcx, [rcx+10h]
0x18000281b  mov     dword ptr [rsp+0A0h+var_70], eax
0x18000281f  mov     eax, [r8+4]
0x180002823  mov     dword ptr [rsp+0A0h+var_78], eax
0x180002827  mov     [rsp+0A0h+phkResult], rdx
0x18000282c  call    WPP_SF_dZDD
0x180002831  mov     rcx, cs:WPP_GLOBAL_Control
0x180002838  jmp     loc_1800025C9
0x18000283d  cmp     [rbx+4], r12d
0x180002841  jz      loc_18000260A
0x180002847  jmp     loc_1800025EC
0x18000284c  cmp     [rbx+4], r12d
0x180002850  jz      loc_18000260A
0x180002856  jmp     loc_1800025EC
0x18000285b  mov     rcx, [rcx+10h]
0x18000285f  lea     r9, aSpacceptcreden; "SpAcceptCredentials"
0x180002866  mov     edx, 1Eh
0x18000286b  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002872  call    WPP_SF_s
0x180002877  jmp     loc_1800026B5
0x18000287c  cmp     rcx, r15
0x18000287f  jz      short loc_18000289C
0x180002881  test    byte ptr [rcx+1Ch], 8
0x180002885  jz      short loc_18000289C
0x180002887  mov     rcx, [rcx+10h]
0x18000288b  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002892  mov     edx, 1Fh
0x180002897  call    WPP_SF_
0x18000289c  lea     r8, [rbx+18h]
0x1800028a0  mov     r9d, 1
0x1800028a6  lea     rdx, [rbx+8]
0x1800028aa  lea     rcx, [rbp+57h+var_30]
0x1800028ae  call    cs:__imp_LsaIEventWritePackageNotCacheLogonUser
0x1800028b4  jmp     loc_1800027AA
0x1800028b9  cmp     [rbp+57h+var_50], r12d
0x1800028bd  jz      loc_18000275C
0x1800028c3  mov     r14d, 1
0x1800028c9  jmp     loc_18000275C
0x1800028ce  call    cs:__imp_RegCloseKey
0x1800028d4  jmp     loc_180002769
0x1800028d9  movzx   edi, si
0x1800028dc  mov     eax, edi
0x1800028de  or      eax, 0C0070000h
0x1800028e3  test    edi, edi
0x1800028e5  cmovnz  edi, eax
0x1800028e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028ef  cmp     rcx, r15
0x1800028f2  jz      loc_1800027A2
0x1800028f8  test    byte ptr [rcx+1Ch], 1
0x1800028fc  jz      loc_1800027A2
0x180002902  mov     rcx, [rcx+10h]
0x180002906  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x18000290d  mov     edx, 20h ; ' '
0x180002912  mov     dword ptr [rsp+0A0h+phkResult], edi
0x180002916  mov     r9d, esi
0x180002919  call    WPP_SF_DD
0x18000291e  jmp     loc_1800027A2
0x180002923  test    byte ptr [rcx+1Ch], 8
0x180002927  jz      loc_1800027DA
0x18000292d  mov     rcx, [rcx+10h]
0x180002931  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002938  mov     edx, 21h ; '!'
0x18000293d  call    WPP_SF_
0x180002942  jmp     loc_1800027DA
0x180002947  lea     rdx, [rbp+57h+arg_10]; unsigned __int8 *
0x18000294b  lea     rcx, [rbp+57h+var_48]; struct _TS_CREDENTIAL **
0x18000294f  call    ?TSCredTableLocate@@YAJPEAPEAU_TS_CREDENTIAL@@PEAE@Z; TSCredTableLocate(_TS_CREDENTIAL * *,uchar *)
0x180002954  mov     edi, eax
0x180002956  test    eax, eax
0x180002958  js      loc_180002799
0x18000295e  cmp     [rbp+57h+arg_10], r12b
0x180002962  jnz     short loc_180002974
0x180002964  lea     rcx, [rbp+57h+var_48]; struct _TS_CREDENTIAL **
0x180002968  call    ?TSCredTableInsertOrLocate@@YAJPEAPEAU_TS_CREDENTIAL@@@Z; TSCredTableInsertOrLocate(_TS_CREDENTIAL * *)
0x18000296d  mov     edi, eax
0x18000296f  jmp     loc_180002799
0x180002974  mov     rsi, [rbp+57h+var_48]
0x180002978  mov     rcx, rbx; struct _SECPKG_PRIMARY_CRED *
0x18000297b  mov     rdx, rsi; struct _TS_CREDENTIAL *
0x18000297e  call    ?TSUpdateCredentialsPassword@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_TS_CREDENTIAL@@@Z; TSUpdateCredentialsPassword(_SECPKG_PRIMARY_CRED *,_TS_CREDENTIAL *)
0x180002983  mov     edi, eax
0x180002985  jmp     loc_18000279D
0x18000298a  mov     rcx, [rcx+10h]
0x18000298e  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002995  mov     edx, 1Dh
0x18000299a  call    WPP_SF_d
0x18000299f  jmp     loc_18000260A
```
