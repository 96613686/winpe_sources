# CDescriptionManager::HrPersistDeviceSettingsToRegistry(_GUID const &,CTable<CUString,CUString> const &,CTable<_GUID,FileInfo> const &,int)

- ea: `0x18001cc38`
- end: `0x18001d042`
- name: `?HrPersistDeviceSettingsToRegistry@CDescriptionManager@@AEAAJAEBU_GUID@@AEBV?$CTable@VCUString@@V1@@@AEBV?$CTable@U_GUID@@UFileInfo@@@@H@Z`
- size: `1034`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800162e0`

## callees

- `0x18000db4c`
- `0x18001add0`
- `0x18001bf14`
- `0x18001cc38`
- `0x18001d048`
- `0x18001d0d8`
- `0x18001d100`
- `0x1800311bc`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cfaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cff1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cfaf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cebc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cebc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfe8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cd06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cdc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cd06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cdc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ce51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ce51`

## string_xrefs

- `0x18001cd3d`: `HrRegCreateKeyEx`
- `0x18001cdff`: `HrRegCreateKeyEx`
- `0x18001ce83`: `HrRegSetValue`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrPersistDeviceSettingsToRegistry(
        __int64 a1,
        const struct _GUID *a2,
        __int64 *a3,
        __int64 a4,
        int a5)
{
  signed int v8; // edi
  int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  unsigned __int16 *v12; // rbx
  LSTATUS v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // r9d
  int v16; // r14d
  unsigned int v17; // esi
  __int64 v18; // rdx
  LSTATUS v19; // eax
  DWORD v20; // eax
  const BYTE *v21; // rcx
  LSTATUS v22; // eax
  int v23; // r15d
  unsigned int i; // esi
  __int64 v25; // r14
  const struct _GUID *v26; // rdx
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  struct _SECURITY_ATTRIBUTES *dwOptions; // [rsp+20h] [rbp-51h]
  struct _SECURITY_ATTRIBUTES *dwOptionsa; // [rsp+20h] [rbp-51h]
  struct _SECURITY_ATTRIBUTES *dwOptionsb; // [rsp+20h] [rbp-51h]
  HKEY v33; // [rsp+50h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-11h] BYREF
  HKEY v36; // [rsp+68h] [rbp-9h] BYREF
  void *Block; // [rsp+70h] [rbp-1h] BYREF
  HKEY v38; // [rsp+78h] [rbp+7h] BYREF
  DWORD dwDisposition; // [rsp+D0h] [rbp+5Fh] BYREF
  int v40; // [rsp+D4h] [rbp+63h]

  v40 = HIDWORD(a1);
  v36 = 0;
  dwDisposition = 0;
  v8 = HrCreateOrOpenDescriptionKey(&v36);
  if ( v8 < 0 )
    goto LABEL_48;
  Block = 0;
  hKey = 0;
  v9 = CUString::HrInitFromGUID((CUString *)&Block, a2);
  v12 = (unsigned __int16 *)Block;
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_46;
  v8 = HrRegCreateKeyEx(v36, (const unsigned __int16 *)Block, v10, v11, dwOptions, &hKey, &dwDisposition);
  if ( v8 < 0 )
    goto LABEL_46;
  phkResult = 0;
  v13 = RegCreateKeyExW(hKey, L"UDN Mappings", 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  v8 = v13;
  if ( v13 > 0 )
    v8 = (unsigned __int16)v13 | 0x80070000;
  if ( v8 < 0 )
  {
    phkResult = 0;
LABEL_9:
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
        (unsigned int)"HrRegCreateKeyEx",
        v8);
    goto LABEL_12;
  }
  if ( v8 )
    goto LABEL_9;
LABEL_12:
  if ( v8 < 0 )
    goto LABEL_34;
  v16 = *((_DWORD *)a3 + 2);
  v17 = 0;
  if ( v16 <= 0 )
    goto LABEL_33;
  while ( v8 >= 0 )
  {
    v18 = *a3;
    v33 = 0;
    v19 = RegCreateKeyExW(phkResult, *(LPCWSTR *)(v18 + 8LL * v17), 0, 0, 0, 0x2001Fu, 0, &v33, &dwDisposition);
    v8 = v19;
    if ( v19 > 0 )
      v8 = (unsigned __int16)v19 | 0x80070000;
    if ( v8 < 0 )
    {
      v33 = 0;
LABEL_20:
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
          (unsigned int)"HrRegCreateKeyEx",
          v8);
      if ( v8 < 0 )
        goto LABEL_31;
      goto LABEL_24;
    }
    if ( v8 )
      goto LABEL_20;
LABEL_24:
    v20 = CbOfTSzAndTermSafe(*(const unsigned __int16 **)(a3[2] + 8LL * v17));
    v22 = RegSetValueExW(v33, &Format, 0, 1u, v21, v20);
    v8 = v22;
    if ( v22 > 0 )
      v8 = (unsigned __int16)v22 | 0x80070000;
    if ( v8 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
        (unsigned int)"HrRegSetValue",
        v8);
    RegCloseKey(v33);
LABEL_31:
    if ( (int)++v17 >= v16 )
      break;
  }
  v12 = (unsigned __int16 *)Block;
LABEL_33:
  RegCloseKey(phkResult);
LABEL_34:
  if ( a5 )
  {
    v38 = 0;
    v8 = HrRegCreateKeyEx(hKey, L"Files", v14, v15, dwOptionsa, &v38, &dwDisposition);
    if ( v8 >= 0 )
    {
      v23 = *(_DWORD *)(a4 + 8);
      for ( i = 0; (int)i < v23; ++i )
      {
        if ( v8 < 0 )
          break;
        v25 = 16LL * i;
        v26 = (const struct _GUID *)(v25 + *(_QWORD *)a4);
        Block = 0;
        v8 = CUString::HrInitFromGUID((CUString *)&Block, v26);
        if ( v8 >= 0 )
        {
          v33 = 0;
          v8 = HrRegCreateKeyEx(v38, (const unsigned __int16 *)Block, v27, v28, dwOptionsb, &v33, &dwDisposition);
          if ( v8 >= 0 )
          {
            v8 = HrRegSetSz(v33, L"Filename", *(const unsigned __int16 **)(v25 + *(_QWORD *)(a4 + 16)));
            if ( v8 >= 0 )
              v8 = HrRegSetSz(v33, L"Mimetype", *(const unsigned __int16 **)(v25 + *(_QWORD *)(a4 + 16) + 8));
            RegCloseKey(v33);
          }
        }
        free(Block);
      }
      RegCloseKey(v38);
    }
  }
  RegCloseKey(hKey);
  if ( v8 < 0 )
LABEL_46:
    HrRegDeleteKeyTree(v36, v12);
  RegCloseKey(v36);
  free(v12);
LABEL_48:
  if ( v8 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cc38  mov     qword ptr [rsp-8+dwDisposition], rcx
0x18001cc3d  push    rbp
0x18001cc3e  push    rbx
0x18001cc3f  push    rsi
0x18001cc40  push    rdi
0x18001cc41  push    r12
0x18001cc43  push    r13
0x18001cc45  push    r14
0x18001cc47  push    r15
0x18001cc49  lea     rbp, [rsp-17h]
0x18001cc4e  sub     rsp, 88h
0x18001cc55  xor     r15d, r15d
0x18001cc58  lea     rcx, [rbp+4Fh+var_58]; phkResult
0x18001cc5c  mov     [rbp+4Fh+var_58], r15
0x18001cc60  mov     r12, r9
0x18001cc63  mov     [rbp+4Fh+dwDisposition], r15d
0x18001cc67  mov     r13, r8
0x18001cc6a  mov     rbx, rdx
0x18001cc6d  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x18001cc72  lea     rsi, WPP_GLOBAL_Control
0x18001cc79  mov     edi, eax
0x18001cc7b  test    eax, eax
0x18001cc7d  js      loc_18001CFFE
0x18001cc83  mov     rdx, rbx; struct _GUID *
0x18001cc86  mov     [rbp+4Fh+Block], r15
0x18001cc8a  lea     rcx, [rbp+4Fh+Block]; this
0x18001cc8e  mov     [rbp+4Fh+hKey], r15
0x18001cc92  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18001cc97  mov     rbx, [rbp+4Fh+Block]
0x18001cc9b  mov     edi, eax
0x18001cc9d  test    eax, eax
0x18001cc9f  js      loc_18001CFD8
0x18001cca5  mov     rcx, [rbp+4Fh+var_58]; HKEY
0x18001cca9  lea     rax, [rbp+4Fh+dwDisposition]
0x18001ccad  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x18001ccb2  mov     rdx, rbx; unsigned __int16 *
0x18001ccb5  lea     rax, [rbp+4Fh+hKey]
0x18001ccb9  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x18001ccbe  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001ccc3  mov     edi, eax
0x18001ccc5  test    eax, eax
0x18001ccc7  js      loc_18001CFD8
0x18001cccd  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001ccd1  lea     rax, [rbp+4Fh+dwDisposition]
0x18001ccd5  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18001ccda  lea     rdx, aUdnMappings; "UDN Mappings"
0x18001cce1  lea     rax, [rbp+4Fh+var_68]
0x18001cce5  mov     [rbp+4Fh+var_68], r15
0x18001cce9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001ccee  xor     r9d, r9d; lpClass
0x18001ccf1  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001ccf6  xor     r8d, r8d; Reserved
0x18001ccf9  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18001cd01  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x18001cd06  call    cs:__imp_RegCreateKeyExW
0x18001cd0c  mov     edi, eax
0x18001cd0e  test    eax, eax
0x18001cd10  jle     short loc_18001CD1B
0x18001cd12  movzx   edi, ax
0x18001cd15  or      edi, 80070000h
0x18001cd1b  test    edi, edi
0x18001cd1d  jns     short loc_18001CD25
0x18001cd1f  mov     [rbp+4Fh+var_68], r15
0x18001cd23  jmp     short loc_18001CD27
0x18001cd25  jz      short loc_18001CD59
0x18001cd27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd2e  cmp     rcx, rsi
0x18001cd31  jz      short loc_18001CD59
0x18001cd33  test    byte ptr [rcx+1Ch], 1
0x18001cd37  jz      short loc_18001CD59
0x18001cd39  mov     rcx, [rcx+10h]
0x18001cd3d  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x18001cd44  mov     edx, 0Ah
0x18001cd49  mov     [rsp+0C0h+dwOptions], edi
0x18001cd4d  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001cd54  call    WPP_SF_sd
0x18001cd59  test    edi, edi
0x18001cd5b  js      loc_18001CEC2
0x18001cd61  mov     r14d, [r13+8]
0x18001cd65  mov     esi, r15d
0x18001cd68  test    r14d, r14d
0x18001cd6b  jle     loc_18001CEB8
0x18001cd71  lea     rbx, WPP_GLOBAL_Control
0x18001cd78  test    edi, edi
0x18001cd7a  js      loc_18001CEB4
0x18001cd80  mov     rdx, [r13+0]
0x18001cd84  lea     rax, [rbp+4Fh+dwDisposition]
0x18001cd88  mov     rcx, [rbp+4Fh+var_68]; hKey
0x18001cd8c  xor     r9d, r9d; lpClass
0x18001cd8f  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18001cd94  xor     r8d, r8d; Reserved
0x18001cd97  mov     [rbp+4Fh+var_70], r15
0x18001cd9b  lea     rax, [rbp+4Fh+var_70]
0x18001cd9f  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001cda4  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001cdad  mov     r15d, esi
0x18001cdb0  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x18001cdb8  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x18001cdc0  mov     rdx, [rdx+r15*8]; lpSubKey
0x18001cdc4  call    cs:__imp_RegCreateKeyExW
0x18001cdca  mov     edi, eax
0x18001cdcc  test    eax, eax
0x18001cdce  jle     short loc_18001CDD9
0x18001cdd0  movzx   edi, ax
0x18001cdd3  or      edi, 80070000h
0x18001cdd9  test    edi, edi
0x18001cddb  jns     short loc_18001CDE7
0x18001cddd  mov     [rbp+4Fh+var_70], 0
0x18001cde5  jmp     short loc_18001CDE9
0x18001cde7  jz      short loc_18001CE27
0x18001cde9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdf0  cmp     rcx, rbx
0x18001cdf3  jz      short loc_18001CE1B
0x18001cdf5  test    byte ptr [rcx+1Ch], 1
0x18001cdf9  jz      short loc_18001CE1B
0x18001cdfb  mov     rcx, [rcx+10h]
0x18001cdff  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x18001ce06  mov     edx, 0Ah
0x18001ce0b  mov     [rsp+0C0h+dwOptions], edi
0x18001ce0f  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001ce16  call    WPP_SF_sd
0x18001ce1b  test    edi, edi
0x18001ce1d  jns     short loc_18001CE27
0x18001ce1f  xor     r15d, r15d
0x18001ce22  jmp     loc_18001CEA9
0x18001ce27  mov     rax, [r13+10h]
0x18001ce2b  mov     rcx, [rax+r15*8]; unsigned __int16 *
0x18001ce2f  call    ?CbOfTSzAndTermSafe@@YAKPEBG@Z; CbOfTSzAndTermSafe(ushort const *)
0x18001ce34  mov     [rsp+0C0h+samDesired], eax; cbData
0x18001ce38  lea     rdx, Format; lpValueName
0x18001ce3f  mov     qword ptr [rsp+0C0h+dwOptions], rcx; lpData
0x18001ce44  mov     r9d, 1; dwType
0x18001ce4a  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18001ce4e  xor     r8d, r8d; Reserved
0x18001ce51  call    cs:__imp_RegSetValueExW
0x18001ce57  xor     r15d, r15d
0x18001ce5a  mov     edi, eax
0x18001ce5c  test    eax, eax
0x18001ce5e  jle     short loc_18001CE69
0x18001ce60  movzx   edi, ax
0x18001ce63  or      edi, 80070000h
0x18001ce69  test    edi, edi
0x18001ce6b  jz      short loc_18001CE9F
0x18001ce6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce74  cmp     rcx, rbx
0x18001ce77  jz      short loc_18001CE9F
0x18001ce79  test    byte ptr [rcx+1Ch], 1
0x18001ce7d  jz      short loc_18001CE9F
0x18001ce7f  mov     rcx, [rcx+10h]
0x18001ce83  lea     r9, aHrregsetvalue; "HrRegSetValue"
0x18001ce8a  mov     edx, 10h
0x18001ce8f  mov     [rsp+0C0h+dwOptions], edi; struct _SECURITY_ATTRIBUTES *
0x18001ce93  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001ce9a  call    WPP_SF_sd
0x18001ce9f  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18001cea3  call    cs:__imp_RegCloseKey
0x18001cea9  inc     esi
0x18001ceab  cmp     esi, r14d
0x18001ceae  jl      loc_18001CD78
0x18001ceb4  mov     rbx, [rbp+4Fh+Block]
0x18001ceb8  mov     rcx, [rbp+4Fh+var_68]; hKey
0x18001cebc  call    cs:__imp_RegCloseKey
0x18001cec2  cmp     [rbp+4Fh+arg_20], r15d
0x18001cec6  jz      loc_18001CFCA
0x18001cecc  mov     rcx, [rbp+4Fh+hKey]; HKEY
0x18001ced0  lea     rax, [rbp+4Fh+dwDisposition]
0x18001ced4  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x18001ced9  lea     rdx, SubKey; "Files"
0x18001cee0  lea     rax, [rbp+4Fh+var_48]
0x18001cee4  mov     [rbp+4Fh+var_48], r15
0x18001cee8  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x18001ceed  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001cef2  mov     edi, eax
0x18001cef4  test    eax, eax
0x18001cef6  js      loc_18001CFCA
0x18001cefc  mov     r15d, [r12+8]
0x18001cf01  xor     esi, esi
0x18001cf03  test    r15d, r15d
0x18001cf06  jle     loc_18001CFC0
0x18001cf0c  test    edi, edi
0x18001cf0e  js      loc_18001CFC0
0x18001cf14  mov     rdx, [r12]
0x18001cf18  lea     rcx, [rbp+4Fh+Block]; this
0x18001cf1c  mov     r14d, esi
0x18001cf1f  shl     r14, 4
0x18001cf23  add     rdx, r14; struct _GUID *
0x18001cf26  mov     [rbp+4Fh+Block], 0
0x18001cf2e  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18001cf33  mov     edi, eax
0x18001cf35  test    eax, eax
0x18001cf37  js      short loc_18001CFAB
0x18001cf39  mov     rdx, [rbp+4Fh+Block]; unsigned __int16 *
0x18001cf3d  lea     rax, [rbp+4Fh+dwDisposition]
0x18001cf41  mov     rcx, [rbp+4Fh+var_48]; HKEY
0x18001cf45  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x18001cf4a  lea     rax, [rbp+4Fh+var_70]
0x18001cf4e  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x18001cf53  mov     [rbp+4Fh+var_70], 0
0x18001cf5b  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001cf60  mov     edi, eax
0x18001cf62  test    eax, eax
0x18001cf64  js      short loc_18001CFAB
0x18001cf66  mov     r8, [r12+10h]
0x18001cf6b  lea     rdx, aFilename; "Filename"
0x18001cf72  mov     rcx, [rbp+4Fh+var_70]; HKEY
0x18001cf76  mov     r8, [r14+r8]; unsigned __int16 *
0x18001cf7a  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18001cf7f  mov     edi, eax
0x18001cf81  test    eax, eax
0x18001cf83  js      short loc_18001CFA1
0x18001cf85  mov     r8, [r12+10h]
0x18001cf8a  lea     rdx, aMimetype_0; "Mimetype"
0x18001cf91  mov     rcx, [rbp+4Fh+var_70]; HKEY
0x18001cf95  mov     r8, [r14+r8+8]; unsigned __int16 *
0x18001cf9a  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18001cf9f  mov     edi, eax
0x18001cfa1  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18001cfa5  call    cs:__imp_RegCloseKey
0x18001cfab  mov     rcx, [rbp+4Fh+Block]; Block
0x18001cfaf  call    cs:__imp_free
0x18001cfb5  inc     esi
0x18001cfb7  cmp     esi, r15d
0x18001cfba  jl      loc_18001CF0C
0x18001cfc0  mov     rcx, [rbp+4Fh+var_48]; hKey
0x18001cfc4  call    cs:__imp_RegCloseKey
0x18001cfca  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001cfce  call    cs:__imp_RegCloseKey
0x18001cfd4  test    edi, edi
0x18001cfd6  jns     short loc_18001CFE4
0x18001cfd8  mov     rcx, [rbp+4Fh+var_58]; HKEY
0x18001cfdc  mov     rdx, rbx; unsigned __int16 *
0x18001cfdf  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x18001cfe4  mov     rcx, [rbp+4Fh+var_58]; hKey
0x18001cfe8  call    cs:__imp_RegCloseKey
0x18001cfee  mov     rcx, rbx; Block
0x18001cff1  call    cs:__imp_free
0x18001cff7  lea     rsi, WPP_GLOBAL_Control
0x18001cffe  test    edi, edi
0x18001d000  jz      short loc_18001D02C
0x18001d002  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d009  cmp     rcx, rsi
0x18001d00c  jz      short loc_18001D02C
0x18001d00e  test    byte ptr [rcx+1Ch], 1
0x18001d012  jz      short loc_18001D02C
0x18001d014  mov     rcx, [rcx+10h]
0x18001d018  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001d01f  mov     edx, 15h
0x18001d024  mov     r9d, edi
0x18001d027  call    WPP_SF_d
0x18001d02c  mov     eax, edi
0x18001d02e  add     rsp, 88h
0x18001d035  pop     r15
0x18001d037  pop     r14
0x18001d039  pop     r13
0x18001d03b  pop     r12
0x18001d03d  pop     rdi
0x18001d03e  pop     rsi
0x18001d03f  pop     rbx
0x18001d040  pop     rbp
0x18001d041  retn
```
