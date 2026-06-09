# CIconCache::ExtractIconW(int,int,int,HICON__ * *)

- ea: `0x18001ff48`
- end: `0x18002031b`
- name: `?ExtractIconW@CIconCache@@QEAAJHHHPEAPEAUHICON__@@@Z`
- size: `979`
- prototype: `__int64 __usercall@<rax>(CIconCache *__hidden this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, HICON *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f6e0`

## callees

- `0x1800181e0`
- `0x18001fb6c`
- `0x18001ff48`
- `0x1800205a4`
- `0x180043380`
- `0x180054320`
- `0x18007c6f0`
- `0x18007c808`
- `0x18007c8c8`
- `0x18007d6d8`
- `0x180083dec`
- `0x18009c148`
- `0x18009ca34`
- `0x1800f5058`
- `0x180106504`
- `0x1801141f4`
- `0x18014cce0`
- `0x18014ec10`
- `0x180233280`
- `0x1802aa6d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ffe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ffe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800202a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800202a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800200c6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800200c6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800201d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800201d0`
- `USER32!DestroyIcon` at `0x18002026b`
- `USER32!DestroyIcon` at `0x180020282`
- `USER32!DestroyIcon` at `0x18002026b`
- `USER32!DestroyIcon` at `0x180020282`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18001ffbb`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18002001c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020299`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800202d2`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18001ffbb`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18002001c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020299`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800202d2`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180020164`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180020180`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180020164`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180020180`
- `Windows.Storage!SHDefExtractIconW` at `0x180020143`
- `Windows.Storage!SHDefExtractIconW` at `0x180020221`
- `Windows.Storage!SHDefExtractIconW` at `0x180020143`
- `Windows.Storage!SHDefExtractIconW` at `0x180020221`

## string_xrefs

- `0x18002021a`: `imageres.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIconCache::ExtractIconW(CIconCache *this, int a2, unsigned int a3, int a4, HICON *phiconLarge)
{
  int v6; // r15d
  struct _RTL_CRITICAL_SECTION *v8; // rax
  HRESULT IconW; // ebx
  const struct RECOVERY_ENTRY *ItemPtr; // rsi
  struct _RTL_CRITICAL_SECTION *v11; // rax
  unsigned int v12; // esi
  HRESULT IconFromPidl; // eax
  const WCHAR *v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  CIconCache *v18; // rcx
  const unsigned __int16 *v19; // rbx
  unsigned int v20; // eax
  int v21; // ecx
  UINT v22; // r8d
  const WCHAR *v23; // rcx
  unsigned int v24; // eax
  int v25; // ecx
  struct IImageList2 **v26; // rax
  CIconCache *v27; // rcx
  int v28; // r9d
  __int64 v29; // rax
  CIconCache *v30; // rcx
  int v31; // r9d
  const WCHAR *ExtensionW; // rax
  int v33; // eax
  int v34; // edx
  HICON v35; // rsi
  struct _RTL_CRITICAL_SECTION *v36; // rax
  struct _RTL_CRITICAL_SECTION *v37; // rax
  HICON v40; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszIconFile[2]; // [rsp+48h] [rbp-B8h] BYREF
  int iIndex[4]; // [rsp+58h] [rbp-A8h]
  _QWORD v44[42]; // [rsp+70h] [rbp-90h] BYREF

  v6 = a2;
  LODWORD(v40) = a2;
  *phiconLarge = 0;
  wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "ExtractIconW");
  v44[0] = &IconCacheTelemetry::ExtractIconW::`vftable';
  IconCacheTelemetry::ExtractIconW::StartActivity((IconCacheTelemetry::ExtractIconW *)v44);
  v8 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  EnterCriticalSection(v8);
  _InterlockedIncrement((volatile signed __int32 *)this + 18);
  IconW = -2147467259;
  ItemPtr = (const struct RECOVERY_ENTRY *)DSA_GetItemPtr(*((HDSA *)this + 5), v6);
  if ( g_dwThreadExtracting == GetCurrentThreadId() )
    ++g_fPausedExtracting;
  *(_OWORD *)pszIconFile = 0;
  *(_OWORD *)iIndex = 0;
  if ( ItemPtr )
    IconW = RECOVERY_ENTRY::CloneFrom((RECOVERY_ENTRY *)pszIconFile, *((struct _HashTable ***)this + 7), ItemPtr);
  v11 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  LeaveCriticalSection(v11);
  v12 = LOWORD(pszIconFile[0]);
  if ( IconW >= 0 )
  {
    if ( ((__int64)pszIconFile[0] & 3) != 1 )
    {
      if ( ((__int64)pszIconFile[0] & 3) == 2 )
      {
        if ( !pszIconFile[1] )
          goto LABEL_34;
        IconFromPidl = ExtractIconFromPidl((LPCITEMIDLIST)pszIconFile[1], HIWORD(iIndex[0]), phiconLarge, a3, a4);
LABEL_33:
        IconW = IconFromPidl;
        goto LABEL_34;
      }
      if ( ((__int64)pszIconFile[0] & 3) != 3 )
        goto LABEL_34;
LABEL_31:
      v26 = (struct IImageList2 **)Global_WindowsStorage_Untyped_rgshil();
      IconW = CIconCache::ExtractFromOtherImagelist(v27, *v26, v6, v28, phiconLarge);
      if ( IconW >= 0 )
        goto LABEL_34;
      v29 = Global_WindowsStorage_Untyped_rgshil();
      IconFromPidl = CIconCache::ExtractFromOtherImagelist(v30, *(struct IImageList2 **)(v29 + 8), v6, v31, phiconLarge);
      goto LABEL_33;
    }
    if ( pszIconFile[1] )
    {
      pszPath = 0;
      v14 = *(const WCHAR **)&iIndex[2];
      if ( !*(_QWORD *)&iIndex[2] )
        goto LABEL_23;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszPath,
        0);
      v17 = _AllocString<CTCoAllocPolicy>(v16, v15, v14, &pszPath);
      v19 = pszPath;
      if ( v17 >= 0 )
        PathRemoveFileSpecW(pszPath);
      if ( v19 && CIconCache::_IsCaseSensitiveFolder(v18, v19) )
      {
        v20 = CRecoveryTable::ConvertREtoGIL(v12);
        v21 = v20 | 0x100;
        if ( !a4 )
          v21 = v20;
        v22 = v21 | 8;
        if ( (v12 & 0x80u) != 0 )
          v22 = v21;
        v23 = v14;
      }
      else
      {
LABEL_23:
        v24 = CRecoveryTable::ConvertREtoGIL(v12);
        v25 = v24 | 0x100;
        if ( !a4 )
          v25 = v24;
        v22 = v25 | 8;
        if ( (v12 & 0x80u) != 0 )
          v22 = v25;
        v23 = pszIconFile[1];
      }
      IconW = SHDefExtractIconW(v23, iIndex[0], v22, phiconLarge, 0, a3);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszPath);
      v6 = (int)v40;
    }
    if ( !a4 )
    {
      if ( IconW != 1 )
        goto LABEL_36;
      goto LABEL_31;
    }
  }
LABEL_34:
  if ( IconW == 1 )
  {
    IconW = -2147467259;
    goto LABEL_37;
  }
LABEL_36:
  if ( IconW < 0 )
  {
LABEL_37:
    if ( !a4 )
    {
      if ( (v12 & 3) != 1
        || iIndex[0]
        || (v12 & 0x80u) == 0
        || (ExtensionW = PathFindExtensionW(pszIconFile[1]),
            v33 = CompareStringOrdinal(ExtensionW, -1, L".exe", -1, 1),
            v34 = -15,
            v33 != 2) )
      {
        v34 = -2;
      }
      IconW = SHDefExtractIconW(L"imageres.dll", v34, 0, phiconLarge, 0, a3);
      if ( IconW >= 0 )
        IconW = 1;
    }
    goto LABEL_50;
  }
  v40 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::reset(
    &v40,
    0);
  IconW = ApplyIconStamp(*phiconLarge, v12, &v40);
  if ( IconW < 0 )
  {
    DestroyIcon(*phiconLarge);
    *phiconLarge = 0;
  }
  else
  {
    v35 = v40;
    if ( v40 )
    {
      DestroyIcon(*phiconLarge);
      v40 = 0;
      *phiconLarge = v35;
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>(&v40);
LABEL_50:
  v36 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  EnterCriticalSection(v36);
  RECOVERY_ENTRY::Destruct((RECOVERY_ENTRY *)pszIconFile, *((struct _HashTable ***)this + 7));
  if ( g_dwThreadExtracting == GetCurrentThreadId() )
    --g_fPausedExtracting;
  CIconCache::Release(this);
  v37 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  LeaveCriticalSection(v37);
  wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, (unsigned int)IconW);
  IconCacheTelemetry::ExtractIconW::~ExtractIconW((IconCacheTelemetry::ExtractIconW *)v44);
  return (unsigned int)IconW;
}

```

## disassembly

```asm
0x18001ff48  push    rbp
0x18001ff4a  push    rbx
0x18001ff4b  push    rsi
0x18001ff4c  push    rdi
0x18001ff4d  push    r12
0x18001ff4f  push    r13
0x18001ff51  push    r15
0x18001ff53  lea     rbp, [rsp-0D0h]
0x18001ff5b  sub     rsp, 1D0h
0x18001ff62  mov     rax, cs:__security_cookie
0x18001ff69  xor     rax, rsp
0x18001ff6c  mov     [rbp+100h+var_40], rax
0x18001ff73  mov     r12d, r9d
0x18001ff76  mov     [rsp+200h+var_1D0], r8d
0x18001ff7b  mov     r15d, edx
0x18001ff7e  mov     dword ptr [rsp+200h+var_1C8], edx
0x18001ff82  mov     r13, rcx
0x18001ff85  mov     rdi, [rbp+100h+phiconLarge]
0x18001ff8c  mov     qword ptr [rdi], 0
0x18001ff93  lea     rdx, aExtracticonw_1; "ExtractIconW"
0x18001ff9a  lea     rcx, [rsp+200h+var_190]
0x18001ff9f  call    ??0?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ffa4  lea     rax, ??_7ExtractIconW@IconCacheTelemetry@@6B@; const IconCacheTelemetry::ExtractIconW::`vftable'
0x18001ffab  mov     [rsp+200h+var_190], rax
0x18001ffb0  lea     rcx, [rsp+200h+var_190]; this
0x18001ffb5  call    ?StartActivity@ExtractIconW@IconCacheTelemetry@@QEAAXXZ; IconCacheTelemetry::ExtractIconW::StartActivity(void)
0x18001ffba  nop
0x18001ffbb  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18001ffc1  mov     rcx, rax; lpCriticalSection
0x18001ffc4  call    cs:__imp_EnterCriticalSection
0x18001ffca  lock inc dword ptr [r13+48h]
0x18001ffcf  mov     ebx, 80004005h
0x18001ffd4  mov     edx, r15d; i
0x18001ffd7  mov     rcx, [r13+28h]; hdsa
0x18001ffdb  call    DSA_GetItemPtr
0x18001ffe0  mov     rsi, rax
0x18001ffe3  call    cs:__imp_GetCurrentThreadId
0x18001ffe9  cmp     cs:?g_dwThreadExtracting@@3KA, eax; ulong g_dwThreadExtracting
0x18001ffef  jnz     short loc_18001FFF7
0x18001fff1  inc     cs:?g_fPausedExtracting@@3HA; int g_fPausedExtracting
0x18001fff7  xorps   xmm0, xmm0
0x18001fffa  movups  xmmword ptr [rsp+200h+pszIconFile], xmm0
0x18001ffff  movups  xmmword ptr [rsp+200h+iIndex], xmm0
0x180020004  test    rsi, rsi
0x180020007  jz      short loc_18002001C
0x180020009  mov     r8, rsi; struct RECOVERY_ENTRY *
0x18002000c  mov     rdx, [r13+38h]; struct _HashTable **
0x180020010  lea     rcx, [rsp+200h+pszIconFile]; this
0x180020015  call    ?CloneFrom@RECOVERY_ENTRY@@QEAAJPEAPEAU_HashTable@@PEBU1@@Z; RECOVERY_ENTRY::CloneFrom(_HashTable * *,RECOVERY_ENTRY const *)
0x18002001a  mov     ebx, eax
0x18002001c  call    cs:__imp_Global_WindowsStorage_csIconCache
0x180020022  mov     rcx, rax; lpCriticalSection
0x180020025  call    cs:__imp_LeaveCriticalSection
0x18002002b  movzx   esi, word ptr [rsp+200h+pszIconFile]
0x180020030  test    ebx, ebx
0x180020032  js      loc_180020199
0x180020038  mov     ecx, esi
0x18002003a  and     ecx, 3
0x18002003d  sub     ecx, 1
0x180020040  jz      short loc_180020082
0x180020042  sub     ecx, 1
0x180020045  jz      short loc_180020055
0x180020047  cmp     ecx, 1
0x18002004a  jz      loc_180020164
0x180020050  jmp     loc_180020199
0x180020055  cmp     [rsp+200h+pszIconFile+8], 0
0x18002005b  jz      loc_180020199
0x180020061  movzx   edx, word ptr [rsp+200h+iIndex+2]; unsigned int
0x180020066  mov     dword ptr [rsp+200h+phiconSmall], r12d; int
0x18002006b  mov     r9d, [rsp+200h+var_1D0]; unsigned int
0x180020070  mov     r8, rdi; HICON *
0x180020073  mov     rcx, [rsp+200h+pszIconFile+8]; pidl
0x180020078  call    ?ExtractIconFromPidl@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@IPEAPEAUHICON__@@HH@Z; ExtractIconFromPidl(_ITEMIDLIST_ABSOLUTE const *,uint,HICON__ * *,int,int)
0x18002007d  jmp     loc_180020197
0x180020082  cmp     [rsp+200h+pszIconFile+8], 0
0x180020088  jz      loc_18002015A
0x18002008e  mov     [rsp+200h+pszPath], 0
0x180020097  mov     r15, qword ptr [rsp+200h+iIndex+8]
0x18002009c  test    r15, r15
0x18002009f  jz      short loc_180020104
0x1800200a1  xor     edx, edx
0x1800200a3  lea     rcx, [rsp+200h+pszPath]
0x1800200a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800200ad  lea     r9, [rsp+200h+pszPath]
0x1800200b2  mov     r8, r15
0x1800200b5  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800200ba  mov     rbx, [rsp+200h+pszPath]
0x1800200bf  test    eax, eax
0x1800200c1  js      short loc_1800200CC
0x1800200c3  mov     rcx, rbx; pszPath
0x1800200c6  call    cs:__imp_PathRemoveFileSpecW
0x1800200cc  test    rbx, rbx
0x1800200cf  jz      short loc_180020104
0x1800200d1  mov     rdx, rbx; unsigned __int16 *
0x1800200d4  call    ?_IsCaseSensitiveFolder@CIconCache@@AEAAHPEBG@Z; CIconCache::_IsCaseSensitiveFolder(ushort const *)
0x1800200d9  test    eax, eax
0x1800200db  jz      short loc_180020104
0x1800200dd  mov     ecx, esi; unsigned int
0x1800200df  call    ?ConvertREtoGIL@CRecoveryTable@@SAII@Z; CRecoveryTable::ConvertREtoGIL(uint)
0x1800200e4  mov     ecx, eax
0x1800200e6  bts     ecx, 8
0x1800200ea  test    r12d, r12d
0x1800200ed  cmovz   ecx, eax
0x1800200f0  mov     r8d, ecx
0x1800200f3  or      r8d, 8
0x1800200f7  test    sil, 80h
0x1800200fb  cmovnz  r8d, ecx
0x1800200ff  mov     rcx, r15
0x180020102  jmp     short loc_18002012B
0x180020104  mov     ecx, esi; unsigned int
0x180020106  call    ?ConvertREtoGIL@CRecoveryTable@@SAII@Z; CRecoveryTable::ConvertREtoGIL(uint)
0x18002010b  mov     ecx, eax
0x18002010d  bts     ecx, 8
0x180020111  test    r12d, r12d
0x180020114  cmovz   ecx, eax
0x180020117  mov     r8d, ecx
0x18002011a  or      r8d, 8
0x18002011e  test    sil, 80h
0x180020122  cmovnz  r8d, ecx; uFlags
0x180020126  mov     rcx, [rsp+200h+pszIconFile+8]; pszIconFile
0x18002012b  mov     eax, [rsp+200h+var_1D0]
0x18002012f  mov     [rsp+200h+nIconSize], eax; nIconSize
0x180020133  mov     [rsp+200h+phiconSmall], 0; phiconSmall
0x18002013c  mov     r9, rdi; phiconLarge
0x18002013f  mov     edx, [rsp+200h+iIndex]; iIndex
0x180020143  call    cs:__imp_SHDefExtractIconW
0x180020149  mov     ebx, eax
0x18002014b  lea     rcx, [rsp+200h+pszPath]; void *
0x180020150  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180020155  mov     r15d, dword ptr [rsp+200h+var_1C8]
0x18002015a  test    r12d, r12d
0x18002015d  jnz     short loc_180020199
0x18002015f  cmp     ebx, 1
0x180020162  jnz     short loc_1800201A5
0x180020164  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x18002016a  mov     [rsp+200h+phiconSmall], rdi; HICON *
0x18002016f  mov     r8d, r15d; int
0x180020172  mov     rdx, [rax]; struct IImageList2 *
0x180020175  call    ?ExtractFromOtherImagelist@CIconCache@@QEAAJPEAUIImageList2@@HHPEAPEAUHICON__@@@Z; CIconCache::ExtractFromOtherImagelist(IImageList2 *,int,int,HICON__ * *)
0x18002017a  mov     ebx, eax
0x18002017c  test    eax, eax
0x18002017e  jns     short loc_180020199
0x180020180  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x180020186  mov     [rsp+200h+phiconSmall], rdi; HICON *
0x18002018b  mov     r8d, r15d; int
0x18002018e  mov     rdx, [rax+8]; struct IImageList2 *
0x180020192  call    ?ExtractFromOtherImagelist@CIconCache@@QEAAJPEAUIImageList2@@HHPEAPEAUHICON__@@@Z; CIconCache::ExtractFromOtherImagelist(IImageList2 *,int,int,HICON__ * *)
0x180020197  mov     ebx, eax
0x180020199  cmp     ebx, 1
0x18002019c  jnz     short loc_1800201A5
0x18002019e  mov     ebx, 80004005h
0x1800201a3  jmp     short loc_1800201AD
0x1800201a5  test    ebx, ebx
0x1800201a7  jns     loc_180020234
0x1800201ad  test    r12d, r12d
0x1800201b0  jnz     loc_180020299
0x1800201b6  mov     al, sil
0x1800201b9  and     al, 3
0x1800201bb  cmp     al, 1
0x1800201bd  jnz     short loc_1800201FE
0x1800201bf  cmp     [rsp+200h+iIndex], r12d
0x1800201c4  jnz     short loc_1800201FE
0x1800201c6  test    sil, sil
0x1800201c9  jns     short loc_1800201FE
0x1800201cb  mov     rcx, [rsp+200h+pszIconFile+8]; pszPath
0x1800201d0  call    cs:__imp_PathFindExtensionW
0x1800201d6  mov     rcx, rax; lpString1
0x1800201d9  mov     dword ptr [rsp+200h+phiconSmall], 1; bIgnoreCase
0x1800201e1  or      edx, 0FFFFFFFFh; cchCount1
0x1800201e4  mov     r9d, edx; cchCount2
0x1800201e7  lea     r8, aExe; ".exe"
0x1800201ee  call    cs:__imp_CompareStringOrdinal
0x1800201f4  cmp     eax, 2
0x1800201f7  lea     edx, [r12-0Fh]
0x1800201fc  jz      short loc_180020203
0x1800201fe  mov     edx, 0FFFFFFFEh; iIndex
0x180020203  mov     eax, [rsp+200h+var_1D0]
0x180020207  mov     [rsp+200h+nIconSize], eax; nIconSize
0x18002020b  mov     [rsp+200h+phiconSmall], 0; phiconSmall
0x180020214  mov     r9, rdi; phiconLarge
0x180020217  xor     r8d, r8d; uFlags
0x18002021a  lea     rcx, pszIconPath; "imageres.dll"
0x180020221  call    cs:__imp_SHDefExtractIconW
0x180020227  mov     ebx, eax
0x180020229  test    eax, eax
0x18002022b  js      short loc_180020299
0x18002022d  mov     ebx, 1
0x180020232  jmp     short loc_180020299
0x180020234  mov     [rsp+200h+var_1C8], 0
0x18002023d  xor     edx, edx
0x18002023f  lea     rcx, [rsp+200h+var_1C8]
0x180020244  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHICON__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::reset(HICON__ *)
0x180020249  mov     edx, esi; unsigned int
0x18002024b  lea     r8, [rsp+200h+var_1C8]; HICON *
0x180020250  mov     rcx, [rdi]; HICON
0x180020253  call    ?ApplyIconStamp@@YAJPEAUHICON__@@IPEAPEAU1@@Z; ApplyIconStamp(HICON__ *,uint,HICON__ * *)
0x180020258  mov     ebx, eax
0x18002025a  test    eax, eax
0x18002025c  js      short loc_18002027F
0x18002025e  mov     rsi, [rsp+200h+var_1C8]
0x180020263  test    rsi, rsi
0x180020266  jz      short loc_18002028F
0x180020268  mov     rcx, [rdi]; hIcon
0x18002026b  call    cs:__imp_DestroyIcon
0x180020271  mov     [rsp+200h+var_1C8], 0
0x18002027a  mov     [rdi], rsi
0x18002027d  jmp     short loc_18002028F
0x18002027f  mov     rcx, [rdi]; hIcon
0x180020282  call    cs:__imp_DestroyIcon
0x180020288  mov     qword ptr [rdi], 0
0x18002028f  lea     rcx, [rsp+200h+var_1C8]
0x180020294  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>(void)
0x180020299  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18002029f  mov     rcx, rax; lpCriticalSection
0x1800202a2  call    cs:__imp_EnterCriticalSection
0x1800202a8  mov     rdx, [r13+38h]; struct _HashTable **
0x1800202ac  lea     rcx, [rsp+200h+pszIconFile]; this
0x1800202b1  call    ?Destruct@RECOVERY_ENTRY@@QEAAXPEAPEAU_HashTable@@@Z; RECOVERY_ENTRY::Destruct(_HashTable * *)
0x1800202b6  call    cs:__imp_GetCurrentThreadId
0x1800202bc  cmp     cs:?g_dwThreadExtracting@@3KA, eax; ulong g_dwThreadExtracting
0x1800202c2  jnz     short loc_1800202CA
0x1800202c4  dec     cs:?g_fPausedExtracting@@3HA; int g_fPausedExtracting
0x1800202ca  mov     rcx, r13; this
0x1800202cd  call    ?Release@CIconCache@@UEAAKXZ; CIconCache::Release(void)
0x1800202d2  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800202d8  mov     rcx, rax; lpCriticalSection
0x1800202db  call    cs:__imp_LeaveCriticalSection
0x1800202e1  mov     edx, ebx
0x1800202e3  lea     rcx, [rsp+200h+var_190]
0x1800202e8  call    ?Stop@?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800202ed  nop
0x1800202ee  lea     rcx, [rsp+200h+var_190]; this
0x1800202f3  call    ??1ExtractIconW@IconCacheTelemetry@@QEAA@XZ; IconCacheTelemetry::ExtractIconW::~ExtractIconW(void)
0x1800202f8  mov     eax, ebx
0x1800202fa  mov     rcx, [rbp+100h+var_40]
0x180020301  xor     rcx, rsp; StackCookie
0x180020304  call    __security_check_cookie
0x180020309  add     rsp, 1D0h
0x180020310  pop     r15
0x180020312  pop     r13
0x180020314  pop     r12
0x180020316  pop     rdi
0x180020317  pop     rsi
0x180020318  pop     rbx
0x180020319  pop     rbp
0x18002031a  retn
```
