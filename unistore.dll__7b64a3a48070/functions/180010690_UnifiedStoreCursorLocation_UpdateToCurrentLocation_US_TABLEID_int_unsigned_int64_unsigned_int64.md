# UnifiedStoreCursorLocation::UpdateToCurrentLocation(US_TABLEID,int,unsigned __int64,unsigned __int64)

- ea: `0x180010690`
- end: `0x180010e5c`
- name: `?UpdateToCurrentLocation@UnifiedStoreCursorLocation@@QEAAJW4US_TABLEID@@H_K1@Z`
- size: `1996`
- prototype: `int __high(enum US_TABLEID, int, unsigned __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180002fbc`
- `0x18000d9d0`
- `0x180010e70`
- `0x180010ea0`
- `0x180012100`
- `0x1800123e0`
- `0x180012bb0`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180010690`
- `0x180045990`
- `0x18004bd20`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010b08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010c1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010b08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010c1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800106f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800106f9`
- `ESENT!JetGetSecondaryIndexBookmark` at `0x18001099e`
- `ESENT!JetGetSecondaryIndexBookmark` at `0x18001099e`
- `ESENT!JetRetrieveColumn` at `0x180010b48`
- `ESENT!JetRetrieveColumn` at `0x180010b48`
- `ESENT!JetGetBookmark` at `0x1800107f7`
- `ESENT!JetGetBookmark` at `0x1800107f7`
- `ESENT!JetGetErrorInfoW` at `0x180010870`
- `ESENT!JetGetErrorInfoW` at `0x180010a20`
- `ESENT!JetGetErrorInfoW` at `0x180010bc2`
- `ESENT!JetGetErrorInfoW` at `0x180010870`
- `ESENT!JetGetErrorInfoW` at `0x180010a20`
- `ESENT!JetGetErrorInfoW` at `0x180010bc2`

## string_xrefs

- `0x180010a8c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180010c97`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180010ccf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180010d94`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180010787`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800108b5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010ae1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010c29`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010ce8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010db7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall UnifiedStoreCursorLocation::UpdateToCurrentLocation(
        __int64 a1,
        int a2,
        int a3,
        JET_SESID a4,
        JET_TABLEID tableid)
{
  __int64 v5; // rbx
  int v7; // r14d
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 *v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r9
  unsigned int HresultFromJetError; // ebx
  void *pvPrimaryBookmark; // rcx
  unsigned __int64 cbPrimaryBookmarkMax; // rax
  void *v18; // r8
  unsigned __int64 v19; // r9
  JET_ERR Bookmark; // eax
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rbx
  unsigned __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 result; // rax
  unsigned __int64 v28; // rbx
  __int64 v29; // r14
  unsigned __int64 v30; // rbx
  __int64 v31; // r14
  __int64 v32; // r9
  JET_ERR SecondaryIndexBookmark; // eax
  int v34; // ecx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // ecx
  unsigned int v38; // ebx
  JET_ERR v39; // eax
  int v40; // ebx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rbx
  unsigned __int64 v45; // rdi
  int v46; // [rsp+50h] [rbp-B0h] BYREF
  JET_ERR v47; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int pcbActual; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int pcbSecondaryKeyActual; // [rsp+64h] [rbp-9Ch] BYREF
  int pvData; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h]
  JET_COLUMNID columnid[4]; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+80h] [rbp-80h] BYREF
  __int128 v54; // [rsp+84h] [rbp-7Ch]
  __int128 v55; // [rsp+94h] [rbp-6Ch]
  __int128 v56; // [rsp+A4h] [rbp-5Ch]
  __int128 v57; // [rsp+B4h] [rbp-4Ch]
  __int128 v58; // [rsp+C4h] [rbp-3Ch]
  __int128 v59; // [rsp+D4h] [rbp-2Ch]
  __int128 v60; // [rsp+E4h] [rbp-1Ch]
  __int128 v61; // [rsp+F4h] [rbp-Ch]
  __int128 v62; // [rsp+104h] [rbp+4h]
  int v63; // [rsp+114h] [rbp+14h]

  v51 = a3;
  v5 = a2;
  *(_DWORD *)a1 = 0;
  pvData = 0;
  v7 = a3;
  *(_QWORD *)columnid = 0;
  if ( a2 && a2 != 53 )
    v9 = 65539;
  else
    v9 = 17170435;
  AcquireSRWLockShared(&g_columnIdMapping);
  if ( dword_18010D248 )
  {
    v10 = qword_18010C4C8[5 * v5 + 2];
    v11 = &qword_18010C4C8[5 * v5];
    if ( v10 )
    {
      v12 = (unsigned __int64)v9 >> 16;
      v13 = *(_QWORD *)(v10 + 16 * (v12 & ((8LL << *((_BYTE *)v11 + 32)) - 1)));
      if ( v13 )
      {
        v14 = **(_QWORD **)(v10 + 16 * (v12 & ((8LL << *((_BYTE *)v11 + 32)) - 1)) + 8);
        while ( v13 != v14 )
        {
          if ( *(_QWORD *)(v13 + 16) >= v12 )
          {
            if ( *(_QWORD *)(v13 + 16) > v12 )
              break;
            if ( v9 == *(_DWORD *)(v13 + 24) )
            {
              if ( (__int64 *)v13 != v11 )
              {
                *(_QWORD *)columnid = *(_QWORD *)(v13 + 28);
                ReleaseSRWLockShared(&g_columnIdMapping);
                goto LABEL_52;
              }
              break;
            }
          }
          v13 = *(_QWORD *)v13;
        }
      }
    }
  }
  ReleaseSRWLockShared(&g_columnIdMapping);
  Log_UnistoreHREvent_0(
    2147549183LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    753);
LABEL_52:
  pvData = -1;
  v39 = JetRetrieveColumn(a4, tableid, columnid[0], &pvData, 4u, 0, 4u, 0);
  v40 = v39;
  if ( !g_fInProc || dword_18010D924 )
    goto LABEL_57;
  if ( v39 == -1414 )
    goto LABEL_70;
  v47 = v39;
  if ( v39 < 0 )
  {
    v53 = 152;
    v63 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    if ( (int)JetGetErrorInfoW(&v47, &v53, 152, 1, 0) >= 0 )
    {
      if ( DWORD1(v54) != 10 )
      {
        if ( DWORD1(v54) == 11 )
        {
          v46 = v47;
          UnistoreTelemetry::JetInconsistentError<unsigned long>(&v46);
        }
        else if ( DWORD1(v54) == 12 )
        {
          v46 = v47;
          UnistoreTelemetry::JetFragmentationError<unsigned long>(&v46);
        }
        goto LABEL_57;
      }
      if ( v47 != -1414 )
      {
LABEL_70:
        v41 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v40);
        if ( v41 >= 0 )
        {
          v46 = v40;
          UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v46);
          if ( (unsigned int)IsJetCorruptionError(v40) )
          {
            Log_AssertionEvent(
              v42,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
              109);
            __int2c();
          }
        }
        else
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v41,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            102);
        }
      }
    }
  }
LABEL_57:
  if ( v40 == -1603 )
    return 2147942425LL;
  if ( v40 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v40);
    Log_UnistoreHREvent_0(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      772);
    if ( (HresultFromJetError & 0x80000000) != 0 )
    {
      Log_UnistoreHREvent_0(
        HresultFromJetError,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        955);
      return HresultFromJetError;
    }
  }
  pcbActual = 0;
  pcbSecondaryKeyActual = 0;
  while ( 1 )
  {
    pvPrimaryBookmark = *(void **)(a1 + 8);
    cbPrimaryBookmarkMax = *(_QWORD *)(a1 + 16) - (_QWORD)pvPrimaryBookmark;
    if ( cbPrimaryBookmarkMax > 0xFFFFFFFF )
    {
      v26 = 969;
      goto LABEL_28;
    }
    v18 = *(void **)(a1 + 32);
    v19 = *(_QWORD *)(a1 + 40) - (_QWORD)v18;
    if ( v19 > 0xFFFFFFFF )
    {
      v26 = 972;
LABEL_28:
      Log_UnistoreHREvent_0(
        2147942934LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v26);
      return 2147942934LL;
    }
    if ( v7 )
    {
      Bookmark = JetGetBookmark(a4, tableid, pvPrimaryBookmark, cbPrimaryBookmarkMax, &pcbActual);
      v21 = Bookmark;
      if ( g_fInProc && !dword_18010D924 )
      {
        if ( Bookmark != -1414 )
        {
          v47 = Bookmark;
          if ( Bookmark >= 0 )
            goto LABEL_23;
          v53 = 152;
          v63 = 0;
          v54 = 0;
          v55 = 0;
          v56 = 0;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v60 = 0;
          v61 = 0;
          v62 = 0;
          if ( (int)JetGetErrorInfoW(&v47, &v53, 152, 1, 0) < 0 )
            goto LABEL_23;
          v34 = DWORD1(v54) - 10;
          if ( DWORD1(v54) != 10 )
            goto LABEL_47;
          if ( v47 == -1414 )
            goto LABEL_23;
        }
        v35 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v21);
        if ( v35 < 0 )
          goto LABEL_82;
        v46 = v21;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v46);
        if ( (unsigned int)IsJetCorruptionError(v21) )
          goto LABEL_45;
      }
    }
    else
    {
      SecondaryIndexBookmark = JetGetSecondaryIndexBookmark(
                                 a4,
                                 tableid,
                                 v18,
                                 v19,
                                 &pcbSecondaryKeyActual,
                                 pvPrimaryBookmark,
                                 cbPrimaryBookmarkMax,
                                 &pcbActual,
                                 0);
      v21 = SecondaryIndexBookmark;
      if ( g_fInProc && !dword_18010D924 )
      {
        if ( SecondaryIndexBookmark == -1414 )
          goto LABEL_43;
        v47 = SecondaryIndexBookmark;
        if ( SecondaryIndexBookmark < 0 )
        {
          v53 = 152;
          v63 = 0;
          v54 = 0;
          v55 = 0;
          v56 = 0;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v60 = 0;
          v61 = 0;
          v62 = 0;
          if ( (int)JetGetErrorInfoW(&v47, &v53, 152, 1, 0) >= 0 )
          {
            v34 = DWORD1(v54) - 10;
            if ( DWORD1(v54) == 10 )
            {
              if ( v47 == -1414 )
                goto LABEL_23;
LABEL_43:
              v35 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v21);
              if ( v35 >= 0 )
              {
                v46 = v21;
                UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v46);
                if ( !(unsigned int)IsJetCorruptionError(v21) )
                  goto LABEL_23;
LABEL_45:
                Log_AssertionEvent(
                  v36,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  109);
                __int2c();
                goto LABEL_23;
              }
LABEL_82:
              Log_UnistoreHREvent_0(
                (unsigned int)v35,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                102);
              goto LABEL_23;
            }
LABEL_47:
            v37 = v34 - 1;
            if ( v37 )
            {
              if ( v37 == 1 )
              {
                v46 = v47;
                UnistoreTelemetry::JetFragmentationError<unsigned long>(&v46);
              }
            }
            else
            {
              v46 = v47;
              UnistoreTelemetry::JetInconsistentError<unsigned long>(&v46);
            }
          }
        }
      }
    }
LABEL_23:
    if ( v21 != -1038 )
      break;
    v28 = *(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8);
    v29 = pcbActual;
    if ( v28 < pcbActual )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(a1 + 8, pcbActual) )
      {
        v32 = 1005;
        goto LABEL_85;
      }
      memset_0(*(void **)(a1 + 16), 0, (unsigned int)v29 - v28);
      *(_QWORD *)(a1 + 16) = v29 + *(_QWORD *)(a1 + 8);
    }
    v30 = *(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32);
    v31 = pcbSecondaryKeyActual;
    if ( v30 < pcbSecondaryKeyActual )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               a1 + 32,
                               pcbSecondaryKeyActual) )
      {
        v32 = 1010;
        goto LABEL_85;
      }
      memset_0(*(void **)(a1 + 40), 0, v31 - v30);
      *(_QWORD *)(a1 + 40) = v31 + *(_QWORD *)(a1 + 32);
    }
    v7 = v51;
  }
  if ( v21 < 0 )
  {
    v38 = MakeHresultFromJetError(v21);
    Log_UnistoreHREvent_0(
      v38,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      1020);
    return v38;
  }
  else
  {
    v22 = *(_QWORD *)(a1 + 8);
    v23 = pcbActual;
    v24 = *(_QWORD *)(a1 + 16) - v22;
    if ( pcbActual <= v24 )
    {
      v25 = v22 + pcbActual;
      goto LABEL_88;
    }
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(a1 + 8, pcbActual) )
    {
      v32 = 1023;
      goto LABEL_85;
    }
    memset_0(*(void **)(a1 + 16), 0, v23 - v24);
    v25 = v23 + *(_QWORD *)(a1 + 8);
LABEL_88:
    *(_QWORD *)(a1 + 16) = v25;
    v43 = *(_QWORD *)(a1 + 32);
    v44 = pcbSecondaryKeyActual;
    v45 = *(_QWORD *)(a1 + 40) - v43;
    if ( pcbSecondaryKeyActual <= v45 )
    {
LABEL_91:
      *(_QWORD *)(a1 + 40) = v44 + v43;
      *(_DWORD *)(a1 + 4) = pvData;
      result = 0;
      *(_DWORD *)a1 = 1;
    }
    else
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              a1 + 32,
                              pcbSecondaryKeyActual) )
      {
        memset_0(*(void **)(a1 + 40), 0, (unsigned int)v44 - v45);
        v43 = *(_QWORD *)(a1 + 32);
        goto LABEL_91;
      }
      v32 = 1024;
LABEL_85:
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v32);
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010690  mov     [rsp-8+arg_8], rbx
0x180010695  push    rbp
0x180010696  push    rsi
0x180010697  push    rdi
0x180010698  push    r12
0x18001069a  push    r13
0x18001069c  push    r14
0x18001069e  push    r15
0x1800106a0  lea     rbp, [rsp-30h]
0x1800106a5  sub     rsp, 130h
0x1800106ac  mov     rax, cs:__security_cookie
0x1800106b3  xor     rax, rsp
0x1800106b6  mov     [rbp+60h+var_40], rax
0x1800106ba  xor     r15d, r15d
0x1800106bd  mov     [rsp+160h+var_F4], r8d
0x1800106c2  xor     eax, eax
0x1800106c4  movsxd  rbx, edx
0x1800106c7  mov     [rcx], r15d
0x1800106ca  mov     r12, r9
0x1800106cd  mov     [rsp+160h+pvData], r15d
0x1800106d2  mov     r14d, r8d
0x1800106d5  mov     qword ptr [rsp+160h+columnid], rax
0x1800106da  mov     rsi, rcx
0x1800106dd  test    edx, edx
0x1800106df  jz      short loc_1800106EA
0x1800106e1  cmp     ebx, 35h ; '5'
0x1800106e4  jnz     loc_180010C41
0x1800106ea  mov     edi, 1060003h
0x1800106ef  lea     r13, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x1800106f6  mov     rcx, r13; SRWLock
0x1800106f9  call    cs:__imp_AcquireSRWLockShared
0x1800106ff  cmp     cs:dword_18010D248, r15d
0x180010706  jz      loc_180010C1A
0x18001070c  lea     rcx, [rbx+rbx*4]
0x180010710  lea     rdx, [r13+8]
0x180010714  mov     r9, [rdx+rcx*8+10h]
0x180010719  lea     rdx, [rdx+rcx*8]
0x18001071d  test    r9, r9
0x180010720  jz      loc_180010C1A
0x180010726  movzx   ecx, byte ptr [rdx+20h]
0x18001072a  mov     eax, 8
0x18001072f  shl     rax, cl
0x180010732  dec     rax
0x180010735  mov     r8d, edi
0x180010738  shr     r8, 10h
0x18001073c  and     rax, r8
0x18001073f  add     rax, rax
0x180010742  mov     rcx, [r9+rax*8]
0x180010746  test    rcx, rcx
0x180010749  jz      loc_180010C1A
0x18001074f  mov     rax, [r9+rax*8+8]
0x180010754  mov     r9, [rax]
0x180010757  cmp     rcx, r9
0x18001075a  jz      loc_180010C1A
0x180010760  cmp     [rcx+10h], r8
0x180010764  jb      short loc_180010775
0x180010766  ja      loc_180010C1A
0x18001076c  cmp     edi, [rcx+18h]
0x18001076f  jz      loc_180010C11
0x180010775  mov     rcx, [rcx]
0x180010778  jmp     short loc_180010757
0x18001077a  mov     ecx, ebx; int
0x18001077c  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180010781  mov     r9d, 304h
0x180010787  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001078e  xor     edx, edx
0x180010790  mov     ecx, eax
0x180010792  mov     ebx, eax
0x180010794  call    Log_UnistoreHREvent_0
0x180010799  test    ebx, ebx
0x18001079b  js      loc_180010CE2
0x1800107a1  mov     [rsp+160h+var_100], r15d
0x1800107a6  mov     [rsp+160h+pcbSecondaryKeyActual], r15d
0x1800107ab  mov     rcx, [rsi+8]
0x1800107af  mov     edx, 0FFFFFFFFh
0x1800107b4  mov     rax, [rsi+10h]
0x1800107b8  sub     rax, rcx
0x1800107bb  cmp     rax, rdx
0x1800107be  ja      loc_1800108F7
0x1800107c4  mov     r8, [rsi+20h]; pvSecondaryKey
0x1800107c8  mov     r9, [rsi+28h]
0x1800107cc  sub     r9, r8; cbSecondaryKeyMax
0x1800107cf  cmp     r9, rdx
0x1800107d2  ja      loc_1800108AF
0x1800107d8  lea     rdx, [rsp+160h+var_100]
0x1800107dd  test    r14d, r14d
0x1800107e0  jz      loc_180010978
0x1800107e6  mov     [rsp+160h+pcbActual], rdx; pcbActual
0x1800107eb  mov     r8, rcx; pvBookmark
0x1800107ee  mov     rdx, r13; tableid
0x1800107f1  mov     rcx, r12; sesid
0x1800107f4  mov     r9d, eax; cbMax
0x1800107f7  call    cs:__imp_JetGetBookmark
0x1800107fd  cmp     cs:?g_fInProc@@3HA, r15d; int g_fInProc
0x180010804  mov     ebx, eax
0x180010806  jz      short loc_18001087E
0x180010808  cmp     cs:dword_18010D924, r15d
0x18001080f  jnz     short loc_18001087E
0x180010811  cmp     eax, 0FFFFFA7Ah
0x180010816  jz      loc_180010D34
0x18001081c  mov     [rsp+160h+var_108], eax
0x180010820  test    eax, eax
0x180010822  jns     short loc_18001087E
0x180010824  xorps   xmm0, xmm0
0x180010827  mov     [rbp+60h+var_E0], 98h
0x18001082e  xor     eax, eax
0x180010830  lea     rdx, [rbp+60h+var_E0]
0x180010834  mov     r9d, 1
0x18001083a  mov     [rbp+60h+var_4C], eax
0x18001083d  mov     r8d, 98h
0x180010843  mov     dword ptr [rsp+160h+pcbActual], eax
0x180010847  lea     rcx, [rsp+160h+var_108]
0x18001084c  movups  [rbp+60h+var_DC], xmm0
0x180010850  movups  [rbp+60h+var_CC], xmm0
0x180010854  movups  [rbp+60h+var_BC], xmm0
0x180010858  movups  [rbp+60h+var_AC], xmm0
0x18001085c  movups  [rbp+60h+var_9C], xmm0
0x180010860  movups  [rbp+60h+var_8C], xmm0
0x180010864  movups  [rbp+60h+var_7C], xmm0
0x180010868  movups  [rbp+60h+var_6C], xmm0
0x18001086c  movups  [rbp+60h+var_5C], xmm0
0x180010870  call    cs:__imp_JetGetErrorInfoW
0x180010876  test    eax, eax
0x180010878  jns     loc_180010A9F
0x18001087e  cmp     ebx, 0FFFFFBF2h
0x180010884  jz      short loc_1800108FF
0x180010886  test    ebx, ebx
0x180010888  js      loc_180010AD4
0x18001088e  mov     rax, [rsi+8]
0x180010892  mov     r14, [rsi+10h]
0x180010896  mov     ebx, [rsp+160h+var_100]
0x18001089a  sub     r14, rax
0x18001089d  cmp     rbx, r14
0x1800108a0  ja      loc_180010DD2
0x1800108a6  lea     rcx, [rax+rbx]
0x1800108aa  jmp     loc_180010DFA
0x1800108af  mov     r9d, 3CCh
0x1800108b5  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800108bc  mov     edx, 1
0x1800108c1  mov     ecx, 80070216h
0x1800108c6  call    Log_UnistoreHREvent_0
0x1800108cb  mov     eax, 80070216h
0x1800108d0  mov     rcx, [rbp+60h+var_40]
0x1800108d4  xor     rcx, rsp; StackCookie
0x1800108d7  call    __security_check_cookie
0x1800108dc  mov     rbx, [rsp+160h+arg_8]
0x1800108e4  add     rsp, 130h
0x1800108eb  pop     r15
0x1800108ed  pop     r14
0x1800108ef  pop     r13
0x1800108f1  pop     r12
0x1800108f3  pop     rdi
0x1800108f4  pop     rsi
0x1800108f5  pop     rbp
0x1800108f6  retn
0x1800108f7  mov     r9d, 3C9h
0x1800108fd  jmp     short loc_1800108B5
0x1800108ff  mov     rbx, [rsi+10h]
0x180010903  sub     rbx, [rsi+8]
0x180010907  mov     r14d, [rsp+160h+var_100]
0x18001090c  cmp     rbx, r14
0x18001090f  jnb     short loc_180010941
0x180010911  mov     edx, r14d
0x180010914  lea     rcx, [rsi+8]
0x180010918  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18001091d  xor     edx, edx; Val
0x18001091f  test    al, al
0x180010921  jz      loc_180010DA9
0x180010927  mov     rcx, [rsi+10h]; void *
0x18001092b  mov     r8d, r14d
0x18001092e  sub     r8, rbx; Size
0x180010931  call    memset_0
0x180010936  mov     rcx, [rsi+8]
0x18001093a  add     rcx, r14
0x18001093d  mov     [rsi+10h], rcx
0x180010941  mov     rbx, [rsi+28h]
0x180010945  sub     rbx, [rsi+20h]
0x180010949  mov     r14d, [rsp+160h+pcbSecondaryKeyActual]
0x18001094e  cmp     rbx, r14
0x180010951  jnb     loc_180010D1C
0x180010957  mov     edx, r14d
0x18001095a  lea     rcx, [rsi+20h]
0x18001095e  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180010963  xor     edx, edx; Val
0x180010965  test    al, al
0x180010967  jnz     loc_180010D02
0x18001096d  mov     r9d, 3F2h
0x180010973  jmp     loc_180010DB7
0x180010978  xor     r14d, r14d
0x18001097b  mov     [rsp+160h+grbit], r14d; grbit
0x180010980  mov     [rsp+160h+pcbPrimaryBookmarkActual], rdx; pcbPrimaryBookmarkActual
0x180010985  mov     rdx, r13; tableid
0x180010988  mov     [rsp+160h+cbPrimaryBookmarkMax], eax; cbPrimaryBookmarkMax
0x18001098c  lea     rax, [rsp+160h+pcbSecondaryKeyActual]
0x180010991  mov     [rsp+160h+pvPrimaryBookmark], rcx; pvPrimaryBookmark
0x180010996  mov     rcx, r12; sesid
0x180010999  mov     [rsp+160h+pcbActual], rax; pcbSecondaryKeyActual
0x18001099e  call    cs:__imp_JetGetSecondaryIndexBookmark
0x1800109a4  cmp     cs:?g_fInProc@@3HA, r14d; int g_fInProc
0x1800109ab  mov     ebx, eax
0x1800109ad  jz      loc_18001087E
0x1800109b3  cmp     cs:dword_18010D924, r14d
0x1800109ba  jnz     loc_18001087E
0x1800109c0  cmp     eax, 0FFFFFA7Ah
0x1800109c5  jz      short loc_180010A44
0x1800109c7  mov     [rsp+160h+var_108], eax
0x1800109cb  test    eax, eax
0x1800109cd  jns     loc_18001087E
0x1800109d3  xorps   xmm0, xmm0
0x1800109d6  mov     [rbp+60h+var_E0], 98h
0x1800109dd  xor     eax, eax
0x1800109df  mov     dword ptr [rsp+160h+pcbActual], r14d
0x1800109e4  mov     r9d, 1
0x1800109ea  mov     [rbp+60h+var_4C], eax
0x1800109ed  mov     r8d, 98h
0x1800109f3  lea     rdx, [rbp+60h+var_E0]
0x1800109f7  lea     rcx, [rsp+160h+var_108]
0x1800109fc  movups  [rbp+60h+var_DC], xmm0
0x180010a00  movups  [rbp+60h+var_CC], xmm0
0x180010a04  movups  [rbp+60h+var_BC], xmm0
0x180010a08  movups  [rbp+60h+var_AC], xmm0
0x180010a0c  movups  [rbp+60h+var_9C], xmm0
0x180010a10  movups  [rbp+60h+var_8C], xmm0
0x180010a14  movups  [rbp+60h+var_7C], xmm0
0x180010a18  movups  [rbp+60h+var_6C], xmm0
0x180010a1c  movups  [rbp+60h+var_5C], xmm0
0x180010a20  call    cs:__imp_JetGetErrorInfoW
0x180010a26  test    eax, eax
0x180010a28  js      loc_18001087E
0x180010a2e  mov     ecx, dword ptr [rbp+60h+var_DC+4]
0x180010a31  sub     ecx, 0Ah
0x180010a34  jnz     short loc_180010AAB
0x180010a36  cmp     [rsp+160h+var_108], 0FFFFFA7Ah
0x180010a3e  jz      loc_18001087E
0x180010a44  mov     r9d, ebx; unsigned int
0x180010a47  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x180010a4e  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x180010a55  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180010a5c  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180010a61  test    eax, eax
0x180010a63  js      loc_180010D8E
0x180010a69  lea     rcx, [rsp+160h+var_110]
0x180010a6e  mov     [rsp+160h+var_110], ebx
0x180010a72  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x180010a77  mov     ecx, ebx; int
0x180010a79  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x180010a7e  test    eax, eax
0x180010a80  jz      loc_18001087E
0x180010a86  mov     r8d, 6Dh ; 'm'
0x180010a8c  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010a93  call    Log_AssertionEvent
0x180010a98  int     2Ch; Windows NT - assertion failure
0x180010a9a  jmp     loc_18001087E
0x180010a9f  mov     ecx, dword ptr [rbp+60h+var_DC+4]
0x180010aa2  sub     ecx, 0Ah
0x180010aa5  jz      loc_180010D26
0x180010aab  sub     ecx, 1
0x180010aae  jz      loc_180010D77
0x180010ab4  cmp     ecx, 1
0x180010ab7  jnz     loc_18001087E
0x180010abd  mov     eax, [rsp+160h+var_108]
0x180010ac1  lea     rcx, [rsp+160h+var_110]
0x180010ac6  mov     [rsp+160h+var_110], eax
0x180010aca  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x180010acf  jmp     loc_18001087E
0x180010ad4  mov     ecx, ebx; int
0x180010ad6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180010adb  mov     r9d, 3FCh
0x180010ae1  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010ae8  xor     edx, edx
0x180010aea  mov     ecx, eax
0x180010aec  mov     ebx, eax
0x180010aee  call    Log_UnistoreHREvent_0
0x180010af3  mov     eax, ebx
0x180010af5  jmp     loc_1800108D0
0x180010afa  movsd   xmm0, qword ptr [rcx+1Ch]
0x180010aff  mov     rcx, r13; SRWLock
0x180010b02  movsd   qword ptr [rsp+160h+columnid], xmm0
0x180010b08  call    cs:__imp_ReleaseSRWLockShared
0x180010b0e  mov     r13, [rbp+60h+tableid]
0x180010b15  lea     r9, [rsp+160h+pvData]; pvData
0x180010b1a  mov     r8d, [rsp+160h+columnid]; columnid
0x180010b1f  mov     eax, 0FFFFFFFFh
0x180010b24  mov     [rsp+160h+pcbPrimaryBookmarkActual], r15; pretinfo
0x180010b29  mov     rdx, r13; tableid
0x180010b2c  mov     [rsp+160h+cbPrimaryBookmarkMax], 4; grbit
0x180010b34  mov     rcx, r12; sesid
0x180010b37  mov     [rsp+160h+pvPrimaryBookmark], r15; pcbActual
0x180010b3c  mov     dword ptr [rsp+160h+pcbActual], 4; cbData
0x180010b44  mov     [rsp+160h+pvData], eax
0x180010b48  call    cs:__imp_JetRetrieveColumn
0x180010b4e  cmp     cs:?g_fInProc@@3HA, r15d; int g_fInProc
0x180010b55  mov     ebx, eax
0x180010b57  jz      short loc_180010BCC
0x180010b59  cmp     cs:dword_18010D924, r15d
0x180010b60  jnz     short loc_180010BCC
0x180010b62  cmp     eax, 0FFFFFA7Ah
0x180010b67  jz      loc_180010C70
0x180010b6d  mov     [rsp+160h+var_108], eax
0x180010b71  test    eax, eax
  ... truncated ...
```
