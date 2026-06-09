# CSetupFilesCleanup::Purge(unsigned __int64,IEmptyVolumeCacheCallBack *)

- ea: `0x180005c30`
- end: `0x18000629e`
- name: `?Purge@CSetupFilesCleanup@@UEAAJ_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `1646`
- prototype: `__int64 __fastcall(CSetupFilesCleanup *this, __int64, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001178`
- `0x1800012ac`
- `0x18000166c`
- `0x180003be8`
- `0x1800040c0`
- `0x1800047ac`
- `0x180005b50`
- `0x180005c30`
- `0x180007e34`
- `0x18001200c`
- `0x1800131a2`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ffe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005d9f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005d9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061b8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006198`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061c1`
- `WDSCORE!CurrentIP` at `0x180005c9b`
- `WDSCORE!CurrentIP` at `0x180005db2`
- `WDSCORE!CurrentIP` at `0x180005e2d`
- `WDSCORE!CurrentIP` at `0x180005ea9`
- `WDSCORE!CurrentIP` at `0x180005f1d`
- `WDSCORE!CurrentIP` at `0x180005f92`
- `WDSCORE!CurrentIP` at `0x180006006`
- `WDSCORE!CurrentIP` at `0x180005c9b`
- `WDSCORE!CurrentIP` at `0x180005db2`
- `WDSCORE!CurrentIP` at `0x180005e2d`
- `WDSCORE!CurrentIP` at `0x180005ea9`
- `WDSCORE!CurrentIP` at `0x180005f1d`
- `WDSCORE!CurrentIP` at `0x180005f92`
- `WDSCORE!CurrentIP` at `0x180006006`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005cfb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005e11`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005e8d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005f0f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005f84`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005ff8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000606c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005cfb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005e11`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005e8d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005f0f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005f84`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005ff8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000606c`

## string_xrefs

- `0x180005dbb`: `CSetupFilesCleanup::Purge - RemoveUninstall Failed Hr= %x`

## pseudocode

```c
__int64 __fastcall CSetupFilesCleanup::Purge(
        CSetupFilesCleanup *this,
        __int64 a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  __int64 v3; // r12
  int v5; // r14d
  int v6; // r15d
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r13d
  int UninstallInterfaceCommon; // r15d
  int v13; // r12d
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  HANDLE MutexW; // rbx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  HMODULE v44; // [rsp+90h] [rbp-70h] BYREF
  HMODULE hLibModule; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v51[10]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v52[144]; // [rsp+120h] [rbp+20h] BYREF

  v43 = (__int64)a3;
  v3 = a2;
  v42 = a2;
  v5 = 0;
  memset_0(v51, 0, sizeof(v51));
  v46 = 0;
  v6 = 0;
  v44 = 0;
  v40 = 0;
  LastError = GetLastError();
  v8 = CurrentIP();
  v9 = ConstructPartialMsgW(
         0x4000000u,
         "CSetupFilesCleanup::Purge - Cleaning up  stuff for session: %s",
         *((const char **)this + 9));
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    617,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Purge",
    v8,
    LastError,
    0,
    0);
  v11 = CSetupFilesCleanup::MinimumBlockChecks(this);
  if ( !v11 )
  {
    if ( *((_DWORD *)this + 13) || *((_DWORD *)this + 6) )
    {
      v41 = 0;
      hLibModule = 0;
      UninstallInterfaceCommon = pGetUninstallInterfaceCommon(v10, &v41, &hLibModule);
      if ( UninstallInterfaceCommon >= 0 )
      {
        v13 = 1;
        if ( (**(unsigned int (__fastcall ***)(__int64))v41)(v41) )
        {
          if ( *((_DWORD *)this + 14) || (v13 = SetupRemoveUninstallWarning()) != 0 )
            UninstallInterfaceCommon = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 48LL))(v41);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 72LL))(v41);
        if ( hLibModule )
          FreeLibrary(hLibModule);
        if ( UninstallInterfaceCommon < 0 )
        {
          v14 = GetLastError();
          v15 = CurrentIP();
          v16 = ConstructPartialMsgW(
                  0x2000000u,
                  "CSetupFilesCleanup::Purge - RemoveUninstall Failed Hr= %x",
                  UninstallInterfaceCommon);
          WdsSetupLogMessageW(
            v16,
            0,
            L"D",
            0,
            661,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"CSetupFilesCleanup::Purge",
            v15,
            v14,
            0,
            0);
          v5 = UninstallInterfaceCommon;
        }
        if ( !v13 )
        {
          v17 = GetLastError();
          v18 = CurrentIP();
          v19 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::Purge - user selected no in the warning popup");
          WdsSetupLogMessageW(
            v19,
            0,
            L"D",
            0,
            667,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"CSetupFilesCleanup::Purge",
            v18,
            v17,
            0,
            0);
          v11 = 6;
LABEL_15:
          v3 = v42;
          v6 = v40;
          goto LABEL_16;
        }
        if ( v5 < 0 )
          goto LABEL_15;
        v3 = v42;
      }
    }
    v51[0] = 1;
    v51[2] = &v46;
    v51[3] = *((_QWORD *)this + 2);
    v51[4] = v43;
    v51[7] = &v44;
    v51[8] = *((_QWORD *)this + 10);
    v51[1] = 0;
    v51[6] = v3;
    v51[9] = 0;
    MutexW = CreateMutexW(0, 1, L"Global\\Microsoft.Windows.Setup.SetupCln");
    v5 = CSetupFilesCleanup::CleanVolume(this, (struct _SETUPCLN_PARAMS *)v51);
    if ( MutexW )
    {
      ReleaseMutex(MutexW);
      CloseHandle(MutexW);
    }
    v6 = 1;
  }
LABEL_16:
  v20 = GetLastError();
  v21 = CurrentIP();
  v22 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::Purge - Space Requested to be freed: %llu", v3);
  WdsSetupLogMessageW(
    v22,
    0,
    L"D",
    0,
    701,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Purge",
    v21,
    v20,
    0,
    0);
  v23 = GetLastError();
  v24 = CurrentIP();
  v25 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::Purge - Space Freed: %llu", v44);
  WdsSetupLogMessageW(
    v25,
    0,
    L"D",
    0,
    702,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Purge",
    v24,
    v23,
    0,
    0);
  v26 = GetLastError();
  v27 = CurrentIP();
  v28 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::Purge - Return status: %x", v5);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    703,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Purge",
    v27,
    v26,
    0,
    0);
  v29 = GetLastError();
  v30 = CurrentIP();
  v31 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::Purge - Block status: %d", v11);
  WdsSetupLogMessageW(
    v31,
    0,
    L"D",
    0,
    704,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Purge",
    v30,
    v29,
    0,
    0);
  if ( *((_QWORD *)this + 10) )
  {
    if ( (unsigned int)dword_18001F018 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v43 = (__int64)_TlgCVGetter::_TlgCVGetter(
                       (_TlgCVGetter *)v52,
                       *((struct TraceLoggingCorrelationVector **)this + 10));
      hLibModule = v44;
      v48 = *((_QWORD *)this + 8);
      v49 = *((_QWORD *)this + 9);
      v50[0] = 0x80000000LL;
      v40 = v5;
      LODWORD(v42) = v11;
      LODWORD(v41) = v6;
      v47 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v32,
        (unsigned int)word_18001B722,
        v33,
        v34,
        (__int64)v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&hLibModule,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v43);
    }
  }
  else if ( (unsigned int)dword_18001F018 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v50[0] = v44;
    v48 = *((_QWORD *)this + 8);
    v47 = *((_QWORD *)this + 9);
    v43 = 0x80000000LL;
    LODWORD(v41) = v5;
    LODWORD(v42) = v11;
    v40 = v6;
    v49 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v36,
      (unsigned int)byte_18001B669,
      v37,
      v38,
      (__int64)&v43,
      (__int64)&v47,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)v50,
      (__int64)&v40,
      (__int64)&v42,
      (__int64)&v41);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005c30  mov     [rsp-8+arg_18], rbx
0x180005c35  push    rbp
0x180005c36  push    rsi
0x180005c37  push    rdi
0x180005c38  push    r12
0x180005c3a  push    r13
0x180005c3c  push    r14
0x180005c3e  push    r15
0x180005c40  lea     rbp, [rsp-0C0h]
0x180005c48  sub     rsp, 1C0h
0x180005c4f  mov     rax, cs:__security_cookie
0x180005c56  xor     rax, rsp
0x180005c59  mov     [rbp+0F0h+var_40], rax
0x180005c60  xor     r13d, r13d
0x180005c63  mov     [rbp+0F0h+var_168], r8
0x180005c67  mov     r12, rdx
0x180005c6a  mov     [rbp+0F0h+var_170], rdx
0x180005c6e  mov     rsi, rcx
0x180005c71  xor     edx, edx; Val
0x180005c73  lea     rcx, [rbp+0F0h+var_120]; void *
0x180005c77  mov     r14d, r13d
0x180005c7a  lea     r8d, [r13+50h]; Size
0x180005c7e  call    memset_0
0x180005c83  mov     [rbp+0F0h+var_150], r13d
0x180005c87  mov     r15d, r13d
0x180005c8a  mov     [rbp+0F0h+var_160], r13
0x180005c8e  mov     [rsp+1F0h+var_180], r13d
0x180005c93  call    cs:__imp_GetLastError
0x180005c99  mov     edi, eax
0x180005c9b  call    cs:__imp_CurrentIP
0x180005ca1  mov     r8, [rsi+48h]
0x180005ca5  lea     rdx, aCsetupfilescle_2; "CSetupFilesCleanup::Purge - Cleaning up"...
0x180005cac  mov     ecx, 4000000h; unsigned int
0x180005cb1  mov     rbx, rax
0x180005cb4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005cb9  mov     dword ptr [rsp+1F0h+var_1A0], r13d
0x180005cbe  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005cc5  mov     [rsp+1F0h+var_1A8], r13
0x180005cca  lea     r8, aD; "D"
0x180005cd1  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005cd5  xor     r9d, r9d
0x180005cd8  mov     [rsp+1F0h+var_1B8], rbx
0x180005cdd  xor     edx, edx
0x180005cdf  mov     [rsp+1F0h+var_1C0], rcx
0x180005ce4  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005ceb  mov     [rsp+1F0h+var_1C8], rcx
0x180005cf0  mov     rcx, rax
0x180005cf3  mov     dword ptr [rsp+1F0h+var_1D0], 269h
0x180005cfb  call    cs:__imp_WdsSetupLogMessageW
0x180005d01  mov     rcx, rsi; this
0x180005d04  call    ?MinimumBlockChecks@CSetupFilesCleanup@@QEAAKXZ; CSetupFilesCleanup::MinimumBlockChecks(void)
0x180005d09  xor     edi, edi
0x180005d0b  mov     r13d, eax
0x180005d0e  test    eax, eax
0x180005d10  jnz     loc_180005EA1
0x180005d16  cmp     [rsi+34h], edi
0x180005d19  jnz     short loc_180005D24
0x180005d1b  cmp     [rsi+18h], edi
0x180005d1e  jz      loc_18000614E
0x180005d24  lea     r8, [rbp+0F0h+hLibModule]
0x180005d28  mov     [rsp+1F0h+var_178], rdi
0x180005d2d  lea     rdx, [rsp+1F0h+var_178]
0x180005d32  mov     [rbp+0F0h+hLibModule], rdi
0x180005d36  call    pGetUninstallInterfaceCommon
0x180005d3b  mov     r15d, eax
0x180005d3e  test    eax, eax
0x180005d40  js      loc_18000614E
0x180005d46  mov     rcx, [rsp+1F0h+var_178]
0x180005d4b  mov     r12d, 1
0x180005d51  mov     rax, [rcx]
0x180005d54  mov     rax, [rax]
0x180005d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d5c  test    eax, eax
0x180005d5e  jz      short loc_180005D85
0x180005d60  cmp     [rsi+38h], edi
0x180005d63  jnz     short loc_180005D71
0x180005d65  call    SetupRemoveUninstallWarning
0x180005d6a  mov     r12d, eax
0x180005d6d  test    eax, eax
0x180005d6f  jz      short loc_180005D85
0x180005d71  mov     rcx, [rsp+1F0h+var_178]
0x180005d76  mov     rax, [rcx]
0x180005d79  mov     rax, [rax+30h]
0x180005d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d82  mov     r15d, eax
0x180005d85  mov     rcx, [rsp+1F0h+var_178]
0x180005d8a  mov     rax, [rcx]
0x180005d8d  mov     rax, [rax+48h]
0x180005d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d96  mov     rcx, [rbp+0F0h+hLibModule]; hLibModule
0x180005d9a  test    rcx, rcx
0x180005d9d  jz      short loc_180005DA5
0x180005d9f  call    cs:__imp_FreeLibrary
0x180005da5  test    r15d, r15d
0x180005da8  jns     short loc_180005E1C
0x180005daa  call    cs:__imp_GetLastError
0x180005db0  mov     edi, eax
0x180005db2  call    cs:__imp_CurrentIP
0x180005db8  mov     r8d, r15d
0x180005dbb  lea     rdx, aCsetupfilescle_14; "CSetupFilesCleanup::Purge - RemoveUnins"...
0x180005dc2  mov     ecx, 2000000h; unsigned int
0x180005dc7  mov     rbx, rax
0x180005dca  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005dcf  mov     dword ptr [rsp+1F0h+var_1A0], r14d
0x180005dd4  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005ddb  mov     [rsp+1F0h+var_1A8], r14
0x180005de0  lea     r8, aD; "D"
0x180005de7  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005deb  xor     r9d, r9d
0x180005dee  mov     [rsp+1F0h+var_1B8], rbx
0x180005df3  xor     edx, edx
0x180005df5  mov     [rsp+1F0h+var_1C0], rcx
0x180005dfa  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005e01  mov     [rsp+1F0h+var_1C8], rcx
0x180005e06  mov     rcx, rax
0x180005e09  mov     dword ptr [rsp+1F0h+var_1D0], 295h
0x180005e11  call    cs:__imp_WdsSetupLogMessageW
0x180005e17  xor     edi, edi
0x180005e19  mov     r14d, r15d
0x180005e1c  test    r12d, r12d
0x180005e1f  jnz     loc_180006141
0x180005e25  call    cs:__imp_GetLastError
0x180005e2b  mov     edi, eax
0x180005e2d  call    cs:__imp_CurrentIP
0x180005e33  lea     rdx, aCsetupfilescle_25; "CSetupFilesCleanup::Purge - user select"...
0x180005e3a  mov     ecx, 4000000h; unsigned int
0x180005e3f  mov     rbx, rax
0x180005e42  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005e47  mov     dword ptr [rsp+1F0h+var_1A0], r12d
0x180005e4c  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005e53  mov     [rsp+1F0h+var_1A8], 0
0x180005e5c  lea     r8, aD; "D"
0x180005e63  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005e67  xor     r9d, r9d
0x180005e6a  mov     [rsp+1F0h+var_1B8], rbx
0x180005e6f  xor     edx, edx
0x180005e71  mov     [rsp+1F0h+var_1C0], rcx
0x180005e76  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005e7d  mov     [rsp+1F0h+var_1C8], rcx
0x180005e82  mov     rcx, rax
0x180005e85  mov     dword ptr [rsp+1F0h+var_1D0], 29Bh
0x180005e8d  call    cs:__imp_WdsSetupLogMessageW
0x180005e93  lea     r13d, [r12+6]
0x180005e98  mov     r12, [rbp+0F0h+var_170]
0x180005e9c  mov     r15d, [rsp+1F0h+var_180]
0x180005ea1  call    cs:__imp_GetLastError
0x180005ea7  mov     edi, eax
0x180005ea9  call    cs:__imp_CurrentIP
0x180005eaf  mov     r8, r12
0x180005eb2  lea     rdx, aCsetupfilescle_10; "CSetupFilesCleanup::Purge - Space Reque"...
0x180005eb9  mov     ecx, 4000000h; unsigned int
0x180005ebe  mov     rbx, rax
0x180005ec1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005ec6  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x180005ece  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005ed5  mov     [rsp+1F0h+var_1A8], 0
0x180005ede  lea     r8, aD; "D"
0x180005ee5  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005ee9  xor     r9d, r9d
0x180005eec  mov     [rsp+1F0h+var_1B8], rbx
0x180005ef1  xor     edx, edx
0x180005ef3  mov     [rsp+1F0h+var_1C0], rcx
0x180005ef8  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005eff  mov     [rsp+1F0h+var_1C8], rcx
0x180005f04  mov     rcx, rax
0x180005f07  mov     dword ptr [rsp+1F0h+var_1D0], 2BDh
0x180005f0f  call    cs:__imp_WdsSetupLogMessageW
0x180005f15  call    cs:__imp_GetLastError
0x180005f1b  mov     edi, eax
0x180005f1d  call    cs:__imp_CurrentIP
0x180005f23  mov     r8, [rbp+0F0h+var_160]
0x180005f27  lea     rdx, aCsetupfilescle_7; "CSetupFilesCleanup::Purge - Space Freed"...
0x180005f2e  mov     ecx, 4000000h; unsigned int
0x180005f33  mov     rbx, rax
0x180005f36  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005f3b  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x180005f43  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005f4a  mov     [rsp+1F0h+var_1A8], 0
0x180005f53  lea     r8, aD; "D"
0x180005f5a  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005f5e  xor     r9d, r9d
0x180005f61  mov     [rsp+1F0h+var_1B8], rbx
0x180005f66  xor     edx, edx
0x180005f68  mov     [rsp+1F0h+var_1C0], rcx
0x180005f6d  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005f74  mov     [rsp+1F0h+var_1C8], rcx
0x180005f79  mov     rcx, rax
0x180005f7c  mov     dword ptr [rsp+1F0h+var_1D0], 2BEh
0x180005f84  call    cs:__imp_WdsSetupLogMessageW
0x180005f8a  call    cs:__imp_GetLastError
0x180005f90  mov     edi, eax
0x180005f92  call    cs:__imp_CurrentIP
0x180005f98  mov     r8d, r14d
0x180005f9b  lea     rdx, aCsetupfilescle_22; "CSetupFilesCleanup::Purge - Return stat"...
0x180005fa2  mov     ecx, 4000000h; unsigned int
0x180005fa7  mov     rbx, rax
0x180005faa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005faf  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x180005fb7  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180005fbe  mov     [rsp+1F0h+var_1A8], 0
0x180005fc7  lea     r8, aD; "D"
0x180005fce  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180005fd2  xor     r9d, r9d
0x180005fd5  mov     [rsp+1F0h+var_1B8], rbx
0x180005fda  xor     edx, edx
0x180005fdc  mov     [rsp+1F0h+var_1C0], rcx
0x180005fe1  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005fe8  mov     [rsp+1F0h+var_1C8], rcx
0x180005fed  mov     rcx, rax
0x180005ff0  mov     dword ptr [rsp+1F0h+var_1D0], 2BFh
0x180005ff8  call    cs:__imp_WdsSetupLogMessageW
0x180005ffe  call    cs:__imp_GetLastError
0x180006004  mov     edi, eax
0x180006006  call    cs:__imp_CurrentIP
0x18000600c  mov     r8d, r13d
0x18000600f  lea     rdx, aCsetupfilescle_0; "CSetupFilesCleanup::Purge - Block statu"...
0x180006016  mov     ecx, 4000000h; unsigned int
0x18000601b  mov     rbx, rax
0x18000601e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006023  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x18000602b  lea     rcx, aCsetupfilescle_23; "CSetupFilesCleanup::Purge"
0x180006032  mov     [rsp+1F0h+var_1A8], 0
0x18000603b  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18000603f  mov     [rsp+1F0h+var_1B8], rbx
0x180006044  mov     [rsp+1F0h+var_1C0], rcx
0x180006049  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006050  mov     [rsp+1F0h+var_1C8], rcx
0x180006055  lea     r8, aD; "D"
0x18000605c  mov     rcx, rax
0x18000605f  mov     dword ptr [rsp+1F0h+var_1D0], 2C0h
0x180006067  xor     r9d, r9d
0x18000606a  xor     edx, edx
0x18000606c  call    cs:__imp_WdsSetupLogMessageW
0x180006072  cmp     qword ptr [rsi+50h], 0
0x180006077  mov     eax, cs:dword_18001F018
0x18000607d  jz      loc_1800061D2
0x180006083  cmp     eax, 5
0x180006086  jbe     loc_180006271
0x18000608c  call    _tlgKeywordOn
0x180006091  test    al, al
0x180006093  jz      loc_180006271
0x180006099  mov     rdx, [rsi+50h]; struct TraceLoggingCorrelationVector *
0x18000609d  lea     rcx, [rbp+0F0h+var_D0]; this
0x1800060a1  call    ??0_TlgCVGetter@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; _TlgCVGetter::_TlgCVGetter(TraceLoggingCorrelationVector *)
0x1800060a6  mov     [rbp+0F0h+var_168], rax
0x1800060aa  lea     rdx, word_18001B722
0x1800060b1  mov     rax, [rbp+0F0h+var_160]
0x1800060b5  mov     [rbp+0F0h+hLibModule], rax
0x1800060b9  mov     rax, [rsi+40h]
0x1800060bd  mov     [rbp+0F0h+var_140], rax
0x1800060c1  mov     rax, [rsi+48h]
0x1800060c5  mov     [rbp+0F0h+var_138], rax
0x1800060c9  mov     eax, 80000000h
0x1800060ce  mov     [rbp+0F0h+var_130], rax
0x1800060d2  lea     rax, [rbp+0F0h+var_168]
0x1800060d6  mov     [rsp+1F0h+var_190], rax
0x1800060db  lea     rax, [rsp+1F0h+var_180]
0x1800060e0  mov     [rsp+1F0h+var_198], rax
0x1800060e5  lea     rax, [rbp+0F0h+var_170]
0x1800060e9  mov     [rsp+1F0h+var_1A0], rax
0x1800060ee  lea     rax, [rsp+1F0h+var_178]
0x1800060f3  mov     [rsp+1F0h+var_1A8], rax
0x1800060f8  lea     rax, [rbp+0F0h+hLibModule]
0x1800060fc  mov     [rsp+1F0h+var_1B0], rax
0x180006101  lea     rax, [rbp+0F0h+var_148]
0x180006105  mov     [rsp+1F0h+var_1B8], rax
0x18000610a  lea     rax, [rbp+0F0h+var_140]
0x18000610e  mov     [rsp+1F0h+var_1C0], rax
0x180006113  lea     rax, [rbp+0F0h+var_138]
0x180006117  mov     [rsp+1F0h+var_1C8], rax
0x18000611c  lea     rax, [rbp+0F0h+var_130]
0x180006120  mov     [rsp+1F0h+var_1D0], rax
0x180006125  mov     [rsp+1F0h+var_180], r14d
0x18000612a  mov     dword ptr [rbp+0F0h+var_170], r13d
0x18000612e  mov     dword ptr [rsp+1F0h+var_178], r15d
0x180006133  mov     [rbp+0F0h+var_148], r12
0x180006137  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U1@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@433AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000613c  jmp     loc_180006271
0x180006141  test    r14d, r14d
0x180006144  js      loc_180005E98
0x18000614a  mov     r12, [rbp+0F0h+var_170]
0x18000614e  lea     rax, [rbp+0F0h+var_150]
0x180006152  mov     [rbp+0F0h+var_120], 1
0x18000615a  mov     [rbp+0F0h+var_110], rax
0x18000615e  lea     r8, Name; "Global\\Microsoft.Windows.Setup.SetupCl"...
0x180006165  mov     rax, [rsi+10h]
0x180006169  mov     edx, 1; bInitialOwner
0x18000616e  mov     [rbp+0F0h+var_108], rax
0x180006172  xor     ecx, ecx; lpMutexAttributes
0x180006174  mov     rax, [rbp+0F0h+var_168]
0x180006178  mov     [rbp+0F0h+var_100], rax
0x18000617c  lea     rax, [rbp+0F0h+var_160]
0x180006180  mov     [rbp+0F0h+var_E8], rax
0x180006184  mov     rax, [rsi+50h]
0x180006188  mov     [rbp+0F0h+var_E0], rax
0x18000618c  mov     [rbp+0F0h+var_118], rdi
0x180006190  mov     [rbp+0F0h+var_F0], r12
0x180006194  mov     [rbp+0F0h+var_D8], rdi
0x180006198  call    cs:__imp_CreateMutexW
0x18000619e  lea     rdx, [rbp+0F0h+var_120]; struct _SETUPCLN_PARAMS *
  ... truncated ...
```
