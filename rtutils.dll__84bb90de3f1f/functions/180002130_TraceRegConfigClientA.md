# TraceRegConfigClientA

- ea: `0x180002130`
- end: `0x180002677`
- name: `TraceRegConfigClientA`
- size: `1351`
- prototype: `LSTATUS __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001100`
- `0x180001c20`
- `0x180001fa0`

## callees

- `0x180002130`
- `0x180002680`
- `0x180003774`
- `0x180003bb0`
- `0x180003bf0`
- `0x180007a68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180002564`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180002564`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002660`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002660`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180002536`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180002536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000264b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000264b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002594`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800021c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002222`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000227a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800022db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002333`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000238c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800021c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002222`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000227a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800022db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002333`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000238c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800024e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800024e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18000254b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18000254b`

## string_xrefs

- `0x180002360`: `FileDirectory`

## pseudocode

```c
LSTATUS __fastcall TraceRegConfigClientA(__int64 a1, int a2)
{
  __int64 v3; // rbx
  HKEY v4; // rcx
  int v5; // edx
  int v6; // ecx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // eax
  HKEY v10; // rcx
  int v11; // edx
  int v12; // eax
  unsigned int v13; // ecx
  int v14; // eax
  int v15; // eax
  HKEY v16; // rcx
  int v17; // eax
  HKEY v18; // rcx
  const CHAR *v19; // rcx
  size_t v20; // rdx
  BYTE *v21; // r8
  bool v22; // zf
  BYTE *v23; // rax
  LSTATUS result; // eax
  __int64 v25; // rcx
  const CHAR *v26; // rdx
  __int64 v27; // r9
  CHAR *v28; // r8
  CHAR *v29; // rax
  size_t v30; // rdx
  CHAR *i; // rax
  size_t *v32; // r8
  size_t v33; // rdx
  CHAR *j; // rax
  int v35; // eax
  int v36; // eax
  HANDLE EventA; // rax
  int v38; // esi
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[260]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v47[12]; // [rsp+154h] [rbp+54h] BYREF
  BYTE v48[272]; // [rsp+160h] [rbp+60h] BYREF

  hKey = 0;
  v3 = 2147483646;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  pcchLength = 0;
  if ( !a2 )
  {
    v4 = *(HKEY *)(a1 + 1072);
    hKey = v4;
    goto LABEL_3;
  }
  v25 = 2147483646;
  v26 = "Software\\Microsoft\\Tracing";
  v27 = 260;
  v28 = SubKey;
  do
  {
    if ( !v25 )
      break;
    if ( !*v26 )
      break;
    *v28++ = *v26++;
    --v25;
    --v27;
  }
  while ( v27 );
  v22 = v27 == 0;
  v29 = v28 - 1;
  if ( v27 )
    v29 = v28;
  *v29 = 0;
  if ( !v27 )
    goto LABEL_30;
  v30 = 260;
  for ( i = SubKey; *i; ++i )
  {
    if ( !--v30 )
    {
      LOWORD(result) = 87;
      return (unsigned __int16)result;
    }
  }
  result = StringCopyWorkerA((STRSAFE_LPSTR)&v47[-v30], v30, (size_t *)v28, "\\", (size_t)lpData);
  if ( result < 0 )
    return (unsigned __int16)result;
  v33 = 260;
  for ( j = SubKey; *j; ++j )
  {
    if ( !--v33 )
    {
      LOWORD(result) = 87;
      return (unsigned __int16)result;
    }
  }
  result = StringCopyWorkerA((STRSAFE_LPSTR)&v47[-v33], v33, v32, (STRSAFE_PCNZCH)(a1 + 64), (size_t)lpDataa);
  if ( result < 0 )
    return (unsigned __int16)result;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey)
    || (v38 = TraceRegCreateDefaultsA(SubKey, &hKey)) == 0 )
  {
    v4 = hKey;
    *(_QWORD *)(a1 + 1072) = hKey;
LABEL_3:
    cbData = 4;
    if ( RegQueryValueExA(v4, "EnableFileTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v5 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v5 = *(_DWORD *)Data;
    }
    v6 = *(_DWORD *)(a1 + 56);
    cbData = 4;
    v7 = v6 | 2;
    v8 = v6 & 0xFFFFFFFD;
    if ( v5 == 1 )
      v8 = v7;
    *(_DWORD *)(a1 + 56) = v8;
    if ( RegQueryValueExA(hKey, "FileTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v9 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v9 = *(_DWORD *)Data;
    }
    v10 = hKey;
    cbData = 4;
    *(_DWORD *)(a1 + 272) = v9 & 0xFFFF0000;
    if ( RegQueryValueExA(v10, "EnableConsoleTracing", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v11 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v11 = *(_DWORD *)Data;
    }
    v12 = *(_DWORD *)(a1 + 56);
    v13 = v12 & 0xFFFFFFFB;
    v14 = v12 | 4;
    if ( v11 == 1 )
      v13 = v14;
    *(_DWORD *)(a1 + 56) = v13;
    cbData = 4;
    if ( RegQueryValueExA(hKey, "ConsoleTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v15 = -65536;
      *(_DWORD *)Data = -65536;
    }
    else
    {
      v15 = *(_DWORD *)Data;
    }
    v16 = hKey;
    cbData = 4;
    *(_DWORD *)(a1 + 276) = v15 & 0xFFFF0000;
    if ( RegQueryValueExA(v16, "MaxFileSize", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v17 = 0x100000;
      *(_DWORD *)Data = 0x100000;
    }
    else
    {
      v17 = *(_DWORD *)Data;
    }
    v18 = hKey;
    *(_DWORD *)(a1 + 280) = v17;
    cbData = 260;
    v48[260] = 0;
    if ( !RegQueryValueExA(v18, "FileDirectory", 0, &Type, v48, &cbData) && Type - 1 <= 1 )
    {
      if ( cbData >= 0x105uLL )
        _report_rangecheckfailure();
      v48[cbData] = 0;
      goto LABEL_56;
    }
    v19 = "%windir%\\tracing";
    v20 = 260;
    v21 = v48;
    do
    {
      if ( !v3 )
        break;
      if ( !*v19 )
        break;
      *v21++ = *v19++;
      --v3;
      --v20;
    }
    while ( v20 );
    v22 = v20 == 0;
    v23 = v21 - 1;
    if ( v20 )
      v23 = v21;
    *v23 = 0;
    if ( v20 )
    {
      if ( StringLengthWorkerA((STRSAFE_PCNZCH)v48, v20, &pcchLength) < 0 )
        v35 = 0;
      else
        v35 = pcchLength;
      cbData = v35 + 1;
LABEL_56:
      if ( ExpandEnvironmentStringsA((LPCSTR)v48, (LPSTR)(a1 + 284), 0x104u)
        && ((v36 = lstrlenA((LPCSTR)(a1 + 284)),
             _o_mbstowcs(a1 + 546, a1 + 284, v36 + 1),
             (EventA = *(HANDLE *)(a1 + 1080)) != 0)
         || (EventA = CreateEventA(0, 0, 0, 0), (*(_QWORD *)(a1 + 1080) = EventA) != 0)) )
      {
        return RegNotifyChangeKeyValue(*(HKEY *)(a1 + 1072), 0, 0xEu, EventA, 1);
      }
      else
      {
        return GetLastError();
      }
    }
LABEL_30:
    result = 122;
    if ( !v22 )
      return 0;
    return result;
  }
  if ( hKey )
    RegCloseKey(hKey);
  *(_QWORD *)(a1 + 1072) = 0;
  return v38;
}

```

## disassembly

```asm
0x180002130  mov     [rsp-8+arg_8], rbx
0x180002135  mov     [rsp-8+arg_10], rsi
0x18000213a  push    rbp
0x18000213b  push    rdi
0x18000213c  push    r14
0x18000213e  lea     rbp, [rsp-180h]
0x180002146  sub     rsp, 280h
0x18000214d  mov     rax, cs:__security_cookie
0x180002154  xor     rax, rsp
0x180002157  mov     [rbp+190h+var_20], rax
0x18000215e  xor     r14d, r14d
0x180002161  mov     rdi, rcx
0x180002164  mov     [rsp+290h+hKey], r14
0x180002169  mov     ebx, 7FFFFFFEh
0x18000216e  mov     [rsp+290h+Type], r14d
0x180002173  mov     dword ptr [rsp+290h+Data], r14d
0x180002178  mov     [rsp+290h+cbData], r14d
0x18000217d  mov     [rsp+290h+pcchLength], r14
0x180002182  test    edx, edx
0x180002184  jnz     loc_18000240C
0x18000218a  mov     rcx, [rcx+430h]; hKey
0x180002191  mov     [rsp+290h+hKey], rcx
0x180002196  lea     rax, [rsp+290h+cbData]
0x18000219b  mov     [rsp+290h+cbData], 4
0x1800021a3  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800021a8  lea     r9, [rsp+290h+Type]; lpType
0x1800021ad  lea     rax, [rsp+290h+Data]
0x1800021b2  xor     r8d, r8d; lpReserved
0x1800021b5  lea     rdx, ValueName; "EnableFileTracing"
0x1800021bc  mov     [rsp+290h+lpData], rax; lpData
0x1800021c1  call    cs:__imp_RegQueryValueExA
0x1800021c7  test    eax, eax
0x1800021c9  jnz     loc_1800025D6
0x1800021cf  cmp     [rsp+290h+Type], 4
0x1800021d4  jnz     loc_1800025D6
0x1800021da  mov     edx, dword ptr [rsp+290h+Data]
0x1800021de  mov     ecx, [rdi+38h]
0x1800021e1  lea     r9, [rsp+290h+Type]; lpType
0x1800021e6  mov     eax, ecx
0x1800021e8  mov     [rsp+290h+cbData], 4
0x1800021f0  or      eax, 2
0x1800021f3  and     ecx, 0FFFFFFFDh
0x1800021f6  cmp     edx, 1
0x1800021f9  lea     rdx, aFiletracingmas_0; "FileTracingMask"
0x180002200  cmovz   ecx, eax
0x180002203  lea     rax, [rsp+290h+cbData]
0x180002208  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000220d  xor     r8d, r8d; lpReserved
0x180002210  lea     rax, [rsp+290h+Data]
0x180002215  mov     [rdi+38h], ecx
0x180002218  mov     rcx, [rsp+290h+hKey]; hKey
0x18000221d  mov     [rsp+290h+lpData], rax; lpData
0x180002222  call    cs:__imp_RegQueryValueExA
0x180002228  test    eax, eax
0x18000222a  jnz     loc_1800025E2
0x180002230  cmp     [rsp+290h+Type], 4
0x180002235  jnz     loc_1800025E2
0x18000223b  mov     eax, dword ptr [rsp+290h+Data]
0x18000223f  mov     rcx, [rsp+290h+hKey]; hKey
0x180002244  lea     r9, [rsp+290h+Type]; lpType
0x180002249  and     eax, 0FFFF0000h
0x18000224e  mov     [rsp+290h+cbData], 4
0x180002256  mov     [rdi+110h], eax
0x18000225c  lea     rdx, aEnableconsolet_0; "EnableConsoleTracing"
0x180002263  lea     rax, [rsp+290h+cbData]
0x180002268  xor     r8d, r8d; lpReserved
0x18000226b  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180002270  lea     rax, [rsp+290h+Data]
0x180002275  mov     [rsp+290h+lpData], rax; lpData
0x18000227a  call    cs:__imp_RegQueryValueExA
0x180002280  test    eax, eax
0x180002282  jnz     loc_1800025F0
0x180002288  cmp     [rsp+290h+Type], 4
0x18000228d  jnz     loc_1800025F0
0x180002293  mov     edx, dword ptr [rsp+290h+Data]
0x180002297  mov     ecx, [rdi+38h]
0x18000229a  lea     r9, [rsp+290h+Type]; lpType
0x18000229f  mov     eax, ecx
0x1800022a1  and     ecx, 0FFFFFFFBh
0x1800022a4  or      eax, 4
0x1800022a7  cmp     edx, 1
0x1800022aa  lea     rdx, aConsoletracing; "ConsoleTracingMask"
0x1800022b1  cmovz   ecx, eax
0x1800022b4  lea     rax, [rsp+290h+cbData]
0x1800022b9  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800022be  xor     r8d, r8d; lpReserved
0x1800022c1  mov     [rdi+38h], ecx
0x1800022c4  lea     rax, [rsp+290h+Data]
0x1800022c9  mov     rcx, [rsp+290h+hKey]; hKey
0x1800022ce  mov     [rsp+290h+lpData], rax; lpData
0x1800022d3  mov     [rsp+290h+cbData], 4
0x1800022db  call    cs:__imp_RegQueryValueExA
0x1800022e1  test    eax, eax
0x1800022e3  jnz     loc_1800025FC
0x1800022e9  cmp     [rsp+290h+Type], 4
0x1800022ee  jnz     loc_1800025FC
0x1800022f4  mov     eax, dword ptr [rsp+290h+Data]
0x1800022f8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800022fd  lea     r9, [rsp+290h+Type]; lpType
0x180002302  and     eax, 0FFFF0000h
0x180002307  mov     [rsp+290h+cbData], 4
0x18000230f  mov     [rdi+114h], eax
0x180002315  lea     rdx, aMaxfilesize; "MaxFileSize"
0x18000231c  lea     rax, [rsp+290h+cbData]
0x180002321  xor     r8d, r8d; lpReserved
0x180002324  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180002329  lea     rax, [rsp+290h+Data]
0x18000232e  mov     [rsp+290h+lpData], rax; lpData
0x180002333  call    cs:__imp_RegQueryValueExA
0x180002339  test    eax, eax
0x18000233b  jnz     loc_18000260A
0x180002341  cmp     [rsp+290h+Type], 4
0x180002346  jnz     loc_18000260A
0x18000234c  mov     eax, dword ptr [rsp+290h+Data]
0x180002350  mov     rcx, [rsp+290h+hKey]; hKey
0x180002355  lea     r9, [rsp+290h+Type]; lpType
0x18000235a  mov     [rdi+118h], eax
0x180002360  lea     rdx, aFiledirectory_0; "FileDirectory"
0x180002367  lea     rax, [rsp+290h+cbData]
0x18000236c  mov     [rsp+290h+cbData], 104h
0x180002374  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180002379  xor     r8d, r8d; lpReserved
0x18000237c  lea     rax, [rbp+190h+var_130]
0x180002380  mov     [rbp+190h+var_2C], r14b
0x180002387  mov     [rsp+290h+lpData], rax; lpData
0x18000238c  call    cs:__imp_RegQueryValueExA
0x180002392  test    eax, eax
0x180002394  jz      loc_180002618
0x18000239a  lea     rcx, Src; "%windir%\\tracing"
0x1800023a1  mov     edx, 104h
0x1800023a6  lea     r8, [rbp+190h+var_130]
0x1800023aa  test    rbx, rbx
0x1800023ad  jz      short loc_1800023C8
0x1800023af  movzx   eax, byte ptr [rcx]
0x1800023b2  test    al, al
0x1800023b4  jz      short loc_1800023C8
0x1800023b6  mov     [r8], al
0x1800023b9  inc     rcx
0x1800023bc  inc     r8
0x1800023bf  dec     rbx
0x1800023c2  sub     rdx, 1; cchMax
0x1800023c6  jnz     short loc_1800023AA
0x1800023c8  test    rdx, rdx
0x1800023cb  lea     rax, [r8-1]
0x1800023cf  cmovnz  rax, r8
0x1800023d3  mov     [rax], r14b
0x1800023d6  jnz     loc_180002503
0x1800023dc  mov     eax, 7Ah ; 'z'
0x1800023e1  cmovnz  eax, r14d
0x1800023e5  mov     rcx, [rbp+190h+var_20]
0x1800023ec  xor     rcx, rsp; StackCookie
0x1800023ef  call    __security_check_cookie
0x1800023f4  lea     r11, [rsp+290h+var_10]
0x1800023fc  mov     rbx, [r11+28h]
0x180002400  mov     rsi, [r11+30h]
0x180002404  mov     rsp, r11
0x180002407  pop     r14
0x180002409  pop     rdi
0x18000240a  pop     rbp
0x18000240b  retn
0x18000240c  mov     rcx, rbx
0x18000240f  lea     rdx, SubKey; "Software\\Microsoft\\Tracing"
0x180002416  mov     r9d, 104h
0x18000241c  lea     r8, [rsp+290h+SubKey]
0x180002421  test    rcx, rcx
0x180002424  jz      short loc_18000243F
0x180002426  movzx   eax, byte ptr [rdx]
0x180002429  test    al, al
0x18000242b  jz      short loc_18000243F
0x18000242d  mov     [r8], al
0x180002430  inc     rdx
0x180002433  inc     r8; pcchNewDestLength
0x180002436  dec     rcx
0x180002439  sub     r9, 1
0x18000243d  jnz     short loc_180002421
0x18000243f  test    r9, r9
0x180002442  lea     rax, [r8-1]
0x180002446  cmovnz  rax, r8
0x18000244a  mov     [rax], r14b
0x18000244d  jz      short loc_1800023DC
0x18000244f  mov     edx, 104h; cchDest
0x180002454  lea     rax, [rsp+290h+SubKey]
0x180002459  nop     dword ptr [rax+00000000h]
0x180002460  cmp     [rax], r14b
0x180002463  jz      short loc_180002475
0x180002465  inc     rax
0x180002468  sub     rdx, 1
0x18000246c  jnz     short loc_180002460
0x18000246e  mov     eax, 80070057h
0x180002473  jmp     short loc_1800024A9
0x180002475  lea     rcx, [rbp+190h+var_13C]
0x180002479  sub     rcx, rdx; pszDest
0x18000247c  lea     r9, pszSrc; "\\"
0x180002483  call    StringCopyWorkerA
0x180002488  test    eax, eax
0x18000248a  js      short loc_1800024A9
0x18000248c  mov     edx, 104h; cchDest
0x180002491  lea     rax, [rsp+290h+SubKey]
0x180002496  cmp     [rax], r14b
0x180002499  jz      short loc_1800024B1
0x18000249b  inc     rax
0x18000249e  sub     rdx, 1
0x1800024a2  jnz     short loc_180002496
0x1800024a4  mov     eax, 80070057h
0x1800024a9  movzx   eax, ax
0x1800024ac  jmp     loc_1800023E5
0x1800024b1  lea     rcx, [rbp+190h+var_13C]
0x1800024b5  sub     rcx, rdx; pszDest
0x1800024b8  lea     r9, [rdi+40h]; pszSrc
0x1800024bc  call    StringCopyWorkerA
0x1800024c1  test    eax, eax
0x1800024c3  js      short loc_1800024A9
0x1800024c5  lea     rax, [rsp+290h+hKey]
0x1800024ca  mov     r9d, 20019h; samDesired
0x1800024d0  xor     r8d, r8d; ulOptions
0x1800024d3  mov     [rsp+290h+lpData], rax; phkResult
0x1800024d8  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800024dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800024e4  call    cs:__imp_RegOpenKeyExA
0x1800024ea  test    eax, eax
0x1800024ec  jnz     loc_18000259F
0x1800024f2  mov     rcx, [rsp+290h+hKey]
0x1800024f7  mov     [rdi+430h], rcx
0x1800024fe  jmp     loc_180002196
0x180002503  lea     r8, [rsp+290h+pcchLength]; pcchLength
0x180002508  lea     rcx, [rbp+190h+var_130]; psz
0x18000250c  call    StringLengthWorkerA
0x180002511  test    eax, eax
0x180002513  js      loc_180002643
0x180002519  mov     rax, [rsp+290h+pcchLength]
0x18000251e  inc     rax
0x180002521  mov     [rsp+290h+cbData], eax
0x180002525  mov     r8d, 104h; nSize
0x18000252b  lea     rdx, [rdi+11Ch]; lpDst
0x180002532  lea     rcx, [rbp+190h+var_130]; lpSrc
0x180002536  call    cs:__imp_ExpandEnvironmentStringsA
0x18000253c  test    eax, eax
0x18000253e  jz      loc_18000264B
0x180002544  lea     rcx, [rdi+11Ch]; lpString
0x18000254b  call    cs:__imp_lstrlenA
0x180002551  inc     eax
0x180002553  lea     rcx, [rdi+222h]
0x18000255a  movsxd  r8, eax
0x18000255d  lea     rdx, [rdi+11Ch]
0x180002564  call    cs:__imp__o_mbstowcs
0x18000256a  mov     rax, [rdi+438h]
0x180002571  test    rax, rax
0x180002574  jz      loc_180002656
0x18000257a  mov     rcx, [rdi+430h]; hKey
0x180002581  mov     r9, rax; hEvent
0x180002584  xor     edx, edx; bWatchSubtree
0x180002586  mov     dword ptr [rsp+290h+lpData], 1; fAsynchronous
0x18000258e  mov     r8d, 0Eh; dwNotifyFilter
0x180002594  call    cs:__imp_RegNotifyChangeKeyValue
0x18000259a  jmp     loc_1800023E5
0x18000259f  lea     rdx, [rsp+290h+hKey]; phkResult
0x1800025a4  lea     rcx, [rsp+290h+SubKey]; lpSubKey
0x1800025a9  call    TraceRegCreateDefaultsA
0x1800025ae  mov     esi, eax
0x1800025b0  test    eax, eax
0x1800025b2  jz      loc_1800024F2
0x1800025b8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800025bd  test    rcx, rcx
0x1800025c0  jz      short loc_1800025C8
0x1800025c2  call    cs:__imp_RegCloseKey
0x1800025c8  mov     [rdi+430h], r14
0x1800025cf  mov     eax, esi
0x1800025d1  jmp     loc_1800023E5
0x1800025d6  mov     edx, r14d
0x1800025d9  mov     dword ptr [rsp+290h+Data], edx
0x1800025dd  jmp     loc_1800021DE
0x1800025e2  mov     eax, 0FFFF0000h
0x1800025e7  mov     dword ptr [rsp+290h+Data], eax
0x1800025eb  jmp     loc_18000223F
0x1800025f0  mov     edx, r14d
0x1800025f3  mov     dword ptr [rsp+290h+Data], edx
0x1800025f7  jmp     loc_180002297
0x1800025fc  mov     eax, 0FFFF0000h
0x180002601  mov     dword ptr [rsp+290h+Data], eax
0x180002605  jmp     loc_1800022F8
0x18000260a  mov     eax, 100000h
0x18000260f  mov     dword ptr [rsp+290h+Data], eax
0x180002613  jmp     loc_180002350
0x180002618  mov     eax, [rsp+290h+Type]
0x18000261c  dec     eax
0x18000261e  cmp     eax, 1
0x180002621  ja      loc_18000239A
0x180002627  mov     eax, [rsp+290h+cbData]
0x18000262b  cmp     rax, 105h
0x180002631  jnb     short loc_18000263D
0x180002633  mov     [rbp+rax+190h+var_130], r14b
0x180002638  jmp     loc_180002525
0x18000263d  call    __report_rangecheckfailure
0x180002643  mov     rax, r14
0x180002646  jmp     loc_18000251E
0x18000264b  call    cs:__imp_GetLastError
0x180002651  jmp     loc_1800023E5
0x180002656  xor     r9d, r9d; lpName
0x180002659  xor     r8d, r8d; bInitialState
0x18000265c  xor     edx, edx; bManualReset
  ... truncated ...
```
