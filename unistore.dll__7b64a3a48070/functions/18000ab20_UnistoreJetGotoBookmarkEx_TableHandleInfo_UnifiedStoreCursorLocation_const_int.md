# UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)

- ea: `0x18000ab20`
- end: `0x18000b346`
- name: `?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z`
- size: `2086`
- prototype: `__int64 __fastcall(struct TableHandleInfo *, const struct UnifiedStoreCursorLocation *, int *)`
- caller_count: `12`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008af0`
- `0x180009a50`
- `0x180009b40`
- `0x18000d9d0`
- `0x180010030`
- `0x1800111d0`
- `0x18001d4a0`
- `0x18002b4b0`
- `0x1800327f0`
- `0x18004dd50`
- `0x1800556c8`
- `0x18007f780`

## callees

- `0x1800068f0`
- `0x18000ab20`
- `0x18000f530`
- `0x180011ed0`
- `0x180045990`
- `0x18004bd20`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c5086`
- `0x1800c5092`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetGotoBookmark` at `0x18000ad85`
- `ESENT!JetGotoBookmark` at `0x18000ad85`
- `ESENT!JetGotoSecondaryIndexBookmark` at `0x18000afce`
- `ESENT!JetGotoSecondaryIndexBookmark` at `0x18000afce`
- `ESENT!JetGetErrorInfoW` at `0x18000ae12`
- `ESENT!JetGetErrorInfoW` at `0x18000ae12`

## string_xrefs

- `0x18000b216`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000b250`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000acab`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000ae40`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000af7c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b329`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000aba5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000abcd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ac08`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ac28`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ac63`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ad0a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ad6a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ae5d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ae74`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000ae8b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000aea2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000aec4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000af1f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000af93`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000b03f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000b056`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000b197`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18000b312`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`

## pseudocode

```c
__int64 __fastcall UnistoreJetGotoBookmarkEx(
        struct TableHandleInfo *a1,
        const struct UnifiedStoreCursorLocation *a2,
        int *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rsi
  size_t v8; // rsi
  const void *v9; // r15
  size_t v10; // rsi
  const void *v11; // r15
  __int64 v13; // r9
  unsigned __int64 cbPrimaryBookmark; // r15
  unsigned __int64 v15; // r12
  __int64 v16; // rcx
  JET_ERR v17; // eax
  int v18; // esi
  int v19; // r14d
  unsigned int HresultFromJetError; // eax
  unsigned int v21; // ebx
  __int64 v22; // r9
  __int64 v23; // rax
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // r12
  unsigned __int64 v26; // rcx
  void *pvPrimaryBookmark; // r13
  JET_ERR v28; // r15d
  __int64 v29; // rcx
  unsigned __int64 v30; // r12
  unsigned __int64 v31; // rax
  unsigned int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  unsigned __int64 v35; // r13
  unsigned __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // r9
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // r15
  unsigned __int64 v43; // r12
  __int64 v44; // r9
  JET_ERR v45; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v48; // [rsp+54h] [rbp-ACh]
  __int128 v49; // [rsp+64h] [rbp-9Ch]
  __int128 v50; // [rsp+74h] [rbp-8Ch]
  __int128 v51; // [rsp+84h] [rbp-7Ch]
  __int128 v52; // [rsp+94h] [rbp-6Ch]
  __int128 v53; // [rsp+A4h] [rbp-5Ch]
  __int128 v54; // [rsp+B4h] [rbp-4Ch]
  __int128 v55; // [rsp+C4h] [rbp-3Ch]
  __int128 v56; // [rsp+D4h] [rbp-2Ch]
  int v57; // [rsp+E4h] [rbp-1Ch]

  if ( a3 )
    *a3 = 0;
  if ( !*(_DWORD *)a2 )
    return 2147942425LL;
  if ( *((_DWORD *)a1 + 6) && *((_DWORD *)a2 + 1) == *((_DWORD *)a1 + 7) )
  {
    v6 = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
    if ( !*((_DWORD *)a1 + 6) )
      Log_AssertionEvent(
        a1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
        371);
    if ( v6 == *((_QWORD *)a1 + 5) - *((_QWORD *)a1 + 4) )
    {
      if ( !*(_DWORD *)a2 )
        Log_AssertionEvent(
          a1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
          350);
      v7 = *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4);
      if ( !*((_DWORD *)a1 + 6) )
        Log_AssertionEvent(
          a1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
          350);
      if ( v7 == *((_QWORD *)a1 + 8) - *((_QWORD *)a1 + 7) )
      {
        if ( !*((_DWORD *)a1 + 6) )
          Log_AssertionEvent(
            a1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            371);
        v8 = *((_QWORD *)a1 + 5) - *((_QWORD *)a1 + 4);
        if ( !*((_DWORD *)a1 + 6) )
          Log_AssertionEvent(
            a1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            357);
        v9 = (const void *)*((_QWORD *)a1 + 4);
        if ( !*(_DWORD *)a2 )
          Log_AssertionEvent(
            a1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            364);
        if ( !memcmp_0(*((const void **)a2 + 1), v9, v8) )
        {
          if ( !*((_DWORD *)a1 + 6) )
            Log_AssertionEvent(
              a1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
              350);
          v10 = *((_QWORD *)a1 + 8) - *((_QWORD *)a1 + 7);
          if ( !*((_DWORD *)a1 + 6) )
            Log_AssertionEvent(
              a1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
              336);
          v11 = (const void *)*((_QWORD *)a1 + 7);
          if ( !*(_DWORD *)a2 )
            Log_AssertionEvent(
              a1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
              343);
          if ( !memcmp_0(*((const void **)a2 + 4), v11, v10) )
            return 0;
        }
      }
    }
  }
  if ( !*(_DWORD *)a2 )
    Log_AssertionEvent(a1, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 371);
  cbPrimaryBookmark = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
  if ( cbPrimaryBookmark > 0xFFFFFFFF )
  {
    v13 = 880;
LABEL_30:
    Log_UnistoreHREvent_0(
      2147942934LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v13);
    return 2147942934LL;
  }
  if ( !*(_DWORD *)a2 )
    Log_AssertionEvent(a1, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 350);
  v15 = *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4);
  if ( v15 > 0xFFFFFFFF )
  {
    v13 = 883;
    goto LABEL_30;
  }
  if ( !*(_DWORD *)a2 )
    Log_AssertionEvent(a1, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 350);
  v16 = *(unsigned int *)a2;
  if ( *((_QWORD *)a2 + 5) == *((_QWORD *)a2 + 4) )
  {
    if ( !(_DWORD)v16 )
      Log_AssertionEvent(
        v16,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
        364);
    v17 = JetGotoBookmark(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), *((void **)a2 + 1), cbPrimaryBookmark);
    v18 = 1;
    v19 = v17;
    if ( g_fInProc && !dword_18010D924 )
    {
      if ( v17 != -1414 )
      {
        v45 = v17;
        if ( v17 >= 0 )
          goto LABEL_54;
        v47 = 152;
        v57 = 0;
        v48 = 0;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        if ( (int)JetGetErrorInfoW(&v45, &v47, 152, 1, 0) < 0 )
          goto LABEL_47;
        if ( DWORD1(v48) != 10 )
        {
          if ( DWORD1(v48) == 11 )
          {
            LODWORD(v46) = v45;
            UnistoreTelemetry::JetInconsistentError<unsigned long>(&v46);
          }
          else if ( DWORD1(v48) == 12 )
          {
            LODWORD(v46) = v45;
            UnistoreTelemetry::JetFragmentationError<unsigned long>(&v46);
          }
          goto LABEL_47;
        }
        if ( v45 == -1414 )
        {
LABEL_47:
          HresultFromJetError = MakeHresultFromJetError(v19);
          v21 = HresultFromJetError;
          if ( v19 == -2147024871 || HresultFromJetError == -2147024871 )
            return v21;
          v22 = 928;
LABEL_50:
          Log_UnistoreHREvent_0(
            v21,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            v22);
          return v21;
        }
      }
      v39 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v19);
      if ( v39 >= 0 )
      {
        LODWORD(v46) = v19;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v46);
        if ( (unsigned int)IsJetCorruptionError(v19) )
        {
          Log_AssertionEvent(
            v40,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            109);
          __int2c();
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v39,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          102);
      }
    }
    if ( v19 >= 0 )
    {
LABEL_54:
      if ( !*(_DWORD *)a2 )
      {
        *((_DWORD *)a1 + 7) = -1;
        v18 = 0;
LABEL_74:
        *((_DWORD *)a1 + 6) = v18;
        return 0;
      }
      *((_DWORD *)a1 + 6) = 0;
      *((_DWORD *)a1 + 7) = *((_DWORD *)a2 + 1);
      v23 = *((_QWORD *)a1 + 4);
      v24 = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
      v25 = *((_QWORD *)a1 + 5) - v23;
      if ( v24 > v25 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                 (char *)a1 + 32,
                                 *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1)) )
        {
          v44 = 399;
LABEL_110:
          Log_UnistoreHREvent_0(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            v44);
          v38 = 931;
          goto LABEL_111;
        }
        memset_0(*((void **)a1 + 5), 0, v24 - v25);
        v26 = v24 + *((_QWORD *)a1 + 4);
      }
      else
      {
        v26 = v24 + v23;
      }
      *((_QWORD *)a1 + 5) = v26;
      memcpy_0(*((void **)a1 + 4), *((const void **)a2 + 1), *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1));
      v41 = *((_QWORD *)a1 + 7);
      v42 = *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4);
      v43 = *((_QWORD *)a1 + 8) - v41;
      if ( v42 <= v43 )
      {
LABEL_107:
        *((_QWORD *)a1 + 8) = v42 + v41;
        memcpy_0(*((void **)a1 + 7), *((const void **)a2 + 4), *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4));
        goto LABEL_74;
      }
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)a1 + 56,
                              *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4)) )
      {
        memset_0(*((void **)a1 + 8), 0, v42 - v43);
        v41 = *((_QWORD *)a1 + 7);
        goto LABEL_107;
      }
      v44 = 404;
      goto LABEL_110;
    }
    goto LABEL_47;
  }
  if ( !(_DWORD)v16 )
    Log_AssertionEvent(v16, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 371);
  if ( *((_QWORD *)a2 + 2) == *((_QWORD *)a2 + 1) )
    Log_AssertionEvent(
      v16,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      889);
  if ( !*(_DWORD *)a2 )
    Log_AssertionEvent(v16, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 364);
  pvPrimaryBookmark = (void *)*((_QWORD *)a2 + 1);
  if ( !*(_DWORD *)a2 )
    Log_AssertionEvent(v16, "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h", 343);
  v28 = JetGotoSecondaryIndexBookmark(
          *((_QWORD *)a1 + 1),
          *((_QWORD *)a1 + 2),
          *((void **)a2 + 4),
          v15,
          pvPrimaryBookmark,
          cbPrimaryBookmark,
          1u);
  CheckCorruption(v28);
  if ( (int)(v28 + 0x80000000) >= 0 && v28 != -1017 )
  {
LABEL_76:
    v32 = MakeHresultFromJetError(v28);
    v21 = v32;
    if ( v28 == -2147024871 || v32 == -2147024871 )
      return v21;
    v22 = 918;
    goto LABEL_50;
  }
  if ( !*(_DWORD *)a2 )
  {
    *((_DWORD *)a1 + 7) = -1;
    v33 = 0;
    goto LABEL_80;
  }
  *((_DWORD *)a1 + 6) = 0;
  *((_DWORD *)a1 + 7) = *((_DWORD *)a2 + 1);
  v29 = *((_QWORD *)a1 + 4);
  v30 = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
  v46 = *((_QWORD *)a1 + 5) - v29;
  if ( v30 > v46 )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve((char *)a1 + 32, v30) )
    {
      v37 = 399;
      goto LABEL_93;
    }
    memset_0(*((void **)a1 + 5), 0, v30 - v46);
    v31 = v30 + *((_QWORD *)a1 + 4);
  }
  else
  {
    v31 = v30 + v29;
  }
  *((_QWORD *)a1 + 5) = v31;
  memcpy_0(*((void **)a1 + 4), *((const void **)a2 + 1), *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1));
  v34 = *((_QWORD *)a1 + 7);
  v35 = *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4);
  v46 = *((_QWORD *)a1 + 8) - v34;
  if ( v35 <= v46 )
  {
    v36 = v34 + v35;
LABEL_90:
    *((_QWORD *)a1 + 8) = v36;
    memcpy_0(*((void **)a1 + 7), *((const void **)a2 + 4), *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4));
    v33 = 1;
LABEL_80:
    *((_DWORD *)a1 + 6) = v33;
    if ( a3 && v28 == -1017 )
    {
      *a3 = 1;
      return 0;
    }
    if ( v28 >= 0 )
      return 0;
    goto LABEL_76;
  }
  if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve((char *)a1 + 56, v35) )
  {
    memset_0(*((void **)a1 + 8), 0, v35 - v46);
    v36 = v35 + *((_QWORD *)a1 + 7);
    goto LABEL_90;
  }
  v37 = 404;
LABEL_93:
  Log_UnistoreHREvent_0(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
    v37);
  v38 = 906;
LABEL_111:
  Log_UnistoreHREvent_0(
    2147942414LL,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    v38);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000ab20  push    rbp
0x18000ab22  push    rbx
0x18000ab23  push    rdi
0x18000ab24  push    r14
0x18000ab26  lea     rbp, [rsp-18h]
0x18000ab2b  sub     rsp, 118h
0x18000ab32  mov     rax, cs:__security_cookie
0x18000ab39  xor     rax, rsp
0x18000ab3c  mov     [rbp+30h+var_40], rax
0x18000ab40  mov     r14, r8
0x18000ab43  mov     rbx, rdx
0x18000ab46  mov     rdi, rcx
0x18000ab49  test    r8, r8
0x18000ab4c  jnz     loc_18000B0C1
0x18000ab52  cmp     dword ptr [rdx], 0
0x18000ab55  jz      loc_18000B0CD
0x18000ab5b  cmp     dword ptr [rcx+18h], 0
0x18000ab5f  mov     [rsp+130h+arg_18], rsi
0x18000ab67  mov     [rsp+130h+var_20], r12
0x18000ab6f  mov     [rsp+130h+var_28], r13
0x18000ab77  mov     [rsp+130h+var_30], r15
0x18000ab7f  jz      loc_18000ACFF
0x18000ab85  mov     eax, [rcx+1Ch]
0x18000ab88  cmp     [rdx+4], eax
0x18000ab8b  jnz     loc_18000ACFF
0x18000ab91  mov     rsi, [rdx+10h]
0x18000ab95  sub     rsi, [rdx+8]
0x18000ab99  cmp     dword ptr [rcx+18h], 0
0x18000ab9d  jnz     short loc_18000ABB1
0x18000ab9f  mov     r8d, 173h
0x18000aba5  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000abac  call    Log_AssertionEvent
0x18000abb1  mov     rax, [rdi+28h]
0x18000abb5  sub     rax, [rdi+20h]
0x18000abb9  cmp     rsi, rax
0x18000abbc  jnz     loc_18000ACFF
0x18000abc2  cmp     dword ptr [rbx], 0
0x18000abc5  jnz     short loc_18000ABD9
0x18000abc7  mov     r8d, 15Eh
0x18000abcd  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000abd4  call    Log_AssertionEvent
0x18000abd9  mov     rsi, [rbx+28h]
0x18000abdd  sub     rsi, [rbx+20h]
0x18000abe1  cmp     dword ptr [rdi+18h], 0
0x18000abe5  jz      loc_18000AE57
0x18000abeb  mov     rax, [rdi+40h]
0x18000abef  sub     rax, [rdi+38h]
0x18000abf3  cmp     rsi, rax
0x18000abf6  jnz     loc_18000ACFF
0x18000abfc  cmp     dword ptr [rdi+18h], 0
0x18000ac00  jnz     short loc_18000AC14
0x18000ac02  mov     r8d, 173h
0x18000ac08  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ac0f  call    Log_AssertionEvent
0x18000ac14  mov     rsi, [rdi+28h]
0x18000ac18  sub     rsi, [rdi+20h]
0x18000ac1c  cmp     dword ptr [rdi+18h], 0
0x18000ac20  jnz     short loc_18000AC34
0x18000ac22  mov     r8d, 165h
0x18000ac28  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ac2f  call    Log_AssertionEvent
0x18000ac34  cmp     dword ptr [rbx], 0
0x18000ac37  mov     r15, [rdi+20h]
0x18000ac3b  jz      loc_18000AE85
0x18000ac41  mov     rcx, [rbx+8]; Buf1
0x18000ac45  mov     r8, rsi; Size
0x18000ac48  mov     rdx, r15; Buf2
0x18000ac4b  call    memcmp_0
0x18000ac50  test    eax, eax
0x18000ac52  jnz     loc_18000ACFF
0x18000ac58  cmp     [rdi+18h], eax
0x18000ac5b  jnz     short loc_18000AC6F
0x18000ac5d  mov     r8d, 15Eh
0x18000ac63  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ac6a  call    Log_AssertionEvent
0x18000ac6f  mov     rsi, [rdi+40h]
0x18000ac73  sub     rsi, [rdi+38h]
0x18000ac77  cmp     dword ptr [rdi+18h], 0
0x18000ac7b  jz      loc_18000AE6E
0x18000ac81  cmp     dword ptr [rbx], 0
0x18000ac84  mov     r15, [rdi+38h]
0x18000ac88  jz      loc_18000AE9C
0x18000ac8e  mov     rcx, [rbx+20h]; Buf1
0x18000ac92  mov     r8, rsi; Size
0x18000ac95  mov     rdx, r15; Buf2
0x18000ac98  call    memcmp_0
0x18000ac9d  test    eax, eax
0x18000ac9f  jnz     short loc_18000ACFF
0x18000aca1  xor     eax, eax
0x18000aca3  jmp     short loc_18000ACC6
0x18000aca5  mov     r9d, 370h
0x18000acab  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000acb2  mov     edx, 1
0x18000acb7  mov     ecx, 80070216h
0x18000acbc  call    Log_UnistoreHREvent_0
0x18000acc1  mov     eax, 80070216h
0x18000acc6  mov     r13, [rsp+130h+var_28]
0x18000acce  mov     r12, [rsp+130h+var_20]
0x18000acd6  mov     rsi, [rsp+130h+arg_18]
0x18000acde  mov     r15, [rsp+130h+var_30]
0x18000ace6  mov     rcx, [rbp+30h+var_40]
0x18000acea  xor     rcx, rsp; StackCookie
0x18000aced  call    __security_check_cookie
0x18000acf2  add     rsp, 118h
0x18000acf9  pop     r14
0x18000acfb  pop     rdi
0x18000acfc  pop     rbx
0x18000acfd  pop     rbp
0x18000acfe  retn
0x18000acff  cmp     dword ptr [rbx], 0
0x18000ad02  jnz     short loc_18000AD16
0x18000ad04  mov     r8d, 173h
0x18000ad0a  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ad11  call    Log_AssertionEvent
0x18000ad16  mov     r15, [rbx+10h]
0x18000ad1a  mov     r13d, 0FFFFFFFFh
0x18000ad20  sub     r15, [rbx+8]
0x18000ad24  cmp     r15, r13
0x18000ad27  ja      loc_18000ACA5
0x18000ad2d  cmp     dword ptr [rbx], 0
0x18000ad30  jz      loc_18000AEBE
0x18000ad36  mov     r12, [rbx+28h]
0x18000ad3a  sub     r12, [rbx+20h]
0x18000ad3e  cmp     r12, r13
0x18000ad41  ja      loc_18000AEB3
0x18000ad47  cmp     dword ptr [rbx], 0
0x18000ad4a  jz      loc_18000AF19
0x18000ad50  mov     rax, [rbx+28h]
0x18000ad54  mov     ecx, [rbx]
0x18000ad56  cmp     rax, [rbx+20h]
0x18000ad5a  jnz     loc_18000AF64
0x18000ad60  test    ecx, ecx
0x18000ad62  jnz     short loc_18000AD76
0x18000ad64  mov     r8d, 16Ch
0x18000ad6a  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ad71  call    Log_AssertionEvent
0x18000ad76  mov     r8, [rbx+8]; pvBookmark
0x18000ad7a  mov     r9d, r15d; cbBookmark
0x18000ad7d  mov     rdx, [rdi+10h]; tableid
0x18000ad81  mov     rcx, [rdi+8]; sesid
0x18000ad85  call    cs:__imp_JetGotoBookmark
0x18000ad8b  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x18000ad92  mov     esi, 1
0x18000ad97  mov     r14d, eax
0x18000ad9a  jz      loc_18000AED5
0x18000ada0  cmp     cs:dword_18010D924, 0
0x18000ada7  jnz     loc_18000AED5
0x18000adad  cmp     eax, 0FFFFFA7Ah
0x18000adb2  jz      loc_18000B1EF
0x18000adb8  mov     [rsp+130h+var_F0], eax
0x18000adbc  test    eax, eax
0x18000adbe  jns     loc_18000AEDE
0x18000adc4  xorps   xmm0, xmm0
0x18000adc7  mov     [rsp+130h+var_E0], 98h
0x18000adcf  xor     eax, eax
0x18000add1  lea     rdx, [rsp+130h+var_E0]
0x18000add6  mov     r9d, esi
0x18000add9  mov     [rbp+30h+var_4C], eax
0x18000addc  mov     r8d, 98h
0x18000ade2  mov     dword ptr [rsp+130h+pvPrimaryBookmark], eax
0x18000ade6  lea     rcx, [rsp+130h+var_F0]
0x18000adeb  movups  [rsp+130h+var_DC], xmm0
0x18000adf0  movups  [rsp+130h+var_CC], xmm0
0x18000adf5  movups  [rsp+130h+var_BC], xmm0
0x18000adfa  movups  [rbp+30h+var_AC], xmm0
0x18000adfe  movups  [rbp+30h+var_9C], xmm0
0x18000ae02  movups  [rbp+30h+var_8C], xmm0
0x18000ae06  movups  [rbp+30h+var_7C], xmm0
0x18000ae0a  movups  [rbp+30h+var_6C], xmm0
0x18000ae0e  movups  [rbp+30h+var_5C], xmm0
0x18000ae12  call    cs:__imp_JetGetErrorInfoW
0x18000ae18  test    eax, eax
0x18000ae1a  jns     loc_18000AF30
0x18000ae20  mov     ecx, r14d; int
0x18000ae23  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000ae28  mov     ebx, eax
0x18000ae2a  cmp     r14d, 80070019h
0x18000ae31  jz      short loc_18000AE50
0x18000ae33  cmp     eax, 80070019h
0x18000ae38  jz      short loc_18000AE50
0x18000ae3a  mov     r9d, 3A0h
0x18000ae40  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ae47  xor     edx, edx
0x18000ae49  mov     ecx, ebx
0x18000ae4b  call    Log_UnistoreHREvent_0
0x18000ae50  mov     eax, ebx
0x18000ae52  jmp     loc_18000ACC6
0x18000ae57  mov     r8d, 15Eh
0x18000ae5d  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ae64  call    Log_AssertionEvent
0x18000ae69  jmp     loc_18000ABEB
0x18000ae6e  mov     r8d, 150h
0x18000ae74  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ae7b  call    Log_AssertionEvent
0x18000ae80  jmp     loc_18000AC81
0x18000ae85  mov     r8d, 16Ch
0x18000ae8b  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ae92  call    Log_AssertionEvent
0x18000ae97  jmp     loc_18000AC41
0x18000ae9c  mov     r8d, 157h
0x18000aea2  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000aea9  call    Log_AssertionEvent
0x18000aeae  jmp     loc_18000AC8E
0x18000aeb3  mov     r9d, 373h
0x18000aeb9  jmp     loc_18000ACAB
0x18000aebe  mov     r8d, 15Eh
0x18000aec4  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000aecb  call    Log_AssertionEvent
0x18000aed0  jmp     loc_18000AD36
0x18000aed5  test    r14d, r14d
0x18000aed8  js      loc_18000AE20
0x18000aede  cmp     dword ptr [rbx], 0
0x18000aee1  jz      loc_18000B02B
0x18000aee7  mov     dword ptr [rdi+18h], 0
0x18000aeee  mov     eax, [rbx+4]
0x18000aef1  mov     [rdi+1Ch], eax
0x18000aef4  mov     r14, [rbx+10h]
0x18000aef8  mov     rax, [rdi+20h]
0x18000aefc  mov     r12, [rdi+28h]
0x18000af00  sub     r14, [rbx+8]
0x18000af04  sub     r12, rax
0x18000af07  cmp     r14, r12
0x18000af0a  ja      loc_18000B263
0x18000af10  lea     rcx, [r14+rax]
0x18000af14  jmp     loc_18000B28F
0x18000af19  mov     r8d, 15Eh
0x18000af1f  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000af26  call    Log_AssertionEvent
0x18000af2b  jmp     loc_18000AD50
0x18000af30  mov     ecx, dword ptr [rsp+130h+var_DC+4]
0x18000af34  sub     ecx, 0Ah
0x18000af37  jz      loc_18000B1E1
0x18000af3d  sub     ecx, esi
0x18000af3f  jz      loc_18000B1CA
0x18000af45  cmp     ecx, esi
0x18000af47  jnz     loc_18000AE20
0x18000af4d  mov     eax, [rsp+130h+var_F0]
0x18000af51  lea     rcx, [rsp+130h+var_E8]
0x18000af56  mov     dword ptr [rsp+130h+var_E8], eax
0x18000af5a  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000af5f  jmp     loc_18000AE20
0x18000af64  test    ecx, ecx
0x18000af66  jz      loc_18000B039
0x18000af6c  mov     rax, [rbx+10h]
0x18000af70  cmp     rax, [rbx+8]
0x18000af74  jnz     short loc_18000AF88
0x18000af76  mov     r8d, 379h
0x18000af7c  lea     rdx, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000af83  call    Log_AssertionEvent
0x18000af88  cmp     dword ptr [rbx], 0
0x18000af8b  jnz     short loc_18000AF9F
0x18000af8d  mov     r8d, 16Ch
0x18000af93  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000af9a  call    Log_AssertionEvent
0x18000af9f  cmp     dword ptr [rbx], 0
0x18000afa2  mov     r13, [rbx+8]
0x18000afa6  jz      loc_18000B050
0x18000afac  mov     r8, [rbx+20h]; pvSecondaryKey
0x18000afb0  mov     esi, 1
0x18000afb5  mov     rdx, [rdi+10h]; tableid
0x18000afb9  mov     r9d, r12d; cbSecondaryKey
0x18000afbc  mov     rcx, [rdi+8]; sesid
0x18000afc0  mov     [rsp+130h+grbit], esi; grbit
0x18000afc4  mov     [rsp+130h+cbPrimaryBookmark], r15d; cbPrimaryBookmark
0x18000afc9  mov     [rsp+130h+pvPrimaryBookmark], r13; pvPrimaryBookmark
0x18000afce  call    cs:__imp_JetGotoSecondaryIndexBookmark
0x18000afd4  mov     ecx, eax; int
0x18000afd6  mov     r15d, eax
0x18000afd9  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18000afde  mov     eax, 80000000h
0x18000afe3  lea     ecx, [r15+rax]
0x18000afe7  test    eax, ecx
0x18000afe9  jz      short loc_18000B067
0x18000afeb  cmp     dword ptr [rbx], 0
0x18000afee  jz      loc_18000B0A1
0x18000aff4  mov     dword ptr [rdi+18h], 0
0x18000affb  mov     eax, [rbx+4]
0x18000affe  mov     [rdi+1Ch], eax
0x18000b001  mov     r12, [rbx+10h]
0x18000b005  mov     rcx, [rdi+20h]
0x18000b009  mov     rax, [rdi+28h]
0x18000b00d  sub     r12, [rbx+8]
0x18000b011  sub     rax, rcx
0x18000b014  mov     [rsp+130h+var_E8], rax
0x18000b019  cmp     r12, rax
0x18000b01c  ja      loc_18000B0D7
0x18000b022  lea     rax, [r12+rcx]
0x18000b026  jmp     loc_18000B105
0x18000b02b  mov     [rdi+1Ch], r13d
0x18000b02f  xor     esi, esi
0x18000b031  mov     [rdi+18h], esi
0x18000b034  jmp     loc_18000ACA1
0x18000b039  mov     r8d, 173h
0x18000b03f  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b046  call    Log_AssertionEvent
0x18000b04b  jmp     loc_18000AF6C
0x18000b050  mov     r8d, 157h
0x18000b056  lea     rdx, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b05d  call    Log_AssertionEvent
0x18000b062  jmp     loc_18000AFAC
  ... truncated ...
```
