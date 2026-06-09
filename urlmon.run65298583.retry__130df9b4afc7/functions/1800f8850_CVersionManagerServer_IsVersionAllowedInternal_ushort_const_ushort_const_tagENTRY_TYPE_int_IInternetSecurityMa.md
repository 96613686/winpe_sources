# CVersionManagerServer::_IsVersionAllowedInternal(ushort const *,ushort const *,tagENTRY_TYPE,int,IInternetSecurityManagerEx2 *,IUri *,ushort * *,ushort * *,int *,int *)

- ea: `0x1800f8850`
- end: `0x1800f8e78`
- name: `?_IsVersionAllowedInternal@CVersionManagerServer@@AEAAJPEBG0W4tagENTRY_TYPE@@HPEAUIInternetSecurityManagerEx2@@PEAUIUri@@PEAPEAG4PEAH5@Z`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f6630`

## callees

- `0x1800150e0`
- `0x18001e340`
- `0x1800f61e0`
- `0x1800f6fac`
- `0x1800f7f28`
- `0x1800f8000`
- `0x1800f81bc`
- `0x1800f85c8`
- `0x1800f86b0`
- `0x1800f8850`
- `0x1800f9860`
- `0x1800f9bf8`
- `0x1800faab0`
- `0x1800fcc7c`
- `0x18011ba3e`
- `0x18011c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800f8b85`
- `msvcrt!memcpy_s` at `0x1800f8b85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8dd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8dd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f892e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f8c12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f892e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f8c12`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800f8b9a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800f8b9a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f8de3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f8de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e0f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8d1b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8d5e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8d1b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8d5e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8e48`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8e51`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8e48`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8e51`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_IsVersionAllowedInternal(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        struct IInternetSecurityManagerEx2 *a6,
        struct IUri *a7,
        OLECHAR **a8,
        OLECHAR **a9,
        _DWORD *a10,
        _DWORD *a11)
{
  OLECHAR **v13; // rbx
  OLECHAR *v14; // r12
  OLECHAR *v15; // r13
  int v16; // r14d
  __int64 v17; // rcx
  int FileInfoForEntry; // esi
  int v19; // edx
  int v20; // r9d
  const unsigned __int16 *v21; // r12
  int v22; // r8d
  unsigned int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rbx
  char *v28; // rbx
  unsigned int v29; // r10d
  int v30; // eax
  int v31; // r14d
  __int64 v32; // rcx
  int v33; // eax
  const OLECHAR *v34; // rcx
  const OLECHAR *v35; // rcx
  int v36; // [rsp+40h] [rbp-30h] BYREF
  enum tagURLZONE v37; // [rsp+44h] [rbp-2Ch] BYREF
  CBlockListManager *v38[2]; // [rsp+48h] [rbp-28h] BYREF
  void *Source; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v40[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v43; // [rsp+C8h] [rbp+58h]

  v43 = a4;
  if ( a10 && a11 && a2 && (unsigned int)(a4 - 1) <= 1 )
  {
    if ( !*(_BYTE *)(a1 + 24) )
      return 2147947423LL;
    if ( a8 )
      *a8 = 0;
    v13 = a9;
    if ( a9 )
      *a9 = 0;
    v14 = 0;
    *a10 = 1;
    v15 = 0;
    *a11 = 0;
    v16 = 0;
    v17 = *(_QWORD *)(a1 + 1688);
    Source = 0;
    v36 = 0;
    v37 = URLZONE_INVALID;
    FileInfoForEntry = CFileInfoCache::GetFileInfoForEntry(v17, a2, (unsigned __int8 *)&Source, a4, a4);
    if ( FileInfoForEntry < 0 )
      goto LABEL_81;
    v40[0] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1928));
    if ( *(_QWORD *)(a1 + 1984) )
    {
      FileInfoForEntry = CVersionManagerServer::_EnsureLoadedBlockListIsLatestNotThreadSafe(
                           (CVersionManagerServer *)a1,
                           v19);
      if ( FileInfoForEntry < 0 )
        goto LABEL_32;
      v21 = (const unsigned __int16 *)(a1 + 30);
    }
    else
    {
      v21 = (const unsigned __int16 *)(a1 + 30);
      v38[0] = 0;
      FileInfoForEntry = CVersionManagerServer::_CreateBlockListManager(
                           (CVersionManagerServer *)a1,
                           v38,
                           (const unsigned __int16 *)(a1 + 30),
                           v20);
      if ( FileInfoForEntry < 0 )
        goto LABEL_17;
      FileInfoForEntry = CVersionManagerServer::_SwitchBlockListNotThreadSafe((CVersionManagerServer *)a1, v38, v22);
      if ( FileInfoForEntry < 0 )
      {
        if ( v38[0] )
          CBlockListManager::`scalar deleting destructor'(v38[0], v23);
        goto LABEL_17;
      }
    }
    v24 = *(_QWORD *)(a1 + 1984);
    if ( v24 )
    {
      LODWORD(v38[0]) = 0;
      FileInfoForEntry = CBlockListManager::GetBlockListEntry(v24, a2, v40, v43, v38, a5);
      if ( FileInfoForEntry >= 0 && LODWORD(v38[0]) )
      {
        v25 = v40[0];
        if ( v40[0] )
        {
          FileInfoForEntry = CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(
                               (CVersionManagerServer *)a1,
                               *(struct CBlockListManager **)(a1 + 1984),
                               v21,
                               1,
                               1);
          if ( FileInfoForEntry < 0 )
            goto LABEL_69;
          v40[0] = 0;
          LODWORD(v38[0]) = 0;
          FileInfoForEntry = CVersionManagerServer::_GetGroupEntry(a1, a2, v43, a5, v25, Source, v40, v38);
          if ( FileInfoForEntry >= 0 )
          {
            if ( LODWORD(v38[0]) )
            {
              v27 = v40[0];
              if ( v40[0] )
              {
                if ( *(_BYTE *)(v40[0] + 18LL) )
                {
                  v16 = 3;
                  *a11 = 1;
                  *a10 = 0;
LABEL_30:
                  v14 = 0;
                  goto LABEL_31;
                }
                if ( !*(_BYTE *)(v40[0] + 17LL) )
                {
                  if ( !*(_BYTE *)(v40[0] + 16LL) )
                  {
                    if ( !*(_BYTE *)(a1 + 26) )
                      goto LABEL_30;
                    v33 = 0;
                    LODWORD(v38[0]) = 0;
                    if ( a7 && a6 )
                    {
                      FileInfoForEntry = CVersionManagerServer::_IsUriExcludedFromVersionCheckNotThreadSafe(
                                           (CVersionManagerServer *)a1,
                                           a6,
                                           a7,
                                           (enum EXT_SQM_VERSION_REASON *)&v36,
                                           (int *)v38,
                                           &v37);
                      if ( FileInfoForEntry < 0 )
                      {
LABEL_68:
                        v16 = v36;
                        goto LABEL_69;
                      }
                      v16 = v36;
                      v33 = (int)v38[0];
                    }
                    if ( !v33 )
                    {
                      LODWORD(v38[0]) = 0;
                      FileInfoForEntry = CVersionManagerServer::_IsEntryExcludedFromVersionCheck(
                                           v26,
                                           a2,
                                           &v36,
                                           v43,
                                           v38);
                      if ( FileInfoForEntry >= 0 && !LODWORD(v38[0]) )
                      {
                        v16 = 6;
                        *a11 = *(_BYTE *)(v27 + 19) != 0;
                        *a10 = 0;
                        if ( !*a11 && (v34 = *(const OLECHAR **)(v27 + 8)) != 0 && a8 )
                        {
                          v14 = SysAllocString(v34);
                          if ( !v14 )
                          {
                            FileInfoForEntry = -2147024882;
                            goto LABEL_31;
                          }
                        }
                        else
                        {
                          v14 = 0;
                        }
                        if ( !*a11 )
                        {
                          v35 = *(const OLECHAR **)v27;
                          if ( *(_QWORD *)v27 )
                          {
                            v13 = a9;
                            if ( a9 )
                            {
                              v15 = SysAllocString(v35);
                              if ( !v15 )
                                FileInfoForEntry = -2147024882;
                            }
LABEL_32:
                            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1928));
                            if ( FileInfoForEntry >= 0 )
                            {
                              if ( !Source )
                              {
LABEL_85:
                                if ( a8 && v14 )
                                {
                                  *a8 = v14;
                                  v14 = 0;
                                }
                                if ( v13 )
                                {
                                  if ( v15 )
                                  {
                                    *v13 = v15;
                                    v15 = 0;
                                  }
                                }
LABEL_91:
                                SysFreeString(v14);
                                SysFreeString(v15);
                                return (unsigned int)FileInfoForEntry;
                              }
                              if ( a7 && a6 && v37 == URLZONE_INVALID )
                                ((void (__fastcall *)(struct IInternetSecurityManagerEx2 *, struct IUri *, enum tagURLZONE *, _QWORD, _QWORD, _QWORD))a6->lpVtbl->MapUrlToZoneEx2)(
                                  a6,
                                  a7,
                                  &v37,
                                  0,
                                  0,
                                  0);
                              v28 = (char *)operator new(0xA78u);
                              if ( v28 )
                              {
                                *(_QWORD *)v28 = 0;
                                *((_DWORD *)v28 + 2) = 0;
                                *((_DWORD *)v28 + 664) = -1;
                                *(_QWORD *)(v28 + 2660) = 0;
                                *((_DWORD *)v28 + 667) = 0;
                                *((_QWORD *)v28 + 334) = 0;
                                memset_0(v28 + 1616, 0, 0x208u);
                                memset_0(v28 + 2136, 0, 0x208u);
                                if ( a7 )
                                  ((void (__fastcall *)(struct IUri *, char *))a7->lpVtbl->GetAbsoluteUri)(a7, v28);
                                *((_DWORD *)v28 + 2) = v43;
                                if ( !memcpy_s(v28 + 16, 0x640u, Source, 0x640u) )
                                {
                                  *((_QWORD *)v28 + 5) = PathFindFileNameW((LPCWSTR)v28 + 544);
                                  if ( (int)StringCchCopyW((unsigned __int16 *)v28 + 808, 0x104u, a2) >= 0
                                    && (int)StringCchCopyW((unsigned __int16 *)v28 + 1068, v29, a3) >= 0 )
                                  {
                                    *((_DWORD *)v28 + 664) = v37;
                                    *((_DWORD *)v28 + 665) = v16;
                                    *((_DWORD *)v28 + 666) = *a10;
                                    *((_DWORD *)v28 + 667) = a5;
                                    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1784));
                                    v30 = *(_DWORD *)(a1 + 1840);
                                    v31 = -2147467259;
                                    if ( v30 < 32 )
                                    {
                                      v32 = a1 + 1832;
                                      if ( v30 )
                                        *(_QWORD *)(*(_QWORD *)v32 + 2672LL) = v28;
                                      else
                                        *(_QWORD *)(a1 + 1824) = v28;
                                      ++*(_DWORD *)(a1 + 1840);
                                      *(_QWORD *)v32 = v28;
                                      v31 = 0;
                                      *((_QWORD *)v28 + 334) = 0;
                                    }
                                    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1784));
                                    if ( v31 >= 0 )
                                    {
                                      SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 1696));
LABEL_80:
                                      v13 = a9;
                                      goto LABEL_81;
                                    }
                                  }
                                }
                              }
                              else
                              {
                                v28 = 0;
                              }
                              CVersionManagerServer::s_TelParamsFree((struct CVersionManagerServer::TELEMETRY_PARAMS *)v28);
                              goto LABEL_80;
                            }
LABEL_81:
                            if ( Source && !*((_BYTE *)Source + 1593) )
                            {
                              CoTaskMemFree(Source);
                              Source = 0;
                            }
                            if ( FileInfoForEntry < 0 )
                              goto LABEL_91;
                            goto LABEL_85;
                          }
                        }
LABEL_31:
                        v13 = a9;
                        goto LABEL_32;
                      }
                      goto LABEL_68;
                    }
LABEL_69:
                    v14 = 0;
                    goto LABEL_31;
                  }
                  if ( !*(_BYTE *)(a1 + 26) )
                    goto LABEL_30;
                }
              }
            }
          }
          v16 = 10;
          goto LABEL_30;
        }
        v13 = a9;
      }
      v16 = 5;
    }
LABEL_17:
    v14 = 0;
    goto LABEL_32;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800f8850  mov     rax, rsp
0x1800f8853  mov     [rax+8], rbx
0x1800f8857  mov     [rax+20h], r9d
0x1800f885b  mov     [rax+18h], r8
0x1800f885f  mov     [rax+10h], rdx
0x1800f8863  push    rbp
0x1800f8864  push    rsi
0x1800f8865  push    rdi
0x1800f8866  push    r12
0x1800f8868  push    r13
0x1800f886a  push    r14
0x1800f886c  push    r15
0x1800f886e  mov     rbp, rsp
0x1800f8871  sub     rsp, 70h
0x1800f8875  mov     rdi, rcx
0x1800f8878  xor     r8d, r8d
0x1800f887b  mov     rcx, [rbp+arg_48]
0x1800f8882  test    rcx, rcx
0x1800f8885  jz      loc_1800F8E5B
0x1800f888b  mov     r15, [rbp+arg_50]
0x1800f8892  test    r15, r15
0x1800f8895  jz      loc_1800F8E5B
0x1800f889b  test    rdx, rdx
0x1800f889e  jz      loc_1800F8E5B
0x1800f88a4  lea     eax, [r9-1]
0x1800f88a8  cmp     eax, 1
0x1800f88ab  ja      loc_1800F8E5B
0x1800f88b1  cmp     [rdi+18h], r8b
0x1800f88b5  jnz     short loc_1800F88C1
0x1800f88b7  mov     eax, 8007139Fh
0x1800f88bc  jmp     loc_1800F8E60
0x1800f88c1  mov     rax, [rbp+arg_38]
0x1800f88c5  test    rax, rax
0x1800f88c8  jz      short loc_1800F88CD
0x1800f88ca  mov     [rax], r8
0x1800f88cd  mov     rbx, [rbp+arg_40]
0x1800f88d4  test    rbx, rbx
0x1800f88d7  jz      short loc_1800F88DC
0x1800f88d9  mov     [rbx], r8
0x1800f88dc  mov     eax, [rbp+arg_20]
0x1800f88df  mov     r12, r8
0x1800f88e2  mov     dword ptr [rcx], 1
0x1800f88e8  mov     r13, r8
0x1800f88eb  mov     [r15], r8d
0x1800f88ee  mov     r14d, r8d
0x1800f88f1  mov     rcx, [rdi+698h]
0x1800f88f8  mov     [rbp+Source], r8
0x1800f88fc  mov     [rbp+var_30], r8d
0x1800f8900  lea     r8, [rbp+Source]
0x1800f8904  mov     dword ptr [rsp+70h+var_48], eax
0x1800f8908  mov     [rbp+var_2C], 0FFFFFFFFh
0x1800f890f  mov     dword ptr [rsp+70h+var_50], r9d
0x1800f8914  call    ?GetFileInfoForEntry@CFileInfoCache@@QEAAJPEBGPEAPEAUEXT_FILEINFO@@HW4tagENTRY_TYPE@@H@Z; CFileInfoCache::GetFileInfoForEntry(ushort const *,EXT_FILEINFO * *,int,tagENTRY_TYPE,int)
0x1800f8919  mov     esi, eax
0x1800f891b  test    eax, eax
0x1800f891d  js      loc_1800F8DFD
0x1800f8923  lea     rcx, [rdi+788h]; lpCriticalSection
0x1800f892a  mov     [rbp+var_10], r13
0x1800f892e  call    cs:__imp_EnterCriticalSection
0x1800f8934  mov     rcx, rdi; this
0x1800f8937  cmp     [rdi+7C0h], r13
0x1800f893e  jnz     short loc_1800F8982
0x1800f8940  lea     r12, [rdi+1Eh]
0x1800f8944  mov     [rbp+var_28], r13
0x1800f8948  mov     r8, r12; unsigned __int16 *
0x1800f894b  lea     rdx, [rbp+var_28]; struct CBlockListManager **
0x1800f894f  call    ?_CreateBlockListManager@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@PEBGH@Z; CVersionManagerServer::_CreateBlockListManager(CBlockListManager * *,ushort const *,int)
0x1800f8954  mov     esi, eax
0x1800f8956  test    eax, eax
0x1800f8958  js      short loc_1800F897A
0x1800f895a  lea     rdx, [rbp+var_28]; struct CBlockListManager **
0x1800f895e  mov     rcx, rdi; this
0x1800f8961  call    ?_SwitchBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@H@Z; CVersionManagerServer::_SwitchBlockListNotThreadSafe(CBlockListManager * *,int)
0x1800f8966  mov     esi, eax
0x1800f8968  test    eax, eax
0x1800f896a  jns     short loc_1800F8995
0x1800f896c  mov     rcx, [rbp+var_28]; this
0x1800f8970  test    rcx, rcx
0x1800f8973  jz      short loc_1800F897A
0x1800f8975  call    ??_GCBlockListManager@@QEAAPEAXI@Z; CBlockListManager::`scalar deleting destructor'(uint)
0x1800f897a  mov     r12, r13
0x1800f897d  jmp     loc_1800F8A94
0x1800f8982  call    ?_EnsureLoadedBlockListIsLatestNotThreadSafe@CVersionManagerServer@@AEAAJH@Z; CVersionManagerServer::_EnsureLoadedBlockListIsLatestNotThreadSafe(int)
0x1800f8987  mov     esi, eax
0x1800f8989  test    eax, eax
0x1800f898b  js      loc_1800F8A94
0x1800f8991  lea     r12, [rdi+1Eh]
0x1800f8995  mov     rcx, [rdi+7C0h]
0x1800f899c  test    rcx, rcx
0x1800f899f  jz      short loc_1800F897A
0x1800f89a1  mov     r9d, [rbp+arg_18]
0x1800f89a5  lea     rax, [rbp+var_28]
0x1800f89a9  mov     rdx, [rbp+arg_8]
0x1800f89ad  lea     r8, [rbp+var_10]
0x1800f89b1  mov     [rsp+70h+var_50], rax
0x1800f89b6  mov     dword ptr [rbp+var_28], r13d
0x1800f89ba  call    ?GetBlockListEntry@CBlockListManager@@QEAAJPEBGPEAPEBUBLOCKLIST_ENTRY@@W4tagENTRY_TYPE@@PEAH@Z; CBlockListManager::GetBlockListEntry(ushort const *,BLOCKLIST_ENTRY const * *,tagENTRY_TYPE,int *)
0x1800f89bf  mov     esi, eax
0x1800f89c1  test    eax, eax
0x1800f89c3  js      loc_1800F8DA2
0x1800f89c9  cmp     dword ptr [rbp+var_28], r13d
0x1800f89cd  jz      loc_1800F8DA2
0x1800f89d3  mov     rbx, [rbp+var_10]
0x1800f89d7  test    rbx, rbx
0x1800f89da  jz      loc_1800F8D9B
0x1800f89e0  mov     rdx, [rdi+7C0h]; struct CBlockListManager *
0x1800f89e7  mov     eax, 1
0x1800f89ec  mov     r9d, eax; int
0x1800f89ef  mov     dword ptr [rsp+70h+var_50], eax; int
0x1800f89f3  mov     r8, r12; unsigned __int16 *
0x1800f89f6  mov     rcx, rdi; this
0x1800f89f9  call    ?_ForceLoadFullBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAVCBlockListManager@@PEBGHH@Z; CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(CBlockListManager *,ushort const *,int,int)
0x1800f89fe  mov     esi, eax
0x1800f8a00  test    eax, eax
0x1800f8a02  js      loc_1800F8D7E
0x1800f8a08  mov     r12d, [rbp+arg_18]
0x1800f8a0c  lea     rax, [rbp+var_28]
0x1800f8a10  mov     r9d, [rbp+arg_20]
0x1800f8a14  mov     r8d, r12d
0x1800f8a17  mov     rdx, [rbp+arg_8]
0x1800f8a1b  mov     rcx, rdi
0x1800f8a1e  mov     [rsp+70h+var_38], rax
0x1800f8a23  lea     rax, [rbp+var_10]
0x1800f8a27  mov     [rsp+70h+var_40], rax
0x1800f8a2c  mov     rax, [rbp+Source]
0x1800f8a30  mov     [rsp+70h+var_48], rax
0x1800f8a35  mov     [rsp+70h+var_50], rbx
0x1800f8a3a  mov     [rbp+var_10], r13
0x1800f8a3e  mov     dword ptr [rbp+var_28], r13d
0x1800f8a42  call    ?_GetGroupEntry@CVersionManagerServer@@AEAAJPEBGW4tagENTRY_TYPE@@HPEBUBLOCKLIST_ENTRY@@PEAUEXT_FILEINFO@@PEAPEBUGROUP_ENTRY@@PEAH@Z; CVersionManagerServer::_GetGroupEntry(ushort const *,tagENTRY_TYPE,int,BLOCKLIST_ENTRY const *,EXT_FILEINFO *,GROUP_ENTRY const * *,int *)
0x1800f8a47  xor     r9d, r9d
0x1800f8a4a  mov     esi, eax
0x1800f8a4c  test    eax, eax
0x1800f8a4e  js      loc_1800F8D90
0x1800f8a54  cmp     dword ptr [rbp+var_28], r9d
0x1800f8a58  jz      loc_1800F8D90
0x1800f8a5e  mov     rbx, [rbp+var_10]
0x1800f8a62  test    rbx, rbx
0x1800f8a65  jz      loc_1800F8D90
0x1800f8a6b  cmp     [rbx+12h], r9b
0x1800f8a6f  jz      loc_1800F8C48
0x1800f8a75  mov     rax, [rbp+arg_48]
0x1800f8a7c  lea     r14d, [r9+3]
0x1800f8a80  mov     dword ptr [r15], 1
0x1800f8a87  mov     [rax], r9d
0x1800f8a8a  mov     r12, r9
0x1800f8a8d  mov     rbx, [rbp+arg_40]
0x1800f8a94  lea     rcx, [rdi+788h]; lpCriticalSection
0x1800f8a9b  call    cs:__imp_LeaveCriticalSection
0x1800f8aa1  test    esi, esi
0x1800f8aa3  js      loc_1800F8DFD
0x1800f8aa9  cmp     [rbp+Source], 0
0x1800f8aae  jz      loc_1800F8E21
0x1800f8ab4  mov     r15, [rbp+arg_30]
0x1800f8ab8  test    r15, r15
0x1800f8abb  jz      short loc_1800F8AF4
0x1800f8abd  mov     rcx, [rbp+arg_28]
0x1800f8ac1  test    rcx, rcx
0x1800f8ac4  jz      short loc_1800F8AF4
0x1800f8ac6  cmp     [rbp+var_2C], 0FFFFFFFFh
0x1800f8aca  jnz     short loc_1800F8AF4
0x1800f8acc  mov     rax, [rcx]
0x1800f8acf  lea     r8, [rbp+var_2C]
0x1800f8ad3  mov     [rsp+70h+var_48], 0
0x1800f8adc  xor     r9d, r9d
0x1800f8adf  mov     rdx, r15
0x1800f8ae2  mov     [rsp+70h+var_50], 0
0x1800f8aeb  mov     rax, [rax+60h]
0x1800f8aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8af4  mov     ecx, 0A78h; Size
0x1800f8af9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f8afe  mov     rbx, rax
0x1800f8b01  xor     eax, eax
0x1800f8b03  test    rbx, rbx
0x1800f8b06  jz      loc_1800F8DEB
0x1800f8b0c  lea     rcx, [rbx+650h]; void *
0x1800f8b13  mov     [rbx], rax
0x1800f8b16  xor     edx, edx; Val
0x1800f8b18  mov     [rbx+8], eax
0x1800f8b1b  mov     r8d, 208h; Size
0x1800f8b21  mov     dword ptr [rbx+0A60h], 0FFFFFFFFh
0x1800f8b2b  mov     [rbx+0A64h], rax
0x1800f8b32  mov     [rbx+0A6Ch], eax
0x1800f8b38  mov     [rbx+0A70h], rax
0x1800f8b3f  call    memset_0
0x1800f8b44  lea     rcx, [rbx+858h]; void *
0x1800f8b4b  xor     edx, edx; Val
0x1800f8b4d  mov     r8d, 208h; Size
0x1800f8b53  call    memset_0
0x1800f8b58  test    r15, r15
0x1800f8b5b  jz      short loc_1800F8B6F
0x1800f8b5d  mov     rax, [r15]
0x1800f8b60  mov     rdx, rbx
0x1800f8b63  mov     rcx, r15
0x1800f8b66  mov     rax, [rax+38h]
0x1800f8b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8b6f  mov     eax, [rbp+arg_18]
0x1800f8b72  lea     rcx, [rbx+10h]; Destination
0x1800f8b76  mov     edx, 640h; DestinationSize
0x1800f8b7b  mov     [rbx+8], eax
0x1800f8b7e  mov     r8, [rbp+Source]; Source
0x1800f8b82  mov     r9d, edx; SourceSize
0x1800f8b85  call    cs:__imp_memcpy_s
0x1800f8b8b  test    eax, eax
0x1800f8b8d  jnz     loc_1800F8DEE
0x1800f8b93  lea     rcx, [rbx+440h]; pszPath
0x1800f8b9a  call    cs:__imp_PathFindFileNameW
0x1800f8ba0  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1800f8ba4  lea     rcx, [rbx+650h]; unsigned __int16 *
0x1800f8bab  mov     r10d, 104h
0x1800f8bb1  mov     [rbx+28h], rax
0x1800f8bb5  mov     edx, r10d; unsigned __int64
0x1800f8bb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f8bbd  test    eax, eax
0x1800f8bbf  js      loc_1800F8DEE
0x1800f8bc5  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x1800f8bc9  lea     rcx, [rbx+858h]; unsigned __int16 *
0x1800f8bd0  mov     edx, r10d; unsigned __int64
0x1800f8bd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f8bd8  test    eax, eax
0x1800f8bda  js      loc_1800F8DEE
0x1800f8be0  mov     eax, [rbp+var_2C]
0x1800f8be3  lea     r15, [rdi+6F8h]
0x1800f8bea  mov     [rbx+0A60h], eax
0x1800f8bf0  mov     rcx, r15; lpCriticalSection
0x1800f8bf3  mov     rax, [rbp+arg_48]
0x1800f8bfa  mov     [rbx+0A64h], r14d
0x1800f8c01  mov     eax, [rax]
0x1800f8c03  mov     [rbx+0A68h], eax
0x1800f8c09  mov     eax, [rbp+arg_20]
0x1800f8c0c  mov     [rbx+0A6Ch], eax
0x1800f8c12  call    cs:__imp_EnterCriticalSection
0x1800f8c18  mov     eax, [rdi+730h]
0x1800f8c1e  mov     r14d, 80004005h
0x1800f8c24  cmp     eax, 20h ; ' '
0x1800f8c27  jge     loc_1800F8DCE
0x1800f8c2d  lea     rcx, [rdi+728h]
0x1800f8c34  test    eax, eax
0x1800f8c36  jnz     loc_1800F8DAD
0x1800f8c3c  mov     [rdi+720h], rbx
0x1800f8c43  jmp     loc_1800F8DB7
0x1800f8c48  cmp     [rbx+11h], r9b
0x1800f8c4c  jnz     loc_1800F8D90
0x1800f8c52  cmp     [rbx+10h], r9b
0x1800f8c56  jnz     loc_1800F8D86
0x1800f8c5c  cmp     [rdi+1Ah], r9b
0x1800f8c60  jz      loc_1800F8A8A
0x1800f8c66  mov     r8, [rbp+arg_30]; struct IUri *
0x1800f8c6a  mov     eax, r9d
0x1800f8c6d  mov     dword ptr [rbp+var_28], eax
0x1800f8c70  test    r8, r8
0x1800f8c73  jz      short loc_1800F8CB0
0x1800f8c75  mov     rdx, [rbp+arg_28]; struct IInternetSecurityManagerEx2 *
0x1800f8c79  test    rdx, rdx
0x1800f8c7c  jz      short loc_1800F8CB0
0x1800f8c7e  lea     rax, [rbp+var_2C]
0x1800f8c82  mov     rcx, rdi; this
0x1800f8c85  mov     [rsp+70h+var_48], rax; enum tagURLZONE *
0x1800f8c8a  lea     r9, [rbp+var_30]; enum EXT_SQM_VERSION_REASON *
0x1800f8c8e  lea     rax, [rbp+var_28]
0x1800f8c92  mov     [rsp+70h+var_50], rax; int *
0x1800f8c97  call    ?_IsUriExcludedFromVersionCheckNotThreadSafe@CVersionManagerServer@@AEAAJPEAUIInternetSecurityManagerEx2@@PEAUIUri@@PEAW4EXT_SQM_VERSION_REASON@@PEAHPEAW4tagURLZONE@@@Z; CVersionManagerServer::_IsUriExcludedFromVersionCheckNotThreadSafe(IInternetSecurityManagerEx2 *,IUri *,EXT_SQM_VERSION_REASON *,int *,tagURLZONE *)
0x1800f8c9c  xor     r9d, r9d
0x1800f8c9f  mov     esi, eax
0x1800f8ca1  test    eax, eax
0x1800f8ca3  js      loc_1800F8D7A
0x1800f8ca9  mov     r14d, [rbp+var_30]
0x1800f8cad  mov     eax, dword ptr [rbp+var_28]
0x1800f8cb0  test    eax, eax
0x1800f8cb2  jnz     loc_1800F8D7E
0x1800f8cb8  mov     rdx, [rbp+arg_8]
0x1800f8cbc  lea     rax, [rbp+var_28]
0x1800f8cc0  mov     dword ptr [rbp+var_28], r9d
0x1800f8cc4  lea     r8, [rbp+var_30]
0x1800f8cc8  mov     r9d, r12d
0x1800f8ccb  mov     [rsp+70h+var_50], rax
0x1800f8cd0  call    ?_IsEntryExcludedFromVersionCheck@CVersionManagerServer@@AEAAJPEBGPEAW4EXT_SQM_VERSION_REASON@@W4tagENTRY_TYPE@@PEAH@Z; CVersionManagerServer::_IsEntryExcludedFromVersionCheck(ushort const *,EXT_SQM_VERSION_REASON *,tagENTRY_TYPE,int *)
0x1800f8cd5  xor     r9d, r9d
0x1800f8cd8  mov     esi, eax
0x1800f8cda  test    eax, eax
0x1800f8cdc  js      loc_1800F8D7A
0x1800f8ce2  cmp     dword ptr [rbp+var_28], r9d
0x1800f8ce6  jnz     loc_1800F8D7A
0x1800f8cec  cmp     [rbx+13h], r9b
0x1800f8cf0  lea     r14d, [r9+6]
0x1800f8cf4  mov     eax, r9d
0x1800f8cf7  setnz   al
0x1800f8cfa  mov     [r15], eax
0x1800f8cfd  mov     rax, [rbp+arg_48]
0x1800f8d04  mov     [rax], r9d
0x1800f8d07  cmp     [r15], r9d
0x1800f8d0a  jnz     short loc_1800F8D36
0x1800f8d0c  mov     rcx, [rbx+8]; psz
0x1800f8d10  test    rcx, rcx
0x1800f8d13  jz      short loc_1800F8D36
0x1800f8d15  cmp     [rbp+arg_38], r9
0x1800f8d19  jz      short loc_1800F8D36
0x1800f8d1b  call    cs:__imp_SysAllocString
0x1800f8d21  xor     r9d, r9d
0x1800f8d24  mov     r12, rax
  ... truncated ...
```
