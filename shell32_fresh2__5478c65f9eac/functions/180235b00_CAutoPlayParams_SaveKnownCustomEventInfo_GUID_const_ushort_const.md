# CAutoPlayParams::_SaveKnownCustomEventInfo(_GUID const &,ushort const *)

- ea: `0x180235b00`
- end: `0x180236251`
- name: `?_SaveKnownCustomEventInfo@CAutoPlayParams@@AEAAJAEBU_GUID@@PEBG@Z`
- size: `1873`
- prototype: `void __noreturn(CAutoPlayParams *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022f24`

## callees

- `0x18001b9a0`
- `0x18001e550`
- `0x180022f00`
- `0x18003a3e0`
- `0x18003a560`
- `0x1800662c0`
- `0x1800808f0`
- `0x18018a528`
- `0x180235b00`
- `0x180249490`
- `0x18024a53c`
- `0x180273e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180236177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180236177`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180235f5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1802360ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18023610f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18023615a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180235f5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1802360ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18023610f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18023615a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180236029`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18023606d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180236029`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18023606d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180235f01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180235f01`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180235fd9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180235fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802361bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802361ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802361bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802361ca`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180235b54`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180235cd5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180235b54`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180235cd5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180235c5f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180235c5f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180235c4d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180235c4d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180235bb8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180235d45`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180235bb8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180235d45`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180235c10`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180236218`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180235c10`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180236218`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180235cb4`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180235cb4`
- `Windows.Storage!RegGetValueString` at `0x180235fc2`
- `Windows.Storage!RegGetValueString` at `0x180235fc2`

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
  __int64 v15; // r8
  void *p_lpData; // r9
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
  if ( !(unsigned __int8)_(&pclsid, &GUID_NULL)
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
          v15 = *(_QWORD *)(v14 + 40);
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
          v15 = *(_QWORD *)(v17 + 40);
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
0x180235b00  mov     [rsp-8+arg_18], rbx
0x180235b05  push    rbp
0x180235b06  push    rsi
0x180235b07  push    rdi
0x180235b08  push    r12
0x180235b0a  push    r13
0x180235b0c  push    r14
0x180235b0e  push    r15
0x180235b10  lea     rbp, [rsp-2A0h]
0x180235b18  sub     rsp, 3A0h
0x180235b1f  mov     rax, cs:__security_cookie
0x180235b26  xor     rax, rsp
0x180235b29  mov     [rbp+2D0h+var_40], rax
0x180235b30  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180235b37  mov     rax, rdx
0x180235b3a  mov     rdi, r8
0x180235b3d  mov     r13, rcx
0x180235b40  lea     rdx, [rbp+2D0h+sz]; lpsz
0x180235b44  mov     esi, 27h ; '''
0x180235b49  mov     rcx, rax; rguid
0x180235b4c  mov     r8d, esi; cchMax
0x180235b4f  movdqu  xmmword ptr [rbp+2D0h+pclsid.Data1], xmm0
0x180235b54  call    cs:__imp_StringFromGUID2
0x180235b5b  nop     dword ptr [rax+rax+00h]
0x180235b60  mov     eax, cs:dword_180619570
0x180235b66  lea     r15d, [rsi-26h]
0x180235b6a  movups  xmm0, cs:DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x180235b71  mov     [rsp+3D0h+var_358], eax
0x180235b75  xor     r12d, r12d
0x180235b78  lea     rax, [rsp+3D0h+var_370]
0x180235b7d  mov     [rsp+3D0h+var_354], r15d
0x180235b82  mov     [rsp+3D0h+lpSecurityAttributes], rax
0x180235b87  mov     r9d, r15d
0x180235b8a  lea     rax, [rbp+2D0h+var_348]
0x180235b8e  mov     [rbp+2D0h+var_350], r12
0x180235b92  mov     qword ptr [rsp+3D0h+samDesired], rax
0x180235b97  xor     r8d, r8d
0x180235b9a  lea     rax, [rsp+3D0h+var_368]
0x180235b9f  mov     [rbp+2D0h+var_348], r12d
0x180235ba3  mov     rdx, rdi
0x180235ba6  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x180235bab  mov     ecx, r15d
0x180235bae  mov     [rsp+3D0h+var_370], r12
0x180235bb3  movups  [rsp+3D0h+var_368], xmm0
0x180235bb8  call    cs:__imp_DevGetObjectProperties
0x180235bbf  nop     dword ptr [rax+rax+00h]
0x180235bc4  test    eax, eax
0x180235bc6  js      short loc_180235C1C
0x180235bc8  mov     r8, [rsp+3D0h+var_370]
0x180235bcd  cmp     [rbp+2D0h+var_348], r15d
0x180235bd1  jnz     short loc_180235C0A
0x180235bd3  cmp     [r8+10h], r15d
0x180235bd7  jnz     short loc_180235C0A
0x180235bd9  lea     rdx, DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x180235be0  mov     rcx, r8
0x180235be3  call    IsEqualGUID
0x180235be8  test    eax, eax
0x180235bea  jz      short loc_180235C0A
0x180235bec  cmp     dword ptr [r8+20h], 0Dh
0x180235bf1  jnz     short loc_180235C0A
0x180235bf3  cmp     [r8+24h], r12d
0x180235bf7  jbe     short loc_180235C0A
0x180235bf9  mov     rax, [r8+28h]
0x180235bfd  test    rax, rax
0x180235c00  jz      short loc_180235C0A
0x180235c02  movups  xmm0, xmmword ptr [rax]
0x180235c05  movdqu  xmmword ptr [rbp+2D0h+pclsid.Data1], xmm0
0x180235c0a  mov     ecx, [rbp+2D0h+var_348]
0x180235c0d  mov     rdx, r8
0x180235c10  call    cs:__imp_DevFreeObjectProperties
0x180235c17  nop     dword ptr [rax+rax+00h]
0x180235c1c  lea     rdx, GUID_NULL
0x180235c23  lea     rcx, [rbp+2D0h+pclsid]
0x180235c27  call    __
0x180235c2c  test    al, al
0x180235c2e  jz      loc_180235CCA
0x180235c34  lea     r8, [rbp+2D0h+var_2F0]; unsigned __int16 *
0x180235c38  lea     rdx, [rbp+2D0h+sz]; unsigned __int16 *
0x180235c3c  call    ?_FindKnownCustomEventDeviceFromContainer@CAutoPlayParams@@AEAAJPEAG0_K@Z
0x180235c41  test    eax, eax
0x180235c43  js      short loc_180235C5B
0x180235c45  lea     rdx, [rbp+2D0h+pclsid]; pclsid
0x180235c49  lea     rcx, [rbp+2D0h+var_2F0]; lpsz
0x180235c4d  call    cs:__imp_CLSIDFromString
0x180235c54  nop     dword ptr [rax+rax+00h]
0x180235c59  jmp     short loc_180235C6B
0x180235c5b  lea     rcx, [rbp+2D0h+pclsid]; pguid
0x180235c5f  call    cs:__imp_CoCreateGuid
0x180235c66  nop     dword ptr [rax+rax+00h]
0x180235c6b  mov     ebx, eax
0x180235c6d  test    eax, eax
0x180235c6f  js      loc_180236224
0x180235c75  movups  xmm0, cs:DEVPKEY_DeviceInterface_AutoPlay_CustomEventGuid
0x180235c7c  lea     rax, [rbp+2D0h+pclsid]
0x180235c80  mov     dword ptr [rbp+2D0h+var_310], 0Dh
0x180235c87  mov     qword ptr [rbp+2D0h+var_310+8], rax
0x180235c8b  lea     r9, [rbp+2D0h+var_330]
0x180235c8f  mov     eax, cs:dword_180619570
0x180235c95  mov     r8d, r15d
0x180235c98  mov     rdx, rdi
0x180235c9b  mov     [rbp+2D0h+var_320], eax
0x180235c9e  mov     ecx, r15d
0x180235ca1  mov     dword ptr [rbp+2D0h+var_310+4], 10h
0x180235ca8  movups  [rbp+2D0h+var_330], xmm0
0x180235cac  mov     [rbp+2D0h+var_31C], r15d
0x180235cb0  mov     [rbp+2D0h+var_318], r12
0x180235cb4  call    cs:__imp_DevSetObjectProperties
0x180235cbb  nop     dword ptr [rax+rax+00h]
0x180235cc0  mov     ebx, eax
0x180235cc2  test    eax, eax
0x180235cc4  js      loc_180236224
0x180235cca  mov     r8d, esi; cchMax
0x180235ccd  lea     rdx, [rbp+2D0h+var_2F0]; lpsz
0x180235cd1  lea     rcx, [rbp+2D0h+pclsid]; rguid
0x180235cd5  call    cs:__imp_StringFromGUID2
0x180235cdc  nop     dword ptr [rax+rax+00h]
0x180235ce1  mov     eax, cs:DEVPKEY_NAME.pid
0x180235ce7  lea     rdx, [rbp+2D0h+sz]
0x180235ceb  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x180235cf2  mov     [rbp+2D0h+var_320], eax
0x180235cf5  mov     r9d, 2
0x180235cfb  mov     eax, cs:DEVPKEY_DeviceContainer_Icon.pid
0x180235d01  xor     r8d, r8d
0x180235d04  mov     [rbp+2D0h+var_300], eax
0x180235d07  mov     ecx, r9d
0x180235d0a  lea     rax, [rsp+3D0h+var_370]
0x180235d0f  movaps  [rbp+2D0h+var_330], xmm0
0x180235d13  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Icon.fmtid.Data1
0x180235d1a  mov     [rsp+3D0h+lpSecurityAttributes], rax
0x180235d1f  lea     rax, [rbp+2D0h+var_348]
0x180235d23  mov     qword ptr [rsp+3D0h+samDesired], rax
0x180235d28  lea     rax, [rbp+2D0h+var_330]
0x180235d2c  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x180235d31  mov     [rbp+2D0h+var_31C], r12d
0x180235d35  mov     [rbp+2D0h+var_318], r12
0x180235d39  movaps  [rbp+2D0h+var_310], xmm0
0x180235d3d  mov     [rbp+2D0h+var_2FC], r12d
0x180235d41  mov     [rbp+2D0h+var_2F8], r12
0x180235d45  call    cs:__imp_DevGetObjectProperties
0x180235d4c  nop     dword ptr [rax+rax+00h]
0x180235d51  mov     ebx, eax
0x180235d53  test    eax, eax
0x180235d55  js      loc_18023620B
0x180235d5b  cmp     [rbp+2D0h+var_348], 2
0x180235d5f  jnz     loc_1802361D8
0x180235d65  mov     [rsp+3D0h+lpData], r12
0x180235d6a  mov     ebx, r12d
0x180235d6d  mov     [rsp+3D0h+hKey], r12
0x180235d72  mov     eax, ebx
0x180235d74  lea     r8, [rax+rax*2]
0x180235d78  shl     r8, 4
0x180235d7c  add     r8, [rsp+3D0h+var_370]
0x180235d81  cmp     dword ptr [r8+10h], 0Ah
0x180235d86  jnz     short loc_180235DAB
0x180235d88  lea     rdx, DEVPKEY_NAME
0x180235d8f  mov     rcx, r8
0x180235d92  call    IsEqualGUID
0x180235d97  test    eax, eax
0x180235d99  jz      short loc_180235DD8
0x180235d9b  mov     r8, [r8+28h]
0x180235d9f  test    r8, r8
0x180235da2  jz      short loc_180235DD8
0x180235da4  lea     r9, [rsp+3D0h+lpData]
0x180235da9  jmp     short loc_180235DD3
0x180235dab  cmp     dword ptr [r8+10h], 39h ; '9'
0x180235db0  jnz     short loc_180235DD8
0x180235db2  lea     rdx, DEVPKEY_DeviceContainer_Icon
0x180235db9  mov     rcx, r8
0x180235dbc  call    IsEqualGUID
0x180235dc1  test    eax, eax
0x180235dc3  jz      short loc_180235DD8
0x180235dc5  mov     r8, [r8+28h]
0x180235dc9  test    r8, r8
0x180235dcc  jz      short loc_180235DD8
0x180235dce  lea     r9, [rsp+3D0h+hKey]
0x180235dd3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z
0x180235dd8  add     ebx, r15d
0x180235ddb  cmp     ebx, [rbp+2D0h+var_348]
0x180235dde  jb      short loc_180235D72
0x180235de0  mov     r14, [rsp+3D0h+lpData]
0x180235de5  mov     rsi, [rsp+3D0h+hKey]
0x180235dea  test    r14, r14
0x180235ded  jz      loc_180236185
0x180235df3  test    rsi, rsi
0x180235df6  jz      loc_180236185
0x180235dfc  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3
0x180235e03  lea     rcx, [rbp+2D0h+var_1AC]; void *
0x180235e0a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+10h
0x180235e11  xor     edx, edx; Val
0x180235e13  mov     eax, dword ptr cs:aSoftwareMicros_3+0A0h
0x180235e19  mov     r8d, 164h; Size
0x180235e1f  movups  xmmword ptr [rbp+2D0h+SubKey], xmm0
0x180235e26  mov     [rbp+2D0h+var_1B0], eax
0x180235e2c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+20h
0x180235e33  movups  [rbp+2D0h+var_240], xmm1
0x180235e3a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+30h
0x180235e41  movups  [rbp+2D0h+var_230], xmm0
0x180235e48  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+40h
0x180235e4f  movups  [rbp+2D0h+var_220], xmm1
0x180235e56  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+50h
0x180235e5d  movups  [rbp+2D0h+var_210], xmm0
0x180235e64  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+60h
0x180235e6b  movups  [rbp+2D0h+var_200], xmm1
0x180235e72  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+70h
0x180235e79  movups  [rbp+2D0h+var_1F0], xmm0
0x180235e80  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_3+80h
0x180235e87  movups  [rbp+2D0h+var_1E0], xmm1
0x180235e8e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_3+90h
0x180235e95  movups  [rbp+2D0h+var_1D0], xmm0
0x180235e9c  movups  [rbp+2D0h+var_1C0], xmm1
0x180235ea3  call    memset_0
0x180235ea8  lea     r8, [rbp+2D0h+var_2F0]; unsigned __int16 *
0x180235eac  mov     edx, 104h; unsigned __int64
0x180235eb1  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x180235eb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x180235ebd  mov     ebx, eax
0x180235ebf  test    eax, eax
0x180235ec1  js      loc_1802361B8
0x180235ec7  mov     [rsp+3D0h+lpdwDisposition], r12; lpdwDisposition
0x180235ecc  lea     rax, [rsp+3D0h+hKey]
0x180235ed1  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180235ed6  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180235edd  mov     [rsp+3D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180235ee2  xor     r9d, r9d; lpClass
0x180235ee5  mov     [rsp+3D0h+samDesired], 2001Fh; samDesired
0x180235eed  xor     r8d, r8d; Reserved
0x180235ef0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180235ef7  mov     [rsp+3D0h+dwOptions], r12d; dwOptions
0x180235efc  mov     [rsp+3D0h+hKey], r12
0x180235f01  call    cs:__imp_RegCreateKeyExW
0x180235f08  nop     dword ptr [rax+rax+00h]
0x180235f0d  mov     ebx, eax
0x180235f0f  test    eax, eax
0x180235f11  jle     short loc_180235F1C
0x180235f13  movzx   ebx, ax
0x180235f16  or      ebx, 80070000h
0x180235f1c  test    ebx, ebx
0x180235f1e  js      loc_1802361B8
0x180235f24  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180235f28  lea     rcx, [rbp+2D0h+sz]
0x180235f2c  mov     rax, rdi
0x180235f2f  inc     rax
0x180235f32  cmp     [rcx+rax*2], r12w
0x180235f37  jnz     short loc_180235F2F
0x180235f39  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180235f3e  lea     eax, ds:2[rax*2]
0x180235f45  mov     [rsp+3D0h+samDesired], eax; cbData
0x180235f49  lea     rdx, aContainerid
0x180235f50  lea     rax, [rbp+2D0h+sz]
0x180235f54  mov     r9d, r15d; dwType
0x180235f57  xor     r8d, r8d; Reserved
0x180235f5a  mov     qword ptr [rsp+3D0h+dwOptions], rax; lpData
0x180235f5f  call    cs:__imp_RegSetValueExW
0x180235f66  nop     dword ptr [rax+rax+00h]
0x180235f6b  mov     ebx, eax
0x180235f6d  test    eax, eax
0x180235f6f  jle     short loc_180235F7A
0x180235f71  movzx   ebx, ax
0x180235f74  or      ebx, 80070000h
0x180235f7a  test    ebx, ebx
0x180235f7c  js      loc_180236172
0x180235f82  mov     rax, [r13+20h]
0x180235f86  mov     rbx, rdi
0x180235f89  inc     rbx
0x180235f8c  cmp     [rax+rbx*2], r12w
0x180235f91  jnz     short loc_180235F89
0x180235f93  inc     rbx
0x180235f96  mov     eax, 2
0x180235f9b  mul     rbx
0x180235f9e  cmovb   rax, rdi
0x180235fa2  mov     rcx, rax; dwBytes
0x180235fa5  call    ??2@YAPEAX_K@Z
0x180235faa  mov     rcx, [rsp+3D0h+hKey]
0x180235faf  lea     r8, KeyName
0x180235fb6  mov     r9, rax
0x180235fb9  mov     [rsp+3D0h+dwOptions], ebx
0x180235fbd  xor     edx, edx
0x180235fbf  mov     r15, rax
0x180235fc2  call    cs:__imp_RegGetValueString
0x180235fc9  nop     dword ptr [rax+rax+00h]
0x180235fce  test    eax, eax
0x180235fd0  jz      short loc_180235FED
0x180235fd2  mov     rdx, [r13+20h]; psz2
0x180235fd6  mov     rcx, r15; psz1
0x180235fd9  call    cs:__imp_StrCmpIW
0x180235fe0  nop     dword ptr [rax+rax+00h]
0x180235fe5  test    eax, eax
0x180235fe7  jz      loc_180236079
0x180235fed  lea     rax, [rbp+2D0h+var_2F0]
0x180235ff1  mov     ebx, 104h
0x180235ff6  mov     edx, ebx; unsigned __int64
0x180235ff8  mov     qword ptr [rsp+3D0h+dwOptions], rax
0x180235ffd  lea     r9, aUserchosenexec
0x180236004  lea     r8, aSoftwareMicros_63
0x18023600b  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x180236012  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x180236017  test    eax, eax
0x180236019  js      short loc_180236035
0x18023601b  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180236022  mov     rcx, 0FFFFFFFF80000001h; hKey
  ... truncated ...
```
