# NgscbCheckParseHSTIResults(uchar *,ulong,bool *,_NGSCB_HSTI_RESULTS * *,_NGSCB_HSTI_PARSING_STATUS *)

- ea: `0x180036f9c`
- end: `0x180037fb0`
- name: `?NgscbCheckParseHSTIResults@@YAJPEAEKPEA_NPEAPEAU_NGSCB_HSTI_RESULTS@@PEAU_NGSCB_HSTI_PARSING_STATUS@@@Z`
- size: `4116`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, bool *, struct _NGSCB_HSTI_RESULTS **, struct _NGSCB_HSTI_PARSING_STATUS *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800380a4`

## callees

- `0x1800210b4`
- `0x180021ec0`
- `0x1800229a4`
- `0x1800229f8`
- `0x180022a10`
- `0x180036dcc`
- `0x180036e24`
- `0x180036e64`
- `0x180036f9c`
- `0x180037fb8`
- `0x180038714`
- `0x180038868`
- `0x1800388a8`
- `0x180038900`
- `0x180038994`
- `0x1800389b8`
- `0x1800389e8`
- `0x180038a50`
- `0x180038af4`
- `0x180038b74`
- `0x180038c08`
- `0x180038c48`
- `0x180038d4c`
- `0x180038de0`
- `0x180038e84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037f80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037f72`

## string_xrefs

- `0x18003709b`: `ngscb_common_um`
- `0x180037259`: `ngscb_common_um`
- `0x180037312`: `ngscb_common_um`
- `0x180037481`: `ngscb_common_um`
- `0x18003751b`: `ngscb_common_um`
- `0x18003757f`: `ngscb_common_um`
- `0x1800375ec`: `ngscb_common_um`
- `0x180037673`: `ngscb_common_um`
- `0x18003795f`: `ngscb_common_um`
- `0x180037aa9`: `ngscb_common_um`
- `0x180037c2a`: `ngscb_common_um`
- `0x180037dae`: `ngscb_common_um`

## pseudocode

```c
__int64 __fastcall NgscbCheckParseHSTIResults(
        unsigned __int8 *a1,
        unsigned int a2,
        bool *a3,
        struct _NGSCB_HSTI_RESULTS **a4)
{
  unsigned int v4; // esi
  signed int v8; // ebx
  _BYTE *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // r11d
  unsigned int v14; // r14d
  unsigned int v15; // eax
  unsigned __int8 *v16; // rcx
  unsigned int *v17; // r14
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  int v25; // r14d
  unsigned int v26; // esi
  unsigned __int8 *v27; // rbx
  int v28; // r8d
  __int64 v29; // rax
  const EVENT_DESCRIPTOR *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  unsigned int v33; // r13d
  _BYTE *v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int v37; // r9d
  unsigned int v38; // edx
  unsigned int v39; // eax
  unsigned int v40; // esi
  unsigned int v41; // eax
  struct _NGSCB_HSTI_RESULTS *v42; // r14
  unsigned int v43; // r8d
  int v44; // edx
  unsigned int v45; // eax
  unsigned int v46; // ecx
  unsigned int v47; // r11d
  unsigned int v48; // r12d
  unsigned __int8 *v49; // rbx
  unsigned __int8 *v50; // r14
  __int64 v51; // rax
  unsigned int v52; // r15d
  char *v53; // rdx
  _BYTE *v54; // rcx
  __int64 v55; // rsi
  unsigned __int8 v56; // al
  __int64 v57; // r8
  __int64 v58; // rax
  char v59; // al
  _OWORD *v60; // rcx
  __int64 v61; // r9
  char *v62; // r10
  __int64 v63; // r8
  char *v64; // rax
  __int128 v65; // xmm1
  _BYTE *v66; // r12
  _BYTE *v67; // r15
  bool v68; // al
  __int64 v69; // rax
  __int64 v70; // r8
  unsigned int v71; // ecx
  __int64 v72; // rdx
  __int64 v73; // rax
  int v74; // r9d
  __int64 v75; // rax
  unsigned __int8 *v76; // r12
  unsigned int v77; // esi
  unsigned __int8 *v78; // r14
  unsigned int v79; // eax
  int v80; // edx
  int v81; // r8d
  __int64 v82; // rcx
  char *v83; // r8
  unsigned __int16 *v84; // r14
  __int64 v85; // rax
  void *v86; // rdi
  HANDLE ProcessHeap; // rax
  void *v88; // rdi
  HANDLE v89; // rax
  HANDLE v90; // rax
  char *v91; // rdi
  HANDLE v92; // rax
  unsigned __int16 *v93; // rdi
  HANDLE v94; // rax
  unsigned int Size; // [rsp+30h] [rbp-D0h] BYREF
  char Size_4; // [rsp+34h] [rbp-CCh]
  bool Size_5[3]; // [rsp+35h] [rbp-CBh] BYREF
  unsigned int *v99; // [rsp+38h] [rbp-C8h]
  char v100; // [rsp+40h] [rbp-C0h] BYREF
  bool v101; // [rsp+41h] [rbp-BFh] BYREF
  unsigned int v102; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v103; // [rsp+48h] [rbp-B8h]
  char v104; // [rsp+4Ch] [rbp-B4h] BYREF
  int v105; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v106; // [rsp+54h] [rbp-ACh] BYREF
  void *v107; // [rsp+58h] [rbp-A8h] BYREF
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v109; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  int v111; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v112; // [rsp+80h] [rbp-80h]
  char *v113; // [rsp+88h] [rbp-78h] BYREF
  bool *v114; // [rsp+90h] [rbp-70h]
  struct _NGSCB_HSTI_RESULTS **v115; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  bool *v117; // [rsp+B0h] [rbp-50h]
  __int64 v118; // [rsp+B8h] [rbp-48h]
  wchar_t *v119; // [rsp+C0h] [rbp-40h]
  __int64 v120; // [rsp+C8h] [rbp-38h]
  wchar_t *v121; // [rsp+D0h] [rbp-30h]
  int v122; // [rsp+D8h] [rbp-28h]
  int v123; // [rsp+DCh] [rbp-24h]
  _BYTE v124[512]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = 0;
  v103 = a2;
  v112 = a1;
  v115 = a4;
  v114 = a3;
  v105 = 0;
  Size = 0;
  lpMem = 0;
  v107 = 0;
  v99 = 0;
  Src = 0;
  Size_5[0] = 0;
  v113 = 0;
  v109 = 0;
  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x48u);
  v111 = 1;
  v100 = 1;
  v104 = 0;
  v101 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a3 )
  {
    v8 = -2147467261;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_221;
    v10 = 47;
    goto LABEL_7;
  }
  *a3 = 0;
  NgscbTryOpenEventLog();
  UserData.Ptr = (ULONGLONG)a1;
  v117 = (bool *)&v111;
  v11 = -1;
  *(_QWORD *)&UserData.Size = 4;
  v12 = -1;
  v118 = 4;
  v119 = aNgscbCommonUm;
  do
    ++v12;
  while ( aNgscbCommonUm[v12] );
  v120 = (unsigned int)(2 * v12 + 2);
  NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_DATA_VERSION, 3u, &UserData);
  if ( *(_DWORD *)a1 != 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        *(unsigned int *)a1);
      v9 = WPP_GLOBAL_Control;
    }
    v8 = -2147024883;
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (v9[28] & 0x40) == 0 )
      goto LABEL_221;
    v10 = 49;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, (unsigned int)v8);
    goto LABEL_221;
  }
  v13 = Size;
  v8 = 0;
  if ( *((_DWORD *)a1 + 1) )
  {
    v14 = v103;
    do
    {
      if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(a1, v4, v14) )
      {
        v15 = NgscbpHSTICheckProviderInfo(a1, v4, v14);
        v8 = v15;
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v15);
          }
          if ( v8 < 0 )
            goto LABEL_221;
        }
        v13 = Size;
        v16 = &a1[*(unsigned int *)&a1[12 * v4 + 8]];
        v17 = (unsigned int *)(v16 + 520);
        v18 = *((_DWORD *)v16 + 130);
        if ( Size )
        {
          if ( v18 != v105 )
          {
            NgscbpHSTIGetImplementationID(v16, v124);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, (unsigned int)v124, v105, *v17);
            *(_QWORD *)&UserData.Size = 512;
            UserData.Ptr = (ULONGLONG)v124;
            v118 = 4;
            v117 = (bool *)&v105;
            v21 = -1;
            v119 = (wchar_t *)v17;
            v120 = 4;
            v121 = aNgscbCommonUm;
            do
              ++v21;
            while ( aNgscbCommonUm[v21] );
            v123 = 0;
            v122 = 2 * v21 + 2;
            NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_SEC_FEAT_SIZE_MISMATCH, 4u, &UserData);
            v13 = Size;
            if ( *v17 > Size )
            {
              v13 = *v17;
              Size = *v17;
            }
          }
        }
        else
        {
          v13 = *((_DWORD *)v16 + 130);
          Size = v13;
          v105 = v18;
        }
        v14 = v103;
      }
      ++v4;
    }
    while ( v4 < *((_DWORD *)a1 + 1) );
    v11 = -1;
  }
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52);
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&Size;
    v117 = (bool *)aNgscbCommonUm;
    do
      ++v11;
    while ( aNgscbCommonUm[v11] );
    v118 = (unsigned int)(2 * v11 + 2);
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PROVIDER_COUNT, 2u, &UserData);
    goto LABEL_221;
  }
  v22 = HeapAllocateByByteCount<unsigned char>(&lpMem, v13);
  v8 = v22;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v22);
    if ( v8 < 0 )
      goto LABEL_210;
  }
  v23 = HeapAllocateByByteCount<unsigned char>(&v107, Size);
  v8 = v23;
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v23);
    if ( v8 < 0 )
      goto LABEL_210;
  }
  v24 = 0;
  Size_4 = 0;
  v25 = -1;
  v102 = 0;
  memset_0(lpMem, 0, Size);
  memset_0(v107, 0, Size);
  v26 = 0;
  if ( !*((_DWORD *)a1 + 1) )
  {
LABEL_88:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60);
    v32 = -1;
    UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
    v33 = 0;
    do
      ++v32;
    while ( aNgscbCommonUm[v32] );
    UserData.Reserved = 0;
    UserData.Size = 2 * v32 + 2;
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_NO_PLATSECROLEREF_PROVIDER, 1u, &UserData);
    Size_4 = 1;
LABEL_98:
    if ( Size >= 0xFFFFFDF8 )
    {
      v34 = WPP_GLOBAL_Control;
      v8 = -2147024362;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_210;
      v35 = 61;
    }
    else
    {
      v106 = Size + 520;
      v36 = ULongLongToULong(v24 * (unsigned __int64)(Size + 520), &v106);
      v8 = v36;
      if ( v36 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v36);
          v37 = Size;
          v34 = WPP_GLOBAL_Control;
        }
        if ( v8 < 0 )
          goto LABEL_210;
      }
      else
      {
        v34 = WPP_GLOBAL_Control;
      }
      v38 = v106 + v37;
      if ( v106 + v37 < v106 )
      {
        v8 = -2147024362;
        if ( v34 == (_BYTE *)&WPP_GLOBAL_Control || (v34[28] & 0x40) == 0 )
          goto LABEL_210;
        v35 = 63;
      }
      else
      {
        v39 = v38 + v37;
        if ( v38 + v37 < v38 )
        {
          v8 = -2147024362;
          if ( v34 == (_BYTE *)&WPP_GLOBAL_Control || (v34[28] & 0x40) == 0 )
            goto LABEL_210;
          v35 = 64;
        }
        else
        {
          v40 = v39 + 28;
          if ( v39 + 28 >= v39 )
          {
            v41 = HeapAllocateByByteCount<_NGSCB_HSTI_RESULTS>(&Src, v40);
            v106 = v41;
            v8 = v41;
            if ( !v41 )
              goto LABEL_115;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v41);
            }
            if ( v8 < 0 )
            {
              v42 = (struct _NGSCB_HSTI_RESULTS *)Src;
            }
            else
            {
LABEL_115:
              v42 = (struct _NGSCB_HSTI_RESULTS *)Src;
              v99 = (unsigned int *)Src;
              memset_0(Src, 0, v40);
              v43 = v102;
              *((_DWORD *)v42 + 6) = -1;
              *(_DWORD *)v42 = v40;
              *((_DWORD *)v42 + 4) = 28;
              *((_DWORD *)v42 + 5) = v43;
              v44 = *((_DWORD *)v42 + 4) + v43 * (Size + 520);
              *((_DWORD *)v42 + 1) = v44;
              *((_DWORD *)v42 + 2) = v44 + Size;
              *((_DWORD *)v42 + 3) = Size;
              v45 = *((_DWORD *)v42 + 1);
              v46 = *((_DWORD *)v42 + 2);
              if ( v46 >= v45 && v45 >= *((_DWORD *)v42 + 4) && (v47 = Size, v46 + Size == v40) )
              {
                v48 = 0;
                if ( *((_DWORD *)v112 + 1) )
                {
                  v49 = v112;
                  do
                  {
                    if ( v33 >= v43 )
                      break;
                    if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(v49, v48, v103) )
                    {
                      v50 = &v49[*(unsigned int *)&v49[12 * v48 + 8]];
                      if ( *(_DWORD *)v50 == 3 )
                      {
                        v51 = *((unsigned int *)v50 + 130);
                        v52 = 0;
                        v53 = (char *)&v50[2 * v51 + 524];
                        Src = v53;
                        if ( (_DWORD)v51 )
                        {
                          v54 = v107;
                          do
                          {
                            if ( v52 >= v47 )
                              break;
                            v55 = v52;
                            v56 = v50[v52 + 524];
                            if ( *((_DWORD *)v50 + 1) == 1 )
                            {
                              *((_BYTE *)lpMem + v52) |= v56;
                              if ( v99[6] == -1 )
                                v99[6] = v33;
                            }
                            else if ( v56 )
                            {
                              NgscbpHSTIGetImplementationID(v50, v124);
                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                              {
                                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, v57, v124);
                              }
                              *(_QWORD *)&UserData.Size = 512;
                              UserData.Ptr = (ULONGLONG)v124;
                              v58 = -1;
                              v117 = (bool *)aNgscbCommonUm;
                              do
                                ++v58;
                              while ( aNgscbCommonUm[v58] );
                              v118 = (unsigned int)(2 * v58 + 2);
                              NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PLATSECROLEREF_PROVIDER, 2u, &UserData);
                              v53 = (char *)Src;
                              v54 = v107;
                              Size_4 = 1;
                            }
                            v59 = v53[v52++];
                            v54[v55] |= v59;
                            v47 = Size;
                          }
                          while ( v52 < *((_DWORD *)v50 + 130) );
                        }
                        v60 = v50 + 8;
                        v61 = v99[4];
                        v62 = (char *)v99 + v33 * (v99[3] + 520LL);
                        v63 = 4;
                        *(_DWORD *)&v62[v61] = v47 + 520;
                        *(_DWORD *)&v62[v61 + 4] = Size;
                        v64 = &v62[v61 + 8];
                        do
                        {
                          *(_OWORD *)v64 = *v60;
                          *((_OWORD *)v64 + 1) = v60[1];
                          *((_OWORD *)v64 + 2) = v60[2];
                          *((_OWORD *)v64 + 3) = v60[3];
                          *((_OWORD *)v64 + 4) = v60[4];
                          *((_OWORD *)v64 + 5) = v60[5];
                          *((_OWORD *)v64 + 6) = v60[6];
                          v65 = v60[7];
                          v60 += 8;
                          *((_OWORD *)v64 + 7) = v65;
                          v64 += 128;
                          --v63;
                        }
                        while ( v63 );
                        memcpy_0(&v62[v61 + 520], v53, Size);
                        v47 = Size;
                        ++v33;
                      }
                    }
                    v43 = v102;
                    ++v48;
                  }
                  while ( v48 < *((_DWORD *)v49 + 1) );
                  v8 = v106;
                  v42 = (struct _NGSCB_HSTI_RESULTS *)v99;
                }
                v66 = lpMem;
                memcpy_0((char *)v42 + *((unsigned int *)v42 + 1), lpMem, v47);
                v67 = v107;
                v68 = (*((_BYTE *)v107 + 1) & 8) != 0;
                *(_QWORD *)&UserData.Size = 4;
                v101 = v68;
                v117 = (bool *)aNgscbCommonUm;
                UserData.Ptr = (ULONGLONG)&v101;
                v69 = -1;
                do
                  ++v69;
                while ( aNgscbCommonUm[v69] );
                v118 = (unsigned int)(2 * v69 + 2);
                NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_THUNDERBOLT_CONFIG, 2u, &UserData);
                if ( NgscbGet_TEST_BooleanOverride(L"ReportDEPlatformHstiSecureThunderboltBit", Size_5)
                  && Size_5[0]
                  && (int)NgscbGetCpuVendorA(&v113) >= 0
                  && v113
                  && !(unsigned int)o__stricmp_0(v113, "GenuineIntel")
                  && Size >= 2 )
                {
                  if ( (v67[1] & 8) != 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69);
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70);
                    }
                    v67[1] |= 8u;
                  }
                }
                memcpy_0((char *)v42 + *((unsigned int *)v42 + 2), v67, Size);
                v71 = Size;
                v72 = 0;
                v102 = 0;
                if ( Size )
                {
                  v73 = 0;
                  v74 = 0;
                  do
                  {
                    LOBYTE(v70) = v66[v74] & ~v67[v73];
                    Size_5[0] = v70;
                    if ( (_BYTE)v70 )
                    {
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_dD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v72,
                          v70,
                          (unsigned int)v72,
                          (unsigned __int8)v70);
                      }
                      *(_QWORD *)&UserData.Size = 4;
                      UserData.Ptr = (ULONGLONG)&v102;
                      v118 = 1;
                      v117 = Size_5;
                      v75 = -1;
                      v119 = aNgscbCommonUm;
                      do
                        ++v75;
                      while ( aNgscbCommonUm[v75] );
                      v120 = (unsigned int)(2 * v75 + 2);
                      NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_MISSING_FEATURES, 3u, &UserData);
                      v71 = Size;
                      LODWORD(v72) = v102;
                      Size_4 = 1;
                    }
                    v72 = (unsigned int)(v72 + 1);
                    v102 = v72;
                    v74 = v72;
                    v73 = (unsigned int)v72;
                  }
                  while ( (unsigned int)v72 < v71 );
                }
                if ( Size_4 )
                {
                  v76 = v112;
                  v77 = 0;
                  if ( *((_DWORD *)v112 + 1) )
                  {
                    do
                    {
                      if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(v76, v77, v103) )
                      {
                        v78 = &v76[*(unsigned int *)&v76[12 * v77 + 8]];
                        if ( *(_DWORD *)v78 == 3 )
                        {
                          v79 = HeapAllocateByByteCount<unsigned short>(&v109);
                          v8 = v79;
                          if ( v79 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                72,
                                &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                                v79);
                            }
                            if ( v8 < 0 )
                              goto LABEL_210;
                          }
                          NgscbpHSTIGetImplementationID(v78, v124);
                          if ( v109 )
                          {
                            v82 = *((unsigned int *)v78 + 130);
                            v83 = (char *)&v78[2 * v82];
                            v84 = v109;
                            if ( StringCchCopyNW(v109, 0x2800u, (const unsigned __int16 *)&v83[v82 + 524], 0x27FFu) < 0 )
                              *(_DWORD *)v84 = 63;
                          }
                          else
                          {
                            v84 = 0;
                          }
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v80, v81, (unsigned int)v124, (__int64)v84);
                          }
                          *(_QWORD *)&UserData.Size = 512;
                          UserData.Ptr = (ULONGLONG)v124;
                          v117 = (bool *)v84;
                          v85 = -1;
                          v118 = 20480;
                          v119 = aNgscbCommonUm;
                          do
                            ++v85;
                          while ( aNgscbCommonUm[v85] );
                          v120 = (unsigned int)(2 * v85 + 2);
                          NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PROVIDER_ERROR, 3u, &UserData);
                        }
                      }
                      ++v77;
                    }
                    while ( v77 < *((_DWORD *)v76 + 1) );
                    v42 = (struct _NGSCB_HSTI_RESULTS *)v99;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74);
                  }
                  *v114 = 1;
                }
                *v115 = v42;
                v42 = 0;
              }
              else
              {
                v8 = -2147418113;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    67,
                    &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                    2147549183LL);
                }
              }
            }
            goto LABEL_211;
          }
          v8 = -2147024362;
          if ( v34 == (_BYTE *)&WPP_GLOBAL_Control || (v34[28] & 0x40) == 0 )
            goto LABEL_210;
          v35 = 65;
        }
      }
    }
LABEL_209:
    WPP_SF_d(*((_QWORD *)v34 + 2), v35, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147942934LL);
    goto LABEL_210;
  }
  while ( !(unsigned __int8)NgscbpHSTIHasProviderInfo(a1, v26, v103) )
  {
LABEL_86:
    if ( ++v26 >= *((_DWORD *)a1 + 1) )
    {
      v24 = v102;
      if ( v25 == -1 )
        goto LABEL_88;
      v33 = 0;
      goto LABEL_98;
    }
  }
  v27 = &a1[*(unsigned int *)&a1[12 * v26 + 8]];
  if ( *(_DWORD *)v27 != 3 )
  {
    NgscbpHSTIGetImplementationID(&a1[*(unsigned int *)&a1[12 * v26 + 8]], v124);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v28, (unsigned int)v124, *(_DWORD *)v27);
    v117 = (bool *)v27;
    UserData.Ptr = (ULONGLONG)v124;
    *(_QWORD *)&UserData.Size = 512;
    v29 = -1;
    v118 = 4;
    v119 = aNgscbCommonUm;
    do
      ++v29;
    while ( aNgscbCommonUm[v29] );
    v30 = (const EVENT_DESCRIPTOR *)FVE_AUTODE_HSTI_REPORT_UNKNOWN_VERSIONED_PROVIDER;
    goto LABEL_85;
  }
  if ( v102 + 1 >= v102 )
  {
    ++v102;
    NgscbpHSTIGetImplementationID(v27, v124);
    if ( *((_DWORD *)v27 + 1) == 1 )
    {
      if ( v25 != -1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v31, v124);
        *(_QWORD *)&UserData.Size = 512;
        UserData.Ptr = (ULONGLONG)v124;
        v118 = 1;
        v117 = (bool *)&v100;
        v29 = -1;
        v119 = aNgscbCommonUm;
        do
          ++v29;
        while ( aNgscbCommonUm[v29] );
        Size_4 = 1;
        v30 = (const EVENT_DESCRIPTOR *)FVE_AUTODE_HSTI_REPORT_EXTRA_PLATSECROLEREF_PROVIDER;
        goto LABEL_85;
      }
      v25 = v26;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v31, v124);
      *(_QWORD *)&UserData.Size = 512;
      UserData.Ptr = (ULONGLONG)v124;
      v118 = 1;
      v117 = (bool *)&v100;
      v29 = -1;
      v119 = aNgscbCommonUm;
      do
        ++v29;
      while ( aNgscbCommonUm[v29] );
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, v31, v124);
      *(_QWORD *)&UserData.Size = 512;
      UserData.Ptr = (ULONGLONG)v124;
      v118 = 1;
      v117 = (bool *)&v104;
      v29 = -1;
      v119 = aNgscbCommonUm;
      do
        ++v29;
      while ( aNgscbCommonUm[v29] );
    }
    v30 = &FVE_AUTODE_HSTI_REPORT_PLATSECROLEREF_PROVIDER;
LABEL_85:
    v120 = (unsigned int)(2 * v29 + 2);
    NgscbTryWriteEventLog(v30, 3u, &UserData);
    goto LABEL_86;
  }
  v34 = WPP_GLOBAL_Control;
  v8 = -2147024362;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v35 = 56;
    goto LABEL_209;
  }
LABEL_210:
  v42 = (struct _NGSCB_HSTI_RESULTS *)v99;
LABEL_211:
  v86 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v86);
  }
  v88 = v107;
  if ( v107 )
  {
    v89 = GetProcessHeap();
    HeapFree(v89, 0, v88);
  }
  if ( v42 )
  {
    v90 = GetProcessHeap();
    HeapFree(v90, 0, v42);
  }
  v91 = v113;
  if ( v113 )
  {
    v92 = GetProcessHeap();
    HeapFree(v92, 0, v91);
  }
  v93 = v109;
  if ( v109 )
  {
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v93);
  }
LABEL_221:
  NgscbTryCloseEventLog();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036f9c  push    rbp
0x180036f9e  push    rbx
0x180036f9f  push    rsi
0x180036fa0  push    rdi
0x180036fa1  push    r12
0x180036fa3  push    r13
0x180036fa5  push    r14
0x180036fa7  push    r15
0x180036fa9  lea     rbp, [rsp-208h]
0x180036fb1  sub     rsp, 308h
0x180036fb8  mov     rax, cs:__security_cookie
0x180036fbf  xor     rax, rsp
0x180036fc2  mov     [rbp+240h+var_50], rax
0x180036fc9  xor     esi, esi
0x180036fcb  mov     [rsp+340h+var_2F8], edx
0x180036fcf  mov     rbx, r8
0x180036fd2  mov     [rbp+240h+var_2C0], rcx
0x180036fd6  mov     eax, esi
0x180036fd8  mov     [rbp+240h+var_2A8], r9
0x180036fdc  mov     r13, rcx
0x180036fdf  mov     [rbp+240h+var_2B0], rbx
0x180036fe3  lea     r8d, [rsi+48h]; Size
0x180036fe7  mov     [rsp+340h+var_2F0], esi
0x180036feb  xor     edx, edx; Val
0x180036fed  mov     dword ptr [rsp+340h+Size], esi
0x180036ff1  lea     rcx, [rbp+240h+UserData.Size]; void *
0x180036ff5  mov     [rsp+340h+lpMem], rsi
0x180036ffa  mov     rdi, r9
0x180036ffd  mov     [rsp+340h+var_2E8], rsi
0x180037002  mov     [rsp+340h+var_308], rax
0x180037007  mov     [rsp+340h+Src], rax
0x18003700c  mov     byte ptr [rsp+340h+Size+5], sil
0x180037011  mov     [rbp+240h+var_2B8], rsi
0x180037015  mov     [rsp+340h+var_2D8], rsi
0x18003701a  mov     [rbp+240h+UserData.Ptr], rsi
0x18003701e  call    memset_0
0x180037023  mov     [rsp+340h+var_2C8], 1
0x18003702b  mov     [rsp+340h+var_300], 1
0x180037030  mov     [rsp+340h+var_2F4], sil
0x180037035  mov     [rsp+340h+var_2FF], sil
0x18003703a  test    rdi, rdi
0x18003703d  jz      short loc_180037042
0x18003703f  mov     [rdi], rsi
0x180037042  test    rbx, rbx
0x180037045  jnz     short loc_18003708A
0x180037047  mov     ebx, 80004003h
0x18003704c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037053  lea     rdi, WPP_GLOBAL_Control
0x18003705a  cmp     rcx, rdi
0x18003705d  jz      loc_180037F86
0x180037063  test    byte ptr [rcx+1Ch], 40h
0x180037067  jz      loc_180037F86
0x18003706d  mov     edx, 2Fh ; '/'
0x180037072  mov     rcx, [rcx+10h]
0x180037076  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18003707d  mov     r9d, ebx
0x180037080  call    WPP_SF_d
0x180037085  jmp     loc_180037F86
0x18003708a  mov     [rbx], sil
0x18003708d  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x180037092  lea     rax, [rsp+340h+var_2C8]
0x180037097  mov     [rbp+240h+UserData.Ptr], r13
0x18003709b  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x1800370a2  mov     [rbp+240h+var_290], rax
0x1800370a6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800370aa  mov     qword ptr [rbp+240h+UserData.Size], 4
0x1800370b2  mov     rax, r14
0x1800370b5  mov     [rbp+240h+var_288], 4
0x1800370bd  mov     [rbp+240h+var_280], rcx
0x1800370c1  inc     rax
0x1800370c4  cmp     [rcx+rax*2], si
0x1800370c8  jnz     short loc_1800370C1
0x1800370ca  lea     eax, ds:2[rax*2]
0x1800370d1  mov     dword ptr [rbp+240h+var_278+4], esi
0x1800370d4  lea     r8, [rbp+240h+UserData]; UserData
0x1800370d8  mov     dword ptr [rbp+240h+var_278], eax
0x1800370db  mov     edx, 3; UserDataCount
0x1800370e0  lea     rcx, FVE_AUTODE_HSTI_REPORT_DATA_VERSION; EventDescriptor
0x1800370e7  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800370ec  cmp     dword ptr [r13+0], 1
0x1800370f1  jz      short loc_18003714E
0x1800370f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370fa  lea     rdi, WPP_GLOBAL_Control
0x180037101  cmp     rcx, rdi
0x180037104  jz      short loc_18003712C
0x180037106  test    byte ptr [rcx+1Ch], 2
0x18003710a  jz      short loc_18003712C
0x18003710c  mov     r9d, [r13+0]
0x180037110  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180037117  mov     rcx, [rcx+10h]
0x18003711b  mov     edx, 30h ; '0'
0x180037120  call    WPP_SF_d
0x180037125  mov     rcx, cs:WPP_GLOBAL_Control
0x18003712c  mov     ebx, 8007000Dh
0x180037131  cmp     rcx, rdi
0x180037134  jz      loc_180037F86
0x18003713a  test    byte ptr [rcx+1Ch], 40h
0x18003713e  jz      loc_180037F86
0x180037144  mov     edx, 31h ; '1'
0x180037149  jmp     loc_180037072
0x18003714e  mov     r11d, dword ptr [rsp+340h+Size]
0x180037153  lea     rdi, WPP_GLOBAL_Control
0x18003715a  xor     edx, edx
0x18003715c  lea     r12, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180037163  mov     ebx, esi
0x180037165  mov     r15d, 40h ; '@'
0x18003716b  cmp     [r13+4], edx
0x18003716f  jbe     loc_1800372DB
0x180037175  mov     r14d, [rsp+340h+var_2F8]
0x18003717a  mov     r8d, r14d
0x18003717d  mov     edx, esi
0x18003717f  mov     rcx, r13
0x180037182  call    NgscbpHSTIHasProviderInfo
0x180037187  xor     edx, edx
0x180037189  test    al, al
0x18003718b  jz      loc_1800372CB
0x180037191  mov     r8d, r14d
0x180037194  mov     edx, esi
0x180037196  mov     rcx, r13
0x180037199  call    NgscbpHSTICheckProviderInfo
0x18003719e  xor     edx, edx
0x1800371a0  mov     ebx, eax
0x1800371a2  test    eax, eax
0x1800371a4  jz      short loc_1800371D6
0x1800371a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371ad  cmp     rcx, rdi
0x1800371b0  jz      short loc_1800371CE
0x1800371b2  test    [rcx+1Ch], r15b
0x1800371b6  jz      short loc_1800371CE
0x1800371b8  mov     rcx, [rcx+10h]
0x1800371bc  mov     edx, 32h ; '2'
0x1800371c1  mov     r9d, eax
0x1800371c4  mov     r8, r12
0x1800371c7  call    WPP_SF_d
0x1800371cc  xor     edx, edx
0x1800371ce  test    ebx, ebx
0x1800371d0  js      loc_180037F86
0x1800371d6  mov     r11d, dword ptr [rsp+340h+Size]
0x1800371db  mov     eax, esi
0x1800371dd  lea     rcx, [rax+rax*2]
0x1800371e1  mov     ecx, [r13+rcx*4+8]
0x1800371e6  add     rcx, r13
0x1800371e9  lea     r14, [rcx+208h]
0x1800371f0  mov     eax, [r14]
0x1800371f3  test    r11d, r11d
0x1800371f6  jnz     short loc_180037208
0x1800371f8  mov     r11d, eax
0x1800371fb  mov     dword ptr [rsp+340h+Size], eax
0x1800371ff  mov     [rsp+340h+var_2F0], eax
0x180037203  jmp     loc_1800372C6
0x180037208  cmp     eax, [rsp+340h+var_2F0]
0x18003720c  jz      loc_1800372C6
0x180037212  lea     rdx, [rbp+240h+var_250]
0x180037216  call    NgscbpHSTIGetImplementationID
0x18003721b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037222  cmp     rcx, rdi
0x180037225  jz      short loc_180037249
0x180037227  test    byte ptr [rcx+1Ch], 4
0x18003722b  jz      short loc_180037249
0x18003722d  mov     eax, [r14]
0x180037230  lea     r9, [rbp+240h+var_250]
0x180037234  mov     rcx, [rcx+10h]
0x180037238  mov     [rsp+340h+var_318], eax
0x18003723c  mov     eax, [rsp+340h+var_2F0]
0x180037240  mov     dword ptr [rsp+340h+var_320], eax
0x180037244  call    WPP_SF_Sdd
0x180037249  lea     rax, [rbp+240h+var_250]
0x18003724d  mov     qword ptr [rbp+240h+UserData.Size], 200h
0x180037255  mov     [rbp+240h+UserData.Ptr], rax
0x180037259  lea     rdx, aNgscbCommonUm; "ngscb_common_um"
0x180037260  lea     rax, [rsp+340h+var_2F0]
0x180037265  mov     [rbp+240h+var_288], 4
0x18003726d  xor     ecx, ecx
0x18003726f  mov     [rbp+240h+var_290], rax
0x180037273  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037277  mov     [rbp+240h+var_280], r14
0x18003727b  mov     [rbp+240h+var_278], 4
0x180037283  mov     [rbp+240h+var_270], rdx
0x180037287  inc     rax
0x18003728a  cmp     [rdx+rax*2], cx
0x18003728e  jnz     short loc_180037287
0x180037290  lea     eax, ds:2[rax*2]
0x180037297  mov     [rbp+240h+var_264], ecx
0x18003729a  lea     rcx, FVE_AUTODE_HSTI_REPORT_SEC_FEAT_SIZE_MISMATCH; EventDescriptor
0x1800372a1  mov     [rbp+240h+var_268], eax
0x1800372a4  lea     r8, [rbp+240h+UserData]; UserData
0x1800372a8  mov     edx, 4; UserDataCount
0x1800372ad  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800372b2  mov     r11d, dword ptr [rsp+340h+Size]
0x1800372b7  xor     edx, edx
0x1800372b9  cmp     [r14], r11d
0x1800372bc  jbe     short loc_1800372C6
0x1800372be  mov     r11d, [r14]
0x1800372c1  mov     dword ptr [rsp+340h+Size], r11d
0x1800372c6  mov     r14d, [rsp+340h+var_2F8]
0x1800372cb  inc     esi
0x1800372cd  cmp     esi, [r13+4]
0x1800372d1  jb      loc_18003717A
0x1800372d7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800372db  test    r11d, r11d
0x1800372de  jnz     short loc_18003734F
0x1800372e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372e7  cmp     rcx, rdi
0x1800372ea  jz      short loc_180037301
0x1800372ec  test    byte ptr [rcx+1Ch], 4
0x1800372f0  jz      short loc_180037301
0x1800372f2  mov     rcx, [rcx+10h]
0x1800372f6  lea     edx, [r11+34h]
0x1800372fa  call    WPP_SF_
0x1800372ff  xor     edx, edx
0x180037301  lea     rax, [rsp+340h+Size]
0x180037306  mov     qword ptr [rbp+240h+UserData.Size], 4
0x18003730e  mov     [rbp+240h+UserData.Ptr], rax
0x180037312  lea     rax, aNgscbCommonUm; "ngscb_common_um"
0x180037319  mov     [rbp+240h+var_290], rax
0x18003731d  inc     r14
0x180037320  cmp     [rax+r14*2], dx
0x180037325  jnz     short loc_18003731D
0x180037327  lea     eax, ds:2[r14*2]
0x18003732f  mov     dword ptr [rbp+240h+var_288+4], edx
0x180037332  mov     edx, 2; UserDataCount
0x180037337  mov     dword ptr [rbp+240h+var_288], eax
0x18003733a  lea     r8, [rbp+240h+UserData]; UserData
0x18003733e  lea     rcx, FVE_AUTODE_HSTI_REPORT_PROVIDER_COUNT; EventDescriptor
0x180037345  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18003734a  jmp     loc_180037F86
0x18003734f  mov     edx, r11d
0x180037352  lea     rcx, [rsp+340h+lpMem]
0x180037357  call    ??$HeapAllocateByByteCount@E@@YAJPEAPEAE_K@Z; HeapAllocateByByteCount<uchar>(uchar * *,unsigned __int64)
0x18003735c  xor     r14d, r14d
0x18003735f  mov     ebx, eax
0x180037361  test    eax, eax
0x180037363  jz      short loc_180037392
0x180037365  mov     rcx, cs:WPP_GLOBAL_Control
0x18003736c  cmp     rcx, rdi
0x18003736f  jz      short loc_18003738A
0x180037371  test    [rcx+1Ch], r15b
0x180037375  jz      short loc_18003738A
0x180037377  mov     rcx, [rcx+10h]
0x18003737b  lea     edx, [r14+35h]
0x18003737f  mov     r9d, eax
0x180037382  mov     r8, r12
0x180037385  call    WPP_SF_d
0x18003738a  test    ebx, ebx
0x18003738c  js      loc_180037EF1
0x180037392  mov     edx, dword ptr [rsp+340h+Size]
0x180037396  lea     rcx, [rsp+340h+var_2E8]
0x18003739b  call    ??$HeapAllocateByByteCount@E@@YAJPEAPEAE_K@Z; HeapAllocateByByteCount<uchar>(uchar * *,unsigned __int64)
0x1800373a0  mov     ebx, eax
0x1800373a2  test    eax, eax
0x1800373a4  jz      short loc_1800373D4
0x1800373a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373ad  cmp     rcx, rdi
0x1800373b0  jz      short loc_1800373CC
0x1800373b2  test    [rcx+1Ch], r15b
0x1800373b6  jz      short loc_1800373CC
0x1800373b8  mov     rcx, [rcx+10h]
0x1800373bc  mov     edx, 36h ; '6'
0x1800373c1  mov     r9d, eax
0x1800373c4  mov     r8, r12
0x1800373c7  call    WPP_SF_d
0x1800373cc  test    ebx, ebx
0x1800373ce  js      loc_180037EF1
0x1800373d4  mov     r8d, dword ptr [rsp+340h+Size]; Size
0x1800373d9  xor     ebx, ebx
0x1800373db  mov     rcx, [rsp+340h+lpMem]; void *
0x1800373e0  xor     edx, edx; Val
0x1800373e2  mov     byte ptr [rsp+340h+Size+4], r14b
0x1800373e7  or      r14d, 0FFFFFFFFh
0x1800373eb  mov     [rsp+340h+var_2FC], ebx
0x1800373ef  call    memset_0
0x1800373f4  mov     r8d, dword ptr [rsp+340h+Size]; Size
0x1800373f9  xor     edx, edx; Val
0x1800373fb  mov     rcx, [rsp+340h+var_2E8]; void *
0x180037400  call    memset_0
0x180037405  xor     eax, eax
0x180037407  mov     esi, eax
0x180037409  cmp     [r13+4], eax
0x18003740d  jbe     loc_180037653
0x180037413  mov     r8d, [rsp+340h+var_2F8]
0x180037418  mov     edx, esi
0x18003741a  mov     rcx, r13
0x18003741d  call    NgscbpHSTIHasProviderInfo
0x180037422  test    al, al
0x180037424  jz      loc_180037639
0x18003742a  mov     eax, esi
0x18003742c  lea     rcx, [rax+rax*2]
0x180037430  mov     ebx, [r13+rcx*4+8]
0x180037435  add     rbx, r13
0x180037438  cmp     dword ptr [rbx], 3
0x18003743b  jz      short loc_1800374B5
0x18003743d  lea     rdx, [rbp+240h+var_250]
0x180037441  mov     rcx, rbx
0x180037444  call    NgscbpHSTIGetImplementationID
0x180037449  mov     rcx, cs:WPP_GLOBAL_Control
0x180037450  cmp     rcx, rdi
0x180037453  jz      short loc_180037473
0x180037455  test    byte ptr [rcx+1Ch], 4
0x180037459  jz      short loc_180037473
0x18003745b  mov     eax, [rbx]
  ... truncated ...
```
