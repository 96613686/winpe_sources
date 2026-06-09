# UnistoreJetMakeKey(TableHandleInfo *,_USPROPVAL const *,ulong)

- ea: `0x18000f2f0`
- end: `0x18000f52a`
- name: `?UnistoreJetMakeKey@@YAJPEAUTableHandleInfo@@PEBU_USPROPVAL@@K@Z`
- size: `570`
- prototype: `int(struct TableHandleInfo *, const struct _USPROPVAL *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab6c4`

## callees

- `0x1800068f0`
- `0x18000f2f0`
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

- `ESENT!JetMakeKey` at `0x18000f359`
- `ESENT!JetMakeKey` at `0x18000f359`
- `ESENT!JetGetErrorInfoW` at `0x18000f3df`
- `ESENT!JetGetErrorInfoW` at `0x18000f3df`

## string_xrefs

- `0x18000f4df`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000f517`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000f410`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f44c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000f465`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreJetMakeKey(struct TableHandleInfo *a1, const struct _USPROPVAL *a2, JET_GRBIT a3)
{
  int DataFromUSPropVal; // eax
  unsigned int v6; // esi
  JET_ERR Key; // eax
  int v8; // ebx
  unsigned int HresultFromJetError; // ebx
  int v11; // eax
  __int64 v12; // rcx
  unsigned int cbData; // [rsp+30h] [rbp-89h] BYREF
  void *pvData; // [rsp+38h] [rbp-81h] BYREF
  int v15; // [rsp+40h] [rbp-79h] BYREF
  __int128 v16; // [rsp+44h] [rbp-75h]
  __int128 v17; // [rsp+54h] [rbp-65h]
  __int128 v18; // [rsp+64h] [rbp-55h]
  __int128 v19; // [rsp+74h] [rbp-45h]
  __int128 v20; // [rsp+84h] [rbp-35h]
  __int128 v21; // [rsp+94h] [rbp-25h]
  __int128 v22; // [rsp+A4h] [rbp-15h]
  __int128 v23; // [rsp+B4h] [rbp-5h]
  __int128 v24; // [rsp+C4h] [rbp+Bh]
  int v25; // [rsp+D4h] [rbp+1Bh]

  pvData = 0;
  cbData = 0;
  DataFromUSPropVal = GetDataFromUSPropVal(a2, (const void **)&pvData, &cbData);
  v6 = DataFromUSPropVal;
  if ( DataFromUSPropVal >= 0 )
  {
    Key = JetMakeKey(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2), pvData, cbData, a3);
    v8 = Key;
    if ( g_fInProc && !dword_18010D924 )
    {
      if ( Key != -1414 )
      {
        cbData = Key;
        if ( Key >= 0 )
          return 0;
        v15 = 152;
        v25 = 0;
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v24 = 0;
        if ( (int)JetGetErrorInfoW(&cbData, &v15, 152, 1, 0) < 0 )
          goto LABEL_11;
        if ( DWORD1(v16) != 10 )
        {
          if ( DWORD1(v16) == 11 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetInconsistentError<unsigned long>(&pvData);
          }
          else if ( DWORD1(v16) == 12 )
          {
            LODWORD(pvData) = cbData;
            UnistoreTelemetry::JetFragmentationError<unsigned long>(&pvData);
          }
          goto LABEL_11;
        }
        if ( cbData == -1414 )
        {
LABEL_11:
          HresultFromJetError = MakeHresultFromJetError(v8);
          Log_UnistoreHREvent_0(
            HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1355);
          return HresultFromJetError;
        }
      }
      v11 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v8);
      if ( v11 >= 0 )
      {
        LODWORD(pvData) = v8;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&pvData);
        if ( (unsigned int)IsJetCorruptionError(v8) )
        {
          Log_AssertionEvent(
            v12,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            109);
          __int2c();
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v11,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          102);
      }
    }
    if ( v8 >= 0 )
      return 0;
    goto LABEL_11;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)DataFromUSPropVal,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    1326);
  Log_UnistoreHREvent_0(
    v6,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    1347);
  return v6;
}

```

## disassembly

```asm
0x18000f2f0  push    rbp
0x18000f2f2  push    rbx
0x18000f2f3  push    rsi
0x18000f2f4  push    rdi
0x18000f2f5  push    r14
0x18000f2f7  lea     rbp, [rsp-37h]
0x18000f2fc  sub     rsp, 0F0h
0x18000f303  mov     rax, cs:__security_cookie
0x18000f30a  xor     rax, rsp
0x18000f30d  mov     [rbp+57h+var_30], rax
0x18000f311  mov     rax, rdx
0x18000f314  mov     edi, r8d
0x18000f317  mov     rbx, rcx
0x18000f31a  lea     r8, [rsp+110h+cbData]; unsigned int *
0x18000f31f  xor     r14d, r14d
0x18000f322  lea     rdx, [rsp+110h+pvData]; void **
0x18000f327  mov     rcx, rax; struct _USPROPVAL *
0x18000f32a  mov     [rsp+110h+pvData], r14
0x18000f32f  mov     [rsp+110h+cbData], r14d
0x18000f334  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x18000f339  mov     esi, eax
0x18000f33b  test    eax, eax
0x18000f33d  js      loc_18000F446
0x18000f343  mov     r9d, [rsp+110h+cbData]; cbData
0x18000f348  mov     r8, [rsp+110h+pvData]; pvData
0x18000f34d  mov     rdx, [rbx+10h]; tableid
0x18000f351  mov     rcx, [rbx+8]; sesid
0x18000f355  mov     [rsp+110h+grbit], edi; grbit
0x18000f359  call    cs:__imp_JetMakeKey
0x18000f35f  cmp     cs:?g_fInProc@@3HA, r14d; int g_fInProc
0x18000f366  mov     ebx, eax
0x18000f368  jz      loc_18000F43E
0x18000f36e  cmp     cs:dword_18010D924, r14d
0x18000f375  jnz     loc_18000F43E
0x18000f37b  cmp     eax, 0FFFFFA7Ah
0x18000f380  jz      loc_18000F4B8
0x18000f386  mov     [rsp+110h+cbData], eax
0x18000f38a  test    eax, eax
0x18000f38c  jns     loc_18000F442
0x18000f392  xorps   xmm0, xmm0
0x18000f395  mov     [rbp+57h+var_D0], 98h
0x18000f39c  xor     eax, eax
0x18000f39e  mov     [rsp+110h+grbit], r14d
0x18000f3a3  mov     r9d, 1
0x18000f3a9  mov     [rbp+57h+var_3C], eax
0x18000f3ac  mov     r8d, 98h
0x18000f3b2  lea     rdx, [rbp+57h+var_D0]
0x18000f3b6  lea     rcx, [rsp+110h+cbData]
0x18000f3bb  movups  [rbp+57h+var_CC], xmm0
0x18000f3bf  movups  [rbp+57h+var_BC], xmm0
0x18000f3c3  movups  [rbp+57h+var_AC], xmm0
0x18000f3c7  movups  [rbp+57h+var_9C], xmm0
0x18000f3cb  movups  [rbp+57h+var_8C], xmm0
0x18000f3cf  movups  [rbp+57h+var_7C], xmm0
0x18000f3d3  movups  [rbp+57h+var_6C], xmm0
0x18000f3d7  movups  [rbp+57h+var_5C], xmm0
0x18000f3db  movups  [rbp+57h+var_4C], xmm0
0x18000f3df  call    cs:__imp_JetGetErrorInfoW
0x18000f3e5  test    eax, eax
0x18000f3e7  js      short loc_18000F403
0x18000f3e9  mov     ecx, dword ptr [rbp+57h+var_CC+4]
0x18000f3ec  sub     ecx, 0Ah
0x18000f3ef  jz      loc_18000F4AA
0x18000f3f5  sub     ecx, 1
0x18000f3f8  jz      loc_18000F493
0x18000f3fe  cmp     ecx, 1
0x18000f401  jz      short loc_18000F47C
0x18000f403  mov     ecx, ebx; int
0x18000f405  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000f40a  mov     r9d, 54Bh
0x18000f410  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f417  xor     edx, edx
0x18000f419  mov     ecx, eax
0x18000f41b  mov     ebx, eax
0x18000f41d  call    Log_UnistoreHREvent_0
0x18000f422  mov     eax, ebx
0x18000f424  mov     rcx, [rbp+57h+var_30]
0x18000f428  xor     rcx, rsp; StackCookie
0x18000f42b  call    __security_check_cookie
0x18000f430  add     rsp, 0F0h
0x18000f437  pop     r14
0x18000f439  pop     rdi
0x18000f43a  pop     rsi
0x18000f43b  pop     rbx
0x18000f43c  pop     rbp
0x18000f43d  retn
0x18000f43e  test    ebx, ebx
0x18000f440  js      short loc_18000F403
0x18000f442  xor     eax, eax
0x18000f444  jmp     short loc_18000F424
0x18000f446  mov     r9d, 52Eh
0x18000f44c  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f453  mov     edx, 1
0x18000f458  mov     ecx, esi
0x18000f45a  call    Log_UnistoreHREvent_0
0x18000f45f  mov     r9d, 543h
0x18000f465  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f46c  mov     edx, 1
0x18000f471  mov     ecx, esi
0x18000f473  call    Log_UnistoreHREvent_0
0x18000f478  mov     eax, esi
0x18000f47a  jmp     short loc_18000F424
0x18000f47c  mov     eax, [rsp+110h+cbData]
0x18000f480  lea     rcx, [rsp+110h+pvData]
0x18000f485  mov     dword ptr [rsp+110h+pvData], eax
0x18000f489  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000f48e  jmp     loc_18000F403
0x18000f493  mov     eax, [rsp+110h+cbData]
0x18000f497  lea     rcx, [rsp+110h+pvData]
0x18000f49c  mov     dword ptr [rsp+110h+pvData], eax
0x18000f4a0  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000f4a5  jmp     loc_18000F403
0x18000f4aa  cmp     [rsp+110h+cbData], 0FFFFFA7Ah
0x18000f4b2  jz      loc_18000F403
0x18000f4b8  mov     r9d, ebx; unsigned int
0x18000f4bb  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18000f4c2  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18000f4c9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f4d0  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000f4d5  test    eax, eax
0x18000f4d7  jns     short loc_18000F4F4
0x18000f4d9  mov     r9d, 66h ; 'f'
0x18000f4df  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f4e6  xor     edx, edx
0x18000f4e8  mov     ecx, eax
0x18000f4ea  call    Log_UnistoreHREvent_0
0x18000f4ef  jmp     loc_18000F43E
0x18000f4f4  lea     rcx, [rsp+110h+pvData]
0x18000f4f9  mov     dword ptr [rsp+110h+pvData], ebx
0x18000f4fd  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x18000f502  mov     ecx, ebx; int
0x18000f504  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18000f509  test    eax, eax
0x18000f50b  jz      loc_18000F43E
0x18000f511  mov     r8d, 6Dh ; 'm'
0x18000f517  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000f51e  call    Log_AssertionEvent
0x18000f523  int     2Ch; Windows NT - assertion failure
0x18000f525  jmp     loc_18000F43E
```
