# ChannelConfigWriter::ChannelConfigWriter(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,ulong,bool,void *)

- ea: `0x14002bd08`
- end: `0x14002c5ac`
- name: `??0ChannelConfigWriter@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_NPEAX@Z`
- size: `2212`
- prototype: `__int64 __fastcall(int, int, int, int, HKEY)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1400178bc`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140006db0`
- `0x140007fd0`
- `0x14000a4d8`
- `0x14000cc80`
- `0x14000d62c`
- `0x14000d6e8`
- `0x140016438`
- `0x14001650c`
- `0x140019094`
- `0x140019348`
- `0x140022cec`
- `0x140023c6c`
- `0x14002bd08`
- `0x14002c5c8`
- `0x14002c664`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002bf88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c1d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002bf88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c1d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14002c3af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14002c3af`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14002c3a4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14002c3a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ChannelConfigWriter::ChannelConfigWriter(__int64 a1, _OWORD *a2, int a3, char a4, HKEY a5)
{
  __int64 v9; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v11; // ebx
  void *v12; // rbx
  HKEY *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int LegacyChannelRegPath; // eax
  unsigned int v17; // ebx
  char v18; // r15
  void *v19; // rbx
  HKEY *v20; // rax
  HKEY v21; // rbx
  const char *v22; // r8
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  const char *v26; // r8
  void *v27; // rbx
  HKEY *v28; // rax
  int v29; // r13d
  int v30; // r13d
  const char *v31; // r8
  PVOID *v32; // rcx
  void *v33; // rax
  unsigned int v34; // eax
  const char *v35; // r8
  unsigned int v36; // ebx
  void *v37; // rbx
  HKEY *v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // ebx
  HANDLE hTransaction; // [rsp+20h] [rbp-E0h]
  HANDLE hTransactiona; // [rsp+20h] [rbp-E0h]
  __int16 *v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h]
  unsigned int v47; // [rsp+58h] [rbp-A8h]
  int v48; // [rsp+5Ch] [rbp-A4h]
  int v49; // [rsp+60h] [rbp-A0h]
  char v50; // [rsp+64h] [rbp-9Ch]
  __int16 *pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  unsigned int v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+84h] [rbp-7Ch]
  int v56; // [rsp+88h] [rbp-78h]
  char v57; // [rsp+8Ch] [rbp-74h]
  wchar_t *v58[2]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v60; // [rsp+D0h] [rbp-30h]
  wchar_t *v61[4]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v62[88]; // [rsp+F8h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v64; // [rsp+178h] [rbp+78h] BYREF

  ChannelConfigWriteData::ChannelConfigWriteData((ChannelConfigWriteData *)a1);
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = a5;
  *(_OWORD *)v58 = *a2;
  v60 = (_QWORD *)(a1 + 280);
  MakeOrThrowOOM(a1 + 280, v58);
  *(_QWORD *)(a1 + 312) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a1 + 320);
  *(_BYTE *)(a1 + 352) = 0;
  *(_BYTE *)(a1 + 353) = a4;
  a5 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v61);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v62);
  WinevtRegPath = RegistryPaths::GetWinevtRegPath(v9, &a5, v61, v62);
  v11 = WinevtRegPath;
  if ( WinevtRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, WinevtRegPath);
    }
    pExceptionObject = word_14003838A;
    v52 = 0;
    v53 = 0;
    v54 = v11;
    v55 = -1;
    v56 = -1;
    v57 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v12 = *(void **)(a1 + 272);
  v13 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1 + 264);
  OpenRegKey(a5, v61[0], 0x20019u, v13, v12);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v14 = *(_QWORD *)(a1 + 280);
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v14 + 2 * v15) );
  v58[0] = *(wchar_t **)(a1 + 280);
  v58[1] = (wchar_t *)v15;
  LegacyChannelRegPath = RegistryPaths::GetLegacyChannelRegPath(v14, v58, &a5, lpSubKey);
  v17 = LegacyChannelRegPath;
  if ( LegacyChannelRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids,
        LegacyChannelRegPath);
    }
    pExceptionObject = word_14003838A;
    v52 = 0;
    v53 = 0;
    v54 = v17;
    v55 = -1;
    v56 = -1;
    v57 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v18 = 0;
  hKey = 0;
  v19 = *(void **)(a1 + 272);
  v20 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  hTransaction = v19;
  v21 = a5;
  if ( !OpenRegKey(a5, lpSubKey[0], 0x20019u, v20, hTransaction) )
  {
    *(_BYTE *)(a1 + 352) = 1;
    if ( (unsigned int)(a3 - 2) <= 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&v44, 0x57u, v22, 61);
      throw (EvtException *)&v44;
    }
    v18 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v18
    || *(_BYTE *)(a1 + 353)
    && (v58[0] = *(wchar_t **)(a1 + 280),
        v58[1] = (wchar_t *)((__int64)(*(_QWORD *)(a1 + 288) - (unsigned __int64)v58[0]) >> 1),
        !(unsigned __int8)IsCoreChannel(v58)) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v58);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    v24 = RegistryPaths::GetWinevtRegPath(v23, &a5, v58, &pExceptionObject);
    v25 = v24;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, v24);
      }
      v44 = word_14003838A;
      v45 = 0;
      v46 = 0;
      v47 = v25;
      v48 = -1;
      v49 = -1;
      v50 = 0;
      throw (EvtException *)&v44;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v58,
                             L"\\Channels\\",
                             10)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v58,
                             *(_QWORD *)(a1 + 280),
                             (__int64)(*(_QWORD *)(a1 + 288) - *(_QWORD *)(a1 + 280)) >> 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&v44, 0xEu, v26, 85);
      throw (EvtException *)&v44;
    }
    hKey = 0;
    v27 = *(void **)(a1 + 272);
    v28 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    hTransactiona = v27;
    v21 = a5;
    if ( OpenRegKey(a5, v58[0], 0x20019u, v28, hTransactiona) )
    {
      if ( v18 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x5B, *v60);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_dcf685af8c5436a5470889b599bac37f_Traceguids,
              183,
              (__int64)lpSubKey[0]);
            v32 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 && *((_BYTE *)v32 + 25) >= 2u )
            WPP_SF_d(v32[2], 17, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 183);
        }
        EvtException::EvtException((EvtException *)&v44, 0xB7u, v31, 116);
        throw (EvtException *)&v44;
      }
    }
    else
    {
      if ( v18 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x5C, *(_QWORD *)(a1 + 280));
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids);
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a1 + 320, lpSubKey);
        *(_QWORD *)(a1 + 312) = v21;
      }
      v18 = 1;
    }
    *(_BYTE *)(a1 + 352) = 2;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(lpSubKey, v58);
    if ( hKey )
      RegCloseKey(hKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v58);
  }
  if ( a3 )
  {
    v29 = a3 - 1;
    if ( v29 )
    {
      v30 = v29 - 1;
      if ( v30 )
      {
        if ( v30 != 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 87);
          }
          EvtException::EvtException((EvtException *)&v44, 0x57u, v22, 161);
          throw (EvtException *)&v44;
        }
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 183);
          }
          EvtException::EvtException((EvtException *)&v44, 0xB7u, v22, 131);
          throw (EvtException *)&v44;
        }
      }
      else if ( v18 )
      {
        v33 = *(void **)(a1 + 272);
        v34 = v33 == (void *)-1LL
            ? RegDeleteKeyExW(v21, lpSubKey[0], 0, 0)
            : RegDeleteKeyTransactedW(v21, lpSubKey[0], 0, 0, v33, 0);
        v36 = v34;
        if ( v34 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, v34);
          }
          EvtException::EvtException((EvtException *)&v44, v36, v35, 148);
          throw (EvtException *)&v44;
        }
      }
    }
    else if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, 2);
      }
      EvtException::EvtException((EvtException *)&v44, 2u, v22, 157);
      throw (EvtException *)&v44;
    }
  }
  v64 = 0;
  v37 = *(void **)(a1 + 272);
  v38 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1 + 256);
  v39 = CreateRegKey(a5, lpSubKey[0], 0x2001Fu, 0, v38, &v64, v37);
  v40 = v39;
  if ( v39 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids, v39);
    }
    v44 = word_14003838A;
    v45 = 0;
    v46 = 0;
    v47 = v40;
    v48 = -1;
    v49 = -1;
    v50 = 0;
    throw (EvtException *)&v44;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v62);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v61);
  return a1;
}

```

## disassembly

```asm
0x14002bd08  mov     [rsp-8+arg_10], rbx
0x14002bd0d  mov     [rsp-8+arg_0], rcx
0x14002bd12  push    rbp
0x14002bd13  push    rsi
0x14002bd14  push    rdi
0x14002bd15  push    r12
0x14002bd17  push    r13
0x14002bd19  push    r14
0x14002bd1b  push    r15
0x14002bd1d  lea     rbp, [rsp-20h]
0x14002bd22  sub     rsp, 120h
0x14002bd29  mov     dil, r9b
0x14002bd2c  mov     r13d, r8d
0x14002bd2f  mov     rbx, rdx
0x14002bd32  mov     r14, rcx
0x14002bd35  call    ??0ChannelConfigWriteData@@AEAA@XZ; ChannelConfigWriteData::ChannelConfigWriteData(void)
0x14002bd3a  nop
0x14002bd3b  xor     r12d, r12d
0x14002bd3e  mov     [r14+100h], r12
0x14002bd45  lea     r15, [r14+108h]
0x14002bd4c  mov     [r15], r12
0x14002bd4f  mov     rax, [rbp+50h+arg_20]
0x14002bd56  mov     [r14+110h], rax
0x14002bd5d  movaps  xmm0, xmmword ptr [rbx]
0x14002bd60  movdqa  xmmword ptr [rbp+50h+var_C0], xmm0
0x14002bd65  lea     rsi, [r14+118h]
0x14002bd6c  mov     [rbp+50h+var_80], rsi
0x14002bd70  lea     rdx, [rbp+50h+var_C0]
0x14002bd74  mov     rcx, rsi
0x14002bd77  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002bd7c  nop
0x14002bd7d  mov     [r14+138h], r12
0x14002bd84  lea     rcx, [r14+140h]
0x14002bd8b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002bd90  nop
0x14002bd91  mov     [r14+160h], r12b
0x14002bd98  mov     [r14+161h], dil
0x14002bd9f  mov     [rbp+50h+arg_20], r12
0x14002bda6  lea     rcx, [rbp+50h+var_78]
0x14002bdaa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002bdaf  nop
0x14002bdb0  lea     rcx, [rbp+50h+var_58]
0x14002bdb4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002bdb9  nop
0x14002bdba  lea     r9, [rbp+50h+var_58]
0x14002bdbe  lea     r8, [rbp+50h+var_78]
0x14002bdc2  lea     rdx, [rbp+50h+arg_20]
0x14002bdc9  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002bdce  mov     ebx, eax
0x14002bdd0  test    eax, eax
0x14002bdd2  jz      short loc_14002BE49
0x14002bdd4  lea     rdi, WPP_GLOBAL_Control
0x14002bddb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bde2  cmp     rcx, rdi
0x14002bde5  jz      short loc_14002BE0B
0x14002bde7  test    byte ptr [rcx+1Ch], 4
0x14002bdeb  jz      short loc_14002BE0B
0x14002bded  cmp     byte ptr [rcx+19h], 2
0x14002bdf1  jb      short loc_14002BE0B
0x14002bdf3  lea     edx, [r12+0Ah]
0x14002bdf8  mov     r9d, eax
0x14002bdfb  lea     r8, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids
0x14002be02  mov     rcx, [rcx+10h]
0x14002be06  call    WPP_SF_d
0x14002be0b  lea     rax, word_14003838A
0x14002be12  mov     [rsp+150h+pExceptionObject], rax
0x14002be17  mov     [rsp+150h+var_E0], r12
0x14002be1c  mov     [rsp+150h+var_D8], r12
0x14002be21  mov     [rbp+50h+var_D0], ebx
0x14002be24  mov     [rbp+50h+var_CC], 0FFFFFFFFh
0x14002be2b  or      r12, 0FFFFFFFFFFFFFFFFh
0x14002be2f  mov     [rbp+50h+var_C8], r12d
0x14002be33  mov     [rbp+50h+var_C4], 0
0x14002be37  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002be3e  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x14002be43  call    _CxxThrowException_0
0x14002be49  mov     rbx, [r14+110h]
0x14002be50  mov     rcx, r15
0x14002be53  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002be58  mov     [rsp+150h+hTransaction], rbx; void *
0x14002be5d  mov     r9, rax; HKEY *
0x14002be60  mov     edi, 20019h
0x14002be65  mov     r8d, edi; unsigned int
0x14002be68  mov     rdx, [rbp+50h+var_78]; wchar_t *
0x14002be6c  mov     rcx, [rbp+50h+arg_20]; HKEY
0x14002be73  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14002be78  lea     rcx, [rbp+50h+lpSubKey]
0x14002be7c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002be81  nop
0x14002be82  mov     rcx, [rsi]
0x14002be85  or      r12, 0FFFFFFFFFFFFFFFFh
0x14002be89  mov     rax, r12
0x14002be8c  xor     esi, esi
0x14002be8e  inc     rax
0x14002be91  cmp     [rcx+rax*2], si
0x14002be95  jnz     short loc_14002BE8E
0x14002be97  mov     [rbp+50h+var_C0], rcx
0x14002be9b  mov     [rbp+50h+var_C0+8], rax
0x14002be9f  lea     r9, [rbp+50h+lpSubKey]
0x14002bea3  lea     r8, [rbp+50h+arg_20]
0x14002beaa  lea     rdx, [rbp+50h+var_C0]
0x14002beae  call    ?GetLegacyChannelRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetLegacyChannelRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002beb3  mov     ebx, eax
0x14002beb5  test    eax, eax
0x14002beb7  jz      short loc_14002BF2E
0x14002beb9  lea     rdi, WPP_GLOBAL_Control
0x14002bec0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bec7  cmp     rcx, rdi
0x14002beca  jz      short loc_14002BEF0
0x14002becc  test    byte ptr [rcx+1Ch], 4
0x14002bed0  jz      short loc_14002BEF0
0x14002bed2  cmp     byte ptr [rcx+19h], 2
0x14002bed6  jb      short loc_14002BEF0
0x14002bed8  mov     edx, 0Bh
0x14002bedd  mov     r9d, eax
0x14002bee0  lea     r8, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids
0x14002bee7  mov     rcx, [rcx+10h]
0x14002beeb  call    WPP_SF_d
0x14002bef0  lea     rax, word_14003838A
0x14002bef7  mov     [rsp+150h+pExceptionObject], rax
0x14002befc  mov     [rsp+150h+var_E0], rsi
0x14002bf01  mov     [rsp+150h+var_D8], 0
0x14002bf0a  mov     [rbp+50h+var_D0], ebx
0x14002bf0d  mov     [rbp+50h+var_CC], 0FFFFFFFFh
0x14002bf14  mov     [rbp+50h+var_C8], r12d
0x14002bf18  mov     [rbp+50h+var_C4], sil
0x14002bf1c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002bf23  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x14002bf28  call    _CxxThrowException_0
0x14002bf2e  mov     r15b, sil
0x14002bf31  mov     [rbp+50h+hKey], rsi
0x14002bf35  mov     rbx, [r14+110h]
0x14002bf3c  lea     rcx, [rbp+50h+hKey]
0x14002bf40  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002bf45  mov     [rsp+150h+hTransaction], rbx; void *
0x14002bf4a  mov     r9, rax; HKEY *
0x14002bf4d  mov     r8d, edi; unsigned int
0x14002bf50  mov     rdx, [rbp+50h+lpSubKey]; wchar_t *
0x14002bf54  mov     rbx, [rbp+50h+arg_20]
0x14002bf5b  mov     rcx, rbx; HKEY
0x14002bf5e  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14002bf63  test    eax, eax
0x14002bf65  jnz     short loc_14002BF7F
0x14002bf67  mov     byte ptr [r14+160h], 1
0x14002bf6f  lea     eax, [r13-2]
0x14002bf73  cmp     eax, 1
0x14002bf76  jbe     loc_14002C07E
0x14002bf7c  mov     r15b, 1
0x14002bf7f  mov     rcx, [rbp+50h+hKey]; hKey
0x14002bf83  test    rcx, rcx
0x14002bf86  jz      short loc_14002BF8E
0x14002bf88  call    cs:__imp_RegCloseKey
0x14002bf8e  lea     rdi, WPP_GLOBAL_Control
0x14002bf95  lea     rsi, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids
0x14002bf9c  xor     ecx, ecx
0x14002bf9e  test    r15b, r15b
0x14002bfa1  jz      short loc_14002BFDF
0x14002bfa3  cmp     [r14+161h], cl
0x14002bfaa  jz      loc_14002C1F5
0x14002bfb0  lea     rdx, [r14+118h]
0x14002bfb7  mov     rcx, [rdx]
0x14002bfba  mov     [rbp+50h+var_C0], rcx
0x14002bfbe  mov     rax, [rdx+8]
0x14002bfc2  sub     rax, rcx
0x14002bfc5  sar     rax, 1
0x14002bfc8  mov     [rbp+50h+var_C0+8], rax
0x14002bfcc  lea     rcx, [rbp+50h+var_C0]
0x14002bfd0  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002bfd5  xor     ecx, ecx
0x14002bfd7  test    al, al
0x14002bfd9  jnz     loc_14002C1F5
0x14002bfdf  lea     rcx, [rbp+50h+var_C0]
0x14002bfe3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002bfe8  nop
0x14002bfe9  lea     rcx, [rsp+150h+pExceptionObject]
0x14002bfee  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002bff3  nop
0x14002bff4  lea     r9, [rsp+150h+pExceptionObject]
0x14002bff9  lea     r8, [rbp+50h+var_C0]
0x14002bffd  lea     rdx, [rbp+50h+arg_20]
0x14002c004  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002c009  mov     ebx, eax
0x14002c00b  test    eax, eax
0x14002c00d  jz      loc_14002C0DC
0x14002c013  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c01a  cmp     rcx, rdi
0x14002c01d  jz      short loc_14002C03F
0x14002c01f  test    byte ptr [rcx+1Ch], 4
0x14002c023  jz      short loc_14002C03F
0x14002c025  cmp     byte ptr [rcx+19h], 2
0x14002c029  jb      short loc_14002C03F
0x14002c02b  mov     edx, 0Dh
0x14002c030  mov     r9d, eax
0x14002c033  mov     r8, rsi
0x14002c036  mov     rcx, [rcx+10h]
0x14002c03a  call    WPP_SF_d
0x14002c03f  lea     rax, word_14003838A
0x14002c046  mov     [rsp+150h+var_110], rax
0x14002c04b  xor     eax, eax
0x14002c04d  mov     [rsp+150h+var_108], rax
0x14002c052  mov     [rsp+150h+var_100], rax
0x14002c057  mov     [rsp+150h+var_F8], ebx
0x14002c05b  mov     [rsp+150h+var_F4], 0FFFFFFFFh
0x14002c063  mov     [rsp+150h+var_F0], r12d
0x14002c068  mov     [rsp+150h+var_EC], al
0x14002c06c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002c073  lea     rcx, [rsp+150h+var_110]; pExceptionObject
0x14002c078  call    _CxxThrowException_0
0x14002c07e  lea     rdi, WPP_GLOBAL_Control
0x14002c085  mov     ebx, 57h ; 'W'
0x14002c08a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c091  cmp     rcx, rdi
0x14002c094  jz      short loc_14002C0B8
0x14002c096  test    byte ptr [rcx+1Ch], 4
0x14002c09a  jz      short loc_14002C0B8
0x14002c09c  cmp     byte ptr [rcx+19h], 2
0x14002c0a0  jb      short loc_14002C0B8
0x14002c0a2  lea     edx, [rbx-4Bh]
0x14002c0a5  mov     r9d, ebx
0x14002c0a8  lea     r8, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids
0x14002c0af  mov     rcx, [rcx+10h]
0x14002c0b3  call    WPP_SF_d
0x14002c0b8  mov     r9d, 3Dh ; '='; int
0x14002c0be  mov     edx, ebx; unsigned int
0x14002c0c0  lea     rcx, [rsp+150h+var_110]; this
0x14002c0c5  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002c0ca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002c0d1  lea     rcx, [rsp+150h+var_110]; pExceptionObject
0x14002c0d6  call    _CxxThrowException_0
0x14002c0dc  mov     r8d, 0Ah
0x14002c0e2  lea     rdx, aChannels_1; "\\Channels\\"
0x14002c0e9  lea     rcx, [rbp+50h+var_C0]
0x14002c0ed  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002c0f2  xor     ebx, ebx
0x14002c0f4  test    al, al
0x14002c0f6  jz      loc_14002C55A
0x14002c0fc  lea     rax, [r14+118h]
0x14002c103  mov     r8, [rax+8]
0x14002c107  sub     r8, [rax]
0x14002c10a  sar     r8, 1
0x14002c10d  mov     rdx, [rax]
0x14002c110  lea     rcx, [rbp+50h+var_C0]
0x14002c114  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002c119  test    al, al
0x14002c11b  jz      loc_14002C55A
0x14002c121  mov     [rbp+50h+hKey], rbx
0x14002c125  mov     rbx, [r14+110h]
0x14002c12c  lea     rcx, [rbp+50h+hKey]
0x14002c130  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002c135  mov     [rsp+150h+hTransaction], rbx; void *
0x14002c13a  mov     r9, rax; HKEY *
0x14002c13d  mov     r8d, 20019h; unsigned int
0x14002c143  mov     rdx, [rbp+50h+var_C0]; wchar_t *
0x14002c147  mov     rbx, [rbp+50h+arg_20]
0x14002c14e  mov     rcx, rbx; HKEY
0x14002c151  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14002c156  test    eax, eax
0x14002c158  jnz     loc_14002C26F
0x14002c15e  test    r15b, r15b
0x14002c161  jz      short loc_14002C1B6
0x14002c163  mov     rdx, [r14+118h]; unsigned int
0x14002c16a  lea     ecx, [rax+5Ch]; this
0x14002c16d  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14002c172  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c179  cmp     rcx, rdi
0x14002c17c  jz      short loc_14002C19F
0x14002c17e  test    byte ptr [rcx+1Ch], 8
0x14002c182  jz      short loc_14002C19F
0x14002c184  cmp     byte ptr [rcx+19h], 3
0x14002c188  jb      short loc_14002C19F
0x14002c18a  mov     edx, 0Fh
0x14002c18f  mov     r9, [rbp+50h+lpSubKey]
0x14002c193  mov     r8, rsi
0x14002c196  mov     rcx, [rcx+10h]
0x14002c19a  call    WPP_SF_S
0x14002c19f  lea     rdx, [rbp+50h+lpSubKey]
0x14002c1a3  lea     rcx, [r14+140h]
0x14002c1aa  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14002c1af  mov     [r14+138h], rbx
0x14002c1b6  mov     r15b, 1
0x14002c1b9  mov     byte ptr [r14+160h], 2
0x14002c1c1  lea     rdx, [rbp+50h+var_C0]
0x14002c1c5  lea     rcx, [rbp+50h+lpSubKey]
0x14002c1c9  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14002c1ce  nop
0x14002c1cf  mov     rcx, [rbp+50h+hKey]; hKey
0x14002c1d3  test    rcx, rcx
0x14002c1d6  jz      short loc_14002C1DF
0x14002c1d8  call    cs:__imp_RegCloseKey
0x14002c1de  nop
0x14002c1df  lea     rcx, [rsp+150h+pExceptionObject]
0x14002c1e4  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002c1e9  nop
0x14002c1ea  lea     rcx, [rbp+50h+var_C0]
0x14002c1ee  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002c1f3  xor     ecx, ecx
0x14002c1f5  test    r13d, r13d
0x14002c1f8  jz      loc_14002C46A
0x14002c1fe  sub     r13d, 1
0x14002c202  jz      loc_14002C411
  ... truncated ...
```
