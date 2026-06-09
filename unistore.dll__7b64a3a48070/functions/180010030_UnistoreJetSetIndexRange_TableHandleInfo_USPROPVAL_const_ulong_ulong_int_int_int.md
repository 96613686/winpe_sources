# UnistoreJetSetIndexRange(TableHandleInfo *,_USPROPVAL const *,ulong,ulong,int,int,int)

- ea: `0x180010030`
- end: `0x180010681`
- name: `?UnistoreJetSetIndexRange@@YAJPEAUTableHandleInfo@@PEBU_USPROPVAL@@KKHHH@Z`
- size: `1617`
- prototype: `__int64 __usercall@<rax>(struct TableHandleInfo *@<rcx>, const struct _USPROPVAL *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int, int, int)`
- caller_count: `10`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180058af4`
- `0x18005e9d0`
- `0x180062fe0`
- `0x180067630`
- `0x1800ab6c4`
- `0x1800ad740`
- `0x1800adfb0`
- `0x1800af518`
- `0x1800af748`
- `0x1800af870`

## callees

- `0x180003b3c`
- `0x1800068f0`
- `0x180008638`
- `0x18000ab20`
- `0x18000f530`
- `0x18000f880`
- `0x180010030`
- `0x180011ed0`
- `0x180029494`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x180078a40`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetMakeKey` at `0x1800100bc`
- `ESENT!JetMakeKey` at `0x180010306`
- `ESENT!JetMakeKey` at `0x1800100bc`
- `ESENT!JetMakeKey` at `0x180010306`
- `ESENT!JetSetIndexRange` at `0x1800101bc`
- `ESENT!JetSetIndexRange` at `0x1800101bc`
- `ESENT!JetGetErrorInfoW` at `0x180010142`
- `ESENT!JetGetErrorInfoW` at `0x180010236`
- `ESENT!JetGetErrorInfoW` at `0x180010142`
- `ESENT!JetGetErrorInfoW` at `0x180010236`

## string_xrefs

- `0x180010527`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001055f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800105f5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001062d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001015d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18001028a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18001033e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010357`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18001047f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800104aa`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800104c3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010578`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010591`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180010646`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18001065f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreJetSetIndexRange(
        struct TableHandleInfo *a1,
        const struct _USPROPVAL *a2,
        unsigned int a3,
        JET_GRBIT a4,
        int a5,
        int a6,
        int a7)
{
  JET_GRBIT v11; // ebx
  int DataFromUSPropVal; // eax
  unsigned int HresultFromJetError; // edi
  JET_ERR Key; // eax
  int v15; // ebx
  unsigned int i; // ebx
  JET_GRBIT v17; // r8d
  JET_ERR v18; // eax
  int v19; // ebx
  unsigned int v21; // ebx
  JET_GRBIT grbit; // r15d
  int v23; // eax
  JET_ERR v24; // edi
  __int64 v25; // r9
  int v26; // r8d
  int v27; // r10d
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  unsigned int cbData; // [rsp+30h] [rbp-D0h] BYREF
  void *pvData; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh]
  void *v37; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+84h] [rbp-7Ch]
  __int128 v41; // [rsp+94h] [rbp-6Ch]
  __int128 v42; // [rsp+A4h] [rbp-5Ch]
  __int128 v43; // [rsp+B4h] [rbp-4Ch]
  __int128 v44; // [rsp+C4h] [rbp-3Ch]
  __int128 v45; // [rsp+D4h] [rbp-2Ch]
  __int128 v46; // [rsp+E4h] [rbp-1Ch]
  __int128 v47; // [rsp+F4h] [rbp-Ch]
  __int128 v48; // [rsp+104h] [rbp+4h]
  int v49; // [rsp+114h] [rbp+14h]

  if ( a3 )
  {
    pvData = 0;
    v11 = a4;
    cbData = 0;
    if ( a3 != 1 )
      v11 = 0;
    DataFromUSPropVal = GetDataFromUSPropVal(a2, (const void **)&pvData, &cbData);
    HresultFromJetError = DataFromUSPropVal;
    if ( DataFromUSPropVal < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)DataFromUSPropVal,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1326);
      Log_UnistoreHREvent_0(
        HresultFromJetError,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1347);
      goto LABEL_38;
    }
    Key = JetMakeKey(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), pvData, cbData, v11 | 1);
    v15 = Key;
    if ( g_fInProc && !dword_18010D924 )
    {
      if ( Key != -1414 )
      {
        cbData = Key;
        if ( Key >= 0 )
          goto LABEL_11;
        v39 = 152;
        v49 = 0;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v48 = 0;
        if ( (int)JetGetErrorInfoW(&cbData, &v39, 152, 1, 0) < 0 )
        {
LABEL_10:
          HresultFromJetError = MakeHresultFromJetError(v15);
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1355);
          if ( (HresultFromJetError & 0x80000000) == 0 )
            goto LABEL_11;
LABEL_38:
          v25 = 1374;
LABEL_39:
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            v25);
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1401);
          return HresultFromJetError;
        }
        if ( DWORD1(v40) != 10 )
        {
          if ( DWORD1(v40) == 11 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetInconsistentError<unsigned long>(&pvData);
          }
          else if ( DWORD1(v40) == 12 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetFragmentationError<unsigned long>(&pvData);
          }
          goto LABEL_10;
        }
        if ( cbData == -1414 )
          goto LABEL_10;
      }
      v29 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v15);
      if ( v29 >= 0 )
      {
        LODWORD(pvData) = v15;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&pvData);
        if ( (unsigned int)IsJetCorruptionError(v15) )
        {
          Log_AssertionEvent(
            v30,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            109);
          __int2c();
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v29,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          102);
      }
    }
    if ( v15 >= 0 )
    {
LABEL_11:
      for ( i = 1; i < a3; ++i )
      {
        pvData = 0;
        cbData = 0;
        grbit = a4;
        if ( i != a3 - 1 )
          grbit = 0;
        v23 = GetDataFromUSPropVal((const struct _USPROPVAL *)((char *)a2 + 24 * i), (const void **)&pvData, &cbData);
        HresultFromJetError = v23;
        if ( v23 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v23,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1326);
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1347);
LABEL_54:
          v25 = 1381;
          goto LABEL_39;
        }
        v24 = JetMakeKey(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), pvData, cbData, grbit);
        CheckCorruption(v24);
        if ( v24 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v24);
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1355);
          if ( (HresultFromJetError & 0x80000000) != 0 )
            goto LABEL_54;
        }
      }
      goto LABEL_13;
    }
    goto LABEL_10;
  }
LABEL_13:
  v17 = 0;
  if ( a5 )
    v17 = 2;
  if ( a6 )
    v17 |= 4u;
  if ( a7 )
    v17 |= 1u;
  v18 = JetSetIndexRange(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), v17);
  v19 = v18;
  if ( !g_fInProc || dword_18010D924 )
    goto LABEL_24;
  if ( v18 == -1414 )
    goto LABEL_65;
  cbData = v18;
  if ( v18 >= 0 )
    return 0;
  v39 = 152;
  v49 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  if ( (int)JetGetErrorInfoW(&cbData, &v39, 152, 1, 0) < 0 )
    goto LABEL_24;
  if ( DWORD1(v40) != 10 )
  {
    if ( DWORD1(v40) == 11 )
    {
      LODWORD(pvData) = cbData;
      UnistoreTelemetry::JetInconsistentError<unsigned long>(&pvData);
    }
    else if ( DWORD1(v40) == 12 )
    {
      LODWORD(pvData) = cbData;
      UnistoreTelemetry::JetFragmentationError<unsigned long>(&pvData);
    }
    goto LABEL_24;
  }
  if ( cbData != -1414 )
  {
LABEL_65:
    v31 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v19);
    if ( v31 >= 0 )
    {
      LODWORD(pvData) = v19;
      UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&pvData);
      if ( (unsigned int)IsJetCorruptionError(v19) )
      {
        Log_AssertionEvent(
          v32,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          109);
        __int2c();
      }
    }
    else
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v31,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        102);
    }
  }
LABEL_24:
  if ( v19 != -1603 )
  {
    if ( v19 >= 0 )
      return 0;
    v21 = MakeHresultFromJetError(v19);
    Log_UnistoreHREvent_0(
      v21,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      1441);
    return v21;
  }
  if ( *((_DWORD *)a1 + 6) )
  {
    UnifiedStoreCursorLocation::UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)&v35);
    v26 = v36;
    v36 = *((_DWORD *)a1 + 7);
    *((_DWORD *)a1 + 7) = v26;
    utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(
      &v37,
      (char *)a1 + 32);
    utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(
      &Block,
      (char *)a1 + 56);
    v27 = v35;
    v35 = *((_DWORD *)a1 + 6);
    *((_DWORD *)a1 + 6) = v27;
    v28 = UnistoreJetGotoBookmarkEx(a1, (const struct UnifiedStoreCursorLocation *)&v35, 0);
    v21 = v28;
    if ( v28 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v28,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        859);
      Log_UnistoreHREvent_0(
        v21,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1436);
      UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)&v35);
      return v21;
    }
    if ( Block != (void *)-1LL )
      operator delete(Block);
    if ( v37 != (void *)-1LL )
      operator delete(v37);
  }
  return 2147942425LL;
}

```

## disassembly

```asm
0x180010030  mov     [rsp-8+arg_10], rbx
0x180010035  push    rbp
0x180010036  push    rsi
0x180010037  push    rdi
0x180010038  push    r12
0x18001003a  push    r13
0x18001003c  push    r14
0x18001003e  push    r15
0x180010040  lea     rbp, [rsp-30h]
0x180010045  sub     rsp, 130h
0x18001004c  mov     rax, cs:__security_cookie
0x180010053  xor     rax, rsp
0x180010056  mov     [rbp+60h+var_40], rax
0x18001005a  xor     r15d, r15d
0x18001005d  mov     r12d, r9d
0x180010060  mov     r14d, r8d
0x180010063  mov     r13, rdx
0x180010066  mov     rsi, rcx
0x180010069  test    r8d, r8d
0x18001006c  jz      loc_180010188
0x180010072  cmp     r8d, 1
0x180010076  mov     [rsp+160h+pvData], r15
0x18001007b  mov     ebx, r9d
0x18001007e  mov     [rsp+160h+cbData], r15d
0x180010083  lea     r8, [rsp+160h+cbData]; unsigned int *
0x180010088  mov     rcx, r13; struct _USPROPVAL *
0x18001008b  lea     rdx, [rsp+160h+pvData]; void **
0x180010090  cmovnz  ebx, r15d
0x180010094  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x180010099  mov     edi, eax
0x18001009b  test    eax, eax
0x18001009d  js      loc_1800104A4
0x1800100a3  mov     r9d, [rsp+160h+cbData]; cbData
0x1800100a8  or      ebx, 1
0x1800100ab  mov     r8, [rsp+160h+pvData]; pvData
0x1800100b0  mov     rdx, [rsi+10h]; tableid
0x1800100b4  mov     rcx, [rsi+8]; sesid
0x1800100b8  mov     [rsp+160h+grbit], ebx; grbit
0x1800100bc  call    cs:__imp_JetMakeKey
0x1800100c2  cmp     cs:?g_fInProc@@3HA, r15d; int g_fInProc
0x1800100c9  mov     ebx, eax
0x1800100cb  jz      loc_1800102A0
0x1800100d1  cmp     cs:dword_18010D924, r15d
0x1800100d8  jnz     loc_1800102A0
0x1800100de  cmp     eax, 0FFFFFA7Ah
0x1800100e3  jz      loc_180010500
0x1800100e9  mov     [rsp+160h+cbData], eax
0x1800100ed  test    eax, eax
0x1800100ef  jns     loc_180010177
0x1800100f5  xorps   xmm0, xmm0
0x1800100f8  mov     [rbp+60h+var_E0], 98h
0x1800100ff  xor     eax, eax
0x180010101  mov     [rsp+160h+grbit], r15d
0x180010106  mov     r9d, 1
0x18001010c  mov     [rbp+60h+var_4C], eax
0x18001010f  mov     r8d, 98h
0x180010115  lea     rdx, [rbp+60h+var_E0]
0x180010119  lea     rcx, [rsp+160h+cbData]
0x18001011e  movups  [rbp+60h+var_DC], xmm0
0x180010122  movups  [rbp+60h+var_CC], xmm0
0x180010126  movups  [rbp+60h+var_BC], xmm0
0x18001012a  movups  [rbp+60h+var_AC], xmm0
0x18001012e  movups  [rbp+60h+var_9C], xmm0
0x180010132  movups  [rbp+60h+var_8C], xmm0
0x180010136  movups  [rbp+60h+var_7C], xmm0
0x18001013a  movups  [rbp+60h+var_6C], xmm0
0x18001013e  movups  [rbp+60h+var_5C], xmm0
0x180010142  call    cs:__imp_JetGetErrorInfoW
0x180010148  test    eax, eax
0x18001014a  jns     loc_1800103A6
0x180010150  mov     ecx, ebx; int
0x180010152  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180010157  mov     r9d, 54Bh
0x18001015d  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010164  xor     edx, edx
0x180010166  mov     ecx, eax
0x180010168  mov     edi, eax
0x18001016a  call    Log_UnistoreHREvent_0
0x18001016f  test    edi, edi
0x180010171  js      loc_180010338
0x180010177  mov     ebx, 1
0x18001017c  cmp     ebx, r14d
0x18001017f  jb      loc_1800102AD
0x180010185  xor     r15d, r15d
0x180010188  cmp     [rbp+60h+arg_20], 0
0x18001018f  mov     r8d, r15d
0x180010192  jz      short loc_18001019A
0x180010194  mov     r8d, 2
0x18001019a  cmp     [rbp+60h+arg_28], 0
0x1800101a1  jz      short loc_1800101A7
0x1800101a3  or      r8d, 4
0x1800101a7  cmp     [rbp+60h+arg_30], 0
0x1800101ae  jz      short loc_1800101B4
0x1800101b0  or      r8d, 1; grbit
0x1800101b4  mov     rdx, [rsi+10h]; tableidSrc
0x1800101b8  mov     rcx, [rsi+8]; sesid
0x1800101bc  call    cs:__imp_JetSetIndexRange
0x1800101c2  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x1800101c9  mov     ebx, eax
0x1800101cb  jz      short loc_180010244
0x1800101cd  cmp     cs:dword_18010D924, 0
0x1800101d4  jnz     short loc_180010244
0x1800101d6  cmp     eax, 0FFFFFA7Ah
0x1800101db  jz      loc_1800105CE
0x1800101e1  mov     [rsp+160h+cbData], eax
0x1800101e5  test    eax, eax
0x1800101e7  jns     short loc_180010254
0x1800101e9  xorps   xmm0, xmm0
0x1800101ec  mov     [rbp+60h+var_E0], 98h
0x1800101f3  xor     eax, eax
0x1800101f5  mov     [rsp+160h+grbit], r15d
0x1800101fa  mov     r9d, 1
0x180010200  mov     [rbp+60h+var_4C], eax
0x180010203  mov     r8d, 98h
0x180010209  lea     rdx, [rbp+60h+var_E0]
0x18001020d  lea     rcx, [rsp+160h+cbData]
0x180010212  movups  [rbp+60h+var_DC], xmm0
0x180010216  movups  [rbp+60h+var_CC], xmm0
0x18001021a  movups  [rbp+60h+var_BC], xmm0
0x18001021e  movups  [rbp+60h+var_AC], xmm0
0x180010222  movups  [rbp+60h+var_9C], xmm0
0x180010226  movups  [rbp+60h+var_8C], xmm0
0x18001022a  movups  [rbp+60h+var_7C], xmm0
0x18001022e  movups  [rbp+60h+var_6C], xmm0
0x180010232  movups  [rbp+60h+var_5C], xmm0
0x180010236  call    cs:__imp_JetGetErrorInfoW
0x18001023c  test    eax, eax
0x18001023e  jns     loc_180010371
0x180010244  cmp     ebx, 0FFFFF9BDh
0x18001024a  jz      loc_180010324
0x180010250  test    ebx, ebx
0x180010252  js      short loc_18001027D
0x180010254  xor     eax, eax
0x180010256  mov     rcx, [rbp+60h+var_40]
0x18001025a  xor     rcx, rsp; StackCookie
0x18001025d  call    __security_check_cookie
0x180010262  mov     rbx, [rsp+160h+arg_10]
0x18001026a  add     rsp, 130h
0x180010271  pop     r15
0x180010273  pop     r14
0x180010275  pop     r13
0x180010277  pop     r12
0x180010279  pop     rdi
0x18001027a  pop     rsi
0x18001027b  pop     rbp
0x18001027c  retn
0x18001027d  mov     ecx, ebx; int
0x18001027f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180010284  mov     r9d, 5A1h
0x18001028a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010291  xor     edx, edx
0x180010293  mov     ecx, eax
0x180010295  mov     ebx, eax
0x180010297  call    Log_UnistoreHREvent_0
0x18001029c  mov     eax, ebx
0x18001029e  jmp     short loc_180010256
0x1800102a0  test    ebx, ebx
0x1800102a2  jns     loc_180010177
0x1800102a8  jmp     loc_180010150
0x1800102ad  xor     eax, eax
0x1800102af  lea     ecx, [r14-1]
0x1800102b3  cmp     ebx, ecx
0x1800102b5  mov     [rsp+160h+pvData], rax
0x1800102ba  mov     [rsp+160h+cbData], eax
0x1800102be  lea     r8, [rsp+160h+cbData]; unsigned int *
0x1800102c3  mov     r15d, r12d
0x1800102c6  lea     rdx, [rsp+160h+pvData]; void **
0x1800102cb  cmovnz  r15d, eax
0x1800102cf  mov     eax, ebx
0x1800102d1  lea     rcx, [rax+rax*2]
0x1800102d5  lea     rcx, ds:0[rcx*8]
0x1800102dd  add     rcx, r13; struct _USPROPVAL *
0x1800102e0  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x1800102e5  mov     edi, eax
0x1800102e7  test    eax, eax
0x1800102e9  js      loc_180010572
0x1800102ef  mov     r9d, [rsp+160h+cbData]; cbData
0x1800102f4  mov     r8, [rsp+160h+pvData]; pvData
0x1800102f9  mov     rdx, [rsi+10h]; tableid
0x1800102fd  mov     rcx, [rsi+8]; sesid
0x180010301  mov     [rsp+160h+grbit], r15d; grbit
0x180010306  call    cs:__imp_JetMakeKey
0x18001030c  mov     ecx, eax; int
0x18001030e  mov     edi, eax
0x180010310  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180010315  test    edi, edi
0x180010317  js      loc_180010472
0x18001031d  inc     ebx
0x18001031f  jmp     loc_18001017C
0x180010324  cmp     dword ptr [rsi+18h], 0
0x180010328  jnz     loc_1800103DB
0x18001032e  mov     eax, 80070019h
0x180010333  jmp     loc_180010256
0x180010338  mov     r9d, 55Eh
0x18001033e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010345  mov     edx, 1
0x18001034a  mov     ecx, edi
0x18001034c  call    Log_UnistoreHREvent_0
0x180010351  mov     r9d, 579h
0x180010357  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001035e  mov     edx, 1
0x180010363  mov     ecx, edi
0x180010365  call    Log_UnistoreHREvent_0
0x18001036a  mov     eax, edi
0x18001036c  jmp     loc_180010256
0x180010371  mov     ecx, dword ptr [rbp+60h+var_DC+4]
0x180010374  sub     ecx, 0Ah
0x180010377  jz      loc_1800105C0
0x18001037d  sub     ecx, 1
0x180010380  jz      loc_1800105A9
0x180010386  cmp     ecx, 1
0x180010389  jnz     loc_180010244
0x18001038f  mov     eax, [rsp+160h+cbData]
0x180010393  lea     rcx, [rsp+160h+pvData]
0x180010398  mov     dword ptr [rsp+160h+pvData], eax
0x18001039c  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x1800103a1  jmp     loc_180010244
0x1800103a6  mov     ecx, dword ptr [rbp+60h+var_DC+4]
0x1800103a9  sub     ecx, 0Ah
0x1800103ac  jz      loc_1800104F2
0x1800103b2  sub     ecx, 1
0x1800103b5  jz      loc_1800104DB
0x1800103bb  cmp     ecx, 1
0x1800103be  jnz     loc_180010150
0x1800103c4  mov     eax, [rsp+160h+cbData]
0x1800103c8  lea     rcx, [rsp+160h+pvData]
0x1800103cd  mov     dword ptr [rsp+160h+pvData], eax
0x1800103d1  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x1800103d6  jmp     loc_180010150
0x1800103db  lea     rcx, [rsp+160h+var_120]; this
0x1800103e0  call    ??0UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::UnifiedStoreCursorLocation(void)
0x1800103e5  mov     eax, [rsi+1Ch]
0x1800103e8  lea     rdx, [rsi+20h]
0x1800103ec  mov     r8d, [rsp+160h+var_11C]
0x1800103f1  lea     rcx, [rsp+160h+var_118]
0x1800103f6  mov     [rsp+160h+var_11C], eax
0x1800103fa  mov     [rsi+1Ch], r8d
0x1800103fe  call    ?swap@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@QEAAXAEAV12@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>> &)
0x180010403  lea     rdx, [rsi+38h]
0x180010407  lea     rcx, [rsp+160h+Block]
0x18001040c  call    ?swap@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@QEAAXAEAV12@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>> &)
0x180010411  mov     eax, [rsi+18h]
0x180010414  lea     rdx, [rsp+160h+var_120]; struct UnifiedStoreCursorLocation *
0x180010419  mov     r10d, [rsp+160h+var_120]
0x18001041e  xor     r8d, r8d; int *
0x180010421  mov     rcx, rsi; struct TableHandleInfo *
0x180010424  mov     [rsp+160h+var_120], eax
0x180010428  mov     [rsi+18h], r10d
0x18001042c  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x180010431  mov     ebx, eax
0x180010433  test    eax, eax
0x180010435  js      loc_180010640
0x18001043b  mov     rcx, [rsp+160h+Block]; Block
0x180010440  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010444  jz      short loc_180010452
0x180010446  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001044d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010452  mov     rcx, [rsp+160h+var_118]; Block
0x180010457  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001045b  jz      loc_18001032E
0x180010461  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180010468  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001046d  jmp     loc_18001032E
0x180010472  mov     ecx, edi; int
0x180010474  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180010479  mov     r9d, 54Bh
0x18001047f  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010486  xor     edx, edx
0x180010488  mov     ecx, eax
0x18001048a  mov     edi, eax
0x18001048c  call    Log_UnistoreHREvent_0
0x180010491  test    edi, edi
0x180010493  jns     loc_18001031D
0x180010499  mov     r9d, 565h
0x18001049f  jmp     loc_18001033E
0x1800104a4  mov     r9d, 52Eh
0x1800104aa  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800104b1  mov     edx, 1
0x1800104b6  mov     ecx, edi
0x1800104b8  call    Log_UnistoreHREvent_0
0x1800104bd  mov     r9d, 543h
0x1800104c3  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800104ca  mov     edx, 1
0x1800104cf  mov     ecx, edi
0x1800104d1  call    Log_UnistoreHREvent_0
0x1800104d6  jmp     loc_180010338
0x1800104db  mov     eax, [rsp+160h+cbData]
0x1800104df  lea     rcx, [rsp+160h+pvData]
0x1800104e4  mov     dword ptr [rsp+160h+pvData], eax
0x1800104e8  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x1800104ed  jmp     loc_180010150
0x1800104f2  cmp     [rsp+160h+cbData], 0FFFFFA7Ah
0x1800104fa  jz      loc_180010150
0x180010500  mov     r9d, ebx; unsigned int
0x180010503  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18001050a  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x180010511  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180010518  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001051d  test    eax, eax
0x18001051f  jns     short loc_18001053C
  ... truncated ...
```
