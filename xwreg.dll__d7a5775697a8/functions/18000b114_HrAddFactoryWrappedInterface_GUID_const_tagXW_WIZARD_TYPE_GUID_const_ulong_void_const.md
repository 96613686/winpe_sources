# HrAddFactoryWrappedInterface(_GUID const *,tagXW_WIZARD_TYPE,_GUID const *,ulong,void * const)

- ea: `0x18000b114`
- end: `0x18000b4b1`
- name: `?HrAddFactoryWrappedInterface@@YAJPEBU_GUID@@W4tagXW_WIZARD_TYPE@@0KQEAX@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006a60`

## callees

- `0x180007820`
- `0x180007a00`
- `0x180007a84`
- `0x1800095a0`
- `0x180009994`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000af74`
- `0x18000b114`
- `0x1800102e0`
- `0x18001230c`
- `0x18001250c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b18a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b19a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b18a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b19a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b2c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b2c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b373`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b373`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b30d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b30d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3bf`

## pseudocode

```c
__int64 __fastcall HrAddFactoryWrappedInterface(
        const GUID *a1,
        unsigned int a2,
        const GUID *a3,
        DWORD a4,
        HANDLE hSourceHandle)
{
  __int64 v9; // rsi
  __int64 v10; // rax
  int v11; // eax
  signed int v12; // ebx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  int v17; // eax
  HANDLE v18; // rsi
  PVOID *v19; // rcx
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[24]; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR v25[40]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[136]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR sz[40]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(sz, 0, sizeof(sz));
  memset_0(v25, 0, sizeof(v25));
  StringFromGUID2(a1, sz, 40);
  StringFromGUID2(a3, v25, 40);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x87u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x87u, L"Factory");
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  StringCchCatW(SubKey, 0x87u, sz);
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  StringCchCatW(SubKey, 0x87u, L"Wrapped Interfaces");
  StringCchCatW(SubKey, 0x87u, &qword_180016C40);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( SubKey[v10] );
  swprintf_sfn(&SubKey[v10], 135 - v10, L"%#0*.*lx");
  CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>((__int64)v24);
  v11 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v24);
  v12 = v11;
  if ( v11 >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    v12 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
          (unsigned int)SubKey,
          v12);
      goto LABEL_27;
    }
    v12 = 1;
    if ( dwDisposition == 1 )
    {
      do
        ++v9;
      while ( v25[v9] );
      v14 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)v25, 2 * v9);
      v12 = v14;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      if ( v12 >= 0 )
        goto LABEL_17;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_17;
      v16 = 25;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_17;
      v16 = 26;
    }
    WPP_SF_SD(v15[2], v16, (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)SubKey, v12);
LABEL_17:
    RegCloseKey(hKey);
    hObject = 0;
    if ( v12 < 0 )
      goto LABEL_28;
    v17 = HrDuplicateHandle(hSourceHandle, a4, &hObject);
    v18 = hObject;
    v12 = v17;
    if ( v17 >= 0 )
      HrWriteManifestTypeEntry(sz, v25, a2, hObject);
    if ( v18 )
      CloseHandle(v18);
LABEL_27:
    if ( v12 >= 0 )
    {
LABEL_29:
      CPXWizardRegistryLockedTransaction<3>::HrRelease(v24);
LABEL_33:
      v19 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_34;
    }
LABEL_28:
    CPXWizardRegistryLockedTransaction<3>::HrRestore(v24);
    goto LABEL_29;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
      (unsigned int)SubKey,
      v11);
    goto LABEL_33;
  }
LABEL_34:
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x10) != 0 )
    WPP_SF_D(v19[2], 29, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)v12);
LABEL_37:
  CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v24);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b114  push    rbp
0x18000b116  push    rbx
0x18000b117  push    rsi
0x18000b118  push    rdi
0x18000b119  push    r12
0x18000b11b  push    r13
0x18000b11d  push    r14
0x18000b11f  push    r15
0x18000b121  lea     rbp, [rsp-148h]
0x18000b129  sub     rsp, 248h
0x18000b130  mov     rax, cs:__security_cookie
0x18000b137  xor     rax, rsp
0x18000b13a  mov     [rbp+180h+var_50], rax
0x18000b141  mov     r12, [rbp+180h+hSourceHandle]
0x18000b148  mov     rdi, r8
0x18000b14b  mov     r14d, edx
0x18000b14e  mov     rbx, rcx
0x18000b151  mov     esi, 50h ; 'P'
0x18000b156  lea     rcx, [rbp+180h+sz]; void *
0x18000b15d  mov     r8d, esi; Size
0x18000b160  xor     edx, edx; Val
0x18000b162  mov     r15d, r9d
0x18000b165  call    memset_0
0x18000b16a  mov     r8d, esi; Size
0x18000b16d  lea     rcx, [rbp+180h+var_200]; void *
0x18000b171  xor     edx, edx; Val
0x18000b173  call    memset_0
0x18000b178  mov     esi, 28h ; '('
0x18000b17d  lea     rdx, [rbp+180h+sz]; lpsz
0x18000b184  mov     r8d, esi; cchMax
0x18000b187  mov     rcx, rbx; rguid
0x18000b18a  call    cs:__imp_StringFromGUID2
0x18000b190  mov     r8d, esi; cchMax
0x18000b193  lea     rdx, [rbp+180h+var_200]; lpsz
0x18000b197  mov     rcx, rdi; rguid
0x18000b19a  call    cs:__imp_StringFromGUID2
0x18000b1a0  lea     ebx, [rsi+5Fh]
0x18000b1a3  xor     r13d, r13d
0x18000b1a6  mov     edx, ebx; unsigned __int64
0x18000b1a8  mov     [rbp+180h+SubKey], r13w
0x18000b1ad  lea     r8, aSoftwareMicros_0
0x18000b1b4  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b1b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x18000b1bd  lea     r8, aFactory_0
0x18000b1c4  mov     edx, ebx; unsigned __int64
0x18000b1c6  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b1ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b1cf  lea     rdi, qword_180016C40
0x18000b1d6  mov     edx, ebx; unsigned __int64
0x18000b1d8  mov     r8, rdi; unsigned __int16 *
0x18000b1db  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b1df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b1e4  lea     r8, [rbp+180h+sz]; unsigned __int16 *
0x18000b1eb  mov     edx, ebx; unsigned __int64
0x18000b1ed  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b1f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b1f6  mov     r8, rdi; unsigned __int16 *
0x18000b1f9  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b1fd  mov     edx, ebx; unsigned __int64
0x18000b1ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b204  lea     r8, aWrappedInterfa
0x18000b20b  mov     edx, ebx; unsigned __int64
0x18000b20d  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b211  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b216  mov     r8, rdi; unsigned __int16 *
0x18000b219  lea     rcx, [rbp+180h+SubKey]; unsigned __int16 *
0x18000b21d  mov     edx, ebx; unsigned __int64
0x18000b21f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000b224  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b228  lea     rcx, [rbp+180h+SubKey]
0x18000b22c  mov     rax, rsi
0x18000b22f  inc     rax
0x18000b232  cmp     [rcx+rax*2], r13w
0x18000b237  jnz     short loc_18000B22F
0x18000b239  sub     rbx, rax
0x18000b23c  mov     [rsp+280h+samDesired], r14d
0x18000b241  mov     r9d, 8
0x18000b247  lea     rcx, [rbp+180h+SubKey]
0x18000b24b  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000b24f  mov     [rsp+280h+dwOptions], r9d
0x18000b254  mov     rdx, rbx; unsigned __int64
0x18000b257  lea     r8, a0Lx
0x18000b25e  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ
0x18000b263  lea     rcx, [rsp+280h+var_218]
0x18000b268  call    ??0?$CPXWizardRegistryLockedTransaction@$01@@QEAA@XZ
0x18000b26d  lea     rcx, [rsp+280h+var_218]
0x18000b272  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z
0x18000b277  mov     ebx, eax
0x18000b279  test    eax, eax
0x18000b27b  js      loc_18000B422
0x18000b281  lea     rax, [rsp+280h+dwDisposition]
0x18000b286  mov     [rsp+280h+hKey], r13
0x18000b28b  mov     [rsp+280h+lpdwDisposition], rax; lpdwDisposition
0x18000b290  lea     rdx, [rbp+180h+SubKey]; lpSubKey
0x18000b294  lea     rax, [rsp+280h+hKey]
0x18000b299  mov     [rsp+280h+dwDisposition], r13d
0x18000b29e  mov     [rsp+280h+phkResult], rax; phkResult
0x18000b2a3  xor     r9d, r9d; lpClass
0x18000b2a6  mov     [rsp+280h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18000b2ab  xor     r8d, r8d; Reserved
0x18000b2ae  mov     [rsp+280h+samDesired], 20006h; samDesired
0x18000b2b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b2bd  mov     [rsp+280h+dwOptions], r13d; dwOptions
0x18000b2c2  call    cs:__imp_RegCreateKeyExW
0x18000b2c8  mov     ebx, eax
0x18000b2ca  test    eax, eax
0x18000b2cc  jnz     loc_18000B3C7
0x18000b2d2  lea     ebx, [rax+1]
0x18000b2d5  lea     rdi, WPP_GLOBAL_Control
0x18000b2dc  cmp     [rsp+280h+dwDisposition], ebx
0x18000b2e0  jnz     short loc_18000B33F
0x18000b2e2  lea     rax, [rbp+180h+var_200]
0x18000b2e6  inc     rsi
0x18000b2e9  cmp     [rax+rsi*2], r13w
0x18000b2ee  jnz     short loc_18000B2E6
0x18000b2f0  mov     rcx, [rsp+280h+hKey]; hKey
0x18000b2f5  lea     eax, [rsi+rsi]
0x18000b2f8  mov     [rsp+280h+samDesired], eax; cbData
0x18000b2fc  mov     r9d, ebx; dwType
0x18000b2ff  lea     rax, [rbp+180h+var_200]
0x18000b303  xor     r8d, r8d; Reserved
0x18000b306  xor     edx, edx; lpValueName
0x18000b308  mov     qword ptr [rsp+280h+dwOptions], rax; lpData
0x18000b30d  call    cs:__imp_RegSetValueExW
0x18000b313  mov     ebx, eax
0x18000b315  test    eax, eax
0x18000b317  jle     short loc_18000B322
0x18000b319  movzx   ebx, ax
0x18000b31c  or      ebx, 80070000h
0x18000b322  test    ebx, ebx
0x18000b324  jns     short loc_18000B36E
0x18000b326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b32d  cmp     rcx, rdi
0x18000b330  jz      short loc_18000B36E
0x18000b332  test    byte ptr [rcx+1Ch], 4
0x18000b336  jz      short loc_18000B36E
0x18000b338  mov     edx, 19h
0x18000b33d  jmp     short loc_18000B356
0x18000b33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b346  cmp     rcx, rdi
0x18000b349  jz      short loc_18000B36E
0x18000b34b  test    byte ptr [rcx+1Ch], 10h
0x18000b34f  jz      short loc_18000B36E
0x18000b351  mov     edx, 1Ah
0x18000b356  mov     rcx, [rcx+10h]
0x18000b35a  lea     r9, [rbp+180h+SubKey]
0x18000b35e  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000b365  mov     [rsp+280h+dwOptions], ebx
0x18000b369  call    WPP_SF_SD
0x18000b36e  mov     rcx, [rsp+280h+hKey]; hKey
0x18000b373  call    cs:__imp_RegCloseKey
0x18000b379  mov     [rsp+280h+hObject], r13
0x18000b37e  test    ebx, ebx
0x18000b380  js      loc_18000B40C
0x18000b386  lea     r8, [rsp+280h+hObject]; void **
0x18000b38b  mov     edx, r15d; dwProcessId
0x18000b38e  mov     rcx, r12; hSourceHandle
0x18000b391  call    ?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z
0x18000b396  mov     rsi, [rsp+280h+hObject]
0x18000b39b  mov     ebx, eax
0x18000b39d  test    eax, eax
0x18000b39f  js      short loc_18000B3B7
0x18000b3a1  mov     r9, rsi; void *
0x18000b3a4  lea     rdx, [rbp+180h+var_200]; unsigned __int16 *
0x18000b3a8  mov     r8d, r14d; unsigned int
0x18000b3ab  lea     rcx, [rbp+180h+sz]; unsigned __int16 *
0x18000b3b2  call    ?HrWriteManifestTypeEntry@@YAJQEAG0KQEAX@Z
0x18000b3b7  test    rsi, rsi
0x18000b3ba  jz      short loc_18000B408
0x18000b3bc  mov     rcx, rsi; hObject
0x18000b3bf  call    cs:__imp_CloseHandle
0x18000b3c5  jmp     short loc_18000B408
0x18000b3c7  jle     short loc_18000B3D2
0x18000b3c9  movzx   ebx, ax
0x18000b3cc  or      ebx, 80070000h
0x18000b3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3d9  lea     rdi, WPP_GLOBAL_Control
0x18000b3e0  cmp     rcx, rdi
0x18000b3e3  jz      short loc_18000B408
0x18000b3e5  test    byte ptr [rcx+1Ch], 4
0x18000b3e9  jz      short loc_18000B408
0x18000b3eb  mov     rcx, [rcx+10h]
0x18000b3ef  lea     r9, [rbp+180h+SubKey]
0x18000b3f3  mov     edx, 1Bh
0x18000b3f8  mov     [rsp+280h+dwOptions], ebx
0x18000b3fc  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000b403  call    WPP_SF_SD
0x18000b408  test    ebx, ebx
0x18000b40a  jns     short loc_18000B416
0x18000b40c  lea     rcx, [rsp+280h+var_218]
0x18000b411  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ
0x18000b416  lea     rcx, [rsp+280h+var_218]
0x18000b41b  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ
0x18000b420  jmp     short loc_18000B458
0x18000b422  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b429  lea     rdi, WPP_GLOBAL_Control
0x18000b430  cmp     rcx, rdi
0x18000b433  jz      short loc_18000B482
0x18000b435  test    byte ptr [rcx+1Ch], 4
0x18000b439  jz      short loc_18000B45F
0x18000b43b  mov     rcx, [rcx+10h]
0x18000b43f  lea     r9, [rbp+180h+SubKey]
0x18000b443  mov     edx, 1Ch
0x18000b448  mov     [rsp+280h+dwOptions], eax
0x18000b44c  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000b453  call    WPP_SF_SD
0x18000b458  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b45f  cmp     rcx, rdi
0x18000b462  jz      short loc_18000B482
0x18000b464  test    byte ptr [rcx+1Ch], 10h
0x18000b468  jz      short loc_18000B482
0x18000b46a  mov     rcx, [rcx+10h]
0x18000b46e  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000b475  mov     edx, 1Dh
0x18000b47a  mov     r9d, ebx
0x18000b47d  call    WPP_SF_D
0x18000b482  lea     rcx, [rsp+280h+var_218]
0x18000b487  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ
0x18000b48c  mov     eax, ebx
0x18000b48e  mov     rcx, [rbp+180h+var_50]
0x18000b495  xor     rcx, rsp; StackCookie
0x18000b498  call    __security_check_cookie
0x18000b49d  add     rsp, 248h
0x18000b4a4  pop     r15
0x18000b4a6  pop     r14
0x18000b4a8  pop     r13
0x18000b4aa  pop     r12
0x18000b4ac  pop     rdi
0x18000b4ad  pop     rsi
0x18000b4ae  pop     rbx
0x18000b4af  pop     rbp
0x18000b4b0  retn
```
