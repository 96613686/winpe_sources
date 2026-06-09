# IconCacheSave

- ea: `0x1801a393c`
- end: `0x1801a3c95`
- name: `IconCacheSave`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18049fc60`

## callees

- `0x18000fc30`
- `0x18002ff60`
- `0x1800300c0`
- `0x18003029c`
- `0x18004ea24`
- `0x1800ced54`
- `0x18015d52c`
- `0x1801a2fa4`
- `0x1801a393c`
- `0x1801eed68`
- `0x180249490`
- `0x18024a53c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a3c2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a3c2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801a3c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a39bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801a39bc`
- `USER32!GetSystemMetrics` at `0x1801a3a08`
- `USER32!GetSystemMetrics` at `0x1801a3a08`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801a3b36`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801a3bfd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801a3b36`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801a3bfd`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1801a3a4e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1801a3a4e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1801a39ad`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1801a3c3a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1801a39ad`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1801a3c3a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_MaxIcons` at `0x1801a39e1`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_MaxIcons` at `0x1801a39e1`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801a3aec`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x1801a3aec`
- `SHLWAPI!__imp_SHGetCurColorRes` at `0x1801a3ab5`
- `SHLWAPI!__imp_SHGetCurColorRes` at `0x1801a3ab5`
- `Windows.Storage!QueryNewMaxIcons` at `0x1801a39c8`
- `Windows.Storage!QueryNewMaxIcons` at `0x1801a39c8`
- `Windows.Storage!GetSystemImageListBitDepth` at `0x1801a3ac5`
- `Windows.Storage!GetSystemImageListBitDepth` at `0x1801a3ac5`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1801a398d`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1801a398d`

## string_xrefs

- `0x1801a3967`: `SaveCache`

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
0x1801a393c  mov     [rsp-8+arg_0], rbx
0x1801a3941  mov     [rsp-8+arg_8], rdi
0x1801a3946  push    rbp
0x1801a3947  lea     rbp, [rsp-310h]
0x1801a394f  sub     rsp, 410h
0x1801a3956  mov     rax, cs:__security_cookie
0x1801a395d  xor     rax, rsp
0x1801a3960  mov     [rbp+310h+var_10], rax
0x1801a3967  lea     rdx, aSavecache; "SaveCache"
0x1801a396e  xor     ebx, ebx
0x1801a3970  lea     rcx, [rbp+310h+var_370]
0x1801a3974  call    ??0?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801a3979  lea     rax, ??_7SaveCache@IconCacheTelemetry@@6B@; const IconCacheTelemetry::SaveCache::`vftable'
0x1801a3980  lea     rcx, [rbp+310h+var_370]; this
0x1801a3984  mov     [rbp+310h+var_370], rax
0x1801a3988  call    ?StartActivity@SaveCache@IconCacheTelemetry@@QEAAXXZ; IconCacheTelemetry::SaveCache::StartActivity(void)
0x1801a398d  call    cs:__imp_IsDesktopExplorerProcess
0x1801a3994  nop     dword ptr [rax+rax+00h]
0x1801a3999  test    eax, eax
0x1801a399b  jz      loc_1801A3C55
0x1801a39a1  cmp     cs:?g_fDirtyIcons@@3HA, ebx; int g_fDirtyIcons
0x1801a39a7  jz      loc_1801A3C55
0x1801a39ad  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1801a39b4  nop     dword ptr [rax+rax+00h]
0x1801a39b9  mov     rcx, rax; lpCriticalSection
0x1801a39bc  call    cs:__imp_EnterCriticalSection
0x1801a39c3  nop     dword ptr [rax+rax+00h]
0x1801a39c8  call    cs:__imp_?QueryNewMaxIcons@@YAHXZ; QueryNewMaxIcons(void)
0x1801a39cf  nop     dword ptr [rax+rax+00h]
0x1801a39d4  call    ?IconCacheReady@@YAHXZ; IconCacheReady(void)
0x1801a39d9  test    eax, eax
0x1801a39db  jz      loc_1801A3C3A
0x1801a39e1  call    cs:__imp_Global_WindowsStorage_MaxIcons
0x1801a39e8  nop     dword ptr [rax+rax+00h]
0x1801a39ed  lea     rcx, [rbp+310h+pszFile]; pszPath
0x1801a39f4  call    ?GetIconCachePath@@YAJPEAGI@Z; GetIconCachePath(ushort *,uint)
0x1801a39f9  mov     ebx, eax
0x1801a39fb  test    eax, eax
0x1801a39fd  js      loc_1801A3C3A
0x1801a3a03  mov     ecx, 43h ; 'C'; nIndex
0x1801a3a08  call    cs:__imp_GetSystemMetrics
0x1801a3a0f  nop     dword ptr [rax+rax+00h]
0x1801a3a14  lea     rcx, [rbp+310h+pszFile]; pszFile
0x1801a3a1b  test    eax, eax
0x1801a3a1d  jnz     loc_1801A3C2E
0x1801a3a23  mov     r9d, 1; fCreate
0x1801a3a29  mov     [rsp+410h+pstm], 0
0x1801a3a32  lea     rax, [rsp+410h+pstm]
0x1801a3a37  mov     edx, 1021h; grfMode
0x1801a3a3c  mov     [rsp+410h+ppstm], rax; ppstm
0x1801a3a41  mov     [rsp+410h+pstmTemplate], 0; pstmTemplate
0x1801a3a4a  lea     r8d, [r9+1]; dwAttributes
0x1801a3a4e  call    cs:__imp_SHCreateStreamOnFileEx
0x1801a3a55  nop     dword ptr [rax+rax+00h]
0x1801a3a5a  mov     ebx, eax
0x1801a3a5c  test    eax, eax
0x1801a3a5e  js      loc_1801A3C19
0x1801a3a64  mov     rcx, [rsp+410h+pstm]
0x1801a3a69  mov     [rsp+410h+var_3D8], 600000h
0x1801a3a72  mov     rdx, [rsp+410h+var_3D8]
0x1801a3a77  mov     rax, [rcx]
0x1801a3a7a  mov     rax, [rax+30h]
0x1801a3a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3a83  mov     ebx, eax
0x1801a3a85  test    eax, eax
0x1801a3a87  js      loc_1801A3C19
0x1801a3a8d  xor     edx, edx; Val
0x1801a3a8f  lea     rcx, [rsp+410h+pv]; void *
0x1801a3a94  lea     r8d, [rdx+48h]; Size
0x1801a3a98  call    memset_0
0x1801a3a9d  mov     [rsp+410h+var_3BC], 346E6957h
0x1801a3aa5  mov     [rsp+410h+var_3B8], 507h
0x1801a3aad  mov     [rsp+410h+var_3B4], 295Ah
0x1801a3ab5  call    cs:__imp_SHGetCurColorRes
0x1801a3abc  nop     dword ptr [rax+rax+00h]
0x1801a3ac1  mov     [rsp+410h+var_3B0], eax
0x1801a3ac5  call    cs:__imp_?GetSystemImageListBitDepth@@YAHXZ; GetSystemImageListBitDepth(void)
0x1801a3acc  nop     dword ptr [rax+rax+00h]
0x1801a3ad1  mov     ebx, eax
0x1801a3ad3  call    ?IsBiDiLocalizedSystemEx@@YAHPEAG@Z; IsBiDiLocalizedSystemEx(ushort *)
0x1801a3ad8  neg     eax
0x1801a3ada  sbb     ecx, ecx
0x1801a3adc  xor     edi, edi
0x1801a3ade  and     ecx, 2000h
0x1801a3ae4  or      ecx, ebx
0x1801a3ae6  mov     [rsp+410h+var_3AC], ecx
0x1801a3aea  xor     ebx, ebx
0x1801a3aec  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x1801a3af3  nop     dword ptr [rax+rax+00h]
0x1801a3af8  lea     r8, [rsp+410h+var_3A4]
0x1801a3afd  lea     rdx, [rsp+410h+var_3A8]
0x1801a3b02  add     r8, rbx
0x1801a3b05  add     rdx, rbx
0x1801a3b08  mov     rcx, [rax+rbx]
0x1801a3b0c  mov     rax, [rcx]
0x1801a3b0f  mov     rax, [rax+80h]
0x1801a3b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3b1b  inc     rdi
0x1801a3b1e  add     rbx, 8
0x1801a3b22  cmp     rdi, 6
0x1801a3b26  jnz     short loc_1801A3AEC
0x1801a3b28  mov     rcx, [rsp+410h+pstm]; pstm
0x1801a3b2d  lea     r8d, [rdi+42h]; cb
0x1801a3b31  lea     rdx, [rsp+410h+pv]; pv
0x1801a3b36  call    cs:__imp_IStream_Write
0x1801a3b3d  nop     dword ptr [rax+rax+00h]
0x1801a3b42  mov     ebx, eax
0x1801a3b44  test    eax, eax
0x1801a3b46  js      loc_1801A3C19
0x1801a3b4c  mov     rdx, [rsp+410h+pstm]; struct IStream *
0x1801a3b51  call    ?WriteLocations@CIconCache@@QEAAJPEAUIStream@@@Z; CIconCache::WriteLocations(IStream *)
0x1801a3b56  mov     ebx, eax
0x1801a3b58  test    eax, eax
0x1801a3b5a  js      loc_1801A3C19
0x1801a3b60  mov     rcx, [rsp+410h+pstm]
0x1801a3b65  xor     edx, edx
0x1801a3b67  mov     rax, [rcx]
0x1801a3b6a  mov     rax, [rax+40h]
0x1801a3b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3b73  mov     ebx, eax
0x1801a3b75  test    eax, eax
0x1801a3b77  js      loc_1801A3C19
0x1801a3b7d  mov     rcx, [rsp+410h+pstm]
0x1801a3b82  lea     r9, [rsp+410h+var_3D0]
0x1801a3b87  mov     rdx, cs:g_li0
0x1801a3b8e  lea     r8d, [rdi-5]
0x1801a3b92  mov     [rsp+410h+var_3D0], 0
0x1801a3b9b  mov     rax, [rcx]
0x1801a3b9e  mov     rax, [rax+28h]
0x1801a3ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3ba7  test    eax, eax
0x1801a3ba9  js      short loc_1801A3BC1
0x1801a3bab  mov     rcx, [rsp+410h+pstm]
0x1801a3bb0  mov     rdx, [rsp+410h+var_3D0]
0x1801a3bb5  mov     rax, [rcx]
0x1801a3bb8  mov     rax, [rax+30h]
0x1801a3bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3bc1  mov     rcx, [rsp+410h+pstm]
0x1801a3bc6  xor     r9d, r9d
0x1801a3bc9  mov     rdx, cs:g_li0
0x1801a3bd0  xor     r8d, r8d
0x1801a3bd3  mov     rax, [rcx]
0x1801a3bd6  mov     rax, [rax+28h]
0x1801a3bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3bdf  mov     ebx, eax
0x1801a3be1  test    eax, eax
0x1801a3be3  js      short loc_1801A3C19
0x1801a3be5  mov     rcx, [rsp+410h+pstm]; pstm
0x1801a3bea  lea     rdx, [rsp+410h+var_3D8]; pv
0x1801a3bef  mov     r8d, 4; cb
0x1801a3bf5  mov     dword ptr [rsp+410h+var_3D8], 48h ; 'H'
0x1801a3bfd  call    cs:__imp_IStream_Write
0x1801a3c04  nop     dword ptr [rax+rax+00h]
0x1801a3c09  mov     ebx, eax
0x1801a3c0b  test    eax, eax
0x1801a3c0d  js      short loc_1801A3C19
0x1801a3c0f  mov     cs:?g_fDirtyIcons@@3HA, 0; int g_fDirtyIcons
0x1801a3c19  lea     rcx, [rsp+410h+pstm]
0x1801a3c1e  call    ??$SafeRelease@UIUpdatableItemSet@@@@YAXPEAPEAUIUpdatableItemSet@@@Z; SafeRelease<IUpdatableItemSet>(IUpdatableItemSet * *)
0x1801a3c23  test    ebx, ebx
0x1801a3c25  jns     short loc_1801A3C3A
0x1801a3c27  lea     rcx, [rbp+310h+pszFile]; lpFileName
0x1801a3c2e  call    cs:__imp_DeleteFileW
0x1801a3c35  nop     dword ptr [rax+rax+00h]
0x1801a3c3a  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1801a3c41  nop     dword ptr [rax+rax+00h]
0x1801a3c46  mov     rcx, rax; lpCriticalSection
0x1801a3c49  call    cs:__imp_LeaveCriticalSection
0x1801a3c50  nop     dword ptr [rax+rax+00h]
0x1801a3c55  xor     edx, edx
0x1801a3c57  lea     rcx, [rbp+310h+var_370]
0x1801a3c5b  call    ?Stop@?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801a3c60  not     ebx
0x1801a3c62  lea     rcx, [rbp+310h+var_370]; this
0x1801a3c66  shr     ebx, 1Fh
0x1801a3c69  call    ??1SaveCache@IconCacheTelemetry@@QEAA@XZ; IconCacheTelemetry::SaveCache::~SaveCache(void)
0x1801a3c6e  mov     eax, ebx
0x1801a3c70  mov     rcx, [rbp+310h+var_10]
0x1801a3c77  xor     rcx, rsp; StackCookie
0x1801a3c7a  call    __security_check_cookie
0x1801a3c7f  lea     r11, [rsp+410h+var_s0]
0x1801a3c87  mov     rbx, [r11+10h]
0x1801a3c8b  mov     rdi, [r11+18h]
0x1801a3c8f  mov     rsp, r11
0x1801a3c92  pop     rbp
0x1801a3c93  retn
```
