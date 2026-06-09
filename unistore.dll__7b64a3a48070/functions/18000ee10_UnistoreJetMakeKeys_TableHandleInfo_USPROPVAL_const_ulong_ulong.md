# UnistoreJetMakeKeys(TableHandleInfo *,_USPROPVAL const *,ulong,ulong)

- ea: `0x18000ee10`
- end: `0x18000f2e5`
- name: `?UnistoreJetMakeKeys@@YAJPEAUTableHandleInfo@@PEBU_USPROPVAL@@KK@Z`
- size: `1237`
- prototype: `int(struct TableHandleInfo *, const struct _USPROPVAL *, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056cf0`
- `0x180058870`
- `0x180058960`
- `0x180058af4`
- `0x180061700`
- `0x180067630`
- `0x1800ad740`
- `0x1800adfb0`
- `0x1800ae200`
- `0x1800ae300`
- `0x1800aefc0`
- `0x1800af110`
- `0x1800af748`

## callees

- `0x1800068f0`
- `0x18000ee10`
- `0x18000f530`
- `0x18000f880`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetMakeKey` at `0x18000ee9c`
- `ESENT!JetMakeKey` at `0x18000efea`
- `ESENT!JetMakeKey` at `0x18000ee9c`
- `ESENT!JetMakeKey` at `0x18000efea`
- `ESENT!JetGetErrorInfoW` at `0x18000ef25`
- `ESENT!JetGetErrorInfoW` at `0x18000f072`
- `ESENT!JetGetErrorInfoW` at `0x18000ef25`
- `ESENT!JetGetErrorInfoW` at `0x18000f072`

## string_xrefs

- `0x18000f1c6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000f1fe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000f25d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000f295`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000ef40`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f08d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f0b4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f149`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f162`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f2ae`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f2c7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreJetMakeKeys(
        struct TableHandleInfo *a1,
        const struct _USPROPVAL *a2,
        unsigned int a3,
        JET_GRBIT a4)
{
  JET_GRBIT v8; // ebx
  int DataFromUSPropVal; // eax
  unsigned int HresultFromJetError; // edi
  JET_ERR Key; // eax
  int v12; // ebx
  unsigned int i; // ebx
  JET_GRBIT grbit; // r14d
  int v16; // eax
  JET_ERR v17; // eax
  int v18; // edi
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  unsigned int cbData; // [rsp+30h] [rbp-99h] BYREF
  void *pvData; // [rsp+38h] [rbp-91h] BYREF
  int v26; // [rsp+40h] [rbp-89h] BYREF
  __int128 v27; // [rsp+44h] [rbp-85h]
  __int128 v28; // [rsp+54h] [rbp-75h]
  __int128 v29; // [rsp+64h] [rbp-65h]
  __int128 v30; // [rsp+74h] [rbp-55h]
  __int128 v31; // [rsp+84h] [rbp-45h]
  __int128 v32; // [rsp+94h] [rbp-35h]
  __int128 v33; // [rsp+A4h] [rbp-25h]
  __int128 v34; // [rsp+B4h] [rbp-15h]
  __int128 v35; // [rsp+C4h] [rbp-5h]
  int v36; // [rsp+D4h] [rbp+Bh]

  if ( !a3 )
    return 0;
  pvData = 0;
  v8 = a4;
  cbData = 0;
  if ( a3 != 1 )
    v8 = 0;
  DataFromUSPropVal = GetDataFromUSPropVal(a2, (const void **)&pvData, &cbData);
  HresultFromJetError = DataFromUSPropVal;
  if ( DataFromUSPropVal >= 0 )
  {
    Key = JetMakeKey(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), pvData, cbData, v8 | 1);
    v12 = Key;
    if ( g_fInProc && !dword_18010D924 )
    {
      if ( Key != -1414 )
      {
        cbData = Key;
        if ( Key >= 0 )
        {
LABEL_11:
          for ( i = 1; ; ++i )
          {
            if ( i >= a3 )
              return 0;
            pvData = 0;
            cbData = 0;
            grbit = a4;
            if ( i != a3 - 1 )
              grbit = 0;
            v16 = GetDataFromUSPropVal(
                    (const struct _USPROPVAL *)((char *)a2 + 24 * i),
                    (const void **)&pvData,
                    &cbData);
            HresultFromJetError = v16;
            if ( v16 < 0 )
            {
              Log_UnistoreHREvent_0(
                (unsigned int)v16,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                1326);
              Log_UnistoreHREvent_0(
                HresultFromJetError,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
                1347);
LABEL_52:
              v19 = 1381;
              goto LABEL_27;
            }
            v17 = JetMakeKey(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), pvData, cbData, grbit);
            v18 = v17;
            if ( !g_fInProc || dword_18010D924 )
              goto LABEL_32;
            if ( v17 == -1414 )
              goto LABEL_47;
            cbData = v17;
            if ( v17 >= 0 )
              continue;
            v26 = 152;
            v36 = 0;
            v27 = 0;
            v28 = 0;
            v29 = 0;
            v30 = 0;
            v31 = 0;
            v32 = 0;
            v33 = 0;
            v34 = 0;
            v35 = 0;
            if ( (int)JetGetErrorInfoW(&cbData, &v26, 152, 1, 0) >= 0 )
            {
              switch ( DWORD1(v27) )
              {
                case 0xA:
                  if ( cbData != -1414 )
                  {
LABEL_47:
                    v22 = RegistrySetDWORD(
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Unified Store",
                            L"CorruptReason",
                            v18);
                    if ( v22 >= 0 )
                    {
                      LODWORD(pvData) = v18;
                      UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&pvData);
                      if ( (unsigned int)IsJetCorruptionError(v18) )
                      {
                        Log_AssertionEvent(
                          v23,
                          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                          109);
                        __int2c();
                      }
                    }
                    else
                    {
                      Log_UnistoreHREvent_0(
                        (unsigned int)v22,
                        0,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                        102);
                    }
LABEL_32:
                    if ( v18 >= 0 )
                      continue;
                  }
                  break;
                case 0xB:
                  LODWORD(pvData) = cbData;
                  UnistoreTelemetry::JetInconsistentError<unsigned long>(&pvData);
                  break;
                case 0xC:
                  LODWORD(pvData) = cbData;
                  UnistoreTelemetry::JetFragmentationError<unsigned long>(&pvData);
                  break;
              }
            }
            HresultFromJetError = MakeHresultFromJetError(v18);
            Log_UnistoreHREvent_0(
              HresultFromJetError,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
              1355);
            if ( (HresultFromJetError & 0x80000000) != 0 )
              goto LABEL_52;
          }
        }
        v26 = 152;
        v36 = 0;
        v27 = 0;
        v28 = 0;
        v29 = 0;
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        if ( (int)JetGetErrorInfoW(&cbData, &v26, 152, 1, 0) < 0 )
          goto LABEL_10;
        if ( DWORD1(v27) != 10 )
        {
          if ( DWORD1(v27) == 11 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetInconsistentError<unsigned long>(&pvData);
          }
          else if ( DWORD1(v27) == 12 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetFragmentationError<unsigned long>(&pvData);
          }
          goto LABEL_10;
        }
        if ( cbData == -1414 )
          goto LABEL_10;
      }
      v20 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v12);
      if ( v20 >= 0 )
      {
        LODWORD(pvData) = v12;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&pvData);
        if ( (unsigned int)IsJetCorruptionError(v12) )
        {
          Log_AssertionEvent(
            v21,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            109);
          __int2c();
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v20,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          102);
      }
    }
    if ( v12 >= 0 )
      goto LABEL_11;
LABEL_10:
    HresultFromJetError = MakeHresultFromJetError(v12);
    Log_UnistoreHREvent_0(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      1355);
    if ( (HresultFromJetError & 0x80000000) == 0 )
      goto LABEL_11;
    goto LABEL_26;
  }
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
LABEL_26:
  v19 = 1374;
LABEL_27:
  Log_UnistoreHREvent_0(
    HresultFromJetError,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    v19);
  return HresultFromJetError;
}

```

## disassembly

```asm
0x18000ee10  mov     [rsp-8+arg_10], rbx
0x18000ee15  push    rbp
0x18000ee16  push    rsi
0x18000ee17  push    rdi
0x18000ee18  push    r12
0x18000ee1a  push    r13
0x18000ee1c  push    r14
0x18000ee1e  push    r15
0x18000ee20  lea     rbp, [rsp-27h]
0x18000ee25  sub     rsp, 0F0h
0x18000ee2c  mov     rax, cs:__security_cookie
0x18000ee33  xor     rax, rsp
0x18000ee36  mov     [rbp+57h+var_40], rax
0x18000ee3a  mov     r12d, r9d
0x18000ee3d  mov     esi, r8d
0x18000ee40  mov     r13, rdx
0x18000ee43  mov     r15, rcx
0x18000ee46  test    r8d, r8d
0x18000ee49  jz      loc_18000EF63
0x18000ee4f  xor     r14d, r14d
0x18000ee52  lea     rdx, [rsp+120h+pvData]; void **
0x18000ee57  cmp     r8d, 1
0x18000ee5b  mov     [rsp+120h+pvData], r14
0x18000ee60  mov     ebx, r9d
0x18000ee63  mov     [rsp+120h+cbData], r14d
0x18000ee68  lea     r8, [rsp+120h+cbData]; unsigned int *
0x18000ee6d  mov     rcx, r13; struct _USPROPVAL *
0x18000ee70  cmovnz  ebx, r14d
0x18000ee74  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x18000ee79  mov     edi, eax
0x18000ee7b  test    eax, eax
0x18000ee7d  js      loc_18000F143
0x18000ee83  mov     r9d, [rsp+120h+cbData]; cbData
0x18000ee88  or      ebx, 1
0x18000ee8b  mov     r8, [rsp+120h+pvData]; pvData
0x18000ee90  mov     rdx, [r15+10h]; tableid
0x18000ee94  mov     rcx, [r15+8]; sesid
0x18000ee98  mov     [rsp+120h+grbit], ebx; grbit
0x18000ee9c  call    cs:__imp_JetMakeKey
0x18000eea2  cmp     cs:?g_fInProc@@3HA, r14d; int g_fInProc
0x18000eea9  mov     ebx, eax
0x18000eeab  jz      loc_18000EF8C
0x18000eeb1  cmp     cs:dword_18010D924, r14d
0x18000eeb8  jnz     loc_18000EF8C
0x18000eebe  cmp     eax, 0FFFFFA7Ah
0x18000eec3  jz      loc_18000F19F
0x18000eec9  mov     [rsp+120h+cbData], eax
0x18000eecd  test    eax, eax
0x18000eecf  jns     loc_18000EF5A
0x18000eed5  xorps   xmm0, xmm0
0x18000eed8  mov     [rsp+120h+var_E0], 98h
0x18000eee0  xor     eax, eax
0x18000eee2  mov     [rsp+120h+grbit], r14d
0x18000eee7  mov     r9d, 1
0x18000eeed  mov     [rbp+57h+var_4C], eax
0x18000eef0  mov     r8d, 98h
0x18000eef6  lea     rdx, [rsp+120h+var_E0]
0x18000eefb  lea     rcx, [rsp+120h+cbData]
0x18000ef00  movups  [rsp+120h+var_DC], xmm0
0x18000ef05  movups  [rbp+57h+var_CC], xmm0
0x18000ef09  movups  [rbp+57h+var_BC], xmm0
0x18000ef0d  movups  [rbp+57h+var_AC], xmm0
0x18000ef11  movups  [rbp+57h+var_9C], xmm0
0x18000ef15  movups  [rbp+57h+var_8C], xmm0
0x18000ef19  movups  [rbp+57h+var_7C], xmm0
0x18000ef1d  movups  [rbp+57h+var_6C], xmm0
0x18000ef21  movups  [rbp+57h+var_5C], xmm0
0x18000ef25  call    cs:__imp_JetGetErrorInfoW
0x18000ef2b  test    eax, eax
0x18000ef2d  jns     loc_18000F0CE
0x18000ef33  mov     ecx, ebx; int
0x18000ef35  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000ef3a  mov     r9d, 54Bh
0x18000ef40  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ef47  xor     edx, edx
0x18000ef49  mov     ecx, eax
0x18000ef4b  mov     edi, eax
0x18000ef4d  call    Log_UnistoreHREvent_0
0x18000ef52  test    edi, edi
0x18000ef54  js      loc_18000F0AE
0x18000ef5a  mov     ebx, 1
0x18000ef5f  cmp     ebx, esi
0x18000ef61  jb      short loc_18000EF92
0x18000ef63  xor     eax, eax
0x18000ef65  mov     rcx, [rbp+57h+var_40]
0x18000ef69  xor     rcx, rsp; StackCookie
0x18000ef6c  call    __security_check_cookie
0x18000ef71  mov     rbx, [rsp+120h+arg_10]
0x18000ef79  add     rsp, 0F0h
0x18000ef80  pop     r15
0x18000ef82  pop     r14
0x18000ef84  pop     r13
0x18000ef86  pop     r12
0x18000ef88  pop     rdi
0x18000ef89  pop     rsi
0x18000ef8a  pop     rbp
0x18000ef8b  retn
0x18000ef8c  test    ebx, ebx
0x18000ef8e  jns     short loc_18000EF5A
0x18000ef90  jmp     short loc_18000EF33
0x18000ef92  xor     eax, eax
0x18000ef94  lea     ecx, [rsi-1]
0x18000ef97  cmp     ebx, ecx
0x18000ef99  mov     [rsp+120h+pvData], rax
0x18000ef9e  mov     [rsp+120h+cbData], eax
0x18000efa2  lea     r8, [rsp+120h+cbData]; unsigned int *
0x18000efa7  mov     r14d, r12d
0x18000efaa  lea     rdx, [rsp+120h+pvData]; void **
0x18000efaf  cmovnz  r14d, eax
0x18000efb3  mov     eax, ebx
0x18000efb5  lea     rcx, [rax+rax*2]
0x18000efb9  lea     rcx, ds:0[rcx*8]
0x18000efc1  add     rcx, r13; struct _USPROPVAL *
0x18000efc4  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x18000efc9  mov     edi, eax
0x18000efcb  test    eax, eax
0x18000efcd  js      loc_18000F2A8
0x18000efd3  mov     r9d, [rsp+120h+cbData]; cbData
0x18000efd8  mov     r8, [rsp+120h+pvData]; pvData
0x18000efdd  mov     rdx, [r15+10h]; tableid
0x18000efe1  mov     rcx, [r15+8]; sesid
0x18000efe5  mov     [rsp+120h+grbit], r14d; grbit
0x18000efea  call    cs:__imp_JetMakeKey
0x18000eff0  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x18000eff7  mov     edi, eax
0x18000eff9  jz      loc_18000F104
0x18000efff  cmp     cs:dword_18010D924, 0
0x18000f006  jnz     loc_18000F104
0x18000f00c  cmp     eax, 0FFFFFA7Ah
0x18000f011  jz      loc_18000F236
0x18000f017  mov     [rsp+120h+cbData], eax
0x18000f01b  test    eax, eax
0x18000f01d  jns     loc_18000F0A7
0x18000f023  xorps   xmm0, xmm0
0x18000f026  mov     [rsp+120h+var_E0], 98h
0x18000f02e  xor     eax, eax
0x18000f030  lea     rdx, [rsp+120h+var_E0]
0x18000f035  mov     r9d, 1
0x18000f03b  mov     [rbp+57h+var_4C], eax
0x18000f03e  mov     r8d, 98h
0x18000f044  mov     [rsp+120h+grbit], eax
0x18000f048  lea     rcx, [rsp+120h+cbData]
0x18000f04d  movups  [rsp+120h+var_DC], xmm0
0x18000f052  movups  [rbp+57h+var_CC], xmm0
0x18000f056  movups  [rbp+57h+var_BC], xmm0
0x18000f05a  movups  [rbp+57h+var_AC], xmm0
0x18000f05e  movups  [rbp+57h+var_9C], xmm0
0x18000f062  movups  [rbp+57h+var_8C], xmm0
0x18000f066  movups  [rbp+57h+var_7C], xmm0
0x18000f06a  movups  [rbp+57h+var_6C], xmm0
0x18000f06e  movups  [rbp+57h+var_5C], xmm0
0x18000f072  call    cs:__imp_JetGetErrorInfoW
0x18000f078  test    eax, eax
0x18000f07a  jns     loc_18000F10D
0x18000f080  mov     ecx, edi; int
0x18000f082  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000f087  mov     r9d, 54Bh
0x18000f08d  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f094  xor     edx, edx
0x18000f096  mov     ecx, eax
0x18000f098  mov     edi, eax
0x18000f09a  call    Log_UnistoreHREvent_0
0x18000f09f  test    edi, edi
0x18000f0a1  js      loc_18000F2DA
0x18000f0a7  inc     ebx
0x18000f0a9  jmp     loc_18000EF5F
0x18000f0ae  mov     r9d, 55Eh
0x18000f0b4  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f0bb  mov     edx, 1
0x18000f0c0  mov     ecx, edi
0x18000f0c2  call    Log_UnistoreHREvent_0
0x18000f0c7  mov     eax, edi
0x18000f0c9  jmp     loc_18000EF65
0x18000f0ce  mov     ecx, dword ptr [rsp+120h+var_DC+4]
0x18000f0d2  sub     ecx, 0Ah
0x18000f0d5  jz      loc_18000F191
0x18000f0db  sub     ecx, 1
0x18000f0de  jz      loc_18000F17A
0x18000f0e4  cmp     ecx, 1
0x18000f0e7  jnz     loc_18000EF33
0x18000f0ed  mov     eax, [rsp+120h+cbData]
0x18000f0f1  lea     rcx, [rsp+120h+pvData]
0x18000f0f6  mov     dword ptr [rsp+120h+pvData], eax
0x18000f0fa  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000f0ff  jmp     loc_18000EF33
0x18000f104  test    edi, edi
0x18000f106  jns     short loc_18000F0A7
0x18000f108  jmp     loc_18000F080
0x18000f10d  mov     ecx, dword ptr [rsp+120h+var_DC+4]
0x18000f111  sub     ecx, 0Ah
0x18000f114  jz      loc_18000F228
0x18000f11a  sub     ecx, 1
0x18000f11d  jz      loc_18000F211
0x18000f123  cmp     ecx, 1
0x18000f126  jnz     loc_18000F080
0x18000f12c  mov     eax, [rsp+120h+cbData]
0x18000f130  lea     rcx, [rsp+120h+pvData]
0x18000f135  mov     dword ptr [rsp+120h+pvData], eax
0x18000f139  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000f13e  jmp     loc_18000F080
0x18000f143  mov     r9d, 52Eh
0x18000f149  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f150  mov     edx, 1
0x18000f155  mov     ecx, edi
0x18000f157  call    Log_UnistoreHREvent_0
0x18000f15c  mov     r9d, 543h
0x18000f162  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f169  mov     edx, 1
0x18000f16e  mov     ecx, edi
0x18000f170  call    Log_UnistoreHREvent_0
0x18000f175  jmp     loc_18000F0AE
0x18000f17a  mov     eax, [rsp+120h+cbData]
0x18000f17e  lea     rcx, [rsp+120h+pvData]
0x18000f183  mov     dword ptr [rsp+120h+pvData], eax
0x18000f187  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000f18c  jmp     loc_18000EF33
0x18000f191  cmp     [rsp+120h+cbData], 0FFFFFA7Ah
0x18000f199  jz      loc_18000EF33
0x18000f19f  mov     r9d, ebx; unsigned int
0x18000f1a2  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18000f1a9  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18000f1b0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f1b7  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000f1bc  test    eax, eax
0x18000f1be  jns     short loc_18000F1DB
0x18000f1c0  mov     r9d, 66h ; 'f'
0x18000f1c6  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f1cd  xor     edx, edx
0x18000f1cf  mov     ecx, eax
0x18000f1d1  call    Log_UnistoreHREvent_0
0x18000f1d6  jmp     loc_18000EF8C
0x18000f1db  lea     rcx, [rsp+120h+pvData]
0x18000f1e0  mov     dword ptr [rsp+120h+pvData], ebx
0x18000f1e4  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x18000f1e9  mov     ecx, ebx; int
0x18000f1eb  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18000f1f0  test    eax, eax
0x18000f1f2  jz      loc_18000EF8C
0x18000f1f8  mov     r8d, 6Dh ; 'm'
0x18000f1fe  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f205  call    Log_AssertionEvent
0x18000f20a  int     2Ch; Windows NT - assertion failure
0x18000f20c  jmp     loc_18000EF8C
0x18000f211  mov     eax, [rsp+120h+cbData]
0x18000f215  lea     rcx, [rsp+120h+pvData]
0x18000f21a  mov     dword ptr [rsp+120h+pvData], eax
0x18000f21e  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000f223  jmp     loc_18000F080
0x18000f228  cmp     [rsp+120h+cbData], 0FFFFFA7Ah
0x18000f230  jz      loc_18000F080
0x18000f236  mov     r9d, edi; unsigned int
0x18000f239  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18000f240  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18000f247  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f24e  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000f253  test    eax, eax
0x18000f255  jns     short loc_18000F272
0x18000f257  mov     r9d, 66h ; 'f'
0x18000f25d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f264  xor     edx, edx
0x18000f266  mov     ecx, eax
0x18000f268  call    Log_UnistoreHREvent_0
0x18000f26d  jmp     loc_18000F104
0x18000f272  lea     rcx, [rsp+120h+pvData]
0x18000f277  mov     dword ptr [rsp+120h+pvData], edi
0x18000f27b  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x18000f280  mov     ecx, edi; int
0x18000f282  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18000f287  test    eax, eax
0x18000f289  jz      loc_18000F104
0x18000f28f  mov     r8d, 6Dh ; 'm'
0x18000f295  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f29c  call    Log_AssertionEvent
0x18000f2a1  int     2Ch; Windows NT - assertion failure
0x18000f2a3  jmp     loc_18000F104
0x18000f2a8  mov     r9d, 52Eh
0x18000f2ae  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f2b5  mov     edx, 1
0x18000f2ba  mov     ecx, edi
0x18000f2bc  call    Log_UnistoreHREvent_0
0x18000f2c1  mov     r9d, 543h
0x18000f2c7  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f2ce  mov     edx, 1
0x18000f2d3  mov     ecx, edi
0x18000f2d5  call    Log_UnistoreHREvent_0
0x18000f2da  mov     r9d, 565h
0x18000f2e0  jmp     loc_18000F0B4
```
