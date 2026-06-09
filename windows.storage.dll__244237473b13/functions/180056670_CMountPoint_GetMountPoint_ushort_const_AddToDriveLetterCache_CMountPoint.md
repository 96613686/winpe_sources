# CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)

- ea: `0x180056670`
- end: `0x180056de7`
- name: `?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z`
- size: `1911`
- prototype: ``
- caller_count: `16`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800130b0`
- `0x180041f50`
- `0x1800a2f64`
- `0x18024a294`
- `0x180289de0`
- `0x1802bc91c`
- `0x1802edc30`
- `0x1802f99e8`
- `0x180301cb4`
- `0x18032c640`
- `0x18033d9c4`
- `0x180369798`
- `0x180371f84`
- `0x1805d9fa0`
- `0x1805ec764`
- `0x1806216e0`

## callees

- `0x18003ad20`
- `0x18004e06c`
- `0x1800551d0`
- `0x1800559e0`
- `0x180056580`
- `0x180056670`
- `0x180056df0`
- `0x180159c78`
- `0x1802d7a50`
- `0x180363e2c`
- `0x1803b1f60`
- `0x1803b2ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005671f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005671f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800568cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800568cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056a74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056c1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056a74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056c1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056b20`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056b20`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180056d51`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180056d51`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005670c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005670c`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18005693e`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18005693e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800569c0`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180056be5`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800569c0`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180056be5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800566d8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800566d8`

## pseudocode

```c
__int64 __fastcall CMountPoint::GetMountPoint(unsigned __int64 a1, int a2, struct CMtPtLocal *a3)
{
  int v3; // ebx
  struct CMtPtLocal *v4; // rsi
  volatile signed __int32 *v6; // rdi
  int v7; // r14d
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  WCHAR v10; // dx
  WCHAR v11; // ax
  int Error; // r15d
  int v13; // r13d
  __int64 v14; // rbx
  WCHAR *v15; // r14
  WCHAR *v16; // r8
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  struct CMtPtLocal *v19; // rdi
  __int64 v20; // r8
  unsigned int v21; // ebx
  int v23; // edx
  _WORD *v24; // rax
  unsigned __int64 i; // rcx
  WCHAR *v26; // r8
  unsigned __int64 v27; // rsi
  unsigned __int64 v28; // rdi
  __int64 v29; // rcx
  _WORD *v30; // rdx
  __int64 v31; // r8
  _WORD *v32; // rcx
  int v33; // edx
  _WORD *v34; // rax
  unsigned __int64 j; // rcx
  __int64 v36; // rcx
  WCHAR *p_pszPath; // rdx
  __int64 v38; // r8
  WCHAR *v39; // rcx
  volatile signed __int32 *v40; // [rsp+38h] [rbp-D0h]
  int DriveNumberW; // [rsp+44h] [rbp-C4h]
  WCHAR sz[4]; // [rsp+48h] [rbp-C0h] BYREF
  struct CMountPoint *v44; // [rsp+50h] [rbp-B8h] BYREF
  struct CMtPtLocal *v45[2]; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR pszPath; // [rsp+78h] [rbp-90h] BYREF
  char v47[526]; // [rsp+7Ah] [rbp-8Eh] BYREF
  WCHAR v48[264]; // [rsp+288h] [rbp+180h] BYREF
  WCHAR v49[264]; // [rsp+498h] [rbp+390h] BYREF

  v3 = a2;
  v4 = a3;
  v45[0] = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Start,
      a3,
      1,
      &v44);
  v6 = 0;
  *(_QWORD *)v4 = 0;
  v40 = 0;
  v44 = 0;
  DriveNumberW = PathGetDriveNumberW((LPCWSTR)a1);
  v7 = DriveNumberW;
  if ( DriveNumberW != -1 )
  {
    InitOnceExecuteOnce(&InitOnce, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &Parameter, 0);
    EnterCriticalSection(&Parameter);
    if ( HIDWORD(qword_180828300) )
      goto LABEL_34;
    if ( !a1 )
      goto LABEL_13;
    v8 = *(_WORD *)a1;
    v9 = (WCHAR *)a1;
    if ( *(_WORD *)a1 == 92 )
    {
      if ( *(_WORD *)(a1 + 2) != 92 || *(_WORD *)(a1 + 4) != 63 || *(_WORD *)(a1 + 6) != 92 )
        goto LABEL_8;
      v8 = *(_WORD *)(a1 + 8);
      v9 = (WCHAR *)(a1 + 8);
    }
    if ( v8 >= 0x61u )
    {
      v10 = *v9;
      if ( *v9 <= 0x7Au )
        goto LABEL_9;
    }
LABEL_8:
    v10 = *v9;
    if ( (unsigned __int16)(*v9 - 65) <= 0x19u )
    {
LABEL_9:
      if ( v9[1] == 58 )
      {
        v11 = v9[2];
        if ( !v11 || v11 == 92 && !v9[3] )
        {
          sz[0] = v10;
          CharLowerBuffW(sz, 1u);
          if ( sz[0] )
            goto LABEL_115;
        }
      }
    }
LABEL_13:
    if ( (unsigned int)CMountPoint::_IsNetDriveLazyLoadNetDLLs(DriveNumberW) )
    {
LABEL_115:
      CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, &v44);
      v19 = v44;
      goto LABEL_35;
    }
    memset_0(v47, 0, 0x206u);
    Error = 1;
    pszPath = 0;
    if ( qword_1808282E8 )
    {
      v13 = 0;
      *(_DWORD *)sz = *(_DWORD *)qword_1808282E8;
      if ( *(int *)sz > 0 )
      {
        while ( 1 )
        {
          if ( v6 )
          {
LABEL_32:
            v3 = a2;
            v4 = v45[0];
            v7 = DriveNumberW;
            if ( pszPath )
              goto LABEL_33;
            break;
          }
          if ( qword_1808282E8 && v13 >= 0 && v13 < *(_DWORD *)qword_1808282E8 )
            v14 = *(_QWORD *)(*(_QWORD *)(qword_1808282E8 + 8) + 8LL * v13);
          else
            v14 = 0;
          v15 = (WCHAR *)(v14 + 520);
          if ( (unsigned __int64)(v14 + 520) < 0x10000 )
          {
            if ( SHGetFolderPathW(0, (unsigned int)v15 | 0x4000, 0, 0, v48) < 0 )
              goto LABEL_31;
            v16 = v48;
          }
          else
          {
            v16 = (WCHAR *)(v14 + 520);
          }
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          if ( v17 && v16[v17 - 1] == 92 )
            --v17;
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(a1 + 2 * v18) );
          if ( v18 && *(_WORD *)(a1 + 2 * v18 - 2) == 92 )
            --v18;
          if ( v17 <= v18 )
          {
            if ( *(_WORD *)(a1 + 2 * v17) == 92 )
            {
              v23 = v17;
            }
            else
            {
              if ( v18 != v17 )
                goto LABEL_30;
              v23 = v18;
            }
            if ( CompareStringOrdinal((LPCWCH)a1, v23, v16, v17, 1) == 2 )
            {
              if ( v17 < v18 )
              {
                v24 = (_WORD *)(a1 + 2 + 2 * v17);
                for ( i = a1 + 2 * v18; (unsigned __int64)v24 < i; ++v24 )
                {
                  if ( *v24 == 92 )
                    break;
                }
              }
              if ( a1 < 0x10000 )
              {
                if ( SHGetFolderPathW(0, a1 | 0x4000, 0, 0, v49) >= 0 )
                {
                  v26 = v49;
                  goto LABEL_65;
                }
              }
              else
              {
                v26 = (WCHAR *)a1;
LABEL_65:
                v27 = -1;
                do
                  ++v27;
                while ( v26[v27] );
                if ( v27 && v26[v27 - 1] == 92 )
                  --v27;
                v28 = -1;
                do
                  ++v28;
                while ( *(_WORD *)(v14 + 2 * v28) );
                if ( v28 && *(_WORD *)(v14 + 2 * v28 - 2) == 92 )
                  --v28;
                if ( v27 <= v28 )
                {
                  if ( *(_WORD *)(v14 + 2 * v27) == 92 )
                  {
                    v33 = v27;
                  }
                  else
                  {
                    if ( v28 != v27 )
                      goto LABEL_72;
                    v33 = v28;
                  }
                  if ( CompareStringOrdinal((LPCWCH)v14, v33, v26, v27, 1) == 2 )
                  {
                    if ( v27 < v28 )
                    {
                      v34 = (_WORD *)(v14 + 2 * (v27 + 1));
                      for ( j = v14 + 2 * v28; (unsigned __int64)v34 < j; ++v34 )
                      {
                        if ( *v34 == 92 )
                          break;
                      }
                    }
                    v6 = *(volatile signed __int32 **)(v14 + 1040);
                    v40 = v6;
                    v44 = (struct CMountPoint *)v6;
                    _InterlockedIncrement(v6 + 12);
                    v36 = 2147483646;
                    p_pszPath = &pszPath;
                    v38 = 260;
                    do
                    {
                      if ( !v36 )
                        break;
                      if ( !*v15 )
                        break;
                      *p_pszPath++ = *v15++;
                      --v36;
                      --v38;
                    }
                    while ( v38 );
                    v39 = p_pszPath - 1;
                    if ( v38 )
                      v39 = p_pszPath;
                    *v39 = 0;
                    ++*(_DWORD *)(v14 + 1048);
                    Error = 0;
                    goto LABEL_31;
                  }
                }
              }
LABEL_72:
              if ( (pszPath || GetVolumePathNameW((LPCWSTR)a1, &pszPath, 0x104u) || (int)ResultFromKnownLastError() >= 0)
                && !StrCmpIW(&pszPath, (PCWSTR)(v14 + 520)) )
              {
                v6 = *(volatile signed __int32 **)(v14 + 1040);
                v40 = v6;
                v44 = (struct CMountPoint *)v6;
                _InterlockedIncrement(v6 + 12);
                if ( a2 == 1 )
                {
                  v29 = 2147483646;
                  v30 = (_WORD *)a1;
                  v31 = 260;
                  do
                  {
                    if ( !v29 )
                      break;
                    if ( !*v30 )
                      break;
                    *(_WORD *)v14 = *v30++;
                    v14 += 2;
                    --v29;
                    --v31;
                  }
                  while ( v31 );
                  v32 = (_WORD *)(v14 - 2);
                  if ( v31 )
                    v32 = (_WORD *)v14;
                  *v32 = 0;
                }
                Error = 0;
                goto LABEL_31;
              }
            }
          }
LABEL_30:
          v6 = v40;
LABEL_31:
          if ( ++v13 >= *(int *)sz )
            goto LABEL_32;
        }
      }
    }
    if ( !GetVolumePathNameW((LPCWSTR)a1, &pszPath, 0x104u) )
      Error = ResultFromKnownLastError();
LABEL_33:
    if ( Error >= 0 && !v6 )
    {
      PathCchAddBackslash(&pszPath, 0x104u);
      if ( CMountPoint::_ExtractDriveLetter(&pszPath) )
      {
        CMountPoint::_GetMountPointForDriveLetter(v7, &v44);
        v19 = v44;
      }
      else
      {
        v45[0] = 0;
        CMountPoint::_GetMountPointForFolder(&pszPath, v45);
        v19 = v45[0];
      }
      if ( v19 && v3 == 1 )
        CDriveLetterCache::AddPathLookupEntry(
          (CDriveLetterCache *)&qword_180827FA8,
          (const unsigned __int16 *)a1,
          &pszPath,
          v19);
      goto LABEL_35;
    }
LABEL_34:
    v19 = (struct CMtPtLocal *)v40;
LABEL_35:
    LeaveCriticalSection(&Parameter);
    goto LABEL_36;
  }
  CMountPoint::GetSimulatedMountPointFromVolumeGuid((STRSAFE_PCNZWCH)a1, &v44);
  v19 = v44;
LABEL_36:
  v21 = -2147467259;
  if ( v19 )
  {
    *(_QWORD *)v4 = v19;
    v21 = 0;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Stop,
      v20,
      1,
      v45);
  return v21;
}

```

## disassembly

```asm
0x180056670  mov     r11, rsp
0x180056673  push    rbp
0x180056674  push    rbx
0x180056675  lea     rbp, [r11-5E8h]
0x18005667c  sub     rsp, 6D8h
0x180056683  mov     rax, cs:__security_cookie
0x18005668a  xor     rax, rsp
0x18005668d  mov     [rbp+5E0h+var_40], rax
0x180056694  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18005669b  mov     ebx, edx
0x18005669d  mov     [r11+10h], rsi
0x1800566a1  mov     rsi, r8
0x1800566a4  mov     [r11-18h], rdi
0x1800566a8  mov     [r11-20h], r12
0x1800566ac  mov     r12, rcx
0x1800566af  mov     [r11-30h], r14
0x1800566b3  mov     [rsp+6E0h+var_688], r8
0x1800566b8  mov     [rsp+6E0h+var_6A8], edx
0x1800566bc  jnz     loc_180056A3B
0x1800566c2  xor     edi, edi
0x1800566c4  mov     qword ptr [rsi], 0
0x1800566cb  mov     rcx, r12; pszPath
0x1800566ce  mov     qword ptr [rsp+6E0h+var_6B0], rdi
0x1800566d3  mov     [rsp+6E0h+var_698], rdi
0x1800566d8  call    cs:__imp_PathGetDriveNumberW
0x1800566df  nop     dword ptr [rax+rax+00h]
0x1800566e4  mov     [rsp+3Ch], eax
0x1800566e8  mov     r14d, eax
0x1800566eb  cmp     eax, 0FFFFFFFFh
0x1800566ee  jz      loc_180056CF7
0x1800566f4  xor     r9d, r9d; Context
0x1800566f7  lea     r8, Parameter; Parameter
0x1800566fe  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180056705  lea     rcx, InitOnce; InitOnce
0x18005670c  call    cs:__imp_InitOnceExecuteOnce
0x180056713  nop     dword ptr [rax+rax+00h]
0x180056718  lea     rcx, Parameter; lpCriticalSection
0x18005671f  call    cs:__imp_EnterCriticalSection
0x180056726  nop     dword ptr [rax+rax+00h]
0x18005672b  cmp     dword ptr cs:qword_180828300+4, edi
0x180056731  jnz     loc_1800568BF
0x180056737  test    r12, r12
0x18005673a  jz      short loc_180056788
0x18005673c  movzx   eax, word ptr [r12]
0x180056741  mov     rcx, r12
0x180056744  cmp     ax, 5Ch ; '\'
0x180056748  jz      loc_180056CC0
0x18005674e  cmp     ax, 61h ; 'a'
0x180056752  jnb     loc_180056D30
0x180056758  movzx   edx, word ptr [rcx]
0x18005675b  lea     eax, [rdx-41h]
0x18005675e  cmp     ax, 19h
0x180056762  ja      short loc_180056788
0x180056764  cmp     word ptr [rcx+2], 3Ah ; ':'
0x180056769  jnz     short loc_180056788
0x18005676b  movzx   eax, word ptr [rcx+4]
0x18005676f  test    ax, ax
0x180056772  jz      loc_180056D42
0x180056778  cmp     ax, 5Ch ; '\'
0x18005677c  jnz     short loc_180056788
0x18005677e  cmp     [rcx+6], di
0x180056782  jz      loc_180056D42
0x180056788  mov     ecx, r14d; int
0x18005678b  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x180056790  test    eax, eax
0x180056792  jnz     loc_180056D68
0x180056798  mov     [rsp+6E0h+var_30], r15
0x1800567a0  lea     rcx, [rsp+6E0h+var_66E]; void *
0x1800567a5  xor     edx, edx; Val
0x1800567a7  mov     [rsp+6E0h+var_20], r13
0x1800567af  mov     r8d, 206h; Size
0x1800567b5  call    memset_0
0x1800567ba  xor     eax, eax
0x1800567bc  mov     r15d, 1
0x1800567c2  mov     [rsp+6E0h+pszPath], ax
0x1800567c7  mov     rax, cs:qword_1808282E8
0x1800567ce  test    rax, rax
0x1800567d1  jz      loc_1800569B2
0x1800567d7  mov     eax, [rax]
0x1800567d9  xor     r13d, r13d
0x1800567dc  mov     dword ptr [rsp+6E0h+sz], eax
0x1800567e0  test    eax, eax
0x1800567e2  jle     loc_1800569B2
0x1800567e8  nop     dword ptr [rax+rax+00000000h]
0x1800567f0  test    rdi, rdi
0x1800567f3  jnz     loc_180056890
0x1800567f9  mov     rax, cs:qword_1808282E8
0x180056800  test    rax, rax
0x180056803  jz      loc_1800569F6
0x180056809  test    r13d, r13d
0x18005680c  js      loc_1800569F6
0x180056812  cmp     r13d, [rax]
0x180056815  jge     loc_1800569F6
0x18005681b  mov     rax, [rax+8]
0x18005681f  movsxd  rcx, r13d
0x180056822  mov     rbx, [rax+rcx*8]
0x180056826  lea     r14, [rbx+208h]
0x18005682d  cmp     r14, 10000h
0x180056834  jb      loc_180056D7F
0x18005683a  mov     r8, r14; lpString2
0x18005683d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180056844  inc     rsi
0x180056847  cmp     word ptr [r8+rsi*2], 0
0x18005684d  jnz     short loc_180056844
0x18005684f  test    rsi, rsi
0x180056852  jnz     loc_1800569E1
0x180056858  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18005685f  nop
0x180056860  inc     rdi
0x180056863  cmp     word ptr [r12+rdi*2], 0
0x180056869  jnz     short loc_180056860
0x18005686b  test    rdi, rdi
0x18005686e  jnz     loc_18005699D
0x180056874  cmp     rsi, rdi
0x180056877  jbe     loc_1800569FD
0x18005687d  mov     rdi, qword ptr [rsp+6E0h+var_6B0]
0x180056882  inc     r13d
0x180056885  cmp     r13d, dword ptr [rsp+6E0h+sz]
0x18005688a  jl      loc_1800567F0
0x180056890  cmp     [rsp+6E0h+pszPath], 0
0x180056896  mov     ebx, [rsp+6E0h+var_6A8]
0x18005689a  mov     rsi, [rsp+6E0h+var_688]
0x18005689f  mov     r14d, [rsp+3Ch]
0x1800568a4  jz      loc_1800569B2
0x1800568aa  mov     r13, [rsp+6E0h+var_20]
0x1800568b2  test    r15d, r15d
0x1800568b5  mov     r15, [rsp+6E0h+var_30]
0x1800568bd  jns     short loc_18005692F
0x1800568bf  mov     rdi, qword ptr [rsp+6E0h+var_6B0]
0x1800568c4  lea     rcx, Parameter; lpCriticalSection
0x1800568cb  call    cs:__imp_LeaveCriticalSection
0x1800568d2  nop     dword ptr [rax+rax+00h]
0x1800568d7  mov     r14, [rsp+6E0h+var_28]
0x1800568df  mov     ebx, 80004005h
0x1800568e4  mov     r12, [rsp+6E0h+var_18]
0x1800568ec  test    rdi, rdi
0x1800568ef  jz      short loc_1800568F6
0x1800568f1  mov     [rsi], rdi
0x1800568f4  xor     ebx, ebx
0x1800568f6  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800568fd  mov     rdi, [rsp+6D0h]
0x180056905  mov     rsi, [rsp+6E0h+arg_8]
0x18005690d  jnz     loc_180056A13
0x180056913  mov     eax, ebx
0x180056915  mov     rcx, [rbp+5E0h+var_40]
0x18005691c  xor     rcx, rsp; StackCookie
0x18005691f  call    __security_check_cookie
0x180056924  add     rsp, 6D8h
0x18005692b  pop     rbx
0x18005692c  pop     rbp
0x18005692d  retn
0x18005692f  test    rdi, rdi
0x180056932  jnz     short loc_1800568BF
0x180056934  mov     edx, 104h; cchPath
0x180056939  lea     rcx, [rsp+6E0h+pszPath]; pszPath
0x18005693e  call    cs:__imp_PathCchAddBackslash
0x180056945  nop     dword ptr [rax+rax+00h]
0x18005694a  lea     rcx, [rsp+6E0h+pszPath]; unsigned __int16 *
0x18005694f  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x180056954  test    ax, ax
0x180056957  jz      loc_180056D0E
0x18005695d  lea     rdx, [rsp+6E0h+var_698]; struct CMountPoint **
0x180056962  mov     ecx, r14d; int
0x180056965  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x18005696a  mov     rdi, [rsp+6E0h+var_698]
0x18005696f  test    rdi, rdi
0x180056972  jz      loc_1800568C4
0x180056978  cmp     ebx, 1
0x18005697b  jnz     loc_1800568C4
0x180056981  mov     r9, rdi; struct CMountPoint *
0x180056984  lea     r8, [rsp+6E0h+pszPath]; unsigned __int16 *
0x180056989  mov     rdx, r12; unsigned __int16 *
0x18005698c  lea     rcx, qword_180827FA8; this
0x180056993  call    ?AddPathLookupEntry@CDriveLetterCache@@QEAAJPEBG0PEAVCMountPoint@@@Z; CDriveLetterCache::AddPathLookupEntry(ushort const *,ushort const *,CMountPoint *)
0x180056998  jmp     loc_1800568C4
0x18005699d  cmp     word ptr [r12+rdi*2-2], 5Ch ; '\'
0x1800569a4  jnz     loc_180056874
0x1800569aa  dec     rdi
0x1800569ad  jmp     loc_180056874
0x1800569b2  mov     r8d, 104h; cchBufferLength
0x1800569b8  lea     rdx, [rsp+6E0h+pszPath]; lpszVolumePathName
0x1800569bd  mov     rcx, r12; lpszFileName
0x1800569c0  call    cs:__imp_GetVolumePathNameW
0x1800569c7  nop     dword ptr [rax+rax+00h]
0x1800569cc  test    eax, eax
0x1800569ce  jnz     loc_1800568AA
0x1800569d4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800569d9  mov     r15d, eax
0x1800569dc  jmp     loc_1800568AA
0x1800569e1  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x1800569e8  jnz     loc_180056858
0x1800569ee  dec     rsi
0x1800569f1  jmp     loc_180056858
0x1800569f6  xor     ebx, ebx
0x1800569f8  jmp     loc_180056826
0x1800569fd  cmp     word ptr [r12+rsi*2], 5Ch ; '\'
0x180056a03  jz      short loc_180056A63
0x180056a05  cmp     rdi, rsi
0x180056a08  jnz     loc_18005687D
0x180056a0e  mov     rdx, rdi
0x180056a11  jmp     short loc_180056A66
0x180056a13  lea     rax, [rsp+6E0h+var_688]
0x180056a18  mov     r9d, 1
0x180056a1e  lea     rdx, Shell32_MountPoint_GetMountPoint_Stop
0x180056a25  mov     [rsp+20h], rax
0x180056a2a  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180056a31  call    McGenEventWrite_EventWriteTransfer
0x180056a36  jmp     loc_180056913
0x180056a3b  lea     rax, [rsp+6E0h+var_698]
0x180056a40  mov     r9d, 1
0x180056a46  lea     rdx, Shell32_MountPoint_GetMountPoint_Start
0x180056a4d  mov     [rsp+20h], rax
0x180056a52  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180056a59  call    McGenEventWrite_EventWriteTransfer
0x180056a5e  jmp     loc_1800566C2
0x180056a63  mov     rdx, rsi; cchCount1
0x180056a66  mov     r9d, esi; cchCount2
0x180056a69  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x180056a71  mov     rcx, r12; lpString1
0x180056a74  call    cs:__imp_CompareStringOrdinal
0x180056a7b  nop     dword ptr [rax+rax+00h]
0x180056a80  cmp     eax, 2
0x180056a83  jnz     loc_18005687D
0x180056a89  cmp     rsi, rdi
0x180056a8c  jnb     short loc_180056AAF
0x180056a8e  lea     rax, [r12+2]
0x180056a93  lea     rax, [rax+rsi*2]
0x180056a97  lea     rcx, [r12+rdi*2]
0x180056a9b  cmp     rax, rcx
0x180056a9e  jnb     short loc_180056AAF
0x180056aa0  cmp     word ptr [rax], 5Ch ; '\'
0x180056aa4  jz      short loc_180056AAF
0x180056aa6  add     rax, 2
0x180056aaa  cmp     rax, rcx
0x180056aad  jb      short loc_180056AA0
0x180056aaf  cmp     r12, 10000h
0x180056ab6  jb      loc_180056DB3
0x180056abc  mov     r8, r12; lpString2
0x180056abf  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180056ac6  nop     word ptr [rax+rax+00000000h]
0x180056ad0  inc     rsi
0x180056ad3  cmp     word ptr [r8+rsi*2], 0
0x180056ad9  jnz     short loc_180056AD0
0x180056adb  test    rsi, rsi
0x180056ade  jnz     loc_180056BAD
0x180056ae4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180056aeb  nop     dword ptr [rax+rax+00h]
0x180056af0  inc     rdi
0x180056af3  cmp     word ptr [rbx+rdi*2], 0
0x180056af8  jnz     short loc_180056AF0
0x180056afa  test    rdi, rdi
0x180056afd  jnz     loc_180056B99
0x180056b03  cmp     rsi, rdi
0x180056b06  jbe     loc_180056BC2
0x180056b0c  cmp     [rsp+6E0h+pszPath], 0
0x180056b12  jz      loc_180056BD7
0x180056b18  mov     rdx, r14; psz2
0x180056b1b  lea     rcx, [rsp+6E0h+pszPath]; psz1
0x180056b20  call    cs:__imp_StrCmpIW
0x180056b27  nop     dword ptr [rax+rax+00h]
0x180056b2c  test    eax, eax
0x180056b2e  jnz     loc_18005687D
0x180056b34  mov     rdi, [rbx+410h]
0x180056b3b  mov     qword ptr [rsp+6E0h+var_6B0], rdi
0x180056b40  mov     [rsp+6E0h+var_698], rdi
0x180056b45  lock inc dword ptr [rdi+30h]
0x180056b49  cmp     [rsp+6E0h+var_6A8], 1
0x180056b4e  jnz     short loc_180056B91
0x180056b50  mov     ecx, 7FFFFFFEh
0x180056b55  mov     rdx, r12
0x180056b58  mov     r8d, 104h
0x180056b5e  xchg    ax, ax
0x180056b60  test    rcx, rcx
0x180056b63  jz      short loc_180056B81
0x180056b65  movzx   eax, word ptr [rdx]
0x180056b68  test    ax, ax
0x180056b6b  jz      short loc_180056B81
0x180056b6d  mov     [rbx], ax
0x180056b70  add     rdx, 2
0x180056b74  add     rbx, 2
0x180056b78  dec     rcx
0x180056b7b  sub     r8, 1
0x180056b7f  jnz     short loc_180056B60
0x180056b81  test    r8, r8
0x180056b84  lea     rcx, [rbx-2]
0x180056b88  cmovnz  rcx, rbx
0x180056b8c  xor     eax, eax
0x180056b8e  mov     [rcx], ax
0x180056b91  xor     r15d, r15d
0x180056b94  jmp     loc_180056882
0x180056b99  cmp     word ptr [rbx+rdi*2-2], 5Ch ; '\'
0x180056b9f  jnz     loc_180056B03
0x180056ba5  dec     rdi
0x180056ba8  jmp     loc_180056B03
0x180056bad  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x180056bb4  jnz     loc_180056AE4
0x180056bba  dec     rsi
0x180056bbd  jmp     loc_180056AE4
0x180056bc2  cmp     word ptr [rbx+rsi*2], 5Ch ; '\'
0x180056bc7  jz      short loc_180056C0B
  ... truncated ...
```
