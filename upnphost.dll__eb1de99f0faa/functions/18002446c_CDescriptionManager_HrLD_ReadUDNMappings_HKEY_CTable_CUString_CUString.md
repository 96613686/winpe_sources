# CDescriptionManager::HrLD_ReadUDNMappings(HKEY__ *,CTable<CUString,CUString> &)

- ea: `0x18002446c`
- end: `0x1800247bd`
- name: `?HrLD_ReadUDNMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@VCUString@@V1@@@@Z`
- size: `849`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800162e0`
- `0x18004aaf0`

## callees

- `0x18000db4c`
- `0x18001ab90`
- `0x18001d254`
- `0x18002446c`
- `0x180025554`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002465e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024669`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002465e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024686`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024589`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024589`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800244e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800245d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800244e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800245d4`

## string_xrefs

- `0x1800246e5`: `HrRegOpenKeyEx`
- `0x18002472d`: `HrRegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrLD_ReadUDNMappings(__int64 a1, HKEY a2, __int64 a3)
{
  LSTATUS v5; // eax
  signed int String; // ebx
  STRSAFE_PCNZWCH v7; // rcx
  bool v8; // zf
  DWORD v10; // edi
  int v11; // eax
  bool v12; // zf
  LSTATUS v13; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  void *v18; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  hKey = 0;
  v5 = RegOpenKeyExW(a2, L"UDN Mappings", 0, 0x2001Fu, &hKey);
  String = v5;
  if ( v5 > 0 )
    String = (unsigned __int16)v5 | 0x80070000;
  if ( String < 0 )
  {
    hKey = 0;
  }
  else if ( !String )
  {
    goto LABEL_8;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    goto LABEL_9;
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    15,
    (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
    (unsigned int)"HrRegOpenKeyEx",
    String);
LABEL_8:
  v7 = WPP_GLOBAL_Control;
LABEL_9:
  v8 = String == 0;
  if ( String < 0 )
    goto LABEL_10;
  cchName = 260;
  v10 = 0;
  ftLastWriteTime = 0;
  while ( 1 )
  {
    v11 = RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    v12 = v11 == 0;
    if ( v11 > 0 )
    {
      if ( v11 == 259 )
        goto LABEL_26;
      v11 = (unsigned __int16)v11 | 0x80070000;
      v12 = v11 == 0;
    }
    if ( !v12 )
      break;
    phkResult = 0;
    v13 = RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &phkResult);
    String = v13;
    if ( v13 > 0 )
      String = (unsigned __int16)v13 | 0x80070000;
    if ( String < 0 )
    {
      phkResult = 0;
LABEL_34:
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
          (unsigned int)"HrRegOpenKeyEx",
          String);
      if ( String < 0 )
        goto LABEL_25;
      goto LABEL_21;
    }
    if ( String )
      goto LABEL_34;
LABEL_21:
    v18 = 0;
    Block = 0;
    String = CUString::HrAssign((CUString *)&v18, Name);
    if ( String >= 0 )
    {
      String = HrRegQueryString(phkResult, &Format, (struct CUString *)&Block);
      if ( String >= 0 )
        String = CTable<CUString,CUString>::HrInsertTransfer(a3, &v18, &Block);
    }
    RegCloseKey(phkResult);
    free(Block);
    free(v18);
LABEL_25:
    ++v10;
    cchName = 260;
    if ( String < 0 )
      goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
      (unsigned int)"HrRegEnumKeyEx",
      v11);
LABEL_26:
  RegCloseKey(hKey);
  v7 = WPP_GLOBAL_Control;
  v8 = String == 0;
LABEL_10:
  if ( !v8 && v7 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 81, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)String);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18002446c  mov     [rsp-8+arg_0], rbx
0x180024471  mov     [rsp-8+arg_18], rsi
0x180024476  push    rbp
0x180024477  push    rdi
0x180024478  push    r15
0x18002447a  lea     rbp, [rsp-190h]
0x180024482  sub     rsp, 290h
0x180024489  mov     rax, cs:__security_cookie
0x180024490  xor     rax, rsp
0x180024493  mov     [rbp+1A0h+var_20], rax
0x18002449a  mov     rsi, r8
0x18002449d  mov     rbx, rdx
0x1800244a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244a7  lea     r15, WPP_GLOBAL_Control
0x1800244ae  cmp     rcx, r15
0x1800244b1  jz      short loc_1800244BD
0x1800244b3  test    byte ptr [rcx+1Ch], 40h
0x1800244b7  jnz     loc_1800246A4
0x1800244bd  lea     rax, [rsp+2A0h+hKey]
0x1800244c2  mov     [rsp+2A0h+hKey], 0
0x1800244cb  mov     r9d, 2001Fh; samDesired
0x1800244d1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800244d6  xor     r8d, r8d; ulOptions
0x1800244d9  lea     rdx, aUdnMappings; "UDN Mappings"
0x1800244e0  mov     rcx, rbx; hKey
0x1800244e3  call    cs:__imp_RegOpenKeyExW
0x1800244e9  mov     ebx, eax
0x1800244eb  test    eax, eax
0x1800244ed  jle     short loc_1800244F8
0x1800244ef  movzx   ebx, ax
0x1800244f2  or      ebx, 80070000h
0x1800244f8  test    ebx, ebx
0x1800244fa  js      loc_1800246BE
0x180024500  jnz     loc_1800246C7
0x180024506  mov     rcx, cs:WPP_GLOBAL_Control
0x18002450d  test    ebx, ebx
0x18002450f  jns     short loc_180024540
0x180024511  jnz     loc_18002478D
0x180024517  mov     eax, ebx
0x180024519  mov     rcx, [rbp+1A0h+var_20]
0x180024520  xor     rcx, rsp; StackCookie
0x180024523  call    __security_check_cookie
0x180024528  lea     r11, [rsp+2A0h+var_10]
0x180024530  mov     rbx, [r11+20h]
0x180024534  mov     rsi, [r11+38h]
0x180024538  mov     rsp, r11
0x18002453b  pop     r15
0x18002453d  pop     rdi
0x18002453e  pop     rbp
0x18002453f  retn
0x180024540  mov     [rsp+2A0h+cchName], 104h
0x180024548  xor     edi, edi
0x18002454a  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], 0
0x180024553  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024558  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x18002455d  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180024562  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180024567  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180024570  lea     r8, [rsp+2A0h+Name]; lpName
0x180024575  mov     [rsp+2A0h+lpClass], 0; lpClass
0x18002457e  mov     edx, edi; dwIndex
0x180024580  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x180024589  call    cs:__imp_RegEnumKeyExW
0x18002458f  test    eax, eax
0x180024591  jle     short loc_1800245A8
0x180024593  cmp     eax, 103h
0x180024598  jz      loc_180024681
0x18002459e  movzx   eax, ax
0x1800245a1  or      eax, 80070000h
0x1800245a6  test    eax, eax
0x1800245a8  jnz     loc_18002474E
0x1800245ae  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800245b3  lea     rax, [rsp+2A0h+var_250]
0x1800245b8  mov     r9d, 2001Fh; samDesired
0x1800245be  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800245c3  xor     r8d, r8d; ulOptions
0x1800245c6  mov     [rsp+2A0h+var_250], 0
0x1800245cf  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x1800245d4  call    cs:__imp_RegOpenKeyExW
0x1800245da  mov     ebx, eax
0x1800245dc  test    eax, eax
0x1800245de  jle     short loc_1800245E9
0x1800245e0  movzx   ebx, ax
0x1800245e3  or      ebx, 80070000h
0x1800245e9  test    ebx, ebx
0x1800245eb  js      loc_180024706
0x1800245f1  jnz     loc_18002470F
0x1800245f7  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800245fc  mov     [rsp+2A0h+var_240], 0
0x180024605  lea     rcx, [rsp+2A0h+var_240]; this
0x18002460a  mov     [rsp+2A0h+Block], 0
0x180024613  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180024618  mov     ebx, eax
0x18002461a  test    eax, eax
0x18002461c  js      short loc_18002464E
0x18002461e  mov     rcx, [rsp+2A0h+var_250]; hKey
0x180024623  lea     r8, [rsp+2A0h+Block]; this
0x180024628  lea     rdx, Format; lpValueName
0x18002462f  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180024634  mov     ebx, eax
0x180024636  test    eax, eax
0x180024638  js      short loc_18002464E
0x18002463a  lea     r8, [rsp+2A0h+Block]
0x18002463f  mov     rcx, rsi
0x180024642  lea     rdx, [rsp+2A0h+var_240]
0x180024647  call    ?HrInsertTransfer@?$CTable@VCUString@@V1@@@QEAAJAEAVCUString@@0@Z; CTable<CUString,CUString>::HrInsertTransfer(CUString &,CUString &)
0x18002464c  mov     ebx, eax
0x18002464e  mov     rcx, [rsp+2A0h+var_250]; hKey
0x180024653  call    cs:__imp_RegCloseKey
0x180024659  mov     rcx, [rsp+2A0h+Block]; Block
0x18002465e  call    cs:__imp_free
0x180024664  mov     rcx, [rsp+2A0h+var_240]; Block
0x180024669  call    cs:__imp_free
0x18002466f  inc     edi
0x180024671  mov     [rsp+2A0h+cchName], 104h
0x180024679  test    ebx, ebx
0x18002467b  jns     loc_180024553
0x180024681  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024686  call    cs:__imp_RegCloseKey
0x18002468c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024693  test    ebx, ebx
0x180024695  jmp     loc_180024511
0x18002469a  test    ebx, ebx
0x18002469c  jns     loc_1800245F7
0x1800246a2  jmp     short loc_18002466F
0x1800246a4  mov     rcx, [rcx+10h]
0x1800246a8  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800246af  mov     edx, 50h ; 'P'
0x1800246b4  call    WPP_SF_
0x1800246b9  jmp     loc_1800244BD
0x1800246be  mov     [rsp+2A0h+hKey], 0
0x1800246c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246ce  cmp     rcx, r15
0x1800246d1  jz      loc_18002450D
0x1800246d7  test    byte ptr [rcx+1Ch], 1
0x1800246db  jz      loc_18002450D
0x1800246e1  mov     rcx, [rcx+10h]
0x1800246e5  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x1800246ec  mov     edx, 0Fh
0x1800246f1  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x1800246f5  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x1800246fc  call    WPP_SF_sd
0x180024701  jmp     loc_180024506
0x180024706  mov     [rsp+2A0h+var_250], 0
0x18002470f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024716  cmp     rcx, r15
0x180024719  jz      loc_18002469A
0x18002471f  test    byte ptr [rcx+1Ch], 1
0x180024723  jz      loc_18002469A
0x180024729  mov     rcx, [rcx+10h]
0x18002472d  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x180024734  mov     edx, 0Fh
0x180024739  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x18002473d  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024744  call    WPP_SF_sd
0x180024749  jmp     loc_18002469A
0x18002474e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024755  cmp     rcx, r15
0x180024758  jz      loc_180024681
0x18002475e  test    byte ptr [rcx+1Ch], 1
0x180024762  jz      loc_180024681
0x180024768  mov     rcx, [rcx+10h]
0x18002476c  lea     r9, aHrregenumkeyex; "HrRegEnumKeyEx"
0x180024773  mov     edx, 0Dh
0x180024778  mov     dword ptr [rsp+2A0h+phkResult], eax
0x18002477c  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024783  call    WPP_SF_sd
0x180024788  jmp     loc_180024681
0x18002478d  cmp     rcx, r15
0x180024790  jz      loc_180024517
0x180024796  test    byte ptr [rcx+1Ch], 1
0x18002479a  jz      loc_180024517
0x1800247a0  mov     rcx, [rcx+10h]
0x1800247a4  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800247ab  mov     edx, 51h ; 'Q'
0x1800247b0  mov     r9d, ebx
0x1800247b3  call    WPP_SF_d
0x1800247b8  jmp     loc_180024517
```
