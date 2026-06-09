# WlLoadInactivitySettings(_WLSM_GLOBAL_CONTEXT *,_INACTIVITY_SETTINGS *)

- ea: `0x14002c6b0`
- end: `0x14002cf95`
- name: `?WlLoadInactivitySettings@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@PEAU_INACTIVITY_SETTINGS@@@Z`
- size: `2277`
- prototype: `void(struct _WLSM_GLOBAL_CONTEXT *, struct _INACTIVITY_SETTINGS *)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002bcc0`
- `0x14002bf00`
- `0x14002c380`
- `0x14005f964`

## callees

- `0x1400057f4`
- `0x140015260`
- `0x1400155f0`
- `0x1400156c8`
- `0x14001a520`
- `0x140027310`
- `0x14002c6b0`
- `0x14002d330`
- `0x140041c34`
- `0x14004df08`
- `0x140053720`
- `0x1400544e0`
- `0x14005fae4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002cc22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002cc22`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c83e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c8c0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c9d5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002ca57`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002cb7d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c83e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c8c0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002c9d5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002ca57`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14002cb7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c749`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c7d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c96b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cb0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c749`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c7d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c96b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002cb0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c812`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c894`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c90e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c9a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002ca2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002caad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002cb51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c812`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c894`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c90e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002c9a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002ca2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002caad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002cb51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c946`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cbf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e0f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c946`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cbf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002cce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e0f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14002cc3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14002cc3e`

## pseudocode

```c
void __fastcall WlLoadInactivitySettings(struct _WLSM_GLOBAL_CONTEXT *a1, struct _INACTIVITY_SETTINGS *a2)
{
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // r13d
  unsigned int v7; // r14d
  __int64 v8; // rax
  unsigned int v9; // eax
  HKEY v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  CUser *v13; // rcx
  __int64 v14; // rdx
  int Policies; // eax
  CUser *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // ebx
  unsigned int v20; // r13d
  struct _tagEASPolicy *v21; // r14
  CUser *v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // eax
  unsigned int v27; // ecx
  CUser *v28; // rcx
  CUser *v29; // rcx
  DWORD cbData; // [rsp+30h] [rbp-498h] BYREF
  DWORD Type; // [rsp+34h] [rbp-494h] BYREF
  int v32; // [rsp+38h] [rbp-490h]
  HKEY hKey; // [rsp+40h] [rbp-488h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-480h]
  int v35; // [rsp+4Ch] [rbp-47Ch]
  unsigned int v36; // [rsp+50h] [rbp-478h]
  unsigned int v37; // [rsp+54h] [rbp-474h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-470h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-468h] BYREF
  int v40; // [rsp+64h] [rbp-464h]
  struct _tagEASPolicy *v41; // [rsp+68h] [rbp-460h] BYREF
  unsigned __int16 Data[264]; // [rsp+70h] [rbp-458h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp-248h] BYREF

  v4 = 0;
  hKey = 0;
  phkResult = 0;
  v5 = 0;
  v40 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v34 = 0;
  Type = 0;
  cbData = 0;
  memset_0(a2, 0, 0x224u);
  v8 = *((_QWORD *)a1 + 4);
  if ( v8 )
  {
    v10 = *(HKEY *)(v8 + 232);
    phkResult = v10;
LABEL_9:
    if ( RegOpenKeyExW(v10, L"Control Panel\\Desktop", 0, 0x20019u, &hKey) )
      goto LABEL_31;
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"ScreenSaverIsSecure", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      if ( Type == 1 )
      {
        if ( cbData > 2 && !Data[((unsigned __int64)cbData >> 1) - 1] )
        {
          v6 = _o__wtoi(Data);
          v32 = v6;
          v35 = v6;
        }
      }
      else
      {
        if ( Type == 4 )
          v6 = *(_DWORD *)Data;
        v32 = v6;
        v35 = v6;
      }
    }
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"ScreenSaveActive", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      if ( Type == 1 )
      {
        if ( cbData <= 2 || Data[((unsigned __int64)cbData >> 1) - 1] )
          goto LABEL_26;
        v7 = _o__wtoi(Data);
      }
      else if ( Type == 4 )
      {
        v7 = *(_DWORD *)Data;
      }
      v36 = v7;
      v34 = v7;
    }
LABEL_26:
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"SCRNSAVE.EXE", 0, &Type, (LPBYTE)Data, &cbData)
      && Type == 1
      && !Data[((unsigned __int64)cbData >> 1) - 1] )
    {
      StringCchCopyW((unsigned __int16 *)a2 + 6, 0x10Cu, Data);
    }
    RegCloseKey(hKey);
LABEL_31:
    if ( !RegOpenKeyExW(
            phkResult,
            L"Software\\Policies\\Microsoft\\Windows\\Control Panel\\Desktop",
            0,
            0x20019u,
            &hKey) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"ScreenSaverIsSecure", 0, &Type, (LPBYTE)Data, &cbData) )
      {
        if ( Type == 1 )
        {
          if ( cbData > 2 && !Data[((unsigned __int64)cbData >> 1) - 1] )
          {
            v6 = _o__wtoi(Data);
            v32 = v6;
            v35 = v6;
          }
        }
        else
        {
          if ( Type == 4 )
            v6 = *(_DWORD *)Data;
          v32 = v6;
          v35 = v6;
        }
      }
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"ScreenSaveActive", 0, &Type, (LPBYTE)Data, &cbData) )
      {
        if ( Type == 1 )
        {
          if ( cbData > 2 && !Data[((unsigned __int64)cbData >> 1) - 1] )
          {
            v7 = _o__wtoi(Data);
            v34 = v7;
            v36 = v7;
          }
        }
        else
        {
          if ( Type == 4 )
            v7 = *(_DWORD *)Data;
          v34 = v7;
          v36 = v7;
        }
      }
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"SCRNSAVE.EXE", 0, &Type, (LPBYTE)Data, &cbData)
        && Type == 1
        && !Data[((unsigned __int64)cbData >> 1) - 1] )
      {
        StringCchCopyW((unsigned __int16 *)a2 + 6, 0x10Cu, Data);
      }
      RegCloseKey(hKey);
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           0,
           0x20019u,
           &hKey) )
    {
LABEL_69:
      if ( v7 != 1 )
        goto LABEL_84;
      if ( *((_WORD *)a2 + 6) && (unsigned int)_o__wcsicmp((char *)a2 + 12, L"(NONE)") )
      {
        if ( ExpandEnvironmentStringsW((LPCWSTR)a2 + 6, Dst, 0x104u) - 1 <= 0x103 )
        {
          StringCchCopyW((unsigned __int16 *)a2 + 6, 0x10Cu, Dst);
          StringCchCatW((unsigned __int16 *)a2 + 6, 0x10Cu, L" /s");
LABEL_83:
          v4 = 0;
          goto LABEL_84;
        }
        *((_WORD *)a2 + 6) = 0;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_83;
        }
        v14 = 20;
      }
      else
      {
        *((_WORD *)a2 + 6) = 0;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_83;
        }
        v14 = 19;
      }
      WPP_SF_(*((_QWORD *)v13 + 2), v14, WPP_9c18ab671221381626cab8868253e78d_Traceguids);
      goto LABEL_83;
    }
    *((_DWORD *)a2 + 1) = 5;
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"ScreenSaverGracePeriod", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      if ( Type == 1 )
      {
        if ( cbData <= 2 || Data[((unsigned __int64)cbData >> 1) - 1] )
          goto LABEL_62;
        v11 = _o__wtoi(Data);
        goto LABEL_61;
      }
      if ( Type == 4 )
      {
        v11 = *(_DWORD *)Data;
LABEL_61:
        *((_DWORD *)a2 + 1) = v11;
      }
    }
LABEL_62:
    v12 = *((unsigned int *)a2 + 1);
    if ( (unsigned int)v12 > 0x15180 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v12);
      }
      *((_DWORD *)a2 + 1) = 86400;
    }
    RegCloseKey(hKey);
    goto LABEL_69;
  }
  v9 = RegOpenKeyExW(HKEY_USERS, L".DEFAULT", 0, 0x20019u, &phkResult);
  if ( !v9 )
  {
    v5 = 1;
    v40 = 1;
    v10 = phkResult;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v9);
  }
LABEL_84:
  if ( phkResult && v5 )
    RegCloseKey(phkResult);
  v41 = 0;
  v37 = 0;
  v39 = 0;
  Policies = EasEngineGetPolicies(1, 0, 3u, &v39, &v41);
  if ( Policies >= 0 )
  {
    v19 = v39;
    if ( v39 )
    {
      v20 = 0;
      v21 = v41;
      v22 = WPP_GLOBAL_Control;
      do
      {
        v23 = 32LL * v20;
        if ( *(_DWORD *)((char *)v21 + v23) == 7 && *(_WORD *)((char *)v21 + v23 + 8) == 19 )
        {
          v4 = *(_DWORD *)((char *)v21 + v23 + 16);
          if ( v22 != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)v22 + 7) & 0x20000) != 0
            && *((_BYTE *)v22 + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)v22 + 2), 16, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v4);
            v22 = WPP_GLOBAL_Control;
          }
        }
        ++v20;
      }
      while ( v20 < v19 );
      v6 = v32;
    }
    else
    {
      v21 = v41;
    }
    _FreePolicies(v19, v21);
    v7 = v34;
  }
  else if ( Policies == -1073283051 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v17 = 14;
      v18 = 3221684245LL;
LABEL_97:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_9c18ab671221381626cab8868253e78d_Traceguids, v18);
    }
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v17 = 15;
      v18 = (unsigned int)Policies;
      goto LABEL_97;
    }
  }
  CMachine::RegQueryDWORD(
    v16,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
    L"InactivityTimeoutSecs",
    0,
    &v37);
  v26 = v37;
  if ( v4 )
  {
    if ( v37 )
    {
      if ( v4 <= v37 )
        v26 = v4;
    }
    else
    {
      v26 = v4;
    }
  }
  else
  {
    v27 = 0;
    if ( v37 )
      v27 = v37;
    v26 = v27;
  }
  *((_DWORD *)a2 + 2) = v26;
  *(_DWORD *)a2 = v7;
  if ( v26 || v6 )
  {
    if ( v7 == 1 )
    {
      v7 = 4;
      *(_DWORD *)a2 = 4;
    }
    else if ( !v7 || v7 >= 5 )
    {
      v7 = 2;
      *(_DWORD *)a2 = 2;
    }
  }
  if ( !*((_WORD *)a2 + 6) )
  {
    if ( v7 == 1 )
    {
      *(_DWORD *)a2 = 0;
    }
    else if ( v7 == 4 )
    {
      *(_DWORD *)a2 = 2;
    }
  }
  v28 = (CUser *)*((_QWORD *)a1 + 4);
  if ( !v28 || !(unsigned int)CUser::IsLockWorkstationDisabled(v28) )
    goto LABEL_141;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9c18ab671221381626cab8868253e78d_Traceguids);
    v29 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a2 == 2 )
  {
    *(_DWORD *)a2 = 0;
    goto LABEL_141;
  }
  if ( *(_DWORD *)a2 == 4 )
  {
    *(_DWORD *)a2 = 1;
LABEL_141:
    v29 = WPP_GLOBAL_Control;
  }
  if ( v29 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x20000) != 0 && *((_BYTE *)v29 + 25) >= 4u )
    WPP_SF_ddS(*((_QWORD *)v29 + 2), v24, v25, *(_DWORD *)a2, *((_DWORD *)a2 + 1), (__int64)a2 + 12);
}

```

## disassembly

```asm
0x14002c6b0  mov     [rsp+arg_10], rbx
0x14002c6b5  mov     [rsp+arg_18], rsi
0x14002c6ba  push    rdi
0x14002c6bb  push    r12
0x14002c6bd  push    r13
0x14002c6bf  push    r14
0x14002c6c1  push    r15
0x14002c6c3  sub     rsp, 4A0h
0x14002c6ca  mov     rax, cs:__security_cookie
0x14002c6d1  xor     rax, rsp
0x14002c6d4  mov     [rsp+4C8h+var_38], rax
0x14002c6dc  mov     rdi, rdx
0x14002c6df  mov     r15, rcx
0x14002c6e2  xor     esi, esi
0x14002c6e4  mov     [rsp+4C8h+hKey], rsi
0x14002c6e9  mov     [rsp+4C8h+var_470], rsi
0x14002c6ee  mov     ebx, esi
0x14002c6f0  mov     [rsp+4C8h+var_464], ebx
0x14002c6f4  mov     r13d, esi
0x14002c6f7  mov     [rsp+4C8h+var_490], esi
0x14002c6fb  mov     r14d, esi
0x14002c6fe  mov     [rsp+4C8h+var_480], esi
0x14002c702  mov     [rsp+4C8h+Type], esi
0x14002c706  mov     [rsp+4C8h+cbData], esi
0x14002c70a  xor     edx, edx; Val
0x14002c70c  mov     r8d, 224h; Size
0x14002c712  mov     rcx, rdi; void *
0x14002c715  call    memset_0
0x14002c71a  nop
0x14002c71b  mov     rax, [r15+20h]
0x14002c71f  test    rax, rax
0x14002c722  jnz     loc_14002C7AE
0x14002c728  lea     rax, [rsp+4C8h+var_470]
0x14002c72d  mov     [rsp+4C8h+phkResult], rax; phkResult
0x14002c732  mov     r9d, 20019h; samDesired
0x14002c738  xor     r8d, r8d; ulOptions
0x14002c73b  lea     rdx, aDefault; ".DEFAULT"
0x14002c742  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14002c749  call    cs:__imp_RegOpenKeyExW
0x14002c74f  test    eax, eax
0x14002c751  jz      short loc_14002C79E
0x14002c753  lea     r12, WPP_GLOBAL_Control
0x14002c75a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c761  cmp     rcx, r12
0x14002c764  jz      loc_14002CCDA
0x14002c76a  test    dword ptr [rcx+1Ch], 20000h
0x14002c771  jz      loc_14002CCDA
0x14002c777  cmp     byte ptr [rcx+19h], 2
0x14002c77b  jb      loc_14002CCDA
0x14002c781  mov     edx, 11h
0x14002c786  mov     r9d, eax
0x14002c789  lea     r8, WPP_9c18ab671221381626cab8868253e78d_Traceguids
0x14002c790  mov     rcx, [rcx+10h]
0x14002c794  call    WPP_SF_d
0x14002c799  jmp     loc_14002CCDA
0x14002c79e  mov     ebx, 1
0x14002c7a3  mov     [rsp+4C8h+var_464], ebx
0x14002c7a7  mov     rcx, [rsp+4C8h+var_470]
0x14002c7ac  jmp     short loc_14002C7BA
0x14002c7ae  mov     rcx, [rax+0E8h]; hKey
0x14002c7b5  mov     [rsp+4C8h+var_470], rcx
0x14002c7ba  lea     rax, [rsp+4C8h+hKey]
0x14002c7bf  mov     [rsp+4C8h+phkResult], rax; phkResult
0x14002c7c4  mov     r9d, 20019h; samDesired
0x14002c7ca  xor     r8d, r8d; ulOptions
0x14002c7cd  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x14002c7d4  call    cs:__imp_RegOpenKeyExW
0x14002c7da  test    eax, eax
0x14002c7dc  jnz     loc_14002C94C
0x14002c7e2  mov     [rsp+4C8h+cbData], 208h
0x14002c7ea  lea     rax, [rsp+4C8h+cbData]
0x14002c7ef  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002c7f4  lea     rax, [rsp+4C8h+Data]
0x14002c7f9  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002c7fe  lea     r9, [rsp+4C8h+Type]; lpType
0x14002c803  xor     r8d, r8d; lpReserved
0x14002c806  lea     rdx, aScreensaveriss; "ScreenSaverIsSecure"
0x14002c80d  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002c812  call    cs:__imp_RegQueryValueExW
0x14002c818  test    eax, eax
0x14002c81a  jnz     short loc_14002C864
0x14002c81c  mov     eax, [rsp+4C8h+Type]
0x14002c820  cmp     eax, 1
0x14002c823  jnz     short loc_14002C851
0x14002c825  mov     eax, [rsp+4C8h+cbData]
0x14002c829  cmp     eax, 2
0x14002c82c  jbe     short loc_14002C864
0x14002c82e  shr     rax, 1
0x14002c831  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002c837  jnz     short loc_14002C864
0x14002c839  lea     rcx, [rsp+4C8h+Data]
0x14002c83e  call    cs:__imp__o__wtoi
0x14002c844  mov     r13d, eax
0x14002c847  mov     [rsp+4C8h+var_490], eax
0x14002c84b  mov     [rsp+4C8h+var_47C], eax
0x14002c84f  jmp     short loc_14002C864
0x14002c851  cmp     eax, 4
0x14002c854  cmovz   r13d, dword ptr [rsp+4C8h+Data]
0x14002c85a  mov     [rsp+4C8h+var_490], r13d
0x14002c85f  mov     [rsp+4C8h+var_47C], r13d
0x14002c864  mov     [rsp+4C8h+cbData], 208h
0x14002c86c  lea     rax, [rsp+4C8h+cbData]
0x14002c871  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002c876  lea     rax, [rsp+4C8h+Data]
0x14002c87b  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002c880  lea     r9, [rsp+4C8h+Type]; lpType
0x14002c885  xor     r8d, r8d; lpReserved
0x14002c888  lea     rdx, aScreensaveacti; "ScreenSaveActive"
0x14002c88f  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002c894  call    cs:__imp_RegQueryValueExW
0x14002c89a  test    eax, eax
0x14002c89c  jnz     short loc_14002C8DE
0x14002c89e  mov     eax, [rsp+4C8h+Type]
0x14002c8a2  cmp     eax, 1
0x14002c8a5  jnz     short loc_14002C8CB
0x14002c8a7  mov     eax, [rsp+4C8h+cbData]
0x14002c8ab  cmp     eax, 2
0x14002c8ae  jbe     short loc_14002C8DE
0x14002c8b0  shr     rax, 1
0x14002c8b3  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002c8b9  jnz     short loc_14002C8DE
0x14002c8bb  lea     rcx, [rsp+4C8h+Data]
0x14002c8c0  call    cs:__imp__o__wtoi
0x14002c8c6  mov     r14d, eax
0x14002c8c9  jmp     short loc_14002C8D4
0x14002c8cb  cmp     eax, 4
0x14002c8ce  cmovz   r14d, dword ptr [rsp+4C8h+Data]
0x14002c8d4  mov     [rsp+4C8h+var_478], r14d
0x14002c8d9  mov     [rsp+4C8h+var_480], r14d
0x14002c8de  mov     [rsp+4C8h+cbData], 208h
0x14002c8e6  lea     rax, [rsp+4C8h+cbData]
0x14002c8eb  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002c8f0  lea     rax, [rsp+4C8h+Data]
0x14002c8f5  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002c8fa  lea     r9, [rsp+4C8h+Type]; lpType
0x14002c8ff  xor     r8d, r8d; lpReserved
0x14002c902  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x14002c909  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002c90e  call    cs:__imp_RegQueryValueExW
0x14002c914  test    eax, eax
0x14002c916  jnz     short loc_14002C941
0x14002c918  cmp     [rsp+4C8h+Type], 1
0x14002c91d  jnz     short loc_14002C941
0x14002c91f  mov     eax, [rsp+4C8h+cbData]
0x14002c923  shr     rax, 1
0x14002c926  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002c92c  jnz     short loc_14002C941
0x14002c92e  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x14002c932  lea     r8, [rsp+4C8h+Data]; unsigned __int16 *
0x14002c937  mov     edx, 10Ch; unsigned __int64
0x14002c93c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002c941  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002c946  call    cs:__imp_RegCloseKey
0x14002c94c  lea     rax, [rsp+4C8h+hKey]
0x14002c951  mov     [rsp+4C8h+phkResult], rax; phkResult
0x14002c956  mov     r9d, 20019h; samDesired
0x14002c95c  xor     r8d, r8d; ulOptions
0x14002c95f  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x14002c966  mov     rcx, [rsp+4C8h+var_470]; hKey
0x14002c96b  call    cs:__imp_RegOpenKeyExW
0x14002c971  test    eax, eax
0x14002c973  jnz     loc_14002CAEB
0x14002c979  mov     [rsp+4C8h+cbData], 208h
0x14002c981  lea     rax, [rsp+4C8h+cbData]
0x14002c986  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002c98b  lea     rax, [rsp+4C8h+Data]
0x14002c990  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002c995  lea     r9, [rsp+4C8h+Type]; lpType
0x14002c99a  xor     r8d, r8d; lpReserved
0x14002c99d  lea     rdx, aScreensaveriss; "ScreenSaverIsSecure"
0x14002c9a4  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002c9a9  call    cs:__imp_RegQueryValueExW
0x14002c9af  test    eax, eax
0x14002c9b1  jnz     short loc_14002C9FB
0x14002c9b3  mov     eax, [rsp+4C8h+Type]
0x14002c9b7  cmp     eax, 1
0x14002c9ba  jnz     short loc_14002C9E8
0x14002c9bc  mov     eax, [rsp+4C8h+cbData]
0x14002c9c0  cmp     eax, 2
0x14002c9c3  jbe     short loc_14002C9FB
0x14002c9c5  shr     rax, 1
0x14002c9c8  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002c9ce  jnz     short loc_14002C9FB
0x14002c9d0  lea     rcx, [rsp+4C8h+Data]
0x14002c9d5  call    cs:__imp__o__wtoi
0x14002c9db  mov     r13d, eax
0x14002c9de  mov     [rsp+4C8h+var_490], eax
0x14002c9e2  mov     [rsp+4C8h+var_47C], eax
0x14002c9e6  jmp     short loc_14002C9FB
0x14002c9e8  cmp     eax, 4
0x14002c9eb  cmovz   r13d, dword ptr [rsp+4C8h+Data]
0x14002c9f1  mov     [rsp+4C8h+var_490], r13d
0x14002c9f6  mov     [rsp+4C8h+var_47C], r13d
0x14002c9fb  mov     [rsp+4C8h+cbData], 208h
0x14002ca03  lea     rax, [rsp+4C8h+cbData]
0x14002ca08  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002ca0d  lea     rax, [rsp+4C8h+Data]
0x14002ca12  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002ca17  lea     r9, [rsp+4C8h+Type]; lpType
0x14002ca1c  xor     r8d, r8d; lpReserved
0x14002ca1f  lea     rdx, aScreensaveacti; "ScreenSaveActive"
0x14002ca26  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002ca2b  call    cs:__imp_RegQueryValueExW
0x14002ca31  test    eax, eax
0x14002ca33  jnz     short loc_14002CA7D
0x14002ca35  mov     eax, [rsp+4C8h+Type]
0x14002ca39  cmp     eax, 1
0x14002ca3c  jnz     short loc_14002CA6A
0x14002ca3e  mov     eax, [rsp+4C8h+cbData]
0x14002ca42  cmp     eax, 2
0x14002ca45  jbe     short loc_14002CA7D
0x14002ca47  shr     rax, 1
0x14002ca4a  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002ca50  jnz     short loc_14002CA7D
0x14002ca52  lea     rcx, [rsp+4C8h+Data]
0x14002ca57  call    cs:__imp__o__wtoi
0x14002ca5d  mov     r14d, eax
0x14002ca60  mov     [rsp+4C8h+var_480], eax
0x14002ca64  mov     [rsp+4C8h+var_478], eax
0x14002ca68  jmp     short loc_14002CA7D
0x14002ca6a  cmp     eax, 4
0x14002ca6d  cmovz   r14d, dword ptr [rsp+4C8h+Data]
0x14002ca73  mov     [rsp+4C8h+var_480], r14d
0x14002ca78  mov     [rsp+4C8h+var_478], r14d
0x14002ca7d  mov     [rsp+4C8h+cbData], 208h
0x14002ca85  lea     rax, [rsp+4C8h+cbData]
0x14002ca8a  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002ca8f  lea     rax, [rsp+4C8h+Data]
0x14002ca94  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002ca99  lea     r9, [rsp+4C8h+Type]; lpType
0x14002ca9e  xor     r8d, r8d; lpReserved
0x14002caa1  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x14002caa8  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002caad  call    cs:__imp_RegQueryValueExW
0x14002cab3  test    eax, eax
0x14002cab5  jnz     short loc_14002CAE0
0x14002cab7  cmp     [rsp+4C8h+Type], 1
0x14002cabc  jnz     short loc_14002CAE0
0x14002cabe  mov     eax, [rsp+4C8h+cbData]
0x14002cac2  shr     rax, 1
0x14002cac5  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002cacb  jnz     short loc_14002CAE0
0x14002cacd  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x14002cad1  lea     r8, [rsp+4C8h+Data]; unsigned __int16 *
0x14002cad6  mov     edx, 10Ch; unsigned __int64
0x14002cadb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002cae0  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002cae5  call    cs:__imp_RegCloseKey
0x14002caeb  lea     rax, [rsp+4C8h+hKey]
0x14002caf0  mov     [rsp+4C8h+phkResult], rax; phkResult
0x14002caf5  mov     r9d, 20019h; samDesired
0x14002cafb  xor     r8d, r8d; ulOptions
0x14002cafe  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002cb05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002cb0c  call    cs:__imp_RegOpenKeyExW
0x14002cb12  test    eax, eax
0x14002cb14  jnz     loc_14002CBFA
0x14002cb1a  mov     dword ptr [rdi+4], 5
0x14002cb21  mov     [rsp+4C8h+cbData], 208h
0x14002cb29  lea     rax, [rsp+4C8h+cbData]
0x14002cb2e  mov     [rsp+4C8h+lpcbData], rax; lpcbData
0x14002cb33  lea     rax, [rsp+4C8h+Data]
0x14002cb38  mov     [rsp+4C8h+phkResult], rax; lpData
0x14002cb3d  lea     r9, [rsp+4C8h+Type]; lpType
0x14002cb42  xor     r8d, r8d; lpReserved
0x14002cb45  lea     rdx, aScreensavergra; "ScreenSaverGracePeriod"
0x14002cb4c  mov     rcx, [rsp+4C8h+hKey]; hKey
0x14002cb51  call    cs:__imp_RegQueryValueExW
0x14002cb57  test    eax, eax
0x14002cb59  jnz     short loc_14002CB91
0x14002cb5b  mov     eax, [rsp+4C8h+Type]
0x14002cb5f  cmp     eax, 1
0x14002cb62  jnz     short loc_14002CB85
0x14002cb64  mov     eax, [rsp+4C8h+cbData]
0x14002cb68  cmp     eax, 2
0x14002cb6b  jbe     short loc_14002CB91
0x14002cb6d  shr     rax, 1
0x14002cb70  cmp     word ptr [rsp+rax*2+4C8h+var_460+6], 0
0x14002cb76  jnz     short loc_14002CB91
0x14002cb78  lea     rcx, [rsp+4C8h+Data]
0x14002cb7d  call    cs:__imp__o__wtoi
0x14002cb83  jmp     short loc_14002CB8E
0x14002cb85  cmp     eax, 4
0x14002cb88  jnz     short loc_14002CB91
0x14002cb8a  mov     eax, dword ptr [rsp+4C8h+Data]
0x14002cb8e  mov     [rdi+4], eax
0x14002cb91  mov     r9d, [rdi+4]
0x14002cb95  cmp     r9d, 15180h
0x14002cb9c  jbe     short loc_14002CBE6
0x14002cb9e  lea     r12, WPP_GLOBAL_Control
0x14002cba5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cbac  cmp     rcx, r12
0x14002cbaf  jz      short loc_14002CBDD
0x14002cbb1  test    dword ptr [rcx+1Ch], 20000h
0x14002cbb8  jz      short loc_14002CBDD
0x14002cbba  cmp     byte ptr [rcx+19h], 2
0x14002cbbe  jb      short loc_14002CBDD
0x14002cbc0  mov     edx, 12h
0x14002cbc5  mov     dword ptr [rsp+4C8h+phkResult], 15180h
0x14002cbcd  lea     r8, WPP_9c18ab671221381626cab8868253e78d_Traceguids
  ... truncated ...
```
