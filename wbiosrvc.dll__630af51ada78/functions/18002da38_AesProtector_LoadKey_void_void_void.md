# AesProtector::LoadKey(void *,void *,void * *)

- ea: `0x18002da38`
- end: `0x18002dd68`
- name: `?LoadKey@AesProtector@@AEAAJPEAX0PEAPEAX@Z`
- size: `816`
- prototype: `int(AesProtector *__hidden this, void *, void *, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d6a0`
- `0x1800926a0`

## callees

- `0x18002d538`
- `0x18002da38`
- `0x18002dd70`
- `0x1800382f4`
- `0x180039380`
- `0x18003c8dc`
- `0x18003ecc8`
- `0x180060dc8`
- `0x180068f60`
- `0x180091f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc39`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002da86`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002da86`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002db67`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002db67`
- `bcrypt!BCryptImportKey` at `0x18002dd06`
- `bcrypt!BCryptImportKey` at `0x18002dd06`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18002dc2f`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18002dc2f`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x18002dbd5`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x18002dbd5`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002db46`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002dc53`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002dc6c`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002db46`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002dc53`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18002dc6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AesProtector::LoadKey(AesProtector *this, void *a2, void *a3, void **a4)
{
  unsigned __int8 *pbInput; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  WCHAR *v11; // r15
  int v12; // edi
  signed int Item; // eax
  __int64 v14; // rcx
  bool v15; // cc
  __int64 v16; // rdx
  AesProtector *v17; // rcx
  __int64 v18; // rax
  LPWSTR i; // rcx
  AesProtector *v20; // rcx
  NTSTATUS v21; // eax
  __int64 v23; // [rsp+50h] [rbp-E8h] BYREF
  DWORD pcchMaxChars; // [rsp+58h] [rbp-E0h] BYREF
  __int16 v25; // [rsp+5Ch] [rbp-DCh] BYREF
  unsigned __int8 *v26; // [rsp+60h] [rbp-D8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-D0h] BYREF
  ULONG cbInput[2]; // [rsp+70h] [rbp-C8h] BYREF
  __int128 v29; // [rsp+78h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+88h] [rbp-B0h]
  LPWSTR pszCredentials[3]; // [rsp+98h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-88h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-78h]
  __int64 *v34; // [rsp+D0h] [rbp-68h]
  __int64 v35; // [rsp+D8h] [rbp-60h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-58h]

  phKey = 0;
  pbInput = 0;
  v26 = 0;
  *(_QWORD *)cbInput = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !IsValidSid(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  try
  {
    v25 = 0;
    std::vector<unsigned short>::vector<unsigned short>(pszCredentials, v8, &v25);
    pcchMaxChars = 2049;
    v35 = 0;
    v36 = Vault_DefaultVault_ID;
    if ( !IsVaultApiPresent() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    v32 = 0;
    v33 = 0;
    v29 = 0;
    v30 = 0;
    v23 = 0;
    v34 = &v23;
    v11 = pszCredentials[0];
    v12 = CBioKeyVault::_OpenVault((CBioKeyVault *)&v35);
    if ( v12 < 0 )
    {
      VaultFree(v23);
LABEL_28:
      CBioKeyVault::~CBioKeyVault((CBioKeyVault *)&v35);
      std::vector<unsigned short>::_Tidy(pszCredentials);
      if ( v12 >= 0 )
      {
        v21 = BCryptImportKey(a3, 0, L"KeyDataBlob", &phKey, 0, 0, pbInput, cbInput[0], 0);
        if ( v21 < 0 )
        {
          v12 = v21 | 0x10000000;
        }
        else
        {
          *a4 = phKey;
          phKey = 0;
        }
      }
      goto LABEL_38;
    }
    LODWORD(v29) = 2;
    DWORD2(v29) = 8;
    LODWORD(v30) = GetLengthSid(a2);
    *((_QWORD *)&v30 + 1) = a2;
    LODWORD(v32) = 1;
    DWORD2(v32) = 7;
    *(_QWORD *)&v33 = L"WinBio Key Resource";
    Item = VaultGetItem(v35, &CBioKeyVault::_guidSchema, &v32, &v29, 0, 0, 0, &v23);
    v12 = Item;
    v15 = Item <= 0;
    if ( !Item )
    {
      v16 = v23;
      if ( *(_DWORD *)(*(_QWORD *)(v23 + 40) + 8LL) != 8 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v14);
        v16 = v23;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(v16 + 40) + 16LL) & 1) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v14);
        v16 = v23;
      }
      if ( CredUnprotectW(
             1,
             *(LPWSTR *)(*(_QWORD *)(v16 + 40) + 24LL),
             *(_DWORD *)(*(_QWORD *)(v16 + 40) + 16LL) >> 1,
             v11,
             &pcchMaxChars) )
      {
        VaultFree(v23);
        v23 = 0;
LABEL_25:
        v12 = AesProtector::DecodeKey(v17, pszCredentials[0], pcchMaxChars, &v26, (unsigned __int64 *)cbInput);
        v18 = 2LL * pcchMaxChars;
        for ( i = pszCredentials[0]; v18; --v18 )
        {
          *(_BYTE *)i = 0;
          i = (LPWSTR)((char *)i + 1);
        }
        pbInput = v26;
        goto LABEL_28;
      }
      Item = GetLastError();
      v12 = Item;
      v15 = Item <= 0;
    }
    if ( !v15 )
      v12 = (unsigned __int16)Item | 0x80070000;
    VaultFree(v23);
    v23 = 0;
    if ( v12 < 0 )
      goto LABEL_28;
    goto LABEL_25;
  }
  catch ( std::bad_alloc )
  {
    pcchMaxChars = -2147024882;
    v12 = -2147024882;
    pbInput = v26;
  }
LABEL_38:
  if ( pbInput )
    AesProtector::MemZeroAndRelease(v20, pbInput, *(unsigned __int64 *)cbInput);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002da38  push    rbx
0x18002da3a  push    rsi
0x18002da3b  push    rdi
0x18002da3c  push    r12
0x18002da3e  push    r13
0x18002da40  push    r14
0x18002da42  push    r15
0x18002da44  sub     rsp, 100h
0x18002da4b  mov     rax, cs:__security_cookie
0x18002da52  xor     rax, rsp
0x18002da55  mov     [rsp+138h+var_48], rax
0x18002da5d  mov     r12, r9
0x18002da60  mov     r13, r8
0x18002da63  mov     r14, rdx
0x18002da66  xor     ebx, ebx
0x18002da68  mov     [rsp+138h+phKey], rbx
0x18002da6d  mov     esi, ebx
0x18002da6f  mov     [rsp+138h+var_D8], rbx
0x18002da74  mov     qword ptr [rsp+138h+var_C8], rbx
0x18002da79  test    rdx, rdx
0x18002da7c  jnz     short loc_18002DA83
0x18002da7e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da83  mov     rcx, r14; pSid
0x18002da86  call    cs:__imp_IsValidSid
0x18002da8c  test    eax, eax
0x18002da8e  jnz     short loc_18002DA95
0x18002da90  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da95  test    r13, r13
0x18002da98  jnz     short loc_18002DA9F
0x18002da9a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da9f  test    r12, r12
0x18002daa2  jnz     short loc_18002DAAA
0x18002daa4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002daa9  nop
0x18002daaa  mov     [rsp+138h+var_DC], bx
0x18002daaf  lea     r8, [rsp+138h+var_DC]
0x18002dab4  lea     rcx, [rsp+138h+pszCredentials]
0x18002dabc  call    ??$?0V?$allocator@G@std@@$0A@@?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBGAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,ushort const &,std::allocator<ushort> const &)
0x18002dac1  nop
0x18002dac2  mov     [rsp+138h+var_E0], 801h
0x18002daca  mov     [rsp+138h+var_60], rbx
0x18002dad2  movups  xmm0, cs:Vault_DefaultVault_ID
0x18002dad9  movdqu  [rsp+138h+var_58], xmm0
0x18002dae2  call    ?IsVaultApiPresent@@YA_NXZ; IsVaultApiPresent(void)
0x18002dae7  test    al, al
0x18002dae9  jnz     short loc_18002DAF1
0x18002daeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002daf0  nop
0x18002daf1  xorps   xmm0, xmm0
0x18002daf4  movups  [rsp+138h+var_88], xmm0
0x18002dafc  movups  [rsp+138h+var_78], xmm0
0x18002db04  xorps   xmm1, xmm1
0x18002db07  movups  [rsp+138h+var_C0], xmm1
0x18002db0c  movups  [rsp+138h+var_B0], xmm1
0x18002db14  mov     [rsp+138h+var_E8], rbx
0x18002db19  lea     rax, [rsp+138h+var_E8]
0x18002db1e  mov     [rsp+138h+var_68], rax
0x18002db26  mov     r15, [rsp+138h+pszCredentials]
0x18002db2e  lea     rcx, [rsp+138h+var_60]; this
0x18002db36  call    ?_OpenVault@CBioKeyVault@@AEAAJXZ; CBioKeyVault::_OpenVault(void)
0x18002db3b  mov     edi, eax
0x18002db3d  test    eax, eax
0x18002db3f  jns     short loc_18002DB51
0x18002db41  mov     rcx, [rsp+138h+var_E8]
0x18002db46  call    cs:__imp_VaultFree
0x18002db4c  jmp     loc_18002DCBB
0x18002db51  mov     dword ptr [rsp+138h+var_C0], 2
0x18002db59  mov     dword ptr [rsp+138h+var_C0+8], 8
0x18002db64  mov     rcx, r14; pSid
0x18002db67  call    cs:__imp_GetLengthSid
0x18002db6d  mov     dword ptr [rsp+138h+var_B0], eax
0x18002db74  mov     qword ptr [rsp+138h+var_B0+8], r14
0x18002db7c  mov     dword ptr [rsp+138h+var_88], 1
0x18002db87  mov     dword ptr [rsp+138h+var_88+8], 7
0x18002db92  lea     rax, aWinbioKeyResou; "WinBio Key Resource"
0x18002db99  mov     qword ptr [rsp+138h+var_78], rax
0x18002dba1  lea     rax, [rsp+138h+var_E8]
0x18002dba6  mov     qword ptr [rsp+138h+cbInput], rax
0x18002dbab  mov     dword ptr [rsp+138h+pbInput], ebx
0x18002dbaf  mov     qword ptr [rsp+138h+cbKeyObject], rbx
0x18002dbb4  mov     [rsp+138h+pcchMaxChars], rbx
0x18002dbb9  lea     r9, [rsp+138h+var_C0]
0x18002dbbe  lea     r8, [rsp+138h+var_88]
0x18002dbc6  lea     rdx, ?_guidSchema@CBioKeyVault@@0U_GUID@@A; _GUID CBioKeyVault::_guidSchema
0x18002dbcd  mov     rcx, [rsp+138h+var_60]
0x18002dbd5  call    cs:__imp_VaultGetItem
0x18002dbdb  mov     edi, eax
0x18002dbdd  test    eax, eax
0x18002dbdf  jnz     short loc_18002DC43
0x18002dbe1  mov     rdx, [rsp+138h+var_E8]
0x18002dbe6  mov     rax, [rdx+28h]
0x18002dbea  cmp     dword ptr [rax+8], 8
0x18002dbee  jz      short loc_18002DBFA
0x18002dbf0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dbf5  mov     rdx, [rsp+138h+var_E8]
0x18002dbfa  mov     rax, [rdx+28h]
0x18002dbfe  test    byte ptr [rax+10h], 1
0x18002dc02  jz      short loc_18002DC0E
0x18002dc04  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dc09  mov     rdx, [rsp+138h+var_E8]
0x18002dc0e  mov     rdx, [rdx+28h]
0x18002dc12  mov     r8d, [rdx+10h]
0x18002dc16  shr     r8d, 1; cchProtectedCredentials
0x18002dc19  lea     rax, [rsp+138h+var_E0]
0x18002dc1e  mov     [rsp+138h+pcchMaxChars], rax; pcchMaxChars
0x18002dc23  mov     r9, r15; pszCredentials
0x18002dc26  mov     rdx, [rdx+18h]; pszProtectedCredentials
0x18002dc2a  mov     ecx, 1; fAsSelf
0x18002dc2f  call    cs:__imp_CredUnprotectW
0x18002dc35  test    eax, eax
0x18002dc37  jnz     short loc_18002DC67
0x18002dc39  call    cs:__imp_GetLastError
0x18002dc3f  mov     edi, eax
0x18002dc41  test    eax, eax
0x18002dc43  jle     short loc_18002DC4E
0x18002dc45  movzx   edi, ax
0x18002dc48  or      edi, 80070000h
0x18002dc4e  mov     rcx, [rsp+138h+var_E8]
0x18002dc53  call    cs:__imp_VaultFree
0x18002dc59  mov     rax, rbx
0x18002dc5c  mov     [rsp+138h+var_E8], rbx
0x18002dc61  test    edi, edi
0x18002dc63  jns     short loc_18002DC77
0x18002dc65  jmp     short loc_18002DCBB
0x18002dc67  mov     rcx, [rsp+138h+var_E8]
0x18002dc6c  call    cs:__imp_VaultFree
0x18002dc72  mov     [rsp+138h+var_E8], rbx
0x18002dc77  mov     r8d, [rsp+138h+var_E0]; unsigned __int64
0x18002dc7c  lea     rax, [rsp+138h+var_C8]
0x18002dc81  mov     [rsp+138h+pcchMaxChars], rax; unsigned __int64 *
0x18002dc86  lea     r9, [rsp+138h+var_D8]; unsigned __int8 **
0x18002dc8b  mov     rdx, [rsp+138h+pszCredentials]; unsigned __int16 *
0x18002dc93  call    ?DecodeKey@AesProtector@@AEAAJPEAG_KPEAPEAEPEA_K@Z; AesProtector::DecodeKey(ushort *,unsigned __int64,uchar * *,unsigned __int64 *)
0x18002dc98  mov     edi, eax
0x18002dc9a  mov     eax, [rsp+138h+var_E0]
0x18002dc9e  add     rax, rax
0x18002dca1  mov     rcx, [rsp+138h+pszCredentials]
0x18002dca9  jz      short loc_18002DCB6
0x18002dcab  mov     [rcx], bl
0x18002dcad  inc     rcx
0x18002dcb0  sub     rax, 1
0x18002dcb4  jnz     short loc_18002DCAB
0x18002dcb6  mov     rsi, [rsp+138h+var_D8]
0x18002dcbb  lea     rcx, [rsp+138h+var_60]; this
0x18002dcc3  call    ??1CBioKeyVault@@QEAA@XZ; CBioKeyVault::~CBioKeyVault(void)
0x18002dcc8  nop
0x18002dcc9  lea     rcx, [rsp+138h+pszCredentials]
0x18002dcd1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18002dcd6  nop
0x18002dcd7  test    edi, edi
0x18002dcd9  js      short loc_18002DD31
0x18002dcdb  mov     [rsp+138h+dwFlags], ebx; dwFlags
0x18002dcdf  mov     eax, [rsp+138h+var_C8]
0x18002dce3  mov     [rsp+138h+cbInput], eax; cbInput
0x18002dce7  mov     [rsp+138h+pbInput], rsi; pbInput
0x18002dcec  mov     [rsp+138h+cbKeyObject], ebx; cbKeyObject
0x18002dcf0  mov     [rsp+138h+pcchMaxChars], rbx; pbKeyObject
0x18002dcf5  lea     r9, [rsp+138h+phKey]; phKey
0x18002dcfa  lea     r8, pszBlobType; "KeyDataBlob"
0x18002dd01  xor     edx, edx; hImportKey
0x18002dd03  mov     rcx, r13; hAlgorithm
0x18002dd06  call    cs:__imp_BCryptImportKey
0x18002dd0c  test    eax, eax
0x18002dd0e  js      short loc_18002DD20
0x18002dd10  mov     rax, [rsp+138h+phKey]
0x18002dd15  mov     [r12], rax
0x18002dd19  mov     [rsp+138h+phKey], rbx
0x18002dd1e  jmp     short loc_18002DD31
0x18002dd20  mov     edi, eax
0x18002dd22  bts     edi, 1Ch
0x18002dd26  jmp     short loc_18002DD31
0x18002dd28  mov     edi, [rsp+138h+var_E0]
0x18002dd2c  mov     rsi, [rsp+138h+var_D8]
0x18002dd31  test    rsi, rsi
0x18002dd34  jz      short loc_18002DD43
0x18002dd36  mov     r8, qword ptr [rsp+138h+var_C8]; unsigned __int64
0x18002dd3b  mov     rdx, rsi; void *
0x18002dd3e  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x18002dd43  mov     eax, edi
0x18002dd45  mov     rcx, [rsp+138h+var_48]
0x18002dd4d  xor     rcx, rsp; StackCookie
0x18002dd50  call    __security_check_cookie
0x18002dd55  add     rsp, 100h
0x18002dd5c  pop     r15
0x18002dd5e  pop     r14
0x18002dd60  pop     r13
0x18002dd62  pop     r12
0x18002dd64  pop     rdi
0x18002dd65  pop     rsi
0x18002dd66  pop     rbx
0x18002dd67  retn
```
