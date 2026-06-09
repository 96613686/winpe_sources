# CAutoPlayParams::_SaveKnownCustomEventInfo(_GUID const &,ushort const *)

- ea: `0x18021f850`
- end: `0x18021ff22`
- name: `?_SaveKnownCustomEventInfo@CAutoPlayParams@@AEAAJAEBU_GUID@@PEBG@Z`
- size: `1746`
- prototype: `void __noreturn(CAutoPlayParams *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c0ec8`

## callees

- `0x18001f630`
- `0x1800257d0`
- `0x18003eab0`
- `0x18003ef10`
- `0x18006b4d0`
- `0x180083dec`
- `0x180177f38`
- `0x18021f850`
- `0x180233280`
- `0x1802342fc`
- `0x18025c218`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18021fe61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18021fe61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18021fd31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18021fd6f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18021fd31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18021fd6f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18021fc21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18021fc21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fc79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fdb6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fe05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fe4a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fc79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fdb6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fe05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18021fe4a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18021fce7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18021fce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021fe9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021fea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021fe9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021fea8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18021f8a4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18021fa01`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18021f8a4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18021fa01`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18021f997`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18021f997`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18021f98b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18021f98b`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x18021f9e6`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x18021f9e6`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18021f954`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18021fef0`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18021f954`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18021fef0`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18021f902`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18021fa6b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18021f902`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18021fa6b`
- `Windows.Storage!RegGetValueString` at `0x18021fcd6`
- `Windows.Storage!RegGetValueString` at `0x18021fcd6`

## pseudocode

```c
void __fastcall __noreturn CAutoPlayParams::_SaveKnownCustomEventInfo(
        CAutoPlayParams *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // r8
  GUID *v6; // rax
  CAutoPlayParams *v7; // rcx
  unsigned __int64 v8; // r9
  HRESULT v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  const size_t *v15; // r8
  _QWORD *p_lpData; // r9
  __int64 v17; // r8
  BYTE *v18; // r14
  BYTE *v19; // rsi
  LSTATUS v20; // eax
  signed int v21; // ebx
  __int64 v22; // rdi
  __int64 v23; // rax
  LSTATUS v24; // eax
  signed int v25; // ebx
  __int64 v26; // rbx
  unsigned __int64 v27; // rbx
  WCHAR *v28; // r15
  const BYTE *v29; // rcx
  __int64 v30; // rax
  LSTATUS v31; // eax
  signed int v32; // ebx
  __int64 v33; // rax
  LSTATUS v34; // eax
  signed int v35; // ebx
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+7Ch] [rbp-84h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  unsigned int v43; // [rsp+88h] [rbp-78h] BYREF
  GUID pclsid; // [rsp+90h] [rbp-70h] BYREF
  DEVPROPKEY v45; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+B4h] [rbp-4Ch]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  DEVPROPKEY v48; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+D4h] [rbp-2Ch]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  OLECHAR v51[40]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR SubKey[82]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v54[364]; // [rsp+224h] [rbp+124h] BYREF

  pclsid = GUID_NULL;
  StringFromGUID2(a2, sz, 39);
  v40 = 1;
  v41 = 1;
  v42 = 0;
  v43 = 0;
  v38 = 0;
  v39 = DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid;
  if ( (int)DevGetObjectProperties(1, a3, 0, 1, &v39, &v43, &v38) >= 0 )
  {
    v5 = v38;
    if ( v43 == 1 && *(_DWORD *)(v38 + 16) == 1 )
    {
      if ( (unsigned int)IsEqualGUID(v38, &DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid) )
      {
        if ( *(_DWORD *)(v5 + 32) == 13 )
        {
          if ( *(_DWORD *)(v5 + 36) )
          {
            v6 = *(GUID **)(v5 + 40);
            if ( v6 )
              pclsid = *v6;
          }
        }
      }
    }
    DevFreeObjectProperties(v43, v5);
  }
  if ( !(unsigned int)IsEqualGUID(&pclsid, &GUID_NULL)
    || (CAutoPlayParams::_FindKnownCustomEventDeviceFromContainer(v7, sz, v51, v8) < 0
      ? (v9 = CoCreateGuid(&pclsid))
      : (v9 = CLSIDFromString(v51, &pclsid)),
        v9 >= 0
     && (*(_QWORD *)&v48.fmtid.Data1 = 0x100000000DLL,
         *(_QWORD *)v48.fmtid.Data4 = &pclsid,
         v45.pid = 1,
         v45.fmtid = (DEVPROPGUID)DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid,
         v46 = 1,
         v47 = 0,
         (int)DevSetObjectProperties(1, a3, 1, &v45) >= 0)) )
  {
    StringFromGUID2(&pclsid, v51, 39);
    v45 = DEVPKEY_NAME;
    v48 = DEVPKEY_DeviceContainer_Icon;
    v46 = 0;
    v47 = 0;
    v49 = 0;
    v50 = 0;
    if ( (int)DevGetObjectProperties(2, sz, 0, 2, &v45, &v43, &v38) < 0 )
      goto LABEL_68;
    if ( v43 == 2 )
    {
      lpData = 0;
      v10 = 0;
      hKey = 0;
      while ( 1 )
      {
        v11 = v38 + 48LL * v10;
        if ( *(_DWORD *)(v11 + 16) == 10 )
        {
          if ( !(unsigned int)IsEqualGUID(v38 + 48LL * v10, &DEVPKEY_NAME) )
            goto LABEL_28;
          v15 = *(const size_t **)(v14 + 40);
          if ( !v15 )
            goto LABEL_28;
          p_lpData = &lpData;
        }
        else
        {
          if ( *(_DWORD *)(v11 + 16) != 57 )
            goto LABEL_28;
          if ( !(unsigned int)IsEqualGUID(v38 + 48LL * v10, &DEVPKEY_DeviceContainer_Icon) )
            goto LABEL_28;
          v15 = *(const size_t **)(v17 + 40);
          if ( !v15 )
            goto LABEL_28;
          p_lpData = &hKey;
        }
        _AllocString<CTCoAllocPolicy>(v13, v12, v15, p_lpData);
LABEL_28:
        if ( ++v10 >= v43 )
        {
          v18 = lpData;
          v19 = (BYTE *)hKey;
          if ( lpData && hKey )
          {
            wcscpy(SubKey, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\KnownDevices\\");
            memset_0(v54, 0, 0x164u);
            if ( (int)StringCchCatW(SubKey, 0x104u, v51) >= 0 )
            {
              hKey = 0;
              v20 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
              v21 = v20;
              if ( v20 > 0 )
                v21 = (unsigned __int16)v20 | 0x80070000;
              if ( v21 >= 0 )
              {
                v22 = -1;
                v23 = -1;
                do
                  ++v23;
                while ( sz[v23] );
                v24 = RegSetValueExW(hKey, L"ContainerID", 0, 1u, (const BYTE *)sz, 2 * v23 + 2);
                v25 = v24;
                if ( v24 > 0 )
                  v25 = (unsigned __int16)v24 | 0x80070000;
                if ( v25 >= 0 )
                {
                  v26 = -1;
                  do
                    ++v26;
                  while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v26) );
                  v27 = v26 + 1;
                  v28 = (WCHAR *)operator new(saturated_mul(v27, 2u));
                  if ( !(unsigned int)RegGetValueString(hKey, 0, L"CustomEvent", v28, v27)
                    || StrCmpIW(v28, *((PCWSTR *)this + 4)) )
                  {
                    if ( (int)StringCchPrintfW(
                                SubKey,
                                0x104u,
                                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\%s\\%s",
                                L"UserChosenExecuteHandlers",
                                v51) >= 0 )
                      RegDeleteTreeW(HKEY_CURRENT_USER, SubKey);
                    if ( (int)StringCchPrintfW(
                                SubKey,
                                0x104u,
                                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\%s\\%s",
                                L"EventHandlersDefaultSelection",
                                v51) >= 0 )
                      RegDeleteTreeW(HKEY_CURRENT_USER, SubKey);
                  }
                  CZeroInitNew::operator delete(v28);
                  v29 = (const BYTE *)*((_QWORD *)this + 4);
                  v30 = -1;
                  do
                    ++v30;
                  while ( *(_WORD *)&v29[2 * v30] );
                  v31 = RegSetValueExW(hKey, L"CustomEvent", 0, 1u, v29, 2 * v30 + 2);
                  v32 = v31;
                  if ( v31 > 0 )
                    v32 = (unsigned __int16)v31 | 0x80070000;
                  if ( v32 >= 0 )
                  {
                    v33 = -1;
                    do
                      ++v33;
                    while ( *(_WORD *)&v18[2 * v33] );
                    v34 = RegSetValueExW(hKey, L"Label", 0, 1u, v18, 2 * v33 + 2);
                    v35 = v34;
                    if ( v34 > 0 )
                      v35 = (unsigned __int16)v34 | 0x80070000;
                    if ( v35 >= 0 )
                    {
                      do
                        ++v22;
                      while ( *(_WORD *)&v19[2 * v22] );
                      RegSetValueExW(hKey, L"Icon", 0, 2u, v19, 2 * v22 + 2);
                    }
                  }
                }
                RegCloseKey(hKey);
              }
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids);
          }
          CoTaskMemFree(v18);
          CoTaskMemFree(v19);
          goto LABEL_68;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6a67a0b5e4173297d889067deb12d96d_Traceguids);
LABEL_68:
    if ( v38 )
      DevFreeObjectProperties(v43, v38);
  }
}

```

## disassembly

```asm
0x18021f850  mov     [rsp-8+arg_18], rbx
0x18021f855  push    rbp
0x18021f856  push    rsi
0x18021f857  push    rdi
0x18021f858  push    r12
0x18021f85a  push    r13
0x18021f85c  push    r14
0x18021f85e  push    r15
0x18021f860  lea     rbp, [rsp-2A0h]
0x18021f868  sub     rsp, 3A0h
0x18021f86f  mov     rax, cs:__security_cookie
0x18021f876  xor     rax, rsp
0x18021f879  mov     [rbp+2D0h+var_40], rax
0x18021f880  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18021f887  mov     rax, rdx
0x18021f88a  mov     rdi, r8
0x18021f88d  mov     r13, rcx
0x18021f890  lea     rdx, [rbp+2D0h+sz]; lpsz
0x18021f894  mov     esi, 27h ; '''
0x18021f899  mov     rcx, rax; rguid
0x18021f89c  mov     r8d, esi; cchMax
0x18021f89f  movdqu  xmmword ptr [rbp+2D0h+pclsid.Data1], xmm0
0x18021f8a4  call    cs:__imp_StringFromGUID2
0x18021f8aa  mov     eax, cs:dword_1805D85D0
0x18021f8b0  lea     r15d, [rsi-26h]
0x18021f8b4  movups  xmm0, cs:DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x18021f8bb  mov     [rsp+3D0h+var_358], eax
0x18021f8bf  xor     r12d, r12d
0x18021f8c2  lea     rax, [rsp+3D0h+var_370]
0x18021f8c7  mov     [rsp+3D0h+var_354], r15d
0x18021f8cc  mov     [rsp+3D0h+lpSecurityAttributes], rax
0x18021f8d1  mov     r9d, r15d
0x18021f8d4  lea     rax, [rbp+2D0h+var_348]
0x18021f8d8  mov     [rbp+2D0h+var_350], r12
0x18021f8dc  mov     qword ptr [rsp+3D0h+samDesired], rax
0x18021f8e1  xor     r8d, r8d
0x18021f8e4  lea     rax, [rsp+3D0h+var_368]
0x18021f8e9  mov     [rbp+2D0h+var_348], r12d
0x18021f8ed  mov     rdx, rdi
0x18021f8f0  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x18021f8f5  mov     ecx, r15d
0x18021f8f8  mov     [rsp+3D0h+var_370], r12
0x18021f8fd  movups  [rsp+3D0h+var_368], xmm0
0x18021f902  call    cs:__imp_DevGetObjectProperties
0x18021f908  test    eax, eax
0x18021f90a  js      short loc_18021F95A
0x18021f90c  mov     r8, [rsp+3D0h+var_370]
0x18021f911  cmp     [rbp+2D0h+var_348], r15d
0x18021f915  jnz     short loc_18021F94E
0x18021f917  cmp     [r8+10h], r15d
0x18021f91b  jnz     short loc_18021F94E
0x18021f91d  lea     rdx, DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x18021f924  mov     rcx, r8
0x18021f927  call    IsEqualGUID
0x18021f92c  test    eax, eax
0x18021f92e  jz      short loc_18021F94E
0x18021f930  cmp     dword ptr [r8+20h], 0Dh
0x18021f935  jnz     short loc_18021F94E
0x18021f937  cmp     [r8+24h], r12d
0x18021f93b  jbe     short loc_18021F94E
0x18021f93d  mov     rax, [r8+28h]
0x18021f941  test    rax, rax
0x18021f944  jz      short loc_18021F94E
0x18021f946  movups  xmm0, xmmword ptr [rax]
0x18021f949  movdqu  xmmword ptr [rbp+2D0h+pclsid.Data1], xmm0
0x18021f94e  mov     ecx, [rbp+2D0h+var_348]
0x18021f951  mov     rdx, r8
0x18021f954  call    cs:__imp_DevFreeObjectProperties
0x18021f95a  lea     rdx, GUID_NULL
0x18021f961  lea     rcx, [rbp+2D0h+pclsid]
0x18021f965  call    IsEqualGUID
0x18021f96a  test    eax, eax
0x18021f96c  jz      loc_18021F9F6
0x18021f972  lea     r8, [rbp+2D0h+var_2F0]; unsigned __int16 *
0x18021f976  lea     rdx, [rbp+2D0h+sz]; unsigned __int16 *
0x18021f97a  call    ?_FindKnownCustomEventDeviceFromContainer@CAutoPlayParams@@AEAAJPEAG0_K@Z
0x18021f97f  test    eax, eax
0x18021f981  js      short loc_18021F993
0x18021f983  lea     rdx, [rbp+2D0h+pclsid]; pclsid
0x18021f987  lea     rcx, [rbp+2D0h+var_2F0]; lpsz
0x18021f98b  call    cs:__imp_CLSIDFromString
0x18021f991  jmp     short loc_18021F99D
0x18021f993  lea     rcx, [rbp+2D0h+pclsid]; pguid
0x18021f997  call    cs:__imp_CoCreateGuid
0x18021f99d  mov     ebx, eax
0x18021f99f  test    eax, eax
0x18021f9a1  js      loc_18021FEF6
0x18021f9a7  movups  xmm0, cs:DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x18021f9ae  lea     rax, [rbp+2D0h+pclsid]
0x18021f9b2  mov     dword ptr [rbp+2D0h+var_310], 0Dh
0x18021f9b9  mov     qword ptr [rbp+2D0h+var_310+8], rax
0x18021f9bd  lea     r9, [rbp+2D0h+var_330]
0x18021f9c1  mov     eax, cs:dword_1805D85D0
0x18021f9c7  mov     r8d, r15d
0x18021f9ca  mov     rdx, rdi
0x18021f9cd  mov     [rbp+2D0h+var_320], eax
0x18021f9d0  mov     ecx, r15d
0x18021f9d3  mov     dword ptr [rbp+2D0h+var_310+4], 10h
0x18021f9da  movups  [rbp+2D0h+var_330], xmm0
0x18021f9de  mov     [rbp+2D0h+var_31C], r15d
0x18021f9e2  mov     [rbp+2D0h+var_318], r12
0x18021f9e6  call    cs:__imp_DevSetObjectProperties
0x18021f9ec  mov     ebx, eax
0x18021f9ee  test    eax, eax
0x18021f9f0  js      loc_18021FEF6
0x18021f9f6  mov     r8d, esi; cchMax
0x18021f9f9  lea     rdx, [rbp+2D0h+var_2F0]; lpsz
0x18021f9fd  lea     rcx, [rbp+2D0h+pclsid]; rguid
0x18021fa01  call    cs:__imp_StringFromGUID2
0x18021fa07  mov     eax, cs:DEVPKEY_NAME.pid
0x18021fa0d  lea     rdx, [rbp+2D0h+sz]
0x18021fa11  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x18021fa18  mov     [rbp+2D0h+var_320], eax
0x18021fa1b  mov     r9d, 2
0x18021fa21  mov     eax, cs:DEVPKEY_DeviceContainer_Icon.pid
0x18021fa27  xor     r8d, r8d
0x18021fa2a  mov     [rbp+2D0h+var_300], eax
0x18021fa2d  mov     ecx, r9d
0x18021fa30  lea     rax, [rsp+3D0h+var_370]
0x18021fa35  movaps  [rbp+2D0h+var_330], xmm0
0x18021fa39  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Icon.fmtid.Data1
0x18021fa40  mov     [rsp+3D0h+lpSecurityAttributes], rax
0x18021fa45  lea     rax, [rbp+2D0h+var_348]
0x18021fa49  mov     qword ptr [rsp+3D0h+samDesired], rax
0x18021fa4e  lea     rax, [rbp+2D0h+var_330]
0x18021fa52  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x18021fa57  mov     [rbp+2D0h+var_31C], r12d
0x18021fa5b  mov     [rbp+2D0h+var_318], r12
0x18021fa5f  movaps  [rbp+2D0h+var_310], xmm0
0x18021fa63  mov     [rbp+2D0h+var_2FC], r12d
0x18021fa67  mov     [rbp+2D0h+var_2F8], r12
0x18021fa6b  call    cs:__imp_DevGetObjectProperties
0x18021fa71  mov     ebx, eax
0x18021fa73  test    eax, eax
0x18021fa75  js      loc_18021FEE3
0x18021fa7b  cmp     [rbp+2D0h+var_348], 2
0x18021fa7f  jnz     loc_18021FEB0
0x18021fa85  mov     [rsp+3D0h+lpData], r12
0x18021fa8a  mov     ebx, r12d
0x18021fa8d  mov     [rsp+3D0h+hKey], r12
0x18021fa92  mov     eax, ebx
0x18021fa94  lea     r8, [rax+rax*2]
0x18021fa98  shl     r8, 4
0x18021fa9c  add     r8, [rsp+3D0h+var_370]
0x18021faa1  cmp     dword ptr [r8+10h], 0Ah
0x18021faa6  jnz     short loc_18021FACB
0x18021faa8  lea     rdx, DEVPKEY_NAME
0x18021faaf  mov     rcx, r8
0x18021fab2  call    IsEqualGUID
0x18021fab7  test    eax, eax
0x18021fab9  jz      short loc_18021FAF8
0x18021fabb  mov     r8, [r8+28h]
0x18021fabf  test    r8, r8
0x18021fac2  jz      short loc_18021FAF8
0x18021fac4  lea     r9, [rsp+3D0h+lpData]
0x18021fac9  jmp     short loc_18021FAF3
0x18021facb  cmp     dword ptr [r8+10h], 39h ; '9'
0x18021fad0  jnz     short loc_18021FAF8
0x18021fad2  lea     rdx, DEVPKEY_DeviceContainer_Icon
0x18021fad9  mov     rcx, r8
0x18021fadc  call    IsEqualGUID
0x18021fae1  test    eax, eax
0x18021fae3  jz      short loc_18021FAF8
0x18021fae5  mov     r8, [r8+28h]
0x18021fae9  test    r8, r8
0x18021faec  jz      short loc_18021FAF8
0x18021faee  lea     r9, [rsp+3D0h+hKey]
0x18021faf3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z
0x18021faf8  add     ebx, r15d
0x18021fafb  cmp     ebx, [rbp+2D0h+var_348]
0x18021fafe  jb      short loc_18021FA92
0x18021fb00  mov     r14, [rsp+3D0h+lpData]
0x18021fb05  mov     rsi, [rsp+3D0h+hKey]
0x18021fb0a  test    r14, r14
0x18021fb0d  jz      loc_18021FE69
0x18021fb13  test    rsi, rsi
0x18021fb16  jz      loc_18021FE69
0x18021fb1c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3
0x18021fb23  lea     rcx, [rbp+2D0h+var_1AC]; void *
0x18021fb2a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+10h
0x18021fb31  xor     edx, edx; Val
0x18021fb33  mov     eax, dword ptr cs:aSoftwareMicros_3+0A0h
0x18021fb39  mov     r8d, 164h; Size
0x18021fb3f  movups  xmmword ptr [rbp+2D0h+SubKey], xmm0
0x18021fb46  mov     [rbp+2D0h+var_1B0], eax
0x18021fb4c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+20h
0x18021fb53  movups  [rbp+2D0h+var_240], xmm1
0x18021fb5a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+30h
0x18021fb61  movups  [rbp+2D0h+var_230], xmm0
0x18021fb68  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+40h
0x18021fb6f  movups  [rbp+2D0h+var_220], xmm1
0x18021fb76  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+50h
0x18021fb7d  movups  [rbp+2D0h+var_210], xmm0
0x18021fb84  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+60h
0x18021fb8b  movups  [rbp+2D0h+var_200], xmm1
0x18021fb92  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+70h
0x18021fb99  movups  [rbp+2D0h+var_1F0], xmm0
0x18021fba0  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+80h
0x18021fba7  movups  [rbp+2D0h+var_1E0], xmm1
0x18021fbae  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+90h
0x18021fbb5  movups  [rbp+2D0h+var_1D0], xmm0
0x18021fbbc  movups  [rbp+2D0h+var_1C0], xmm1
0x18021fbc3  call    memset_0
0x18021fbc8  lea     r8, [rbp+2D0h+var_2F0]; unsigned __int16 *
0x18021fbcc  mov     edx, 104h; unsigned __int64
0x18021fbd1  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x18021fbd8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18021fbdd  mov     ebx, eax
0x18021fbdf  test    eax, eax
0x18021fbe1  js      loc_18021FE9C
0x18021fbe7  mov     [rsp+3D0h+lpdwDisposition], r12; lpdwDisposition
0x18021fbec  lea     rax, [rsp+3D0h+hKey]
0x18021fbf1  mov     [rsp+3D0h+phkResult], rax; phkResult
0x18021fbf6  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x18021fbfd  mov     [rsp+3D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18021fc02  xor     r9d, r9d; lpClass
0x18021fc05  mov     [rsp+3D0h+samDesired], 2001Fh; samDesired
0x18021fc0d  xor     r8d, r8d; Reserved
0x18021fc10  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18021fc17  mov     [rsp+3D0h+dwOptions], r12d; dwOptions
0x18021fc1c  mov     [rsp+3D0h+hKey], r12
0x18021fc21  call    cs:__imp_RegCreateKeyExW
0x18021fc27  mov     ebx, eax
0x18021fc29  test    eax, eax
0x18021fc2b  jle     short loc_18021FC36
0x18021fc2d  movzx   ebx, ax
0x18021fc30  or      ebx, 80070000h
0x18021fc36  test    ebx, ebx
0x18021fc38  js      loc_18021FE9C
0x18021fc3e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18021fc42  lea     rcx, [rbp+2D0h+sz]
0x18021fc46  mov     rax, rdi
0x18021fc49  inc     rax
0x18021fc4c  cmp     [rcx+rax*2], r12w
0x18021fc51  jnz     short loc_18021FC49
0x18021fc53  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18021fc58  lea     eax, ds:2[rax*2]
0x18021fc5f  mov     [rsp+3D0h+samDesired], eax; cbData
0x18021fc63  lea     rdx, aContainerid
0x18021fc6a  lea     rax, [rbp+2D0h+sz]
0x18021fc6e  mov     r9d, r15d; dwType
0x18021fc71  xor     r8d, r8d; Reserved
0x18021fc74  mov     qword ptr [rsp+3D0h+dwOptions], rax; lpData
0x18021fc79  call    cs:__imp_RegSetValueExW
0x18021fc7f  mov     ebx, eax
0x18021fc81  test    eax, eax
0x18021fc83  jle     short loc_18021FC8E
0x18021fc85  movzx   ebx, ax
0x18021fc88  or      ebx, 80070000h
0x18021fc8e  test    ebx, ebx
0x18021fc90  js      loc_18021FE5C
0x18021fc96  mov     rax, [r13+20h]
0x18021fc9a  mov     rbx, rdi
0x18021fc9d  inc     rbx
0x18021fca0  cmp     [rax+rbx*2], r12w
0x18021fca5  jnz     short loc_18021FC9D
0x18021fca7  inc     rbx
0x18021fcaa  mov     eax, 2
0x18021fcaf  mul     rbx
0x18021fcb2  cmovb   rax, rdi
0x18021fcb6  mov     rcx, rax; dwBytes
0x18021fcb9  call    ??2@YAPEAX_K@Z
0x18021fcbe  mov     rcx, [rsp+3D0h+hKey]
0x18021fcc3  lea     r8, KeyName
0x18021fcca  mov     r9, rax
0x18021fccd  mov     [rsp+3D0h+dwOptions], ebx
0x18021fcd1  xor     edx, edx
0x18021fcd3  mov     r15, rax
0x18021fcd6  call    cs:__imp_RegGetValueString
0x18021fcdc  test    eax, eax
0x18021fcde  jz      short loc_18021FCF5
0x18021fce0  mov     rdx, [r13+20h]; psz2
0x18021fce4  mov     rcx, r15; psz1
0x18021fce7  call    cs:__imp_StrCmpIW
0x18021fced  test    eax, eax
0x18021fcef  jz      loc_18021FD75
0x18021fcf5  lea     rax, [rbp+2D0h+var_2F0]
0x18021fcf9  mov     ebx, 104h
0x18021fcfe  mov     edx, ebx; unsigned __int64
0x18021fd00  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x18021fd05  lea     r9, aUserchosenexec
0x18021fd0c  lea     r8, aSoftwareMicros_63
0x18021fd13  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x18021fd1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x18021fd1f  test    eax, eax
0x18021fd21  js      short loc_18021FD37
0x18021fd23  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x18021fd2a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18021fd31  call    cs:__imp_RegDeleteTreeW
0x18021fd37  lea     rax, [rbp+2D0h+var_2F0]
0x18021fd3b  mov     rdx, rbx; unsigned __int64
0x18021fd3e  lea     r9, aEventhandlersd
0x18021fd45  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x18021fd4a  lea     r8, aSoftwareMicros_63
0x18021fd51  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x18021fd58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x18021fd5d  test    eax, eax
0x18021fd5f  js      short loc_18021FD75
0x18021fd61  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x18021fd68  mov     rcx, 0FFFFFFFF80000001h; hKey
  ... truncated ...
```
