# DavAsyncQueryDirectory

- ea: `0x1800229b0`
- end: `0x180023357`
- name: `DavAsyncQueryDirectory`
- size: `2471`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000d9e4`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18000bc5c`
- `0x1800134d8`
- `0x1800229b0`
- `0x1800283fc`
- `0x180028440`
- `0x180028584`
- `0x180028680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002300b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002300b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023292`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022d74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022d74`
- `KERNEL32!LocalAlloc` at `0x180022ab4`
- `KERNEL32!LocalAlloc` at `0x180022b1e`
- `KERNEL32!LocalAlloc` at `0x180022cd7`
- `KERNEL32!LocalAlloc` at `0x180022e76`
- `KERNEL32!LocalAlloc` at `0x180022f6b`
- `KERNEL32!LocalAlloc` at `0x180022ff9`
- `KERNEL32!LocalAlloc` at `0x18002304a`
- `KERNEL32!LocalAlloc` at `0x180022ab4`
- `KERNEL32!LocalAlloc` at `0x180022b1e`
- `KERNEL32!LocalAlloc` at `0x180022cd7`
- `KERNEL32!LocalAlloc` at `0x180022e76`
- `KERNEL32!LocalAlloc` at `0x180022f6b`
- `KERNEL32!LocalAlloc` at `0x180022ff9`
- `KERNEL32!LocalAlloc` at `0x18002304a`
- `WINHTTP!WinHttpReadData` at `0x180022bee`
- `WINHTTP!WinHttpReadData` at `0x180022bee`

## pseudocode

```c
__int64 __fastcall DavAsyncQueryDirectory(__int64 a1, char a2)
{
  __int64 v2; // r9
  __int64 v4; // r12
  unsigned int v5; // ebx
  unsigned int v6; // eax
  void *v7; // rbx
  HLOCAL v8; // rax
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD *v12; // rdi
  DWORD *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // r14d
  __int64 v16; // r12
  void *v17; // r13
  __int64 v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  DWORD v21; // r12d
  unsigned int v22; // eax
  __int64 v23; // rbx
  _DWORD *v24; // rax
  _DWORD *v25; // r14
  DWORD v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rdx
  _QWORD *v31; // r12
  DWORD CurrentThreadId; // eax
  unsigned int v33; // r13d
  __int64 v34; // r13
  int v35; // r12d
  _QWORD *v36; // rcx
  int v37; // edx
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // r13
  DWORD v41; // eax
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  _QWORD *v44; // rbx
  _QWORD *v45; // rcx
  _QWORD *v46; // r12
  _WORD *v47; // rax
  __int64 v48; // rcx
  const wchar_t *v49; // r8
  __int64 v50; // rdx
  _WORD *v51; // rcx
  _QWORD *v52; // rax
  _QWORD *v53; // r13
  _WORD *v54; // rax
  _DWORD *v55; // r10
  const wchar_t *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  _WORD *v59; // rcx
  bool v60; // zf
  _QWORD *v61; // rdx
  _BYTE *v62; // rcx
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  __int64 v73; // rax
  _QWORD *v74; // rcx
  _QWORD *v75; // rcx
  int v76; // r8d
  _QWORD *v77; // rax
  DWORD v78; // eax
  __int64 v80; // [rsp+30h] [rbp-38h] BYREF
  __int64 v81; // [rsp+38h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-28h]
  HLOCAL v83; // [rsp+48h] [rbp-20h]
  void *v84; // [rsp+50h] [rbp-18h]
  int v85; // [rsp+B0h] [rbp+48h]
  unsigned int v86; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v87; // [rsp+C0h] [rbp+58h]
  __int64 v88; // [rsp+C8h] [rbp+60h]

  LOBYTE(v86) = a2;
  v2 = *(unsigned int *)(a1 + 52);
  v86 = 0;
  v88 = 0;
  hMem = 0;
  v4 = 0;
  v83 = 0;
  v85 = 1;
  if ( (_DWORD)v2 == 3 )
  {
    v6 = DavQueryAndParseResponseEx(*(_QWORD *)(a1 + 552), 0);
    if ( v6 )
    {
      if ( v6 != 2
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v6);
      }
      v5 = 2;
      goto LABEL_136;
    }
    *(_DWORD *)(a1 + 52) = 4;
  }
  else if ( (_DWORD)v2 != 4 )
  {
    v5 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v2);
    goto LABEL_136;
  }
  v7 = *(void **)(a1 + 552);
  v84 = v7;
  if ( !*(_QWORD *)(a1 + 520) )
  {
    v8 = LocalAlloc(0x40u, 0x1000u);
    if ( !v8 )
    {
      LastError = GetLastError();
      v5 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v11 = 27;
      goto LABEL_18;
    }
    *(_QWORD *)(a1 + 520) = v8;
  }
  v12 = *(DWORD **)(a1 + 528);
  if ( !v12 )
  {
    v13 = (DWORD *)LocalAlloc(0x40u, 4u);
    v12 = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      v5 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v11 = 28;
LABEL_18:
      WPP_SF_d(v10[2], v11, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, LastError);
      goto LABEL_52;
    }
    *(_QWORD *)(a1 + 528) = v13;
  }
  v14 = *(_QWORD *)(a1 + 536);
  v15 = 0;
  v16 = *(_QWORD *)(a1 + 544);
  v17 = *(void **)(a1 + 520);
  *(_DWORD *)(a1 + 52) = 4;
  v88 = v14;
  v80 = v14;
  v87 = v16;
  v81 = v16;
  while ( 1 )
  {
    v18 = *(unsigned int *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 56) == 1 )
    {
      *(_DWORD *)(a1 + 56) = 2;
      if ( WinHttpReadData(v7, v17, 0x1000u, v12) )
      {
        v15 += *v12;
        if ( *(_DWORD *)(a1 + 512) )
        {
          v18 = (unsigned int)(10 * *(_DWORD *)&DavFileAttributesLimitInBytes);
          if ( v15 <= (unsigned int)v18 )
            goto LABEL_39;
          v5 = 58;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_135;
          v20 = 31;
        }
        else
        {
          v18 = *(unsigned int *)&DavFileAttributesLimitInBytes;
          if ( v15 <= *(_DWORD *)&DavFileAttributesLimitInBytes )
            goto LABEL_39;
          v5 = 58;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_135;
          v20 = 32;
        }
      }
      else
      {
        v78 = GetLastError();
        v5 = v78;
        if ( v78 == 997 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
          return v5;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_135:
          v4 = v87;
          goto LABEL_136;
        }
        v20 = 29;
        v18 = v78;
      }
LABEL_134:
      WPP_SF_d(v19[2], v20, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v18);
      goto LABEL_135;
    }
    if ( *(_DWORD *)(a1 + 56) != 2 )
    {
      v5 = 87;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_135;
      v20 = 34;
      goto LABEL_134;
    }
LABEL_39:
    *(_DWORD *)(a1 + 56) = 1;
    v21 = *v12;
    v22 = DavPushData((_DWORD)v17, (unsigned int)&v80, (unsigned int)&v81, *v12, *v12 == 0);
    v5 = v22;
    if ( v22 )
      break;
    v88 = v80;
    if ( !*(_QWORD *)(a1 + 536) )
      *(_QWORD *)(a1 + 536) = v80;
    v23 = v81;
    v87 = v81;
    if ( !*(_QWORD *)(a1 + 544) )
      *(_QWORD *)(a1 + 544) = v81;
    if ( !v21 )
    {
      v24 = LocalAlloc(0x40u, 0xA0u);
      v25 = v24;
      if ( !v24 )
      {
        v26 = GetLastError();
        v5 = v26;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = 35;
          v29 = v26;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      v30 = v88;
      v31 = v24 + 16;
      *((_QWORD *)v24 + 9) = v24 + 16;
      *((_QWORD *)v24 + 8) = v24 + 16;
      v5 = DavParseData((__int64)v24, v30, v23, &v86);
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          CurrentThreadId = GetCurrentThreadId();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
            CurrentThreadId,
            v5);
        }
        DavFinalizeFileAttributesList(v25);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = 36;
          v29 = v5;
LABEL_50:
          WPP_SF_d(v27[2], v28, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v29);
        }
LABEL_51:
        v4 = v87;
        goto LABEL_52;
      }
      v5 = 0;
      v33 = v86;
      if ( *(_DWORD *)(a1 + 512) )
      {
        v34 = *(_QWORD *)(v88 + 56);
        if ( v34 && (_DWORD *)v34 != v25 )
        {
          v35 = v25[1];
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids,
              *(_QWORD *)(v88 + 56));
          *(_DWORD *)(v34 + 4) = v35;
          v36 = *(_QWORD **)(v34 + 64);
          v37 = v35 + 1;
          v25 = (_DWORD *)v34;
          if ( v36 == (_QWORD *)(v34 + 64) )
          {
            v5 = 0;
          }
          else
          {
            do
            {
              v38 = v36;
              v36 = (_QWORD *)*v36;
              *((_DWORD *)v38 - 15) = v37++;
            }
            while ( v36 != (_QWORD *)(v34 + 64) );
          }
        }
        v33 = v86;
LABEL_70:
        if ( *(_DWORD *)(a1 + 512) )
        {
          v39 = LocalAlloc(0x40u, 0xA0u);
          hMem = v39;
          v40 = v39;
          if ( !v39 )
          {
            v41 = GetLastError();
            v5 = v41;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v43 = 40;
              goto LABEL_75;
            }
LABEL_76:
            DavFinalizeFileAttributesList(v25);
            goto LABEL_51;
          }
          v46 = v39 + 8;
          v39[9] = v39 + 8;
          v39[8] = v39 + 8;
          v47 = LocalAlloc(0x40u, 4u);
          v40[12] = v47;
          if ( !v47 )
          {
            v41 = GetLastError();
            v5 = v41;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_76;
            v43 = 41;
            goto LABEL_75;
          }
          v48 = 2147483646;
          v49 = L".";
          v50 = 2;
          do
          {
            if ( !v48 )
              break;
            if ( !*v49 )
              break;
            *v47++ = *v49++;
            --v48;
            --v50;
          }
          while ( v50 );
          v51 = v47 - 1;
          if ( v50 )
            v51 = v47;
          *v51 = 0;
          *((_DWORD *)v40 + 22) = 1;
          v52 = LocalAlloc(0x40u, 0xA0u);
          v83 = v52;
          if ( !v52 )
          {
            v41 = GetLastError();
            v5 = v41;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_76;
            v43 = 42;
            goto LABEL_75;
          }
          v53 = v52 + 8;
          v52[9] = v52 + 8;
          v52[8] = v52 + 8;
          v54 = LocalAlloc(0x40u, 6u);
          v55 = v83;
          *((_QWORD *)v83 + 12) = v54;
          if ( !v54 )
          {
            v41 = GetLastError();
            v5 = v41;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_76;
            v43 = 43;
LABEL_75:
            WPP_SF_d(v42[2], v43, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v41);
            goto LABEL_76;
          }
          v56 = L"..";
          v57 = 3;
          v58 = 2147483646;
          do
          {
            if ( !v58 )
              break;
            if ( !*v56 )
              break;
            *v54++ = *v56++;
            --v58;
            --v57;
          }
          while ( v57 );
          v59 = v54 - 1;
          v60 = v57 == 0;
          v61 = v25 + 16;
          if ( !v60 )
            v59 = v54;
          *v59 = 0;
          v62 = hMem;
          v55[22] = 2;
          *((_BYTE *)v55 + 84) = 1;
          v62[84] = 1;
          v63 = v25[5];
          v55[5] = v63;
          *((_DWORD *)v62 + 5) = v63;
          v64 = v25[4];
          v55[4] = v64;
          *((_DWORD *)v62 + 4) = v64;
          v65 = v25[11];
          v55[11] = v65;
          *((_DWORD *)v62 + 11) = v65;
          v66 = v25[10];
          v55[10] = v66;
          *((_DWORD *)v62 + 10) = v66;
          v67 = v25[9];
          v55[9] = v67;
          *((_DWORD *)v62 + 9) = v67;
          v68 = v25[8];
          v55[8] = v68;
          *((_DWORD *)v62 + 8) = v68;
          v69 = v25[13];
          v55[13] = v69;
          *((_DWORD *)v62 + 13) = v69;
          v70 = v25[12];
          v55[12] = v70;
          *((_DWORD *)v62 + 12) = v70;
          v71 = v25[7];
          v55[7] = v71;
          *((_DWORD *)v62 + 7) = v71;
          v72 = v25[6];
          v55[6] = v72;
          *((_DWORD *)v62 + 6) = v72;
          v73 = *v61;
          v74 = *(_QWORD **)(*v61 + 8LL);
          if ( *v74 != *v61 || (*v46 = v73, v46[1] = v74, *v74 = v46, *(_QWORD *)(v73 + 8) = v46, *v46 != v73) )
            __fastfail(3u);
          *v53 = v73;
          v53[1] = v46;
          *v46 = v53;
          *(_QWORD *)(v73 + 8) = v53;
          v75 = (_QWORD *)*v61;
          v33 = v86 + 2;
          v76 = v25[1];
          v85 = 0;
          while ( 1 )
          {
            ++v76;
            if ( v75 == v61 )
              break;
            v77 = v75;
            v75 = (_QWORD *)*v75;
            *((_DWORD *)v77 - 15) = v76;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids,
              v33,
              v76);
        }
        *(_QWORD *)(a1 + 2312) = v25;
        *(_DWORD *)(a1 + 2320) = v33;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v25);
      }
      else
      {
        if ( v86 == 1 )
          goto LABEL_70;
        v44 = v31;
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_85;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v86);
          v45 = WPP_GLOBAL_Control;
        }
        do
        {
          if ( v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 2) != 0 )
          {
            WPP_SF_S(v45[2], 39, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v44[4]);
            v45 = WPP_GLOBAL_Control;
          }
LABEL_85:
          v44 = (_QWORD *)*v44;
        }
        while ( v44 != v31 );
        DavFinalizeFileAttributesList(v25);
        v5 = 2;
      }
      goto LABEL_135;
    }
    v7 = v84;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v22);
  v4 = v81;
  v88 = v80;
LABEL_52:
  if ( v5 != 997 )
LABEL_136:
    DavCloseContext(v88, v4);
  if ( v85 == 1 )
  {
    if ( hMem )
      DavFinalizeFileAttributesList(hMem);
    if ( v83 )
      DavFinalizeFileAttributesList(v83);
  }
  return v5;
}

```

## disassembly

```asm
0x1800229b0  mov     byte ptr [rsp-40h+arg_8], dl
0x1800229b4  push    rbp
0x1800229b5  push    rbx
0x1800229b6  push    rsi
0x1800229b7  push    rdi
0x1800229b8  push    r12
0x1800229ba  push    r13
0x1800229bc  push    r14
0x1800229be  push    r15
0x1800229c0  mov     rbp, rsp
0x1800229c3  sub     rsp, 68h
0x1800229c7  mov     r9d, [rcx+34h]
0x1800229cb  xor     r13d, r13d
0x1800229ce  mov     rsi, rcx
0x1800229d1  mov     [rbp+arg_8], r13d
0x1800229d5  mov     ecx, r9d
0x1800229d8  mov     [rbp+arg_18], r13
0x1800229dc  mov     [rbp+hMem], r13
0x1800229e0  mov     r12d, r13d
0x1800229e3  mov     [rbp+var_20], r13
0x1800229e7  lea     r15d, [r13+4]
0x1800229eb  mov     [rbp+arg_0], 1
0x1800229f2  sub     ecx, 3
0x1800229f5  jz      short loc_180022A3D
0x1800229f7  cmp     ecx, 1
0x1800229fa  jz      loc_180022A96
0x180022a00  lea     ebx, [r13+57h]
0x180022a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a0b  lea     rdi, WPP_GLOBAL_Control
0x180022a12  cmp     rcx, rdi
0x180022a15  jz      loc_1800232D6
0x180022a1b  test    byte ptr [rcx+1Ch], 1
0x180022a1f  jz      loc_1800232D6
0x180022a25  mov     rcx, [rcx+10h]
0x180022a29  lea     edx, [rbx-29h]
0x180022a2c  lea     r8, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x180022a33  call    WPP_SF_d
0x180022a38  jmp     loc_1800232D6
0x180022a3d  mov     rcx, [rsi+228h]
0x180022a44  xor     edx, edx
0x180022a46  call    DavQueryAndParseResponseEx
0x180022a4b  test    eax, eax
0x180022a4d  jz      short loc_180022A92
0x180022a4f  mov     r15d, 2
0x180022a55  cmp     eax, r15d
0x180022a58  jz      short loc_180022A8A
0x180022a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a61  lea     rdi, WPP_GLOBAL_Control
0x180022a68  cmp     rcx, rdi
0x180022a6b  jz      short loc_180022A8A
0x180022a6d  test    byte ptr [rcx+1Ch], 1
0x180022a71  jz      short loc_180022A8A
0x180022a73  mov     rcx, [rcx+10h]
0x180022a77  lea     edx, [r15+18h]
0x180022a7b  mov     r9d, eax
0x180022a7e  lea     r8, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x180022a85  call    WPP_SF_d
0x180022a8a  mov     ebx, r15d
0x180022a8d  jmp     loc_1800232D6
0x180022a92  mov     [rsi+34h], r15d
0x180022a96  mov     rbx, [rsi+228h]
0x180022a9d  mov     [rbp+var_18], rbx
0x180022aa1  cmp     [rsi+208h], r13
0x180022aa8  jnz     short loc_180022B0C
0x180022aaa  mov     edx, 1000h; uBytes
0x180022aaf  mov     ecx, 40h ; '@'; uFlags
0x180022ab4  call    cs:__imp_LocalAlloc
0x180022aba  test    rax, rax
0x180022abd  jnz     short loc_180022B05
0x180022abf  call    cs:__imp_GetLastError
0x180022ac5  mov     ebx, eax
0x180022ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ace  lea     rdi, WPP_GLOBAL_Control
0x180022ad5  cmp     rcx, rdi
0x180022ad8  jz      loc_180022D24
0x180022ade  test    byte ptr [rcx+1Ch], 1
0x180022ae2  jz      loc_180022D24
0x180022ae8  mov     edx, 1Bh
0x180022aed  mov     rcx, [rcx+10h]
0x180022af1  lea     r8, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x180022af8  mov     r9d, eax
0x180022afb  call    WPP_SF_d
0x180022b00  jmp     loc_180022D24
0x180022b05  mov     [rsi+208h], rax
0x180022b0c  mov     rdi, [rsi+210h]
0x180022b13  test    rdi, rdi
0x180022b16  jnz     short loc_180022B63
0x180022b18  mov     rdx, r15; uBytes
0x180022b1b  lea     ecx, [rdi+40h]; uFlags
0x180022b1e  call    cs:__imp_LocalAlloc
0x180022b24  mov     rdi, rax
0x180022b27  test    rax, rax
0x180022b2a  jnz     short loc_180022B5C
0x180022b2c  call    cs:__imp_GetLastError
0x180022b32  mov     ebx, eax
0x180022b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b3b  lea     rdi, WPP_GLOBAL_Control
0x180022b42  cmp     rcx, rdi
0x180022b45  jz      loc_180022D24
0x180022b4b  test    byte ptr [rcx+1Ch], 1
0x180022b4f  jz      loc_180022D24
0x180022b55  mov     edx, 1Ch
0x180022b5a  jmp     short loc_180022AED
0x180022b5c  mov     [rsi+210h], rax
0x180022b63  mov     rdx, [rsi+218h]
0x180022b6a  mov     r14d, r13d
0x180022b6d  mov     r12, [rsi+220h]
0x180022b74  xor     r8d, r8d
0x180022b77  mov     r13, [rsi+208h]
0x180022b7e  mov     [rsi+34h], r15d
0x180022b82  mov     r15d, 2
0x180022b88  mov     [rbp+arg_18], rdx
0x180022b8c  mov     [rbp+var_38], rdx
0x180022b90  mov     [rbp+arg_10], r12
0x180022b94  mov     [rbp+var_30], r12
0x180022b98  mov     r9d, [rsi+38h]
0x180022b9c  mov     ecx, r9d
0x180022b9f  sub     ecx, 1
0x180022ba2  jz      short loc_180022BDB
0x180022ba4  cmp     ecx, 1
0x180022ba7  jz      loc_180022C5A
0x180022bad  mov     ebx, 57h ; 'W'
0x180022bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bb9  lea     rdi, WPP_GLOBAL_Control
0x180022bc0  cmp     rcx, rdi
0x180022bc3  jz      loc_1800232D2
0x180022bc9  test    byte ptr [rcx+1Ch], 1
0x180022bcd  jz      loc_1800232D2
0x180022bd3  lea     edx, [rbx-35h]
0x180022bd6  jmp     loc_1800232C2
0x180022bdb  mov     r9, rdi; lpdwNumberOfBytesRead
0x180022bde  mov     [rsi+38h], r15d
0x180022be2  mov     r8d, 1000h; dwNumberOfBytesToRead
0x180022be8  mov     rdx, r13; lpBuffer
0x180022beb  mov     rcx, rbx; hRequest
0x180022bee  call    cs:__imp_WinHttpReadData
0x180022bf4  xor     r8d, r8d
0x180022bf7  test    eax, eax
0x180022bf9  jz      loc_180023292
0x180022bff  add     r14d, [rdi]
0x180022c02  cmp     [rsi+200h], r8d
0x180022c09  jz      short loc_180022C4A
0x180022c0b  mov     eax, cs:DavFileAttributesLimitInBytes
0x180022c11  lea     r9d, [rax+rax*4]
0x180022c15  add     r9d, r9d
0x180022c18  cmp     r14d, r9d
0x180022c1b  jbe     short loc_180022C5A
0x180022c1d  lea     ebx, [r8+3Ah]
0x180022c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c28  lea     rdi, WPP_GLOBAL_Control
0x180022c2f  cmp     rcx, rdi
0x180022c32  jz      loc_1800232D2
0x180022c38  test    byte ptr [rcx+1Ch], 1
0x180022c3c  jz      loc_1800232D2
0x180022c42  lea     edx, [rbx-1Bh]
0x180022c45  jmp     loc_1800232C2
0x180022c4a  mov     r9d, cs:DavFileAttributesLimitInBytes
0x180022c51  cmp     r14d, r9d
0x180022c54  ja      loc_18002326F
0x180022c5a  mov     eax, r8d
0x180022c5d  mov     dword ptr [rsi+38h], 1
0x180022c64  mov     r12d, [rdi]
0x180022c67  lea     r8, [rbp+var_30]
0x180022c6b  test    r12d, r12d
0x180022c6e  lea     rdx, [rbp+var_38]
0x180022c72  mov     r9d, r12d
0x180022c75  mov     rcx, r13
0x180022c78  setz    al
0x180022c7b  mov     [rsp+68h+var_48], eax
0x180022c7f  call    DavPushData
0x180022c84  xor     r8d, r8d
0x180022c87  mov     ebx, eax
0x180022c89  test    eax, eax
0x180022c8b  jnz     loc_18002322D
0x180022c91  mov     rdx, [rbp+var_38]
0x180022c95  mov     [rbp+arg_18], rdx
0x180022c99  cmp     [rsi+218h], r8
0x180022ca0  jnz     short loc_180022CA9
0x180022ca2  mov     [rsi+218h], rdx
0x180022ca9  mov     rbx, [rbp+var_30]
0x180022cad  mov     [rbp+arg_10], rbx
0x180022cb1  cmp     [rsi+220h], r8
0x180022cb8  jnz     short loc_180022CC1
0x180022cba  mov     [rsi+220h], rbx
0x180022cc1  test    r12d, r12d
0x180022cc4  jz      short loc_180022CCF
0x180022cc6  mov     rbx, [rbp+var_18]
0x180022cca  jmp     loc_180022B98
0x180022ccf  mov     edx, 0A0h; uBytes
0x180022cd4  lea     ecx, [rdx-60h]; uFlags
0x180022cd7  call    cs:__imp_LocalAlloc
0x180022cdd  xor     r13d, r13d
0x180022ce0  mov     r14, rax
0x180022ce3  test    rax, rax
0x180022ce6  jnz     short loc_180022D35
0x180022ce8  call    cs:__imp_GetLastError
0x180022cee  mov     ebx, eax
0x180022cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cf7  lea     rdi, WPP_GLOBAL_Control
0x180022cfe  cmp     rcx, rdi
0x180022d01  jz      short loc_180022D20
0x180022d03  test    byte ptr [rcx+1Ch], 1
0x180022d07  jz      short loc_180022D20
0x180022d09  lea     edx, [r14+23h]
0x180022d0d  mov     r9d, eax
0x180022d10  mov     rcx, [rcx+10h]
0x180022d14  lea     r8, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x180022d1b  call    WPP_SF_d
0x180022d20  mov     r12, [rbp+arg_10]
0x180022d24  cmp     ebx, 3E5h
0x180022d2a  jz      loc_1800232E2
0x180022d30  jmp     loc_1800232D6
0x180022d35  mov     rdx, [rbp+arg_18]
0x180022d39  lea     r12, [rax+40h]
0x180022d3d  lea     r9, [rbp+arg_8]
0x180022d41  mov     [r12+8], r12
0x180022d46  mov     r8, rbx
0x180022d49  mov     [r12], r12
0x180022d4d  mov     rcx, r14
0x180022d50  call    DavParseData
0x180022d55  mov     ebx, eax
0x180022d57  test    eax, eax
0x180022d59  jz      short loc_180022DD1
0x180022d5b  mov     rax, cs:WPP_GLOBAL_Control
0x180022d62  lea     rdi, WPP_GLOBAL_Control
0x180022d69  cmp     rax, rdi
0x180022d6c  jz      short loc_180022D9D
0x180022d6e  test    byte ptr [rax+1Ch], 8
0x180022d72  jz      short loc_180022D9D
0x180022d74  call    cs:__imp_GetCurrentThreadId
0x180022d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d81  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180022d88  mov     edx, 2Fh ; '/'
0x180022d8d  mov     [rsp+68h+var_48], ebx
0x180022d91  mov     r9d, eax
0x180022d94  mov     rcx, [rcx+10h]
0x180022d98  call    WPP_SF_Dd
0x180022d9d  mov     edx, 1
0x180022da2  mov     rcx, r14; hMem
0x180022da5  call    DavFinalizeFileAttributesList
0x180022daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180022db1  cmp     rcx, rdi
0x180022db4  jz      loc_180022D20
0x180022dba  test    byte ptr [rcx+1Ch], 1
0x180022dbe  jz      loc_180022D20
0x180022dc4  mov     edx, 24h ; '$'
0x180022dc9  mov     r9d, ebx
0x180022dcc  jmp     loc_180022D10
0x180022dd1  xor     r11d, r11d
0x180022dd4  lea     rdi, WPP_GLOBAL_Control
0x180022ddb  mov     ebx, r13d
0x180022dde  mov     r13d, [rbp+arg_8]
0x180022de2  cmp     [rsi+200h], r11d
0x180022de9  jz      loc_180022ED4
0x180022def  mov     rax, [rbp+arg_18]
0x180022df3  mov     r13, [rax+38h]
0x180022df7  test    r13, r13
0x180022dfa  jz      short loc_180022E5D
0x180022dfc  cmp     r13, r14
0x180022dff  jz      short loc_180022E5D
0x180022e01  mov     r12d, [r14+4]
0x180022e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e0c  cmp     rcx, rdi
0x180022e0f  jz      short loc_180022E31
0x180022e11  test    [rcx+1Ch], r15b
0x180022e15  jz      short loc_180022E31
0x180022e17  mov     rcx, [rcx+10h]
0x180022e1b  lea     edx, [r11+25h]
0x180022e1f  mov     r9, r13
0x180022e22  lea     r8, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x180022e29  call    WPP_SF_q
0x180022e2e  xor     r11d, r11d
0x180022e31  lea     r8, [r13+40h]
0x180022e35  mov     [r13+4], r12d
0x180022e39  mov     rcx, [r8]
0x180022e3c  lea     edx, [r12+1]
0x180022e41  mov     r14, r13
0x180022e44  cmp     rcx, r8
0x180022e47  jz      loc_180022ECF
0x180022e4d  lea     rax, [rcx]
0x180022e50  mov     rcx, [rcx]
0x180022e53  mov     [rax-3Ch], edx
0x180022e56  inc     edx
0x180022e58  cmp     rcx, r8
0x180022e5b  jnz     short loc_180022E4D
0x180022e5d  mov     r13d, [rbp+arg_8]
0x180022e61  cmp     [rsi+200h], r11d
0x180022e68  jz      loc_1800231E1
0x180022e6e  mov     edx, 0A0h; uBytes
0x180022e73  lea     ecx, [rdx-60h]; uFlags
0x180022e76  call    cs:__imp_LocalAlloc
0x180022e7c  mov     [rbp+hMem], rax
0x180022e80  mov     r13, rax
0x180022e83  test    rax, rax
0x180022e86  jnz     loc_180022F56
0x180022e8c  call    cs:__imp_GetLastError
0x180022e92  mov     ebx, eax
0x180022e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e9b  cmp     rcx, rdi
0x180022e9e  jz      short loc_180022EBD
  ... truncated ...
```
