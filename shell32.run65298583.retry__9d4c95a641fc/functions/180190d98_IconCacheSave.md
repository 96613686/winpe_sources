# IconCacheSave

- ea: `0x180190d98`
- end: `0x180191096`
- name: `IconCacheSave`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18046b930`

## callees

- `0x18000f5a4`
- `0x180060798`
- `0x18007c6f0`
- `0x18007c7b8`
- `0x18007c808`
- `0x1800bc020`
- `0x18014c984`
- `0x1801903fc`
- `0x180190d98`
- `0x1801d71fc`
- `0x180233280`
- `0x1802342fc`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180191042`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180191042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180191051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180191051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180190e0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180190e0c`
- `USER32!GetSystemMetrics` at `0x180190e46`
- `USER32!GetSystemMetrics` at `0x180190e46`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180190f56`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180191017`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180190f56`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180191017`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180190e86`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180190e86`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180190e03`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180191048`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180190e03`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180191048`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_MaxIcons` at `0x180190e25`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_MaxIcons` at `0x180190e25`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180190f12`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180190f12`
- `SHLWAPI!__imp_SHGetCurColorRes` at `0x180190ee7`
- `SHLWAPI!__imp_SHGetCurColorRes` at `0x180190ee7`
- `Windows.Storage!QueryNewMaxIcons` at `0x180190e12`
- `Windows.Storage!QueryNewMaxIcons` at `0x180190e12`
- `Windows.Storage!GetSystemImageListBitDepth` at `0x180190ef1`
- `Windows.Storage!GetSystemImageListBitDepth` at `0x180190ef1`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x180190de9`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x180190de9`

## string_xrefs

- `0x180190dc3`: `SaveCache`

## pseudocode

```c
_BOOL8 IconCacheSave()
{
  HRESULT IconCachePath; // ebx
  struct _RTL_CRITICAL_SECTION *v1; // rax
  unsigned int v2; // edx
  int SystemImageListBitDepth; // ebx
  unsigned __int16 *v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  CIconCache *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rax
  IStream *pstm; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pv[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh]
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  _BYTE v20[56]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v21[42]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszFile[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  IconCachePath = 0;
  wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "SaveCache");
  v21[0] = &IconCacheTelemetry::SaveCache::`vftable';
  IconCacheTelemetry::SaveCache::StartActivity((IconCacheTelemetry::SaveCache *)v21);
  if ( (unsigned int)IsDesktopExplorerProcess() && g_fDirtyIcons )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
    EnterCriticalSection(v1);
    QueryNewMaxIcons();
    if ( (unsigned int)IconCacheReady() )
    {
      Global_WindowsStorage_MaxIcons();
      IconCachePath = GetIconCachePath(pszFile, v2);
      if ( IconCachePath >= 0 )
      {
        if ( GetSystemMetrics(67) )
          goto LABEL_19;
        pstm = 0;
        IconCachePath = SHCreateStreamOnFileEx(pszFile, 0x1021u, 2u, 1, 0, &pstm);
        if ( IconCachePath >= 0 )
        {
          v12 = 6291456;
          IconCachePath = ((__int64 (__fastcall *)(IStream *, __int64))pstm->lpVtbl->SetSize)(pstm, 6291456);
          if ( IconCachePath >= 0 )
          {
            memset_0(pv, 0, 0x48u);
            v15 = 879651159;
            v16 = 1287;
            v17 = 10586;
            v18 = SHGetCurColorRes();
            SystemImageListBitDepth = GetSystemImageListBitDepth();
            v5 = 0;
            v19 = SystemImageListBitDepth | ((unsigned int)IsBiDiLocalizedSystemEx(v4) != 0 ? 0x2000 : 0);
            v6 = 0;
            do
            {
              v7 = Global_WindowsStorage_Untyped_rgshil();
              (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *))(**(_QWORD **)(v7 + v6) + 128LL))(
                *(_QWORD *)(v7 + v6),
                &v20[v6],
                &v20[v6 + 4]);
              ++v5;
              v6 += 8;
            }
            while ( v5 != 6 );
            IconCachePath = IStream_Write(pstm, pv, 0x48u);
            if ( IconCachePath >= 0 )
            {
              IconCachePath = CIconCache::WriteLocations(v8, pstm);
              if ( IconCachePath >= 0 )
              {
                IconCachePath = ((__int64 (__fastcall *)(IStream *, _QWORD))pstm->lpVtbl->Commit)(pstm, 0);
                if ( IconCachePath >= 0 )
                {
                  v13 = 0;
                  if ( ((int (__fastcall *)(IStream *, __int64, __int64, __int64 *))pstm->lpVtbl->Seek)(
                         pstm,
                         g_li0,
                         1,
                         &v13) >= 0 )
                    ((void (__fastcall *)(IStream *, __int64))pstm->lpVtbl->SetSize)(pstm, v13);
                  IconCachePath = ((__int64 (__fastcall *)(IStream *, __int64, _QWORD, _QWORD))pstm->lpVtbl->Seek)(
                                    pstm,
                                    g_li0,
                                    0,
                                    0);
                  if ( IconCachePath >= 0 )
                  {
                    LODWORD(v12) = 72;
                    IconCachePath = IStream_Write(pstm, &v12, 4u);
                    if ( IconCachePath >= 0 )
                      g_fDirtyIcons = 0;
                  }
                }
              }
            }
          }
        }
        SafeRelease<IUpdatableItemSet>(&pstm);
        if ( IconCachePath < 0 )
LABEL_19:
          DeleteFileW(pszFile);
      }
    }
    v9 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
    LeaveCriticalSection(v9);
  }
  wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v21, 0);
  IconCacheTelemetry::SaveCache::~SaveCache((IconCacheTelemetry::SaveCache *)v21);
  return IconCachePath >= 0;
}

```

## disassembly

```asm
0x180190d98  mov     [rsp-8+arg_0], rbx
0x180190d9d  mov     [rsp-8+arg_8], rdi
0x180190da2  push    rbp
0x180190da3  lea     rbp, [rsp-310h]
0x180190dab  sub     rsp, 410h
0x180190db2  mov     rax, cs:__security_cookie
0x180190db9  xor     rax, rsp
0x180190dbc  mov     [rbp+310h+var_10], rax
0x180190dc3  lea     rdx, aSavecache; "SaveCache"
0x180190dca  xor     ebx, ebx
0x180190dcc  lea     rcx, [rbp+310h+var_370]
0x180190dd0  call    ??0?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180190dd5  lea     rax, ??_7SaveCache@IconCacheTelemetry@@6B@; const IconCacheTelemetry::SaveCache::`vftable'
0x180190ddc  lea     rcx, [rbp+310h+var_370]; this
0x180190de0  mov     [rbp+310h+var_370], rax
0x180190de4  call    ?StartActivity@SaveCache@IconCacheTelemetry@@QEAAXXZ; IconCacheTelemetry::SaveCache::StartActivity(void)
0x180190de9  call    cs:__imp_IsDesktopExplorerProcess
0x180190def  test    eax, eax
0x180190df1  jz      loc_180191057
0x180190df7  cmp     cs:?g_fDirtyIcons@@3HA, ebx; int g_fDirtyIcons
0x180190dfd  jz      loc_180191057
0x180190e03  call    cs:__imp_Global_WindowsStorage_csIconCache
0x180190e09  mov     rcx, rax; lpCriticalSection
0x180190e0c  call    cs:__imp_EnterCriticalSection
0x180190e12  call    cs:__imp_?QueryNewMaxIcons@@YAHXZ; QueryNewMaxIcons(void)
0x180190e18  call    ?IconCacheReady@@YAHXZ; IconCacheReady(void)
0x180190e1d  test    eax, eax
0x180190e1f  jz      loc_180191048
0x180190e25  call    cs:__imp_Global_WindowsStorage_MaxIcons
0x180190e2b  lea     rcx, [rbp+310h+pszFile]; pszPath
0x180190e32  call    ?GetIconCachePath@@YAJPEAGI@Z; GetIconCachePath(ushort *,uint)
0x180190e37  mov     ebx, eax
0x180190e39  test    eax, eax
0x180190e3b  js      loc_180191048
0x180190e41  mov     ecx, 43h ; 'C'; nIndex
0x180190e46  call    cs:__imp_GetSystemMetrics
0x180190e4c  lea     rcx, [rbp+310h+pszFile]; pszFile
0x180190e53  test    eax, eax
0x180190e55  jnz     loc_180191042
0x180190e5b  mov     r9d, 1; fCreate
0x180190e61  mov     [rsp+410h+pstm], 0
0x180190e6a  lea     rax, [rsp+410h+pstm]
0x180190e6f  mov     edx, 1021h; grfMode
0x180190e74  mov     [rsp+410h+ppstm], rax; ppstm
0x180190e79  mov     [rsp+410h+pstmTemplate], 0; pstmTemplate
0x180190e82  lea     r8d, [r9+1]; dwAttributes
0x180190e86  call    cs:__imp_SHCreateStreamOnFileEx
0x180190e8c  mov     ebx, eax
0x180190e8e  test    eax, eax
0x180190e90  js      loc_18019102D
0x180190e96  mov     rcx, [rsp+410h+pstm]
0x180190e9b  mov     [rsp+410h+var_3D8], 600000h
0x180190ea4  mov     rdx, [rsp+410h+var_3D8]
0x180190ea9  mov     rax, [rcx]
0x180190eac  mov     rax, [rax+30h]
0x180190eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190eb5  mov     ebx, eax
0x180190eb7  test    eax, eax
0x180190eb9  js      loc_18019102D
0x180190ebf  xor     edx, edx; Val
0x180190ec1  lea     rcx, [rsp+410h+pv]; void *
0x180190ec6  lea     r8d, [rdx+48h]; Size
0x180190eca  call    memset_0
0x180190ecf  mov     [rsp+410h+var_3BC], 346E6957h
0x180190ed7  mov     [rsp+410h+var_3B8], 507h
0x180190edf  mov     [rsp+410h+var_3B4], 295Ah
0x180190ee7  call    cs:__imp_SHGetCurColorRes
0x180190eed  mov     [rsp+410h+var_3B0], eax
0x180190ef1  call    cs:__imp_?GetSystemImageListBitDepth@@YAHXZ; GetSystemImageListBitDepth(void)
0x180190ef7  mov     ebx, eax
0x180190ef9  call    ?IsBiDiLocalizedSystemEx@@YAHPEAG@Z; IsBiDiLocalizedSystemEx(ushort *)
0x180190efe  neg     eax
0x180190f00  sbb     ecx, ecx
0x180190f02  xor     edi, edi
0x180190f04  and     ecx, 2000h
0x180190f0a  or      ecx, ebx
0x180190f0c  mov     [rsp+410h+var_3AC], ecx
0x180190f10  xor     ebx, ebx
0x180190f12  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x180190f18  lea     r8, [rsp+410h+var_3A4]
0x180190f1d  lea     rdx, [rsp+410h+var_3A8]
0x180190f22  add     r8, rbx
0x180190f25  add     rdx, rbx
0x180190f28  mov     rcx, [rax+rbx]
0x180190f2c  mov     rax, [rcx]
0x180190f2f  mov     rax, [rax+80h]
0x180190f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190f3b  inc     rdi
0x180190f3e  add     rbx, 8
0x180190f42  cmp     rdi, 6
0x180190f46  jnz     short loc_180190F12
0x180190f48  mov     rcx, [rsp+410h+pstm]; pstm
0x180190f4d  lea     r8d, [rdi+42h]; cb
0x180190f51  lea     rdx, [rsp+410h+pv]; pv
0x180190f56  call    cs:__imp_IStream_Write
0x180190f5c  mov     ebx, eax
0x180190f5e  test    eax, eax
0x180190f60  js      loc_18019102D
0x180190f66  mov     rdx, [rsp+410h+pstm]; struct IStream *
0x180190f6b  call    ?WriteLocations@CIconCache@@QEAAJPEAUIStream@@@Z; CIconCache::WriteLocations(IStream *)
0x180190f70  mov     ebx, eax
0x180190f72  test    eax, eax
0x180190f74  js      loc_18019102D
0x180190f7a  mov     rcx, [rsp+410h+pstm]
0x180190f7f  xor     edx, edx
0x180190f81  mov     rax, [rcx]
0x180190f84  mov     rax, [rax+40h]
0x180190f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190f8d  mov     ebx, eax
0x180190f8f  test    eax, eax
0x180190f91  js      loc_18019102D
0x180190f97  mov     rcx, [rsp+410h+pstm]
0x180190f9c  lea     r9, [rsp+410h+var_3D0]
0x180190fa1  mov     rdx, cs:g_li0
0x180190fa8  lea     r8d, [rdi-5]
0x180190fac  mov     [rsp+410h+var_3D0], 0
0x180190fb5  mov     rax, [rcx]
0x180190fb8  mov     rax, [rax+28h]
0x180190fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190fc1  test    eax, eax
0x180190fc3  js      short loc_180190FDB
0x180190fc5  mov     rcx, [rsp+410h+pstm]
0x180190fca  mov     rdx, [rsp+410h+var_3D0]
0x180190fcf  mov     rax, [rcx]
0x180190fd2  mov     rax, [rax+30h]
0x180190fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190fdb  mov     rcx, [rsp+410h+pstm]
0x180190fe0  xor     r9d, r9d
0x180190fe3  mov     rdx, cs:g_li0
0x180190fea  xor     r8d, r8d
0x180190fed  mov     rax, [rcx]
0x180190ff0  mov     rax, [rax+28h]
0x180190ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190ff9  mov     ebx, eax
0x180190ffb  test    eax, eax
0x180190ffd  js      short loc_18019102D
0x180190fff  mov     rcx, [rsp+410h+pstm]; pstm
0x180191004  lea     rdx, [rsp+410h+var_3D8]; pv
0x180191009  mov     r8d, 4; cb
0x18019100f  mov     dword ptr [rsp+410h+var_3D8], 48h ; 'H'
0x180191017  call    cs:__imp_IStream_Write
0x18019101d  mov     ebx, eax
0x18019101f  test    eax, eax
0x180191021  js      short loc_18019102D
0x180191023  mov     cs:?g_fDirtyIcons@@3HA, 0; int g_fDirtyIcons
0x18019102d  lea     rcx, [rsp+410h+pstm]
0x180191032  call    ??$SafeRelease@UIUpdatableItemSet@@@@YAXPEAPEAUIUpdatableItemSet@@@Z; SafeRelease<IUpdatableItemSet>(IUpdatableItemSet * *)
0x180191037  test    ebx, ebx
0x180191039  jns     short loc_180191048
0x18019103b  lea     rcx, [rbp+310h+pszFile]; lpFileName
0x180191042  call    cs:__imp_DeleteFileW
0x180191048  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18019104e  mov     rcx, rax; lpCriticalSection
0x180191051  call    cs:__imp_LeaveCriticalSection
0x180191057  xor     edx, edx
0x180191059  lea     rcx, [rbp+310h+var_370]
0x18019105d  call    ?Stop@?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180191062  not     ebx
0x180191064  lea     rcx, [rbp+310h+var_370]; this
0x180191068  shr     ebx, 1Fh
0x18019106b  call    ??1SaveCache@IconCacheTelemetry@@QEAA@XZ; IconCacheTelemetry::SaveCache::~SaveCache(void)
0x180191070  mov     eax, ebx
0x180191072  mov     rcx, [rbp+310h+var_10]
0x180191079  xor     rcx, rsp; StackCookie
0x18019107c  call    __security_check_cookie
0x180191081  lea     r11, [rsp+410h+var_s0]
0x180191089  mov     rbx, [r11+10h]
0x18019108d  mov     rdi, [r11+18h]
0x180191091  mov     rsp, r11
0x180191094  pop     rbp
0x180191095  retn
```
