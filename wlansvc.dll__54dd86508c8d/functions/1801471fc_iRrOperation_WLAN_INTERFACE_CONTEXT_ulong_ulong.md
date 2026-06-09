# iRrOperation(_WLAN_INTERFACE_CONTEXT *,ulong,ulong)

- ea: `0x1801471fc`
- end: `0x18014795a`
- name: `?iRrOperation@@YAKPEAU_WLAN_INTERFACE_CONTEXT@@KK@Z`
- size: `1886`
- prototype: `unsigned int __fastcall(struct _WLAN_INTERFACE_CONTEXT *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180034040`

## callees

- `0x1800052e0`
- `0x18000aa0c`
- `0x180011530`
- `0x18006c058`
- `0x1800a6f54`
- `0x1800ac8ac`
- `0x180106340`
- `0x180107330`
- `0x180146a98`
- `0x1801471fc`
- `0x180148140`
- `0x180160ae4`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801474ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801474ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147799`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147628`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147661`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147661`
- `RPCRT4!UuidFromStringW` at `0x180147675`
- `RPCRT4!UuidFromStringW` at `0x180147675`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1801475c0`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1801475c0`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1801475ec`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1801475ec`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180147821`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180147821`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801476a8`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801476a8`
- `DEVOBJ!DevObjRestartDevices` at `0x1801476e1`
- `DEVOBJ!DevObjRestartDevices` at `0x1801476e1`
- `DEVOBJ!DevObjGetClassDevs` at `0x180147558`
- `DEVOBJ!DevObjGetClassDevs` at `0x180147558`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801474df`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801474df`

## pseudocode

```c
__int64 __fastcall iRrOperation(PVOID *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int v4; // r15d
  unsigned int v5; // r14d
  PVOID *v6; // r12
  unsigned int v7; // r13d
  char v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // esi
  _DWORD *v11; // rax
  __int64 v12; // r14
  unsigned int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  __int64 DeviceInfoList; // rax
  DWORD LastError; // eax
  __int64 v19; // rdx
  unsigned int v20; // r15d
  __int64 i; // rdx
  HKEY v22; // rbx
  unsigned int v23; // eax
  DWORD v24; // eax
  int v25; // edx
  int v26; // ecx
  int v27; // r8d
  DWORD v28; // eax
  __int64 v29; // rdx
  DWORD v30; // eax
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r9
  int lpcbData; // [rsp+28h] [rbp-D8h]
  BOOL v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v39; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+8Ch] [rbp-74h] BYREF
  _DWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v42; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v43; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v44; // [rsp+A0h] [rbp-60h] BYREF
  int v45; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v46; // [rsp+A8h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v48[3]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 StringUuid[39]; // [rsp+F2h] [rbp-Eh] BYREF
  _BYTE v51[400]; // [rsp+140h] [rbp+40h] BYREF

  v3 = 13;
  v4 = a3;
  v37 = a3;
  v5 = a2;
  v39 = a2;
  v6 = a1;
  v38 = 50;
  v7 = 1;
  if ( (byte_1802A0A43 & 4) != 0 )
  {
    LOBYTE(a3) = 1;
    McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, 1, a2);
  }
  if ( !g_bResetRecoveryForLimitDetection )
  {
    if ( (byte_1802A0A43 & 4) != 0 )
    {
      LOBYTE(a3) = 3;
      McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, 2, 0);
    }
    goto LABEL_6;
  }
  if ( !*((_QWORD *)v6[87] + 87) )
    goto LABEL_6;
  v7 = 3;
  v41[0] = 524672;
  v41[1] = -559038737;
  WlanLogLimitConnectivity(3, a2, v5, v4);
  v9 = (*((__int64 (__fastcall **)(PVOID, _DWORD *))v6[87] + 87))(v6[88], v41);
  v10 = v9;
  v38 = v9;
  v3 = v9;
  if ( (byte_1802A0A43 & 4) != 0 )
  {
    LOBYTE(a3) = 3;
    McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, 6, v9);
  }
  if ( v10 )
  {
LABEL_6:
    if ( g_bNoDisableEnableForLimitDetection )
    {
      if ( (byte_1802A0A43 & 4) != 0 )
      {
        v8 = 2;
LABEL_22:
        LOBYTE(a3) = 4;
        McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, v8, 0);
      }
    }
    else
    {
      if ( !g_bDisableEnableForLimitDetectionForWdiOnly || (v11 = v6[96]) == 0 || v11[65] )
      {
        memset(v48, 0, sizeof(v48));
        memset_0(v51, 0, sizeof(v51));
        cbData = 0;
        Uuid = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 901, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
        }
        DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
        v12 = DeviceInfoList;
        if ( DeviceInfoList == -1 )
        {
          LastError = GetLastError();
          v3 = LastError;
          a1 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_87;
          }
          v19 = 902;
        }
        else
        {
          if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
          {
            v20 = 0;
            LODWORD(v48[0]) = 48;
            for ( i = 0; ; i = v20 )
            {
              if ( !(unsigned int)DevObjEnumDeviceInfo(v12, i, v48) )
                goto LABEL_81;
              if ( !(unsigned int)DevObjGetDeviceInstanceId(v12, v48, v51, 200, 0) )
              {
                v24 = GetLastError();
                v3 = v24;
                a1 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                {
                  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  {
                    v29 = 904;
                    goto LABEL_80;
                  }
LABEL_82:
                  if ( a1 != &WPP_GLOBAL_Control && *((_BYTE *)a1 + 105) && (*((_BYTE *)a1 + 108) & 1) != 0 )
                    WPP_SF_(a1[12], 908, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
                }
LABEL_86:
                v4 = v37;
                goto LABEL_87;
              }
              lpcbData = 131097;
              v22 = (HKEY)DevObjOpenDevRegKey(v12, v48, 1);
              if ( v22 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
              {
                v30 = GetLastError();
                v3 = v30;
                LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 105)
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    905,
                    &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
                    v30);
                }
                goto LABEL_86;
              }
              cbData = 78;
              v23 = RegQueryValueExW(v22, L"NetCfgInstanceId", 0, 0, Data, &cbData);
              if ( v23
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  906,
                  &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
                  v23);
              }
              RegCloseKey(v22);
              StringUuid[36] = 0;
              v24 = UuidFromStringW(StringUuid, &Uuid);
              v3 = v24;
              if ( v24 )
              {
                a1 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                {
                  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  {
                    v29 = 907;
LABEL_80:
                    WPP_SF_d(a1[12], v29, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v24);
LABEL_81:
                    a1 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  goto LABEL_82;
                }
                goto LABEL_86;
              }
              if ( *(PVOID *)&Uuid.Data1 == v6[1] && *(PVOID *)Uuid.Data4 == v6[2] )
                break;
              ++v20;
            }
            v4 = v37;
            v7 = 4;
            WlanLogLimitConnectivity(4, a2, v39, v37);
            v3 = 0;
            if ( !(unsigned int)DevObjRestartDevices(v12, v48, 1) )
            {
              v28 = GetLastError();
              v3 = v28;
              v26 = (int)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  909,
                  &WPP_ddf81be17d3f38632d423248857aa840_Traceguids,
                  v28);
              }
            }
            if ( (byte_1802A0A43 & 4) != 0 )
            {
              LOBYTE(v27) = 4;
              McTemplateU0uud_EventWriteTransfer(v26, v25, v27, 6, v3);
            }
LABEL_91:
            DevObjDestroyDeviceInfoList(v12);
LABEL_92:
            v5 = v39;
LABEL_93:
            v10 = v38;
            goto LABEL_94;
          }
          LastError = GetLastError();
          v3 = LastError;
          a1 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
LABEL_87:
            if ( v7 == 1 && (byte_1802A0A43 & 4) != 0 )
            {
              LOBYTE(a3) = 1;
              McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, 7, v3);
            }
            if ( v12 == -1 )
              goto LABEL_92;
            goto LABEL_91;
          }
          v19 = 903;
        }
        WPP_SF_d(a1[12], v19, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, LastError);
        goto LABEL_87;
      }
      if ( (byte_1802A0A43 & 4) != 0 )
      {
        v8 = 3;
        goto LABEL_22;
      }
    }
    if ( !g_bNoDisconnectForLimitDetection )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 910, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
      }
      v7 = 5;
      WlanLogLimitConnectivity(5, a2, v5, v4);
      v13 = IntfDisconnect(0, *v6, 0, 8u, 0, 0, 0);
      v3 = v13;
      if ( (byte_1802A0A43 & 4) != 0 )
      {
        LOBYTE(v16) = 5;
        McTemplateU0uud_EventWriteTransfer(v15, v14, v16, 6, v13);
      }
      goto LABEL_93;
    }
    v12 = -1;
    if ( (byte_1802A0A43 & 4) != 0 )
    {
      LOBYTE(a3) = 5;
      McTemplateU0uud_EventWriteTransfer((_DWORD)a1, a2, a3, 2, 0);
    }
    goto LABEL_87;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 900, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids);
    v10 = v3;
  }
LABEL_94:
  v31 = WlansvcLogger::Provider();
  if ( *(_DWORD *)v31 > 5u && (unsigned __int8)tlgKeywordOn(v31, 0x400000000000LL, v32) )
  {
    v39 = g_bDisableEnableForLimitDetectionForWdiOnly;
    v38 = g_bNoDisableEnableForLimitDetection;
    cbData = g_bNoDisconnectForLimitDetection;
    v42 = v10;
    v37 = g_bResetRecoveryForLimitDetection == 0;
    v45 = *((_DWORD *)v6 + 6);
    *(_QWORD *)&Uuid.Data1 = v6 + 1;
    v43 = v3;
    v44 = v7;
    v46 = v4;
    v41[0] = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v34,
      (__int64)byte_180275879,
      v33,
      v34,
      (__int64 *)&Uuid,
      (__int64)v41,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v37,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&cbData);
  }
  TriageProviderLoggingHelper(v6, v5, v7, v3, v10, lpcbData);
  return v3;
}

```

## disassembly

```asm
0x1801471fc  mov     [rsp-8+arg_18], rbx
0x180147201  push    rbp
0x180147202  push    rsi
0x180147203  push    rdi
0x180147204  push    r12
0x180147206  push    r13
0x180147208  push    r14
0x18014720a  push    r15
0x18014720c  lea     rbp, [rsp-1E0h]
0x180147214  sub     rsp, 2E0h
0x18014721b  mov     rax, cs:__security_cookie
0x180147222  xor     rax, rsp
0x180147225  mov     [rbp+210h+var_40], rax
0x18014722c  test    cs:byte_1802A0A43, 4
0x180147233  mov     ebx, 0Dh
0x180147238  mov     r15d, r8d
0x18014723b  mov     [rbp+210h+var_290], r8d
0x18014723f  mov     r14d, edx
0x180147242  mov     [rbp+210h+var_288], edx
0x180147245  mov     r12, rcx
0x180147248  mov     [rbp+210h+var_28C], 32h ; '2'
0x18014724f  lea     r13d, [rbx-0Ch]
0x180147253  jz      short loc_180147264
0x180147255  mov     r9b, r13b
0x180147258  mov     dword ptr [rsp+310h+lpData], edx
0x18014725c  mov     r8b, r13b
0x18014725f  call    McTemplateU0uud_EventWriteTransfer
0x180147264  xor     edi, edi
0x180147266  cmp     cs:?g_bResetRecoveryForLimitDetection@@3HA, edi; int g_bResetRecoveryForLimitDetection
0x18014726c  jnz     short loc_1801472A7
0x18014726e  test    cs:byte_1802A0A43, 4
0x180147275  jz      short loc_180147286
0x180147277  mov     r9b, 2
0x18014727a  mov     dword ptr [rsp+310h+lpData], edi
0x18014727e  mov     r8b, 3
0x180147281  call    McTemplateU0uud_EventWriteTransfer
0x180147286  cmp     cs:?g_bNoDisableEnableForLimitDetection@@3HA, edi; int g_bNoDisableEnableForLimitDetection
0x18014728c  jz      loc_180147368
0x180147292  test    cs:byte_1802A0A43, 4
0x180147299  jz      loc_1801473A9
0x18014729f  mov     r9b, 2
0x1801472a2  jmp     loc_18014739D
0x1801472a7  mov     rax, [r12+2B8h]
0x1801472af  cmp     [rax+2B8h], rdi
0x1801472b6  jz      short loc_180147286
0x1801472b8  mov     r13d, 3
0x1801472be  mov     [rbp+210h+var_280], 80180h
0x1801472c5  mov     ecx, r13d
0x1801472c8  mov     [rbp+210h+var_27C], 0DEADBEEFh
0x1801472cf  mov     r9d, r15d
0x1801472d2  mov     r8d, r14d
0x1801472d5  call    ?WlanLogLimitConnectivity@@YAKW4_LimitedRecoveryType@@KKK@Z; WlanLogLimitConnectivity(_LimitedRecoveryType,ulong,ulong,ulong)
0x1801472da  mov     rax, [r12+2B8h]
0x1801472e2  lea     rdx, [rbp+210h+var_280]
0x1801472e6  mov     rcx, [r12+2C0h]
0x1801472ee  mov     rax, [rax+2B8h]
0x1801472f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801472fa  test    cs:byte_1802A0A43, 4
0x180147301  mov     esi, eax
0x180147303  mov     [rbp+210h+var_28C], eax
0x180147306  mov     ebx, eax
0x180147308  jz      short loc_180147319
0x18014730a  mov     r9b, 6
0x18014730d  mov     dword ptr [rsp+310h+lpData], eax
0x180147311  mov     r8b, r13b
0x180147314  call    McTemplateU0uud_EventWriteTransfer
0x180147319  test    esi, esi
0x18014731b  jnz     loc_180147286
0x180147321  mov     rcx, cs:WPP_GLOBAL_Control
0x180147328  lea     rdi, WPP_GLOBAL_Control
0x18014732f  cmp     rcx, rdi
0x180147332  jz      loc_18014782E
0x180147338  cmp     byte ptr [rcx+69h], 1
0x18014733c  jb      loc_18014782E
0x180147342  test    byte ptr [rcx+6Ch], 1
0x180147346  jz      loc_18014782E
0x18014734c  mov     rcx, [rcx+60h]
0x180147350  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180147357  mov     edx, 384h
0x18014735c  call    WPP_SF_
0x180147361  mov     esi, ebx
0x180147363  jmp     loc_18014782E
0x180147368  cmp     cs:?g_bDisableEnableForLimitDetectionForWdiOnly@@3HA, edi; int g_bDisableEnableForLimitDetectionForWdiOnly
0x18014736e  jz      loc_18014746B
0x180147374  mov     rax, [r12+300h]
0x18014737c  test    rax, rax
0x18014737f  jz      loc_18014746B
0x180147385  cmp     [rax+104h], edi
0x18014738b  jnz     loc_18014746B
0x180147391  test    cs:byte_1802A0A43, 4
0x180147398  jz      short loc_1801473A9
0x18014739a  mov     r9b, 3
0x18014739d  mov     r8b, 4
0x1801473a0  mov     dword ptr [rsp+310h+lpData], edi
0x1801473a4  call    McTemplateU0uud_EventWriteTransfer
0x1801473a9  cmp     cs:?g_bNoDisconnectForLimitDetection@@3HA, edi; int g_bNoDisconnectForLimitDetection
0x1801473af  jz      short loc_1801473D6
0x1801473b1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801473b5  test    cs:byte_1802A0A43, 4
0x1801473bc  jz      loc_1801477FA
0x1801473c2  mov     r9b, 2
0x1801473c5  mov     dword ptr [rsp+310h+lpData], edi
0x1801473c9  mov     r8b, 5
0x1801473cc  call    McTemplateU0uud_EventWriteTransfer
0x1801473d1  jmp     loc_1801477FA
0x1801473d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801473dd  lea     rdi, WPP_GLOBAL_Control
0x1801473e4  cmp     rcx, rdi
0x1801473e7  jz      short loc_18014740A
0x1801473e9  cmp     byte ptr [rcx+69h], 1
0x1801473ed  jb      short loc_18014740A
0x1801473ef  test    byte ptr [rcx+6Ch], 1
0x1801473f3  jz      short loc_18014740A
0x1801473f5  mov     rcx, [rcx+60h]
0x1801473f9  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180147400  mov     edx, 38Eh
0x180147405  call    WPP_SF_
0x18014740a  mov     esi, 5
0x18014740f  mov     r9d, r15d
0x180147412  mov     ecx, esi
0x180147414  mov     r8d, r14d
0x180147417  mov     r13d, esi
0x18014741a  call    ?WlanLogLimitConnectivity@@YAKW4_LimitedRecoveryType@@KKK@Z; WlanLogLimitConnectivity(_LimitedRecoveryType,ulong,ulong,ulong)
0x18014741f  mov     rdx, [r12]; void *
0x180147423  mov     r9b, 8; unsigned __int8
0x180147426  mov     [rsp+310h+var_2E0], 0; int
0x18014742e  xor     r8d, r8d; unsigned int
0x180147431  mov     dword ptr [rsp+310h+lpcbData], 0; int
0x180147439  xor     ecx, ecx; unsigned int
0x18014743b  mov     dword ptr [rsp+310h+lpData], 0; int
0x180147443  call    ?IntfDisconnect@@YAKKPEAXKEHHH@Z; IntfDisconnect(ulong,void *,ulong,uchar,int,int,int)
0x180147448  test    cs:byte_1802A0A43, 4
0x18014744f  mov     ebx, eax
0x180147451  jz      loc_18014782B
0x180147457  mov     r9b, 6
0x18014745a  mov     dword ptr [rsp+310h+lpData], eax
0x18014745e  mov     r8b, sil
0x180147461  call    McTemplateU0uud_EventWriteTransfer
0x180147466  jmp     loc_18014782B
0x18014746b  xorps   xmm0, xmm0
0x18014746e  lea     rcx, [rbp+210h+var_1D0]; void *
0x180147472  xor     edx, edx; Val
0x180147474  mov     r8d, 190h; Size
0x18014747a  movups  [rbp+210h+var_250], xmm0
0x18014747e  movups  [rbp+210h+var_240], xmm0
0x180147482  movups  [rbp+210h+var_230], xmm0
0x180147486  call    memset_0
0x18014748b  xorps   xmm0, xmm0
0x18014748e  mov     [rbp+210h+cbData], edi
0x180147491  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x180147495  mov     rcx, cs:WPP_GLOBAL_Control
0x18014749c  lea     rdi, WPP_GLOBAL_Control
0x1801474a3  lea     rsi, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x1801474aa  cmp     rcx, rdi
0x1801474ad  jz      short loc_1801474CC
0x1801474af  cmp     byte ptr [rcx+69h], 1
0x1801474b3  jb      short loc_1801474CC
0x1801474b5  test    byte ptr [rcx+6Ch], 1
0x1801474b9  jz      short loc_1801474CC
0x1801474bb  mov     rcx, [rcx+60h]
0x1801474bf  mov     edx, 385h
0x1801474c4  mov     r8, rsi
0x1801474c7  call    WPP_SF_
0x1801474cc  xor     r9d, r9d
0x1801474cf  mov     [rsp+310h+lpData], 0
0x1801474d8  xor     r8d, r8d
0x1801474db  xor     edx, edx
0x1801474dd  xor     ecx, ecx
0x1801474df  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801474e5  mov     r14, rax
0x1801474e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801474ec  jnz     short loc_180147533
0x1801474ee  call    cs:__imp_GetLastError
0x1801474f4  mov     ebx, eax
0x1801474f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801474fd  cmp     rcx, rdi
0x180147500  jz      loc_1801477FA
0x180147506  cmp     byte ptr [rcx+69h], 1
0x18014750a  jb      loc_1801477FA
0x180147510  test    byte ptr [rcx+6Ch], 1
0x180147514  jz      loc_1801477FA
0x18014751a  mov     edx, 386h
0x18014751f  mov     rcx, [rcx+60h]
0x180147523  mov     r9d, eax
0x180147526  mov     r8, rsi
0x180147529  call    WPP_SF_d
0x18014752e  jmp     loc_1801477FA
0x180147533  mov     [rsp+310h+lpcbData], 0
0x18014753c  lea     rdx, GUID_DEVCLASS_NET
0x180147543  mov     r9d, 2
0x180147549  mov     [rsp+310h+lpData], 0
0x180147552  xor     r8d, r8d
0x180147555  mov     rcx, r14
0x180147558  call    cs:__imp_DevObjGetClassDevs
0x18014755e  test    eax, eax
0x180147560  jnz     short loc_180147595
0x180147562  call    cs:__imp_GetLastError
0x180147568  mov     ebx, eax
0x18014756a  mov     rcx, cs:WPP_GLOBAL_Control
0x180147571  cmp     rcx, rdi
0x180147574  jz      loc_1801477FA
0x18014757a  cmp     byte ptr [rcx+69h], 1
0x18014757e  jb      loc_1801477FA
0x180147584  test    byte ptr [rcx+6Ch], 1
0x180147588  jz      loc_1801477FA
0x18014758e  mov     edx, 387h
0x180147593  jmp     short loc_18014751F
0x180147595  xor     r15d, r15d
0x180147598  mov     dword ptr [rbp+210h+var_250], 30h ; '0'
0x18014759f  xor     edx, edx
0x1801475a1  jmp     loc_1801476A1
0x1801475a6  mov     r9d, 0C8h
0x1801475ac  mov     [rsp+310h+lpData], 0
0x1801475b5  lea     r8, [rbp+210h+var_1D0]
0x1801475b9  mov     rcx, r14
0x1801475bc  lea     rdx, [rbp+210h+var_250]
0x1801475c0  call    cs:__imp_DevObjGetDeviceInstanceId
0x1801475c6  test    eax, eax
0x1801475c8  jz      loc_180147799
0x1801475ce  xor     r9d, r9d
0x1801475d1  mov     dword ptr [rsp+310h+lpcbData], 20019h
0x1801475d9  lea     rdx, [rbp+210h+var_250]
0x1801475dd  mov     dword ptr [rsp+310h+lpData], 2
0x1801475e5  mov     rcx, r14
0x1801475e8  lea     r8d, [r9+1]
0x1801475ec  call    cs:__imp_DevObjOpenDevRegKey
0x1801475f2  mov     rbx, rax
0x1801475f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801475f9  jz      loc_180147763
0x1801475ff  lea     rax, [rbp+210h+cbData]
0x180147603  mov     [rbp+210h+cbData], 4Eh ; 'N'
0x18014760a  mov     [rsp+310h+lpcbData], rax; lpcbData
0x18014760f  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180147616  lea     rax, [rbp+210h+Data]
0x18014761a  xor     r9d, r9d; lpType
0x18014761d  xor     r8d, r8d; lpReserved
0x180147620  mov     [rsp+310h+lpData], rax; lpData
0x180147625  mov     rcx, rbx; hKey
0x180147628  call    cs:__imp_RegQueryValueExW
0x18014762e  test    eax, eax
0x180147630  jz      short loc_18014765E
0x180147632  mov     rcx, cs:WPP_GLOBAL_Control
0x180147639  cmp     rcx, rdi
0x18014763c  jz      short loc_18014765E
0x18014763e  cmp     byte ptr [rcx+69h], 1
0x180147642  jb      short loc_18014765E
0x180147644  test    byte ptr [rcx+6Ch], 1
0x180147648  jz      short loc_18014765E
0x18014764a  mov     rcx, [rcx+60h]
0x18014764e  mov     edx, 38Ah
0x180147653  mov     r9d, eax
0x180147656  mov     r8, rsi
0x180147659  call    WPP_SF_d
0x18014765e  mov     rcx, rbx; hKey
0x180147661  call    cs:__imp_RegCloseKey
0x180147667  xor     eax, eax
0x180147669  lea     rdx, [rbp+210h+Uuid]; Uuid
0x18014766d  lea     rcx, [rbp+210h+StringUuid]; StringUuid
0x180147671  mov     [rbp+210h+var_1D6], ax
0x180147675  call    cs:__imp_UuidFromStringW
0x18014767b  mov     ebx, eax
0x18014767d  test    eax, eax
0x18014767f  jnz     loc_180147740
0x180147685  mov     rax, qword ptr [rbp+210h+Uuid.Data1]
0x180147689  cmp     rax, [r12+8]
0x18014768e  jnz     short loc_18014769B
0x180147690  mov     rax, qword ptr [rbp+210h+Uuid.Data4]
0x180147694  cmp     rax, [r12+10h]
0x180147699  jz      short loc_1801476BB
0x18014769b  inc     r15d
0x18014769e  mov     edx, r15d
0x1801476a1  lea     r8, [rbp+210h+var_250]
0x1801476a5  mov     rcx, r14
0x1801476a8  call    cs:__imp_DevObjEnumDeviceInfo
0x1801476ae  test    eax, eax
0x1801476b0  jnz     loc_1801475A6
0x1801476b6  jmp     loc_1801477CD
0x1801476bb  mov     r15d, [rbp+210h+var_290]
0x1801476bf  mov     r13d, 4
0x1801476c5  mov     r8d, [rbp+210h+var_288]
0x1801476c9  mov     ecx, r13d
0x1801476cc  mov     r9d, r15d
0x1801476cf  call    ?WlanLogLimitConnectivity@@YAKW4_LimitedRecoveryType@@KKK@Z; WlanLogLimitConnectivity(_LimitedRecoveryType,ulong,ulong,ulong)
0x1801476d4  lea     r8d, [r13-3]
0x1801476d8  mov     rcx, r14
0x1801476db  lea     rdx, [rbp+210h+var_250]
0x1801476df  xor     ebx, ebx
0x1801476e1  call    cs:__imp_DevObjRestartDevices
0x1801476e7  test    eax, eax
0x1801476e9  jnz     short loc_18014771F
0x1801476eb  call    cs:__imp_GetLastError
0x1801476f1  mov     ebx, eax
0x1801476f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801476fa  cmp     rcx, rdi
0x1801476fd  jz      short loc_18014771F
0x1801476ff  cmp     byte ptr [rcx+69h], 1
0x180147703  jb      short loc_18014771F
0x180147705  test    byte ptr [rcx+6Ch], 1
0x180147709  jz      short loc_18014771F
0x18014770b  mov     rcx, [rcx+60h]
  ... truncated ...
```
