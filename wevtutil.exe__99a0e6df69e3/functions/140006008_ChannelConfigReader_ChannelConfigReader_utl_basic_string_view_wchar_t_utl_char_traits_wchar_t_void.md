# ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)

- ea: `0x140006008`
- end: `0x140006a2a`
- name: `??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z`
- size: `2594`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140005f20`
- `0x14001d828`
- `0x14002d8e4`
- `0x14002daf0`
- `0x14002ddb0`
- `0x14002e018`

## callees

- `0x140003700`
- `0x1400039a0`
- `0x140004ae0`
- `0x140005600`
- `0x140006008`
- `0x140006cd0`
- `0x140006db0`
- `0x140007310`
- `0x140007fd0`
- `0x14000d6e8`
- `0x140016284`
- `0x14001a9b8`
- `0x140022510`
- `0x140022cec`
- `0x14002ba80`
- `0x14002c5c8`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006427`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006427`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140006201`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14000641a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140006201`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14000641a`

## string_xrefs

- `0x140006337`: `SYSTEM\CurrentControlSet\Services\Eventlog`
- `0x1400062ef`: `\ControlSet001\services\eventlog`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ChannelConfigReader::ChannelConfigReader(__int64 a1, __int128 *a2, __int64 a3)
{
  _WORD **v5; // rsi
  const char *v6; // r8
  _WORD *v7; // rax
  __int64 v8; // rdx
  _WORD *v9; // rcx
  unsigned __int64 v10; // r8
  HKEY v11; // rbx
  void *hTransaction; // rdi
  HKEY *phkResult; // rax
  unsigned int v14; // eax
  unsigned int v15; // edi
  __int16 v16; // r8
  _WORD *v17; // r12
  __int64 v18; // rbx
  PVOID *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  void *v22; // rbx
  HKEY *v23; // rax
  unsigned int v24; // eax
  const char *v25; // r8
  unsigned int v26; // edi
  const char *v27; // r8
  void *v28; // rbx
  HKEY *v29; // rax
  unsigned int v30; // edi
  const char *v31; // r8
  __int64 v32; // r8
  __int64 v33; // r9
  const char *v34; // r8
  void *v35; // rbx
  HKEY *v36; // rax
  PVOID *v37; // rcx
  int DWORDHelper; // eax
  const char *v39; // r8
  PVOID *v41; // rcx
  __int128 pExceptionObject; // [rsp+40h] [rbp-99h] BYREF
  __int64 v43; // [rsp+50h] [rbp-89h]
  int v44; // [rsp+58h] [rbp-81h]
  __int64 v45; // [rsp+5Ch] [rbp-7Dh]
  char v46; // [rsp+64h] [rbp-75h]
  LPCWSTR v47[2]; // [rsp+70h] [rbp-69h] BYREF
  char v48; // [rsp+80h] [rbp-59h] BYREF
  void *v49; // [rsp+90h] [rbp-49h] BYREF
  const char *v50; // [rsp+98h] [rbp-41h]
  char v51; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v52[40]; // [rsp+B0h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+D8h] [rbp-1h] BYREF
  char v54; // [rsp+E8h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+148h] [rbp+6Fh]
  _QWORD *v56; // [rsp+150h] [rbp+77h]

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = a3;
  v5 = (_WORD **)(a1 + 32);
  v56 = (_QWORD *)(a1 + 32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a1 + 32);
  memset_0((void *)(a1 + 64), 0, 0x48u);
  *(_DWORD *)(a1 + 136) = 0;
  *(_BYTE *)(a1 + 140) = 0;
  pExceptionObject = *a2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v5,
                           &pExceptionObject) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v6, 100);
    throw (EvtException *)&pExceptionObject;
  }
  v7 = *v5;
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  if ( !v8 || (unsigned __int64)(v8 + 1) > 0x100 )
  {
LABEL_127:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 15000);
    }
    *(_QWORD *)&pExceptionObject = word_14003838A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v43 = 0;
    v44 = 15000;
    v45 = -1;
    v46 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v9 = &v7[v8];
  while ( v7 != v9 )
  {
    if ( *v7 <= 0x3Fu )
    {
      v10 = 0xD40004C4FFFFFFFFuLL;
      if ( _bittest64((const __int64 *)&v10, (unsigned __int16)*v7) )
        goto LABEL_127;
    }
    if ( *v7 == 92 || *v7 == 124 )
      goto LABEL_127;
    ++v7;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v49);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpSubKey,
                           qword_1400421D0,
                           (qword_1400421D8 - qword_1400421D0) >> 1)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           lpSubKey,
                           L"\\Microsoft\\Windows\\CurrentVersion\\WINEVT",
                           40) )
  {
    v41 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_102b51fcdce430aa865b164defc92936_Traceguids, 14);
        v41 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 4) != 0 && *((_BYTE *)v41 + 25) >= 2u )
        WPP_SF_d(v41[2], 18, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
    }
    *(_QWORD *)&pExceptionObject = word_14003838A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v43 = 0;
    v44 = 14;
    v45 = -1;
    v46 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v50 = (const char *)v49;
  *(_WORD *)v49 = 0;
  v11 = ::hKey;
  hTransaction = *(void **)(a1 + 24);
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1 + 8);
  if ( hTransaction == (void *)-1LL )
    v14 = RegOpenKeyExW(v11, lpSubKey[0], 0, 0x20019u, phkResult);
  else
    v14 = RegOpenKeyTransactedW(v11, lpSubKey[0], 0, 0x20019u, phkResult, hTransaction, 0);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v14);
    }
    *(_QWORD *)&pExceptionObject = word_14003838A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v43 = 0;
    v44 = v15;
    v45 = -1;
    v46 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  v17 = *v5;
  v18 = -1;
  do
    ++v18;
  while ( v17[v18] != v16 );
  if ( byte_140042230 == (_BYTE)v16 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v47,
                             L"SYSTEM\\CurrentControlSet\\Services\\Eventlog",
                             42) )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_117;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_44;
      v20 = 12;
      goto LABEL_43;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v47,
                                qword_1400421F0,
                                (qword_1400421F8 - qword_1400421F0) >> 1)
         || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                v47,
                                L"\\ControlSet001\\services\\eventlog",
                                32) )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_117;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_44;
    v20 = 11;
LABEL_43:
    WPP_SF_d(v19[2], v20, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids, 14);
    v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_44:
    if ( v19 == &WPP_GLOBAL_Control )
      goto LABEL_117;
    if ( (*((_BYTE *)v19 + 28) & 4) == 0 || *((_BYTE *)v19 + 25) < 2u )
      goto LABEL_113;
    v21 = 13;
    goto LABEL_112;
  }
  hKey = (HKEY)qword_140042240;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           v47,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v47,
                           v17,
                           v18) )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_117;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_113:
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 2u )
        WPP_SF_d(v19[2], 20, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
LABEL_117:
      *(_QWORD *)&pExceptionObject = word_14003838A;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v43 = 0;
      v44 = 14;
      v45 = -1;
      v46 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    v21 = 14;
LABEL_112:
    WPP_SF_d(v19[2], v21, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids, 14);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_113;
  }
  v22 = *(void **)(a1 + 24);
  v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1);
  if ( v22 == (void *)-1LL )
    v24 = RegOpenKeyExW(hKey, v47[0], 0, 0x20019u, v23);
  else
    v24 = RegOpenKeyTransactedW(hKey, v47[0], 0, 0x20019u, v23, v22, 0);
  v26 = v24;
  if ( !v24 )
  {
    *(_BYTE *)(a1 + 140) = 1;
    *(_DWORD *)(a1 + 136) = 0;
    if ( (char *)v47[0] != &v48 )
      operator delete((void *)v47[0]);
    if ( v49 != &v51 )
      operator delete(v49);
    if ( (char *)lpSubKey[0] != &v54 )
      operator delete((void *)lpSubKey[0]);
    return a1;
  }
  if ( v24 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v24);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v26, v25, 131);
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v47,
                           L"Channels\\")
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v47,
                           *(_QWORD *)(a1 + 32),
                           (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32)) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)v52, 0xEu, v27, 140);
    throw (EvtException *)v52;
  }
  *(_BYTE *)(a1 + 140) = 2;
  v28 = *(void **)(a1 + 24);
  v29 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1);
  v30 = OpenRegKey(*(HKEY *)(a1 + 8), v47[0], 0x20019u, v29, v28);
  if ( v30 == 2 )
  {
    v31 = v50;
    if ( v49 == v50 )
      goto LABEL_76;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &pExceptionObject,
                             v33,
                             (v32 - v33) >> 1)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &pExceptionObject,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &pExceptionObject,
                             v47[0],
                             v47[1] - v47[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)v52, 0xEu, v34, 154);
      throw (EvtException *)v52;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v47, &pExceptionObject);
    v35 = *(void **)(a1 + 24);
    v36 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1);
    v30 = OpenRegKey(hKey, v47[0], 0x20019u, v36, v35);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
  }
  if ( v30 )
  {
    if ( v30 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v30);
      }
      EvtException::EvtException((EvtException *)v52, v30, v31, 170);
      throw (EvtException *)v52;
    }
LABEL_76:
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
          *v56,
          (__int64)v47[0]);
        v37 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 4) != 0 && *((_BYTE *)v37 + 25) >= 2u )
        WPP_SF_d(v37[2], 25, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 15007);
    }
    EvtException::EvtException((EvtException *)v52, 0x3A9Fu, v31, 167);
    throw (EvtException *)v52;
  }
  DWORDHelper = GetDWORDHelper(*(_QWORD *)a1, 1, L"Type");
  *(_DWORD *)(a1 + 136) = DWORDHelper;
  if ( DWORDHelper > 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)v52, 0xDu, v39, 176);
    throw (EvtException *)v52;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v49);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x140006008  mov     [rsp-8+arg_18], rbx
0x14000600d  mov     [rsp-8+arg_0], rcx
0x140006012  push    rbp
0x140006013  push    rsi
0x140006014  push    rdi
0x140006015  push    r12
0x140006017  push    r13
0x140006019  push    r14
0x14000601b  push    r15
0x14000601d  lea     rbp, [rsp-27h]
0x140006022  sub     rsp, 100h
0x140006029  mov     rbx, rdx
0x14000602c  mov     r15, rcx
0x14000602f  xor     r13d, r13d
0x140006032  mov     [rcx], r13
0x140006035  mov     [rcx+8], r13
0x140006039  mov     [rcx+10h], r13
0x14000603d  mov     [rcx+18h], r8
0x140006041  lea     rsi, [rcx+20h]
0x140006045  mov     [rbp+57h+arg_10], rsi
0x140006049  mov     rcx, rsi
0x14000604c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140006051  nop
0x140006052  lea     rcx, [r15+40h]; void *
0x140006056  xor     edx, edx; Val
0x140006058  lea     r8d, [r13+48h]; Size
0x14000605c  call    memset_0
0x140006061  nop
0x140006062  mov     [r15+88h], r13d
0x140006069  mov     [r15+8Ch], r13b
0x140006070  movaps  xmm0, xmmword ptr [rbx]
0x140006073  movdqa  [rsp+130h+pExceptionObject], xmm0
0x140006079  lea     rdx, [rsp+130h+pExceptionObject]
0x14000607e  mov     rcx, rsi
0x140006081  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140006086  test    al, al
0x140006088  jnz     short loc_1400060EE
0x14000608a  lea     rbx, WPP_GLOBAL_Control
0x140006091  lea     edi, [r13+0Eh]
0x140006095  mov     rcx, cs:WPP_GLOBAL_Control
0x14000609c  cmp     rcx, rbx
0x14000609f  jz      short loc_1400060CA
0x1400060a1  mov     sil, 4
0x1400060a4  test    [rcx+1Ch], sil
0x1400060a8  jz      short loc_1400060CA
0x1400060aa  lea     r14d, [r13+2]
0x1400060ae  cmp     [rcx+19h], r14b
0x1400060b2  jb      short loc_1400060CA
0x1400060b4  lea     edx, [rdi+2]
0x1400060b7  mov     r9d, edi
0x1400060ba  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x1400060c1  mov     rcx, [rcx+10h]
0x1400060c5  call    WPP_SF_d
0x1400060ca  mov     r9d, 64h ; 'd'; int
0x1400060d0  mov     edx, edi; unsigned int
0x1400060d2  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1400060d7  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400060dc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400060e3  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1400060e8  call    _CxxThrowException_0
0x1400060ee  mov     rax, [rsi]
0x1400060f1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400060f5  inc     rdx
0x1400060f8  cmp     [rax+rdx*2], r13w
0x1400060fd  jnz     short loc_1400060F5
0x1400060ff  mov     r14d, 2
0x140006105  test    rdx, rdx
0x140006108  jz      loc_1400069B3
0x14000610e  lea     rcx, [rdx+1]
0x140006112  cmp     rcx, 100h
0x140006119  ja      loc_1400069B3
0x14000611f  lea     rcx, [rax+rdx*2]
0x140006123  lea     r9d, [r14+5Ah]
0x140006127  cmp     rax, rcx
0x14000612a  jz      short loc_140006162
0x14000612c  cmp     word ptr [rax], 3Fh ; '?'
0x140006130  ja      short loc_140006149
0x140006132  movzx   edx, word ptr [rax]
0x140006135  mov     r8, 0D40004C4FFFFFFFFh
0x14000613f  bt      r8, rdx
0x140006143  jb      loc_1400069B3
0x140006149  cmp     [rax], r9w
0x14000614d  jz      loc_1400069B3
0x140006153  cmp     word ptr [rax], 7Ch ; '|'
0x140006157  jz      loc_1400069B3
0x14000615d  add     rax, r14
0x140006160  jmp     short loc_140006127
0x140006162  lea     rcx, [rbp+57h+lpSubKey]
0x140006166  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000616b  nop
0x14000616c  lea     rcx, [rbp+57h+var_A0]
0x140006170  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140006175  nop
0x140006176  mov     rdx, cs:qword_1400421D0
0x14000617d  mov     r8, cs:qword_1400421D8
0x140006184  sub     r8, rdx
0x140006187  sar     r8, 1
0x14000618a  lea     rcx, [rbp+57h+lpSubKey]
0x14000618e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140006193  test    al, al
0x140006195  jz      loc_14000690F
0x14000619b  mov     r8d, 28h ; '('
0x1400061a1  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\CurrentVersion\\W"...
0x1400061a8  lea     rcx, [rbp+57h+lpSubKey]
0x1400061ac  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400061b1  test    al, al
0x1400061b3  jz      loc_14000690F
0x1400061b9  mov     rcx, [rbp+57h+var_A0]
0x1400061bd  mov     [rbp+57h+var_98], rcx
0x1400061c1  mov     [rcx], r13w
0x1400061c5  mov     rbx, cs:hKey
0x1400061cc  mov     rdi, [r15+18h]
0x1400061d0  lea     rcx, [r15+8]
0x1400061d4  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400061d9  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400061dd  xor     r8d, r8d; ulOptions
0x1400061e0  mov     rcx, rbx; hKey
0x1400061e3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400061e7  jz      short loc_140006209
0x1400061e9  mov     [rsp+130h+pExtendedParemeter], r13; pExtendedParemeter
0x1400061ee  mov     [rsp+130h+hTransaction], rdi; hTransaction
0x1400061f3  mov     [rsp+130h+phkResult], rax; phkResult
0x1400061f8  mov     r13d, 20019h
0x1400061fe  mov     r9d, r13d; samDesired
0x140006201  call    cs:__imp_RegOpenKeyTransactedW
0x140006207  jmp     short loc_14000621D
0x140006209  mov     [rsp+130h+phkResult], rax; phkResult
0x14000620e  mov     r13d, 20019h
0x140006214  mov     r9d, r13d; samDesired
0x140006217  call    cs:__imp_RegOpenKeyExW
0x14000621d  mov     edi, eax
0x14000621f  xor     r8d, r8d
0x140006222  test    eax, eax
0x140006224  jz      short loc_14000629E
0x140006226  lea     rbx, WPP_GLOBAL_Control
0x14000622d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006234  cmp     rcx, rbx
0x140006237  jz      short loc_140006262
0x140006239  mov     sil, 4
0x14000623c  test    [rcx+1Ch], sil
0x140006240  jz      short loc_140006262
0x140006242  cmp     [rcx+19h], r14b
0x140006246  jb      short loc_140006262
0x140006248  lea     edx, [r8+13h]
0x14000624c  mov     r9d, eax
0x14000624f  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140006256  mov     rcx, [rcx+10h]
0x14000625a  call    WPP_SF_d
0x14000625f  xor     r8d, r8d
0x140006262  lea     rax, word_14003838A
0x140006269  mov     qword ptr [rsp+130h+pExceptionObject], rax
0x14000626e  mov     qword ptr [rsp+130h+pExceptionObject+8], r8
0x140006273  mov     [rsp+130h+var_E0], 0
0x14000627c  mov     [rsp+130h+var_D8], edi
0x140006280  mov     [rbp+57h+var_D4], 0FFFFFFFFFFFFFFFFh
0x140006288  mov     [rbp+57h+var_CC], r8b
0x14000628c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006293  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140006298  call    _CxxThrowException_0
0x14000629e  lea     rcx, [rbp+57h+var_C0]
0x1400062a2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400062a7  nop
0x1400062a8  mov     r12, [rsi]
0x1400062ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400062af  inc     rbx
0x1400062b2  cmp     [r12+rbx*2], r8w
0x1400062b7  jnz     short loc_1400062AF
0x1400062b9  mov     edi, 0Eh
0x1400062be  mov     sil, 4
0x1400062c1  lea     rcx, [rbp+57h+var_C0]
0x1400062c5  cmp     cs:byte_140042230, r8b
0x1400062cc  jz      short loc_140006331
0x1400062ce  mov     rdx, cs:qword_1400421F0
0x1400062d5  mov     r8, cs:qword_1400421F8
0x1400062dc  sub     r8, rdx
0x1400062df  sar     r8, 1
0x1400062e2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400062e7  test    al, al
0x1400062e9  jz      short loc_140006307
0x1400062eb  lea     r8d, [rdi+12h]
0x1400062ef  lea     rdx, aControlset001S; "\\ControlSet001\\services\\eventlog"
0x1400062f6  lea     rcx, [rbp+57h+var_C0]
0x1400062fa  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400062ff  test    al, al
0x140006301  jnz     loc_1400063B0
0x140006307  lea     rbx, WPP_GLOBAL_Control
0x14000630e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006315  cmp     rcx, rbx
0x140006318  jz      loc_1400068D6
0x14000631e  test    [rcx+1Ch], sil
0x140006322  jz      short loc_140006389
0x140006324  cmp     [rcx+19h], r14b
0x140006328  jb      short loc_140006389
0x14000632a  mov     edx, 0Bh
0x14000632f  jmp     short loc_14000636F
0x140006331  mov     r8d, 2Ah ; '*'
0x140006337  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x14000633e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140006343  test    al, al
0x140006345  jnz     short loc_1400063B0
0x140006347  lea     rbx, WPP_GLOBAL_Control
0x14000634e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006355  cmp     rcx, rbx
0x140006358  jz      loc_1400068D6
0x14000635e  test    [rcx+1Ch], sil
0x140006362  jz      short loc_140006389
0x140006364  cmp     [rcx+19h], r14b
0x140006368  jb      short loc_140006389
0x14000636a  mov     edx, 0Ch
0x14000636f  mov     r9d, edi
0x140006372  lea     r8, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids
0x140006379  mov     rcx, [rcx+10h]
0x14000637d  call    WPP_SF_d
0x140006382  mov     rcx, cs:WPP_GLOBAL_Control
0x140006389  cmp     rcx, rbx
0x14000638c  jz      loc_1400068D6
0x140006392  test    [rcx+1Ch], sil
0x140006396  jz      loc_1400068AD
0x14000639c  cmp     [rcx+19h], r14b
0x1400063a0  jb      loc_1400068AD
0x1400063a6  mov     edx, 0Dh
0x1400063ab  jmp     loc_140006893
0x1400063b0  mov     rax, cs:qword_140042240
0x1400063b7  mov     [rbp+57h+hKey], rax
0x1400063bb  mov     edx, 5Ch ; '\'
0x1400063c0  lea     rcx, [rbp+57h+var_C0]
0x1400063c4  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400063c9  test    al, al
0x1400063cb  jz      loc_140006872
0x1400063d1  mov     r8, rbx
0x1400063d4  mov     rdx, r12
0x1400063d7  lea     rcx, [rbp+57h+var_C0]
0x1400063db  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400063e0  test    al, al
0x1400063e2  jz      loc_140006872
0x1400063e8  mov     rbx, [r15+18h]
0x1400063ec  mov     rcx, r15
0x1400063ef  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400063f4  mov     rdx, [rbp+57h+var_C0]; lpSubKey
0x1400063f8  mov     r9d, r13d; samDesired
0x1400063fb  xor     r8d, r8d; ulOptions
0x1400063fe  mov     r12, [rbp+57h+hKey]
0x140006402  mov     rcx, r12; hKey
0x140006405  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140006409  jz      short loc_140006422
0x14000640b  mov     [rsp+130h+pExtendedParemeter], r8; pExtendedParemeter
0x140006410  mov     [rsp+130h+hTransaction], rbx; hTransaction
0x140006415  mov     [rsp+130h+phkResult], rax; phkResult
0x14000641a  call    cs:__imp_RegOpenKeyTransactedW
0x140006420  jmp     short loc_14000642D
0x140006422  mov     [rsp+130h+phkResult], rax; phkResult
0x140006427  call    cs:__imp_RegOpenKeyExW
0x14000642d  mov     edi, eax
0x14000642f  test    eax, eax
0x140006431  jnz     short loc_140006483
0x140006433  mov     byte ptr [r15+8Ch], 1
0x14000643b  mov     [r15+88h], eax
0x140006442  lea     rax, [rbp+57h+var_B0]
0x140006446  mov     rcx, [rbp+57h+var_C0]; void *
0x14000644a  cmp     rcx, rax
0x14000644d  jz      short loc_140006455
0x14000644f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006454  nop
0x140006455  lea     rax, [rbp+57h+var_90]
0x140006459  mov     rcx, [rbp+57h+var_A0]; void *
0x14000645d  cmp     rcx, rax
0x140006460  jz      short loc_140006468
0x140006462  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006467  nop
0x140006468  lea     rax, [rbp+57h+var_48]
0x14000646c  mov     rcx, [rbp+57h+lpSubKey]; void *
0x140006470  cmp     rcx, rax
0x140006473  jz      loc_1400067F8
0x140006479  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000647e  jmp     loc_1400067F8
0x140006483  cmp     edi, r14d
0x140006486  jz      short loc_1400064E3
0x140006488  lea     rbx, WPP_GLOBAL_Control
0x14000648f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006496  cmp     rcx, rbx
0x140006499  jz      short loc_1400064BF
0x14000649b  test    [rcx+1Ch], sil
0x14000649f  jz      short loc_1400064BF
0x1400064a1  cmp     [rcx+19h], r14b
0x1400064a5  jb      short loc_1400064BF
0x1400064a7  mov     edx, 15h
0x1400064ac  mov     r9d, edi
0x1400064af  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x1400064b6  mov     rcx, [rcx+10h]
0x1400064ba  call    WPP_SF_d
0x1400064bf  mov     r9d, 83h; int
0x1400064c5  mov     edx, edi; unsigned int
0x1400064c7  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1400064cc  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400064d1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400064d8  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1400064dd  call    _CxxThrowException_0
0x1400064e3  lea     rdx, aChannels_0; "Channels\\"
0x1400064ea  lea     rcx, [rbp+57h+var_C0]
0x1400064ee  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
  ... truncated ...
```
