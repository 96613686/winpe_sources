# HrUnregisterWizardComponentLink(_GUID const *,_GUID const *)

- ea: `0x18000a168`
- end: `0x18000a760`
- name: `?HrUnregisterWizardComponentLink@@YAJPEBU_GUID@@0@Z`
- size: `1528`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ca0`
- `0x18000a768`

## callees

- `0x180007820`
- `0x1800095c0`
- `0x18000a168`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ac34`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1f8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a4bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a515`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a4bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a56e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a65a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a56e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a65a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a557`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a557`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a31e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a584`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a31e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000a584`

## string_xrefs

- `0x18000a21b`: `Components`
- `0x18000a43d`: `Components`

## pseudocode

```c
__int64 __fastcall HrUnregisterWizardComponentLink(GUID *rguid, GUID *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  PVOID *v8; // rcx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  __int64 v13; // rdx
  PVOID *v14; // rcx
  int v15; // edx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[160]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR v22[40]; // [rsp+190h] [rbp+90h] BYREF
  OLECHAR sz[40]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(sz, 0, sizeof(sz));
  memset_0(v22, 0, sizeof(v22));
  hKey = 0;
  phkResult = 0;
  StringFromGUID2(rguid, sz, 40);
  StringFromGUID2(a2, v22, 40);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x9Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x9Du, L"Components");
  StringCchCatW(SubKey, 0x9Du, L"\\");
  StringCchCatW(SubKey, 0x9Du, sz);
  StringCchCatW(SubKey, 0x9Du, L"\\");
  StringCchCatW(SubKey, 0x9Du, L"Parents");
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
  v5 = v4;
  if ( !v4 )
  {
    StringCchCatW(SubKey, 0x9Du, L"\\");
    StringCchCatW(SubKey, 0x9Du, v22);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &phkResult);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 == 2 )
      {
        v5 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            (unsigned int)SubKey,
            1);
      }
      else
      {
        if ( v6 > 0 )
          v5 = (unsigned __int16)v6 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            (unsigned int)SubKey,
            v5);
      }
    }
    else
    {
      v7 = RegDeleteKeyW(hKey, v22);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
    }
    RegCloseKey(hKey);
    goto LABEL_24;
  }
  if ( v4 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        1);
    goto LABEL_26;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
      (unsigned int)SubKey,
      v5);
LABEL_24:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 < 0 )
    goto LABEL_67;
LABEL_26:
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x9Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x9Du, L"Components");
  StringCchCatW(SubKey, 0x9Du, L"\\");
  StringCchCatW(SubKey, 0x9Du, v22);
  StringCchCatW(SubKey, 0x9Du, L"\\");
  StringCchCatW(SubKey, 0x9Du, L"Children");
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
  v5 = v9;
  if ( !v9 )
  {
    StringCchCatW(SubKey, 0x9Du, L"\\");
    StringCchCatW(SubKey, 0x9Du, sz);
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &phkResult);
    v5 = v10;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v5 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            (unsigned int)SubKey,
            1);
        goto LABEL_52;
      }
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_52;
      v15 = 62;
LABEL_51:
      WPP_SF_SD(
        (unsigned int)v14[2],
        v15,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        v5);
      goto LABEL_52;
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    v11 = RegQueryValueExW(phkResult, L"Ordinal", 0, 0, Data, &cbData);
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    RegCloseKey(phkResult);
    if ( v5 < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_39;
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        v5);
    }
    else
    {
      v12 = RegDeleteKeyW(hKey, sz);
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      if ( v5 >= 0 )
      {
        v5 = HrRenumberComponentOrdinalNumbers(v22, v13, *(unsigned int *)Data);
LABEL_52:
        RegCloseKey(hKey);
        goto LABEL_62;
      }
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_39:
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 )
      goto LABEL_52;
    v15 = 60;
    goto LABEL_51;
  }
  if ( v9 == 2 )
  {
    v5 = 1;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_64;
  }
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    goto LABEL_63;
  WPP_SF_SD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    64,
    (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
    (unsigned int)SubKey,
    v5);
LABEL_62:
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
  if ( v5 >= 0 )
  {
LABEL_64:
    if ( v8 == &WPP_GLOBAL_Control )
      return (unsigned int)v5;
    if ( (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_SS(
        (unsigned int)v8[2],
        65,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)v22,
        (__int64)sz);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_67:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    WPP_SF_D(v8[2], 66, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a168  mov     [rsp-8+arg_10], rbx
0x18000a16d  push    rbp
0x18000a16e  push    rsi
0x18000a16f  push    rdi
0x18000a170  push    r12
0x18000a172  push    r15
0x18000a174  lea     rbp, [rsp-140h]
0x18000a17c  sub     rsp, 240h
0x18000a183  mov     rax, cs:__security_cookie
0x18000a18a  xor     rax, rsp
0x18000a18d  mov     [rbp+160h+var_30], rax
0x18000a194  mov     rdi, rdx
0x18000a197  mov     rbx, rcx
0x18000a19a  mov     esi, 50h ; 'P'
0x18000a19f  lea     rcx, [rbp+160h+sz]; void *
0x18000a1a6  mov     r8d, esi; Size
0x18000a1a9  xor     edx, edx; Val
0x18000a1ab  call    memset_0
0x18000a1b0  mov     r8d, esi; Size
0x18000a1b3  lea     rcx, [rbp+160h+var_D0]; void *
0x18000a1ba  xor     edx, edx; Val
0x18000a1bc  call    memset_0
0x18000a1c1  mov     esi, 28h ; '('
0x18000a1c6  mov     [rsp+260h+hKey], 0
0x18000a1cf  mov     r8d, esi; cchMax
0x18000a1d2  mov     [rsp+260h+var_220], 0
0x18000a1db  lea     rdx, [rbp+160h+sz]; lpsz
0x18000a1e2  mov     rcx, rbx; rguid
0x18000a1e5  call    cs:__imp_StringFromGUID2
0x18000a1eb  mov     r8d, esi; cchMax
0x18000a1ee  lea     rdx, [rbp+160h+var_D0]; lpsz
0x18000a1f5  mov     rcx, rdi; rguid
0x18000a1f8  call    cs:__imp_StringFromGUID2
0x18000a1fe  xor     eax, eax
0x18000a200  lea     edi, [rsi+75h]
0x18000a203  mov     edx, edi; unsigned __int64
0x18000a205  mov     [rsp+260h+SubKey], ax
0x18000a20a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a211  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a216  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a21b  lea     r8, aComponents; "Components"
0x18000a222  mov     edx, edi; unsigned __int64
0x18000a224  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a229  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a22e  lea     r8, asc_180016A5C; "\\"
0x18000a235  mov     edx, edi; unsigned __int64
0x18000a237  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a23c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a241  lea     r8, [rbp+160h+sz]; unsigned __int16 *
0x18000a248  mov     edx, edi; unsigned __int64
0x18000a24a  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a24f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a254  lea     r8, asc_180016A5C; "\\"
0x18000a25b  mov     edx, edi; unsigned __int64
0x18000a25d  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a262  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a267  lea     r8, aParents; "Parents"
0x18000a26e  mov     edx, edi; unsigned __int64
0x18000a270  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a275  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a27a  lea     rax, [rsp+260h+hKey]
0x18000a27f  mov     r9d, 20006h; samDesired
0x18000a285  xor     r8d, r8d; ulOptions
0x18000a288  mov     [rsp+260h+phkResult], rax; phkResult
0x18000a28d  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000a292  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a299  call    cs:__imp_RegOpenKeyExW
0x18000a29f  lea     r15d, [rsi-27h]
0x18000a2a3  mov     r12d, 80070000h
0x18000a2a9  lea     rsi, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a2b0  mov     ebx, eax
0x18000a2b2  test    eax, eax
0x18000a2b4  jnz     loc_18000A399
0x18000a2ba  lea     r8, asc_180016A5C; "\\"
0x18000a2c1  mov     edx, edi; unsigned __int64
0x18000a2c3  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a2c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a2cd  lea     r8, [rbp+160h+var_D0]; unsigned __int16 *
0x18000a2d4  mov     edx, edi; unsigned __int64
0x18000a2d6  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a2db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a2e0  lea     rax, [rsp+260h+var_220]
0x18000a2e5  mov     r9d, 2001Fh; samDesired
0x18000a2eb  xor     r8d, r8d; ulOptions
0x18000a2ee  mov     [rsp+260h+phkResult], rax; phkResult
0x18000a2f3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000a2f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a2ff  call    cs:__imp_RegOpenKeyExW
0x18000a305  lea     rdi, WPP_GLOBAL_Control
0x18000a30c  mov     ebx, eax
0x18000a30e  test    eax, eax
0x18000a310  jnz     short loc_18000A332
0x18000a312  mov     rcx, [rsp+260h+hKey]; hKey
0x18000a317  lea     rdx, [rbp+160h+var_D0]; lpSubKey
0x18000a31e  call    cs:__imp_RegDeleteKeyW
0x18000a324  mov     ebx, eax
0x18000a326  test    eax, eax
0x18000a328  jle     short loc_18000A38C
0x18000a32a  movzx   ebx, ax
0x18000a32d  or      ebx, r12d
0x18000a330  jmp     short loc_18000A38C
0x18000a332  cmp     eax, 2
0x18000a335  jnz     short loc_18000A356
0x18000a337  mov     ebx, r15d
0x18000a33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a341  cmp     rcx, rdi
0x18000a344  jz      short loc_18000A38C
0x18000a346  test    byte ptr [rcx+1Ch], 10h
0x18000a34a  jz      short loc_18000A38C
0x18000a34c  lea     edx, [rax+35h]
0x18000a34f  mov     dword ptr [rsp+260h+phkResult], r15d
0x18000a354  jmp     short loc_18000A37B
0x18000a356  test    eax, eax
0x18000a358  jle     short loc_18000A360
0x18000a35a  movzx   ebx, ax
0x18000a35d  or      ebx, r12d
0x18000a360  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a367  cmp     rcx, rdi
0x18000a36a  jz      short loc_18000A38C
0x18000a36c  test    byte ptr [rcx+1Ch], 4
0x18000a370  jz      short loc_18000A38C
0x18000a372  mov     edx, 38h ; '8'
0x18000a377  mov     dword ptr [rsp+260h+phkResult], ebx
0x18000a37b  mov     rcx, [rcx+10h]
0x18000a37f  lea     r9, [rsp+260h+SubKey]
0x18000a384  mov     r8, rsi
0x18000a387  call    WPP_SF_SD
0x18000a38c  mov     rcx, [rsp+260h+hKey]; hKey
0x18000a391  call    cs:__imp_RegCloseKey
0x18000a397  jmp     short loc_18000A40F
0x18000a399  cmp     eax, 2
0x18000a39c  jnz     short loc_18000A3D2
0x18000a39e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3a5  lea     rdi, WPP_GLOBAL_Control
0x18000a3ac  cmp     rcx, rdi
0x18000a3af  jz      short loc_18000A41E
0x18000a3b1  test    byte ptr [rcx+1Ch], 10h
0x18000a3b5  jz      short loc_18000A41E
0x18000a3b7  mov     rcx, [rcx+10h]
0x18000a3bb  lea     edx, [rax+37h]
0x18000a3be  lea     r9, [rsp+260h+SubKey]
0x18000a3c3  mov     dword ptr [rsp+260h+phkResult], r15d
0x18000a3c8  mov     r8, rsi
0x18000a3cb  call    WPP_SF_SD
0x18000a3d0  jmp     short loc_18000A41E
0x18000a3d2  test    eax, eax
0x18000a3d4  jle     short loc_18000A3DC
0x18000a3d6  movzx   ebx, ax
0x18000a3d9  or      ebx, r12d
0x18000a3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3e3  lea     rdi, WPP_GLOBAL_Control
0x18000a3ea  cmp     rcx, rdi
0x18000a3ed  jz      short loc_18000A416
0x18000a3ef  test    byte ptr [rcx+1Ch], 4
0x18000a3f3  jz      short loc_18000A416
0x18000a3f5  mov     rcx, [rcx+10h]
0x18000a3f9  lea     r9, [rsp+260h+SubKey]
0x18000a3fe  mov     edx, 3Ah ; ':'
0x18000a403  mov     dword ptr [rsp+260h+phkResult], ebx
0x18000a407  mov     r8, rsi
0x18000a40a  call    WPP_SF_SD
0x18000a40f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a416  test    ebx, ebx
0x18000a418  js      loc_18000A719
0x18000a41e  xor     eax, eax
0x18000a420  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a427  mov     ebx, 9Dh
0x18000a42c  mov     [rsp+260h+SubKey], ax
0x18000a431  mov     edx, ebx; unsigned __int64
0x18000a433  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a438  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a43d  lea     r8, aComponents; "Components"
0x18000a444  mov     edx, ebx; unsigned __int64
0x18000a446  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a44b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a450  lea     r8, asc_180016A5C; "\\"
0x18000a457  mov     edx, ebx; unsigned __int64
0x18000a459  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a45e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a463  lea     r8, [rbp+160h+var_D0]; unsigned __int16 *
0x18000a46a  mov     edx, ebx; unsigned __int64
0x18000a46c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a471  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a476  lea     r8, asc_180016A5C; "\\"
0x18000a47d  mov     edx, ebx; unsigned __int64
0x18000a47f  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a484  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a489  lea     r8, aChildren; "Children"
0x18000a490  mov     edx, ebx; unsigned __int64
0x18000a492  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a497  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a49c  lea     rax, [rsp+260h+hKey]
0x18000a4a1  mov     r9d, 20006h; samDesired
0x18000a4a7  xor     r8d, r8d; ulOptions
0x18000a4aa  mov     [rsp+260h+phkResult], rax; phkResult
0x18000a4af  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000a4b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a4bb  call    cs:__imp_RegOpenKeyExW
0x18000a4c1  mov     ebx, eax
0x18000a4c3  test    eax, eax
0x18000a4c5  jnz     loc_18000A662
0x18000a4cb  mov     ebx, 9Dh
0x18000a4d0  lea     r8, asc_180016A5C; "\\"
0x18000a4d7  mov     edx, ebx; unsigned __int64
0x18000a4d9  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a4de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4e3  lea     r8, [rbp+160h+sz]; unsigned __int16 *
0x18000a4ea  mov     edx, ebx; unsigned __int64
0x18000a4ec  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000a4f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4f6  lea     rax, [rsp+260h+var_220]
0x18000a4fb  mov     r9d, 2001Fh; samDesired
0x18000a501  xor     r8d, r8d; ulOptions
0x18000a504  mov     [rsp+260h+phkResult], rax; phkResult
0x18000a509  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000a50e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a515  call    cs:__imp_RegOpenKeyExW
0x18000a51b  mov     ebx, eax
0x18000a51d  test    eax, eax
0x18000a51f  jnz     loc_18000A5FB
0x18000a525  mov     rcx, [rsp+260h+var_220]; hKey
0x18000a52a  lea     rdx, aOrdinal; "Ordinal"
0x18000a531  mov     dword ptr [rsp+260h+Data], eax
0x18000a535  xor     r9d, r9d; lpType
0x18000a538  lea     rax, [rsp+260h+cbData]
0x18000a53d  mov     [rsp+260h+cbData], 4
0x18000a545  mov     [rsp+260h+lpcbData], rax; lpcbData
0x18000a54a  xor     r8d, r8d; lpReserved
0x18000a54d  lea     rax, [rsp+260h+Data]
0x18000a552  mov     [rsp+260h+phkResult], rax; lpData
0x18000a557  call    cs:__imp_RegQueryValueExW
0x18000a55d  mov     ebx, eax
0x18000a55f  test    eax, eax
0x18000a561  jle     short loc_18000A569
0x18000a563  movzx   ebx, ax
0x18000a566  or      ebx, r12d
0x18000a569  mov     rcx, [rsp+260h+var_220]; hKey
0x18000a56e  call    cs:__imp_RegCloseKey
0x18000a574  test    ebx, ebx
0x18000a576  js      short loc_18000A5B2
0x18000a578  mov     rcx, [rsp+260h+hKey]; hKey
0x18000a57d  lea     rdx, [rbp+160h+sz]; lpSubKey
0x18000a584  call    cs:__imp_RegDeleteKeyW
0x18000a58a  mov     ebx, eax
0x18000a58c  test    eax, eax
0x18000a58e  jle     short loc_18000A596
0x18000a590  movzx   ebx, ax
0x18000a593  or      ebx, r12d
0x18000a596  test    ebx, ebx
0x18000a598  js      short loc_18000A5E2
0x18000a59a  mov     r8d, dword ptr [rsp+260h+Data]
0x18000a59f  lea     rcx, [rbp+160h+var_D0]
0x18000a5a6  call    ?HrRenumberComponentOrdinalNumbers@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@K@Z; HrRenumberComponentOrdinalNumbers(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong)
0x18000a5ab  mov     ebx, eax
0x18000a5ad  jmp     loc_18000A655
0x18000a5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5b9  cmp     rcx, rdi
0x18000a5bc  jz      loc_18000A655
0x18000a5c2  test    byte ptr [rcx+1Ch], 4
0x18000a5c6  jz      short loc_18000A5E9
0x18000a5c8  mov     rcx, [rcx+10h]
0x18000a5cc  lea     r9, [rsp+260h+SubKey]
0x18000a5d1  mov     edx, 3Bh ; ';'
0x18000a5d6  mov     dword ptr [rsp+260h+phkResult], ebx
0x18000a5da  mov     r8, rsi
0x18000a5dd  call    WPP_SF_SD
0x18000a5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5e9  cmp     rcx, rdi
0x18000a5ec  jz      short loc_18000A655
0x18000a5ee  test    byte ptr [rcx+1Ch], 4
0x18000a5f2  jz      short loc_18000A655
0x18000a5f4  mov     edx, 3Ch ; '<'
0x18000a5f9  jmp     short loc_18000A640
0x18000a5fb  cmp     eax, 2
0x18000a5fe  jnz     short loc_18000A61F
0x18000a600  mov     ebx, r15d
0x18000a603  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a60a  cmp     rcx, rdi
0x18000a60d  jz      short loc_18000A655
0x18000a60f  test    byte ptr [rcx+1Ch], 10h
0x18000a613  jz      short loc_18000A655
0x18000a615  lea     edx, [rax+3Bh]
0x18000a618  mov     dword ptr [rsp+260h+phkResult], r15d
0x18000a61d  jmp     short loc_18000A644
0x18000a61f  test    eax, eax
0x18000a621  jle     short loc_18000A629
0x18000a623  movzx   ebx, ax
0x18000a626  or      ebx, r12d
0x18000a629  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a630  cmp     rcx, rdi
0x18000a633  jz      short loc_18000A655
0x18000a635  test    byte ptr [rcx+1Ch], 4
0x18000a639  jz      short loc_18000A655
0x18000a63b  mov     edx, 3Eh ; '>'
0x18000a640  mov     dword ptr [rsp+260h+phkResult], ebx
0x18000a644  mov     rcx, [rcx+10h]
0x18000a648  lea     r9, [rsp+260h+SubKey]
0x18000a64d  mov     r8, rsi
0x18000a650  call    WPP_SF_SD
0x18000a655  mov     rcx, [rsp+260h+hKey]; hKey
  ... truncated ...
```
