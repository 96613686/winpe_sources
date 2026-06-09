# HrUnregisterWizardTypeComponent(tagXW_WIZARD_TYPE)

- ea: `0x18000ca6c`
- end: `0x18000cd13`
- name: `?HrUnregisterWizardTypeComponent@@YAJW4tagXW_WIZARD_TYPE@@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800077d0`

## callees

- `0x180007820`
- `0x180007a00`
- `0x180007a84`
- `0x1800095a0`
- `0x180009994`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000ab24`
- `0x18000c428`
- `0x18000ca6c`
- `0x18000ce04`
- `0x18000f010`
- `0x18001230c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cbb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cbb4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cbcd`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000cbcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrUnregisterWizardTypeComponent(int a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // edx
  int v5; // r8d
  signed int v6; // ebx
  LSTATUS v7; // eax
  int v8; // eax
  PVOID *v9; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[72]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[2]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(Data, 0, 0x20Au);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x47u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x47u, L"Types");
  StringCchCatW(SubKey, 0x47u, L"\\");
  v2 = -1;
  do
    ++v2;
  while ( SubKey[v2] );
  swprintf_sfn(&SubKey[v2], 71 - v2, L"%#0*.*lx");
  CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(v13);
  v3 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v13);
  v6 = v3;
  if ( v3 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    WPP_SF_SLD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, (unsigned int)SubKey, a1, v3);
    goto LABEL_21;
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hKey) )
  {
    v6 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids, 1);
  }
  else
  {
    cbData = 522;
    RegQueryValueExW(hKey, L"File Name", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
    v7 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 < 0 )
      CPXWizardRegistryLockedTransaction<3>::HrRestore(v13);
  }
  CPXWizardRegistryLockedTransaction<3>::HrRelease(v13);
  if ( v6 < 0 || !*(_WORD *)Data || (v8 = HrRegisterOrUnregisterWithCOM((LPCWSTR)Data, 0), v6 = v8, v8 >= 0) )
  {
LABEL_21:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_25;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_LSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids,
      a1,
      (__int64)Data,
      v8);
    goto LABEL_21;
  }
LABEL_22:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    WPP_SF_D(v9[2], 20, &WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids, (unsigned int)v6);
LABEL_25:
  CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ca6c  mov     [rsp-8+arg_8], rbx
0x18000ca71  mov     [rsp-8+arg_10], rsi
0x18000ca76  push    rbp
0x18000ca77  push    rdi
0x18000ca78  push    r14
0x18000ca7a  lea     rbp, [rsp-210h]
0x18000ca82  sub     rsp, 310h
0x18000ca89  mov     rax, cs:__security_cookie
0x18000ca90  xor     rax, rsp
0x18000ca93  mov     [rbp+220h+var_20], rax
0x18000ca9a  mov     esi, ecx
0x18000ca9c  xor     edx, edx; Val
0x18000ca9e  mov     r8d, 20Ah; Size
0x18000caa4  lea     rcx, [rbp+220h+Data]; void *
0x18000caa8  call    memset_0
0x18000caad  xor     r14d, r14d
0x18000cab0  mov     [rsp+320h+SubKey], r14w
0x18000cab6  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cabd  lea     ebx, [r14+47h]
0x18000cac1  mov     edx, ebx; unsigned __int64
0x18000cac3  lea     rcx, [rsp+320h+SubKey]; unsigned __int16 *
0x18000cac8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cacd  lea     r8, aTypes; "Types"
0x18000cad4  mov     edx, ebx; unsigned __int64
0x18000cad6  lea     rcx, [rsp+320h+SubKey]; unsigned __int16 *
0x18000cadb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cae0  lea     r8, asc_180016DB4; "\\"
0x18000cae7  mov     edx, ebx; unsigned __int64
0x18000cae9  lea     rcx, [rsp+320h+SubKey]; unsigned __int16 *
0x18000caee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000caf3  lea     rcx, [rsp+320h+SubKey]
0x18000caf8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cafc  inc     rax
0x18000caff  cmp     [rcx+rax*2], r14w
0x18000cb04  jnz     short loc_18000CAFC
0x18000cb06  sub     rbx, rax
0x18000cb09  lea     rcx, [rsp+320h+SubKey]
0x18000cb0e  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000cb12  mov     dword ptr [rsp+320h+lpcbData], esi
0x18000cb16  mov     r9d, 8
0x18000cb1c  mov     dword ptr [rsp+320h+phkResult], r9d
0x18000cb21  lea     r8, a0Lx; "%#0*.*lx"
0x18000cb28  mov     rdx, rbx; unsigned __int64
0x18000cb2b  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x18000cb30  lea     rcx, [rsp+320h+var_2E0]
0x18000cb35  call    ??0?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(void)
0x18000cb3a  nop
0x18000cb3b  lea     rcx, [rsp+320h+var_2E0]
0x18000cb40  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x18000cb45  mov     ebx, eax
0x18000cb47  test    eax, eax
0x18000cb49  js      loc_18000CC86
0x18000cb4f  mov     [rsp+320h+hKey], r14
0x18000cb54  lea     rax, [rsp+320h+hKey]
0x18000cb59  mov     [rsp+320h+phkResult], rax; phkResult
0x18000cb5e  mov     r9d, 2001Fh; samDesired
0x18000cb64  xor     r8d, r8d; ulOptions
0x18000cb67  lea     rdx, [rsp+320h+SubKey]; lpSubKey
0x18000cb6c  mov     rbx, 0FFFFFFFF80000002h
0x18000cb73  mov     rcx, rbx; hKey
0x18000cb76  call    cs:__imp_RegOpenKeyExW
0x18000cb7c  lea     rdi, WPP_GLOBAL_Control
0x18000cb83  test    eax, eax
0x18000cb85  jnz     short loc_18000CBF2
0x18000cb87  mov     [rsp+320h+cbData], 20Ah
0x18000cb8f  lea     rax, [rsp+320h+cbData]
0x18000cb94  mov     [rsp+320h+lpcbData], rax; lpcbData
0x18000cb99  lea     rax, [rbp+220h+Data]
0x18000cb9d  mov     [rsp+320h+phkResult], rax; lpData
0x18000cba2  xor     r9d, r9d; lpType
0x18000cba5  xor     r8d, r8d; lpReserved
0x18000cba8  lea     rdx, aFileName_1; "File Name"
0x18000cbaf  mov     rcx, [rsp+320h+hKey]; hKey
0x18000cbb4  call    cs:__imp_RegQueryValueExW
0x18000cbba  mov     rcx, [rsp+320h+hKey]; hKey
0x18000cbbf  call    cs:__imp_RegCloseKey
0x18000cbc5  lea     rdx, [rsp+320h+SubKey]; lpSubKey
0x18000cbca  mov     rcx, rbx; hKey
0x18000cbcd  call    cs:__imp_RegDeleteKeyW
0x18000cbd3  mov     ebx, eax
0x18000cbd5  test    eax, eax
0x18000cbd7  jle     short loc_18000CBE2
0x18000cbd9  movzx   ebx, ax
0x18000cbdc  or      ebx, 80070000h
0x18000cbe2  test    ebx, ebx
0x18000cbe4  jns     short loc_18000CC1F
0x18000cbe6  lea     rcx, [rsp+320h+var_2E0]
0x18000cbeb  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRestore(void)
0x18000cbf0  jmp     short loc_18000CC1F
0x18000cbf2  mov     ebx, 1
0x18000cbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbfe  cmp     rcx, rdi
0x18000cc01  jz      short loc_18000CC1F
0x18000cc03  test    byte ptr [rcx+1Ch], 10h
0x18000cc07  jz      short loc_18000CC1F
0x18000cc09  lea     edx, [rbx+10h]
0x18000cc0c  mov     r9d, ebx
0x18000cc0f  lea     r8, WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids
0x18000cc16  mov     rcx, [rcx+10h]
0x18000cc1a  call    WPP_SF_D
0x18000cc1f  lea     rcx, [rsp+320h+var_2E0]
0x18000cc24  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRelease(void)
0x18000cc29  test    ebx, ebx
0x18000cc2b  js      loc_18000CCB5
0x18000cc31  cmp     word ptr [rbp+220h+Data], r14w
0x18000cc36  jz      short loc_18000CCB5
0x18000cc38  xor     edx, edx; int
0x18000cc3a  lea     rcx, [rbp+220h+Data]; lpSrc
0x18000cc3e  call    ?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z; HrRegisterOrUnregisterWithCOM(ushort * const,int)
0x18000cc43  mov     ebx, eax
0x18000cc45  test    eax, eax
0x18000cc47  jns     short loc_18000CCB5
0x18000cc49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc50  cmp     rcx, rdi
0x18000cc53  jz      loc_18000CCE0
0x18000cc59  test    byte ptr [rcx+1Ch], 4
0x18000cc5d  jz      short loc_18000CCBC
0x18000cc5f  mov     edx, 13h
0x18000cc64  mov     dword ptr [rsp+320h+lpcbData], eax
0x18000cc68  lea     rax, [rbp+220h+Data]
0x18000cc6c  mov     [rsp+320h+phkResult], rax
0x18000cc71  mov     r9d, esi
0x18000cc74  lea     r8, WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids
0x18000cc7b  mov     rcx, [rcx+10h]
0x18000cc7f  call    WPP_SF_LSD
0x18000cc84  jmp     short loc_18000CCB5
0x18000cc86  lea     rdi, WPP_GLOBAL_Control
0x18000cc8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc94  cmp     rcx, rdi
0x18000cc97  jz      short loc_18000CCE0
0x18000cc99  test    byte ptr [rcx+1Ch], 4
0x18000cc9d  jz      short loc_18000CCBC
0x18000cc9f  mov     dword ptr [rsp+320h+lpcbData], eax
0x18000cca3  mov     dword ptr [rsp+320h+phkResult], esi
0x18000cca7  lea     r9, [rsp+320h+SubKey]
0x18000ccac  mov     rcx, [rcx+10h]
0x18000ccb0  call    WPP_SF_SLD
0x18000ccb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccbc  cmp     rcx, rdi
0x18000ccbf  jz      short loc_18000CCE0
0x18000ccc1  test    byte ptr [rcx+1Ch], 10h
0x18000ccc5  jz      short loc_18000CCE0
0x18000ccc7  mov     edx, 14h
0x18000cccc  mov     r9d, ebx
0x18000cccf  lea     r8, WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids
0x18000ccd6  mov     rcx, [rcx+10h]
0x18000ccda  call    WPP_SF_D
0x18000ccdf  nop
0x18000cce0  lea     rcx, [rsp+320h+var_2E0]
0x18000cce5  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
0x18000ccea  mov     eax, ebx
0x18000ccec  mov     rcx, [rbp+220h+var_20]
0x18000ccf3  xor     rcx, rsp; StackCookie
0x18000ccf6  call    __security_check_cookie
0x18000ccfb  lea     r11, [rsp+320h+var_10]
0x18000cd03  mov     rbx, [r11+28h]
0x18000cd07  mov     rsi, [r11+30h]
0x18000cd0b  mov     rsp, r11
0x18000cd0e  pop     r14
0x18000cd10  pop     rdi
0x18000cd11  pop     rbp
0x18000cd12  retn
```
