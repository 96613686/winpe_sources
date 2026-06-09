# ChannelConfigWriter::ChannelConfigWriter(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,ulong,bool,void *)

- ea: `0x18005b6a0`
- end: `0x18005c03a`
- name: `??0ChannelConfigWriter@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_NPEAX@Z`
- size: `2458`
- prototype: `__int64 __fastcall(int, int, int, int, HKEY hKey)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18005afd8`
- `0x1800840c8`

## callees

- `0x180006600`
- `0x180006770`
- `0x180009260`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x18002afa8`
- `0x18002d6dc`
- `0x18002dcc0`
- `0x18003d2f8`
- `0x18005b5f4`
- `0x18005b6a0`
- `0x18005c2d4`
- `0x180077ad0`
- `0x180083b84`
- `0x180083f2c`
- `0x180092008`
- `0x180098c50`
- `0x1800b5d84`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b8e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b8e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005bd4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005bd4a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005bd42`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005bd42`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ChannelConfigWriter::ChannelConfigWriter(__int64 a1, _OWORD *a2, int a3, char a4, HKEY hKey)
{
  __int64 v8; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v10; // ebx
  void *v11; // rbx
  HKEY *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  unsigned int EventlogServiceRegPath; // eax
  unsigned int v16; // ebx
  PVOID *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  char v20; // r15
  HKEY v21; // r12
  __int64 v22; // rcx
  unsigned int v23; // eax
  int v24; // ebx
  void *v25; // rbx
  HKEY *v26; // rax
  int v27; // eax
  int v28; // r13d
  int v29; // r13d
  int v30; // ecx
  unsigned int v31; // ebx
  PVOID *v32; // rcx
  void *hTransaction; // rax
  unsigned int v34; // eax
  unsigned int v35; // ebx
  void *v36; // rbx
  HKEY *v37; // rax
  struct _SECURITY_ATTRIBUTES *const v38; // r9
  unsigned int v39; // eax
  unsigned int v40; // ebx
  __int128 v42; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-B0h]
  int v44; // [rsp+60h] [rbp-A8h]
  __int64 v45; // [rsp+64h] [rbp-A4h]
  char v46; // [rsp+6Ch] [rbp-9Ch]
  wchar_t *v47; // [rsp+70h] [rbp-98h] BYREF
  __int64 v48; // [rsp+80h] [rbp-88h] BYREF
  wchar_t *v49[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v51; // [rsp+D0h] [rbp-38h]
  int v52; // [rsp+D4h] [rbp-34h]
  int v53; // [rsp+D8h] [rbp-30h]
  char v54; // [rsp+DCh] [rbp-2Ch]
  _QWORD *v55; // [rsp+E0h] [rbp-28h]
  wchar_t *v56[2]; // [rsp+E8h] [rbp-20h] BYREF
  char v57; // [rsp+F8h] [rbp-10h] BYREF
  void *v58[2]; // [rsp+108h] [rbp+0h] BYREF
  char v59; // [rsp+118h] [rbp+10h] BYREF
  HKEY v60; // [rsp+170h] [rbp+68h] BYREF
  unsigned int v61; // [rsp+180h] [rbp+78h] BYREF

  LOBYTE(v61) = a4;
  ChannelConfigWriteData::ChannelConfigWriteData((ChannelConfigWriteData *)a1);
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = -1;
  *(_OWORD *)v49 = *a2;
  v55 = (_QWORD *)(a1 + 280);
  MakeOrThrowOOM((void *)(a1 + 280));
  *(_QWORD *)(a1 + 312) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((void *)(a1 + 320));
  *(_WORD *)(a1 + 352) = 0;
  v60 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v56);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v58);
  WinevtRegPath = RegistryPaths::GetWinevtRegPath(v8, &v60, v56, v58);
  v10 = WinevtRegPath;
  if ( WinevtRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, WinevtRegPath);
    }
    pExceptionObject[0] = &byte_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v51 = v10;
    v52 = -1;
    v53 = -1;
    v54 = 0;
    throw (EvtException *)pExceptionObject;
  }
  v11 = *(void **)(a1 + 272);
  v12 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1 + 264);
  OpenRegKey(v60, v56[0], 0x20019u, v12, v11);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v47);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 280) + 2 * v14) );
  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v13, &v60, &v47);
  v16 = EventlogServiceRegPath;
  if ( EventlogServiceRegPath )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_114;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_110;
    v18 = 13;
    v19 = EventlogServiceRegPath;
    goto LABEL_109;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           &v47,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&v47) )
  {
    v16 = 14;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_114;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_110:
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 && *((_BYTE *)v17 + 25) >= 2u )
        WPP_SF_d(v17[2], 11, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, v16);
LABEL_114:
      *(_QWORD *)&v42 = &byte_1800EC961;
      *((_QWORD *)&v42 + 1) = 0;
      v43 = 0;
      v44 = v16;
      v45 = -1;
      v46 = 0;
      throw (EvtException *)&v42;
    }
    v18 = 14;
    v19 = 14;
LABEL_109:
    WPP_SF_d(v17[2], v18, WPP_c10225a1bfc8322526427285fd9158a0_Traceguids, v19);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_110;
  }
  v20 = 0;
  hKey = 0;
  v21 = v60;
  if ( !OpenRegKey(v60, v47, 0x20019u, &hKey, *(void **)(a1 + 272)) )
  {
    *(_BYTE *)(a1 + 352) = 1;
    if ( (unsigned int)(a3 - 2) <= 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 87);
      }
      v42 = 0;
      v43 = 0;
      v44 = 87;
      v45 = 0x3DFFFFFFFFLL;
      throw (EvtException *)&v42;
    }
    v20 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v20
    || *(_BYTE *)(a1 + 353)
    && (v49[0] = *(wchar_t **)(a1 + 280),
        v49[1] = (wchar_t *)((__int64)(*(_QWORD *)(a1 + 288) - (unsigned __int64)v49[0]) >> 1),
        !(unsigned __int8)IsCoreChannel(v49)) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v49);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject);
    v23 = RegistryPaths::GetWinevtRegPath(v22, &v60, v49, pExceptionObject);
    v24 = v23;
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, v23);
      }
      *(_QWORD *)&v42 = &byte_1800EC961;
      *((_QWORD *)&v42 + 1) = 0;
      v43 = 0;
      v44 = v24;
      v45 = -1;
      v46 = 0;
      throw (EvtException *)&v42;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v49)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v49) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 14);
      }
      v42 = 0;
      v43 = 0;
      v44 = 14;
      v45 = 0x55FFFFFFFFLL;
      throw (EvtException *)&v42;
    }
    hKey = 0;
    v25 = *(void **)(a1 + 272);
    v26 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v21 = v60;
    if ( OpenRegKey(v60, v49[0], 0x20019u, v26, v25) )
    {
      if ( v20 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x5B, *v55);
        v31 = v30 + 92;
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
              v31,
              (__int64)v47);
            v32 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 && *((_BYTE *)v32 + 25) >= 2u )
            WPP_SF_d(v32[2], 17, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, v31);
        }
        v42 = 0;
        v43 = 0;
        v44 = v31;
        v45 = 0x74FFFFFFFFLL;
        throw (EvtException *)&v42;
      }
    }
    else
    {
      if ( v20 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x5C, *(_QWORD *)(a1 + 280));
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)(v27 + 15),
            WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids,
            v47);
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a1 + 320, &v47);
        *(_QWORD *)(a1 + 312) = v21;
      }
      v20 = 1;
    }
    *(_BYTE *)(a1 + 352) = 2;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(&v47, v49);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pExceptionObject);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v49);
  }
  if ( a3 )
  {
    v28 = a3 - 1;
    if ( v28 )
    {
      v29 = v28 - 1;
      if ( v29 )
      {
        if ( v29 != 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 87);
          }
          v42 = 0;
          v43 = 0;
          v44 = 87;
          v45 = 0xA1FFFFFFFFLL;
          throw (EvtException *)&v42;
        }
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 183);
          }
          v42 = 0;
          v43 = 0;
          v44 = 183;
          v45 = 0x83FFFFFFFFLL;
          throw (EvtException *)&v42;
        }
      }
      else if ( v20 )
      {
        hTransaction = *(void **)(a1 + 272);
        v34 = hTransaction == (void *)-1LL
            ? RegDeleteKeyExW(v21, v47, 0, 0)
            : RegDeleteKeyTransactedW(v21, v47, 0, 0, hTransaction, 0);
        v35 = v34;
        if ( v34 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, v34);
          }
          v42 = 0;
          v43 = 0;
          v44 = v35;
          v45 = 0x94FFFFFFFFLL;
          throw (EvtException *)&v42;
        }
      }
    }
    else if ( !v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, 2);
      }
      v42 = 0;
      v43 = 0;
      v44 = 2;
      v45 = 0x9DFFFFFFFFLL;
      throw (EvtException *)&v42;
    }
  }
  v61 = 0;
  v36 = *(void **)(a1 + 272);
  v37 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(a1 + 256);
  v39 = CreateRegKey(v21, v47, 0x2001Fu, v38, v37, &v61, v36);
  v40 = v39;
  if ( v39 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids, v39);
    }
    *(_QWORD *)&v42 = &byte_1800EC961;
    *((_QWORD *)&v42 + 1) = 0;
    v43 = 0;
    v44 = v40;
    v45 = -1;
    v46 = 0;
    throw (EvtException *)&v42;
  }
  if ( v47 != (wchar_t *)&v48 )
    operator delete(v47);
  if ( v58[0] != &v59 )
    operator delete(v58[0]);
  if ( (char *)v56[0] != &v57 )
    operator delete(v56[0]);
  return a1;
}

```

## disassembly

```asm
0x18005b6a0  mov     rax, rsp
0x18005b6a3  mov     [rax+18h], rbx
0x18005b6a7  mov     [rax+20h], r9b
0x18005b6ab  mov     [rax+8], rcx
0x18005b6af  push    rbp
0x18005b6b0  push    rsi
0x18005b6b1  push    rdi
0x18005b6b2  push    r12
0x18005b6b4  push    r13
0x18005b6b6  push    r14
0x18005b6b8  push    r15
0x18005b6ba  lea     rbp, [rax-58h]
0x18005b6be  sub     rsp, 120h
0x18005b6c5  mov     r13d, r8d
0x18005b6c8  mov     rbx, rdx
0x18005b6cb  mov     r14, rcx
0x18005b6ce  call    ??0ChannelConfigWriteData@@AEAA@XZ; ChannelConfigWriteData::ChannelConfigWriteData(void)
0x18005b6d3  nop
0x18005b6d4  xor     r12d, r12d
0x18005b6d7  mov     [r14+100h], r12
0x18005b6de  lea     rsi, [r14+108h]
0x18005b6e5  mov     [rsi], r12
0x18005b6e8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005b6ec  mov     [r14+110h], r15
0x18005b6f3  movaps  xmm0, xmmword ptr [rbx]
0x18005b6f6  movdqa  xmmword ptr [rbp+50h+var_C0], xmm0
0x18005b6fb  lea     rdi, [r14+118h]
0x18005b702  mov     [rbp+50h+var_78], rdi
0x18005b706  lea     rdx, [rbp+50h+var_C0]
0x18005b70a  mov     rcx, rdi
0x18005b70d  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005b712  nop
0x18005b713  mov     [r14+138h], r12
0x18005b71a  lea     rcx, [r14+140h]; void *
0x18005b721  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b726  nop
0x18005b727  mov     [r14+160h], r12w
0x18005b72f  mov     [rbp+50h+arg_8], r12
0x18005b733  lea     rcx, [rbp+50h+var_70]; void *
0x18005b737  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b73c  nop
0x18005b73d  lea     rcx, [rbp+50h+var_50]; void *
0x18005b741  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b746  nop
0x18005b747  lea     r9, [rbp+50h+var_50]
0x18005b74b  lea     r8, [rbp+50h+var_70]
0x18005b74f  lea     rdx, [rbp+50h+arg_8]
0x18005b753  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005b758  mov     ebx, eax
0x18005b75a  test    eax, eax
0x18005b75c  jz      short loc_18005B7CB
0x18005b75e  lea     rdi, WPP_GLOBAL_Control
0x18005b765  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b76c  cmp     rcx, rdi
0x18005b76f  jz      short loc_18005B795
0x18005b771  test    byte ptr [rcx+1Ch], 4
0x18005b775  jz      short loc_18005B795
0x18005b777  cmp     byte ptr [rcx+19h], 2
0x18005b77b  jb      short loc_18005B795
0x18005b77d  lea     edx, [r12+0Ah]
0x18005b782  mov     r9d, eax
0x18005b785  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x18005b78c  mov     rcx, [rcx+10h]
0x18005b790  call    WPP_SF_d
0x18005b795  lea     rax, byte_1800EC961
0x18005b79c  mov     [rbp+50h+pExceptionObject], rax
0x18005b7a0  mov     [rbp+50h+var_98], r12
0x18005b7a4  mov     [rbp+50h+var_90], r12
0x18005b7a8  mov     [rbp+50h+var_88], ebx
0x18005b7ab  mov     [rbp+50h+var_84], 0FFFFFFFFh
0x18005b7b2  mov     [rbp+50h+var_80], r15d
0x18005b7b6  mov     [rbp+50h+var_7C], r12b
0x18005b7ba  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b7c1  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18005b7c5  call    _CxxThrowException_0
0x18005b7cb  mov     rbx, [r14+110h]
0x18005b7d2  mov     rcx, rsi
0x18005b7d5  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005b7da  mov     [rsp+150h+hTransaction], rbx; void *
0x18005b7df  mov     r9, rax; HKEY *
0x18005b7e2  mov     r8d, 20019h; unsigned int
0x18005b7e8  mov     rdx, [rbp+50h+var_70]; wchar_t *
0x18005b7ec  mov     rcx, [rbp+50h+arg_8]; HKEY
0x18005b7f0  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18005b7f5  lea     rcx, [rsp+150h+var_E8]; void *
0x18005b7fa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b7ff  nop
0x18005b800  mov     rsi, [rdi]
0x18005b803  mov     rdi, r15
0x18005b806  inc     rdi
0x18005b809  cmp     [rsi+rdi*2], r12w
0x18005b80e  jnz     short loc_18005B806
0x18005b810  lea     r8, [rsp+150h+var_E8]
0x18005b815  lea     rdx, [rbp+50h+arg_8]
0x18005b819  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005b81e  mov     ebx, eax
0x18005b820  test    eax, eax
0x18005b822  jz      short loc_18005B85C
0x18005b824  lea     rdi, WPP_GLOBAL_Control
0x18005b82b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b832  cmp     rcx, rdi
0x18005b835  jz      loc_18005BFFC
0x18005b83b  test    byte ptr [rcx+1Ch], 4
0x18005b83f  jz      loc_18005BFD3
0x18005b845  cmp     byte ptr [rcx+19h], 2
0x18005b849  jb      loc_18005BFD3
0x18005b84f  mov     edx, 0Dh
0x18005b854  mov     r9d, eax
0x18005b857  jmp     loc_18005BFBC
0x18005b85c  mov     edx, 5Ch ; '\'
0x18005b861  lea     rcx, [rsp+150h+var_E8]
0x18005b866  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18005b86b  test    al, al
0x18005b86d  jz      loc_18005BF93
0x18005b873  mov     r8, rdi
0x18005b876  mov     rdx, rsi
0x18005b879  lea     rcx, [rsp+150h+var_E8]
0x18005b87e  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18005b883  test    al, al
0x18005b885  jz      loc_18005BF93
0x18005b88b  mov     r15b, r12b
0x18005b88e  mov     [rbp+50h+hKey], r12
0x18005b895  mov     rax, [r14+110h]
0x18005b89c  mov     [rsp+150h+hTransaction], rax; void *
0x18005b8a1  lea     r9, [rbp+50h+hKey]; HKEY *
0x18005b8a8  mov     r8d, 20019h; unsigned int
0x18005b8ae  mov     rdx, [rsp+150h+var_E8]; wchar_t *
0x18005b8b3  mov     r12, [rbp+50h+arg_8]
0x18005b8b7  mov     rcx, r12; HKEY
0x18005b8ba  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18005b8bf  test    eax, eax
0x18005b8c1  jnz     short loc_18005B8DB
0x18005b8c3  mov     byte ptr [r14+160h], 1
0x18005b8cb  lea     eax, [r13-2]
0x18005b8cf  cmp     eax, 1
0x18005b8d2  jbe     loc_18005B9D3
0x18005b8d8  mov     r15b, 1
0x18005b8db  mov     rcx, [rbp+50h+hKey]; hKey
0x18005b8e2  test    rcx, rcx
0x18005b8e5  jz      short loc_18005B8ED
0x18005b8e7  call    cs:__imp_RegCloseKey
0x18005b8ed  lea     rdi, WPP_GLOBAL_Control
0x18005b8f4  lea     rsi, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x18005b8fb  test    r15b, r15b
0x18005b8fe  jz      short loc_18005B93B
0x18005b900  cmp     byte ptr [r14+161h], 0
0x18005b908  jz      loc_18005BB59
0x18005b90e  lea     rdx, [r14+118h]
0x18005b915  mov     rcx, [rdx]
0x18005b918  mov     [rbp+50h+var_C0], rcx
0x18005b91c  mov     rax, [rdx+8]
0x18005b920  sub     rax, rcx
0x18005b923  sar     rax, 1
0x18005b926  mov     [rbp+50h+var_C0+8], rax
0x18005b92a  lea     rcx, [rbp+50h+var_C0]
0x18005b92e  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005b933  test    al, al
0x18005b935  jnz     loc_18005BB59
0x18005b93b  lea     rcx, [rbp+50h+var_C0]; void *
0x18005b93f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b944  nop
0x18005b945  lea     rcx, [rbp+50h+pExceptionObject]; void *
0x18005b949  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005b94e  nop
0x18005b94f  lea     r9, [rbp+50h+pExceptionObject]
0x18005b953  lea     r8, [rbp+50h+var_C0]
0x18005b957  lea     rdx, [rbp+50h+arg_8]
0x18005b95b  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005b960  mov     ebx, eax
0x18005b962  xor     r12d, r12d
0x18005b965  test    eax, eax
0x18005b967  jz      loc_18005BA44
0x18005b96d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b974  cmp     rcx, rdi
0x18005b977  jz      short loc_18005B999
0x18005b979  test    byte ptr [rcx+1Ch], 4
0x18005b97d  jz      short loc_18005B999
0x18005b97f  cmp     byte ptr [rcx+19h], 2
0x18005b983  jb      short loc_18005B999
0x18005b985  lea     edx, [r12+0Dh]
0x18005b98a  mov     r9d, eax
0x18005b98d  mov     r8, rsi
0x18005b990  mov     rcx, [rcx+10h]
0x18005b994  call    WPP_SF_d
0x18005b999  lea     rax, byte_1800EC961
0x18005b9a0  mov     qword ptr [rsp+150h+var_118+8], rax
0x18005b9a5  mov     [rsp+150h+var_108], r12
0x18005b9aa  mov     qword ptr [rsp+150h+var_100], r12
0x18005b9af  mov     dword ptr [rsp+150h+var_FC+4], ebx
0x18005b9b3  mov     qword ptr [rsp+150h+var_F4], 0FFFFFFFFFFFFFFFFh
0x18005b9bc  mov     byte ptr [rsp+150h+var_F0+4], r12b
0x18005b9c1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005b9c8  lea     rcx, [rsp+150h+var_118+8]; pExceptionObject
0x18005b9cd  call    _CxxThrowException_0
0x18005b9d3  lea     rdi, WPP_GLOBAL_Control
0x18005b9da  mov     ebx, 57h ; 'W'
0x18005b9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9e6  cmp     rcx, rdi
0x18005b9e9  jz      short loc_18005BA0D
0x18005b9eb  test    byte ptr [rcx+1Ch], 4
0x18005b9ef  jz      short loc_18005BA0D
0x18005b9f1  cmp     byte ptr [rcx+19h], 2
0x18005b9f5  jb      short loc_18005BA0D
0x18005b9f7  lea     edx, [rbx-4Bh]
0x18005b9fa  mov     r9d, ebx
0x18005b9fd  lea     r8, WPP_a9e82e42b12a3cc1f70c27fa399b6680_Traceguids
0x18005ba04  mov     rcx, [rcx+10h]
0x18005ba08  call    WPP_SF_d
0x18005ba0d  xorps   xmm0, xmm0
0x18005ba10  movdqu  [rsp+150h+var_118+8], xmm0
0x18005ba16  xor     r15d, r15d
0x18005ba19  mov     qword ptr [rsp+150h+var_100], r15
0x18005ba1e  mov     dword ptr [rsp+150h+var_FC+4], ebx
0x18005ba22  mov     dword ptr [rsp+150h+var_F4], 0FFFFFFFFh
0x18005ba2a  mov     dword ptr [rsp+150h+var_F0], 3Dh ; '='
0x18005ba32  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005ba39  lea     rcx, [rsp+150h+var_118+8]; pExceptionObject
0x18005ba3e  call    _CxxThrowException_0
0x18005ba44  mov     r8d, 0Ah
0x18005ba4a  lea     rdx, aChannels_1; "\\Channels\\"
0x18005ba51  lea     rcx, [rbp+50h+var_C0]
0x18005ba55  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18005ba5a  test    al, al
0x18005ba5c  jz      loc_18005BF31
0x18005ba62  lea     rax, [r14+118h]
0x18005ba69  mov     r8, [rax+8]
0x18005ba6d  sub     r8, [rax]
0x18005ba70  sar     r8, 1
0x18005ba73  mov     rdx, [rax]
0x18005ba76  lea     rcx, [rbp+50h+var_C0]
0x18005ba7a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18005ba7f  test    al, al
0x18005ba81  jz      loc_18005BF31
0x18005ba87  mov     [rbp+50h+hKey], r12
0x18005ba8e  mov     rbx, [r14+110h]
0x18005ba95  lea     rcx, [rbp+50h+hKey]
0x18005ba9c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005baa1  mov     [rsp+150h+hTransaction], rbx; void *
0x18005baa6  mov     r9, rax; HKEY *
0x18005baa9  mov     r8d, 20019h; unsigned int
0x18005baaf  mov     rdx, [rbp+50h+var_C0]; wchar_t *
0x18005bab3  mov     r12, [rbp+50h+arg_8]
0x18005bab7  mov     rcx, r12; HKEY
0x18005baba  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18005babf  test    eax, eax
0x18005bac1  jnz     loc_18005BBE6
0x18005bac7  test    r15b, r15b
0x18005baca  jz      short loc_18005BB1F
0x18005bacc  mov     rdx, [r14+118h]; unsigned int
0x18005bad3  lea     ecx, [rax+5Ch]; this
0x18005bad6  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x18005badb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bae2  cmp     rcx, rdi
0x18005bae5  jz      short loc_18005BB07
0x18005bae7  test    byte ptr [rcx+1Ch], 8
0x18005baeb  jz      short loc_18005BB07
0x18005baed  cmp     byte ptr [rcx+19h], 3
0x18005baf1  jb      short loc_18005BB07
0x18005baf3  lea     edx, [rax+0Fh]
0x18005baf6  mov     r9, [rsp+150h+var_E8]
0x18005bafb  mov     r8, rsi
0x18005bafe  mov     rcx, [rcx+10h]
0x18005bb02  call    WPP_SF_S
0x18005bb07  lea     rdx, [rsp+150h+var_E8]
0x18005bb0c  lea     rcx, [r14+140h]
0x18005bb13  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18005bb18  mov     [r14+138h], r12
0x18005bb1f  mov     r15b, 1
0x18005bb22  mov     byte ptr [r14+160h], 2
0x18005bb2a  lea     rdx, [rbp+50h+var_C0]
0x18005bb2e  lea     rcx, [rsp+150h+var_E8]
0x18005bb33  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18005bb38  nop
0x18005bb39  lea     rcx, [rbp+50h+hKey]
0x18005bb40  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005bb45  nop
0x18005bb46  lea     rcx, [rbp+50h+pExceptionObject]; void *
0x18005bb4a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005bb4f  nop
0x18005bb50  lea     rcx, [rbp+50h+var_C0]; void *
0x18005bb54  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005bb59  test    r13d, r13d
0x18005bb5c  jz      loc_18005BE2A
0x18005bb62  sub     r13d, 1
0x18005bb66  jz      loc_18005BDBC
0x18005bb6c  sub     r13d, 1
0x18005bb70  jz      loc_18005BD14
0x18005bb76  cmp     r13d, 1
0x18005bb7a  jz      loc_18005BCA3
0x18005bb80  mov     ebx, 57h ; 'W'
0x18005bb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb8c  cmp     rcx, rdi
0x18005bb8f  jz      short loc_18005BBAF
0x18005bb91  test    byte ptr [rcx+1Ch], 4
0x18005bb95  jz      short loc_18005BBAF
0x18005bb97  cmp     byte ptr [rcx+19h], 2
0x18005bb9b  jb      short loc_18005BBAF
0x18005bb9d  lea     edx, [rbx-42h]
0x18005bba0  mov     r9d, ebx
0x18005bba3  mov     r8, rsi
  ... truncated ...
```
