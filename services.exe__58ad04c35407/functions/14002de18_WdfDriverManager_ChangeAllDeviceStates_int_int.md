# WdfDriverManager::ChangeAllDeviceStates(int,int)

- ea: `0x14002de18`
- end: `0x14002e2b7`
- name: `?ChangeAllDeviceStates@WdfDriverManager@@QEAAKHH@Z`
- size: `1183`
- prototype: `__int64 __fastcall(WdfDriverManager *this, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140089700`

## callees

- `0x140004c58`
- `0x14001f99c`
- `0x140029228`
- `0x14002de18`
- `0x14002e2c0`
- `0x140032c78`
- `0x140043284`
- `0x1400575b0`
- `0x14008973c`
- `0x14008cf38`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002df17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002df7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e03b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002df17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002df7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e03b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e147`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e147`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e161`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e161`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14002e077`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14002e077`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002df08`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002df08`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002df75`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002df75`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002dfe0`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002e1e7`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002dfe0`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002e1e7`
- `DEVOBJ!DevObjGetDeviceInfoListDetail` at `0x14002e00d`
- `DEVOBJ!DevObjGetDeviceInfoListDetail` at `0x14002e00d`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14002e117`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14002e117`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002e212`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002e212`

## pseudocode

```c
__int64 __fastcall WdfDriverManager::ChangeAllDeviceStates(WdfDriverManager *this, int a2, int a3)
{
  int v3; // ebx
  unsigned int v4; // r12d
  int v5; // r13d
  PRPC_ASYNC_STATE v6; // rcx
  __int64 v7; // rdx
  __int64 DeviceInfoList; // rax
  void *v9; // r14
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v11; // rcx
  DWORD v12; // eax
  DWORD DevNode_Status; // eax
  PRPC_ASYNC_STATE v14; // rcx
  __int64 v15; // rdx
  int v16; // r15d
  HKEY v17; // rsi
  LSTATUS v18; // ebx
  WdfDriverManager *v19; // rcx
  WdfDriverManager *v20; // rbx
  __int64 v21; // rdx
  int v23; // eax
  ULONG pulStatus; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulProblemNumber; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  int v27; // [rsp+3Ch] [rbp-C4h]
  int v28; // [rsp+40h] [rbp-C0h]
  unsigned int v29; // [rsp+44h] [rbp-BCh]
  WdfDriverManager *v30; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h] BYREF
  DEVINST dnDevInst[4]; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+78h] [rbp-88h]
  _DWORD v35[140]; // [rsp+90h] [rbp-70h] BYREF

  v28 = a3;
  v3 = a2;
  v26 = a2;
  v30 = this;
  hKey = 0;
  v32 = 0;
  *(_OWORD *)dnDevInst = 0;
  v34 = 0;
  memset(v35, 0, sizeof(v35));
  pulStatus = 0;
  v4 = 0;
  pulProblemNumber = 0;
  v5 = 0;
  v27 = 0;
  if ( v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 5u )
    {
      goto LABEL_11;
    }
    v7 = 95;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 5u )
    {
      goto LABEL_11;
    }
    v7 = 96;
  }
  WPP_SF_(v6->u.APC.hThread, v7, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids);
LABEL_11:
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v9 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 97, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, LastError);
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    return v4;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, 0, 6, 0, 0) )
  {
    v12 = GetLastError();
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 98, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, v12);
    }
    goto LABEL_56;
  }
  LODWORD(v32) = 48;
  v29 = 1;
  if ( !(unsigned int)DevObjEnumDeviceInfo(v9, 0, &v32) )
    goto LABEL_56;
  while ( !*((_BYTE *)DrvMgrExt + 80) )
  {
    v35[0] = 560;
    if ( !(unsigned int)DevObjGetDeviceInfoListDetail(v9, v35) )
    {
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 3u )
      {
        goto LABEL_52;
      }
      DevNode_Status = GetLastError();
      v14 = WPP_GLOBAL_Control;
      v15 = 99;
      goto LABEL_28;
    }
    DevNode_Status = CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst[1], 0);
    if ( DevNode_Status )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 3u )
      {
        goto LABEL_52;
      }
      v15 = 100;
LABEL_28:
      WPP_SF_d(v14->u.APC.hThread, v15, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, DevNode_Status);
      goto LABEL_52;
    }
    v16 = 0;
    if ( v3 )
    {
      if ( (pulStatus & 0x408) != 0 )
      {
        if ( (pulStatus & 0x400) == 0 || pulProblemNumber == 22 || pulProblemNumber == 1 )
          goto LABEL_52;
      }
      else
      {
        v16 = 1;
      }
    }
    else if ( (pulStatus & 0x400) != 0 )
    {
      goto LABEL_52;
    }
    v17 = (HKEY)DevObjOpenDevRegKey(v9, &v32, 1);
    if ( v17 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v18 = RegOpenKeyExW(v17, L"WUDF", 0, 0x20019u, &hKey);
      RegCloseKey(v17);
      if ( v18 )
        goto LABEL_51;
      RegCloseKey(hKey);
      v19 = (WdfDriverManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->u.APC.hThread, 102, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids);
      }
      if ( v16 )
      {
        v20 = v30;
        if ( WdfDriverManager::AddDeviceToTransientStateList(v30, v9, (struct _DO_DEVINFO_DATA *)&v32) )
        {
          ++v4;
          if ( !v28 )
            goto LABEL_54;
        }
        else
        {
          ++v5;
        }
LABEL_51:
        v3 = v26;
        goto LABEL_52;
      }
      v3 = v26;
      if ( v26 )
        v23 = WdfDriverManager::EnableDevice(v19, dnDevInst[1]);
      else
        v23 = WdfDriverManager::DisableDevice(v19, dnDevInst[1]);
      if ( v23 )
      {
        ++v27;
      }
      else
      {
        ++v4;
        if ( !v28 )
          break;
      }
    }
LABEL_52:
    v21 = v29++;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v9, v21, &v32) )
      break;
  }
  v20 = v30;
LABEL_54:
  if ( v5 )
    WdfTransientDevStateMgr::BeginRestartAttempts(*((WdfTransientDevStateMgr **)v20 + 28));
LABEL_56:
  DevObjDestroyDeviceInfoList(v9);
LABEL_57:
  v11 = WPP_GLOBAL_Control;
LABEL_58:
  if ( v11 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&v11->u.NotificationRoutine + 20) & 1) != 0
    && *((_BYTE *)&v11->u.NotificationRoutine + 17) >= 5u )
  {
    WPP_SF_LLL(v11->u.APC.hThread, 103, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x14002de18  push    rbp
0x14002de1a  push    rbx
0x14002de1b  push    rsi
0x14002de1c  push    rdi
0x14002de1d  push    r12
0x14002de1f  push    r13
0x14002de21  push    r14
0x14002de23  push    r15
0x14002de25  lea     rbp, [rsp-1D8h]
0x14002de2d  sub     rsp, 2D8h
0x14002de34  mov     rax, cs:__security_cookie
0x14002de3b  xor     rax, rsp
0x14002de3e  mov     [rbp+210h+var_50], rax
0x14002de45  xorps   xmm0, xmm0
0x14002de48  mov     [rsp+310h+var_2D0], r8d
0x14002de4d  mov     ebx, edx
0x14002de4f  mov     [rsp+310h+var_2D8], edx
0x14002de53  mov     [rsp+310h+var_2C8], rcx
0x14002de58  xor     edx, edx; Val
0x14002de5a  mov     r8d, 230h; Size
0x14002de60  mov     [rsp+310h+hKey], 0
0x14002de69  lea     rcx, [rbp+210h+var_280]; void *
0x14002de6d  movups  [rsp+310h+var_2B8], xmm0
0x14002de72  movups  xmmword ptr [rsp+310h+dnDevInst], xmm0
0x14002de77  movups  [rsp+310h+var_298], xmm0
0x14002de7c  call    memset
0x14002de81  xor     esi, esi
0x14002de83  mov     [rsp+310h+pulStatus], 0
0x14002de8b  xor     r12d, r12d
0x14002de8e  mov     [rsp+310h+pulProblemNumber], 0
0x14002de96  xor     r13d, r13d
0x14002de99  mov     [rsp+310h+var_2D4], esi
0x14002de9d  test    ebx, ebx
0x14002de9f  jz      short loc_14002DEC5
0x14002dea1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002dea8  lea     rdi, WPP_GLOBAL_Control
0x14002deaf  cmp     rcx, rdi
0x14002deb2  jz      short loc_14002DEF9
0x14002deb4  test    byte ptr [rcx+44h], 1
0x14002deb8  jz      short loc_14002DEF9
0x14002deba  cmp     byte ptr [rcx+41h], 5
0x14002debe  jb      short loc_14002DEF9
0x14002dec0  lea     edx, [rsi+5Fh]
0x14002dec3  jmp     short loc_14002DEE9
0x14002dec5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002decc  lea     rdi, WPP_GLOBAL_Control
0x14002ded3  cmp     rcx, rdi
0x14002ded6  jz      short loc_14002DEF9
0x14002ded8  test    byte ptr [rcx+44h], 1
0x14002dedc  jz      short loc_14002DEF9
0x14002dede  cmp     byte ptr [rcx+41h], 5
0x14002dee2  jb      short loc_14002DEF9
0x14002dee4  mov     edx, 60h ; '`'
0x14002dee9  mov     rcx, [rcx+38h]
0x14002deed  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002def4  call    WPP_SF_
0x14002def9  xor     r9d, r9d
0x14002defc  mov     [rsp+310h+phkResult], rsi
0x14002df01  xor     r8d, r8d
0x14002df04  xor     edx, edx
0x14002df06  xor     ecx, ecx
0x14002df08  call    cs:__imp_DevObjCreateDeviceInfoList
0x14002df0e  mov     r14, rax
0x14002df11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002df15  jnz     short loc_14002DF5D
0x14002df17  call    cs:__imp_GetLastError
0x14002df1d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002df24  cmp     rcx, rdi
0x14002df27  jz      loc_14002E252
0x14002df2d  test    byte ptr [rcx+44h], 1
0x14002df31  jz      loc_14002E21F
0x14002df37  cmp     byte ptr [rcx+41h], 3
0x14002df3b  jb      loc_14002E21F
0x14002df41  mov     rcx, [rcx+38h]
0x14002df45  lea     edx, [r14+62h]
0x14002df49  mov     r9d, eax
0x14002df4c  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002df53  call    WPP_SF_d
0x14002df58  jmp     loc_14002E218
0x14002df5d  mov     [rsp+310h+var_2E8], rsi
0x14002df62  mov     r9d, 6
0x14002df68  xor     r8d, r8d
0x14002df6b  mov     [rsp+310h+phkResult], rsi
0x14002df70  xor     edx, edx
0x14002df72  mov     rcx, r14
0x14002df75  call    cs:__imp_DevObjGetClassDevs
0x14002df7b  test    eax, eax
0x14002df7d  jnz     short loc_14002DFC6
0x14002df7f  call    cs:__imp_GetLastError
0x14002df85  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002df8c  cmp     rcx, rdi
0x14002df8f  jz      loc_14002E20F
0x14002df95  test    byte ptr [rcx+44h], 1
0x14002df99  jz      loc_14002E20F
0x14002df9f  cmp     byte ptr [rcx+41h], 3
0x14002dfa3  jb      loc_14002E20F
0x14002dfa9  mov     rcx, [rcx+38h]
0x14002dfad  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002dfb4  mov     edx, 62h ; 'b'
0x14002dfb9  mov     r9d, eax
0x14002dfbc  call    WPP_SF_d
0x14002dfc1  jmp     loc_14002E20F
0x14002dfc6  lea     r8, [rsp+310h+var_2B8]
0x14002dfcb  mov     dword ptr [rsp+310h+var_2B8], 30h ; '0'
0x14002dfd3  xor     edx, edx
0x14002dfd5  mov     [rsp+310h+var_2CC], 1
0x14002dfdd  mov     rcx, r14
0x14002dfe0  call    cs:__imp_DevObjEnumDeviceInfo
0x14002dfe6  test    eax, eax
0x14002dfe8  jz      loc_14002E20F
0x14002dfee  mov     rax, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x14002dff5  cmp     byte ptr [rax+50h], 0
0x14002dff9  jnz     loc_14002E1F5
0x14002dfff  lea     rdx, [rbp+210h+var_280]
0x14002e003  mov     [rbp+210h+var_280], 230h
0x14002e00a  mov     rcx, r14
0x14002e00d  call    cs:__imp_DevObjGetDeviceInfoListDetail
0x14002e013  test    eax, eax
0x14002e015  jnz     short loc_14002E065
0x14002e017  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e01e  cmp     rax, rdi
0x14002e021  jz      loc_14002E1D3
0x14002e027  test    byte ptr [rax+44h], 1
0x14002e02b  jz      loc_14002E1D3
0x14002e031  cmp     byte ptr [rax+41h], 3
0x14002e035  jb      loc_14002E1D3
0x14002e03b  call    cs:__imp_GetLastError
0x14002e041  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e048  mov     edx, 63h ; 'c'
0x14002e04d  mov     rcx, [rcx+38h]
0x14002e051  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002e058  mov     r9d, eax
0x14002e05b  call    WPP_SF_d
0x14002e060  jmp     loc_14002E1D3
0x14002e065  mov     r8d, [rsp+310h+dnDevInst+4]; dnDevInst
0x14002e06a  lea     rdx, [rsp+310h+pulProblemNumber]; pulProblemNumber
0x14002e06f  xor     r9d, r9d; ulFlags
0x14002e072  lea     rcx, [rsp+310h+pulStatus]; pulStatus
0x14002e077  call    cs:__imp_CM_Get_DevNode_Status
0x14002e07d  test    eax, eax
0x14002e07f  jz      short loc_14002E0AC
0x14002e081  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e088  cmp     rcx, rdi
0x14002e08b  jz      loc_14002E1D3
0x14002e091  test    byte ptr [rcx+44h], 1
0x14002e095  jz      loc_14002E1D3
0x14002e09b  cmp     byte ptr [rcx+41h], 3
0x14002e09f  jb      loc_14002E1D3
0x14002e0a5  mov     edx, 64h ; 'd'
0x14002e0aa  jmp     short loc_14002E04D
0x14002e0ac  xor     r15d, r15d
0x14002e0af  test    ebx, ebx
0x14002e0b1  jz      short loc_14002E0EA
0x14002e0b3  test    [rsp+310h+pulStatus], 408h
0x14002e0bb  jz      short loc_14002E0E2
0x14002e0bd  test    [rsp+310h+pulStatus], 400h
0x14002e0c5  jz      loc_14002E1D3
0x14002e0cb  cmp     [rsp+310h+pulProblemNumber], 16h
0x14002e0d0  jz      loc_14002E1D3
0x14002e0d6  cmp     [rsp+310h+pulProblemNumber], 1
0x14002e0db  jnz     short loc_14002E0F8
0x14002e0dd  jmp     loc_14002E1D3
0x14002e0e2  mov     r15d, 1
0x14002e0e8  jmp     short loc_14002E0F8
0x14002e0ea  test    [rsp+310h+pulStatus], 400h
0x14002e0f2  jnz     loc_14002E1D3
0x14002e0f8  xor     r9d, r9d
0x14002e0fb  mov     dword ptr [rsp+310h+var_2E8], 20019h
0x14002e103  lea     rdx, [rsp+310h+var_2B8]
0x14002e108  mov     dword ptr [rsp+310h+phkResult], 1
0x14002e110  mov     rcx, r14
0x14002e113  lea     r8d, [r9+1]
0x14002e117  call    cs:__imp_DevObjOpenDevRegKey
0x14002e11d  mov     rsi, rax
0x14002e120  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002e124  jz      loc_14002E1D3
0x14002e12a  lea     rax, [rsp+310h+hKey]
0x14002e12f  mov     r9d, 20019h; samDesired
0x14002e135  xor     r8d, r8d; ulOptions
0x14002e138  mov     [rsp+310h+phkResult], rax; phkResult
0x14002e13d  lea     rdx, aWudf; "WUDF"
0x14002e144  mov     rcx, rsi; hKey
0x14002e147  call    cs:__imp_RegOpenKeyExW
0x14002e14d  mov     rcx, rsi; hKey
0x14002e150  mov     ebx, eax
0x14002e152  call    cs:__imp_RegCloseKey
0x14002e158  test    ebx, ebx
0x14002e15a  jnz     short loc_14002E1CF
0x14002e15c  mov     rcx, [rsp+310h+hKey]; hKey
0x14002e161  call    cs:__imp_RegCloseKey
0x14002e167  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e16e  cmp     rcx, rdi
0x14002e171  jz      short loc_14002E19F
0x14002e173  test    byte ptr [rcx+44h], 1
0x14002e177  jz      short loc_14002E19F
0x14002e179  cmp     byte ptr [rcx+41h], 5
0x14002e17d  jb      short loc_14002E19F
0x14002e17f  mov     eax, [rsp+310h+pulProblemNumber]
0x14002e183  lea     edx, [rbx+66h]
0x14002e186  mov     r9d, [rsp+310h+pulStatus]
0x14002e18b  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002e192  mov     rcx, [rcx+38h]
0x14002e196  mov     dword ptr [rsp+310h+phkResult], eax
0x14002e19a  call    WPP_SF_Dd
0x14002e19f  test    r15d, r15d
0x14002e1a2  jz      loc_14002E280
0x14002e1a8  mov     rbx, [rsp+310h+var_2C8]
0x14002e1ad  lea     r8, [rsp+310h+var_2B8]; struct _DO_DEVINFO_DATA *
0x14002e1b2  mov     rcx, rbx; this
0x14002e1b5  mov     rdx, r14; void *
0x14002e1b8  call    ?AddDeviceToTransientStateList@WdfDriverManager@@AEAAKPEAXPEAU_DO_DEVINFO_DATA@@@Z; WdfDriverManager::AddDeviceToTransientStateList(void *,_DO_DEVINFO_DATA *)
0x14002e1bd  test    eax, eax
0x14002e1bf  jz      loc_14002E278
0x14002e1c5  inc     r12d
0x14002e1c8  cmp     [rsp+310h+var_2D0], 0
0x14002e1cd  jz      short loc_14002E1FA
0x14002e1cf  mov     ebx, [rsp+310h+var_2D8]
0x14002e1d3  mov     eax, [rsp+310h+var_2CC]
0x14002e1d7  lea     r8, [rsp+310h+var_2B8]
0x14002e1dc  mov     edx, eax
0x14002e1de  mov     rcx, r14
0x14002e1e1  inc     eax
0x14002e1e3  mov     [rsp+310h+var_2CC], eax
0x14002e1e7  call    cs:__imp_DevObjEnumDeviceInfo
0x14002e1ed  test    eax, eax
0x14002e1ef  jnz     loc_14002DFEE
0x14002e1f5  mov     rbx, [rsp+310h+var_2C8]
0x14002e1fa  test    r13d, r13d
0x14002e1fd  jz      short loc_14002E20B
0x14002e1ff  mov     rcx, [rbx+0E0h]; this
0x14002e206  call    ?BeginRestartAttempts@WdfTransientDevStateMgr@@QEAAKXZ; WdfTransientDevStateMgr::BeginRestartAttempts(void)
0x14002e20b  mov     esi, [rsp+310h+var_2D4]
0x14002e20f  mov     rcx, r14
0x14002e212  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14002e218  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e21f  cmp     rcx, rdi; __annotation("TMF:",
0x14002e222  jz      short loc_14002E252
0x14002e224  test    byte ptr [rcx+44h], 1
0x14002e228  jz      short loc_14002E252
0x14002e22a  cmp     byte ptr [rcx+41h], 5
0x14002e22e  jb      short loc_14002E252
0x14002e230  mov     rcx, [rcx+38h]
0x14002e234  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14002e23b  mov     edx, 67h ; 'g'
0x14002e240  mov     dword ptr [rsp+310h+var_2E8], r13d
0x14002e245  mov     r9d, esi
0x14002e248  mov     dword ptr [rsp+310h+phkResult], r12d
0x14002e24d  call    WPP_SF_LLL
0x14002e252  mov     eax, r12d
0x14002e255  mov     rcx, [rbp+210h+var_50]
0x14002e25c  xor     rcx, rsp; StackCookie
0x14002e25f  call    __security_check_cookie
0x14002e264  add     rsp, 2D8h
0x14002e26b  pop     r15
0x14002e26d  pop     r14
0x14002e26f  pop     r13
0x14002e271  pop     r12
0x14002e273  pop     rdi
0x14002e274  pop     rsi
0x14002e275  pop     rbx
0x14002e276  pop     rbp
0x14002e277  retn
0x14002e278  inc     r13d
0x14002e27b  jmp     loc_14002E1CF
0x14002e280  mov     ebx, [rsp+310h+var_2D8]
0x14002e284  mov     edx, [rsp+310h+dnDevInst+4]; unsigned int
0x14002e288  test    ebx, ebx
0x14002e28a  jz      short loc_14002E293
0x14002e28c  call    ?EnableDevice@WdfDriverManager@@AEAAHK@Z; WdfDriverManager::EnableDevice(ulong)
0x14002e291  jmp     short loc_14002E298
0x14002e293  call    ?DisableDevice@WdfDriverManager@@AEAAHK@Z; WdfDriverManager::DisableDevice(ulong)
0x14002e298  test    eax, eax
0x14002e29a  jnz     short loc_14002E2AE
0x14002e29c  inc     r12d
0x14002e29f  cmp     [rsp+310h+var_2D0], eax
0x14002e2a3  jnz     loc_14002E1D3
0x14002e2a9  jmp     loc_14002E1F5
0x14002e2ae  inc     [rsp+310h+var_2D4]
0x14002e2b2  jmp     loc_14002E1D3
```
