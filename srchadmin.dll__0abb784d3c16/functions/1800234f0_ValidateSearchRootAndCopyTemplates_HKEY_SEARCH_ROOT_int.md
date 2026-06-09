# ValidateSearchRootAndCopyTemplates(HKEY__ *,SEARCH_ROOT *,int)

- ea: `0x1800234f0`
- end: `0x180023842`
- name: `?ValidateSearchRootAndCopyTemplates@@YAJPEAUHKEY__@@PEAUSEARCH_ROOT@@H@Z`
- size: `850`
- prototype: `__int64 __fastcall(HKEY hKey, struct SEARCH_ROOT *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022b78`

## callees

- `0x180003840`
- `0x180005cc0`
- `0x18000687c`
- `0x1800094f0`
- `0x1800095c0`
- `0x18000d4dc`
- `0x1800227dc`
- `0x180022f50`
- `0x180022f90`
- `0x1800234f0`
- `0x18002f56c`

## import_xrefs

- `SHLWAPI!UrlGetPartW` at `0x18002356b`
- `SHLWAPI!UrlGetPartW` at `0x18002356b`
- `SHLWAPI!SHCopyKeyW` at `0x180023784`
- `SHLWAPI!SHCopyKeyW` at `0x180023784`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180023619`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180023619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002362d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002362d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800237f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800237f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023807`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002374f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002374f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800235f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800235db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800235db`

## string_xrefs

- `0x1800236df`: `DoNotCreateSearchConnectors`
- `0x1800237d3`: `DoNotCreateSearchConnectors`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateSearchRootAndCopyTemplates(HKEY hKey, struct SEARCH_ROOT *a2, unsigned int a3)
{
  unsigned int v4; // r14d
  const WCHAR *v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  int PartW; // ebx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rsi
  int Error; // r14d
  void *v15; // r15
  __int64 v16; // r8
  unsigned int v17; // r8d
  LSTATUS v18; // eax
  HKEY hkeyDest; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchOut; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE hMem[20]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszOut; // [rsp+80h] [rbp-80h] BYREF
  __int128 v25; // [rsp+82h] [rbp-7Eh]
  __int128 v26; // [rsp+92h] [rbp-6Eh]
  _BYTE v27[30]; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int16 v28[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h]
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h]
  __int128 v32; // [rsp+100h] [rbp+0h]
  _BYTE v33[28]; // [rsp+110h] [rbp+10h]
  _BYTE v34[420]; // [rsp+12Ch] [rbp+2Ch] BYREF

  LODWORD(hkeyDest) = a3;
  pcchOut = 32;
  pszOut = 0;
  v4 = a3;
  memset(v27, 0, sizeof(v27));
  v6 = (const WCHAR *)*((_QWORD *)a2 + 1);
  v7 = 1;
  v25 = 0;
  v26 = 0;
  PartW = UrlGetPartW(v6, &pszOut, &pcchOut, 1u, 0);
  if ( PartW >= 0 )
  {
    v12 = pcchOut;
    v13 = *((_QWORD *)a2 + 1);
    if ( *(_WORD *)(v13 + 2LL * pcchOut) == 58
      && *(_WORD *)(v13 + 2LL * pcchOut + 2) == 47
      && *(_WORD *)(v13 + 2LL * pcchOut + 4) == 47
      && *(_WORD *)(v13 + 2LL * pcchOut + 6) == 123 )
    {
      StringSid = 0;
      *(_QWORD *)hMem = 0;
      Error = SHQueryToken<_TOKEN_USER>(v9, v8, v11, hMem);
      if ( Error >= 0 )
      {
        v15 = *(void **)hMem;
        if ( !ConvertSidToStringSidW(**(PSID **)hMem, &StringSid) )
          Error = ResultFromKnownLastError();
        LocalFree(v15);
        if ( Error >= 0 )
        {
          v16 = -1;
          do
            ++v16;
          while ( StringSid[v16] );
          v7 = StrCmpNICW((LPCWSTR)(v13 + 2 * (v12 + 4)), StringSid, v16) == 0;
          CoTaskMemFree(StringSid);
        }
      }
      v4 = (unsigned int)hkeyDest;
    }
    *(_OWORD *)v28 = *(_OWORD *)L"SOFTWARE\\Microsoft\\Windows Search\\PHSearchConnectors\\";
    v30 = *(_OWORD *)L"ft\\Windows Search\\PHSearchConnectors\\";
    v29 = *(_OWORD *)L"\\Microsoft\\Windows Search\\PHSearchConnectors\\";
    v32 = *(_OWORD *)L"h\\PHSearchConnectors\\";
    v31 = *(_OWORD *)L"ws Search\\PHSearchConnectors\\";
    *(_OWORD *)v33 = *(_OWORD *)L"chConnectors\\";
    *(_OWORD *)&v33[12] = *(_OWORD *)L"ectors\\";
    memset_0(v34, 0, 0x19Cu);
    PartW = StringCchCatW(v28, 0x104u, &pszOut);
    if ( PartW >= 0 )
    {
      StringSid = 0;
      PartW = RegOpenKeyOpt(HKEY_LOCAL_MACHINE, v28, v17, (HKEY *)&StringSid);
      if ( PartW >= 0 )
      {
        if ( v7 )
          v7 = IsFlagNotSet((HKEY)StringSid, L"DoNotCreateSearchConnectors");
        *(_WORD *)hMem = 0;
        *(_QWORD *)&hMem[2] = 0;
        PartW = StringCchPrintfW((unsigned __int16 *)hMem, 5u, L"%04d", v4);
        if ( PartW >= 0 )
        {
          hkeyDest = 0;
          v18 = RegCreateKeyExW(hKey, (LPCWSTR)hMem, 0, 0, 0, 0x20006u, 0, &hkeyDest, 0);
          PartW = v18;
          if ( v18 > 0 )
            PartW = (unsigned __int16)v18 | 0x80070000;
          if ( PartW >= 0 )
          {
            if ( v7 && StringSid )
              v7 = SHCopyKeyW((HKEY)StringSid, 0, hkeyDest, 0) == 0;
            PartW = RegSetStringValue(hkeyDest, 0, *((const unsigned __int16 **)a2 + 1));
            if ( PartW >= 0 )
            {
              PartW = RegSetDWORDValue(hkeyDest, L"Version", *(_DWORD *)a2);
              if ( PartW >= 0 && !v7 )
                PartW = RegSetDWORDValue(hkeyDest, L"DoNotCreateSearchConnectors", 1u);
            }
            RegCloseKey(hkeyDest);
          }
        }
        if ( StringSid )
          RegCloseKey((HKEY)StringSid);
        if ( PartW >= 0 && !v7 )
          return 1;
      }
    }
  }
  return (unsigned int)PartW;
}

```

## disassembly

```asm
0x1800234f0  mov     [rsp-8+arg_18], rbx
0x1800234f5  push    rbp
0x1800234f6  push    rsi
0x1800234f7  push    rdi
0x1800234f8  push    r12
0x1800234fa  push    r13
0x1800234fc  push    r14
0x1800234fe  push    r15
0x180023500  lea     rbp, [rsp-1E0h]
0x180023508  sub     rsp, 2E0h
0x18002350f  mov     rax, cs:__security_cookie
0x180023516  xor     rax, rsp
0x180023519  mov     [rbp+210h+var_40], rax
0x180023520  xorps   xmm0, xmm0
0x180023523  mov     dword ptr [rsp+310h+hkeyDest], r8d
0x180023528  xor     r15d, r15d
0x18002352b  mov     [rsp+310h+pcchOut], 20h ; ' '
0x180023533  mov     r12, rdx
0x180023536  mov     [rbp+210h+pszOut], r15w
0x18002353b  mov     r14d, r8d
0x18002353e  mov     [rsp+310h+dwFlags], r15d; dwFlags
0x180023543  mov     r13, rcx
0x180023546  lea     r8, [rsp+310h+pcchOut]; pcchOut
0x18002354b  movups  xmmword ptr [rbp+210h+var_26E], xmm0
0x18002354f  mov     rcx, [r12+8]; pszIn
0x180023554  lea     edi, [r15+1]
0x180023558  mov     r9d, edi; dwPart
0x18002355b  lea     rdx, [rbp+210h+pszOut]; pszOut
0x18002355f  movups  [rbp+210h+var_28E], xmm0
0x180023563  movups  [rbp+210h+var_27E], xmm0
0x180023567  movups  xmmword ptr [rbp+210h+var_26E+0Eh], xmm0
0x18002356b  call    cs:__imp_UrlGetPartW
0x180023571  mov     ebx, eax
0x180023573  test    eax, eax
0x180023575  js      loc_180023816
0x18002357b  mov     ebx, [rsp+310h+pcchOut]
0x18002357f  mov     rsi, [r12+8]
0x180023584  cmp     word ptr [rsi+rbx*2], 3Ah ; ':'
0x180023589  jnz     loc_180023638
0x18002358f  cmp     word ptr [rsi+rbx*2+2], 2Fh ; '/'
0x180023595  jnz     loc_180023638
0x18002359b  cmp     word ptr [rsi+rbx*2+4], 2Fh ; '/'
0x1800235a1  jnz     loc_180023638
0x1800235a7  cmp     word ptr [rsi+rbx*2+6], 7Bh ; '{'
0x1800235ad  jnz     loc_180023638
0x1800235b3  lea     r9, [rsp+310h+hMem]
0x1800235b8  mov     [rsp+310h+StringSid], r15
0x1800235bd  mov     [rsp+310h+hMem], r15
0x1800235c2  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x1800235c7  mov     r14d, eax
0x1800235ca  test    eax, eax
0x1800235cc  js      short loc_180023633
0x1800235ce  mov     r15, [rsp+310h+hMem]
0x1800235d3  lea     rdx, [rsp+310h+StringSid]; StringSid
0x1800235d8  mov     rcx, [r15]; Sid
0x1800235db  call    cs:__imp_ConvertSidToStringSidW
0x1800235e1  test    eax, eax
0x1800235e3  jnz     short loc_1800235ED
0x1800235e5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800235ea  mov     r14d, eax
0x1800235ed  mov     rcx, r15; hMem
0x1800235f0  call    cs:__imp_LocalFree
0x1800235f6  xor     r15d, r15d
0x1800235f9  test    r14d, r14d
0x1800235fc  js      short loc_180023633
0x1800235fe  mov     rdx, [rsp+310h+StringSid]; pszStr2
0x180023603  lea     rcx, [rbx+4]
0x180023607  lea     rcx, [rsi+rcx*2]; pszStr1
0x18002360b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002360f  inc     r8; nChar
0x180023612  cmp     [rdx+r8*2], r15w
0x180023617  jnz     short loc_18002360F
0x180023619  call    cs:__imp_StrCmpNICW
0x18002361f  mov     rcx, [rsp+310h+StringSid]; pv
0x180023624  mov     edi, r15d
0x180023627  test    eax, eax
0x180023629  setz    dil
0x18002362d  call    cs:__imp_CoTaskMemFree
0x180023633  mov     r14d, dword ptr [rsp+310h+hkeyDest]
0x180023638  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows Search\\PH"...
0x18002363f  lea     rcx, [rbp+210h+var_1E4]; void *
0x180023643  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_11+10h; "\\Microsoft\\Windows Search\\PHSearchCo"...
0x18002364a  xor     edx, edx; Val
0x18002364c  movaps  xmmword ptr [rbp+210h+var_250], xmm0
0x180023650  mov     r8d, 19Ch; Size
0x180023656  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_11+20h; "ft\\Windows Search\\PHSearchConnectors"...
0x18002365d  movaps  [rbp+210h+var_230], xmm0
0x180023661  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_11+40h; "h\\PHSearchConnectors\\"
0x180023668  movaps  [rbp+210h+var_240], xmm1
0x18002366c  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_11+30h; "ws Search\\PHSearchConnectors\\"
0x180023673  movaps  [rbp+210h+var_210], xmm0
0x180023677  movups  xmm0, xmmword ptr cs:aSoftwareMicros_11+5Ch; "ectors\\"
0x18002367e  movaps  [rbp+210h+var_220], xmm1
0x180023682  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_11+50h; "chConnectors\\"
0x180023689  movaps  xmmword ptr [rbp+210h+var_200], xmm1
0x18002368d  movups  xmmword ptr [rbp+210h+var_200+0Ch], xmm0
0x180023691  call    memset_0
0x180023696  lea     r8, [rbp+210h+pszOut]; unsigned __int16 *
0x18002369a  mov     edx, 104h; unsigned __int64
0x18002369f  lea     rcx, [rbp+210h+var_250]; unsigned __int16 *
0x1800236a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800236a8  mov     ebx, eax
0x1800236aa  test    eax, eax
0x1800236ac  js      loc_180023816
0x1800236b2  lea     r9, [rsp+310h+StringSid]; HKEY *
0x1800236b7  mov     [rsp+310h+StringSid], r15
0x1800236bc  lea     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x1800236c0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800236c7  call    ?RegOpenKeyOpt@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; RegOpenKeyOpt(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x1800236cc  mov     ebx, eax
0x1800236ce  test    eax, eax
0x1800236d0  js      loc_180023816
0x1800236d6  test    edi, edi
0x1800236d8  jz      short loc_1800236ED
0x1800236da  mov     rcx, [rsp+310h+StringSid]; HKEY
0x1800236df  lea     rdx, aDonotcreatesea; "DoNotCreateSearchConnectors"
0x1800236e6  call    ?IsFlagNotSet@@YAHPEAUHKEY__@@PEBG@Z; IsFlagNotSet(HKEY__ *,ushort const *)
0x1800236eb  mov     edi, eax
0x1800236ed  xor     eax, eax
0x1800236ef  mov     word ptr [rsp+310h+hMem], r15w
0x1800236f5  mov     r9d, r14d
0x1800236f8  mov     [rsp+310h+hMem+2], rax
0x1800236fd  lea     r8, a04d; "%04d"
0x180023704  lea     rcx, [rsp+310h+hMem]; unsigned __int16 *
0x180023709  lea     edx, [rax+5]; unsigned __int64
0x18002370c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023711  mov     ebx, eax
0x180023713  test    eax, eax
0x180023715  js      loc_1800237F8
0x18002371b  mov     [rsp+310h+lpdwDisposition], r15; lpdwDisposition
0x180023720  lea     rax, [rsp+310h+hkeyDest]
0x180023725  mov     [rsp+310h+phkResult], rax; phkResult
0x18002372a  lea     rdx, [rsp+310h+hMem]; lpSubKey
0x18002372f  mov     [rsp+310h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180023734  xor     r9d, r9d; lpClass
0x180023737  mov     [rsp+310h+samDesired], 20006h; samDesired
0x18002373f  xor     r8d, r8d; Reserved
0x180023742  mov     rcx, r13; hKey
0x180023745  mov     [rsp+310h+dwFlags], r15d; dwOptions
0x18002374a  mov     [rsp+310h+hkeyDest], r15
0x18002374f  call    cs:__imp_RegCreateKeyExW
0x180023755  mov     ebx, eax
0x180023757  test    eax, eax
0x180023759  jle     short loc_180023764
0x18002375b  movzx   ebx, ax
0x18002375e  or      ebx, 80070000h
0x180023764  test    ebx, ebx
0x180023766  js      loc_1800237F8
0x18002376c  test    edi, edi
0x18002376e  jz      short loc_180023793
0x180023770  mov     rcx, [rsp+310h+StringSid]; hkeySrc
0x180023775  test    rcx, rcx
0x180023778  jz      short loc_180023793
0x18002377a  mov     r8, [rsp+310h+hkeyDest]; hkeyDest
0x18002377f  xor     r9d, r9d; fReserved
0x180023782  xor     edx, edx; pszSrcSubKey
0x180023784  call    cs:__imp_SHCopyKeyW
0x18002378a  test    eax, eax
0x18002378c  mov     edi, r15d
0x18002378f  setz    dil
0x180023793  mov     r8, [r12+8]; unsigned __int16 *
0x180023798  xor     edx, edx; unsigned __int16 *
0x18002379a  mov     rcx, [rsp+310h+hkeyDest]; HKEY
0x18002379f  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetStringValue(HKEY__ *,ushort const *,ushort const *)
0x1800237a4  mov     ebx, eax
0x1800237a6  test    eax, eax
0x1800237a8  js      short loc_1800237E6
0x1800237aa  mov     r8d, [r12]; unsigned int
0x1800237ae  lea     rdx, Value; "Version"
0x1800237b5  mov     rcx, [rsp+310h+hkeyDest]; HKEY
0x1800237ba  call    ?RegSetDWORDValue@@YAJPEAUHKEY__@@PEBGK@Z; RegSetDWORDValue(HKEY__ *,ushort const *,ulong)
0x1800237bf  mov     ebx, eax
0x1800237c1  mov     esi, 1
0x1800237c6  test    eax, eax
0x1800237c8  js      short loc_1800237EB
0x1800237ca  test    edi, edi
0x1800237cc  jnz     short loc_1800237EB
0x1800237ce  mov     rcx, [rsp+310h+hkeyDest]; HKEY
0x1800237d3  lea     rdx, aDonotcreatesea; "DoNotCreateSearchConnectors"
0x1800237da  mov     r8d, esi; unsigned int
0x1800237dd  call    ?RegSetDWORDValue@@YAJPEAUHKEY__@@PEBGK@Z; RegSetDWORDValue(HKEY__ *,ushort const *,ulong)
0x1800237e2  mov     ebx, eax
0x1800237e4  jmp     short loc_1800237EB
0x1800237e6  mov     esi, 1
0x1800237eb  mov     rcx, [rsp+310h+hkeyDest]; hKey
0x1800237f0  call    cs:__imp_RegCloseKey
0x1800237f6  jmp     short loc_1800237FD
0x1800237f8  mov     esi, 1
0x1800237fd  mov     rcx, [rsp+310h+StringSid]; hKey
0x180023802  test    rcx, rcx
0x180023805  jz      short loc_18002380D
0x180023807  call    cs:__imp_RegCloseKey
0x18002380d  test    ebx, ebx
0x18002380f  js      short loc_180023816
0x180023811  test    edi, edi
0x180023813  cmovz   ebx, esi
0x180023816  mov     eax, ebx
0x180023818  mov     rcx, [rbp+210h+var_40]
0x18002381f  xor     rcx, rsp; StackCookie
0x180023822  call    __security_check_cookie
0x180023827  mov     rbx, [rsp+310h+arg_18]
0x18002382f  add     rsp, 2E0h
0x180023836  pop     r15
0x180023838  pop     r14
0x18002383a  pop     r13
0x18002383c  pop     r12
0x18002383e  pop     rdi
0x18002383f  pop     rsi
0x180023840  pop     rbp
0x180023841  retn
```
