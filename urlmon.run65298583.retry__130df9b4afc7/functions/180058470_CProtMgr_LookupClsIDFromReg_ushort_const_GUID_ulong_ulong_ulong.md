# CProtMgr::LookupClsIDFromReg(ushort const *,_GUID *,ulong *,ulong *,ulong)

- ea: `0x180058470`
- end: `0x18005872f`
- name: `?LookupClsIDFromReg@CProtMgr@@UEAAJPEBGPEAU_GUID@@PEAK2K@Z`
- size: `703`
- prototype: `int(CProtMgr *__hidden this, const unsigned __int16 *, struct _GUID *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180044b84`
- `0x180058470`
- `0x180058738`
- `0x1800587e8`
- `0x1800a2718`
- `0x18011baa0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800584aa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800584bd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800584aa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800584bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180058513`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180058513`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800584f6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800584f6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800586e5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800586e5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x180058692`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x180058692`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800586fa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800586fa`

## string_xrefs

- `0x180058533`: `SOFTWARE\Classes\PROTOCOLS\Handler\`
- `0x18005867b`: `CLSID`

## pseudocode

```c
__int64 __fastcall CProtMgr::LookupClsIDFromReg(
        CProtMgr *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int v8; // edi
  PSTR v9; // rax
  __int64 v10; // r10
  __int64 v11; // rcx
  const char *v12; // rdx
  __int64 v13; // r8
  CHAR *v14; // r9
  CHAR *v15; // rax
  __int64 v16; // rcx
  CHAR *v17; // rax
  int v18; // edx
  CHAR *v19; // r8
  CHAR *v20; // rdx
  CHAR *v21; // rax
  DWORD v23; // eax
  DWORD pcbData; // [rsp+40h] [rbp-2B8h] BYREF
  CHAR MultiByteStr[40]; // [rsp+48h] [rbp-2B0h] BYREF
  char v27[16]; // [rsp+70h] [rbp-288h] BYREF
  WCHAR WideCharStr[40]; // [rsp+80h] [rbp-278h] BYREF
  CHAR pszSubKey[256]; // [rsp+D0h] [rbp-228h] BYREF
  CHAR pvData[256]; // [rsp+1D0h] [rbp-128h] BYREF

  v8 = -2146697203;
  if ( a2 )
  {
    if ( (unsigned __int8)IEConfiguration_GetBool(268435481) || (unsigned __int8)IEConfiguration_GetBool(536870925) )
      return (unsigned int)GetKnownImmersiveProtocolClsID(a2, a3);
    if ( !WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, 32, 0, 0) )
      MultiByteStr[0] = 0;
    MultiByteStr[32] = 0;
    v9 = StrChrA(MultiByteStr, 0x3Au);
    if ( v9 )
      *v9 = 0;
    v10 = 2147483646;
    pcbData = 256;
    v11 = 2147483646;
    v12 = "SOFTWARE\\Classes\\PROTOCOLS\\Handler\\";
    v13 = 256;
    v14 = pszSubKey;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v14++ = *v12++;
      --v11;
      --v13;
    }
    while ( v13 );
    v15 = v14 - 1;
    if ( v13 )
      v15 = v14;
    *v15 = 0;
    if ( v13 )
    {
      v16 = 256;
      v17 = pszSubKey;
      do
      {
        if ( !*v17 )
          break;
        ++v17;
        --v16;
      }
      while ( v16 );
      v18 = -2147024809;
      if ( v16 )
      {
        v19 = &pvData[-v16];
        v20 = MultiByteStr;
        do
        {
          if ( !v10 )
            break;
          if ( !*v20 )
            break;
          *v19++ = *v20++;
          --v10;
          --v16;
        }
        while ( v16 );
        v21 = v19 - 1;
        v18 = -2147024774;
        if ( v16 )
        {
          v21 = v19;
          v18 = 0;
        }
        *v21 = 0;
      }
      if ( v18 >= 0
        && (!a6
         || (int)StringCchPrintfA(v27, 0x10u, "\\0x%08x", a6) >= 0 && (int)StringCchCatA(pszSubKey, 0x100u, v27) >= 0)
        && !SHRegGetUSValueA(pszSubKey, "CLSID", 0, pvData, &pcbData, 0, 0, 0) )
      {
        v23 = pcbData;
        if ( pcbData >= 0x100 )
        {
          v23 = 255;
          pcbData = 255;
        }
        if ( v23 >= 0x100uLL )
          _report_rangecheckfailure();
        pvData[v23] = 0;
        if ( !MultiByteToWideChar(0, 0, pvData, -1, WideCharStr, 39) )
          WideCharStr[0] = 0;
        return (unsigned int)CLSIDFromString(WideCharStr, a3);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180058470  mov     [rsp+arg_0], rbx
0x180058475  push    rbp
0x180058476  push    rsi
0x180058477  push    rdi
0x180058478  sub     rsp, 2E0h
0x18005847f  mov     rax, cs:__security_cookie
0x180058486  xor     rax, rsp
0x180058489  mov     [rsp+2F8h+var_28], rax
0x180058491  mov     rsi, r8
0x180058494  mov     rbx, rdx
0x180058497  mov     edi, 800C000Dh
0x18005849c  test    rdx, rdx
0x18005849f  jz      loc_1800585E8
0x1800584a5  mov     ecx, 10000019h
0x1800584aa  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800584b0  test    al, al
0x1800584b2  jnz     loc_180058707
0x1800584b8  mov     ecx, 2000000Dh
0x1800584bd  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800584c3  test    al, al
0x1800584c5  jnz     loc_180058707
0x1800584cb  xor     ebp, ebp
0x1800584cd  lea     rax, [rsp+2F8h+MultiByteStr]
0x1800584d2  mov     [rsp+2F8h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x1800584d7  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800584dd  mov     [rsp+2F8h+lpDefaultChar], rbp; lpDefaultChar
0x1800584e2  mov     r8, rbx; lpWideCharStr
0x1800584e5  mov     [rsp+2F8h+cbMultiByte], 20h ; ' '; cbMultiByte
0x1800584ed  xor     edx, edx; dwFlags
0x1800584ef  xor     ecx, ecx; CodePage
0x1800584f1  mov     [rsp+2F8h+lpMultiByteStr], rax; lpMultiByteStr
0x1800584f6  call    cs:__imp_WideCharToMultiByte
0x1800584fc  test    eax, eax
0x1800584fe  jz      loc_18005860D
0x180058504  mov     edx, 3Ah ; ':'; wMatch
0x180058509  mov     [rsp+2F8h+var_290], bpl
0x18005850e  lea     rcx, [rsp+2F8h+MultiByteStr]; pszStart
0x180058513  call    cs:__imp_StrChrA
0x180058519  test    rax, rax
0x18005851c  jnz     loc_180058617
0x180058522  mov     r10d, 7FFFFFFEh
0x180058528  mov     [rsp+2F8h+pcbData], 100h
0x180058530  mov     ecx, r10d
0x180058533  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\PROTOCOLS\\Handler\\"
0x18005853a  mov     r8d, 100h
0x180058540  lea     r9, [rsp+2F8h+pszSubKey]
0x180058548  test    rcx, rcx
0x18005854b  jz      short loc_180058566
0x18005854d  movzx   eax, byte ptr [rdx]
0x180058550  test    al, al
0x180058552  jz      short loc_180058566
0x180058554  mov     [r9], al
0x180058557  inc     rdx
0x18005855a  inc     r9
0x18005855d  dec     rcx
0x180058560  sub     r8, 1
0x180058564  jnz     short loc_180058548
0x180058566  test    r8, r8
0x180058569  lea     rax, [r9-1]
0x18005856d  cmovnz  rax, r9
0x180058571  mov     [rax], bpl
0x180058574  jz      short loc_1800585E8
0x180058576  mov     ecx, 100h
0x18005857b  lea     rax, [rsp+2F8h+pszSubKey]
0x180058583  cmp     [rax], bpl
0x180058586  jz      short loc_180058591
0x180058588  inc     rax
0x18005858b  sub     rcx, 1
0x18005858f  jnz     short loc_180058583
0x180058591  test    rcx, rcx
0x180058594  mov     edx, 80070057h
0x180058599  cmovnz  edx, ebp
0x18005859c  jz      short loc_1800585E4
0x18005859e  lea     r8, [rsp+2F8h+pvData]
0x1800585a6  sub     r8, rcx
0x1800585a9  lea     rdx, [rsp+2F8h+MultiByteStr]
0x1800585ae  xchg    ax, ax
0x1800585b0  test    r10, r10
0x1800585b3  jz      short loc_1800585CE
0x1800585b5  movzx   eax, byte ptr [rdx]
0x1800585b8  test    al, al
0x1800585ba  jz      short loc_1800585CE
0x1800585bc  mov     [r8], al
0x1800585bf  inc     rdx
0x1800585c2  inc     r8
0x1800585c5  dec     r10
0x1800585c8  sub     rcx, 1
0x1800585cc  jnz     short loc_1800585B0
0x1800585ce  test    rcx, rcx
0x1800585d1  lea     rax, [r8-1]
0x1800585d5  mov     edx, 8007007Ah
0x1800585da  cmovnz  rax, r8
0x1800585de  cmovnz  edx, ebp
0x1800585e1  mov     [rax], bpl
0x1800585e4  test    edx, edx
0x1800585e6  jns     short loc_18005861F
0x1800585e8  mov     eax, edi
0x1800585ea  mov     rcx, [rsp+2F8h+var_28]
0x1800585f2  xor     rcx, rsp; StackCookie
0x1800585f5  call    __security_check_cookie
0x1800585fa  mov     rbx, [rsp+2F8h+arg_0]
0x180058602  add     rsp, 2E0h
0x180058609  pop     rdi
0x18005860a  pop     rsi
0x18005860b  pop     rbp
0x18005860c  retn
0x18005860d  mov     [rsp+2F8h+MultiByteStr], bpl
0x180058612  jmp     loc_180058504
0x180058617  mov     [rax], bpl
0x18005861a  jmp     loc_180058522
0x18005861f  mov     r9d, [rsp+2F8h+arg_28]
0x180058627  test    r9d, r9d
0x18005862a  jz      short loc_180058661
0x18005862c  lea     r8, a0x08x; "\\0x%08x"
0x180058633  mov     edx, 10h; unsigned __int64
0x180058638  lea     rcx, [rsp+2F8h+var_288]; char *
0x18005863d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180058642  test    eax, eax
0x180058644  js      short loc_1800585E8
0x180058646  lea     r8, [rsp+2F8h+var_288]; char *
0x18005864b  mov     edx, 100h; unsigned __int64
0x180058650  lea     rcx, [rsp+2F8h+pszSubKey]; char *
0x180058658  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18005865d  test    eax, eax
0x18005865f  js      short loc_1800585E8
0x180058661  mov     dword ptr [rsp+2F8h+lpUsedDefaultChar], ebp; dwDefaultDataSize
0x180058665  lea     rax, [rsp+2F8h+pcbData]
0x18005866a  mov     [rsp+2F8h+lpDefaultChar], rbp; pvDefaultData
0x18005866f  lea     r9, [rsp+2F8h+pvData]; pvData
0x180058677  mov     [rsp+2F8h+cbMultiByte], ebp; fIgnoreHKCU
0x18005867b  lea     rdx, aClsid_3; "CLSID"
0x180058682  xor     r8d, r8d; pdwType
0x180058685  mov     [rsp+2F8h+lpMultiByteStr], rax; pcbData
0x18005868a  lea     rcx, [rsp+2F8h+pszSubKey]; pszSubKey
0x180058692  call    cs:__imp_SHRegGetUSValueA
0x180058698  test    eax, eax
0x18005869a  jnz     loc_1800585E8
0x1800586a0  mov     eax, [rsp+2F8h+pcbData]
0x1800586a4  cmp     eax, 100h
0x1800586a9  jnb     short loc_180058714
0x1800586ab  mov     ecx, eax
0x1800586ad  cmp     rcx, 100h
0x1800586b4  jnb     short loc_180058729
0x1800586b6  mov     [rsp+rcx+2F8h+pvData], bpl
0x1800586be  lea     rax, [rsp+2F8h+WideCharStr]
0x1800586c6  xor     ecx, ecx; CodePage
0x1800586c8  mov     [rsp+2F8h+cbMultiByte], 27h ; '''; cchWideChar
0x1800586d0  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800586d6  mov     [rsp+2F8h+lpMultiByteStr], rax; lpWideCharStr
0x1800586db  lea     r8, [rsp+2F8h+pvData]; lpMultiByteStr
0x1800586e3  xor     edx, edx; dwFlags
0x1800586e5  call    cs:__imp_MultiByteToWideChar
0x1800586eb  test    eax, eax
0x1800586ed  jz      short loc_18005871F
0x1800586ef  mov     rdx, rsi; pclsid
0x1800586f2  lea     rcx, [rsp+2F8h+WideCharStr]; lpsz
0x1800586fa  call    cs:__imp_CLSIDFromString
0x180058700  mov     edi, eax
0x180058702  jmp     loc_1800585E8
0x180058707  mov     rdx, rsi; struct _GUID *
0x18005870a  mov     rcx, rbx; unsigned __int16 *
0x18005870d  call    ?GetKnownImmersiveProtocolClsID@@YAJPEBGPEAU_GUID@@@Z; GetKnownImmersiveProtocolClsID(ushort const *,_GUID *)
0x180058712  jmp     short loc_180058700
0x180058714  mov     eax, 0FFh
0x180058719  mov     [rsp+2F8h+pcbData], eax
0x18005871d  jmp     short loc_1800586AB
0x18005871f  mov     [rsp+2F8h+WideCharStr], bp
0x180058727  jmp     short loc_1800586EF
0x180058729  call    __report_rangecheckfailure
```
