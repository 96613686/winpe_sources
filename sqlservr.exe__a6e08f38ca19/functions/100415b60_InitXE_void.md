# InitXE(void)

- ea: `0x100415b60`
- end: `0x100415df2`
- name: `?InitXE@@YAXXZ`
- size: `658`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x100412470`

## callees

- `0x100415b60`
- `0x1004403d0`
- `0x10044c280`
- `0x10044c6c0`

## import_xrefs

- `sqlmin!?GetSingletonXEFeatureSwitchObserver@@YAPEAVXE_IFeatureSwitchesObserver@@XZ` at `0x100415d56`
- `sqlmin!?GetSingletonXEFeatureSwitchObserver@@YAPEAVXE_IFeatureSwitchesObserver@@XZ` at `0x100415d56`
- `sqlmin!?XDBGetBlobList@@YAHPEB_WPEA_WPEAUFCBBlobPathList@@PEAUListDirectoryStats@@PEBUFCBFileBaseDirectives@@@Z` at `0x100415c6b`
- `sqlmin!?DBCloseHandle@@YAHPEAX@Z` at `0x100415c60`
- `sqlmin!?DBGetFileSize@@YAKPEAXPEAK@Z` at `0x100415c55`
- `sqlmin!?DBChangeFileSize@@YAHPEAX_K@Z` at `0x100415c4a`
- `sqlmin!?DBReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z` at `0x100415c3f`
- `sqlmin!?DBWriteFile@@YAHPEAXPEBXKPEAKPEAU_OVERLAPPED@@@Z` at `0x100415c33`
- `sqlmin!?IsXStorePathPrefix@FileMgr@@SA_NPEB_W_K@Z` at `0x100415c1b`
- `sqllang!??1XESQLContext@@QEAA@XZ` at `0x100415db2`
- `sqllang!??1XESQLContext@@QEAA@XZ` at `0x100415db2`
- `sqllang!?XEIsOperationAborted@@YAHXZ` at `0x100415d1b`
- `sqllang!?XECheckSessionFilters@@YAHAEBUXESessionProperties@@@Z` at `0x100415d08`
- `sqllang!?XESQLXDBMultiTenantCanonicalizePath@@YAHPEA_WPEB_WHH@Z` at `0x100415d0f`
- `sqllang!?XESQLPathIsURL@@YAHPEB_W@Z` at `0x100415cc3`
- `sqllang!?XESQLURLCombine@@YAHPEA_W_KPEB_W2@Z` at `0x100415cb8`
- `sqllang!?XESQLPathCombine@@YAHPEA_W_KPEB_W2@Z` at `0x100415cad`
- `sqllang!?XESQLPathFindFileName@@YAHPEB_WPEA_W_K@Z` at `0x100415ca2`
- `sqllang!?XESQLPathFindExtension@@YAHPEB_WPEA_W_K@Z` at `0x100415c97`
- `sqllang!?XESQLPathRemoveFileSpec@@YAHPEB_WPEA_W_K@Z` at `0x100415c8c`
- `sqllang!?XESQLPathRemoveBackslash@@YAHPEA_W_K@Z` at `0x100415c81`
- `sqllang!?XESQLPathRemoveExtension@@YAHPEA_W_K@Z` at `0x100415c76`
- `sqllang!?XESQLCanonicalizePath@@YAHPEA_WPEB_W@Z` at `0x100415ce6`
- `sqllang!?XESQLLogMessage@@YAXQEBUXELogMessage@@PEAX@Z` at `0x100415ccf`
- `sqllang!?XESQLSetupThreadContext@@YAHW4XEThreadType@@P6AXPEAX@Z11@Z` at `0x100415bfc`
- `sqllang!?Create@XESQLContext@@SAPEAV1@PEAVIMemObj@@@Z` at `0x100415bea`
- `sqllang!?Create@XESQLContext@@SAPEAV1@PEAVIMemObj@@@Z` at `0x100415bea`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100415d8a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100415bcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100415bcf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100415dc0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100415dc0`
- `sqldk!SystemThread_TlsOffset` at `0x100415bb4`
- `sqldk!SystemThread_TlsIndex` at `0x100415bab`

## pseudocode

```c
void InitXE(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  struct XESQLContext *v2; // rax
  XESQLContext *v3; // rsi
  _DWORD (*v4)(wchar_t *, const wchar_t *, _DWORD, _DWORD); // rcx
  void (__fastcall ***v5)(_QWORD, struct XE_IFeatureSwitchesObserver *); // rbx
  void (__fastcall **v6)(_QWORD, struct XE_IFeatureSwitchesObserver *); // rdi
  struct XE_IFeatureSwitchesObserver *SingletonXEFeatureSwitchObserver; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v9; // [rsp+28h] [rbp-D8h]
  __int16 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h]
  void (*v12)(const struct XELogMessage *const, void *); // [rsp+40h] [rbp-C0h]
  void *(__fastcall *v13)(const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *); // [rsp+48h] [rbp-B8h]
  struct XESQLContext *v14; // [rsp+50h] [rbp-B0h]
  _DWORD (*v15)(wchar_t *, const wchar_t *); // [rsp+58h] [rbp-A8h]
  unsigned int (*v16)(void); // [rsp+60h] [rbp-A0h]
  bool (*v17)(const wchar_t *, unsigned __int64); // [rsp+68h] [rbp-98h]
  void *(__fastcall *v18)(const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *, const struct FCBFileDirectives *); // [rsp+70h] [rbp-90h]
  _DWORD (*v19)(void *, const void *, unsigned int, unsigned int *, struct _OVERLAPPED *); // [rsp+78h] [rbp-88h]
  _DWORD (*v20)(void *, void *, unsigned int, unsigned int *, struct _OVERLAPPED *); // [rsp+80h] [rbp-80h]
  _DWORD (*v21)(void *, unsigned __int64); // [rsp+88h] [rbp-78h]
  unsigned int (*v22)(void *, unsigned int *); // [rsp+90h] [rbp-70h]
  _DWORD (*v23)(void *); // [rsp+98h] [rbp-68h]
  _DWORD (*v24)(const wchar_t *, wchar_t *, struct FCBBlobPathList *, struct ListDirectoryStats *, const struct FCBFileBaseDirectives *); // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  _DWORD (*v26)(wchar_t *, unsigned __int64); // [rsp+B0h] [rbp-50h]
  _DWORD (*v27)(wchar_t *, unsigned __int64); // [rsp+B8h] [rbp-48h]
  _DWORD (*v28)(const wchar_t *, wchar_t *, unsigned __int64); // [rsp+C0h] [rbp-40h]
  _DWORD (*v29)(const wchar_t *, wchar_t *, unsigned __int64); // [rsp+C8h] [rbp-38h]
  _DWORD (*v30)(const wchar_t *, wchar_t *, unsigned __int64); // [rsp+D0h] [rbp-30h]
  _DWORD (*v31)(wchar_t *, unsigned __int64, const wchar_t *, const wchar_t *); // [rsp+D8h] [rbp-28h]
  _DWORD (*v32)(wchar_t *, unsigned __int64, const wchar_t *, const wchar_t *); // [rsp+E0h] [rbp-20h]
  _DWORD (*v33)(const wchar_t *); // [rsp+E8h] [rbp-18h]
  _DWORD (*v34)(wchar_t *, const wchar_t *, _DWORD, _DWORD); // [rsp+F0h] [rbp-10h]
  _DWORD (*v35)(const struct XESessionProperties *); // [rsp+F8h] [rbp-8h]
  _DWORD (*v36)(void); // [rsp+100h] [rbp+0h]
  void (__fastcall *v37)(const wchar_t *, char **); // [rsp+108h] [rbp+8h]
  __int64 v38; // [rsp+110h] [rbp+10h]
  char v39; // [rsp+140h] [rbp+40h] BYREF
  char v40; // [rsp+148h] [rbp+48h] BYREF

  v8[0] = 655370;
  v9 = 10;
  v8[1] = 1310738;
  if ( !(unsigned int)XE_API::Initialize(0, (const struct XEEngineVersion *)v8) )
    goto LABEL_14;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = XESQLContext::Create(*(struct IMemObj **)(*(_QWORD *)(v1 + 992) + 320LL));
  v3 = v2;
  if ( !v2 )
  {
LABEL_13:
    sub_10044C6C0();
    scierrlog(0x6406u);
LABEL_14:
    scierrlog(0x6407u);
    return;
  }
  v13 = XEDBCreateFileW;
  v16 = XEGetConnectionLocaleId;
  v17 = FileMgr::IsXStorePathPrefix;
  v18 = XEXDBCreateFileW;
  v19 = DBWriteFile;
  v20 = DBReadFile;
  v21 = DBChangeFileSize;
  v22 = DBGetFileSize;
  v23 = DBCloseHandle;
  v24 = XDBGetBlobList;
  v26 = XESQLPathRemoveExtension;
  v27 = XESQLPathRemoveBackslash;
  v28 = XESQLPathRemoveFileSpec;
  v29 = XESQLPathFindExtension;
  v30 = XESQLPathFindFileName;
  v31 = XESQLPathCombine;
  v32 = XESQLURLCombine;
  v11 = XESQLSetupThreadContext;
  v33 = XESQLPathIsURL;
  v12 = XESQLLogMessage;
  v15 = XESQLCanonicalizePath;
  v4 = 0;
  v25 = 0;
  v10 = 10;
  v14 = v2;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
    v4 = XESQLXDBMultiTenantCanonicalizePath;
  v35 = XECheckSessionFilters;
  v36 = XEIsOperationAborted;
  v37 = SOSLogToErrorLogV;
  v34 = v4;
  v38 = 0;
  if ( !(unsigned int)qword_1004A9530(&v10) )
  {
LABEL_12:
    XESQLContext::~XESQLContext(v3);
    operator delete(v3, 8u);
    goto LABEL_13;
  }
  v5 = (void (__fastcall ***)(_QWORD, struct XE_IFeatureSwitchesObserver *))qword_1004A96D8();
  v6 = *v5;
  SingletonXEFeatureSwitchObserver = GetSingletonXEFeatureSwitchObserver();
  (*v6)(v5, SingletonXEFeatureSwitchObserver);
  if ( !(unsigned int)qword_1004A9670(8 * (*(_BYTE *)(qword_10049F340 + 1213) & 1u) + 16, &v39)
    || CommonGlobalState::m_CollectingStatistics && !(unsigned int)qword_1004A9668(14, &v40) )
  {
    qword_1004A9540();
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x100415b60  mov     [rsp-8+arg_10], rbx
0x100415b65  push    rbp
0x100415b66  push    rsi
0x100415b67  push    rdi
0x100415b68  lea     rbp, [rsp-20h]
0x100415b6d  sub     rsp, 120h
0x100415b74  mov     edi, 0Ah
0x100415b79  mov     [rsp+130h+var_110], 0A000Ah
0x100415b81  lea     rdx, [rsp+130h+var_110]; struct XEEngineVersion *
0x100415b86  mov     [rsp+130h+var_108], di
0x100415b8b  xor     ecx, ecx; enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption)
0x100415b8d  mov     [rsp+130h+var_10C], 140012h
0x100415b95  call    ?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z; XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)
0x100415b9a  test    eax, eax
0x100415b9c  jz      loc_100415DD5
0x100415ba2  mov     rdx, gs:58h
0x100415bab  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100415bb2  mov     ecx, [rax]
0x100415bb4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100415bbb  mov     ebx, [rax]
0x100415bbd  add     rbx, [rdx+rcx*8]
0x100415bc1  mov     rax, [rbx+100h]
0x100415bc8  test    rax, rax
0x100415bcb  jnz     short loc_100415BDC
0x100415bcd  xor     ecx, ecx
0x100415bcf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100415bd5  mov     rax, [rbx+100h]
0x100415bdc  mov     rax, [rax+3E0h]
0x100415be3  mov     rcx, [rax+140h]
0x100415bea  call    cs:__imp_?Create@XESQLContext@@SAPEAV1@PEAVIMemObj@@@Z; XESQLContext::Create(IMemObj *)
0x100415bf0  mov     rsi, rax
0x100415bf3  test    rax, rax
0x100415bf6  jz      loc_100415DC6
0x100415bfc  mov     rcx, cs:__imp_?XESQLSetupThreadContext@@YAHW4XEThreadType@@P6AXPEAX@Z11@Z; XESQLSetupThreadContext(XEThreadType,void (*)(void *),void *,void *)
0x100415c03  lea     rax, ?XEDBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; XEDBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x100415c0a  mov     [rsp+130h+var_E8], rax
0x100415c0f  lea     rax, ?XEGetConnectionLocaleId@@YAKXZ; XEGetConnectionLocaleId(void)
0x100415c16  mov     [rsp+130h+var_D0], rax
0x100415c1b  mov     rax, cs:__imp_?IsXStorePathPrefix@FileMgr@@SA_NPEB_W_K@Z; FileMgr::IsXStorePathPrefix(wchar_t const *,unsigned __int64)
0x100415c22  mov     [rsp+130h+var_C8], rax
0x100415c27  lea     rax, ?XEXDBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z; XEXDBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,FCBFileDirectives const *)
0x100415c2e  mov     [rsp+130h+var_C0], rax
0x100415c33  mov     rax, cs:__imp_?DBWriteFile@@YAHPEAXPEBXKPEAKPEAU_OVERLAPPED@@@Z; DBWriteFile(void *,void const *,ulong,ulong *,_OVERLAPPED *)
0x100415c3a  mov     [rsp+130h+var_B8], rax
0x100415c3f  mov     rax, cs:__imp_?DBReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; DBReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x100415c46  mov     [rbp+30h+var_B0], rax
0x100415c4a  mov     rax, cs:__imp_?DBChangeFileSize@@YAHPEAX_K@Z; DBChangeFileSize(void *,unsigned __int64)
0x100415c51  mov     [rbp+30h+var_A8], rax
0x100415c55  mov     rax, cs:__imp_?DBGetFileSize@@YAKPEAXPEAK@Z; DBGetFileSize(void *,ulong *)
0x100415c5c  mov     [rbp+30h+var_A0], rax
0x100415c60  mov     rax, cs:__imp_?DBCloseHandle@@YAHPEAX@Z; DBCloseHandle(void *)
0x100415c67  mov     [rbp+30h+var_98], rax
0x100415c6b  mov     rax, cs:__imp_?XDBGetBlobList@@YAHPEB_WPEA_WPEAUFCBBlobPathList@@PEAUListDirectoryStats@@PEBUFCBFileBaseDirectives@@@Z; XDBGetBlobList(wchar_t const *,wchar_t *,FCBBlobPathList *,ListDirectoryStats *,FCBFileBaseDirectives const *)
0x100415c72  mov     [rbp+30h+var_90], rax
0x100415c76  mov     rax, cs:__imp_?XESQLPathRemoveExtension@@YAHPEA_W_K@Z; XESQLPathRemoveExtension(wchar_t *,unsigned __int64)
0x100415c7d  mov     [rbp+30h+var_80], rax
0x100415c81  mov     rax, cs:__imp_?XESQLPathRemoveBackslash@@YAHPEA_W_K@Z; XESQLPathRemoveBackslash(wchar_t *,unsigned __int64)
0x100415c88  mov     [rbp+30h+var_78], rax
0x100415c8c  mov     rax, cs:__imp_?XESQLPathRemoveFileSpec@@YAHPEB_WPEA_W_K@Z; XESQLPathRemoveFileSpec(wchar_t const *,wchar_t *,unsigned __int64)
0x100415c93  mov     [rbp+30h+var_70], rax
0x100415c97  mov     rax, cs:__imp_?XESQLPathFindExtension@@YAHPEB_WPEA_W_K@Z; XESQLPathFindExtension(wchar_t const *,wchar_t *,unsigned __int64)
0x100415c9e  mov     [rbp+30h+var_68], rax
0x100415ca2  mov     rax, cs:__imp_?XESQLPathFindFileName@@YAHPEB_WPEA_W_K@Z; XESQLPathFindFileName(wchar_t const *,wchar_t *,unsigned __int64)
0x100415ca9  mov     [rbp+30h+var_60], rax
0x100415cad  mov     rax, cs:__imp_?XESQLPathCombine@@YAHPEA_W_KPEB_W2@Z; XESQLPathCombine(wchar_t *,unsigned __int64,wchar_t const *,wchar_t const *)
0x100415cb4  mov     [rbp+30h+var_58], rax
0x100415cb8  mov     rax, cs:__imp_?XESQLURLCombine@@YAHPEA_W_KPEB_W2@Z; XESQLURLCombine(wchar_t *,unsigned __int64,wchar_t const *,wchar_t const *)
0x100415cbf  mov     [rbp+30h+var_50], rax
0x100415cc3  mov     rax, cs:__imp_?XESQLPathIsURL@@YAHPEB_W@Z; XESQLPathIsURL(wchar_t const *)
0x100415cca  mov     [rsp+130h+var_F8], rcx
0x100415ccf  mov     rcx, cs:__imp_?XESQLLogMessage@@YAXQEBUXELogMessage@@PEAX@Z; XESQLLogMessage(XELogMessage const * const,void *)
0x100415cd6  mov     [rbp+30h+var_48], rax
0x100415cda  mov     rax, cs:qword_10049F360
0x100415ce1  mov     [rsp+130h+var_F0], rcx
0x100415ce6  mov     rcx, cs:__imp_?XESQLCanonicalizePath@@YAHPEA_WPEB_W@Z; XESQLCanonicalizePath(wchar_t *,wchar_t const *)
0x100415ced  mov     [rsp+130h+var_D8], rcx
0x100415cf2  xor     ecx, ecx
0x100415cf4  mov     [rbp+30h+var_88], rcx
0x100415cf8  mov     [rsp+130h+var_100], di
0x100415cfd  mov     [rsp+130h+var_E0], rsi
0x100415d02  cmp     [rax+38A8h], ecx
0x100415d08  mov     rax, cs:__imp_?XECheckSessionFilters@@YAHAEBUXESessionProperties@@@Z; XECheckSessionFilters(XESessionProperties const &)
0x100415d0f  cmovnz  rcx, cs:__imp_?XESQLXDBMultiTenantCanonicalizePath@@YAHPEA_WPEB_WHH@Z; XESQLXDBMultiTenantCanonicalizePath(wchar_t *,wchar_t const *,int,int)
0x100415d17  mov     [rbp+30h+var_38], rax
0x100415d1b  mov     rax, cs:__imp_?XEIsOperationAborted@@YAHXZ; XEIsOperationAborted(void)
0x100415d22  mov     [rbp+30h+var_30], rax
0x100415d26  lea     rax, ?SOSLogToErrorLogV@@YAXPEB_WAEAPEAD@Z; SOSLogToErrorLogV(wchar_t const *,char * &)
0x100415d2d  mov     [rbp+30h+var_28], rax
0x100415d31  xor     eax, eax
0x100415d33  mov     [rbp+30h+var_40], rcx
0x100415d37  lea     rcx, [rsp+130h+var_100]
0x100415d3c  mov     [rbp+30h+var_20], rax
0x100415d40  call    cs:qword_1004A9530
0x100415d46  test    eax, eax
0x100415d48  jz      short loc_100415DAF
0x100415d4a  call    cs:qword_1004A96D8
0x100415d50  mov     rbx, rax
0x100415d53  mov     rdi, [rax]
0x100415d56  call    cs:__imp_?GetSingletonXEFeatureSwitchObserver@@YAPEAVXE_IFeatureSwitchesObserver@@XZ; GetSingletonXEFeatureSwitchObserver(void)
0x100415d5c  mov     rdx, rax
0x100415d5f  mov     rcx, rbx
0x100415d62  call    qword ptr [rdi]
0x100415d64  mov     rax, cs:qword_10049F340
0x100415d6b  lea     rdx, [rbp+30h+arg_0]
0x100415d6f  movzx   ecx, byte ptr [rax+4BDh]
0x100415d76  and     ecx, 1
0x100415d79  lea     ecx, ds:10h[rcx*8]
0x100415d80  call    cs:qword_1004A9670
0x100415d86  test    eax, eax
0x100415d88  jz      short loc_100415DA9
0x100415d8a  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100415d91  cmp     byte ptr [rax], 0
0x100415d94  jz      short loc_100415DDF
0x100415d96  lea     rdx, [rbp+30h+arg_8]
0x100415d9a  mov     ecx, 0Eh
0x100415d9f  call    cs:qword_1004A9668
0x100415da5  test    eax, eax
0x100415da7  jnz     short loc_100415DDF
0x100415da9  call    cs:qword_1004A9540
0x100415daf  mov     rcx, rsi
0x100415db2  call    cs:__imp_??1XESQLContext@@QEAA@XZ; XESQLContext::~XESQLContext(void)
0x100415db8  mov     edx, 8
0x100415dbd  mov     rcx, rsi
0x100415dc0  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100415dc6  call    sub_10044C6C0
0x100415dcb  mov     ecx, 6406h; unsigned int
0x100415dd0  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100415dd5  mov     ecx, 6407h; unsigned int
0x100415dda  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100415ddf  mov     rbx, [rsp+130h+arg_10]
0x100415de7  add     rsp, 120h
0x100415dee  pop     rdi
0x100415def  pop     rsi
0x100415df0  pop     rbp
0x100415df1  retn
```
