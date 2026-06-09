# AeWERQueryFileInfo

- ea: `0x180034fe0`
- end: `0x1800353b9`
- name: `AeWERQueryFileInfo`
- size: `985`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800353c0`
- `0x180090050`

## callees

- `0x18001ac98`
- `0x18001ad94`
- `0x18002ff34`
- `0x180034fe0`
- `0x18004ec4c`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003527f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800352eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003527f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800352eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003536d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035383`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003536d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035383`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180035159`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180035159`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800351d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003521b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800351d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003521b`

## string_xrefs

- `0x180035079`: `Failed to hash File path [%#x]`
- `0x18003509b`: `AppCompat\Programs`
- `0x1800350c8`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x1800350fc`: `Amcache.hve`
- `0x1800351ed`: `Failed to open file key [%d]`
- `0x180035236`: `Failed to open file key [%d]`

## pseudocode

```c
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
0x180034fe0  mov     [rsp-8+arg_8], rbx
0x180034fe5  mov     [rsp-8+arg_10], rsi
0x180034fea  push    rbp
0x180034feb  push    rdi
0x180034fec  push    r14
0x180034fee  lea     rbp, [rsp-600h]
0x180034ff6  sub     rsp, 700h
0x180034ffd  mov     rax, cs:__security_cookie
0x180035004  xor     rax, rsp
0x180035007  mov     [rbp+610h+var_20], rax
0x18003500e  mov     rsi, rcx
0x180035011  mov     ebx, 20Ah
0x180035016  mov     r8d, ebx; Size
0x180035019  lea     rcx, [rbp+610h+Destination]; void *
0x180035020  xor     edx, edx; Val
0x180035022  call    memset_0
0x180035027  mov     r8d, ebx; Size
0x18003502a  lea     rcx, [rbp+610h+var_650]; void *
0x18003502e  xor     edx, edx; Val
0x180035030  call    memset_0
0x180035035  xor     r14d, r14d
0x180035038  cmp     dword ptr [rsi+4], 210h
0x18003503f  mov     [rsp+710h+var_6D0], r14d
0x180035044  mov     [rsp+710h+phkResult], r14
0x180035049  mov     [rsp+710h+hkey], r14
0x18003504e  mov     [rsp+710h+hKey], r14
0x180035053  jnz     loc_180035348
0x180035059  lea     edi, [r14+1]
0x18003505d  cmp     [rsi], edi
0x18003505f  jnz     loc_180035348
0x180035065  mov     r8, [rsi+8]; unsigned __int16 *
0x180035069  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x18003506e  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x180035073  mov     ebx, eax
0x180035075  test    eax, eax
0x180035077  jns     short loc_18003509B
0x180035079  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x180035080  lea     r8d, [r14+7Dh]
0x180035084  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18003508b  mov     [rsp+710h+Reserved], eax
0x18003508f  mov     ecx, edi
0x180035091  call    AslLogCallPrintf
0x180035096  jmp     loc_18003534D
0x18003509b  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x1800350a2  mov     r9d, 7FFE0030h
0x1800350a8  lea     r8, aSS; "%s\\%s"
0x1800350af  mov     qword ptr [rsp+710h+Reserved], rax
0x1800350b4  mov     edx, 105h; unsigned __int64
0x1800350b9  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x1800350bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800350c2  mov     ebx, eax
0x1800350c4  test    eax, eax
0x1800350c6  jns     short loc_1800350D7
0x1800350c8  lea     r9, aStringcchprint; "StringCchPrintf for StoreDirectory [%#x"...
0x1800350cf  mov     r8d, 88h
0x1800350d5  jmp     short loc_180035084
0x1800350d7  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x1800350db  lea     rcx, [rbp+610h+Destination]; Destination
0x1800350e2  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x1800350e7  mov     ebx, eax
0x1800350e9  test    eax, eax
0x1800350eb  jns     short loc_1800350FC
0x1800350ed  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1800350f4  mov     r8d, 93h
0x1800350fa  jmp     short loc_180035084
0x1800350fc  lea     rax, aAmcacheHve; "Amcache.hve"
0x180035103  mov     edx, 104h; unsigned __int64
0x180035108  lea     r9, [rbp+610h+Destination]
0x18003510f  mov     qword ptr [rsp+710h+Reserved], rax
0x180035114  lea     r8, aSS; "%s\\%s"
0x18003511b  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x180035122  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035127  mov     ebx, eax
0x180035129  test    eax, eax
0x18003512b  jns     short loc_18003513F
0x18003512d  lea     r9, aStringcchprint_0; "StringCchPrintf [%#x]"
0x180035134  mov     r8d, 9Dh
0x18003513a  jmp     loc_180035084
0x18003513f  xor     r9d, r9d; dwOptions
0x180035142  mov     [rsp+710h+Reserved], r14d; Reserved
0x180035147  mov     r8d, 20019h; samDesired
0x18003514d  lea     rdx, [rsp+710h+phkResult]; phkResult
0x180035152  lea     rcx, [rbp+610h+File]; lpFile
0x180035159  call    cs:__imp_RegLoadAppKeyW
0x180035160  nop     dword ptr [rax+rax+00h]
0x180035165  mov     ebx, eax
0x180035167  test    eax, eax
0x180035169  jz      short loc_1800351B7
0x18003516b  cmp     eax, 5
0x18003516e  jz      short loc_18003517D
0x180035170  cmp     eax, 2
0x180035173  jz      short loc_18003517D
0x180035175  mov     r8d, 0AFh
0x18003517b  jmp     short loc_180035188
0x18003517d  mov     edi, 3
0x180035182  mov     r8d, 0ABh
0x180035188  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x18003518f  mov     ecx, edi
0x180035191  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180035198  mov     [rsp+710h+Reserved], ebx
0x18003519c  call    AslLogCallPrintf
0x1800351a1  test    ebx, ebx
0x1800351a3  jle     loc_18003534D
0x1800351a9  movzx   ebx, bx
0x1800351ac  or      ebx, 80070000h
0x1800351b2  jmp     loc_18003534D
0x1800351b7  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800351bc  lea     rax, [rsp+710h+hKey]
0x1800351c1  mov     r9d, 20019h; samDesired
0x1800351c7  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800351cc  xor     r8d, r8d; ulOptions
0x1800351cf  lea     rdx, aRoot_0; "Root"
0x1800351d6  call    cs:__imp_RegOpenKeyExW
0x1800351dd  nop     dword ptr [rax+rax+00h]
0x1800351e2  mov     ebx, eax
0x1800351e4  test    eax, eax
0x1800351e6  jz      short loc_1800351FC
0x1800351e8  cmp     eax, 2
0x1800351eb  jz      short loc_1800351A9
0x1800351ed  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800351f4  mov     r8d, 0BDh
0x1800351fa  jmp     short loc_18003518F
0x1800351fc  mov     rcx, [rsp+710h+hKey]; hKey
0x180035201  lea     rax, [rsp+710h+hkey]
0x180035206  mov     r9d, 20019h; samDesired
0x18003520c  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180035211  xor     r8d, r8d; ulOptions
0x180035214  lea     rdx, aInventoryappli; "InventoryApplicationFile"
0x18003521b  call    cs:__imp_RegOpenKeyExW
0x180035222  nop     dword ptr [rax+rax+00h]
0x180035227  mov     ebx, eax
0x180035229  test    eax, eax
0x18003522b  jz      short loc_180035248
0x18003522d  cmp     eax, 2
0x180035230  jz      loc_1800351A9
0x180035236  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x18003523d  mov     r8d, 0C7h
0x180035243  jmp     loc_18003518F
0x180035248  mov     rcx, [rsp+710h+hkey]; hkey
0x18003524d  lea     rax, [rsp+710h+var_6D0]
0x180035252  mov     [rsp+710h+pcbData], rax; pcbData
0x180035257  lea     rdi, [rsi+10h]
0x18003525b  mov     [rsp+710h+pvData], rdi; pvData
0x180035260  lea     r8, aProgramid; "ProgramId"
0x180035267  mov     r9d, 2; dwFlags
0x18003526d  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x180035272  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180035277  mov     [rsp+710h+var_6D0], 100h
0x18003527f  call    cs:__imp_RegGetValueW
0x180035286  nop     dword ptr [rax+rax+00h]
0x18003528b  mov     ebx, eax
0x18003528d  test    eax, eax
0x18003528f  jz      short loc_1800352B1
0x180035291  cmp     eax, 2
0x180035294  jz      loc_1800351A9
0x18003529a  lea     r9, aFailedToGetPro; "Failed to get program id [%d]"
0x1800352a1  mov     r8d, 0DCh
0x1800352a7  mov     ecx, 3
0x1800352ac  jmp     loc_180035191
0x1800352b1  mov     rcx, [rsp+710h+hkey]; hkey
0x1800352b6  lea     rax, [rsp+710h+var_6D0]
0x1800352bb  mov     [rsp+710h+pcbData], rax; pcbData
0x1800352c0  lea     r8, aFileid; "FileId"
0x1800352c7  add     rsi, 110h
0x1800352ce  mov     [rsp+710h+var_6D0], 100h
0x1800352d6  mov     [rsp+710h+pvData], rsi; pvData
0x1800352db  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800352e0  mov     r9d, 2; dwFlags
0x1800352e6  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800352eb  call    cs:__imp_RegGetValueW
0x1800352f2  nop     dword ptr [rax+rax+00h]
0x1800352f7  mov     ebx, eax
0x1800352f9  test    eax, eax
0x1800352fb  jz      short loc_180035315
0x1800352fd  cmp     eax, 2
0x180035300  jz      loc_1800351A9
0x180035306  lea     r9, aFailedToGetFil; "Failed to get file id [%d]"
0x18003530d  mov     r8d, 0F2h
0x180035313  jmp     short loc_1800352A7
0x180035315  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035319  mov     rcx, rax
0x18003531c  inc     rcx
0x18003531f  cmp     [rsi+rcx*2], r14w
0x180035324  jnz     short loc_18003531C
0x180035326  cmp     rcx, 2Ch ; ','
0x18003532a  jnz     short loc_180035341
0x18003532c  inc     rax
0x18003532f  cmp     [rdi+rax*2], r14w
0x180035334  jnz     short loc_18003532C
0x180035336  cmp     rax, 2Ch ; ','
0x18003533a  jnz     short loc_180035341
0x18003533c  mov     ebx, r14d
0x18003533f  jmp     short loc_18003534D
0x180035341  mov     ebx, 80070002h
0x180035346  jmp     short loc_18003534D
0x180035348  mov     ebx, 80070057h
0x18003534d  mov     rcx, [rsp+710h+hkey]; hKey
0x180035352  test    rcx, rcx
0x180035355  jz      short loc_180035363
0x180035357  call    cs:__imp_RegCloseKey
0x18003535e  nop     dword ptr [rax+rax+00h]
0x180035363  mov     rcx, [rsp+710h+hKey]; hKey
0x180035368  test    rcx, rcx
0x18003536b  jz      short loc_180035379
0x18003536d  call    cs:__imp_RegCloseKey
0x180035374  nop     dword ptr [rax+rax+00h]
0x180035379  mov     rcx, [rsp+710h+phkResult]; hKey
0x18003537e  test    rcx, rcx
0x180035381  jz      short loc_18003538F
0x180035383  call    cs:__imp_RegCloseKey
0x18003538a  nop     dword ptr [rax+rax+00h]
0x18003538f  mov     eax, ebx
0x180035391  mov     rcx, [rbp+610h+var_20]
0x180035398  xor     rcx, rsp; StackCookie
0x18003539b  call    __security_check_cookie
0x1800353a0  lea     r11, [rsp+710h+var_10]
0x1800353a8  mov     rbx, [r11+28h]
0x1800353ac  mov     rsi, [r11+30h]
0x1800353b0  mov     rsp, r11
0x1800353b3  pop     r14
0x1800353b5  pop     rdi
0x1800353b6  pop     rbp
0x1800353b7  retn
```
