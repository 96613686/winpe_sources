# CRCMConnDispatchManager::RefreshConnectionHandlerList(void)

- ea: `0x180075e74`
- end: `0x18007621e`
- name: `?RefreshConnectionHandlerList@CRCMConnDispatchManager@@AEAAJXZ`
- size: `938`
- prototype: `__int64 __fastcall(CRCMConnDispatchManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180076300`

## callees

- `0x1800095a0`
- `0x180009940`
- `0x18000d210`
- `0x180012750`
- `0x1800139c0`
- `0x180027af0`
- `0x180028dd8`
- `0x180028f88`
- `0x180033f60`
- `0x180034e64`
- `0x18004c590`
- `0x180074ca8`
- `0x180075688`
- `0x18007593c`
- `0x180075e74`
- `0x180076328`
- `0x180096e14`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800761ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800761ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007619d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007619d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800760fb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800760fb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007616b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007616b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180075ef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180075ef4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007617f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007617f`

## string_xrefs

- `0x180075f36`: `OpenKey on REG_CONTROL_CONNECTIONHANDLER_LIST failed: 0x%x in %s`
- `0x180076164`: `%SystemRoot%\system32\ole32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180075e74  mov     [rsp-8+arg_8], rbx
0x180075e79  mov     [rsp-8+arg_10], rsi
0x180075e7e  push    rbp
0x180075e7f  push    rdi
0x180075e80  push    r12
0x180075e82  push    r14
0x180075e84  push    r15
0x180075e86  lea     rbp, [rsp-1C0h]
0x180075e8e  sub     rsp, 2C0h
0x180075e95  mov     rax, cs:__security_cookie
0x180075e9c  xor     rax, rsp
0x180075e9f  mov     [rbp+1E0h+var_30], rax
0x180075ea6  mov     r14, rcx
0x180075ea9  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180075eb0  mov     [rsp+2E0h+var_290], rax
0x180075eb5  xor     r15d, r15d
0x180075eb8  mov     [rsp+2E0h+var_288], r15
0x180075ebd  mov     [rsp+2E0h+var_280], r15d
0x180075ec2  mov     [rsp+2E0h+var_278], r15
0x180075ec7  or      eax, 0FFFFFFFFh
0x180075eca  mov     [rsp+2E0h+var_270], eax
0x180075ece  mov     [rsp+2E0h+var_26C], eax
0x180075ed2  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], r15
0x180075ed7  mov     [rsp+2E0h+var_2A0], r15d
0x180075edc  mov     [rsp+2E0h+var_2B0], r15
0x180075ee1  mov     [rbp+1E0h+var_260], r15
0x180075ee5  mov     [rsp+2E0h+var_268], r15
0x180075eea  mov     qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180075eef  lea     rcx, [rsp+2E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180075ef4  call    cs:__imp_GetSystemTimeAsFileTime
0x180075efb  nop     dword ptr [rax+rax+00h]
0x180075f00  mov     r9d, 20019h; unsigned int
0x180075f06  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Ter"...
0x180075f0d  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180075f14  lea     rcx, [rsp+2E0h+var_290]; this
0x180075f19  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180075f1e  mov     ebx, eax
0x180075f20  mov     r12d, 80070000h
0x180075f26  test    eax, eax
0x180075f28  jz      short loc_180075F56
0x180075f2a  jle     short loc_180075F32
0x180075f2c  movzx   ebx, ax
0x180075f2f  or      ebx, r12d
0x180075f32  test    ebx, ebx
0x180075f34  jns     short loc_180075F56
0x180075f36  lea     rdx, aOpenkeyOnRegCo; "OpenKey on REG_CONTROL_CONNECTIONHANDLE"...
0x180075f3d  mov     r8d, ebx
0x180075f40  lea     r9, aCrcmconndispat_0; "CRCMConnDispatchManager::RefreshConnect"...
0x180075f47  mov     ecx, 8; int
0x180075f4c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180075f51  jmp     loc_1800761D1
0x180075f56  mov     [rsp+2E0h+var_270], r15d
0x180075f5b  lea     r8, [rsp+2E0h+var_2A0]; unsigned int *
0x180075f60  lea     rdx, [rsp+2E0h+FileTime1]; unsigned __int16 **
0x180075f65  lea     rcx, [rsp+2E0h+var_290]; this
0x180075f6a  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x180075f6f  mov     edi, eax
0x180075f71  cmp     eax, 103h
0x180075f76  jz      loc_180076059
0x180075f7c  test    eax, eax
0x180075f7e  jz      short loc_180075F9D
0x180075f80  jg      short loc_180075F86
0x180075f82  mov     ebx, eax
0x180075f84  jmp     short loc_180075F8C
0x180075f86  movzx   ebx, ax
0x180075f89  or      ebx, r12d
0x180075f8c  test    ebx, ebx
0x180075f8e  jns     loc_180076059
0x180075f94  lea     rdx, aGetfirstsubkey; "GetFirstSubKey failed: 0x%x in %s"
0x180075f9b  jmp     short loc_180075F3D
0x180075f9d  mov     [rsp+2E0h+var_2B0], r15
0x180075fa2  lea     r8, [rsp+2E0h+var_2B0]; struct CConnectionHandlerItem **
0x180075fa7  mov     rsi, qword ptr [rsp+2E0h+FileTime1.dwLowDateTime]
0x180075fac  mov     rdx, rsi; unsigned __int16 *
0x180075faf  mov     rcx, r14; this
0x180075fb2  call    ?FindConnectionHandler@CRCMConnDispatchManager@@AEAAJPEAGPEAPEAVCConnectionHandlerItem@@@Z; CRCMConnDispatchManager::FindConnectionHandler(ushort *,CConnectionHandlerItem * *)
0x180075fb7  test    eax, eax
0x180075fb9  js      short loc_180075FE2
0x180075fbb  mov     rdi, [rsp+2E0h+var_2B0]
0x180075fc0  mov     rcx, rdi; this
0x180075fc3  call    ?RefreshHandler@CConnectionHandlerItem@@QEAAJXZ; CConnectionHandlerItem::RefreshHandler(void)
0x180075fc8  mov     ebx, eax
0x180075fca  test    eax, eax
0x180075fcc  jnz     short loc_180075FDA
0x180075fce  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180075fd3  mov     [rdi+660h], rax
0x180075fda  mov     rax, [rdi]
0x180075fdd  mov     rcx, rdi
0x180075fe0  jmp     short loc_180076017
0x180075fe2  cmp     ax, 10D8h
0x180075fe6  jnz     short loc_180076059
0x180075fe8  lea     r8, [rsp+2E0h+var_2B0]; struct CConnectionHandlerItem **
0x180075fed  mov     rdx, rsi; unsigned __int16 *
0x180075ff0  mov     rcx, r14; this
0x180075ff3  call    ?LoadConnectionHandler@CRCMConnDispatchManager@@AEAAJPEAGPEAPEAVCConnectionHandlerItem@@@Z; CRCMConnDispatchManager::LoadConnectionHandler(ushort *,CConnectionHandlerItem * *)
0x180075ff8  mov     ebx, eax
0x180075ffa  mov     rcx, [rsp+2E0h+var_2B0]
0x180075fff  test    eax, eax
0x180076001  jnz     short loc_18007600F
0x180076003  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180076008  mov     [rcx+660h], rax
0x18007600f  test    rcx, rcx
0x180076012  jz      short loc_180076020
0x180076014  mov     rax, [rcx]
0x180076017  mov     rax, [rax+10h]
0x18007601b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076020  test    ebx, ebx
0x180076022  jns     short loc_18007603B
0x180076024  mov     r9d, ebx
0x180076027  mov     r8, rsi
0x18007602a  lea     rdx, aFailedToRefres; "Failed to refresh/load handler %s, erro"...
0x180076031  mov     ecx, 4; int
0x180076036  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007603b  lea     r8, [rsp+2E0h+var_2A0]; unsigned int *
0x180076040  lea     rdx, [rsp+2E0h+FileTime1]; unsigned __int16 **
0x180076045  lea     rcx, [rsp+2E0h+var_290]; this
0x18007604a  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x18007604f  mov     edi, eax
0x180076051  test    eax, eax
0x180076053  jz      loc_180075F9D
0x180076059  mov     ebx, r15d
0x18007605c  cmp     edi, 103h
0x180076062  cmovnz  ebx, edi
0x180076065  test    ebx, ebx
0x180076067  jle     short loc_180076071
0x180076069  movzx   ebx, bx
0x18007606c  or      ebx, r12d
0x18007606f  test    ebx, ebx
0x180076071  jns     short loc_18007607F
0x180076073  lea     rdx, aRefreshconnect; "RefreshConnectionHandlerList failed: 0x"...
0x18007607a  jmp     loc_180075F3D
0x18007607f  lea     rdx, [rsp+2E0h+SystemTimeAsFileTime]; struct _FILETIME *
0x180076084  mov     rcx, r14; this
0x180076087  call    ?LoadChildSessionListenerHandlers@CRCMConnDispatchManager@@AEAAJPEAU_FILETIME@@@Z; CRCMConnDispatchManager::LoadChildSessionListenerHandlers(_FILETIME *)
0x18007608c  mov     ebx, eax
0x18007608e  test    eax, eax
0x180076090  jns     short loc_1800760A1
0x180076092  mov     r8d, eax
0x180076095  lea     rdx, aThisLoadhardco; "this->LoadHardcodedHandlers failed: 0x%"...
0x18007609c  jmp     loc_180075F40
0x1800760a1  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], r15
0x1800760a6  mov     esi, r15d
0x1800760a9  lea     rdx, [r14+638h]; struct CResource *
0x1800760b0  lea     rcx, [rbp+1E0h+var_258]; this
0x1800760b4  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800760b9  nop
0x1800760ba  add     r14, 6A0h
0x1800760c1  lea     r8, [rsp+2E0h+var_2B0]
0x1800760c6  mov     r12d, 1
0x1800760cc  mov     edx, r12d
0x1800760cf  mov     rcx, r14
0x1800760d2  call    ?GetNextEntry@?$CListTree@VCConnectionHandlerItem@@@@QEAAHHPEAPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::GetNextEntry(int,CConnectionHandlerItem * *)
0x1800760d7  cmp     eax, r12d
0x1800760da  jnz     loc_1800761C7
0x1800760e0  mov     rdi, [rsp+2E0h+var_2B0]
0x1800760e5  mov     rax, [rdi+660h]
0x1800760ec  mov     qword ptr [rsp+2E0h+FileTime1.dwLowDateTime], rax
0x1800760f1  lea     rdx, [rsp+2E0h+SystemTimeAsFileTime]; lpFileTime2
0x1800760f6  lea     rcx, [rsp+2E0h+FileTime1]; lpFileTime1
0x1800760fb  call    cs:__imp_CompareFileTime
0x180076102  nop     dword ptr [rax+rax+00h]
0x180076107  test    eax, eax
0x180076109  jz      short loc_180076121
0x18007610b  mov     rdx, rdi
0x18007610e  mov     rcx, r14
0x180076111  call    ?Remove@?$CListTree@VCConnectionHandlerItem@@@@QEAAHPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::Remove(CConnectionHandlerItem *)
0x180076116  mov     rcx, rdi; this
0x180076119  call    ?Uninitialize@CConnectionHandlerItem@@QEAAJXZ; CConnectionHandlerItem::Uninitialize(void)
0x18007611e  mov     esi, r12d
0x180076121  mov     rax, [rdi]
0x180076124  mov     rcx, rdi
0x180076127  mov     rax, [rax+10h]
0x18007612b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076130  lea     r8, [rsp+2E0h+var_2B0]
0x180076135  xor     edx, edx
0x180076137  mov     rcx, r14
0x18007613a  call    ?GetNextEntry@?$CListTree@VCConnectionHandlerItem@@@@QEAAHHPEAPEAVCConnectionHandlerItem@@@Z; CListTree<CConnectionHandlerItem>::GetNextEntry(int,CConnectionHandlerItem * *)
0x18007613f  cmp     eax, r12d
0x180076142  jz      short loc_1800760E0
0x180076144  cmp     esi, r12d
0x180076147  jnz     short loc_1800761C7
0x180076149  xor     edx, edx; Val
0x18007614b  mov     r8d, 208h; Size
0x180076151  lea     rcx, [rbp+1E0h+Dst]; void *
0x180076155  call    memset_0
0x18007615a  mov     r8d, 104h; nSize
0x180076160  lea     rdx, [rbp+1E0h+Dst]; lpDst
0x180076164  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\system32\\ole32.dll"
0x18007616b  call    cs:__imp_ExpandEnvironmentStringsW
0x180076172  nop     dword ptr [rax+rax+00h]
0x180076177  test    eax, eax
0x180076179  jz      short loc_1800761C7
0x18007617b  lea     rcx, [rbp+1E0h+Dst]; lpLibFileName
0x18007617f  call    cs:__imp_LoadLibraryW
0x180076186  nop     dword ptr [rax+rax+00h]
0x18007618b  mov     rdi, rax
0x18007618e  test    rax, rax
0x180076191  jz      short loc_1800761C7
0x180076193  lea     rdx, aCofreeunusedli_0; "CoFreeUnusedLibrariesEx"
0x18007619a  mov     rcx, rax; hModule
0x18007619d  call    cs:__imp_GetProcAddress
0x1800761a4  nop     dword ptr [rax+rax+00h]
0x1800761a9  test    rax, rax
0x1800761ac  jz      short loc_1800761B7
0x1800761ae  xor     edx, edx
0x1800761b0  xor     ecx, ecx
0x1800761b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761b7  mov     rcx, rdi; hLibModule
0x1800761ba  call    cs:__imp_FreeLibrary
0x1800761c1  nop     dword ptr [rax+rax+00h]
0x1800761c6  nop
0x1800761c7  lea     rcx, [rbp+1E0h+var_258]; this
0x1800761cb  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800761d0  nop
0x1800761d1  lea     rcx, [rsp+2E0h+var_268]; void *
0x1800761d6  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800761db  nop
0x1800761dc  lea     rcx, [rbp+1E0h+var_260]; void *
0x1800761e0  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800761e5  nop
0x1800761e6  lea     rcx, [rsp+2E0h+var_290]; this
0x1800761eb  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800761f0  mov     eax, ebx
0x1800761f2  mov     rcx, [rbp+1E0h+var_30]
0x1800761f9  xor     rcx, rsp; StackCookie
0x1800761fc  call    __security_check_cookie
0x180076201  lea     r11, [rsp+2E0h+var_20]
0x180076209  mov     rbx, [r11+38h]
0x18007620d  mov     rsi, [r11+40h]
0x180076211  mov     rsp, r11
0x180076214  pop     r15
0x180076216  pop     r14
0x180076218  pop     r12
0x18007621a  pop     rdi
0x18007621b  pop     rbp
0x18007621c  retn
```
