# CStringSrv::CacheResStrings(ulong)

- ea: `0x180055cd4`
- end: `0x180055f0f`
- name: `?CacheResStrings@CStringSrv@@CAJK@Z`
- size: `571`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800564cc`

## callees

- `0x18000a870`
- `0x18000a914`
- `0x18000ba8c`
- `0x180053890`
- `0x180055cd4`
- `0x180056604`
- `0x180056994`
- `0x180056cf0`
- `0x180057018`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055e8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055e8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055d4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055d4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055ef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055ef7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055d1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055d1f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055d29`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055d33`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055d29`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055d33`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055d67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055e75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055eee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055d67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055e75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d9f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180055de9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180055de9`

## string_xrefs

- `0x180055d7b`: `WLIDRes.DLL`
- `0x180055ed2`: `CStringSrv::CacheResStrings`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStringSrv::CacheResStrings(DWORD a1)
{
  signed int v2; // edi
  struct CReadWriteLockEx *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // r15
  __int64 v5; // rax
  HMODULE v6; // rbp
  signed int LastError; // eax
  const char *v8; // rax
  unsigned int v9; // r8d
  int UserDefaultUILanguage; // ecx
  int v11; // eax
  signed int v12; // r14d
  __int64 v13; // rcx
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF
  char v16; // [rsp+80h] [rbp+18h] BYREF
  struct CReadWriteLockEx *v17; // [rsp+88h] [rbp+20h]

  v2 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v15);
  if ( a1 != CStringSrv::m_LCIDLoaded || !CStringSrv::m_LCIDLoaded )
  {
    v3 = CStringSrv::m_pRWLock;
    v17 = CStringSrv::m_pRWLock;
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)CStringSrv::m_pRWLock + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)CStringSrv::m_pRWLock + 32));
    ResetEvent(*((HANDLE *)v3 + 3));
    ResetEvent(*((HANDLE *)v3 + 2));
    _InterlockedIncrement((volatile signed __int32 *)v3 + 2);
    if ( *((int *)v3 + 3) > 0 )
      WaitForSingleObject(*((HANDLE *)v3 + 2), 0xFFFFFFFF);
    if ( a1 == CStringSrv::m_LCIDLoaded && CStringSrv::m_LCIDLoaded )
    {
      _InterlockedDecrement((volatile signed __int32 *)v3 + 2);
      SetEvent(*((HANDLE *)v3 + 3));
      LeaveCriticalSection(v4);
    }
    else
    {
      v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             (__int64)&v16,
             (__int64)L"WLIDRes.DLL");
      v6 = (HMODULE)CStringSrv::OpenResourceDll(v5);
      if ( v6 )
        goto LABEL_30;
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_30:
        if ( !a1
          || !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                              &v15,
                              v6,
                              6022,
                              (unsigned __int16)a1) )
        {
          UserDefaultUILanguage = GetUserDefaultUILanguage();
          v11 = 1033;
          if ( a1 != UserDefaultUILanguage )
            v11 = UserDefaultUILanguage;
          a1 = v11;
        }
        ATL::CAtlMap<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&CStringSrv::mapCache);
        v12 = 0;
        while ( 1 )
        {
          if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                                &v15,
                                v6,
                                *((unsigned int *)&g_rgResStringIDs + v12),
                                (unsigned __int16)a1) )
          {
            a1 = 1033;
            if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                                  &v15,
                                  v6,
                                  *((unsigned int *)&g_rgResStringIDs + v12),
                                  1033) )
              break;
          }
          ATL::CAtlMap<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::SetAt(
            v13,
            *((unsigned int *)&g_rgResStringIDs + v12++),
            v15);
          if ( (unsigned int)v12 >= 0x67 )
          {
            CStringSrv::m_LCIDLoaded = a1;
            _InterlockedDecrement((volatile signed __int32 *)v3 + 2);
            SetEvent(*((HANDLE *)v3 + 3));
            LeaveCriticalSection(v4);
            goto LABEL_23;
          }
        }
        v2 = -2147023084;
        v8 = "fRet";
        v9 = 135;
      }
      else
      {
        v8 = "hr = HRESULT_FROM_WIN32(GetLastError())";
        v9 = 105;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\stringsrv.cpp",
        "CStringSrv::CacheResStrings",
        v9,
        v2,
        v8);
      _InterlockedDecrement((volatile signed __int32 *)v3 + 2);
      SetEvent(*((HANDLE *)v3 + 3));
      LeaveCriticalSection(v4);
      ATL::CAtlMap<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&CStringSrv::mapCache);
LABEL_23:
      if ( v6 )
        FreeLibrary(v6);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180055cd4  mov     [rsp+arg_0], rbx
0x180055cd9  push    rbp
0x180055cda  push    rsi
0x180055cdb  push    rdi
0x180055cdc  push    r12
0x180055cde  push    r13
0x180055ce0  push    r14
0x180055ce2  push    r15
0x180055ce4  sub     rsp, 30h
0x180055ce8  mov     esi, ecx
0x180055cea  xor     edi, edi
0x180055cec  lea     rcx, [rsp+68h+arg_8]
0x180055cf1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180055cf6  nop
0x180055cf7  mov     eax, cs:?m_LCIDLoaded@CStringSrv@@0KA; ulong CStringSrv::m_LCIDLoaded
0x180055cfd  cmp     esi, eax
0x180055cff  jnz     short loc_180055D09
0x180055d01  test    eax, eax
0x180055d03  jnz     loc_180055E93
0x180055d09  mov     rbx, cs:?m_pRWLock@CStringSrv@@0PEAVCReadWriteLockEx@@EA; CReadWriteLockEx * CStringSrv::m_pRWLock
0x180055d10  mov     [rsp+68h+arg_18], rbx
0x180055d18  lea     r15, [rbx+20h]
0x180055d1c  mov     rcx, r15; lpCriticalSection
0x180055d1f  call    cs:__imp_EnterCriticalSection
0x180055d25  mov     rcx, [rbx+18h]; hEvent
0x180055d29  call    cs:__imp_ResetEvent
0x180055d2f  mov     rcx, [rbx+10h]; hEvent
0x180055d33  call    cs:__imp_ResetEvent
0x180055d39  lock inc dword ptr [rbx+8]
0x180055d3d  cmp     dword ptr [rbx+0Ch], 0
0x180055d41  jle     short loc_180055D51
0x180055d43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180055d46  mov     rcx, [rbx+10h]; hHandle
0x180055d4a  call    cs:__imp_WaitForSingleObject
0x180055d50  nop
0x180055d51  mov     eax, cs:?m_LCIDLoaded@CStringSrv@@0KA; ulong CStringSrv::m_LCIDLoaded
0x180055d57  cmp     esi, eax
0x180055d59  jnz     short loc_180055D7B
0x180055d5b  test    eax, eax
0x180055d5d  jz      short loc_180055D7B
0x180055d5f  lock dec dword ptr [rbx+8]
0x180055d63  mov     rcx, [rbx+18h]; hEvent
0x180055d67  call    cs:__imp_SetEvent
0x180055d6d  mov     rcx, r15; lpCriticalSection
0x180055d70  call    cs:__imp_LeaveCriticalSection
0x180055d76  jmp     loc_180055E93
0x180055d7b  lea     rdx, aWlidresDll; "WLIDRes.DLL"
0x180055d82  lea     rcx, [rsp+68h+arg_10]
0x180055d8a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180055d8f  mov     rcx, rax
0x180055d92  call    ?OpenResourceDll@CStringSrv@@CAPEAUHINSTANCE__@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CStringSrv::OpenResourceDll(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180055d97  mov     rbp, rax
0x180055d9a  test    rax, rax
0x180055d9d  jnz     short loc_180055DCA
0x180055d9f  call    cs:__imp_GetLastError
0x180055da5  mov     edi, eax
0x180055da7  test    eax, eax
0x180055da9  jle     short loc_180055DB4
0x180055dab  movzx   edi, ax
0x180055dae  or      edi, 80070000h
0x180055db4  test    edi, edi
0x180055db6  jns     short loc_180055DCA
0x180055db8  lea     rax, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180055dbf  mov     r8d, 69h ; 'i'
0x180055dc5  jmp     loc_180055ECA
0x180055dca  test    esi, esi
0x180055dcc  jz      short loc_180055DE9
0x180055dce  movzx   r9d, si
0x180055dd2  mov     r8d, 1786h
0x180055dd8  mov     rdx, rbp
0x180055ddb  lea     rcx, [rsp+68h+arg_8]
0x180055de0  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@IG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint,ushort)
0x180055de5  test    eax, eax
0x180055de7  jnz     short loc_180055DFE
0x180055de9  call    cs:__imp_GetUserDefaultUILanguage
0x180055def  movzx   ecx, ax
0x180055df2  mov     eax, 409h
0x180055df7  cmp     esi, ecx
0x180055df9  cmovnz  eax, ecx
0x180055dfc  mov     esi, eax
0x180055dfe  lea     rcx, ?mapCache@CStringSrv@@0V?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@A; ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> CStringSrv::mapCache
0x180055e05  call    ?RemoveAll@?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180055e0a  xor     r14d, r14d
0x180055e0d  movsxd  r12, r14d
0x180055e10  lea     r13, ?g_rgResStringIDs@@3PAKA; ulong near * g_rgResStringIDs
0x180055e17  movzx   r9d, si
0x180055e1b  mov     r8d, [r13+r12*4+0]
0x180055e20  mov     rdx, rbp
0x180055e23  lea     rcx, [rsp+68h+arg_8]
0x180055e28  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@IG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint,ushort)
0x180055e2d  test    eax, eax
0x180055e2f  jnz     short loc_180055E4F
0x180055e31  mov     esi, 409h
0x180055e36  mov     r9d, esi
0x180055e39  mov     r8d, [r13+r12*4+0]
0x180055e3e  mov     rdx, rbp
0x180055e41  lea     rcx, [rsp+68h+arg_8]
0x180055e46  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@IG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint,ushort)
0x180055e4b  test    eax, eax
0x180055e4d  jz      short loc_180055EB8
0x180055e4f  mov     r8, [rsp+68h+arg_8]
0x180055e54  mov     edx, [r13+r12*4+0]
0x180055e59  call    ?SetAt@?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@KPEBG@Z; ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::SetAt(ulong,ushort const *)
0x180055e5e  inc     r14d
0x180055e61  cmp     r14d, 67h ; 'g'
0x180055e65  jb      short loc_180055E0D
0x180055e67  mov     cs:?m_LCIDLoaded@CStringSrv@@0KA, esi; ulong CStringSrv::m_LCIDLoaded
0x180055e6d  lock dec dword ptr [rbx+8]
0x180055e71  mov     rcx, [rbx+18h]; hEvent
0x180055e75  call    cs:__imp_SetEvent
0x180055e7b  mov     rcx, r15; lpCriticalSection
0x180055e7e  call    cs:__imp_LeaveCriticalSection
0x180055e84  test    rbp, rbp
0x180055e87  jz      short loc_180055E93
0x180055e89  mov     rcx, rbp; hLibModule
0x180055e8c  call    cs:__imp_FreeLibrary
0x180055e92  nop
0x180055e93  mov     rcx, [rsp+68h+arg_8]
0x180055e98  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180055e9c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180055ea1  mov     eax, edi
0x180055ea3  mov     rbx, [rsp+68h+arg_0]
0x180055ea8  add     rsp, 30h
0x180055eac  pop     r15
0x180055eae  pop     r14
0x180055eb0  pop     r13
0x180055eb2  pop     r12
0x180055eb4  pop     rdi
0x180055eb5  pop     rsi
0x180055eb6  pop     rbp
0x180055eb7  retn
0x180055eb8  mov     edi, 80070714h
0x180055ebd  lea     rax, aFret; "fRet"
0x180055ec4  mov     r8d, 87h; unsigned int
0x180055eca  mov     [rsp+68h+var_48], rax; char *
0x180055ecf  mov     r9d, edi; int
0x180055ed2  lea     rdx, aCstringsrvCach; "CStringSrv::CacheResStrings"
0x180055ed9  lea     rcx, aOnecoreuapDsEx_8; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180055ee0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180055ee5  nop
0x180055ee6  lock dec dword ptr [rbx+8]
0x180055eea  mov     rcx, [rbx+18h]; hEvent
0x180055eee  call    cs:__imp_SetEvent
0x180055ef4  mov     rcx, r15; lpCriticalSection
0x180055ef7  call    cs:__imp_LeaveCriticalSection
0x180055efd  lea     rcx, ?mapCache@CStringSrv@@0V?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@A; ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> CStringSrv::mapCache
0x180055f04  call    ?RemoveAll@?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180055f09  jmp     loc_180055E84
```
