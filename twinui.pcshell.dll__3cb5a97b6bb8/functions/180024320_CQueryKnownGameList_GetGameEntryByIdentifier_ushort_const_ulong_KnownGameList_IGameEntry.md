# CQueryKnownGameList::GetGameEntryByIdentifier(ushort const *,ulong,KnownGameList::IGameEntry * *)

- ea: `0x180024320`
- end: `0x180024b74`
- name: `?GetGameEntryByIdentifier@CQueryKnownGameList@@AEAAJPEBGKPEAPEAUIGameEntry@KnownGameList@@@Z`
- size: `2132`
- prototype: `__int64 __fastcall(CQueryKnownGameList *__hidden this, const unsigned __int16 *, unsigned int, struct KnownGameList::IGameEntry **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cab80`
- `0x1801d76c0`

## callees

- `0x1800134f8`
- `0x180018cc8`
- `0x1800237c8`
- `0x180024320`
- `0x1801b0408`
- `0x1801efb04`
- `0x1802d7718`
- `0x1802d7a10`
- `0x1802d7cf4`
- `0x180356360`
- `0x180356760`
- `0x18035b6a0`
- `0x1806ad100`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x18002464f`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180024666`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x18002464f`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180024666`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800243d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800243d4`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180024683`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x18002488e`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x1806ecdd7`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180024683`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x18002488e`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x1806ecdd7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18002461a`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18002461a`

## string_xrefs

- `0x180024443`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024464`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002447f`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024512`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024771`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024797`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024838`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800249a1`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024a7e`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024abb`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024aef`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180024b4a`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1806ecd98`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1806ecdbe`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CQueryKnownGameList::GetGameEntryByIdentifier(
        CQueryKnownGameList *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct KnownGameList::IGameEntry **a4)
{
  _locale_t v6; // r15
  __int64 v7; // rax
  _locale_t *v8; // rsi
  unsigned int i; // ebx
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // esi
  void *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  void *v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // r9d
  int EnumerateEntriesInstance; // eax
  int v23; // ebx
  _locale_t v24; // rsi
  _locale_t v25; // r14
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, KnownGameList **); // r12
  KnownGameList *v28; // rcx
  int v29; // eax
  int v30; // r12d
  int v31; // eax
  __int64 v32; // rbx
  struct localeinfo_struct *v33; // rcx
  bool v34; // zf
  __int64 v35; // rbx
  int v36; // r12d
  wint_t v37; // ax
  unsigned __int16 v38; // cx
  KnownGameList *v39; // r12
  KnownGameList *v40; // rcx
  __int64 v41; // rcx
  KnownGameList *v42; // rcx
  __int64 v43; // rcx
  bool v44; // zf
  __int64 v45; // rcx
  KnownGameList *v46; // rcx
  __int64 v47; // rcx
  void *v48; // r14
  struct KnownGameList::IEnumerateEntries **v49; // rsi
  int v50; // eax
  struct KnownGameList::IGameEntry **v51; // rbx
  unsigned int j; // r12d
  const unsigned __int16 *v53; // r9
  int ProcessArgsByPID; // eax
  unsigned int v55; // r8d
  int ProcessWorkingDirectoryByPID; // eax
  int ProcessParentDirectoryByPID; // eax
  KnownGameList *v58; // rbx
  __int64 v59; // rdx
  _locale_t v60; // rax
  unsigned __int16 **v61; // [rsp+20h] [rbp-E0h]
  KnownGameList *v62; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v63; // [rsp+38h] [rbp-C8h] BYREF
  _locale_t Locale; // [rsp+40h] [rbp-C0h] BYREF
  int v65; // [rsp+48h] [rbp-B8h] BYREF
  KnownGameList *v66; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v67; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v68; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 *v69; // [rsp+60h] [rbp-A0h] BYREF
  KnownGameList *v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+74h] [rbp-8Ch] BYREF
  int v73; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v74; // [rsp+80h] [rbp-80h] BYREF
  KnownGameList *v75; // [rsp+88h] [rbp-78h] BYREF
  __int64 v76; // [rsp+90h] [rbp-70h]
  struct KnownGameList::IGameEntry **v77; // [rsp+98h] [rbp-68h]
  void *v78; // [rsp+A0h] [rbp-60h]
  _locale_t v79; // [rsp+A8h] [rbp-58h]
  __int128 v80; // [rsp+B0h] [rbp-50h] BYREF
  _locale_t v81; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v82[4096]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1128h] [rbp+1028h]

  v77 = a4;
  v68 = a3;
  v74 = a2;
  v6 = 0;
  *a4 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v76 = v7;
  v80 = 0;
  if ( !a2 )
  {
    v11 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80004003LL,
      (int)v61);
    goto LABEL_16;
  }
  v8 = 0;
  for ( i = 0; i < *((_DWORD *)this + 200); ++i )
  {
    v10 = (*(__int64 (__fastcall **)(CQueryKnownGameList *, _QWORD, __int128 *))(*(_QWORD *)this + 88LL))(this, i, &v80);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x433,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)(unsigned int)v10,
        (int)v61);
      goto LABEL_16;
    }
    if ( !(_WORD)v80 || (int)_o__wcsnicmp(&v80, a2, 4) > 0 )
      break;
    v8 = &v81;
  }
  if ( !v8 )
  {
    v11 = -2147024894;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)v11,
      (int)v61);
    return v11;
  }
  v12 = i - 1;
  v13 = 0;
  v78 = 0;
  v67 = 4096;
  v14 = (*(__int64 (__fastcall **)(CQueryKnownGameList *, _QWORD, _BYTE *, unsigned int *))(*(_QWORD *)this + 96LL))(
          this,
          i - 1,
          v82,
          &v67);
  v15 = v14;
  if ( v14 )
  {
    if ( v14 != -2147024774 )
    {
      if ( v14 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28E,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)(unsigned int)v14,
          (int)v61);
      return v15;
    }
    v17 = operator new[](v67, (const struct std::nothrow_t *)std::nothrow);
    v13 = v17;
    v78 = v17;
    if ( !v17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x293,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x8007000ELL,
        (int)v61);
      return 2147942414LL;
    }
    v18 = (*(__int64 (__fastcall **)(CQueryKnownGameList *, _QWORD, void *, unsigned int *))(*(_QWORD *)this + 96LL))(
            this,
            v12,
            v17,
            &v67);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)(unsigned int)v18,
        (int)v61);
      operator delete(v13);
      return v19;
    }
    v48 = v13;
    v49 = (struct KnownGameList::IEnumerateEntries **)v13;
  }
  else
  {
    v48 = 0;
    v49 = (struct KnownGameList::IEnumerateEntries **)v82;
  }
  v63 = 0;
  v20 = v67;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  EnumerateEntriesInstance = KnownGameList::CreateEnumerateEntriesInstance(
                               (KnownGameList *)&v63,
                               v49,
                               (unsigned __int8 *)v20,
                               v21);
  v23 = EnumerateEntriesInstance;
  if ( EnumerateEntriesInstance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)(unsigned int)EnumerateEntriesInstance,
      (int)v61);
    v45 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v44 = v48 == 0;
    goto LABEL_66;
  }
  v62 = 0;
  v66 = 0;
  v24 = 0;
  v79 = 0;
  v25 = 0;
  v81 = 0;
  *(_QWORD *)&v80 = 0;
LABEL_25:
  while ( 2 )
  {
    v26 = v63;
    v27 = *(__int64 (__fastcall **)(__int64, KnownGameList **))(*(_QWORD *)v63 + 24LL);
    v28 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v27(v26, &v62);
    v73 = v29;
    if ( !v29 )
    {
      v30 = 0;
      v75 = 0;
      v71 = 0;
      v31 = (*(__int64 (__fastcall **)(KnownGameList *, KnownGameList **, int *))(*(_QWORD *)v62 + 24LL))(
              v62,
              &v75,
              &v71);
      v23 = v31;
      if ( v31 >= 0 )
      {
        LODWORD(v69) = v71;
        v70 = v75;
        v32 = 0;
        v65 = 0;
        v33 = _create_locale(0, "C");
        Locale = v33;
        while ( 1 )
        {
          v34 = (_DWORD)v32 == (_DWORD)v69;
          if ( (unsigned int)v32 >= (unsigned int)v69 )
            break;
          if ( (unsigned int)v32 >= (unsigned int)v76 )
          {
            v34 = (_DWORD)v32 == (_DWORD)v69;
            break;
          }
          v35 = v32;
          v36 = _towlower_l(*(_WORD *)((char *)v70 + v35 * 2), v33);
          v37 = _towlower_l(v74[v35], Locale);
          v32 = (unsigned int)++v65;
          v30 = v36 - v37;
          v33 = Locale;
          if ( v30 )
            goto LABEL_33;
        }
        if ( !v34 )
        {
          _free_locale(v33);
          goto LABEL_39;
        }
        if ( (_DWORD)v32 != (_DWORD)v76 )
        {
          _free_locale(v33);
          continue;
        }
LABEL_33:
        _free_locale(v33);
        if ( v30 <= 0 )
        {
          if ( v30 )
            continue;
          LOWORD(v65) = 0;
          v23 = (*(__int64 (__fastcall **)(KnownGameList *, int *))(*(_QWORD *)v62 + 40LL))(v62, &v65);
          if ( v23 < 0 )
          {
            v59 = 703;
LABEL_160:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v59,
              (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
              (const char *)(unsigned int)v23,
              (int)v61);
            goto LABEL_92;
          }
          v38 = v65;
          if ( !(_WORD)v65 || v68 )
          {
            for ( j = 0; j < v38; ++j )
            {
              v72 = 0;
              v70 = 0;
              LODWORD(v69) = 0;
              Locale = 0;
              v61 = &v69;
              v23 = (*(__int64 (__fastcall **)(KnownGameList *, _QWORD, int *, KnownGameList **))(*(_QWORD *)v62 + 56LL))(
                      v62,
                      j,
                      &v72,
                      &v70);
              if ( v23 < 0 )
              {
                v59 = 724;
                goto LABEL_160;
              }
              if ( v72 )
              {
                if ( v72 == 1 )
                {
                  if ( !v25 )
                  {
                    ProcessWorkingDirectoryByPID = CQueryKnownGameList::GetProcessWorkingDirectoryByPID(
                                                     this,
                                                     v68,
                                                     (const unsigned __int16 **)&Locale);
                    v23 = ProcessWorkingDirectoryByPID;
                    if ( ProcessWorkingDirectoryByPID < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x2E3,
                        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                        (const char *)(unsigned int)ProcessWorkingDirectoryByPID,
                        (int)&v69);
                      if ( v6 )
                        operator delete(v6);
                      goto LABEL_96;
                    }
                    v25 = Locale;
                    v81 = Locale;
                  }
                  v55 = (unsigned int)v25;
                }
                else
                {
                  if ( v72 != 2 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2F3,
                      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                      (const char *)0x8000FFFFLL,
                      (int)&v69);
                    if ( v6 )
                      operator delete(v6);
                    if ( v25 )
                      operator delete(v25);
                    if ( v24 )
                      operator delete(v24);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
                    if ( v13 )
                      operator delete(v13);
                    return 2147549183LL;
                  }
                  if ( !v6 )
                  {
                    ProcessParentDirectoryByPID = CQueryKnownGameList::GetProcessParentDirectoryByPID(
                                                    this,
                                                    v68,
                                                    (const unsigned __int16 **)&Locale);
                    v23 = ProcessParentDirectoryByPID;
                    if ( ProcessParentDirectoryByPID < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x2EC,
                        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                        (const char *)(unsigned int)ProcessParentDirectoryByPID,
                        (int)&v69);
                      goto LABEL_94;
                    }
                    v6 = Locale;
                    *(_QWORD *)&v80 = Locale;
                  }
                  v55 = (unsigned int)v6;
                }
              }
              else
              {
                if ( !v24 )
                {
                  ProcessArgsByPID = CQueryKnownGameList::GetProcessArgsByPID(
                                       this,
                                       v68,
                                       (const unsigned __int16 **)&Locale);
                  v23 = ProcessArgsByPID;
                  if ( ProcessArgsByPID < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2DA,
                      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
                      (const char *)(unsigned int)ProcessArgsByPID,
                      (int)&v69);
                    if ( v6 )
                      operator delete(v6);
                    if ( v25 )
                      operator delete(v25);
                    goto LABEL_98;
                  }
                  v24 = Locale;
                  v79 = Locale;
                }
                v55 = (unsigned int)v24;
              }
              if ( !KnownGameList::StrStrInsensitive(v70, (const unsigned __int16 *)(unsigned int)v69, v55, v53) )
                goto LABEL_25;
              v38 = v65;
            }
            v58 = v62;
            v39 = v66;
            if ( v66 != v62 )
            {
              if ( v62 )
                (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v62 + 8LL))(v62);
              v70 = v39;
              v39 = v58;
              v66 = v58;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
              v38 = v65;
            }
            if ( v38 )
            {
              v29 = v73;
              goto LABEL_76;
            }
          }
          continue;
        }
LABEL_39:
        v39 = v66;
        if ( v66 )
          goto LABEL_127;
        if ( v6 )
          operator delete(v6);
        if ( v25 )
          operator delete(v25);
        if ( v24 )
          operator delete(v24);
        v40 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v40 + 16LL))(v40);
        }
        v41 = v63;
        if ( v63 )
        {
          v63 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
        if ( v13 )
          goto LABEL_91;
        return 2147943568LL;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A9,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)(unsigned int)v31,
        (int)v61);
      if ( v6 )
        operator delete(v6);
      if ( v25 )
        operator delete(v25);
      if ( v24 )
        operator delete(v24);
      if ( v66 )
        (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v66 + 16LL))(v66);
      v42 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v13 == 0;
      goto LABEL_66;
    }
    break;
  }
  v39 = v66;
LABEL_76:
  if ( v39 )
  {
LABEL_127:
    Locale = 0;
    v74 = (const unsigned __int16 *)v39;
    v50 = Microsoft::WRL::Details::MakeAndInitialize<CGameEntry,KnownGameList::IGameEntry,KnownGameList::IGameEntry *>(
            &Locale,
            &v74);
    v23 = v50;
    if ( v50 >= 0 )
    {
      v60 = Locale;
      Locale = 0;
      v51 = v77;
      *v77 = (struct KnownGameList::IGameEntry *)v60;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Locale);
      goto LABEL_163;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)(unsigned int)v50,
      (int)v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Locale);
LABEL_92:
    if ( v6 )
      operator delete(v6);
LABEL_94:
    if ( v25 )
      operator delete(v25);
LABEL_96:
    if ( v24 )
      operator delete(v24);
LABEL_98:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v44 = v13 == 0;
LABEL_66:
    if ( !v44 )
      operator delete(v13);
    return (unsigned int)v23;
  }
  if ( v29 == 1 )
    goto LABEL_78;
  v51 = v77;
LABEL_163:
  if ( !*v51 )
  {
LABEL_78:
    if ( v6 )
      operator delete(v6);
    if ( v25 )
      operator delete(v25);
    if ( v24 )
      operator delete(v24);
    if ( v39 )
      (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v39 + 16LL))(v39);
    v46 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(KnownGameList *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    if ( v13 )
LABEL_91:
      operator delete(v13);
    return 2147943568LL;
  }
  if ( v6 )
    operator delete(v6);
  if ( v25 )
    operator delete(v25);
  if ( v24 )
    operator delete(v24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  if ( v13 )
    operator delete(v13);
  return 0;
}

```

## disassembly

```asm
0x180024320  push    rbp
0x180024322  push    rbx
0x180024323  push    rsi
0x180024324  push    rdi
0x180024325  push    r12
0x180024327  push    r13
0x180024329  push    r14
0x18002432b  push    r15
0x18002432d  lea     rbp, [rsp-0FE8h]
0x180024335  mov     eax, 10E8h
0x18002433a  call    _alloca_probe
0x18002433f  sub     rsp, rax
0x180024342  mov     rax, cs:__security_cookie
0x180024349  xor     rax, rsp
0x18002434c  mov     [rbp+1020h+var_50], rax
0x180024353  mov     [rbp+1020h+var_1088], r9
0x180024357  mov     dword ptr [rsp+1120h+var_10C8+4], r8d
0x18002435c  mov     r14, rdx
0x18002435f  mov     [rbp+1020h+var_10A0], rdx
0x180024363  mov     r13, rcx
0x180024366  xor     r15d, r15d
0x180024369  mov     [r9], r15
0x18002436c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024373  inc     rax
0x180024376  cmp     [rdx+rax*2], r15w
0x18002437b  jnz     short loc_180024373
0x18002437d  mov     [rbp+1020h+var_1090], rax
0x180024381  xorps   xmm0, xmm0
0x180024384  movups  [rbp+1020h+var_1070], xmm0
0x180024388  test    r14, r14
0x18002438b  jz      loc_180024AE0
0x180024391  mov     rsi, r15
0x180024394  mov     ebx, r15d
0x180024397  cmp     ebx, [r13+320h]
0x18002439e  jnb     short loc_1800243E6
0x1800243a0  mov     rax, [r13+0]
0x1800243a4  lea     r8, [rbp+1020h+var_1070]
0x1800243a8  mov     edx, ebx
0x1800243aa  mov     rcx, r13
0x1800243ad  mov     rax, [rax+58h]
0x1800243b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243b6  mov     edi, eax
0x1800243b8  test    eax, eax
0x1800243ba  js      loc_18002445A
0x1800243c0  cmp     word ptr [rbp+1020h+var_1070], r15w
0x1800243c5  jz      short loc_1800243E6
0x1800243c7  mov     r8d, 4
0x1800243cd  mov     rdx, r14
0x1800243d0  lea     rcx, [rbp+1020h+var_1070]
0x1800243d4  call    cs:__imp__o__wcsnicmp
0x1800243da  test    eax, eax
0x1800243dc  jg      short loc_1800243E6
0x1800243de  lea     rsi, [rbp+1020h+var_1060]
0x1800243e2  inc     ebx
0x1800243e4  jmp     short loc_180024397
0x1800243e6  test    rsi, rsi
0x1800243e9  jz      loc_1800244B5
0x1800243ef  lea     esi, [rbx-1]
0x1800243f2  mov     rdi, r15
0x1800243f5  mov     [rbp+1020h+var_1080], r15
0x1800243f9  mov     dword ptr [rsp+1120h+var_10C8], 1000h
0x180024401  mov     rax, [r13+0]
0x180024405  lea     r9, [rsp+1120h+var_10C8]
0x18002440a  lea     r8, [rbp+1020h+var_1050]
0x18002440e  mov     edx, esi
0x180024410  mov     rcx, r13
0x180024413  mov     rax, [rax+60h]
0x180024417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002441c  mov     ebx, eax
0x18002441e  test    eax, eax
0x180024420  jz      loc_1800244BC
0x180024426  cmp     eax, 8007007Ah
0x18002442b  jz      loc_1800244C8
0x180024431  test    eax, eax
0x180024433  jns     loc_1806ECC10
0x180024439  mov     rcx, [rbp+1028h]; this
0x180024440  mov     r9d, eax; char *
0x180024443  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002444a  mov     edx, 28Eh; void *
0x18002444f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024454  nop
0x180024455  jmp     loc_1806ECC10
0x18002445a  mov     rcx, [rbp+1028h]; this
0x180024461  mov     r9d, eax; char *
0x180024464  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002446b  mov     edx, 433h; void *
0x180024470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024475  mov     rcx, [rbp+1028h]; this
0x18002447c  mov     r9d, edi; char *
0x18002447f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180024486  mov     edx, 286h; void *
0x18002448b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024490  mov     eax, edi
0x180024492  mov     rcx, [rbp+1020h+var_50]
0x180024499  xor     rcx, rsp; StackCookie
0x18002449c  call    __security_check_cookie
0x1800244a1  add     rsp, 10E8h
0x1800244a8  pop     r15
0x1800244aa  pop     r14
0x1800244ac  pop     r13
0x1800244ae  pop     r12
0x1800244b0  pop     rdi
0x1800244b1  pop     rsi
0x1800244b2  pop     rbx
0x1800244b3  pop     rbp
0x1800244b4  retn
0x1800244b5  mov     edi, 80070002h
0x1800244ba  jmp     short loc_180024475
0x1800244bc  cmp     ebx, 8007007Ah
0x1800244c2  jnz     loc_180024B05
0x1800244c8  mov     ecx, dword ptr [rsp+1120h+var_10C8]; unsigned __int64
0x1800244cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800244d3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800244d8  mov     rdi, rax
0x1800244db  mov     [rbp+1020h+var_1080], rax
0x1800244df  test    rax, rax
0x1800244e2  jz      loc_180024764
0x1800244e8  mov     rax, [r13+0]
0x1800244ec  lea     r9, [rsp+1120h+var_10C8]
0x1800244f1  mov     r8, rdi
0x1800244f4  mov     edx, esi
0x1800244f6  mov     rcx, r13
0x1800244f9  mov     rax, [rax+60h]
0x1800244fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024502  mov     ebx, eax
0x180024504  test    eax, eax
0x180024506  jns     short loc_180024533
0x180024508  mov     rcx, [rbp+1028h]; this
0x18002450f  mov     r9d, eax; char *
0x180024512  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180024519  mov     edx, 297h; void *
0x18002451e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024523  nop
0x180024524  mov     rcx, rdi; Block
0x180024527  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002452c  mov     eax, ebx
0x18002452e  jmp     loc_180024492
0x180024533  mov     r14, rdi
0x180024536  mov     rsi, rdi
0x180024539  mov     [rsp+1120h+var_10E8], r15
0x18002453e  mov     ebx, dword ptr [rsp+1120h+var_10C8]
0x180024542  lea     rcx, [rsp+1120h+var_10E8]
0x180024547  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002454c  mov     r8d, ebx; unsigned __int8 *
0x18002454f  mov     rdx, rsi; struct KnownGameList::IEnumerateEntries **
0x180024552  lea     rcx, [rsp+1120h+var_10E8]; this
0x180024557  call    ?CreateEnumerateEntriesInstance@KnownGameList@@YAJPEAPEAUIEnumerateEntries@1@PEAEK@Z; KnownGameList::CreateEnumerateEntriesInstance(KnownGameList::IEnumerateEntries * *,uchar *,ulong)
0x18002455c  mov     ebx, eax
0x18002455e  test    eax, eax
0x180024560  js      loc_18002482E
0x180024566  mov     [rsp+1120h+var_10F0], r15
0x18002456b  mov     [rsp+1120h+var_10D0], r15
0x180024570  mov     rsi, r15
0x180024573  mov     [rbp+1020h+var_1078], r15
0x180024577  mov     r14, r15
0x18002457a  mov     [rbp+1020h+var_1060], r15
0x18002457e  mov     qword ptr [rbp+1020h+var_1070], r15
0x180024582  mov     rbx, [rsp+1120h+var_10E8]
0x180024587  mov     rax, [rbx]
0x18002458a  mov     r12, [rax+18h]
0x18002458e  mov     rcx, [rsp+1120h+var_10F0]
0x180024593  test    rcx, rcx
0x180024596  jz      short loc_1800245AE
0x180024598  mov     [rsp+1120h+var_10F0], 0
0x1800245a1  mov     rax, [rcx]
0x1800245a4  mov     rax, [rax+10h]
0x1800245a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ad  nop
0x1800245ae  lea     rdx, [rsp+1120h+var_10F0]
0x1800245b3  mov     rcx, rbx
0x1800245b6  mov     rax, r12
0x1800245b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245be  mov     [rsp+1120h+var_10A8], eax
0x1800245c2  test    eax, eax
0x1800245c4  jnz     loc_180024B11
0x1800245ca  xor     r12d, r12d
0x1800245cd  mov     [rbp+1020h+var_1098], r12
0x1800245d1  mov     [rsp+1120h+var_10B0], r12d
0x1800245d6  mov     rcx, [rsp+1120h+var_10F0]
0x1800245db  mov     rax, [rcx]
0x1800245de  lea     r8, [rsp+1120h+var_10B0]
0x1800245e3  lea     rdx, [rbp+1020h+var_1098]
0x1800245e7  mov     rax, [rax+18h]
0x1800245eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245f0  mov     ebx, eax
0x1800245f2  test    eax, eax
0x1800245f4  js      loc_18002478D
0x1800245fa  mov     eax, [rsp+1120h+var_10B0]
0x1800245fe  mov     dword ptr [rsp+1120h+var_10C0], eax
0x180024602  mov     rax, [rbp+1020h+var_1098]
0x180024606  mov     [rsp+1120h+var_10B8], rax
0x18002460b  xor     ebx, ebx
0x18002460d  mov     [rsp+1120h+var_10D8], ebx
0x180024611  lea     rdx, Locale; "C"
0x180024618  xor     ecx, ecx; Category
0x18002461a  call    cs:__imp__create_locale
0x180024620  mov     rcx, rax; Locale
0x180024623  mov     [rsp+1120h+Locale], rax
0x180024628  mov     eax, dword ptr [rsp+1120h+var_10C0]
0x18002462c  mov     rdx, [rbp+1020h+var_1090]
0x180024630  cmp     ebx, eax
0x180024632  jnb     loc_180024880
0x180024638  cmp     ebx, edx
0x18002463a  jnb     loc_180024875
0x180024640  add     rbx, rbx
0x180024643  mov     rdx, rcx; Locale
0x180024646  mov     rax, [rsp+1120h+var_10B8]
0x18002464b  movzx   ecx, word ptr [rax+rbx]; C
0x18002464f  call    cs:__imp__towlower_l
0x180024655  movzx   r12d, ax
0x180024659  mov     rdx, [rsp+1120h+Locale]; Locale
0x18002465e  mov     rax, [rbp+1020h+var_10A0]
0x180024662  movzx   ecx, word ptr [rax+rbx]; C
0x180024666  call    cs:__imp__towlower_l
0x18002466c  movzx   ecx, ax
0x18002466f  mov     ebx, [rsp+1120h+var_10D8]
0x180024673  inc     ebx
0x180024675  mov     [rsp+1120h+var_10D8], ebx
0x180024679  sub     r12d, ecx
0x18002467c  mov     rcx, [rsp+1120h+Locale]; Locale
0x180024681  jz      short loc_180024628
0x180024683  call    cs:__imp__free_locale
0x180024689  test    r12d, r12d
0x18002468c  jg      short loc_1800246D9
0x18002468e  jnz     loc_180024582
0x180024694  xor     eax, eax
0x180024696  mov     word ptr [rsp+1120h+var_10D8], ax
0x18002469b  mov     rcx, [rsp+1120h+var_10F0]
0x1800246a0  mov     rax, [rcx]
0x1800246a3  lea     rdx, [rsp+1120h+var_10D8]
0x1800246a8  mov     rax, [rax+28h]
0x1800246ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246b1  mov     ebx, eax
0x1800246b3  test    eax, eax
0x1800246b5  js      loc_1806ECDB6
0x1800246bb  movzx   ecx, word ptr [rsp+1120h+var_10D8]
0x1800246c0  test    cx, cx
0x1800246c3  jz      loc_1806ECC17
0x1800246c9  cmp     dword ptr [rsp+1120h+var_10C8+4], 0
0x1800246ce  jz      loc_180024582
0x1800246d4  jmp     loc_1806ECC17
0x1800246d9  mov     r12, [rsp+1120h+var_10D0]
0x1800246de  test    r12, r12
0x1800246e1  jnz     loc_180024B1B
0x1800246e7  test    r15, r15
0x1800246ea  jz      short loc_1800246F5
0x1800246ec  mov     rcx, r15; Block
0x1800246ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800246f4  nop
0x1800246f5  test    r14, r14
0x1800246f8  jz      short loc_180024703
0x1800246fa  mov     rcx, r14; Block
0x1800246fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024702  nop
0x180024703  test    rsi, rsi
0x180024706  jz      short loc_180024711
0x180024708  mov     rcx, rsi; Block
0x18002470b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024710  nop
0x180024711  mov     rcx, [rsp+1120h+var_10F0]
0x180024716  test    rcx, rcx
0x180024719  jz      short loc_180024731
0x18002471b  mov     [rsp+1120h+var_10F0], 0
0x180024724  mov     rax, [rcx]
0x180024727  mov     rax, [rax+10h]
0x18002472b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024730  nop
0x180024731  mov     rcx, [rsp+1120h+var_10E8]
0x180024736  test    rcx, rcx
0x180024739  jz      short loc_180024751
0x18002473b  mov     [rsp+1120h+var_10E8], 0
0x180024744  mov     rax, [rcx]
0x180024747  mov     rax, [rax+10h]
0x18002474b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024750  nop
0x180024751  test    rdi, rdi
0x180024754  jnz     loc_180024934
0x18002475a  mov     eax, 80070490h
0x18002475f  jmp     loc_180024492
0x180024764  mov     rcx, [rbp+1028h]; this
0x18002476b  mov     r9d, 8007000Eh; char *
0x180024771  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180024778  mov     edx, 293h; void *
0x18002477d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024782  nop
0x180024783  mov     eax, 8007000Eh
0x180024788  jmp     loc_180024492
0x18002478d  mov     rcx, [rbp+1028h]; this
0x180024794  mov     r9d, ebx; char *
0x180024797  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002479e  mov     edx, 2A9h; void *
0x1800247a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247a8  nop
0x1800247a9  test    r15, r15
0x1800247ac  jz      short loc_1800247B7
0x1800247ae  mov     rcx, r15; Block
0x1800247b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800247b6  nop
0x1800247b7  test    r14, r14
0x1800247ba  jz      short loc_1800247C5
  ... truncated ...
```
