# HrRegisterWizardFactoryComponent(_GUID const *,tagXW_COMPONENT_TYPE,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void * const)

- ea: `0x18000bac8`
- end: `0x18000c23a`
- name: `?HrRegisterWizardFactoryComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@0PEBG222KQEAX@Z`
- size: `1906`
- prototype: `__int64 __fastcall(const GUID *, int, const GUID *, const WCHAR *, BYTE *, BYTE *, BYTE *, DWORD dwProcessId, HANDLE hSourceHandle)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006b80`
- `0x180006d80`
- `0x180007120`

## callees

- `0x180007820`
- `0x180007a00`
- `0x180007a84`
- `0x1800095a0`
- `0x180009994`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ace0`
- `0x18000af74`
- `0x18000bac8`
- `0x18000e8bc`
- `0x18000ff64`
- `0x180010400`
- `0x18001250c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bbc5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bbdc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bbc5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bbdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bc95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000bc95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdd0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bd78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000beb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bf49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bfbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c046`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c0db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bd78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000beb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bf49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bfbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c046`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c0db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be65`

## string_xrefs

- `0x18000bafc`: `xwizards.dll`
- `0x18000be99`: `Wrapped CLSID`

## pseudocode

```c
__int64 __fastcall HrRegisterWizardFactoryComponent(
        const GUID *a1,
        int a2,
        const GUID *a3,
        const WCHAR *a4,
        BYTE *a5,
        BYTE *a6,
        BYTE *a7,
        DWORD dwProcessId,
        HANDLE hSourceHandle)
{
  const WCHAR *v9; // rsi
  HANDLE v10; // r15
  int FullNonHardCodedPath; // eax
  signed int v14; // ebx
  int v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  BYTE *v18; // r12
  __int64 v19; // r15
  const BYTE *v20; // rcx
  __int64 v21; // rax
  LSTATUS v22; // eax
  _QWORD *v23; // rcx
  int v24; // edx
  int v25; // r9d
  int v26; // eax
  HANDLE v27; // rsi
  __int64 v28; // rax
  LSTATUS v29; // eax
  __int64 v30; // rax
  LSTATUS v31; // eax
  __int64 v32; // rax
  LSTATUS v33; // eax
  __int64 v34; // rax
  LSTATUS v35; // eax
  int v36; // r12d
  LSTATUS v37; // eax
  PVOID *v38; // rcx
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v45; // [rsp+78h] [rbp-88h]
  _BYTE v46[32]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v47[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[104]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR sz[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v50[264]; // [rsp+210h] [rbp+110h] BYREF

  v9 = L"xwizards.dll";
  v10 = hSourceHandle;
  if ( a4 )
    v9 = a4;
  lpData = a5;
  *(_DWORD *)Data = a2;
  v45 = a7;
  hObject = hSourceHandle;
  FullNonHardCodedPath = HrMakeFullNonHardCodedPath(v9, v50, (unsigned int)a3);
  v14 = FullNonHardCodedPath;
  if ( FullNonHardCodedPath >= 0 )
  {
    memset_0(sz, 0, sizeof(sz));
    memset_0(v47, 0, sizeof(v47));
    StringFromGUID2(a1, sz, 40);
    if ( a3 )
      StringFromGUID2(a3, v47, 40);
    SubKey[0] = 0;
    StringCchCopyW(SubKey, 0x66u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
    StringCchCatW(SubKey, 0x66u, L"Factory");
    StringCchCatW(SubKey, 0x66u, &qword_180016C40);
    StringCchCatW(SubKey, 0x66u, sz);
    CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>(v46);
    v15 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v46);
    v14 = v15;
    if ( v15 < 0 )
    {
      v38 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_98:
        CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v46);
        return (unsigned int)v14;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_95:
        if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 0x10) != 0 )
          WPP_SF_D(v38[2], 21, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)v14);
        goto LABEL_98;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
        (unsigned int)SubKey,
        v15);
LABEL_94:
      v38 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_95;
    }
    hKey = 0;
    dwDisposition = 0;
    v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    v14 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v14 = (unsigned __int16)v16 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
          (unsigned int)SubKey,
          v14);
      goto LABEL_88;
    }
    if ( dwDisposition != 1 )
    {
      v14 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
          (unsigned int)SubKey,
          1);
      goto LABEL_18;
    }
    v17 = RegSetValueExW(hKey, L"Class Type", 0, 4u, Data, 4u);
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
          (unsigned int)SubKey,
          v14);
LABEL_18:
      v18 = lpData;
LABEL_30:
      RegCloseKey(hKey);
      hObject = 0;
      if ( v14 < 0 )
        goto LABEL_89;
      v26 = HrDuplicateHandle(v10, dwProcessId, &hObject, v25);
      v27 = hObject;
      v14 = v26;
      if ( v26 >= 0 )
      {
        HrWriteManifestFactoryEntry(sz, v18, v50);
        if ( v47[0] )
          HrWriteManifestWrappedEntry(L"Factory", sz, v47, v27);
      }
      if ( v27 )
        CloseHandle(v27);
LABEL_88:
      if ( v14 >= 0 )
      {
LABEL_90:
        CPXWizardRegistryLockedTransaction<3>::HrRelease(v46);
        goto LABEL_94;
      }
LABEL_89:
      CPXWizardRegistryLockedTransaction<3>::HrRestore(v46);
      goto LABEL_90;
    }
    v19 = -1;
    v20 = (const BYTE *)qword_18001D230[2 * *(int *)Data + 1];
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)&v20[2 * v21] );
    v22 = RegSetValueExW(hKey, L"Class Description", 0, 1u, v20, 2 * v21 + 2);
    v14 = v22;
    if ( v22 > 0 )
      v14 = (unsigned __int16)v22 | 0x80070000;
    if ( v14 >= 0 )
    {
      if ( a3 )
      {
        v28 = -1;
        do
          ++v28;
        while ( v47[v28] );
        v29 = RegSetValueExW(hKey, L"Wrapped CLSID", 0, 1u, (const BYTE *)v47, 2 * v28 + 2);
        v14 = v29;
        if ( v29 > 0 )
          v14 = (unsigned __int16)v29 | 0x80070000;
        if ( v14 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
              (unsigned int)v47,
              (__int64)SubKey,
              v14);
          goto LABEL_28;
        }
      }
      v30 = -1;
      do
        ++v30;
      while ( v50[v30] );
      v31 = RegSetValueExW(hKey, L"File Name", 0, 2u, (const BYTE *)v50, 2 * v30 + 2);
      v14 = v31;
      if ( v31 > 0 )
        v14 = (unsigned __int16)v31 | 0x80070000;
      if ( v14 >= 0 )
      {
        v18 = lpData;
        if ( lpData )
        {
          v32 = -1;
          do
            ++v32;
          while ( *(_WORD *)&lpData[2 * v32] );
          v33 = RegSetValueExW(hKey, 0, 0, 1u, lpData, 2 * v32 + 2);
          v14 = v33;
          if ( v33 > 0 )
            v14 = (unsigned __int16)v33 | 0x80070000;
          if ( v14 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
                (unsigned int)SubKey,
                v14);
            goto LABEL_29;
          }
        }
        if ( a6 )
        {
          v34 = -1;
          do
            ++v34;
          while ( *(_WORD *)&a6[2 * v34] );
          v35 = RegSetValueExW(hKey, L"ProgID", 0, 1u, a6, 2 * v34 + 2);
          v14 = v35;
          if ( v35 > 0 )
            v14 = (unsigned __int16)v35 | 0x80070000;
          if ( v14 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SSD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
                (_DWORD)a6,
                (__int64)SubKey,
                v14);
            goto LABEL_29;
          }
        }
        v36 = (int)v45;
        if ( v45 )
        {
          do
            ++v19;
          while ( *(_WORD *)&v45[2 * v19] );
          v37 = RegSetValueExW(hKey, L"VersionIndependentProgID", 0, 1u, v45, 2 * v19 + 2);
          v14 = v37;
          if ( v37 > 0 )
            v14 = (unsigned __int16)v37 | 0x80070000;
          if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
              v36,
              (__int64)SubKey,
              v14);
          v18 = lpData;
          v10 = hObject;
          goto LABEL_30;
        }
LABEL_28:
        v18 = lpData;
LABEL_29:
        v10 = hObject;
        goto LABEL_30;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_28;
      v24 = 14;
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_28;
      v24 = 12;
    }
    WPP_SF_SD(v23[2], v24, (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)SubKey, v14);
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
      (_DWORD)v9,
      FullNonHardCodedPath);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000bac8  push    rbp
0x18000baca  push    rbx
0x18000bacb  push    rsi
0x18000bacc  push    rdi
0x18000bacd  push    r12
0x18000bacf  push    r13
0x18000bad1  push    r14
0x18000bad3  push    r15
0x18000bad5  lea     rbp, [rsp-338h]
0x18000badd  sub     rsp, 438h
0x18000bae4  mov     rax, cs:__security_cookie
0x18000baeb  xor     rax, rsp
0x18000baee  mov     [rbp+370h+var_50], rax
0x18000baf5  mov     rax, [rbp+370h+arg_20]
0x18000bafc  lea     rsi, aXwizardsDll; "xwizards.dll"
0x18000bb03  mov     r15, [rbp+370h+hSourceHandle]
0x18000bb0a  test    r9, r9
0x18000bb0d  mov     r13, [rbp+370h+arg_28]
0x18000bb14  mov     rdi, rcx
0x18000bb17  cmovnz  rsi, r9
0x18000bb1b  mov     [rsp+470h+lpData], rax
0x18000bb20  mov     rax, [rbp+370h+arg_30]
0x18000bb27  mov     rcx, rsi; lpSrc
0x18000bb2a  mov     dword ptr [rsp+470h+Data], edx
0x18000bb2e  mov     r12, r8
0x18000bb31  lea     rdx, [rbp+370h+var_260]; unsigned __int16 *
0x18000bb38  mov     [rsp+470h+var_3F8], rax
0x18000bb3d  mov     [rsp+470h+hObject], r15
0x18000bb42  call    ?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z; HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)
0x18000bb47  mov     ebx, eax
0x18000bb49  test    eax, eax
0x18000bb4b  jns     short loc_18000BB8F
0x18000bb4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb54  lea     rdi, WPP_GLOBAL_Control
0x18000bb5b  cmp     rcx, rdi
0x18000bb5e  jz      loc_18000C215
0x18000bb64  test    byte ptr [rcx+1Ch], 4
0x18000bb68  jz      loc_18000C215
0x18000bb6e  mov     rcx, [rcx+10h]
0x18000bb72  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000bb79  mov     edx, 0Ah
0x18000bb7e  mov     [rsp+470h+dwOptions], eax
0x18000bb82  mov     r9, rsi
0x18000bb85  call    WPP_SF_SD
0x18000bb8a  jmp     loc_18000C215
0x18000bb8f  mov     ebx, 50h ; 'P'
0x18000bb94  lea     rcx, [rbp+370h+sz]; void *
0x18000bb9b  mov     r8d, ebx; Size
0x18000bb9e  xor     edx, edx; Val
0x18000bba0  call    memset_0
0x18000bba5  mov     r8d, ebx; Size
0x18000bba8  lea     rcx, [rbp+370h+var_3D0]; void *
0x18000bbac  xor     edx, edx; Val
0x18000bbae  call    memset_0
0x18000bbb3  mov     ebx, 28h ; '('
0x18000bbb8  lea     rdx, [rbp+370h+sz]; lpsz
0x18000bbbf  mov     r8d, ebx; cchMax
0x18000bbc2  mov     rcx, rdi; rguid
0x18000bbc5  call    cs:__imp_StringFromGUID2
0x18000bbcb  xor     edi, edi
0x18000bbcd  test    r12, r12
0x18000bbd0  jz      short loc_18000BBE2
0x18000bbd2  mov     r8d, ebx; cchMax
0x18000bbd5  lea     rdx, [rbp+370h+var_3D0]; lpsz
0x18000bbd9  mov     rcx, r12; rguid
0x18000bbdc  call    cs:__imp_StringFromGUID2
0x18000bbe2  mov     ebx, 66h ; 'f'
0x18000bbe7  mov     [rbp+370h+SubKey], di
0x18000bbeb  mov     edx, ebx; unsigned __int64
0x18000bbed  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bbf4  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x18000bbf8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bbfd  lea     r8, aFactory_0; "Factory"
0x18000bc04  mov     edx, ebx; unsigned __int64
0x18000bc06  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x18000bc0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc0f  lea     r8, qword_180016C40; unsigned __int16 *
0x18000bc16  mov     edx, ebx; unsigned __int64
0x18000bc18  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x18000bc1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc21  lea     r8, [rbp+370h+sz]; unsigned __int16 *
0x18000bc28  mov     edx, ebx; unsigned __int64
0x18000bc2a  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x18000bc2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc33  lea     rcx, [rbp+370h+var_3F0]
0x18000bc37  call    ??0?$CPXWizardRegistryLockedTransaction@$01@@QEAA@XZ; CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>(void)
0x18000bc3c  lea     rcx, [rbp+370h+var_3F0]
0x18000bc40  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x18000bc45  lea     r14, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000bc4c  mov     ebx, eax
0x18000bc4e  test    eax, eax
0x18000bc50  js      loc_18000C1B4
0x18000bc56  lea     rax, [rsp+470h+dwDisposition]
0x18000bc5b  mov     [rsp+470h+hKey], rdi
0x18000bc60  mov     [rsp+470h+lpdwDisposition], rax; lpdwDisposition
0x18000bc65  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x18000bc69  lea     rax, [rsp+470h+hKey]
0x18000bc6e  mov     [rsp+470h+dwDisposition], edi
0x18000bc72  mov     [rsp+470h+phkResult], rax; phkResult
0x18000bc77  xor     r9d, r9d; lpClass
0x18000bc7a  mov     [rsp+470h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000bc7f  xor     r8d, r8d; Reserved
0x18000bc82  mov     [rsp+470h+samDesired], 20006h; samDesired
0x18000bc8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc91  mov     [rsp+470h+dwOptions], edi; dwOptions
0x18000bc95  call    cs:__imp_RegCreateKeyExW
0x18000bc9b  mov     ebx, eax
0x18000bc9d  test    eax, eax
0x18000bc9f  jnz     loc_18000C15F
0x18000bca5  lea     eax, [rbx+1]
0x18000bca8  lea     rdi, WPP_GLOBAL_Control
0x18000bcaf  cmp     [rsp+470h+dwDisposition], eax
0x18000bcb3  jnz     loc_18000C135
0x18000bcb9  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bcbe  lea     rax, [rsp+470h+Data]
0x18000bcc3  mov     [rsp+470h+samDesired], 4; cbData
0x18000bccb  lea     r9d, [rbx+4]; dwType
0x18000bccf  xor     r8d, r8d; Reserved
0x18000bcd2  mov     qword ptr [rsp+470h+dwOptions], rax; lpData
0x18000bcd7  lea     rdx, aClassType_0; "Class Type"
0x18000bcde  call    cs:__imp_RegSetValueExW
0x18000bce4  xor     edx, edx
0x18000bce6  mov     esi, 80070000h
0x18000bceb  mov     ebx, eax
0x18000bced  test    eax, eax
0x18000bcef  jle     short loc_18000BCF6
0x18000bcf1  movzx   ebx, ax
0x18000bcf4  or      ebx, esi
0x18000bcf6  test    ebx, ebx
0x18000bcf8  jns     short loc_18000BD2F
0x18000bcfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd01  cmp     rcx, rdi
0x18000bd04  jz      short loc_18000BD25
0x18000bd06  test    byte ptr [rcx+1Ch], 4
0x18000bd0a  jz      short loc_18000BD25
0x18000bd0c  mov     edx, 0Bh
0x18000bd11  mov     [rsp+470h+dwOptions], ebx
0x18000bd15  mov     rcx, [rcx+10h]
0x18000bd19  lea     r9, [rbp+370h+SubKey]
0x18000bd1d  mov     r8, r14
0x18000bd20  call    WPP_SF_SD
0x18000bd25  mov     r12, [rsp+470h+lpData]
0x18000bd2a  jmp     loc_18000BDC8
0x18000bd2f  movsxd  rax, dword ptr [rsp+470h+Data]
0x18000bd34  lea     rcx, qword_18001D230
0x18000bd3b  add     rax, rax
0x18000bd3e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000bd42  mov     rcx, [rcx+rax*8+8]
0x18000bd47  mov     rax, r15
0x18000bd4a  inc     rax
0x18000bd4d  cmp     [rcx+rax*2], dx
0x18000bd51  jnz     short loc_18000BD4A
0x18000bd53  lea     eax, ds:2[rax*2]
0x18000bd5a  mov     r9d, 1; dwType
0x18000bd60  mov     [rsp+470h+samDesired], eax; cbData
0x18000bd64  lea     rdx, aClassDescripti_0; "Class Description"
0x18000bd6b  mov     qword ptr [rsp+470h+dwOptions], rcx; lpData
0x18000bd70  xor     r8d, r8d; Reserved
0x18000bd73  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bd78  call    cs:__imp_RegSetValueExW
0x18000bd7e  xor     ecx, ecx
0x18000bd80  mov     ebx, eax
0x18000bd82  test    eax, eax
0x18000bd84  jle     short loc_18000BD8B
0x18000bd86  movzx   ebx, ax
0x18000bd89  or      ebx, esi
0x18000bd8b  test    ebx, ebx
0x18000bd8d  jns     loc_18000BE70
0x18000bd93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd9a  cmp     rcx, rdi
0x18000bd9d  jz      short loc_18000BDBE
0x18000bd9f  test    byte ptr [rcx+1Ch], 4
0x18000bda3  jz      short loc_18000BDBE
0x18000bda5  mov     edx, 0Ch
0x18000bdaa  mov     rcx, [rcx+10h]
0x18000bdae  lea     r9, [rbp+370h+SubKey]
0x18000bdb2  mov     r8, r14
0x18000bdb5  mov     [rsp+470h+dwOptions], ebx
0x18000bdb9  call    WPP_SF_SD
0x18000bdbe  mov     r12, [rsp+470h+lpData]
0x18000bdc3  mov     r15, [rsp+470h+hObject]
0x18000bdc8  xor     r13d, r13d
0x18000bdcb  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bdd0  call    cs:__imp_RegCloseKey
0x18000bdd6  mov     [rsp+470h+hObject], r13
0x18000bddb  test    ebx, ebx
0x18000bddd  js      loc_18000C1A0
0x18000bde3  mov     edx, [rbp+370h+dwProcessId]; dwProcessId
0x18000bde9  lea     r8, [rsp+470h+hObject]; void **
0x18000bdee  mov     rcx, r15; hSourceHandle
0x18000bdf1  call    ?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z; HrDuplicateHandle(void *,ulong,void * *,int)
0x18000bdf6  mov     rsi, [rsp+470h+hObject]
0x18000bdfb  mov     ebx, eax
0x18000bdfd  test    eax, eax
0x18000bdff  js      short loc_18000BE59
0x18000be01  movsxd  r9, dword ptr [rsp+470h+Data]
0x18000be06  lea     rcx, qword_18001D230
0x18000be0d  mov     rax, r9
0x18000be10  mov     qword ptr [rsp+470h+samDesired], rsi
0x18000be15  add     rax, rax
0x18000be18  lea     r8, [rbp+370h+var_260]
0x18000be1f  mov     rdx, r12
0x18000be22  mov     rax, [rcx+rax*8+8]
0x18000be27  lea     rcx, [rbp+370h+sz]
0x18000be2e  mov     qword ptr [rsp+470h+dwOptions], rax
0x18000be33  call    ?HrWriteManifestFactoryEntry@@YAJQEAG00W4tagXW_COMPONENT_TYPE@@0QEAX@Z; HrWriteManifestFactoryEntry(ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,ushort * const,void * const)
0x18000be38  cmp     [rbp+370h+var_3D0], r13w
0x18000be3d  jz      short loc_18000BE59
0x18000be3f  mov     r9, rsi; void *
0x18000be42  lea     r8, [rbp+370h+var_3D0]; unsigned __int16 *
0x18000be46  lea     rdx, [rbp+370h+sz]; unsigned __int16 *
0x18000be4d  lea     rcx, aFactory_0; "Factory"
0x18000be54  call    ?HrWriteManifestWrappedEntry@@YAJQEAG00QEAX@Z; HrWriteManifestWrappedEntry(ushort * const,ushort * const,ushort * const,void * const)
0x18000be59  test    rsi, rsi
0x18000be5c  jz      loc_18000C19C
0x18000be62  mov     rcx, rsi; hObject
0x18000be65  call    cs:__imp_CloseHandle
0x18000be6b  jmp     loc_18000C19C
0x18000be70  test    r12, r12
0x18000be73  jz      loc_18000BF0A
0x18000be79  lea     rdx, [rbp+370h+var_3D0]
0x18000be7d  mov     rax, r15
0x18000be80  inc     rax
0x18000be83  cmp     [rdx+rax*2], cx
0x18000be87  jnz     short loc_18000BE80
0x18000be89  mov     rcx, [rsp+470h+hKey]; hKey
0x18000be8e  lea     eax, ds:2[rax*2]
0x18000be95  mov     [rsp+470h+samDesired], eax; cbData
0x18000be99  lea     rdx, aWrappedClsid_0; "Wrapped CLSID"
0x18000bea0  lea     rax, [rbp+370h+var_3D0]
0x18000bea4  mov     r9d, 1; dwType
0x18000beaa  xor     r8d, r8d; Reserved
0x18000bead  mov     qword ptr [rsp+470h+dwOptions], rax; lpData
0x18000beb2  call    cs:__imp_RegSetValueExW
0x18000beb8  xor     ecx, ecx
0x18000beba  mov     ebx, eax
0x18000bebc  test    eax, eax
0x18000bebe  jle     short loc_18000BEC5
0x18000bec0  movzx   ebx, ax
0x18000bec3  or      ebx, esi
0x18000bec5  test    ebx, ebx
0x18000bec7  jns     short loc_18000BF0A
0x18000bec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bed0  cmp     rcx, rdi
0x18000bed3  jz      loc_18000BDBE
0x18000bed9  test    byte ptr [rcx+1Ch], 4
0x18000bedd  jz      loc_18000BDBE
0x18000bee3  mov     rcx, [rcx+10h]
0x18000bee7  lea     rax, [rbp+370h+SubKey]
0x18000beeb  mov     edx, 0Dh
0x18000bef0  mov     [rsp+470h+samDesired], ebx
0x18000bef4  lea     r9, [rbp+370h+var_3D0]
0x18000bef8  mov     qword ptr [rsp+470h+dwOptions], rax
0x18000befd  mov     r8, r14
0x18000bf00  call    WPP_SF_SSD
0x18000bf05  jmp     loc_18000BDBE
0x18000bf0a  lea     rdx, [rbp+370h+var_260]
0x18000bf11  mov     rax, r15
0x18000bf14  inc     rax
0x18000bf17  cmp     [rdx+rax*2], cx
0x18000bf1b  jnz     short loc_18000BF14
0x18000bf1d  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bf22  lea     eax, ds:2[rax*2]
0x18000bf29  mov     [rsp+470h+samDesired], eax; cbData
0x18000bf2d  lea     rdx, aFileName_0; "File Name"
0x18000bf34  lea     rax, [rbp+370h+var_260]
0x18000bf3b  mov     r9d, 2; dwType
0x18000bf41  xor     r8d, r8d; Reserved
0x18000bf44  mov     qword ptr [rsp+470h+dwOptions], rax; lpData
0x18000bf49  call    cs:__imp_RegSetValueExW
0x18000bf4f  xor     ecx, ecx
0x18000bf51  mov     ebx, eax
0x18000bf53  test    eax, eax
0x18000bf55  jle     short loc_18000BF5C
0x18000bf57  movzx   ebx, ax
0x18000bf5a  or      ebx, esi
0x18000bf5c  test    ebx, ebx
0x18000bf5e  jns     short loc_18000BF84
0x18000bf60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf67  cmp     rcx, rdi
0x18000bf6a  jz      loc_18000BDBE
0x18000bf70  test    byte ptr [rcx+1Ch], 4
0x18000bf74  jz      loc_18000BDBE
0x18000bf7a  mov     edx, 0Eh
0x18000bf7f  jmp     loc_18000BDAA
0x18000bf84  mov     r12, [rsp+470h+lpData]
0x18000bf89  test    r12, r12
0x18000bf8c  jz      short loc_18000C00A
0x18000bf8e  mov     rax, r15
0x18000bf91  inc     rax
0x18000bf94  cmp     [r12+rax*2], cx
0x18000bf99  jnz     short loc_18000BF91
0x18000bf9b  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bfa0  lea     eax, ds:2[rax*2]
0x18000bfa7  mov     [rsp+470h+samDesired], eax; cbData
0x18000bfab  mov     r9d, 1; dwType
0x18000bfb1  xor     r8d, r8d; Reserved
0x18000bfb4  mov     qword ptr [rsp+470h+dwOptions], r12; lpData
0x18000bfb9  xor     edx, edx; lpValueName
0x18000bfbb  call    cs:__imp_RegSetValueExW
  ... truncated ...
```
