# RegQueryMultiSzValueToStringArray(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,wchar_t * * *,RegistryHiveType)

- ea: `0x180093a60`
- end: `0x180093ced`
- name: `?RegQueryMultiSzValueToStringArray@@YAJPEAUHKEY__@@PEB_W1PEAKPEAPEAPEA_WW4RegistryHiveType@@@Z`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180093f4c`
- `0x1800940b4`

## callees

- `0x180005a00`
- `0x18005d73c`
- `0x180081a38`
- `0x180081adc`
- `0x18008217c`
- `0x180082210`
- `0x180091d18`
- `0x180093a60`
- `0x180094ad8`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093b0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093bd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093b0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093bd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093c26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093c26`

## string_xrefs

- `0x180093b01`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180093bc3`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
__int64 __fastcall RegQueryMultiSzValueToStringArray(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        wchar_t ***a5)
{
  unsigned int v5; // esi
  unsigned int v8; // r14d
  __int64 v9; // rcx
  char *v10; // rbx
  signed int v11; // edi
  LSTATUS v12; // eax
  REGSAM v13; // eax
  char *v14; // r15
  __int64 v15; // rcx
  LSTATUS v16; // eax
  REGSAM v17; // eax
  __int64 v18; // rax
  const wchar_t *v19; // rsi
  const wchar_t *v20; // r15
  __int64 v21; // rax
  wchar_t ***v22; // r8
  wchar_t **v23; // rcx
  REGSAM samDesired; // [rsp+40h] [rbp-40h] BYREF
  wchar_t ***v26; // [rsp+48h] [rbp-38h]
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  void **v28; // [rsp+58h] [rbp-28h] BYREF
  wchar_t **v29; // [rsp+60h] [rbp-20h]
  __int64 v30; // [rsp+68h] [rbp-18h]

  v28 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v5 = 1024;
  v26 = a5;
  v29 = 0;
  *a5 = 0;
  *a4 = 0;
  v30 = 0;
  v8 = 0;
  v10 = (char *)SafeSusAllocArray(0x400u, 2u);
  if ( !v10 )
    goto LABEL_2;
  hKey = 0;
  samDesired = 1;
  v11 = SetRegistryType(v9, &samDesired);
  if ( v11 >= 0 )
  {
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            0,
            samDesired,
            &hKey);
    if ( v12 )
    {
      v11 = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        v11 = v12;
    }
    else
    {
      samDesired = 0;
      v11 = SafeRegQueryValueCchHelper(7, hKey, a3, v10, 1024, &samDesired, 0);
      v13 = samDesired;
      if ( v11 >= 0 )
        v13 = samDesired + 1;
      v5 = v13;
      RegCloseKey(hKey);
    }
  }
  if ( v11 == -2147024662 )
  {
    v14 = (char *)SafeSusAllocArray(v5, 2u);
    SusFree(v10);
    v10 = v14;
    if ( !v14 )
    {
LABEL_2:
      v11 = -2147024882;
      goto LABEL_33;
    }
    hKey = 0;
    samDesired = 1;
    v11 = SetRegistryType(v15, &samDesired);
    if ( v11 >= 0 )
    {
      v16 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
              0,
              samDesired,
              &hKey);
      if ( v16 )
      {
        v11 = (unsigned __int16)v16 | 0x80070000;
        if ( v16 <= 0 )
          v11 = v16;
      }
      else
      {
        samDesired = 0;
        v11 = SafeRegQueryValueCchHelper(7, hKey, a3, v14, v5, &samDesired, 0);
        v17 = samDesired;
        if ( v11 >= 0 )
          v17 = samDesired + 1;
        v5 = v17;
        RegCloseKey(hKey);
      }
    }
  }
  if ( v11 < 0 )
    goto LABEL_32;
  v18 = v5;
  v19 = (const wchar_t *)v10;
  v20 = (const wchar_t *)&v10[2 * v18];
  if ( v10 >= (char *)v20 )
  {
LABEL_30:
    v22 = v26;
    v23 = v29;
    *a4 = v8;
    v11 = CoDuplicateStringArray(v23, v8, v22);
  }
  else
  {
    while ( 1 )
    {
      if ( !*v19 )
      {
LABEL_29:
        v8 = HIDWORD(v30);
        goto LABEL_30;
      }
      hKey = (HKEY)SusStrDup(v19);
      if ( !hKey )
        break;
      v11 = CSusArrayList<CSearchJob *,CSusArrayListItemOpInterfacePtr<CSearchJob *>>::Add(&v28, &hKey, 0);
      if ( v11 < 0 )
        goto LABEL_31;
      v21 = -1;
      do
        ++v21;
      while ( v19[v21] );
      v19 += v21 + 1;
      if ( v19 >= v20 )
        goto LABEL_29;
    }
    v11 = -2147024882;
  }
LABEL_31:
  if ( v10 )
LABEL_32:
    SusFree(v10);
LABEL_33:
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v28);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180093a60  mov     [rsp-38h+arg_0], rbx
0x180093a65  push    rbp
0x180093a66  push    rsi
0x180093a67  push    rdi
0x180093a68  push    r12
0x180093a6a  push    r13
0x180093a6c  push    r14
0x180093a6e  push    r15
0x180093a70  mov     rbp, rsp
0x180093a73  sub     rsp, 80h
0x180093a7a  mov     rax, cs:__security_cookie
0x180093a81  xor     rax, rsp
0x180093a84  mov     [rbp+var_10], rax
0x180093a88  mov     rax, [rbp+arg_20]
0x180093a8c  lea     rcx, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable'
0x180093a93  xor     r15d, r15d
0x180093a96  mov     [rbp+var_28], rcx
0x180093a9a  mov     esi, 400h
0x180093a9f  mov     [rbp+var_38], rax
0x180093aa3  mov     ecx, esi; unsigned __int64
0x180093aa5  mov     [rbp+var_20], r15
0x180093aa9  mov     [rax], r15
0x180093aac  mov     r13, r9
0x180093aaf  lea     edx, [r15+2]; unsigned __int64
0x180093ab3  mov     [r9], r15d
0x180093ab6  mov     r12, r8
0x180093ab9  mov     [rbp+var_18], r15
0x180093abd  mov     r14d, r15d
0x180093ac0  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180093ac5  mov     rbx, rax
0x180093ac8  test    rax, rax
0x180093acb  jnz     short loc_180093AD7
0x180093acd  mov     edi, 8007000Eh
0x180093ad2  jmp     loc_180093CB4
0x180093ad7  lea     rdx, [rbp+samDesired]
0x180093adb  mov     [rbp+hKey], r15
0x180093adf  mov     [rbp+samDesired], 1
0x180093ae6  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180093aeb  mov     edi, eax
0x180093aed  test    eax, eax
0x180093aef  js      short loc_180093B6A
0x180093af1  mov     r9d, [rbp+samDesired]; samDesired
0x180093af5  lea     rax, [rbp+hKey]
0x180093af9  xor     r8d, r8d; ulOptions
0x180093afc  mov     [rsp+80h+phkResult], rax; phkResult
0x180093b01  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180093b08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093b0f  call    cs:__imp_RegOpenKeyExW
0x180093b15  test    eax, eax
0x180093b17  jz      short loc_180093B29
0x180093b19  movzx   edi, ax
0x180093b1c  or      edi, 80070000h
0x180093b22  test    eax, eax
0x180093b24  cmovle  edi, eax
0x180093b27  jmp     short loc_180093B6A
0x180093b29  mov     rdx, [rbp+hKey]
0x180093b2d  lea     rax, [rbp+samDesired]
0x180093b31  mov     [rsp+80h+var_50], r15
0x180093b36  mov     r9, rbx
0x180093b39  mov     [rsp+80h+var_58], rax
0x180093b3e  mov     r8, r12
0x180093b41  mov     ecx, 7
0x180093b46  mov     dword ptr [rsp+80h+phkResult], esi
0x180093b4a  mov     [rbp+samDesired], r15d
0x180093b4e  call    SafeRegQueryValueCchHelper
0x180093b53  mov     edi, eax
0x180093b55  test    eax, eax
0x180093b57  mov     eax, [rbp+samDesired]
0x180093b5a  js      short loc_180093B5E
0x180093b5c  inc     eax
0x180093b5e  mov     rcx, [rbp+hKey]; hKey
0x180093b62  mov     esi, eax
0x180093b64  call    cs:__imp_RegCloseKey
0x180093b6a  cmp     edi, 800700EAh
0x180093b70  jnz     loc_180093C2C
0x180093b76  mov     ecx, esi; unsigned __int64
0x180093b78  mov     edx, 2; unsigned __int64
0x180093b7d  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180093b82  mov     rcx, rbx; lpMem
0x180093b85  mov     r15, rax
0x180093b88  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180093b8d  mov     rbx, r15
0x180093b90  test    r15, r15
0x180093b93  jz      loc_180093ACD
0x180093b99  lea     rdx, [rbp+samDesired]
0x180093b9d  mov     [rbp+hKey], r14
0x180093ba1  mov     [rbp+samDesired], 1
0x180093ba8  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180093bad  mov     edi, eax
0x180093baf  test    eax, eax
0x180093bb1  js      short loc_180093C2C
0x180093bb3  mov     r9d, [rbp+samDesired]; samDesired
0x180093bb7  lea     rax, [rbp+hKey]
0x180093bbb  xor     r8d, r8d; ulOptions
0x180093bbe  mov     [rsp+80h+phkResult], rax; phkResult
0x180093bc3  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180093bca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093bd1  call    cs:__imp_RegOpenKeyExW
0x180093bd7  test    eax, eax
0x180093bd9  jz      short loc_180093BEB
0x180093bdb  movzx   edi, ax
0x180093bde  or      edi, 80070000h
0x180093be4  test    eax, eax
0x180093be6  cmovle  edi, eax
0x180093be9  jmp     short loc_180093C2C
0x180093beb  mov     rdx, [rbp+hKey]
0x180093bef  lea     rax, [rbp+samDesired]
0x180093bf3  mov     [rsp+80h+var_50], r14
0x180093bf8  mov     r9, r15
0x180093bfb  mov     [rsp+80h+var_58], rax
0x180093c00  mov     r8, r12
0x180093c03  mov     ecx, 7
0x180093c08  mov     dword ptr [rsp+80h+phkResult], esi
0x180093c0c  mov     [rbp+samDesired], r14d
0x180093c10  call    SafeRegQueryValueCchHelper
0x180093c15  mov     edi, eax
0x180093c17  test    eax, eax
0x180093c19  mov     eax, [rbp+samDesired]
0x180093c1c  js      short loc_180093C20
0x180093c1e  inc     eax
0x180093c20  mov     rcx, [rbp+hKey]; hKey
0x180093c24  mov     esi, eax
0x180093c26  call    cs:__imp_RegCloseKey
0x180093c2c  test    edi, edi
0x180093c2e  js      short loc_180093CAC
0x180093c30  mov     eax, esi
0x180093c32  mov     rsi, rbx
0x180093c35  lea     r15, [rbx+rax*2]
0x180093c39  cmp     rbx, r15
0x180093c3c  jnb     short loc_180093C91
0x180093c3e  xor     r12d, r12d
0x180093c41  cmp     [rsi], r12w
0x180093c45  jz      short loc_180093C8D
0x180093c47  mov     rcx, rsi; wchar_t *
0x180093c4a  call    ?SusStrDup@@YAPEA_WPEB_W@Z; SusStrDup(wchar_t const *)
0x180093c4f  mov     [rbp+hKey], rax
0x180093c53  test    rax, rax
0x180093c56  jz      loc_180093CE6
0x180093c5c  xor     r8d, r8d
0x180093c5f  lea     rdx, [rbp+hKey]
0x180093c63  lea     rcx, [rbp+var_28]
0x180093c67  call    ?Add@?$CSusArrayList@PEAVCSearchJob@@V?$CSusArrayListItemOpInterfacePtr@PEAVCSearchJob@@@@@@UEAAJAEBQEAVCSearchJob@@PEAK@Z; CSusArrayList<CSearchJob *,CSusArrayListItemOpInterfacePtr<CSearchJob *>>::Add(CSearchJob * const &,ulong *)
0x180093c6c  mov     edi, eax
0x180093c6e  test    eax, eax
0x180093c70  js      short loc_180093CA7
0x180093c72  or      rax, 0FFFFFFFFFFFFFFFFh
0x180093c76  inc     rax
0x180093c79  cmp     [rsi+rax*2], r12w
0x180093c7e  jnz     short loc_180093C76
0x180093c80  lea     rsi, [rsi+rax*2]
0x180093c84  add     rsi, 2
0x180093c88  cmp     rsi, r15
0x180093c8b  jb      short loc_180093C41
0x180093c8d  mov     r14d, dword ptr [rbp+var_18+4]
0x180093c91  mov     r8, [rbp+var_38]; wchar_t ***
0x180093c95  mov     edx, r14d; unsigned int
0x180093c98  mov     rcx, [rbp+var_20]; wchar_t **
0x180093c9c  mov     [r13+0], r14d
0x180093ca0  call    ?CoDuplicateStringArray@@YAJQEAPEA_WIPEAPEAPEA_W@Z; CoDuplicateStringArray(wchar_t * * const,uint,wchar_t * * *)
0x180093ca5  mov     edi, eax
0x180093ca7  test    rbx, rbx
0x180093caa  jz      short loc_180093CB4
0x180093cac  mov     rcx, rbx; lpMem
0x180093caf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180093cb4  lea     rcx, [rbp+var_28]
0x180093cb8  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(void)
0x180093cbd  mov     eax, edi
0x180093cbf  mov     rcx, [rbp+var_10]
0x180093cc3  xor     rcx, rsp; StackCookie
0x180093cc6  call    __security_check_cookie
0x180093ccb  mov     rbx, [rsp+80h+arg_0]
0x180093cd3  add     rsp, 80h
0x180093cda  pop     r15
0x180093cdc  pop     r14
0x180093cde  pop     r13
0x180093ce0  pop     r12
0x180093ce2  pop     rdi
0x180093ce3  pop     rsi
0x180093ce4  pop     rbp
0x180093ce5  retn
0x180093ce6  mov     edi, 8007000Eh
0x180093ceb  jmp     short loc_180093CA7
```
