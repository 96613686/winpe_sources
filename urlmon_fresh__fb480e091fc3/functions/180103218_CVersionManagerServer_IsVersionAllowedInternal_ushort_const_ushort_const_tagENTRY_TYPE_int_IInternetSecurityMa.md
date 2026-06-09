# CVersionManagerServer::_IsVersionAllowedInternal(ushort const *,ushort const *,tagENTRY_TYPE,int,IInternetSecurityManagerEx2 *,IUri *,ushort * *,ushort * *,int *,int *)

- ea: `0x180103218`
- end: `0x180103889`
- name: `?_IsVersionAllowedInternal@CVersionManagerServer@@AEAAJPEBG0W4tagENTRY_TYPE@@HPEAUIInternetSecurityManagerEx2@@PEAUIUri@@PEAPEAG4PEAH5@Z`
- size: `1649`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180100df0`

## callees

- `0x18001db50`
- `0x180024ea0`
- `0x180100954`
- `0x1801017b0`
- `0x1801028e8`
- `0x1801029c4`
- `0x180102b8c`
- `0x180102f7c`
- `0x180103074`
- `0x180103218`
- `0x1801042e8`
- `0x1801046ac`
- `0x180105658`
- `0x180107a3c`
- `0x1801285fe`
- `0x180129010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180103559`
- `msvcrt!memcpy_s` at `0x180103559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180103469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801037c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180103469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801037c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801032f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801035f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801032f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801035f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180103574`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180103574`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801037db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801037db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010380d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010380d`
- `OLEAUT32!__imp_SysAllocString` at `0x180103701`
- `OLEAUT32!__imp_SysAllocString` at `0x18010374a`
- `OLEAUT32!__imp_SysAllocString` at `0x180103701`
- `OLEAUT32!__imp_SysAllocString` at `0x18010374a`
- `OLEAUT32!__imp_SysFreeString` at `0x18010384c`
- `OLEAUT32!__imp_SysFreeString` at `0x18010385b`
- `OLEAUT32!__imp_SysFreeString` at `0x18010384c`
- `OLEAUT32!__imp_SysFreeString` at `0x18010385b`

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
  CFileInfoCache *v17; // rcx
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
    v17 = *(CFileInfoCache **)(a1 + 1688);
    Source = 0;
    v36 = 0;
    v37 = URLZONE_INVALID;
    FileInfoForEntry = CFileInfoCache::GetFileInfoForEntry(v17, a2, (struct EXT_FILEINFO **)&Source, a4, a4);
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
0x180103218  mov     rax, rsp
0x18010321b  mov     [rax+8], rbx
0x18010321f  mov     [rax+20h], r9d
0x180103223  mov     [rax+18h], r8
0x180103227  mov     [rax+10h], rdx
0x18010322b  push    rbp
0x18010322c  push    rsi
0x18010322d  push    rdi
0x18010322e  push    r12
0x180103230  push    r13
0x180103232  push    r14
0x180103234  push    r15
0x180103236  mov     rbp, rsp
0x180103239  sub     rsp, 70h
0x18010323d  mov     rdi, rcx
0x180103240  xor     r8d, r8d
0x180103243  mov     rcx, [rbp+arg_48]
0x18010324a  test    rcx, rcx
0x18010324d  jz      loc_18010386B
0x180103253  mov     r15, [rbp+arg_50]
0x18010325a  test    r15, r15
0x18010325d  jz      loc_18010386B
0x180103263  test    rdx, rdx
0x180103266  jz      loc_18010386B
0x18010326c  lea     eax, [r9-1]
0x180103270  cmp     eax, 1
0x180103273  ja      loc_18010386B
0x180103279  cmp     [rdi+18h], r8b
0x18010327d  jnz     short loc_180103289
0x18010327f  mov     eax, 8007139Fh
0x180103284  jmp     loc_180103870
0x180103289  mov     rax, [rbp+arg_38]
0x18010328d  test    rax, rax
0x180103290  jz      short loc_180103295
0x180103292  mov     [rax], r8
0x180103295  mov     rbx, [rbp+arg_40]
0x18010329c  test    rbx, rbx
0x18010329f  jz      short loc_1801032A4
0x1801032a1  mov     [rbx], r8
0x1801032a4  mov     eax, [rbp+arg_20]
0x1801032a7  mov     r12, r8
0x1801032aa  mov     dword ptr [rcx], 1
0x1801032b0  mov     r13, r8
0x1801032b3  mov     [r15], r8d
0x1801032b6  mov     r14d, r8d
0x1801032b9  mov     rcx, [rdi+698h]
0x1801032c0  mov     [rbp+Source], r8
0x1801032c4  mov     [rbp+var_30], r8d
0x1801032c8  lea     r8, [rbp+Source]
0x1801032cc  mov     dword ptr [rsp+70h+var_48], eax
0x1801032d0  mov     [rbp+var_2C], 0FFFFFFFFh
0x1801032d7  mov     dword ptr [rsp+70h+var_50], r9d
0x1801032dc  call    ?GetFileInfoForEntry@CFileInfoCache@@QEAAJPEBGPEAPEAUEXT_FILEINFO@@HW4tagENTRY_TYPE@@H@Z; CFileInfoCache::GetFileInfoForEntry(ushort const *,EXT_FILEINFO * *,int,tagENTRY_TYPE,int)
0x1801032e1  mov     esi, eax
0x1801032e3  test    eax, eax
0x1801032e5  js      loc_1801037FB
0x1801032eb  lea     rcx, [rdi+788h]; lpCriticalSection
0x1801032f2  mov     [rbp+var_10], r13
0x1801032f6  call    cs:__imp_EnterCriticalSection
0x1801032fd  nop     dword ptr [rax+rax+00h]
0x180103302  mov     rcx, rdi; this
0x180103305  cmp     [rdi+7C0h], r13
0x18010330c  jnz     short loc_180103350
0x18010330e  lea     r12, [rdi+1Eh]
0x180103312  mov     [rbp+var_28], r13
0x180103316  mov     r8, r12; unsigned __int16 *
0x180103319  lea     rdx, [rbp+var_28]; struct CBlockListManager **
0x18010331d  call    ?_CreateBlockListManager@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@PEBGH@Z; CVersionManagerServer::_CreateBlockListManager(CBlockListManager * *,ushort const *,int)
0x180103322  mov     esi, eax
0x180103324  test    eax, eax
0x180103326  js      short loc_180103348
0x180103328  lea     rdx, [rbp+var_28]; struct CBlockListManager **
0x18010332c  mov     rcx, rdi; this
0x18010332f  call    ?_SwitchBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@H@Z; CVersionManagerServer::_SwitchBlockListNotThreadSafe(CBlockListManager * *,int)
0x180103334  mov     esi, eax
0x180103336  test    eax, eax
0x180103338  jns     short loc_180103363
0x18010333a  mov     rcx, [rbp+var_28]; this
0x18010333e  test    rcx, rcx
0x180103341  jz      short loc_180103348
0x180103343  call    ??_GCBlockListManager@@QEAAPEAXI@Z; CBlockListManager::`scalar deleting destructor'(uint)
0x180103348  mov     r12, r13
0x18010334b  jmp     loc_180103462
0x180103350  call    ?_EnsureLoadedBlockListIsLatestNotThreadSafe@CVersionManagerServer@@AEAAJH@Z; CVersionManagerServer::_EnsureLoadedBlockListIsLatestNotThreadSafe(int)
0x180103355  mov     esi, eax
0x180103357  test    eax, eax
0x180103359  js      loc_180103462
0x18010335f  lea     r12, [rdi+1Eh]
0x180103363  mov     rcx, [rdi+7C0h]
0x18010336a  test    rcx, rcx
0x18010336d  jz      short loc_180103348
0x18010336f  mov     r9d, [rbp+arg_18]
0x180103373  lea     rax, [rbp+var_28]
0x180103377  mov     rdx, [rbp+arg_8]
0x18010337b  lea     r8, [rbp+var_10]
0x18010337f  mov     [rsp+70h+var_50], rax
0x180103384  mov     dword ptr [rbp+var_28], r13d
0x180103388  call    ?GetBlockListEntry@CBlockListManager@@QEAAJPEBGPEAPEBUBLOCKLIST_ENTRY@@W4tagENTRY_TYPE@@PEAH@Z; CBlockListManager::GetBlockListEntry(ushort const *,BLOCKLIST_ENTRY const * *,tagENTRY_TYPE,int *)
0x18010338d  mov     esi, eax
0x18010338f  test    eax, eax
0x180103391  js      loc_180103794
0x180103397  cmp     dword ptr [rbp+var_28], r13d
0x18010339b  jz      loc_180103794
0x1801033a1  mov     rbx, [rbp+var_10]
0x1801033a5  test    rbx, rbx
0x1801033a8  jz      loc_18010378D
0x1801033ae  mov     rdx, [rdi+7C0h]; struct CBlockListManager *
0x1801033b5  mov     eax, 1
0x1801033ba  mov     r9d, eax; int
0x1801033bd  mov     dword ptr [rsp+70h+var_50], eax; int
0x1801033c1  mov     r8, r12; unsigned __int16 *
0x1801033c4  mov     rcx, rdi; this
0x1801033c7  call    ?_ForceLoadFullBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAVCBlockListManager@@PEBGHH@Z; CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(CBlockListManager *,ushort const *,int,int)
0x1801033cc  mov     esi, eax
0x1801033ce  test    eax, eax
0x1801033d0  js      loc_180103770
0x1801033d6  mov     r12d, [rbp+arg_18]
0x1801033da  lea     rax, [rbp+var_28]
0x1801033de  mov     r9d, [rbp+arg_20]
0x1801033e2  mov     r8d, r12d
0x1801033e5  mov     rdx, [rbp+arg_8]
0x1801033e9  mov     rcx, rdi
0x1801033ec  mov     [rsp+70h+var_38], rax
0x1801033f1  lea     rax, [rbp+var_10]
0x1801033f5  mov     [rsp+70h+var_40], rax
0x1801033fa  mov     rax, [rbp+Source]
0x1801033fe  mov     [rsp+70h+var_48], rax
0x180103403  mov     [rsp+70h+var_50], rbx
0x180103408  mov     [rbp+var_10], r13
0x18010340c  mov     dword ptr [rbp+var_28], r13d
0x180103410  call    ?_GetGroupEntry@CVersionManagerServer@@AEAAJPEBGW4tagENTRY_TYPE@@HPEBUBLOCKLIST_ENTRY@@PEAUEXT_FILEINFO@@PEAPEBUGROUP_ENTRY@@PEAH@Z; CVersionManagerServer::_GetGroupEntry(ushort const *,tagENTRY_TYPE,int,BLOCKLIST_ENTRY const *,EXT_FILEINFO *,GROUP_ENTRY const * *,int *)
0x180103415  xor     r9d, r9d
0x180103418  mov     esi, eax
0x18010341a  test    eax, eax
0x18010341c  js      loc_180103782
0x180103422  cmp     dword ptr [rbp+var_28], r9d
0x180103426  jz      loc_180103782
0x18010342c  mov     rbx, [rbp+var_10]
0x180103430  test    rbx, rbx
0x180103433  jz      loc_180103782
0x180103439  cmp     [rbx+12h], r9b
0x18010343d  jz      loc_18010362E
0x180103443  mov     rax, [rbp+arg_48]
0x18010344a  lea     r14d, [r9+3]
0x18010344e  mov     dword ptr [r15], 1
0x180103455  mov     [rax], r9d
0x180103458  mov     r12, r9
0x18010345b  mov     rbx, [rbp+arg_40]
0x180103462  lea     rcx, [rdi+788h]; lpCriticalSection
0x180103469  call    cs:__imp_LeaveCriticalSection
0x180103470  nop     dword ptr [rax+rax+00h]
0x180103475  test    esi, esi
0x180103477  js      loc_1801037FB
0x18010347d  cmp     [rbp+Source], 0
0x180103482  jz      loc_180103825
0x180103488  mov     r15, [rbp+arg_30]
0x18010348c  test    r15, r15
0x18010348f  jz      short loc_1801034C8
0x180103491  mov     rcx, [rbp+arg_28]
0x180103495  test    rcx, rcx
0x180103498  jz      short loc_1801034C8
0x18010349a  cmp     [rbp+var_2C], 0FFFFFFFFh
0x18010349e  jnz     short loc_1801034C8
0x1801034a0  mov     rax, [rcx]
0x1801034a3  lea     r8, [rbp+var_2C]
0x1801034a7  mov     [rsp+70h+var_48], 0
0x1801034b0  xor     r9d, r9d
0x1801034b3  mov     rdx, r15
0x1801034b6  mov     [rsp+70h+var_50], 0
0x1801034bf  mov     rax, [rax+60h]
0x1801034c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801034c8  mov     ecx, 0A78h; Size
0x1801034cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801034d2  mov     rbx, rax
0x1801034d5  xor     eax, eax
0x1801034d7  test    rbx, rbx
0x1801034da  jz      loc_1801037E9
0x1801034e0  lea     rcx, [rbx+650h]; void *
0x1801034e7  mov     [rbx], rax
0x1801034ea  xor     edx, edx; Val
0x1801034ec  mov     [rbx+8], eax
0x1801034ef  mov     r8d, 208h; Size
0x1801034f5  mov     dword ptr [rbx+0A60h], 0FFFFFFFFh
0x1801034ff  mov     [rbx+0A64h], rax
0x180103506  mov     [rbx+0A6Ch], eax
0x18010350c  mov     [rbx+0A70h], rax
0x180103513  call    memset_0
0x180103518  lea     rcx, [rbx+858h]; void *
0x18010351f  xor     edx, edx; Val
0x180103521  mov     r8d, 208h; Size
0x180103527  call    memset_0
0x18010352c  test    r15, r15
0x18010352f  jz      short loc_180103543
0x180103531  mov     rax, [r15]
0x180103534  mov     rdx, rbx
0x180103537  mov     rcx, r15
0x18010353a  mov     rax, [rax+38h]
0x18010353e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103543  mov     eax, [rbp+arg_18]
0x180103546  lea     rcx, [rbx+10h]; Destination
0x18010354a  mov     edx, 640h; DestinationSize
0x18010354f  mov     [rbx+8], eax
0x180103552  mov     r8, [rbp+Source]; Source
0x180103556  mov     r9d, edx; SourceSize
0x180103559  call    cs:__imp_memcpy_s
0x180103560  nop     dword ptr [rax+rax+00h]
0x180103565  test    eax, eax
0x180103567  jnz     loc_1801037EC
0x18010356d  lea     rcx, [rbx+440h]; pszPath
0x180103574  call    cs:__imp_PathFindFileNameW
0x18010357b  nop     dword ptr [rax+rax+00h]
0x180103580  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180103584  lea     rcx, [rbx+650h]; unsigned __int16 *
0x18010358b  mov     r10d, 104h
0x180103591  mov     [rbx+28h], rax
0x180103595  mov     edx, r10d; unsigned __int64
0x180103598  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010359d  test    eax, eax
0x18010359f  js      loc_1801037EC
0x1801035a5  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x1801035a9  lea     rcx, [rbx+858h]; unsigned __int16 *
0x1801035b0  mov     edx, r10d; unsigned __int64
0x1801035b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801035b8  test    eax, eax
0x1801035ba  js      loc_1801037EC
0x1801035c0  mov     eax, [rbp+var_2C]
0x1801035c3  lea     r15, [rdi+6F8h]
0x1801035ca  mov     [rbx+0A60h], eax
0x1801035d0  mov     rcx, r15; lpCriticalSection
0x1801035d3  mov     rax, [rbp+arg_48]
0x1801035da  mov     [rbx+0A64h], r14d
0x1801035e1  mov     eax, [rax]
0x1801035e3  mov     [rbx+0A68h], eax
0x1801035e9  mov     eax, [rbp+arg_20]
0x1801035ec  mov     [rbx+0A6Ch], eax
0x1801035f2  call    cs:__imp_EnterCriticalSection
0x1801035f9  nop     dword ptr [rax+rax+00h]
0x1801035fe  mov     eax, [rdi+730h]
0x180103604  mov     r14d, 80004005h
0x18010360a  cmp     eax, 20h ; ' '
0x18010360d  jge     loc_1801037C0
0x180103613  lea     rcx, [rdi+728h]
0x18010361a  test    eax, eax
0x18010361c  jnz     loc_18010379F
0x180103622  mov     [rdi+720h], rbx
0x180103629  jmp     loc_1801037A9
0x18010362e  cmp     [rbx+11h], r9b
0x180103632  jnz     loc_180103782
0x180103638  cmp     [rbx+10h], r9b
0x18010363c  jnz     loc_180103778
0x180103642  cmp     [rdi+1Ah], r9b
0x180103646  jz      loc_180103458
0x18010364c  mov     r8, [rbp+arg_30]; struct IUri *
0x180103650  mov     eax, r9d
0x180103653  mov     dword ptr [rbp+var_28], eax
0x180103656  test    r8, r8
0x180103659  jz      short loc_180103696
0x18010365b  mov     rdx, [rbp+arg_28]; struct IInternetSecurityManagerEx2 *
0x18010365f  test    rdx, rdx
0x180103662  jz      short loc_180103696
0x180103664  lea     rax, [rbp+var_2C]
0x180103668  mov     rcx, rdi; this
0x18010366b  mov     [rsp+70h+var_48], rax; enum tagURLZONE *
0x180103670  lea     r9, [rbp+var_30]; enum EXT_SQM_VERSION_REASON *
0x180103674  lea     rax, [rbp+var_28]
0x180103678  mov     [rsp+70h+var_50], rax; int *
0x18010367d  call    ?_IsUriExcludedFromVersionCheckNotThreadSafe@CVersionManagerServer@@AEAAJPEAUIInternetSecurityManagerEx2@@PEAUIUri@@PEAW4EXT_SQM_VERSION_REASON@@PEAHPEAW4tagURLZONE@@@Z; CVersionManagerServer::_IsUriExcludedFromVersionCheckNotThreadSafe(IInternetSecurityManagerEx2 *,IUri *,EXT_SQM_VERSION_REASON *,int *,tagURLZONE *)
0x180103682  xor     r9d, r9d
0x180103685  mov     esi, eax
0x180103687  test    eax, eax
0x180103689  js      loc_18010376C
0x18010368f  mov     r14d, [rbp+var_30]
0x180103693  mov     eax, dword ptr [rbp+var_28]
0x180103696  test    eax, eax
0x180103698  jnz     loc_180103770
0x18010369e  mov     rdx, [rbp+arg_8]
0x1801036a2  lea     rax, [rbp+var_28]
0x1801036a6  mov     dword ptr [rbp+var_28], r9d
0x1801036aa  lea     r8, [rbp+var_30]
0x1801036ae  mov     r9d, r12d
0x1801036b1  mov     [rsp+70h+var_50], rax
0x1801036b6  call    ?_IsEntryExcludedFromVersionCheck@CVersionManagerServer@@AEAAJPEBGPEAW4EXT_SQM_VERSION_REASON@@W4tagENTRY_TYPE@@PEAH@Z; CVersionManagerServer::_IsEntryExcludedFromVersionCheck(ushort const *,EXT_SQM_VERSION_REASON *,tagENTRY_TYPE,int *)
0x1801036bb  xor     r9d, r9d
0x1801036be  mov     esi, eax
0x1801036c0  test    eax, eax
0x1801036c2  js      loc_18010376C
0x1801036c8  cmp     dword ptr [rbp+var_28], r9d
0x1801036cc  jnz     loc_18010376C
0x1801036d2  cmp     [rbx+13h], r9b
0x1801036d6  lea     r14d, [r9+6]
0x1801036da  mov     eax, r9d
0x1801036dd  setnz   al
0x1801036e0  mov     [r15], eax
0x1801036e3  mov     rax, [rbp+arg_48]
0x1801036ea  mov     [rax], r9d
0x1801036ed  cmp     [r15], r9d
0x1801036f0  jnz     short loc_180103722
0x1801036f2  mov     rcx, [rbx+8]; psz
0x1801036f6  test    rcx, rcx
0x1801036f9  jz      short loc_180103722
  ... truncated ...
```
