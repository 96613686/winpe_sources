# SpInitialize

- ea: `0x180026ad0`
- end: `0x180026ffb`
- name: `SpInitialize`
- size: `1323`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003520`
- `0x180007aa0`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x1800187bc`
- `0x18001a8ec`
- `0x18002494c`
- `0x180026570`
- `0x1800265e4`
- `0x1800268f4`
- `0x180026ad0`
- `0x1800272f0`
- `0x18002a26c`
- `0x1800332dc`
- `0x180033680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bef`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180026bc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180026bc9`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180026e5d`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180026e5d`
- `ntdll!RtlGetNtProductType` at `0x180026c82`
- `ntdll!RtlGetNtProductType` at `0x180026c82`
- `ntdll!RtlInitUnicodeString` at `0x180026bb7`
- `ntdll!RtlInitUnicodeString` at `0x180026bb7`
- `ntdll!RtlInitializeCriticalSection` at `0x180026e6a`
- `ntdll!RtlInitializeCriticalSection` at `0x180026eed`
- `ntdll!RtlInitializeCriticalSection` at `0x180026e6a`
- `ntdll!RtlInitializeCriticalSection` at `0x180026eed`

## pseudocode

```c
__int64 __fastcall SpInitialize(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  enum _NT_PRODUCT_TYPE v11; // eax
  void *v12; // rdx
  NTSTATUS v13; // eax
  __int64 v14; // r9
  NTSTATUS v15; // eax
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+30h] [rbp-68h] BYREF
  DWORD nSize; // [rsp+34h] [rbp-64h] BYREF
  WCHAR Buffer[16]; // [rsp+38h] [rbp-60h] BYREF

  nSize = 16;
  ProductType = NtProductWinNt;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
  g_TimeForever = 0x7FFFFFFFFFFFFFFFLL;
  g_strNtDigestUTF8ServerRealm = 0;
  g_NtDigestState = 1;
  g_strNTDigestISO8859ServerRealm = 0;
  v5 = (*(_DWORD *)(a2 + 4) >> 5) & 1;
  *(_QWORD *)&g_LsaFunctions = a3;
  g_IsCredGuardEnabled = v5;
  v6 = InitializeDefaultCipherList();
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 15;
    goto LABEL_75;
  }
  NtDigestInitReadRegistry();
  RtlInitUnicodeString(&g_ustrNtDigestPackageName, L"WDigest");
  if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    v6 = UnicodeStringWCharDuplicate(&g_ustrWorkstationName, Buffer, 0);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_77;
      v9 = 17;
      goto LABEL_75;
    }
  }
  else
  {
    g_ustrWorkstationName = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, LastError);
    }
  }
  v6 = NonceInitialize();
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 18;
    goto LABEL_75;
  }
  if ( RtlGetNtProductType(&ProductType) )
  {
    v11 = ProductType;
  }
  else
  {
    v11 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( v11 == NtProductLanManNt )
    g_fDomainController = 1;
  dword_1800459E4 = *(_DWORD *)(a2 + 4);
  dword_1800459E8 = *(_DWORD *)(a2 + 8);
  g_NtDigestSecPkg = *(_DWORD *)a2;
  v6 = UnicodeStringDuplicate(&stru_180045A08, a2 + 40);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 19;
    goto LABEL_75;
  }
  v6 = UnicodeStringDuplicate(&word_1800459F8, a2 + 24);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 20;
    goto LABEL_75;
  }
  v12 = *(void **)(a2 + 16);
  if ( v12 )
  {
    v6 = SidDuplicate(&hMem, v12);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_77;
      v9 = 21;
      goto LABEL_75;
    }
  }
  else
  {
    hMem = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids,
      &stru_180045A08,
      &word_1800459F8);
  if ( (int)EncodeUnicodeString(&stru_180045A08.Length, 0x6FAFu, (__int64)&g_strNTDigestISO8859ServerRealm, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
    g_strNTDigestISO8859ServerRealm = 0;
  }
  if ( (int)EncodeUnicodeString(&stru_180045A08.Length, 0xFDE9u, (__int64)&g_strNtDigestUTF8ServerRealm, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
    g_strNtDigestUTF8ServerRealm = 0;
  }
  strcpy(g_DigestSource.SourceName, "WDIGEST");
  NtAllocateLocallyUniqueId(&g_DigestSource.SourceIdentifier);
  v13 = RtlInitializeCriticalSection(&l_LogSessCritSect);
  v7 = v13;
  if ( v13 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_77;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids,
        (unsigned int)v13);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 25;
    goto LABEL_59;
  }
  g_bLogSessInitialized = 1;
  qword_180045970 = (__int64)&l_LogSessList;
  l_LogSessList = &l_LogSessList;
  v15 = RtlInitializeCriticalSection(&l_CredentialCritSect);
  v7 = v15;
  if ( v15 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_77;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids,
        (unsigned int)v15);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 26;
LABEL_59:
    v14 = v7;
LABEL_76:
    WPP_SF_d(v8[2], v9, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, v14);
    goto LABEL_77;
  }
  g_bCredentialsInitialized = 1;
  qword_1800456B0 = (__int64)&l_CredentialList;
  l_CredentialList.Flink = &l_CredentialList;
  v6 = CtxtHandlerInit();
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_77;
    v9 = 27;
    goto LABEL_75;
  }
  v6 = SsiIHandlerInit();
  v7 = v6;
  if ( v6 >= 0 )
  {
    SPLoadRegOptions();
    goto LABEL_79;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 28;
LABEL_75:
    v14 = (unsigned int)v6;
    goto LABEL_76;
  }
LABEL_77:
  SpShutdown();
LABEL_79:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x180026ad0  push    rbx
0x180026ad2  push    rbp
0x180026ad3  push    rsi
0x180026ad4  push    rdi
0x180026ad5  push    r12
0x180026ad7  push    r14
0x180026ad9  sub     rsp, 68h
0x180026add  mov     rax, cs:__security_cookie
0x180026ae4  xor     rax, rsp
0x180026ae7  mov     [rsp+98h+var_40], rax
0x180026aec  mov     esi, 1
0x180026af1  mov     [rsp+98h+nSize], 10h
0x180026af9  mov     [rsp+98h+ProductType], esi
0x180026afd  mov     rbx, r8
0x180026b00  mov     rdi, rdx
0x180026b03  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b0a  lea     rbp, WPP_GLOBAL_Control
0x180026b11  lea     r14, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026b18  cmp     rcx, rbp
0x180026b1b  jz      short loc_180026B32
0x180026b1d  test    byte ptr [rcx+1Ch], 80h
0x180026b21  jz      short loc_180026B32
0x180026b23  mov     rcx, [rcx+10h]
0x180026b27  lea     edx, [rsi+0Dh]
0x180026b2a  mov     r8, r14
0x180026b2d  call    WPP_SF_
0x180026b32  xorps   xmm0, xmm0
0x180026b35  mov     dword ptr cs:g_TimeForever+4, 7FFFFFFFh
0x180026b3f  xorps   xmm1, xmm1
0x180026b42  mov     dword ptr cs:g_TimeForever, 0FFFFFFFFh
0x180026b4c  movups  cs:g_strNtDigestUTF8ServerRealm, xmm0
0x180026b53  mov     cs:g_NtDigestState, esi
0x180026b59  movups  cs:g_strNTDigestISO8859ServerRealm, xmm1
0x180026b60  mov     eax, [rdi+4]
0x180026b63  shr     eax, 5
0x180026b66  and     eax, esi
0x180026b68  mov     cs:g_LsaFunctions, rbx
0x180026b6f  mov     cs:g_IsCredGuardEnabled, eax
0x180026b75  call    InitializeDefaultCipherList
0x180026b7a  mov     ebx, eax
0x180026b7c  test    eax, eax
0x180026b7e  jns     short loc_180026BA4
0x180026b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b87  cmp     rcx, rbp
0x180026b8a  jz      loc_180026FB0
0x180026b90  test    [rcx+1Ch], sil
0x180026b94  jz      loc_180026FB0
0x180026b9a  mov     edx, 0Fh
0x180026b9f  jmp     loc_180026FA1
0x180026ba4  call    NtDigestInitReadRegistry
0x180026ba9  lea     rdx, aWdigest; "WDigest"
0x180026bb0  lea     rcx, g_ustrNtDigestPackageName; DestinationString
0x180026bb7  call    cs:__imp_RtlInitUnicodeString
0x180026bbd  lea     r8, [rsp+98h+nSize]; nSize
0x180026bc2  xor     ecx, ecx; NameType
0x180026bc4  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x180026bc9  call    cs:__imp_GetComputerNameExW
0x180026bcf  test    eax, eax
0x180026bd1  jnz     short loc_180026C3F
0x180026bd3  xorps   xmm0, xmm0
0x180026bd6  movups  xmmword ptr cs:g_ustrWorkstationName.Length, xmm0
0x180026bdd  mov     rax, cs:WPP_GLOBAL_Control
0x180026be4  cmp     rax, rbp
0x180026be7  jz      short loc_180026C10
0x180026be9  test    [rax+1Ch], sil
0x180026bed  jz      short loc_180026C10
0x180026bef  call    cs:__imp_GetLastError
0x180026bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bfc  mov     edx, 10h
0x180026c01  mov     r9d, eax
0x180026c04  mov     r8, r14
0x180026c07  mov     rcx, [rcx+10h]
0x180026c0b  call    WPP_SF_d
0x180026c10  call    NonceInitialize
0x180026c15  mov     ebx, eax
0x180026c17  test    eax, eax
0x180026c19  jns     short loc_180026C7D
0x180026c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c22  cmp     rcx, rbp
0x180026c25  jz      loc_180026FB0
0x180026c2b  test    [rcx+1Ch], sil
0x180026c2f  jz      loc_180026FB0
0x180026c35  mov     edx, 12h
0x180026c3a  jmp     loc_180026FA1
0x180026c3f  xor     r8d, r8d
0x180026c42  lea     rdx, [rsp+98h+Buffer]
0x180026c47  lea     rcx, g_ustrWorkstationName
0x180026c4e  call    UnicodeStringWCharDuplicate
0x180026c53  mov     ebx, eax
0x180026c55  test    eax, eax
0x180026c57  jns     short loc_180026C10
0x180026c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c60  cmp     rcx, rbp
0x180026c63  jz      loc_180026FB0
0x180026c69  test    [rcx+1Ch], sil
0x180026c6d  jz      loc_180026FB0
0x180026c73  mov     edx, 11h
0x180026c78  jmp     loc_180026FA1
0x180026c7d  lea     rcx, [rsp+98h+ProductType]; ProductType
0x180026c82  call    cs:__imp_RtlGetNtProductType
0x180026c88  test    al, al
0x180026c8a  jnz     short loc_180026C94
0x180026c8c  mov     eax, esi
0x180026c8e  mov     [rsp+98h+ProductType], eax
0x180026c92  jmp     short loc_180026C98
0x180026c94  mov     eax, [rsp+98h+ProductType]
0x180026c98  cmp     eax, 2
0x180026c9b  jnz     short loc_180026CA3
0x180026c9d  mov     cs:g_fDomainController, esi
0x180026ca3  mov     eax, [rdi+4]
0x180026ca6  lea     rdx, [rdi+28h]
0x180026caa  mov     cs:dword_1800459E4, eax
0x180026cb0  lea     rcx, stru_180045A08
0x180026cb7  mov     eax, [rdi+8]
0x180026cba  mov     cs:dword_1800459E8, eax
0x180026cc0  mov     eax, [rdi]
0x180026cc2  mov     cs:g_NtDigestSecPkg, eax
0x180026cc8  call    UnicodeStringDuplicate
0x180026ccd  mov     ebx, eax
0x180026ccf  test    eax, eax
0x180026cd1  jns     short loc_180026CF7
0x180026cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cda  cmp     rcx, rbp
0x180026cdd  jz      loc_180026FB0
0x180026ce3  test    [rcx+1Ch], sil
0x180026ce7  jz      loc_180026FB0
0x180026ced  mov     edx, 13h
0x180026cf2  jmp     loc_180026FA1
0x180026cf7  lea     r12, word_1800459F8
0x180026cfe  mov     rcx, r12
0x180026d01  lea     rdx, [rdi+18h]
0x180026d05  call    UnicodeStringDuplicate
0x180026d0a  mov     ebx, eax
0x180026d0c  test    eax, eax
0x180026d0e  jns     short loc_180026D34
0x180026d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d17  cmp     rcx, rbp
0x180026d1a  jz      loc_180026FB0
0x180026d20  test    [rcx+1Ch], sil
0x180026d24  jz      loc_180026FB0
0x180026d2a  mov     edx, 14h
0x180026d2f  jmp     loc_180026FA1
0x180026d34  mov     rdx, [rdi+10h]
0x180026d38  test    rdx, rdx
0x180026d3b  jz      short loc_180026D73
0x180026d3d  lea     rcx, hMem
0x180026d44  call    SidDuplicate
0x180026d49  mov     ebx, eax
0x180026d4b  test    eax, eax
0x180026d4d  jns     short loc_180026D7E
0x180026d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d56  cmp     rcx, rbp
0x180026d59  jz      loc_180026FB0
0x180026d5f  test    [rcx+1Ch], sil
0x180026d63  jz      loc_180026FB0
0x180026d69  mov     edx, 15h
0x180026d6e  jmp     loc_180026FA1
0x180026d73  mov     cs:hMem, 0
0x180026d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d85  cmp     rcx, rbp
0x180026d88  jz      short loc_180026DAD
0x180026d8a  test    byte ptr [rcx+1Ch], 4
0x180026d8e  jz      short loc_180026DAD
0x180026d90  mov     rcx, [rcx+10h]
0x180026d94  lea     r9, stru_180045A08
0x180026d9b  mov     edx, 16h
0x180026da0  mov     [rsp+98h+var_78], r12
0x180026da5  mov     r8, r14
0x180026da8  call    WPP_SF_ZZ
0x180026dad  xor     r9d, r9d
0x180026db0  lea     r8, g_strNTDigestISO8859ServerRealm
0x180026db7  mov     edx, 6FAFh
0x180026dbc  lea     rcx, stru_180045A08
0x180026dc3  call    EncodeUnicodeString
0x180026dc8  test    eax, eax
0x180026dca  jns     short loc_180026DF9
0x180026dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dd3  cmp     rcx, rbp
0x180026dd6  jz      short loc_180026DEF
0x180026dd8  test    byte ptr [rcx+1Ch], 2
0x180026ddc  jz      short loc_180026DEF
0x180026dde  mov     rcx, [rcx+10h]
0x180026de2  mov     edx, 17h
0x180026de7  mov     r8, r14
0x180026dea  call    WPP_SF_
0x180026def  xorps   xmm0, xmm0
0x180026df2  movups  cs:g_strNTDigestISO8859ServerRealm, xmm0
0x180026df9  xor     r9d, r9d
0x180026dfc  lea     r8, g_strNtDigestUTF8ServerRealm
0x180026e03  mov     edx, 0FDE9h
0x180026e08  lea     rcx, stru_180045A08
0x180026e0f  call    EncodeUnicodeString
0x180026e14  test    eax, eax
0x180026e16  jns     short loc_180026E45
0x180026e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e1f  cmp     rcx, rbp
0x180026e22  jz      short loc_180026E3B
0x180026e24  test    byte ptr [rcx+1Ch], 2
0x180026e28  jz      short loc_180026E3B
0x180026e2a  mov     rcx, [rcx+10h]
0x180026e2e  mov     edx, 18h
0x180026e33  mov     r8, r14
0x180026e36  call    WPP_SF_
0x180026e3b  xorps   xmm0, xmm0
0x180026e3e  movups  cs:g_strNtDigestUTF8ServerRealm, xmm0
0x180026e45  mov     rax, 54534547494457h
0x180026e4f  lea     rcx, g_DigestSource.SourceIdentifier; LocallyUniqueId
0x180026e56  mov     qword ptr cs:g_DigestSource.SourceName, rax
0x180026e5d  call    cs:__imp_NtAllocateLocallyUniqueId
0x180026e63  lea     rcx, ?l_LogSessCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180026e6a  call    cs:__imp_RtlInitializeCriticalSection
0x180026e70  mov     ebx, eax
0x180026e72  test    eax, eax
0x180026e74  jns     short loc_180026ECB
0x180026e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e7d  cmp     rcx, rbp
0x180026e80  jz      loc_180026FB0
0x180026e86  test    [rcx+1Ch], sil
0x180026e8a  jz      short loc_180026EAB
0x180026e8c  mov     rcx, [rcx+10h]
0x180026e90  lea     r8, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids
0x180026e97  mov     edx, 0Ah
0x180026e9c  mov     r9d, eax
0x180026e9f  call    WPP_SF_d
0x180026ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180026eab  cmp     rcx, rbp
0x180026eae  jz      loc_180026FB0
0x180026eb4  test    [rcx+1Ch], sil
0x180026eb8  jz      loc_180026FB0
0x180026ebe  mov     edx, 19h
0x180026ec3  mov     r9d, ebx
0x180026ec6  jmp     loc_180026FA4
0x180026ecb  lea     rax, ?l_LogSessList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_LogSessList
0x180026ed2  mov     cs:?g_bLogSessInitialized@@3HA, esi; int g_bLogSessInitialized
0x180026ed8  lea     rcx, ?l_CredentialCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180026edf  mov     cs:qword_180045970, rax
0x180026ee6  mov     cs:?l_LogSessList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY l_LogSessList
0x180026eed  call    cs:__imp_RtlInitializeCriticalSection
0x180026ef3  mov     ebx, eax
0x180026ef5  test    eax, eax
0x180026ef7  jns     short loc_180026F40
0x180026ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f00  cmp     rcx, rbp
0x180026f03  jz      loc_180026FB0
0x180026f09  test    [rcx+1Ch], sil
0x180026f0d  jz      short loc_180026F2E
0x180026f0f  mov     rcx, [rcx+10h]
0x180026f13  lea     r8, WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids
0x180026f1a  mov     edx, 0Ah
0x180026f1f  mov     r9d, eax
0x180026f22  call    WPP_SF_d
0x180026f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f2e  cmp     rcx, rbp
0x180026f31  jz      short loc_180026FB0
0x180026f33  test    [rcx+1Ch], sil
0x180026f37  jz      short loc_180026FB0
0x180026f39  mov     edx, 1Ah
0x180026f3e  jmp     short loc_180026EC3
0x180026f40  lea     rax, ?l_CredentialList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_CredentialList
0x180026f47  mov     cs:?g_bCredentialsInitialized@@3HA, esi; int g_bCredentialsInitialized
0x180026f4d  mov     cs:qword_1800456B0, rax
0x180026f54  mov     cs:?l_CredentialList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY l_CredentialList
0x180026f5b  call    CtxtHandlerInit
0x180026f60  mov     ebx, eax
0x180026f62  test    eax, eax
0x180026f64  jns     short loc_180026F7F
0x180026f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f6d  cmp     rcx, rbp
0x180026f70  jz      short loc_180026FB0
0x180026f72  test    [rcx+1Ch], sil
0x180026f76  jz      short loc_180026FB0
0x180026f78  mov     edx, 1Bh
0x180026f7d  jmp     short loc_180026FA1
0x180026f7f  call    SsiIHandlerInit
0x180026f84  mov     ebx, eax
0x180026f86  test    eax, eax
0x180026f88  jns     short loc_180026FB7
0x180026f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f91  cmp     rcx, rbp
0x180026f94  jz      short loc_180026FB0
0x180026f96  test    [rcx+1Ch], sil
0x180026f9a  jz      short loc_180026FB0
0x180026f9c  mov     edx, 1Ch
0x180026fa1  mov     r9d, eax
0x180026fa4  mov     rcx, [rcx+10h]
0x180026fa8  mov     r8, r14
0x180026fab  call    WPP_SF_d
0x180026fb0  call    SpShutdown
0x180026fb5  jmp     short loc_180026FBC
0x180026fb7  call    SPLoadRegOptions
0x180026fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fc3  cmp     rcx, rbp
0x180026fc6  jz      short loc_180026FDF
0x180026fc8  test    byte ptr [rcx+1Ch], 80h
0x180026fcc  jz      short loc_180026FDF
0x180026fce  mov     rcx, [rcx+10h]
0x180026fd2  mov     edx, 1Dh
0x180026fd7  mov     r8, r14
0x180026fda  call    WPP_SF_
0x180026fdf  mov     eax, ebx
  ... truncated ...
```
