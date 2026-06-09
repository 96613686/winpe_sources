# SampLoadRODCRolesCache(_SAMP_RODC_ROLES_CACHE * *)

- ea: `0x180039318`
- end: `0x1800397bb`
- name: `?SampLoadRODCRolesCache@@YAJPEAPEAU_SAMP_RODC_ROLES_CACHE@@@Z`
- size: `1187`
- prototype: `__int64 __fastcall(struct _SAMP_RODC_ROLES_CACHE **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039c48`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180039318`
- `0x18003986c`
- `0x180039dd8`
- `0x180039e58`
- `0x180039ef8`
- `0x180071534`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180039571`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180039571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003960a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003960a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039709`
- `ntdll!RtlValidSid` at `0x1800395dc`
- `ntdll!RtlValidSid` at `0x1800396d9`
- `ntdll!RtlValidSid` at `0x1800395dc`
- `ntdll!RtlValidSid` at `0x1800396d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800393a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800393a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800393cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800393cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800396ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800396ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180039467`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180039467`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039536`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039536`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039367`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039367`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800394c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800395fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800396fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800395fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800396fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039788`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800395ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800396cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800395ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800396cb`

## string_xrefs

- `0x18003968e`: `RepairAdmin`

## pseudocode

```c
__int64 __fastcall SampLoadRODCRolesCache(struct _SAMP_RODC_ROLES_CACHE **a1)
{
  DWORD v1; // r15d
  WCHAR *v2; // r13
  BYTE *v3; // r14
  struct _SAMP_RODC_ROLES_CACHE *v4; // rax
  struct _SAMP_RODC_ROLES_CACHE *v5; // r12
  int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS v9; // eax
  int v10; // edi
  unsigned __int64 v11; // rcx
  const WCHAR *v12; // rsi
  unsigned __int64 v13; // rax
  unsigned int v14; // r13d
  DWORD LastError; // eax
  int v16; // edx
  int v17; // r8d
  DWORD v18; // r15d
  DWORD v19; // eax
  DWORD v20; // r15d
  char phkResult; // [rsp+20h] [rbp-59h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-19h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-15h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-11h] BYREF
  DWORD v25; // [rsp+6Ch] [rbp-Dh]
  PSID Sid; // [rsp+70h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  WCHAR *v28; // [rsp+80h] [rbp+7h]
  DWORD cbData; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+F0h] [rbp+77h] BYREF
  DWORD Type; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  hKey = 0;
  v2 = 0;
  cValues = 0;
  v3 = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  Sid = 0;
  v4 = (struct _SAMP_RODC_ROLES_CACHE *)LocalAlloc(0x40u, 0x10u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_2;
  *(_OWORD *)v4 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa\\RODCROLES", 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      v6 = -1073741823;
      if ( v7 == 8 )
        v6 = -1073741801;
      goto LABEL_65;
    }
    v6 = 0;
LABEL_6:
    *a1 = v5;
    goto LABEL_7;
  }
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v9 )
  {
    v10 = -1073741801;
    if ( v9 != 8 )
      v10 = -1073741823;
    v6 = v10;
    goto LABEL_19;
  }
  v11 = 2LL * (cbMaxValueNameLen + 1);
  if ( v11 > 0xFFFFFFFF )
  {
    v6 = -1073741675;
    goto LABEL_65;
  }
  v28 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v11);
  v2 = v28;
  if ( !v28 || (v3 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen + 4LL)) == 0 )
  {
LABEL_2:
    v6 = -1073741801;
    goto LABEL_65;
  }
  v25 = 0;
  v6 = 0;
  v12 = 0;
  if ( !cValues )
    goto LABEL_53;
  do
  {
    if ( v6 < 0 )
      break;
    cchValueName = cbMaxValueNameLen + 1;
    cbData = cbMaxValueLen + 4;
    if ( RegEnumValueW(hKey, v1, v2, &cchValueName, 0, &Type, v3, &cbData) )
      goto LABEL_52;
    if ( Type != 7 )
      goto LABEL_52;
    v13 = (unsigned __int64)cbData >> 1;
    if ( *(_WORD *)&v3[2 * v13 - 4] || *(_WORD *)&v3[2 * v13 - 2] )
      goto LABEL_52;
    v14 = _o__wtoi(v2);
    if ( !(unsigned int)SampValidateBuiltinRidForDC(v14) )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        phkResult = v14;
        v2 = v28;
        WPP_SF_Sd(
          WPP_GLOBAL_Control[3].Buffer,
          57,
          (unsigned int)WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids,
          (_DWORD)v28,
          phkResult);
      }
      else
      {
        v2 = v28;
      }
      goto LABEL_52;
    }
    v12 = (const WCHAR *)v3;
    while ( ConvertStringSidToSidW(v12, &Sid) )
    {
      if ( RtlValidSid(Sid) )
        v6 = SampRODCCacheSearch(v5, Sid, v14, 1u);
      LocalFree(Sid);
      if ( v6 == -1073741801 )
        goto LABEL_50;
LABEL_46:
      while ( *v12 )
        ++v12;
      if ( !*++v12 )
        goto LABEL_50;
    }
    LastError = GetLastError();
    v18 = LastError;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_DdS(WPP_GLOBAL_Control[3].Buffer, v16, v17, LastError, v14, (__int64)v12);
    }
    if ( v18 != 8 )
      goto LABEL_46;
    v6 = -1073741801;
LABEL_50:
    v2 = v28;
    v1 = v25;
LABEL_52:
    v25 = ++v1;
  }
  while ( v1 < cValues );
LABEL_53:
  cbData = cbMaxValueLen + 4;
  if ( RegQueryValueExW(hKey, L"RepairAdmin", 0, &Type, v3, &cbData) || Type != 1 )
    goto LABEL_19;
  if ( ConvertStringSidToSidW((LPCWSTR)v3, &Sid) )
  {
    if ( RtlValidSid(Sid) )
      v6 = SampRODCCacheSearch(v5, Sid, 0x220u, 1u);
    LocalFree(Sid);
    goto LABEL_19;
  }
  v19 = GetLastError();
  v20 = v19;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    WPP_SF_DS(
      WPP_GLOBAL_Control[3].Buffer,
      59,
      (unsigned int)WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids,
      v19,
      (__int64)v12);
  if ( v20 == 8 )
  {
    v6 = -1073741801;
    goto LABEL_65;
  }
LABEL_19:
  if ( v6 < 0 )
  {
LABEL_65:
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 60, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, (unsigned int)v6);
    }
  }
  if ( v3 )
    LocalFree(v3);
  if ( v2 )
    LocalFree(v2);
  if ( v6 >= 0 )
    goto LABEL_6;
  if ( v5 )
    LocalFree(v5);
LABEL_7:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 61, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, (unsigned int)v6, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039318  mov     [rsp-8+arg_0], rcx
0x18003931d  push    rbp
0x18003931e  push    rbx
0x18003931f  push    rsi
0x180039320  push    rdi
0x180039321  push    r12
0x180039323  push    r13
0x180039325  push    r14
0x180039327  push    r15
0x180039329  lea     rbp, [rsp-1Fh]
0x18003932e  sub     rsp, 98h
0x180039335  xor     r15d, r15d
0x180039338  mov     [rbp+57h+hKey], r15
0x18003933c  mov     r13d, r15d
0x18003933f  mov     [rbp+57h+cValues], r15d
0x180039343  mov     r14d, r15d
0x180039346  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18003934a  lea     edx, [r15+10h]; uBytes
0x18003934e  mov     [rbp+57h+cbMaxValueLen], r15d
0x180039352  lea     ebx, [rdx+30h]
0x180039355  mov     [rbp+57h+cchValueName], r15d
0x180039359  mov     ecx, ebx; uFlags
0x18003935b  mov     [rbp+57h+cbData], r15d
0x18003935f  mov     [rbp+57h+Type], r15d
0x180039363  mov     [rbp+57h+Sid], r15
0x180039367  call    cs:__imp_LocalAlloc
0x18003936d  mov     r12, rax
0x180039370  test    rax, rax
0x180039373  jnz     short loc_18003937F
0x180039375  mov     ebx, 0C0000017h
0x18003937a  jmp     loc_180039755
0x18003937f  xorps   xmm0, xmm0
0x180039382  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Lsa"...
0x180039389  movups  xmmword ptr [rax], xmm0
0x18003938c  lea     rax, [rbp+57h+hKey]
0x180039390  mov     r9d, 20019h; samDesired
0x180039396  xor     r8d, r8d; ulOptions
0x180039399  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18003939e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800393a5  call    cs:__imp_RegOpenKeyExW
0x1800393ab  test    eax, eax
0x1800393ad  jz      short loc_180039427
0x1800393af  cmp     eax, 2
0x1800393b2  jnz     short loc_180039414
0x1800393b4  mov     ebx, r15d
0x1800393b7  mov     rax, [rbp+57h+arg_0]
0x1800393bb  mov     [rax], r12
0x1800393be  mov     rcx, [rbp+57h+hKey]; hKey
0x1800393c2  lea     rax, [rcx-1]
0x1800393c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800393ca  ja      short loc_1800393D2
0x1800393cc  call    cs:__imp_RegCloseKey
0x1800393d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393d9  test    dword ptr [rcx+44h], 20000h
0x1800393e0  jz      short loc_1800393FE
0x1800393e2  mov     rcx, [rcx+38h]
0x1800393e6  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x1800393ed  mov     edx, 3Dh ; '='
0x1800393f2  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x1800393f6  mov     r9d, ebx
0x1800393f9  call    WPP_SF_Dd
0x1800393fe  mov     eax, ebx
0x180039400  add     rsp, 98h
0x180039407  pop     r15
0x180039409  pop     r14
0x18003940b  pop     r13
0x18003940d  pop     r12
0x18003940f  pop     rdi
0x180039410  pop     rsi
0x180039411  pop     rbx
0x180039412  pop     rbp
0x180039413  retn
0x180039414  mov     ebx, 0C0000001h
0x180039419  cmp     eax, 8
0x18003941c  lea     edi, [rbx+16h]
0x18003941f  cmovz   ebx, edi
0x180039422  jmp     loc_180039755
0x180039427  mov     rcx, [rbp+57h+hKey]; hKey
0x18003942b  lea     rax, [rbp+57h+cbMaxValueLen]
0x18003942f  mov     [rsp+0D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180039434  xor     r9d, r9d; lpReserved
0x180039437  mov     [rsp+0D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003943c  xor     r8d, r8d; lpcchClass
0x18003943f  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180039444  xor     edx, edx; lpClass
0x180039446  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18003944a  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003944f  lea     rax, [rbp+57h+cValues]
0x180039453  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x180039458  mov     [rsp+0D0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003945d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180039462  mov     [rsp+0D0h+phkResult], r15; lpcSubKeys
0x180039467  call    cs:__imp_RegQueryInfoKeyW
0x18003946d  test    eax, eax
0x18003946f  jz      short loc_18003948E
0x180039471  mov     edi, 0C0000017h
0x180039476  cmp     eax, 8
0x180039479  lea     ebx, [rdi-16h]
0x18003947c  cmovnz  edi, ebx
0x18003947f  mov     ebx, edi
0x180039481  test    ebx, ebx
0x180039483  jns     loc_180039780
0x180039489  jmp     loc_180039755
0x18003948e  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180039491  mov     eax, 0FFFFFFFFh
0x180039496  inc     ecx
0x180039498  add     rcx, rcx
0x18003949b  cmp     rcx, rax
0x18003949e  ja      loc_180039750
0x1800394a4  mov     edx, ecx; uBytes
0x1800394a6  mov     ecx, ebx; uFlags
0x1800394a8  call    cs:__imp_LocalAlloc
0x1800394ae  mov     [rbp+57h+var_50], rax
0x1800394b2  mov     r13, rax
0x1800394b5  test    rax, rax
0x1800394b8  jz      loc_180039375
0x1800394be  mov     edx, [rbp+57h+cbMaxValueLen]
0x1800394c1  mov     ecx, ebx; uFlags
0x1800394c3  add     rdx, 4; uBytes
0x1800394c7  call    cs:__imp_LocalAlloc
0x1800394cd  mov     r14, rax
0x1800394d0  test    rax, rax
0x1800394d3  jz      loc_180039375
0x1800394d9  xor     ecx, ecx
0x1800394db  mov     [rbp+57h+var_64], r15d
0x1800394df  mov     ebx, r15d
0x1800394e2  mov     rsi, r15
0x1800394e5  mov     edi, 0C0000017h
0x1800394ea  cmp     [rbp+57h+cValues], ecx
0x1800394ed  jbe     loc_180039683
0x1800394f3  test    ebx, ebx
0x1800394f5  js      loc_180039683
0x1800394fb  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800394fe  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180039502  inc     eax
0x180039504  mov     r8, r13; lpValueName
0x180039507  mov     [rbp+57h+cchValueName], eax
0x18003950a  mov     edx, r15d; dwIndex
0x18003950d  mov     eax, [rbp+57h+cbMaxValueLen]
0x180039510  add     eax, 4
0x180039513  mov     [rbp+57h+cbData], eax
0x180039516  lea     rax, [rbp+57h+cbData]
0x18003951a  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x18003951f  lea     rax, [rbp+57h+Type]
0x180039523  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x180039528  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x18003952d  mov     [rsp+0D0h+phkResult], rcx; lpReserved
0x180039532  mov     rcx, [rbp+57h+hKey]; hKey
0x180039536  call    cs:__imp_RegEnumValueW
0x18003953c  xor     ecx, ecx
0x18003953e  test    eax, eax
0x180039540  jnz     loc_180039672
0x180039546  cmp     [rbp+57h+Type], 7
0x18003954a  jnz     loc_180039672
0x180039550  mov     eax, [rbp+57h+cbData]
0x180039553  shr     rax, 1
0x180039556  cmp     [r14+rax*2-4], cx
0x18003955c  jnz     loc_180039672
0x180039562  cmp     [r14+rax*2-2], cx
0x180039568  jnz     loc_180039672
0x18003956e  mov     rcx, r13
0x180039571  call    cs:__imp__o__wtoi
0x180039577  mov     ecx, eax; unsigned int
0x180039579  mov     r13d, eax
0x18003957c  call    ?SampValidateBuiltinRidForDC@@YAHK@Z; SampValidateBuiltinRidForDC(ulong)
0x180039581  test    eax, eax
0x180039583  jnz     short loc_1800395C4
0x180039585  mov     rcx, cs:WPP_GLOBAL_Control
0x18003958c  test    byte ptr [rcx+44h], 20h
0x180039590  jz      loc_18003966C
0x180039596  cmp     byte ptr [rcx+41h], 2
0x18003959a  jb      loc_18003966C
0x1800395a0  mov     rcx, [rcx+38h]
0x1800395a4  lea     edx, [rax+39h]
0x1800395a7  mov     dword ptr [rsp+0D0h+phkResult], r13d
0x1800395ac  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x1800395b3  mov     r13, [rbp+57h+var_50]
0x1800395b7  mov     r9, r13
0x1800395ba  call    WPP_SF_Sd
0x1800395bf  jmp     loc_180039670
0x1800395c4  mov     rsi, r14
0x1800395c7  lea     rdx, [rbp+57h+Sid]; Sid
0x1800395cb  mov     rcx, rsi; StringSid
0x1800395ce  call    cs:__imp_ConvertStringSidToSidW
0x1800395d4  test    eax, eax
0x1800395d6  jz      short loc_18003960A
0x1800395d8  mov     rcx, [rbp+57h+Sid]; Sid
0x1800395dc  call    cs:__imp_RtlValidSid
0x1800395e2  test    al, al
0x1800395e4  jz      short loc_1800395FA
0x1800395e6  mov     rdx, [rbp+57h+Sid]; void *
0x1800395ea  mov     r9b, 1; unsigned __int8
0x1800395ed  mov     r8d, r13d; unsigned int
0x1800395f0  mov     rcx, r12; struct _SAMP_RODC_ROLES_CACHE *
0x1800395f3  call    ?SampRODCCacheSearch@@YAJPEAU_SAMP_RODC_ROLES_CACHE@@PEAXKE@Z; SampRODCCacheSearch(_SAMP_RODC_ROLES_CACHE *,void *,ulong,uchar)
0x1800395f8  mov     ebx, eax
0x1800395fa  mov     rcx, [rbp+57h+Sid]; hMem
0x1800395fe  call    cs:__imp_LocalFree
0x180039604  cmp     ebx, edi
0x180039606  jz      short loc_180039660
0x180039608  jmp     short loc_180039642
0x18003960a  call    cs:__imp_GetLastError
0x180039610  mov     r15d, eax
0x180039613  mov     rcx, cs:WPP_GLOBAL_Control
0x18003961a  test    byte ptr [rcx+44h], 20h
0x18003961e  jz      short loc_18003963C
0x180039620  cmp     byte ptr [rcx+41h], 2
0x180039624  jb      short loc_18003963C
0x180039626  mov     rcx, [rcx+38h]
0x18003962a  mov     r9d, eax
0x18003962d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rsi
0x180039632  mov     dword ptr [rsp+0D0h+phkResult], r13d
0x180039637  call    WPP_SF_DdS
0x18003963c  cmp     r15d, 8
0x180039640  jz      short loc_18003965E
0x180039642  xor     ecx, ecx
0x180039644  jmp     short loc_18003964A
0x180039646  add     rsi, 2
0x18003964a  cmp     [rsi], cx
0x18003964d  jnz     short loc_180039646
0x18003964f  add     rsi, 2
0x180039653  cmp     [rsi], cx
0x180039656  jnz     loc_1800395C7
0x18003965c  jmp     short loc_180039662
0x18003965e  mov     ebx, edi
0x180039660  xor     ecx, ecx
0x180039662  mov     r13, [rbp+57h+var_50]
0x180039666  mov     r15d, [rbp+57h+var_64]
0x18003966a  jmp     short loc_180039672
0x18003966c  mov     r13, [rbp+57h+var_50]
0x180039670  xor     ecx, ecx
0x180039672  inc     r15d
0x180039675  mov     [rbp+57h+var_64], r15d
0x180039679  cmp     r15d, [rbp+57h+cValues]
0x18003967d  jb      loc_1800394F3
0x180039683  mov     eax, [rbp+57h+cbMaxValueLen]
0x180039686  lea     r9, [rbp+57h+Type]; lpType
0x18003968a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003968e  lea     rdx, aRepairadmin; "RepairAdmin"
0x180039695  add     eax, 4
0x180039698  xor     r8d, r8d; lpReserved
0x18003969b  mov     [rbp+57h+cbData], eax
0x18003969e  lea     rax, [rbp+57h+cbData]
0x1800396a2  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800396a7  mov     [rsp+0D0h+phkResult], r14; lpData
0x1800396ac  call    cs:__imp_RegQueryValueExW
0x1800396b2  test    eax, eax
0x1800396b4  jnz     loc_180039481
0x1800396ba  cmp     [rbp+57h+Type], 1
0x1800396be  jnz     loc_180039481
0x1800396c4  lea     rdx, [rbp+57h+Sid]; Sid
0x1800396c8  mov     rcx, r14; StringSid
0x1800396cb  call    cs:__imp_ConvertStringSidToSidW
0x1800396d1  test    eax, eax
0x1800396d3  jz      short loc_180039709
0x1800396d5  mov     rcx, [rbp+57h+Sid]; Sid
0x1800396d9  call    cs:__imp_RtlValidSid
0x1800396df  test    al, al
0x1800396e1  jz      short loc_1800396FA
0x1800396e3  mov     rdx, [rbp+57h+Sid]; void *
0x1800396e7  mov     r9b, 1; unsigned __int8
0x1800396ea  mov     r8d, 220h; unsigned int
0x1800396f0  mov     rcx, r12; struct _SAMP_RODC_ROLES_CACHE *
0x1800396f3  call    ?SampRODCCacheSearch@@YAJPEAU_SAMP_RODC_ROLES_CACHE@@PEAXKE@Z; SampRODCCacheSearch(_SAMP_RODC_ROLES_CACHE *,void *,ulong,uchar)
0x1800396f8  mov     ebx, eax
0x1800396fa  mov     rcx, [rbp+57h+Sid]; hMem
0x1800396fe  call    cs:__imp_LocalFree
0x180039704  jmp     loc_180039481
0x180039709  call    cs:__imp_GetLastError
0x18003970f  mov     r15d, eax
0x180039712  mov     rcx, cs:WPP_GLOBAL_Control
0x180039719  test    byte ptr [rcx+44h], 20h
0x18003971d  jz      short loc_180039742
0x18003971f  cmp     byte ptr [rcx+41h], 2
0x180039723  jb      short loc_180039742
0x180039725  mov     rcx, [rcx+38h]
0x180039729  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180039730  mov     edx, 3Bh ; ';'
0x180039735  mov     [rsp+0D0h+phkResult], rsi
0x18003973a  mov     r9d, eax
0x18003973d  call    WPP_SF_DS
0x180039742  cmp     r15d, 8
0x180039746  jnz     loc_180039481
0x18003974c  mov     ebx, edi
0x18003974e  jmp     short loc_180039755
0x180039750  mov     ebx, 0C0000095h
0x180039755  mov     rcx, cs:WPP_GLOBAL_Control
0x18003975c  test    byte ptr [rcx+44h], 20h
0x180039760  jz      short loc_180039780
0x180039762  cmp     byte ptr [rcx+41h], 2
0x180039766  jb      short loc_180039780
0x180039768  mov     rcx, [rcx+38h]
0x18003976c  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180039773  mov     edx, 3Ch ; '<'
0x180039778  mov     r9d, ebx
0x18003977b  call    WPP_SF_d
0x180039780  test    r14, r14
0x180039783  jz      short loc_18003978E
0x180039785  mov     rcx, r14; hMem
0x180039788  call    cs:__imp_LocalFree
  ... truncated ...
```
