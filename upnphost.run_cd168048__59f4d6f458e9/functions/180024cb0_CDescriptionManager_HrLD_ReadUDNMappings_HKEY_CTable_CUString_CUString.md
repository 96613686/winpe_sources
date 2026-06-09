# CDescriptionManager::HrLD_ReadUDNMappings(HKEY__ *,CTable<CUString,CUString> &)

- ea: `0x180024cb0`
- end: `0x18002502c`
- name: `?HrLD_ReadUDNMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@VCUString@@V1@@@@Z`
- size: `892`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x18004dc80`

## callees

- `0x18000f8a0`
- `0x180011cfc`
- `0x1800200f4`
- `0x180024cb0`
- `0x180026510`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024ebb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024ecc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024ebb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024dd4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024dd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e25`

## string_xrefs

- `0x180024f54`: `HrRegOpenKeyEx`
- `0x180024f9c`: `HrRegOpenKeyEx`

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
0x180024cb0  mov     [rsp-8+arg_0], rbx
0x180024cb5  mov     [rsp-8+arg_18], rsi
0x180024cba  push    rbp
0x180024cbb  push    rdi
0x180024cbc  push    r15
0x180024cbe  lea     rbp, [rsp-190h]
0x180024cc6  sub     rsp, 290h
0x180024ccd  mov     rax, cs:__security_cookie
0x180024cd4  xor     rax, rsp
0x180024cd7  mov     [rbp+1A0h+var_20], rax
0x180024cde  mov     rsi, r8
0x180024ce1  mov     rbx, rdx
0x180024ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ceb  lea     r15, WPP_GLOBAL_Control
0x180024cf2  cmp     rcx, r15
0x180024cf5  jz      short loc_180024D01
0x180024cf7  test    byte ptr [rcx+1Ch], 40h
0x180024cfb  jnz     loc_180024F13
0x180024d01  lea     rax, [rsp+2A0h+hKey]
0x180024d06  mov     [rsp+2A0h+hKey], 0
0x180024d0f  mov     r9d, 2001Fh; samDesired
0x180024d15  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180024d1a  xor     r8d, r8d; ulOptions
0x180024d1d  lea     rdx, aUdnMappings; "UDN Mappings"
0x180024d24  mov     rcx, rbx; hKey
0x180024d27  call    cs:__imp_RegOpenKeyExW
0x180024d2e  nop     dword ptr [rax+rax+00h]
0x180024d33  mov     ebx, eax
0x180024d35  test    eax, eax
0x180024d37  jle     short loc_180024D42
0x180024d39  movzx   ebx, ax
0x180024d3c  or      ebx, 80070000h
0x180024d42  test    ebx, ebx
0x180024d44  js      loc_180024F2D
0x180024d4a  jnz     loc_180024F36
0x180024d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d57  test    ebx, ebx
0x180024d59  jns     short loc_180024D8B
0x180024d5b  jnz     loc_180024FFC
0x180024d61  mov     eax, ebx
0x180024d63  mov     rcx, [rbp+1A0h+var_20]
0x180024d6a  xor     rcx, rsp; StackCookie
0x180024d6d  call    __security_check_cookie
0x180024d72  lea     r11, [rsp+2A0h+var_10]
0x180024d7a  mov     rbx, [r11+20h]
0x180024d7e  mov     rsi, [r11+38h]
0x180024d82  mov     rsp, r11
0x180024d85  pop     r15
0x180024d87  pop     rdi
0x180024d88  pop     rbp
0x180024d89  retn
0x180024d8b  mov     [rsp+2A0h+cchName], 104h
0x180024d93  xor     edi, edi
0x180024d95  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], 0
0x180024d9e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024da3  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x180024da8  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180024dad  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180024db2  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180024dbb  lea     r8, [rsp+2A0h+Name]; lpName
0x180024dc0  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180024dc9  mov     edx, edi; dwIndex
0x180024dcb  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x180024dd4  call    cs:__imp_RegEnumKeyExW
0x180024ddb  nop     dword ptr [rax+rax+00h]
0x180024de0  test    eax, eax
0x180024de2  jle     short loc_180024DF9
0x180024de4  cmp     eax, 103h
0x180024de9  jz      loc_180024EEA
0x180024def  movzx   eax, ax
0x180024df2  or      eax, 80070000h
0x180024df7  test    eax, eax
0x180024df9  jnz     loc_180024FBD
0x180024dff  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024e04  lea     rax, [rsp+2A0h+var_250]
0x180024e09  mov     r9d, 2001Fh; samDesired
0x180024e0f  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180024e14  xor     r8d, r8d; ulOptions
0x180024e17  mov     [rsp+2A0h+var_250], 0
0x180024e20  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180024e25  call    cs:__imp_RegOpenKeyExW
0x180024e2c  nop     dword ptr [rax+rax+00h]
0x180024e31  mov     ebx, eax
0x180024e33  test    eax, eax
0x180024e35  jle     short loc_180024E40
0x180024e37  movzx   ebx, ax
0x180024e3a  or      ebx, 80070000h
0x180024e40  test    ebx, ebx
0x180024e42  js      loc_180024F75
0x180024e48  jnz     loc_180024F7E
0x180024e4e  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180024e53  mov     [rsp+2A0h+var_240], 0
0x180024e5c  lea     rcx, [rsp+2A0h+var_240]; this
0x180024e61  mov     [rsp+2A0h+Block], 0
0x180024e6a  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180024e6f  mov     ebx, eax
0x180024e71  test    eax, eax
0x180024e73  js      short loc_180024EA5
0x180024e75  mov     rcx, [rsp+2A0h+var_250]; hKey
0x180024e7a  lea     r8, [rsp+2A0h+Block]; this
0x180024e7f  lea     rdx, Format; lpValueName
0x180024e86  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180024e8b  mov     ebx, eax
0x180024e8d  test    eax, eax
0x180024e8f  js      short loc_180024EA5
0x180024e91  lea     r8, [rsp+2A0h+Block]
0x180024e96  mov     rcx, rsi
0x180024e99  lea     rdx, [rsp+2A0h+var_240]
0x180024e9e  call    ?HrInsertTransfer@?$CTable@VCUString@@V1@@@QEAAJAEAVCUString@@0@Z; CTable<CUString,CUString>::HrInsertTransfer(CUString &,CUString &)
0x180024ea3  mov     ebx, eax
0x180024ea5  mov     rcx, [rsp+2A0h+var_250]; hKey
0x180024eaa  call    cs:__imp_RegCloseKey
0x180024eb1  nop     dword ptr [rax+rax+00h]
0x180024eb6  mov     rcx, [rsp+2A0h+Block]; Block
0x180024ebb  call    cs:__imp_free
0x180024ec2  nop     dword ptr [rax+rax+00h]
0x180024ec7  mov     rcx, [rsp+2A0h+var_240]; Block
0x180024ecc  call    cs:__imp_free
0x180024ed3  nop     dword ptr [rax+rax+00h]
0x180024ed8  inc     edi
0x180024eda  mov     [rsp+2A0h+cchName], 104h
0x180024ee2  test    ebx, ebx
0x180024ee4  jns     loc_180024D9E
0x180024eea  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024eef  call    cs:__imp_RegCloseKey
0x180024ef6  nop     dword ptr [rax+rax+00h]
0x180024efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f02  test    ebx, ebx
0x180024f04  jmp     loc_180024D5B
0x180024f09  test    ebx, ebx
0x180024f0b  jns     loc_180024E4E
0x180024f11  jmp     short loc_180024ED8
0x180024f13  mov     rcx, [rcx+10h]
0x180024f17  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180024f1e  mov     edx, 50h ; 'P'
0x180024f23  call    WPP_SF_
0x180024f28  jmp     loc_180024D01
0x180024f2d  mov     [rsp+2A0h+hKey], 0
0x180024f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f3d  cmp     rcx, r15
0x180024f40  jz      loc_180024D57
0x180024f46  test    byte ptr [rcx+1Ch], 1
0x180024f4a  jz      loc_180024D57
0x180024f50  mov     rcx, [rcx+10h]
0x180024f54  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x180024f5b  mov     edx, 0Fh
0x180024f60  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x180024f64  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024f6b  call    WPP_SF_sd
0x180024f70  jmp     loc_180024D50
0x180024f75  mov     [rsp+2A0h+var_250], 0
0x180024f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f85  cmp     rcx, r15
0x180024f88  jz      loc_180024F09
0x180024f8e  test    byte ptr [rcx+1Ch], 1
0x180024f92  jz      loc_180024F09
0x180024f98  mov     rcx, [rcx+10h]
0x180024f9c  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x180024fa3  mov     edx, 0Fh
0x180024fa8  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x180024fac  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024fb3  call    WPP_SF_sd
0x180024fb8  jmp     loc_180024F09
0x180024fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fc4  cmp     rcx, r15
0x180024fc7  jz      loc_180024EEA
0x180024fcd  test    byte ptr [rcx+1Ch], 1
0x180024fd1  jz      loc_180024EEA
0x180024fd7  mov     rcx, [rcx+10h]
0x180024fdb  lea     r9, aHrregenumkeyex; "HrRegEnumKeyEx"
0x180024fe2  mov     edx, 0Dh
0x180024fe7  mov     dword ptr [rsp+2A0h+phkResult], eax
0x180024feb  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180024ff2  call    WPP_SF_sd
0x180024ff7  jmp     loc_180024EEA
0x180024ffc  cmp     rcx, r15
0x180024fff  jz      loc_180024D61
0x180025005  test    byte ptr [rcx+1Ch], 1
0x180025009  jz      loc_180024D61
0x18002500f  mov     rcx, [rcx+10h]
0x180025013  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18002501a  mov     edx, 51h ; 'Q'
0x18002501f  mov     r9d, ebx
0x180025022  call    WPP_SF_d
0x180025027  jmp     loc_180024D61
```
