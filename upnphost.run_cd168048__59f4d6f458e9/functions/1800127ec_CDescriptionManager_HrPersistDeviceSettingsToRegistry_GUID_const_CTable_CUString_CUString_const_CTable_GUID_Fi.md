# CDescriptionManager::HrPersistDeviceSettingsToRegistry(_GUID const &,CTable<CUString,CUString> const &,CTable<_GUID,FileInfo> const &,int)

- ea: `0x1800127ec`
- end: `0x180012c39`
- name: `?HrPersistDeviceSettingsToRegistry@CDescriptionManager@@AEAAJAEBU_GUID@@AEBV?$CTable@VCUString@@V1@@@AEBV?$CTable@U_GUID@@UFileInfo@@@@H@Z`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5f0`

## callees

- `0x18000fb0c`
- `0x180010d88`
- `0x1800127ec`
- `0x180012c40`
- `0x180012cd8`
- `0x180012d00`
- `0x1800200f4`
- `0x180032c6c`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012be1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012be1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bd2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800128ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001297e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800128ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001297e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a11`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a11`

## string_xrefs

- `0x1800128f7`: `HrRegCreateKeyEx`
- `0x1800129bf`: `HrRegCreateKeyEx`
- `0x180012a49`: `HrRegSetValue`

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
0x1800127ec  mov     qword ptr [rsp-8+dwDisposition], rcx
0x1800127f1  push    rbp
0x1800127f2  push    rbx
0x1800127f3  push    rsi
0x1800127f4  push    rdi
0x1800127f5  push    r12
0x1800127f7  push    r13
0x1800127f9  push    r14
0x1800127fb  push    r15
0x1800127fd  lea     rbp, [rsp-17h]
0x180012802  sub     rsp, 88h
0x180012809  xor     r15d, r15d
0x18001280c  lea     rcx, [rbp+4Fh+var_58]; phkResult
0x180012810  mov     [rbp+4Fh+var_58], r15
0x180012814  mov     r12, r9
0x180012817  mov     [rbp+4Fh+dwDisposition], r15d
0x18001281b  mov     r13, r8
0x18001281e  mov     rbx, rdx
0x180012821  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x180012826  lea     rsi, WPP_GLOBAL_Control
0x18001282d  mov     edi, eax
0x18001282f  test    eax, eax
0x180012831  js      loc_180012BF4
0x180012837  mov     rdx, rbx; struct _GUID *
0x18001283a  mov     [rbp+4Fh+Block], r15
0x18001283e  lea     rcx, [rbp+4Fh+Block]; this
0x180012842  mov     [rbp+4Fh+hKey], r15
0x180012846  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18001284b  mov     rbx, [rbp+4Fh+Block]
0x18001284f  mov     edi, eax
0x180012851  test    eax, eax
0x180012853  js      loc_180012BC2
0x180012859  mov     rcx, [rbp+4Fh+var_58]; HKEY
0x18001285d  lea     rax, [rbp+4Fh+dwDisposition]
0x180012861  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x180012866  mov     rdx, rbx; unsigned __int16 *
0x180012869  lea     rax, [rbp+4Fh+hKey]
0x18001286d  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x180012872  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180012877  mov     edi, eax
0x180012879  test    eax, eax
0x18001287b  js      loc_180012BC2
0x180012881  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180012885  lea     rax, [rbp+4Fh+dwDisposition]
0x180012889  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18001288e  lea     rdx, aUdnMappings; "UDN Mappings"
0x180012895  lea     rax, [rbp+4Fh+var_68]
0x180012899  mov     [rbp+4Fh+var_68], r15
0x18001289d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800128a2  xor     r9d, r9d; lpClass
0x1800128a5  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800128aa  xor     r8d, r8d; Reserved
0x1800128ad  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x1800128b5  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x1800128ba  call    cs:__imp_RegCreateKeyExW
0x1800128c1  nop     dword ptr [rax+rax+00h]
0x1800128c6  mov     edi, eax
0x1800128c8  test    eax, eax
0x1800128ca  jle     short loc_1800128D5
0x1800128cc  movzx   edi, ax
0x1800128cf  or      edi, 80070000h
0x1800128d5  test    edi, edi
0x1800128d7  jns     short loc_1800128DF
0x1800128d9  mov     [rbp+4Fh+var_68], r15
0x1800128dd  jmp     short loc_1800128E1
0x1800128df  jz      short loc_180012913
0x1800128e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e8  cmp     rcx, rsi
0x1800128eb  jz      short loc_180012913
0x1800128ed  test    byte ptr [rcx+1Ch], 1
0x1800128f1  jz      short loc_180012913
0x1800128f3  mov     rcx, [rcx+10h]
0x1800128f7  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x1800128fe  mov     edx, 0Ah
0x180012903  mov     [rsp+0C0h+dwOptions], edi
0x180012907  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001290e  call    WPP_SF_sd
0x180012913  test    edi, edi
0x180012915  js      loc_180012A94
0x18001291b  mov     r14d, [r13+8]
0x18001291f  mov     esi, r15d
0x180012922  test    r14d, r14d
0x180012925  jle     loc_180012A84
0x18001292b  lea     rbx, WPP_GLOBAL_Control
0x180012932  test    edi, edi
0x180012934  js      loc_180012A80
0x18001293a  mov     rdx, [r13+0]
0x18001293e  lea     rax, [rbp+4Fh+dwDisposition]
0x180012942  mov     rcx, [rbp+4Fh+var_68]; hKey
0x180012946  xor     r9d, r9d; lpClass
0x180012949  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18001294e  xor     r8d, r8d; Reserved
0x180012951  mov     [rbp+4Fh+var_70], r15
0x180012955  lea     rax, [rbp+4Fh+var_70]
0x180012959  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001295e  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180012967  mov     r15d, esi
0x18001296a  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x180012972  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x18001297a  mov     rdx, [rdx+r15*8]; lpSubKey
0x18001297e  call    cs:__imp_RegCreateKeyExW
0x180012985  nop     dword ptr [rax+rax+00h]
0x18001298a  mov     edi, eax
0x18001298c  test    eax, eax
0x18001298e  jle     short loc_180012999
0x180012990  movzx   edi, ax
0x180012993  or      edi, 80070000h
0x180012999  test    edi, edi
0x18001299b  jns     short loc_1800129A7
0x18001299d  mov     [rbp+4Fh+var_70], 0
0x1800129a5  jmp     short loc_1800129A9
0x1800129a7  jz      short loc_1800129E7
0x1800129a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129b0  cmp     rcx, rbx
0x1800129b3  jz      short loc_1800129DB
0x1800129b5  test    byte ptr [rcx+1Ch], 1
0x1800129b9  jz      short loc_1800129DB
0x1800129bb  mov     rcx, [rcx+10h]
0x1800129bf  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x1800129c6  mov     edx, 0Ah
0x1800129cb  mov     [rsp+0C0h+dwOptions], edi
0x1800129cf  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x1800129d6  call    WPP_SF_sd
0x1800129db  test    edi, edi
0x1800129dd  jns     short loc_1800129E7
0x1800129df  xor     r15d, r15d
0x1800129e2  jmp     loc_180012A75
0x1800129e7  mov     rax, [r13+10h]
0x1800129eb  mov     rcx, [rax+r15*8]; unsigned __int16 *
0x1800129ef  call    ?CbOfTSzAndTermSafe@@YAKPEBG@Z; CbOfTSzAndTermSafe(ushort const *)
0x1800129f4  mov     [rsp+0C0h+samDesired], eax; cbData
0x1800129f8  lea     rdx, Format; lpValueName
0x1800129ff  mov     qword ptr [rsp+0C0h+dwOptions], rcx; lpData
0x180012a04  mov     r9d, 1; dwType
0x180012a0a  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180012a0e  xor     r8d, r8d; Reserved
0x180012a11  call    cs:__imp_RegSetValueExW
0x180012a18  nop     dword ptr [rax+rax+00h]
0x180012a1d  xor     r15d, r15d
0x180012a20  mov     edi, eax
0x180012a22  test    eax, eax
0x180012a24  jle     short loc_180012A2F
0x180012a26  movzx   edi, ax
0x180012a29  or      edi, 80070000h
0x180012a2f  test    edi, edi
0x180012a31  jz      short loc_180012A65
0x180012a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a3a  cmp     rcx, rbx
0x180012a3d  jz      short loc_180012A65
0x180012a3f  test    byte ptr [rcx+1Ch], 1
0x180012a43  jz      short loc_180012A65
0x180012a45  mov     rcx, [rcx+10h]
0x180012a49  lea     r9, aHrregsetvalue; "HrRegSetValue"
0x180012a50  mov     edx, 10h
0x180012a55  mov     [rsp+0C0h+dwOptions], edi; struct _SECURITY_ATTRIBUTES *
0x180012a59  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180012a60  call    WPP_SF_sd
0x180012a65  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180012a69  call    cs:__imp_RegCloseKey
0x180012a70  nop     dword ptr [rax+rax+00h]
0x180012a75  inc     esi
0x180012a77  cmp     esi, r14d
0x180012a7a  jl      loc_180012932
0x180012a80  mov     rbx, [rbp+4Fh+Block]
0x180012a84  mov     rcx, [rbp+4Fh+var_68]; hKey
0x180012a88  call    cs:__imp_RegCloseKey
0x180012a8f  nop     dword ptr [rax+rax+00h]
0x180012a94  cmp     [rbp+4Fh+arg_20], r15d
0x180012a98  jz      loc_180012BAE
0x180012a9e  mov     rcx, [rbp+4Fh+hKey]; HKEY
0x180012aa2  lea     rax, [rbp+4Fh+dwDisposition]
0x180012aa6  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x180012aab  lea     rdx, SubKey; "Files"
0x180012ab2  lea     rax, [rbp+4Fh+var_48]
0x180012ab6  mov     [rbp+4Fh+var_48], r15
0x180012aba  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x180012abf  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180012ac4  mov     edi, eax
0x180012ac6  test    eax, eax
0x180012ac8  js      loc_180012BAE
0x180012ace  mov     r15d, [r12+8]
0x180012ad3  xor     esi, esi
0x180012ad5  test    r15d, r15d
0x180012ad8  jle     loc_180012B9E
0x180012ade  test    edi, edi
0x180012ae0  js      loc_180012B9E
0x180012ae6  mov     rdx, [r12]
0x180012aea  lea     rcx, [rbp+4Fh+Block]; this
0x180012aee  mov     r14d, esi
0x180012af1  shl     r14, 4
0x180012af5  add     rdx, r14; struct _GUID *
0x180012af8  mov     [rbp+4Fh+Block], 0
0x180012b00  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x180012b05  mov     edi, eax
0x180012b07  test    eax, eax
0x180012b09  js      short loc_180012B83
0x180012b0b  mov     rdx, [rbp+4Fh+Block]; unsigned __int16 *
0x180012b0f  lea     rax, [rbp+4Fh+dwDisposition]
0x180012b13  mov     rcx, [rbp+4Fh+var_48]; HKEY
0x180012b17  mov     [rsp+0C0h+lpSecurityAttributes], rax; unsigned int *
0x180012b1c  lea     rax, [rbp+4Fh+var_70]
0x180012b20  mov     qword ptr [rsp+0C0h+samDesired], rax; HKEY *
0x180012b25  mov     [rbp+4Fh+var_70], 0
0x180012b2d  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180012b32  mov     edi, eax
0x180012b34  test    eax, eax
0x180012b36  js      short loc_180012B83
0x180012b38  mov     r8, [r12+10h]
0x180012b3d  lea     rdx, aFilename; "Filename"
0x180012b44  mov     rcx, [rbp+4Fh+var_70]; HKEY
0x180012b48  mov     r8, [r14+r8]; unsigned __int16 *
0x180012b4c  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180012b51  mov     edi, eax
0x180012b53  test    eax, eax
0x180012b55  js      short loc_180012B73
0x180012b57  mov     r8, [r12+10h]
0x180012b5c  lea     rdx, aMimetype_0; "Mimetype"
0x180012b63  mov     rcx, [rbp+4Fh+var_70]; HKEY
0x180012b67  mov     r8, [r14+r8+8]; unsigned __int16 *
0x180012b6c  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180012b71  mov     edi, eax
0x180012b73  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180012b77  call    cs:__imp_RegCloseKey
0x180012b7e  nop     dword ptr [rax+rax+00h]
0x180012b83  mov     rcx, [rbp+4Fh+Block]; Block
0x180012b87  call    cs:__imp_free
0x180012b8e  nop     dword ptr [rax+rax+00h]
0x180012b93  inc     esi
0x180012b95  cmp     esi, r15d
0x180012b98  jl      loc_180012ADE
0x180012b9e  mov     rcx, [rbp+4Fh+var_48]; hKey
0x180012ba2  call    cs:__imp_RegCloseKey
0x180012ba9  nop     dword ptr [rax+rax+00h]
0x180012bae  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180012bb2  call    cs:__imp_RegCloseKey
0x180012bb9  nop     dword ptr [rax+rax+00h]
0x180012bbe  test    edi, edi
0x180012bc0  jns     short loc_180012BCE
0x180012bc2  mov     rcx, [rbp+4Fh+var_58]; HKEY
0x180012bc6  mov     rdx, rbx; unsigned __int16 *
0x180012bc9  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x180012bce  mov     rcx, [rbp+4Fh+var_58]; hKey
0x180012bd2  call    cs:__imp_RegCloseKey
0x180012bd9  nop     dword ptr [rax+rax+00h]
0x180012bde  mov     rcx, rbx; Block
0x180012be1  call    cs:__imp_free
0x180012be8  nop     dword ptr [rax+rax+00h]
0x180012bed  lea     rsi, WPP_GLOBAL_Control
0x180012bf4  test    edi, edi
0x180012bf6  jz      short loc_180012C22
0x180012bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bff  cmp     rcx, rsi
0x180012c02  jz      short loc_180012C22
0x180012c04  test    byte ptr [rcx+1Ch], 1
0x180012c08  jz      short loc_180012C22
0x180012c0a  mov     rcx, [rcx+10h]
0x180012c0e  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180012c15  mov     edx, 15h
0x180012c1a  mov     r9d, edi
0x180012c1d  call    WPP_SF_d
0x180012c22  mov     eax, edi
0x180012c24  add     rsp, 88h
0x180012c2b  pop     r15
0x180012c2d  pop     r14
0x180012c2f  pop     r13
0x180012c31  pop     r12
0x180012c33  pop     rdi
0x180012c34  pop     rsi
0x180012c35  pop     rbx
0x180012c36  pop     rbp
0x180012c37  retn
```
