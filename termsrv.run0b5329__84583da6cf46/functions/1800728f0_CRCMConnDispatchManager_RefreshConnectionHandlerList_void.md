# CRCMConnDispatchManager::RefreshConnectionHandlerList(void)

- ea: `0x1800728f0`
- end: `0x180072c75`
- name: `?RefreshConnectionHandlerList@CRCMConnDispatchManager@@AEAAJXZ`
- size: `901`
- prototype: `__int64 __fastcall(CRCMConnDispatchManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180072d50`

## callees

- `0x180009ee0`
- `0x18000a210`
- `0x18000d7d0`
- `0x180011f80`
- `0x180013150`
- `0x180026700`
- `0x1800279a8`
- `0x180027b44`
- `0x1800321f0`
- `0x1800330c4`
- `0x180049ff8`
- `0x180071770`
- `0x180072104`
- `0x1800723b8`
- `0x1800728f0`
- `0x180072d78`
- `0x180092f84`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072c18`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072c01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072c01`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180072b71`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180072b71`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180072bdb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180072bdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072970`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072970`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180072be9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180072be9`

## string_xrefs

- `0x1800729ac`: `OpenKey on REG_CONTROL_CONNECTIONHANDLER_LIST failed: 0x%x in %s`
- `0x180072bd4`: `%SystemRoot%\system32\ole32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRCMConnDispatchManager::RefreshConnectionHandlerList(CRCMConnDispatchManager *this)
{
  int v2; // eax
  signed int v3; // ebx
  int NextSubKey; // eax
  unsigned int v5; // edi
  unsigned __int16 *v6; // rsi
  int ConnectionHandler; // eax
  struct CConnectionHandlerItem *v8; // rdi
  int refreshed; // ebx
  __int64 v10; // rax
  struct CConnectionHandlerItem *v11; // rcx
  bool v12; // sf
  int v13; // eax
  int v14; // esi
  char *v15; // r14
  CConnectionHandlerItem *v16; // rdi
  HMODULE LibraryW; // rax
  HMODULE v18; // rdi
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v21; // [rsp+20h] [rbp-E0h]
  struct CConnectionHandlerItem *v22; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+74h] [rbp-8Ch]
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[24]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Dst[264]; // [rsp+A0h] [rbp-60h] BYREF

  v26[0] = &CRegistry::`vftable';
  v26[1] = 0;
  v27 = 0;
  v28 = 0;
  v29 = -1;
  v30 = -1;
  FileTime1 = 0;
  v24 = 0;
  v22 = 0;
  v32 = 0;
  v31 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = CRegistry::OpenKey(
         (CRegistry *)v26,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\ConnectionHandler",
         0x20019u,
         v21);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v3 < 0 )
    {
      _DbgPrintMessage(
        8,
        "OpenKey on REG_CONTROL_CONNECTIONHANDLER_LIST failed: 0x%x in %s",
        (unsigned int)v3,
        "CRCMConnDispatchManager::RefreshConnectionHandlerList");
      goto LABEL_44;
    }
  }
  v29 = 0;
  NextSubKey = CRegistry::GetNextSubKey((CRegistry *)v26, (unsigned __int16 **)&FileTime1, &v24);
  v5 = NextSubKey;
  if ( NextSubKey != 259 )
  {
    if ( NextSubKey )
    {
      if ( NextSubKey > 0 )
        v3 = (unsigned __int16)NextSubKey | 0x80070000;
      else
        v3 = NextSubKey;
      _DbgPrintMessage(
        8,
        "GetFirstSubKey failed: 0x%x in %s",
        (unsigned int)v3,
        "CRCMConnDispatchManager::RefreshConnectionHandlerList");
      goto LABEL_44;
    }
    do
    {
      v22 = 0;
      v6 = (unsigned __int16 *)FileTime1;
      ConnectionHandler = CRCMConnDispatchManager::FindConnectionHandler(this, *(unsigned __int16 **)&FileTime1, &v22);
      if ( ConnectionHandler < 0 )
      {
        if ( (_WORD)ConnectionHandler != 4312 )
          break;
        refreshed = CRCMConnDispatchManager::LoadConnectionHandler(this, v6, &v22);
        v11 = v22;
        if ( !refreshed )
          *((struct _FILETIME *)v22 + 204) = SystemTimeAsFileTime;
        if ( !v11 )
          goto LABEL_22;
        v10 = *(_QWORD *)v11;
      }
      else
      {
        v8 = v22;
        refreshed = CConnectionHandlerItem::RefreshHandler(v22);
        if ( !refreshed )
          *((struct _FILETIME *)v8 + 204) = SystemTimeAsFileTime;
        v10 = *(_QWORD *)v8;
        v11 = v8;
      }
      (*(void (__fastcall **)(struct CConnectionHandlerItem *))(v10 + 16))(v11);
LABEL_22:
      if ( refreshed < 0 )
        _DbgPrintMessage(4, "Failed to refresh/load handler %s, error 0x%x\n", (const char *)v6, refreshed);
      v5 = CRegistry::GetNextSubKey((CRegistry *)v26, (unsigned __int16 **)&FileTime1, &v24);
    }
    while ( !v5 );
  }
  v3 = 0;
  if ( v5 != 259 )
    v3 = v5;
  v12 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v12 = v3 < 0;
  }
  if ( v12 )
  {
    _DbgPrintMessage(
      8,
      "RefreshConnectionHandlerList failed: 0x%x in %s",
      (unsigned int)v3,
      "CRCMConnDispatchManager::RefreshConnectionHandlerList");
  }
  else
  {
    v13 = CRCMConnDispatchManager::LoadChildSessionListenerHandlers(this, &SystemTimeAsFileTime);
    v3 = v13;
    if ( v13 >= 0 )
    {
      FileTime1 = 0;
      v14 = 0;
      CAutoExclusiveLock::CAutoExclusiveLock(
        (CAutoExclusiveLock *)v33,
        (CRCMConnDispatchManager *)((char *)this + 1592));
      v15 = (char *)this + 1696;
      if ( (unsigned int)CListTree<CConnectionHandlerItem>::GetNextEntry(v15, 1, &v22) == 1 )
      {
        do
        {
          v16 = v22;
          FileTime1 = (FILETIME)*((_QWORD *)v22 + 204);
          if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) )
          {
            CListTree<CConnectionHandlerItem>::Remove(v15, v16);
            CConnectionHandlerItem::Uninitialize(v16);
            v14 = 1;
          }
          (*(void (__fastcall **)(CConnectionHandlerItem *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        while ( (unsigned int)CListTree<CConnectionHandlerItem>::GetNextEntry(v15, 0, &v22) == 1 );
        if ( v14 == 1 )
        {
          memset_0(Dst, 0, 0x208u);
          if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\ole32.dll", Dst, 0x104u) )
          {
            LibraryW = LoadLibraryW(Dst);
            v18 = LibraryW;
            if ( LibraryW )
            {
              ProcAddress = GetProcAddress(LibraryW, "CoFreeUnusedLibrariesEx");
              if ( ProcAddress )
                ((void (__fastcall *)(_QWORD, _QWORD))ProcAddress)(0, 0);
              FreeLibrary(v18);
            }
          }
        }
      }
      CAutoLock::Unlock((CAutoLock *)v33);
    }
    else
    {
      _DbgPrintMessage(
        8,
        "this->LoadHardcodedHandlers failed: 0x%x in %s",
        (unsigned int)v13,
        "CRCMConnDispatchManager::RefreshConnectionHandlerList");
    }
  }
LABEL_44:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v31);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v32);
  CRegistry::~CRegistry((CRegistry *)v26);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800728f0  mov     [rsp-8+arg_8], rbx
0x1800728f5  mov     [rsp-8+arg_10], rsi
0x1800728fa  push    rbp
0x1800728fb  push    rdi
0x1800728fc  push    r12
0x1800728fe  push    r14
0x180072900  push    r15
0x180072902  lea     rbp, [rsp-1C0h]
0x18007290a  sub     rsp, 2C0h
0x180072911  mov     rax, cs:__security_cookie
0x180072918  xor     rax, rsp
0x18007291b  mov     [rbp+1E0h+var_30], rax
0x180072922  mov     r14, rcx
0x180072925  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18007292c  mov     [rsp+2E0h+var_290], rax
0x180072931  xor     r15d, r15d
0x180072934  mov     [rsp+2E0h+var_288], r15
0x180072939  mov     [rsp+2E0h+var_280], r15d
0x18007293e  mov     [rsp+2E0h+var_278], r15
0x180072943  or      eax, 0FFFFFFFFh
0x180072946  mov     [rsp+2E0h+var_270], eax
0x18007294a  mov     [rsp+2E0h+var_26C], eax
0x18007294e  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], r15
0x180072953  mov     [rsp+2E0h+var_2A0], r15d
0x180072958  mov     [rsp+2E0h+var_2B0], r15
0x18007295d  mov     [rbp+1E0h+var_260], r15
0x180072961  mov     [rsp+2E0h+var_268], r15
0x180072966  mov     qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18007296b  lea     rcx, [rsp+2E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180072970  call    cs:__imp_GetSystemTimeAsFileTime
0x180072976  mov     r9d, 20019h; unsigned int
0x18007297c  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Ter"...
0x180072983  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18007298a  lea     rcx, [rsp+2E0h+var_290]; this
0x18007298f  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180072994  mov     ebx, eax
0x180072996  mov     r12d, 80070000h
0x18007299c  test    eax, eax
0x18007299e  jz      short loc_1800729CC
0x1800729a0  jle     short loc_1800729A8
0x1800729a2  movzx   ebx, ax
0x1800729a5  or      ebx, r12d
0x1800729a8  test    ebx, ebx
0x1800729aa  jns     short loc_1800729CC
0x1800729ac  lea     rdx, aOpenkeyOnRegCo; "OpenKey on REG_CONTROL_CONNECTIONHANDLE"...
0x1800729b3  mov     r8d, ebx
0x1800729b6  lea     r9, aCrcmconndispat_0; "CRCMConnDispatchManager::RefreshConnect"...
0x1800729bd  mov     ecx, 8; int
0x1800729c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800729c7  jmp     loc_180072C29
0x1800729cc  mov     [rsp+2E0h+var_270], r15d
0x1800729d1  lea     r8, [rsp+2E0h+var_2A0]; unsigned int *
0x1800729d6  lea     rdx, [rsp+2E0h+FileTime1]; unsigned __int16 **
0x1800729db  lea     rcx, [rsp+2E0h+var_290]; this
0x1800729e0  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x1800729e5  mov     edi, eax
0x1800729e7  cmp     eax, 103h
0x1800729ec  jz      loc_180072ACF
0x1800729f2  test    eax, eax
0x1800729f4  jz      short loc_180072A13
0x1800729f6  jg      short loc_1800729FC
0x1800729f8  mov     ebx, eax
0x1800729fa  jmp     short loc_180072A02
0x1800729fc  movzx   ebx, ax
0x1800729ff  or      ebx, r12d
0x180072a02  test    ebx, ebx
0x180072a04  jns     loc_180072ACF
0x180072a0a  lea     rdx, aGetfirstsubkey; "GetFirstSubKey failed: 0x%x in %s"
0x180072a11  jmp     short loc_1800729B3
0x180072a13  mov     [rsp+2E0h+var_2B0], r15
0x180072a18  lea     r8, [rsp+2E0h+var_2B0]; struct CConnectionHandlerItem **
0x180072a1d  mov     rsi, qword ptr [rsp+2E0h+FileTime1.dwLowDateTime]
0x180072a22  mov     rdx, rsi; unsigned __int16 *
0x180072a25  mov     rcx, r14; this
0x180072a28  call    ?FindConnectionHandler@CRCMConnDispatchManager@@AEAAJPEAGPEAPEAVCConnectionHandlerItem@@@Z; CRCMConnDispatchManager::FindConnectionHandler(ushort *,CConnectionHandlerItem * *)
0x180072a2d  test    eax, eax
0x180072a2f  js      short loc_180072A58
0x180072a31  mov     rdi, [rsp+2E0h+var_2B0]
0x180072a36  mov     rcx, rdi; this
0x180072a39  call    ?RefreshHandler@CConnectionHandlerItem@@QEAAJXZ; CConnectionHandlerItem::RefreshHandler(void)
0x180072a3e  mov     ebx, eax
0x180072a40  test    eax, eax
0x180072a42  jnz     short loc_180072A50
0x180072a44  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180072a49  mov     [rdi+660h], rax
0x180072a50  mov     rax, [rdi]
0x180072a53  mov     rcx, rdi
0x180072a56  jmp     short loc_180072A8D
0x180072a58  cmp     ax, 10D8h
0x180072a5c  jnz     short loc_180072ACF
0x180072a5e  lea     r8, [rsp+2E0h+var_2B0]; struct CConnectionHandlerItem **
0x180072a63  mov     rdx, rsi; unsigned __int16 *
0x180072a66  mov     rcx, r14; this
0x180072a69  call    ?LoadConnectionHandler@CRCMConnDispatchManager@@AEAAJPEAGPEAPEAVCConnectionHandlerItem@@@Z; CRCMConnDispatchManager::LoadConnectionHandler(ushort *,CConnectionHandlerItem * *)
0x180072a6e  mov     ebx, eax
0x180072a70  mov     rcx, [rsp+2E0h+var_2B0]
0x180072a75  test    eax, eax
0x180072a77  jnz     short loc_180072A85
0x180072a79  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180072a7e  mov     [rcx+660h], rax
0x180072a85  test    rcx, rcx
0x180072a88  jz      short loc_180072A96
0x180072a8a  mov     rax, [rcx]
0x180072a8d  mov     rax, [rax+10h]
0x180072a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a96  test    ebx, ebx
0x180072a98  jns     short loc_180072AB1
0x180072a9a  mov     r9d, ebx
0x180072a9d  mov     r8, rsi
0x180072aa0  lea     rdx, aFailedToRefres; "Failed to refresh/load handler %s, erro"...
0x180072aa7  mov     ecx, 4; int
0x180072aac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072ab1  lea     r8, [rsp+2E0h+var_2A0]; unsigned int *
0x180072ab6  lea     rdx, [rsp+2E0h+FileTime1]; unsigned __int16 **
0x180072abb  lea     rcx, [rsp+2E0h+var_290]; this
0x180072ac0  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x180072ac5  mov     edi, eax
0x180072ac7  test    eax, eax
0x180072ac9  jz      loc_180072A13
0x180072acf  mov     ebx, r15d
0x180072ad2  cmp     edi, 103h
0x180072ad8  cmovnz  ebx, edi
0x180072adb  test    ebx, ebx
0x180072add  jle     short loc_180072AE7
0x180072adf  movzx   ebx, bx
0x180072ae2  or      ebx, r12d
0x180072ae5  test    ebx, ebx
0x180072ae7  jns     short loc_180072AF5
0x180072ae9  lea     rdx, aRefreshconnect; "RefreshConnectionHandlerList failed: 0x"...
0x180072af0  jmp     loc_1800729B3
0x180072af5  lea     rdx, [rsp+2E0h+SystemTimeAsFileTime]; struct _FILETIME *
0x180072afa  mov     rcx, r14; this
0x180072afd  call    ?LoadChildSessionListenerHandlers@CRCMConnDispatchManager@@AEAAJPEAU_FILETIME@@@Z; CRCMConnDispatchManager::LoadChildSessionListenerHandlers(_FILETIME *)
0x180072b02  mov     ebx, eax
0x180072b04  test    eax, eax
0x180072b06  jns     short loc_180072B17
0x180072b08  mov     r8d, eax
0x180072b0b  lea     rdx, aThisLoadhardco; "this->LoadHardcodedHandlers failed: 0x%"...
0x180072b12  jmp     loc_1800729B6
0x180072b17  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], r15
0x180072b1c  mov     esi, r15d
0x180072b1f  lea     rdx, [r14+638h]; struct CResource *
0x180072b26  lea     rcx, [rbp+1E0h+var_258]; this
0x180072b2a  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180072b2f  nop
0x180072b30  add     r14, 6A0h
0x180072b37  lea     r8, [rsp+2E0h+var_2B0]
0x180072b3c  mov     r12d, 1
0x180072b42  mov     edx, r12d
0x180072b45  mov     rcx, r14
0x180072b48  call    ?GetNextEntry@?$CListTree@VCConnectionHandlerItem@@@@QEAAHHPEAPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::GetNextEntry(int,CConnectionHandlerItem * *)
0x180072b4d  cmp     eax, r12d
0x180072b50  jnz     loc_180072C1F
0x180072b56  mov     rdi, [rsp+2E0h+var_2B0]
0x180072b5b  mov     rax, [rdi+660h]
0x180072b62  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], rax
0x180072b67  lea     rdx, [rsp+2E0h+SystemTimeAsFileTime]; lpFileTime2
0x180072b6c  lea     rcx, [rsp+2E0h+FileTime1]; lpFileTime1
0x180072b71  call    cs:__imp_CompareFileTime
0x180072b77  test    eax, eax
0x180072b79  jz      short loc_180072B91
0x180072b7b  mov     rdx, rdi
0x180072b7e  mov     rcx, r14
0x180072b81  call    ?Remove@?$CListTree@VCConnectionHandlerItem@@@@QEAAHPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::Remove(CConnectionHandlerItem *)
0x180072b86  mov     rcx, rdi; this
0x180072b89  call    ?Uninitialize@CConnectionHandlerItem@@QEAAJXZ; CConnectionHandlerItem::Uninitialize(void)
0x180072b8e  mov     esi, r12d
0x180072b91  mov     rax, [rdi]
0x180072b94  mov     rcx, rdi
0x180072b97  mov     rax, [rax+10h]
0x180072b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ba0  lea     r8, [rsp+2E0h+var_2B0]
0x180072ba5  xor     edx, edx
0x180072ba7  mov     rcx, r14
0x180072baa  call    ?GetNextEntry@?$CListTree@VCConnectionHandlerItem@@@@QEAAHHPEAPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::GetNextEntry(int,CConnectionHandlerItem * *)
0x180072baf  cmp     eax, r12d
0x180072bb2  jz      short loc_180072B56
0x180072bb4  cmp     esi, r12d
0x180072bb7  jnz     short loc_180072C1F
0x180072bb9  xor     edx, edx; Val
0x180072bbb  mov     r8d, 208h; Size
0x180072bc1  lea     rcx, [rbp+1E0h+Dst]; void *
0x180072bc5  call    memset_0
0x180072bca  mov     r8d, 104h; nSize
0x180072bd0  lea     rdx, [rbp+1E0h+Dst]; lpDst
0x180072bd4  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\system32\\ole32.dll"
0x180072bdb  call    cs:__imp_ExpandEnvironmentStringsW
0x180072be1  test    eax, eax
0x180072be3  jz      short loc_180072C1F
0x180072be5  lea     rcx, [rbp+1E0h+Dst]; lpLibFileName
0x180072be9  call    cs:__imp_LoadLibraryW
0x180072bef  mov     rdi, rax
0x180072bf2  test    rax, rax
0x180072bf5  jz      short loc_180072C1F
0x180072bf7  lea     rdx, aCofreeunusedli_0; "CoFreeUnusedLibrariesEx"
0x180072bfe  mov     rcx, rax; hModule
0x180072c01  call    cs:__imp_GetProcAddress
0x180072c07  test    rax, rax
0x180072c0a  jz      short loc_180072C15
0x180072c0c  xor     edx, edx
0x180072c0e  xor     ecx, ecx
0x180072c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c15  mov     rcx, rdi; hLibModule
0x180072c18  call    cs:__imp_FreeLibrary
0x180072c1e  nop
0x180072c1f  lea     rcx, [rbp+1E0h+var_258]; this
0x180072c23  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180072c28  nop
0x180072c29  lea     rcx, [rsp+2E0h+var_268]; void *
0x180072c2e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180072c33  nop
0x180072c34  lea     rcx, [rbp+1E0h+var_260]; void *
0x180072c38  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180072c3d  nop
0x180072c3e  lea     rcx, [rsp+2E0h+var_290]; this
0x180072c43  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180072c48  mov     eax, ebx
0x180072c4a  mov     rcx, [rbp+1E0h+var_30]
0x180072c51  xor     rcx, rsp; StackCookie
0x180072c54  call    __security_check_cookie
0x180072c59  lea     r11, [rsp+2E0h+var_20]
0x180072c61  mov     rbx, [r11+38h]
0x180072c65  mov     rsi, [r11+40h]
0x180072c69  mov     rsp, r11
0x180072c6c  pop     r15
0x180072c6e  pop     r14
0x180072c70  pop     r12
0x180072c72  pop     rdi
0x180072c73  pop     rbp
0x180072c74  retn
```
