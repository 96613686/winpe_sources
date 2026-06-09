# EnableEapMD5Support

- ea: `0x1800435f8`
- end: `0x1800438e4`
- name: `EnableEapMD5Support`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x18002cca4`
- `0x180042a80`
- `0x1800435f8`
- `0x180055030`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x1800438c2`
- `ADVAPI32!RegDeleteKeyW` at `0x1800438c2`
- `ADVAPI32!RegSetValueExW` at `0x1800437e9`
- `ADVAPI32!RegSetValueExW` at `0x1800437e9`
- `ADVAPI32!RegCreateKeyExW` at `0x180043670`
- `ADVAPI32!RegCreateKeyExW` at `0x180043670`
- `ADVAPI32!RegCloseKey` at `0x180043802`
- `ADVAPI32!RegCloseKey` at `0x180043802`

## string_xrefs

- `0x180043631`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\EAP\4`
- `0x1800438b4`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\EAP\4`
- `0x18004371c`: `%SystemRoot%\System32\Raschap.dll`
- `0x1800436a6`: `PerPolicyConfig`
- `0x180043837`: `Successfully enabled EAP-MD5 during migration`
- `0x180043885`: `Failed to enable EAP-MD5 during migration`

## pseudocode

```c
LSTATUS EnableEapMD5Support()
{
  LSTATUS v0; // ebx
  unsigned __int64 v1; // rdi
  LSTATUS v2; // eax
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  int v5; // [rsp+54h] [rbp-ACh] BYREF
  int v6; // [rsp+58h] [rbp-A8h] BYREF
  int v7; // [rsp+5Ch] [rbp-A4h] BYREF
  int v8; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp-90h]
  DWORD dwType[2]; // [rsp+78h] [rbp-88h]
  BYTE *lpData; // [rsp+80h] [rbp-80h]
  DWORD cbData[2]; // [rsp+88h] [rbp-78h]
  const wchar_t *v14; // [rsp+90h] [rbp-70h]
  int v15; // [rsp+98h] [rbp-68h]
  int *v16; // [rsp+A0h] [rbp-60h]
  int v17; // [rsp+A8h] [rbp-58h]
  const wchar_t *v18; // [rsp+B0h] [rbp-50h]
  int v19; // [rsp+B8h] [rbp-48h]
  int *v20; // [rsp+C0h] [rbp-40h]
  int v21; // [rsp+C8h] [rbp-38h]
  const wchar_t *v22; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+D8h] [rbp-28h]
  int *v24; // [rsp+E0h] [rbp-20h]
  int v25; // [rsp+E8h] [rbp-18h]
  const wchar_t *v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+F8h] [rbp-8h]
  _OWORD *v28; // [rsp+100h] [rbp+0h]
  int v29; // [rsp+108h] [rbp+8h]
  const wchar_t *v30; // [rsp+110h] [rbp+10h]
  int v31; // [rsp+118h] [rbp+18h]
  _OWORD *v32; // [rsp+120h] [rbp+20h]
  int v33; // [rsp+128h] [rbp+28h]
  _OWORD v34[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v35[4]; // [rsp+150h] [rbp+50h] BYREF
  int v36; // [rsp+190h] [rbp+90h]

  hKey = 0;
  dwDisposition = -2;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\4",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( !v0 && dwDisposition == 1 )
  {
    v1 = 0;
    v36 = *(_DWORD *)L"l";
    lpValueName = L"PerPolicyConfig";
    lpData = (BYTE *)&v5;
    v14 = L"RolesSupported";
    v16 = &v6;
    v18 = L"InvokeUsernameDialog";
    v20 = &v7;
    v22 = L"InvokePasswordDialog";
    v24 = &v8;
    v26 = L"FriendlyName";
    v34[0] = *(_OWORD *)L"MD5-Challenge";
    v28 = v34;
    *(_OWORD *)((char *)v34 + 12) = *(_OWORD *)L"allenge";
    v30 = L"Path";
    v35[0] = *(_OWORD *)L"%SystemRoot%\\System32\\Raschap.dll";
    v35[1] = *(_OWORD *)L"oot%\\System32\\Raschap.dll";
    v32 = v35;
    v35[2] = *(_OWORD *)L"tem32\\Raschap.dll";
    v35[3] = *(_OWORD *)L"schap.dll";
    v5 = 1;
    v6 = 11;
    v7 = 1;
    v8 = 1;
    dwType[0] = 4;
    cbData[0] = 4;
    v15 = 4;
    v17 = 4;
    v19 = 4;
    v21 = 4;
    v23 = 4;
    v25 = 4;
    v27 = 1;
    v29 = 28;
    v31 = 2;
    v33 = 68;
    do
    {
      if ( v1 >= 6 )
        break;
      v2 = RegSetValueExW(
             hKey,
             *(LPCWSTR *)&dwType[8 * v1 - 2],
             0,
             dwType[8 * v1],
             *(const BYTE **)&cbData[8 * v1 - 2],
             cbData[8 * v1]);
      ++v1;
      v0 = v2;
    }
    while ( !v2 );
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Failed to enable EAP-MD5 during migration");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_70cc9e363f77355498ae630336bd681a_Traceguids, "NPSDS");
    }
    return RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\4");
  }
  else
  {
    result = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Successfully enabled EAP-MD5 during migration");
      return WPP_SF_s(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               75,
               &WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
               "NPSDS");
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800435f8  push    rbp
0x1800435fa  push    rbx
0x1800435fb  push    rdi
0x1800435fc  push    r15
0x1800435fe  lea     rbp, [rsp-0B8h]
0x180043606  sub     rsp, 1B8h
0x18004360d  mov     rax, cs:__security_cookie
0x180043614  xor     rax, rsp
0x180043617  mov     [rbp+0D0h+var_30], rax
0x18004361e  lea     rax, [rsp+1D0h+dwDisposition]
0x180043623  mov     [rsp+1D0h+hKey], 0
0x18004362c  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x180043631  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180043638  lea     rax, [rsp+1D0h+hKey]
0x18004363d  mov     [rsp+1D0h+dwDisposition], 0FFFFFFFEh
0x180043645  mov     [rsp+1D0h+phkResult], rax; phkResult
0x18004364a  xor     r9d, r9d; lpClass
0x18004364d  mov     [rsp+1D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180043656  xor     r8d, r8d; Reserved
0x180043659  mov     [rsp+1D0h+samDesired], 2001Fh; samDesired
0x180043661  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043668  mov     [rsp+1D0h+dwOptions], 0; dwOptions
0x180043670  call    cs:__imp_RegCreateKeyExW
0x180043676  mov     ebx, eax
0x180043678  mov     r15d, 4
0x18004367e  test    eax, eax
0x180043680  jnz     loc_1800437F8
0x180043686  cmp     [rsp+1D0h+dwDisposition], 1
0x18004368b  jnz     loc_1800437F8
0x180043691  mov     eax, dword ptr cs:aSystemrootSyst+40h; "l"
0x180043697  xor     edi, edi
0x180043699  movups  xmm0, xmmword ptr cs:aMd5Challenge; "MD5-Challenge"
0x1800436a0  mov     [rbp+0D0h+var_40], eax
0x1800436a6  lea     rax, aPerpolicyconfi; "PerPolicyConfig"
0x1800436ad  movups  xmm1, xmmword ptr cs:aMd5Challenge+0Ch; "allenge"
0x1800436b4  mov     [rsp+1D0h+lpValueName], rax
0x1800436b9  lea     rax, [rsp+1D0h+var_17C]
0x1800436be  mov     [rbp+0D0h+lpData], rax
0x1800436c2  lea     rax, aRolessupported; "RolesSupported"
0x1800436c9  mov     [rbp+0D0h+var_140], rax
0x1800436cd  lea     rax, [rsp+1D0h+var_178]
0x1800436d2  mov     [rbp+0D0h+var_130], rax
0x1800436d6  lea     rax, aInvokeusername; "InvokeUsernameDialog"
0x1800436dd  mov     [rbp+0D0h+var_120], rax
0x1800436e1  lea     rax, [rsp+1D0h+var_174]
0x1800436e6  mov     [rbp+0D0h+var_110], rax
0x1800436ea  lea     rax, aInvokepassword; "InvokePasswordDialog"
0x1800436f1  mov     [rbp+0D0h+var_100], rax
0x1800436f5  lea     rax, [rsp+1D0h+var_170]
0x1800436fa  mov     [rbp+0D0h+var_F0], rax
0x1800436fe  lea     rax, aFriendlyname; "FriendlyName"
0x180043705  mov     [rbp+0D0h+var_E0], rax
0x180043709  lea     rax, [rbp+0D0h+var_A0]
0x18004370d  movups  xmmword ptr [rbp+0D0h+var_A0], xmm0
0x180043711  mov     [rbp+0D0h+var_D0], rax
0x180043715  lea     rax, aPath; "Path"
0x18004371c  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "%SystemRoot%\\System32\\Raschap.dll"
0x180043723  movups  xmmword ptr [rbp+0D0h+var_A0+0Ch], xmm1
0x180043727  mov     [rbp+0D0h+var_C0], rax
0x18004372b  lea     rax, [rbp+0D0h+var_80]
0x18004372f  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot%\\System32\\Raschap.dll"
0x180043736  movaps  [rbp+0D0h+var_80], xmm0
0x18004373a  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "tem32\\Raschap.dll"
0x180043741  movaps  [rbp+0D0h+var_70], xmm1
0x180043745  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "schap.dll"
0x18004374c  mov     [rbp+0D0h+var_B0], rax
0x180043750  movaps  [rbp+0D0h+var_60], xmm0
0x180043754  movaps  [rbp+0D0h+var_50], xmm1
0x18004375b  mov     [rsp+1D0h+var_17C], 1
0x180043763  mov     [rsp+1D0h+var_178], 0Bh
0x18004376b  mov     [rsp+1D0h+var_174], 1
0x180043773  mov     [rsp+1D0h+var_170], 1
0x18004377b  mov     [rsp+1D0h+dwType], r15d
0x180043780  mov     [rbp+0D0h+cbData], r15d
0x180043784  mov     [rbp+0D0h+var_138], r15d
0x180043788  mov     [rbp+0D0h+var_128], r15d
0x18004378c  mov     [rbp+0D0h+var_118], r15d
0x180043790  mov     [rbp+0D0h+var_108], r15d
0x180043794  mov     [rbp+0D0h+var_F8], r15d
0x180043798  mov     [rbp+0D0h+var_E8], r15d
0x18004379c  mov     [rbp+0D0h+var_D8], 1
0x1800437a3  mov     [rbp+0D0h+var_C8], 1Ch
0x1800437aa  mov     [rbp+0D0h+var_B8], 2
0x1800437b1  mov     [rbp+0D0h+var_A8], 44h ; 'D'
0x1800437b8  cmp     rdi, 6
0x1800437bc  jnb     short loc_1800437F8
0x1800437be  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800437c3  mov     rdx, rdi
0x1800437c6  shl     rdx, 5
0x1800437ca  xor     r8d, r8d; Reserved
0x1800437cd  mov     eax, [rbp+rdx+0D0h+cbData]
0x1800437d1  mov     r9d, [rsp+rdx+1D0h+dwType]; dwType
0x1800437d6  mov     [rsp+1D0h+samDesired], eax; cbData
0x1800437da  mov     rax, [rbp+rdx+0D0h+lpData]
0x1800437df  mov     rdx, [rsp+rdx+1D0h+lpValueName]; lpValueName
0x1800437e4  mov     qword ptr [rsp+1D0h+dwOptions], rax; lpData
0x1800437e9  call    cs:__imp_RegSetValueExW
0x1800437ef  inc     rdi
0x1800437f2  mov     ebx, eax
0x1800437f4  test    eax, eax
0x1800437f6  jz      short loc_1800437B8
0x1800437f8  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800437fd  test    rcx, rcx
0x180043800  jz      short loc_180043808
0x180043802  call    cs:__imp_RegCloseKey
0x180043808  test    ebx, ebx
0x18004380a  jnz     short loc_180043866
0x18004380c  mov     rax, cs:WPP_GLOBAL_Control
0x180043813  lea     rcx, WPP_GLOBAL_Control
0x18004381a  cmp     rax, rcx
0x18004381d  jz      loc_1800438C8
0x180043823  cmp     [rax+19h], r15b
0x180043827  jb      loc_1800438C8
0x18004382d  test    byte ptr [rax+1Ch], 10h
0x180043831  jz      loc_1800438C8
0x180043837  lea     rcx, aSuccessfullyEn; "Successfully enabled EAP-MD5 during mig"...
0x18004383e  call    WppDbgPrint
0x180043843  mov     rcx, cs:WPP_GLOBAL_Control
0x18004384a  lea     edx, [rbx+4Bh]
0x18004384d  lea     r9, aNpsds; "NPSDS"
0x180043854  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x18004385b  mov     rcx, [rcx+10h]
0x18004385f  call    WPP_SF_s
0x180043864  jmp     short loc_1800438C8
0x180043866  mov     rax, cs:WPP_GLOBAL_Control
0x18004386d  lea     rcx, WPP_GLOBAL_Control
0x180043874  cmp     rax, rcx
0x180043877  jz      short loc_1800438B4
0x180043879  cmp     byte ptr [rax+19h], 2
0x18004387d  jb      short loc_1800438B4
0x18004387f  test    byte ptr [rax+1Ch], 10h
0x180043883  jz      short loc_1800438B4
0x180043885  lea     rcx, aFailedToEnable; "Failed to enable EAP-MD5 during migrati"...
0x18004388c  call    WppDbgPrint
0x180043891  mov     rcx, cs:WPP_GLOBAL_Control
0x180043898  lea     r9, aNpsds; "NPSDS"
0x18004389f  mov     edx, 4Ch ; 'L'
0x1800438a4  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x1800438ab  mov     rcx, [rcx+10h]
0x1800438af  call    WPP_SF_s
0x1800438b4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800438bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800438c2  call    cs:__imp_RegDeleteKeyW
0x1800438c8  mov     rcx, [rbp+0D0h+var_30]
0x1800438cf  xor     rcx, rsp; StackCookie
0x1800438d2  call    __security_check_cookie
0x1800438d7  add     rsp, 1B8h
0x1800438de  pop     r15
0x1800438e0  pop     rdi
0x1800438e1  pop     rbx
0x1800438e2  pop     rbp
0x1800438e3  retn
```
