# AeWERQueryFileInfo

- ea: `0x18003359c`
- end: `0x180033940`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033948`
- `0x18008c144`

## callees

- `0x180018e14`
- `0x180018f0c`
- `0x18002e404`
- `0x18003359c`
- `0x18004c8b4`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033825`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003388b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033825`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003388b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033911`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033911`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180033715`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180033715`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003378c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003378c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337cb`

## string_xrefs

- `0x180033635`: `Failed to hash File path [%#x]`
- `0x180033657`: `AppCompat\Programs`
- `0x180033684`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x1800336b8`: `Amcache.hve`
- `0x18003379d`: `Failed to open file key [%d]`
- `0x1800337dc`: `Failed to open file key [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  unsigned int v4; // edi
  int PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // edx
  LSTATUS v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rcx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rsi
  LSTATUS v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v28[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR File[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(Destination, 0, 0x20Au);
  memset_0(v28, 0, 0x20Au);
  v3 = *(_DWORD *)(a1 + 4) == 528;
  pcbData = 0;
  phkResult = 0;
  hkey = 0;
  hKey = 0;
  if ( v3 && (v4 = 1, *(_DWORD *)a1 == 1) )
  {
    PersistedLocation = ComputeFileCacheKey(SubKey, v2, *(const unsigned __int16 **)(a1 + 8));
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "Failed to hash File path [%#x]";
      v8 = 125;
LABEL_5:
      AslLogCallPrintf(1, "AeWERQueryFileInfo", v8, v7, PersistedLocation);
      goto LABEL_42;
    }
    PersistedLocation = StringCchPrintfW(v28, 0x105u, L"%s\\%s", 2147352624, L"AppCompat\\Programs");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf for StoreDirectory [%#x]";
      v8 = 136;
      goto LABEL_5;
    }
    PersistedLocation = AeGetPersistedLocation(Destination, v9, v28);
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "AeGetPersistedLocation failed [%#x]";
      v8 = 147;
      goto LABEL_5;
    }
    PersistedLocation = StringCchPrintfW(File, 0x104u, L"%s\\%s", Destination, L"Amcache.hve");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf [%#x]";
      v8 = 157;
      goto LABEL_5;
    }
    v10 = RegLoadAppKeyW(File, &phkResult, 0x20019u, 0, 0);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 == 5 || v10 == 2 )
      {
        v4 = 3;
        v11 = 171;
      }
      else
      {
        v11 = 175;
      }
      v12 = "RegLoadAppKey failed [%d]";
      goto LABEL_18;
    }
    v14 = RegOpenKeyExW(phkResult, L"Root", 0, 0x20019u, &hKey);
    v6 = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 189;
LABEL_18:
        v13 = v4;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    v15 = RegOpenKeyExW(hKey, L"InventoryApplicationFile", 0, 0x20019u, &hkey);
    v6 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 199;
        goto LABEL_18;
      }
LABEL_20:
      v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_42;
    }
    v16 = a1 + 16;
    pcbData = 256;
    ValueW = RegGetValueW(hkey, SubKey, L"ProgramId", 2u, 0, (PVOID)(a1 + 16), &pcbData);
    v6 = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_20;
      v12 = "Failed to get program id [%d]";
      v11 = 220;
LABEL_30:
      v13 = 3;
LABEL_19:
      AslLogCallPrintf(v13, "AeWERQueryFileInfo", v11, v12, v6);
      if ( v6 <= 0 )
        goto LABEL_42;
      goto LABEL_20;
    }
    pvData = (void *)(a1 + 272);
    pcbData = 256;
    v19 = RegGetValueW(hkey, SubKey, L"FileId", 2u, 0, pvData, &pcbData);
    v6 = v19;
    if ( v19 )
    {
      if ( v19 == 2 )
        goto LABEL_20;
      v12 = "Failed to get file id [%d]";
      v11 = 242;
      goto LABEL_30;
    }
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pvData + v21) );
    if ( v21 != 44 )
      goto LABEL_40;
    do
      ++v20;
    while ( *(_WORD *)(v16 + 2 * v20) );
    if ( v20 == 44 )
      v6 = 0;
    else
LABEL_40:
      v6 = -2147024894;
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_42:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003359c  mov     [rsp-8+arg_8], rbx
0x1800335a1  mov     [rsp-8+arg_10], rsi
0x1800335a6  push    rbp
0x1800335a7  push    rdi
0x1800335a8  push    r14
0x1800335aa  lea     rbp, [rsp-600h]
0x1800335b2  sub     rsp, 700h
0x1800335b9  mov     rax, cs:__security_cookie
0x1800335c0  xor     rax, rsp
0x1800335c3  mov     [rbp+610h+var_20], rax
0x1800335ca  mov     rsi, rcx
0x1800335cd  mov     ebx, 20Ah
0x1800335d2  mov     r8d, ebx; Size
0x1800335d5  lea     rcx, [rbp+610h+Destination]; void *
0x1800335dc  xor     edx, edx; Val
0x1800335de  call    memset_0
0x1800335e3  mov     r8d, ebx; Size
0x1800335e6  lea     rcx, [rbp+610h+var_650]; void *
0x1800335ea  xor     edx, edx; Val
0x1800335ec  call    memset_0
0x1800335f1  xor     r14d, r14d
0x1800335f4  cmp     dword ptr [rsi+4], 210h
0x1800335fb  mov     [rsp+710h+var_6D0], r14d
0x180033600  mov     [rsp+710h+phkResult], r14
0x180033605  mov     [rsp+710h+hkey], r14
0x18003360a  mov     [rsp+710h+hKey], r14
0x18003360f  jnz     loc_1800338E2
0x180033615  lea     edi, [r14+1]
0x180033619  cmp     [rsi], edi
0x18003361b  jnz     loc_1800338E2
0x180033621  mov     r8, [rsi+8]; unsigned __int16 *
0x180033625  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x18003362a  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x18003362f  mov     ebx, eax
0x180033631  test    eax, eax
0x180033633  jns     short loc_180033657
0x180033635  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x18003363c  lea     r8d, [r14+7Dh]
0x180033640  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180033647  mov     [rsp+710h+Reserved], eax
0x18003364b  mov     ecx, edi
0x18003364d  call    AslLogCallPrintf
0x180033652  jmp     loc_1800338E7
0x180033657  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x18003365e  mov     r9d, 7FFE0030h
0x180033664  lea     r8, aSS; "%s\\%s"
0x18003366b  mov     qword ptr [rsp+710h+Reserved], rax
0x180033670  mov     edx, 105h; unsigned __int64
0x180033675  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x180033679  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003367e  mov     ebx, eax
0x180033680  test    eax, eax
0x180033682  jns     short loc_180033693
0x180033684  lea     r9, aStringcchprint; "StringCchPrintf for StoreDirectory [%#x"...
0x18003368b  mov     r8d, 88h
0x180033691  jmp     short loc_180033640
0x180033693  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x180033697  lea     rcx, [rbp+610h+Destination]; Destination
0x18003369e  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x1800336a3  mov     ebx, eax
0x1800336a5  test    eax, eax
0x1800336a7  jns     short loc_1800336B8
0x1800336a9  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1800336b0  mov     r8d, 93h
0x1800336b6  jmp     short loc_180033640
0x1800336b8  lea     rax, aAmcacheHve; "Amcache.hve"
0x1800336bf  mov     edx, 104h; unsigned __int64
0x1800336c4  lea     r9, [rbp+610h+Destination]
0x1800336cb  mov     qword ptr [rsp+710h+Reserved], rax
0x1800336d0  lea     r8, aSS; "%s\\%s"
0x1800336d7  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1800336de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800336e3  mov     ebx, eax
0x1800336e5  test    eax, eax
0x1800336e7  jns     short loc_1800336FB
0x1800336e9  lea     r9, aStringcchprint_0; "StringCchPrintf [%#x]"
0x1800336f0  mov     r8d, 9Dh
0x1800336f6  jmp     loc_180033640
0x1800336fb  xor     r9d, r9d; dwOptions
0x1800336fe  mov     [rsp+710h+Reserved], r14d; Reserved
0x180033703  mov     r8d, 20019h; samDesired
0x180033709  lea     rdx, [rsp+710h+phkResult]; phkResult
0x18003370e  lea     rcx, [rbp+610h+File]; lpFile
0x180033715  call    cs:__imp_RegLoadAppKeyW
0x18003371b  mov     ebx, eax
0x18003371d  test    eax, eax
0x18003371f  jz      short loc_18003376D
0x180033721  cmp     eax, 5
0x180033724  jz      short loc_180033733
0x180033726  cmp     eax, 2
0x180033729  jz      short loc_180033733
0x18003372b  mov     r8d, 0AFh
0x180033731  jmp     short loc_18003373E
0x180033733  mov     edi, 3
0x180033738  mov     r8d, 0ABh
0x18003373e  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x180033745  mov     ecx, edi
0x180033747  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18003374e  mov     [rsp+710h+Reserved], ebx
0x180033752  call    AslLogCallPrintf
0x180033757  test    ebx, ebx
0x180033759  jle     loc_1800338E7
0x18003375f  movzx   ebx, bx
0x180033762  or      ebx, 80070000h
0x180033768  jmp     loc_1800338E7
0x18003376d  mov     rcx, [rsp+710h+phkResult]; hKey
0x180033772  lea     rax, [rsp+710h+hKey]
0x180033777  mov     r9d, 20019h; samDesired
0x18003377d  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180033782  xor     r8d, r8d; ulOptions
0x180033785  lea     rdx, aRoot_0; "Root"
0x18003378c  call    cs:__imp_RegOpenKeyExW
0x180033792  mov     ebx, eax
0x180033794  test    eax, eax
0x180033796  jz      short loc_1800337AC
0x180033798  cmp     eax, 2
0x18003379b  jz      short loc_18003375F
0x18003379d  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800337a4  mov     r8d, 0BDh
0x1800337aa  jmp     short loc_180033745
0x1800337ac  mov     rcx, [rsp+710h+hKey]; hKey
0x1800337b1  lea     rax, [rsp+710h+hkey]
0x1800337b6  mov     r9d, 20019h; samDesired
0x1800337bc  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800337c1  xor     r8d, r8d; ulOptions
0x1800337c4  lea     rdx, aInventoryappli; "InventoryApplicationFile"
0x1800337cb  call    cs:__imp_RegOpenKeyExW
0x1800337d1  mov     ebx, eax
0x1800337d3  test    eax, eax
0x1800337d5  jz      short loc_1800337EE
0x1800337d7  cmp     eax, 2
0x1800337da  jz      short loc_18003375F
0x1800337dc  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800337e3  mov     r8d, 0C7h
0x1800337e9  jmp     loc_180033745
0x1800337ee  mov     rcx, [rsp+710h+hkey]; hkey
0x1800337f3  lea     rax, [rsp+710h+var_6D0]
0x1800337f8  mov     [rsp+710h+pcbData], rax; pcbData
0x1800337fd  lea     rdi, [rsi+10h]
0x180033801  mov     [rsp+710h+pvData], rdi; pvData
0x180033806  lea     r8, aProgramid; "ProgramId"
0x18003380d  mov     r9d, 2; dwFlags
0x180033813  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x180033818  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x18003381d  mov     [rsp+710h+var_6D0], 100h
0x180033825  call    cs:__imp_RegGetValueW
0x18003382b  mov     ebx, eax
0x18003382d  test    eax, eax
0x18003382f  jz      short loc_180033851
0x180033831  cmp     eax, 2
0x180033834  jz      loc_18003375F
0x18003383a  lea     r9, aFailedToGetPro; "Failed to get program id [%d]"
0x180033841  mov     r8d, 0DCh
0x180033847  mov     ecx, 3
0x18003384c  jmp     loc_180033747
0x180033851  mov     rcx, [rsp+710h+hkey]; hkey
0x180033856  lea     rax, [rsp+710h+var_6D0]
0x18003385b  mov     [rsp+710h+pcbData], rax; pcbData
0x180033860  lea     r8, aFileid; "FileId"
0x180033867  add     rsi, 110h
0x18003386e  mov     [rsp+710h+var_6D0], 100h
0x180033876  mov     [rsp+710h+pvData], rsi; pvData
0x18003387b  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180033880  mov     r9d, 2; dwFlags
0x180033886  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18003388b  call    cs:__imp_RegGetValueW
0x180033891  mov     ebx, eax
0x180033893  test    eax, eax
0x180033895  jz      short loc_1800338AF
0x180033897  cmp     eax, 2
0x18003389a  jz      loc_18003375F
0x1800338a0  lea     r9, aFailedToGetFil; "Failed to get file id [%d]"
0x1800338a7  mov     r8d, 0F2h
0x1800338ad  jmp     short loc_180033847
0x1800338af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800338b3  mov     rcx, rax
0x1800338b6  inc     rcx
0x1800338b9  cmp     [rsi+rcx*2], r14w
0x1800338be  jnz     short loc_1800338B6
0x1800338c0  cmp     rcx, 2Ch ; ','
0x1800338c4  jnz     short loc_1800338DB
0x1800338c6  inc     rax
0x1800338c9  cmp     [rdi+rax*2], r14w
0x1800338ce  jnz     short loc_1800338C6
0x1800338d0  cmp     rax, 2Ch ; ','
0x1800338d4  jnz     short loc_1800338DB
0x1800338d6  mov     ebx, r14d
0x1800338d9  jmp     short loc_1800338E7
0x1800338db  mov     ebx, 80070002h
0x1800338e0  jmp     short loc_1800338E7
0x1800338e2  mov     ebx, 80070057h
0x1800338e7  mov     rcx, [rsp+710h+hkey]; hKey
0x1800338ec  test    rcx, rcx
0x1800338ef  jz      short loc_1800338F7
0x1800338f1  call    cs:__imp_RegCloseKey
0x1800338f7  mov     rcx, [rsp+710h+hKey]; hKey
0x1800338fc  test    rcx, rcx
0x1800338ff  jz      short loc_180033907
0x180033901  call    cs:__imp_RegCloseKey
0x180033907  mov     rcx, [rsp+710h+phkResult]; hKey
0x18003390c  test    rcx, rcx
0x18003390f  jz      short loc_180033917
0x180033911  call    cs:__imp_RegCloseKey
0x180033917  mov     eax, ebx
0x180033919  mov     rcx, [rbp+610h+var_20]
0x180033920  xor     rcx, rsp; StackCookie
0x180033923  call    __security_check_cookie
0x180033928  lea     r11, [rsp+710h+var_10]
0x180033930  mov     rbx, [r11+28h]
0x180033934  mov     rsi, [r11+30h]
0x180033938  mov     rsp, r11
0x18003393b  pop     r14
0x18003393d  pop     rdi
0x18003393e  pop     rbp
0x18003393f  retn
```
