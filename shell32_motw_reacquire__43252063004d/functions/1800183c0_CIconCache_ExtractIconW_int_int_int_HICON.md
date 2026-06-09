# CIconCache::ExtractIconW(int,int,int,HICON__ * *)

- ea: `0x1800183c0`
- end: `0x180018806`
- name: `?ExtractIconW@CIconCache@@QEAAJHHHPEAPEAUHICON__@@@Z`
- size: `1094`
- prototype: `__int64 __usercall@<rax>(CIconCache *__hidden this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, HICON *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017ac0`

## callees

- `0x180017fcc`
- `0x1800183c0`
- `0x180018ae4`
- `0x180026890`
- `0x18002ff60`
- `0x180030024`
- `0x18003029c`
- `0x18003ef10`
- `0x1800808f0`
- `0x18009d460`
- `0x1800b1170`
- `0x1800b11c0`
- `0x1800cc8b0`
- `0x1800fb078`
- `0x180120cf4`
- `0x18015c070`
- `0x18015e210`
- `0x18017e650`
- `0x180249490`
- `0x1802c5b2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001878e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001878e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018442`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018774`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018442`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018774`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800186a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800186a2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001867e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001867e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001855c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001855c`
- `USER32!DestroyIcon` at `0x18001872b`
- `USER32!DestroyIcon` at `0x180018748`
- `USER32!DestroyIcon` at `0x18001872b`
- `USER32!DestroyIcon` at `0x180018748`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018433`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800184a6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018765`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800187b0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018433`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800184a6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018765`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800187b0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180018606`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180018628`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180018606`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_rgshil` at `0x180018628`
- `Windows.Storage!SHDefExtractIconW` at `0x1800185df`
- `Windows.Storage!SHDefExtractIconW` at `0x1800186db`
- `Windows.Storage!SHDefExtractIconW` at `0x1800185df`
- `Windows.Storage!SHDefExtractIconW` at `0x1800186db`

## string_xrefs

- `0x1800186d4`: `imageres.dll`

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
  wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&v40);
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
0x1800183c0  push    rbp
0x1800183c2  push    rbx
0x1800183c3  push    rsi
0x1800183c4  push    rdi
0x1800183c5  push    r12
0x1800183c7  push    r13
0x1800183c9  push    r15
0x1800183cb  lea     rbp, [rsp-0D0h]
0x1800183d3  sub     rsp, 1D0h
0x1800183da  mov     rax, cs:__security_cookie
0x1800183e1  xor     rax, rsp
0x1800183e4  mov     [rbp+100h+var_40], rax
0x1800183eb  mov     r12d, r9d
0x1800183ee  mov     [rsp+200h+var_1D0], r8d
0x1800183f3  mov     r15d, edx
0x1800183f6  mov     dword ptr [rsp+200h+var_1C8], edx
0x1800183fa  mov     r13, rcx
0x1800183fd  mov     rdi, [rbp+100h+phiconLarge]
0x180018404  mov     qword ptr [rdi], 0
0x18001840b  lea     rdx, aExtracticonw_1; "ExtractIconW"
0x180018412  lea     rcx, [rsp+200h+var_190]
0x180018417  call    ??0?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001841c  lea     rax, ??_7ExtractIconW@IconCacheTelemetry@@6B@; const IconCacheTelemetry::ExtractIconW::`vftable'
0x180018423  mov     [rsp+200h+var_190], rax
0x180018428  lea     rcx, [rsp+200h+var_190]; this
0x18001842d  call    ?StartActivity@ExtractIconW@IconCacheTelemetry@@QEAAXXZ; IconCacheTelemetry::ExtractIconW::StartActivity(void)
0x180018432  nop
0x180018433  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18001843a  nop     dword ptr [rax+rax+00h]
0x18001843f  mov     rcx, rax; lpCriticalSection
0x180018442  call    cs:__imp_EnterCriticalSection
0x180018449  nop     dword ptr [rax+rax+00h]
0x18001844e  lock inc dword ptr [r13+48h]
0x180018453  mov     ebx, 80004005h
0x180018458  mov     edx, r15d; i
0x18001845b  mov     rcx, [r13+28h]; hdsa
0x18001845f  call    DSA_GetItemPtr
0x180018464  mov     rsi, rax
0x180018467  call    cs:__imp_GetCurrentThreadId
0x18001846e  nop     dword ptr [rax+rax+00h]
0x180018473  cmp     cs:?g_dwThreadExtracting@@3KA, eax; ulong g_dwThreadExtracting
0x180018479  jnz     short loc_180018481
0x18001847b  inc     cs:?g_fPausedExtracting@@3HA; int g_fPausedExtracting
0x180018481  xorps   xmm0, xmm0
0x180018484  movups  xmmword ptr [rsp+200h+pszIconFile], xmm0
0x180018489  movups  xmmword ptr [rsp+200h+iIndex], xmm0
0x18001848e  test    rsi, rsi
0x180018491  jz      short loc_1800184A6
0x180018493  mov     r8, rsi; struct RECOVERY_ENTRY *
0x180018496  mov     rdx, [r13+38h]; struct _HashTable **
0x18001849a  lea     rcx, [rsp+200h+pszIconFile]; this
0x18001849f  call    ?CloneFrom@RECOVERY_ENTRY@@QEAAJPEAPEAU_HashTable@@PEBU1@@Z; RECOVERY_ENTRY::CloneFrom(_HashTable * *,RECOVERY_ENTRY const *)
0x1800184a4  mov     ebx, eax
0x1800184a6  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800184ad  nop     dword ptr [rax+rax+00h]
0x1800184b2  mov     rcx, rax; lpCriticalSection
0x1800184b5  call    cs:__imp_LeaveCriticalSection
0x1800184bc  nop     dword ptr [rax+rax+00h]
0x1800184c1  movzx   esi, word ptr [rsp+200h+pszIconFile]
0x1800184c6  test    ebx, ebx
0x1800184c8  js      loc_180018647
0x1800184ce  mov     ecx, esi
0x1800184d0  and     ecx, 3
0x1800184d3  sub     ecx, 1
0x1800184d6  jz      short loc_180018518
0x1800184d8  sub     ecx, 1
0x1800184db  jz      short loc_1800184EB
0x1800184dd  cmp     ecx, 1
0x1800184e0  jz      loc_180018606
0x1800184e6  jmp     loc_180018647
0x1800184eb  cmp     [rsp+200h+pszIconFile+8], 0
0x1800184f1  jz      loc_180018647
0x1800184f7  movzx   edx, word ptr [rsp+200h+iIndex+2]; unsigned int
0x1800184fc  mov     dword ptr [rsp+200h+phiconSmall], r12d; int
0x180018501  mov     r9d, [rsp+200h+var_1D0]; unsigned int
0x180018506  mov     r8, rdi; HICON *
0x180018509  mov     rcx, [rsp+200h+pszIconFile+8]; pidl
0x18001850e  call    ?ExtractIconFromPidl@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@IPEAPEAUHICON__@@HH@Z; ExtractIconFromPidl(_ITEMIDLIST_ABSOLUTE const *,uint,HICON__ * *,int,int)
0x180018513  jmp     loc_180018645
0x180018518  cmp     [rsp+200h+pszIconFile+8], 0
0x18001851e  jz      loc_1800185FC
0x180018524  mov     [rsp+200h+pszPath], 0
0x18001852d  mov     r15, qword ptr [rsp+200h+iIndex+8]
0x180018532  test    r15, r15
0x180018535  jz      short loc_1800185A0
0x180018537  xor     edx, edx
0x180018539  lea     rcx, [rsp+200h+pszPath]
0x18001853e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018543  lea     r9, [rsp+200h+pszPath]
0x180018548  mov     r8, r15
0x18001854b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180018550  mov     rbx, [rsp+200h+pszPath]
0x180018555  test    eax, eax
0x180018557  js      short loc_180018568
0x180018559  mov     rcx, rbx; pszPath
0x18001855c  call    cs:__imp_PathRemoveFileSpecW
0x180018563  nop     dword ptr [rax+rax+00h]
0x180018568  test    rbx, rbx
0x18001856b  jz      short loc_1800185A0
0x18001856d  mov     rdx, rbx; unsigned __int16 *
0x180018570  call    ?_IsCaseSensitiveFolder@CIconCache@@AEAAHPEBG@Z; CIconCache::_IsCaseSensitiveFolder(ushort const *)
0x180018575  test    eax, eax
0x180018577  jz      short loc_1800185A0
0x180018579  mov     ecx, esi; unsigned int
0x18001857b  call    ?ConvertREtoGIL@CRecoveryTable@@SAII@Z; CRecoveryTable::ConvertREtoGIL(uint)
0x180018580  mov     ecx, eax
0x180018582  bts     ecx, 8
0x180018586  test    r12d, r12d
0x180018589  cmovz   ecx, eax
0x18001858c  mov     r8d, ecx
0x18001858f  or      r8d, 8
0x180018593  test    sil, 80h
0x180018597  cmovnz  r8d, ecx
0x18001859b  mov     rcx, r15
0x18001859e  jmp     short loc_1800185C7
0x1800185a0  mov     ecx, esi; unsigned int
0x1800185a2  call    ?ConvertREtoGIL@CRecoveryTable@@SAII@Z; CRecoveryTable::ConvertREtoGIL(uint)
0x1800185a7  mov     ecx, eax
0x1800185a9  bts     ecx, 8
0x1800185ad  test    r12d, r12d
0x1800185b0  cmovz   ecx, eax
0x1800185b3  mov     r8d, ecx
0x1800185b6  or      r8d, 8
0x1800185ba  test    sil, 80h
0x1800185be  cmovnz  r8d, ecx; uFlags
0x1800185c2  mov     rcx, [rsp+200h+pszIconFile+8]; pszIconFile
0x1800185c7  mov     eax, [rsp+200h+var_1D0]
0x1800185cb  mov     [rsp+200h+nIconSize], eax; nIconSize
0x1800185cf  mov     [rsp+200h+phiconSmall], 0; phiconSmall
0x1800185d8  mov     r9, rdi; phiconLarge
0x1800185db  mov     edx, [rsp+200h+iIndex]; iIndex
0x1800185df  call    cs:__imp_SHDefExtractIconW
0x1800185e6  nop     dword ptr [rax+rax+00h]
0x1800185eb  mov     ebx, eax
0x1800185ed  lea     rcx, [rsp+200h+pszPath]; void *
0x1800185f2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800185f7  mov     r15d, dword ptr [rsp+200h+var_1C8]
0x1800185fc  test    r12d, r12d
0x1800185ff  jnz     short loc_180018647
0x180018601  cmp     ebx, 1
0x180018604  jnz     short loc_180018653
0x180018606  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x18001860d  nop     dword ptr [rax+rax+00h]
0x180018612  mov     [rsp+200h+phiconSmall], rdi; HICON *
0x180018617  mov     r8d, r15d; int
0x18001861a  mov     rdx, [rax]; struct IImageList2 *
0x18001861d  call    ?ExtractFromOtherImagelist@CIconCache@@QEAAJPEAUIImageList2@@HHPEAPEAUHICON__@@@Z; CIconCache::ExtractFromOtherImagelist(IImageList2 *,int,int,HICON__ * *)
0x180018622  mov     ebx, eax
0x180018624  test    eax, eax
0x180018626  jns     short loc_180018647
0x180018628  call    cs:__imp_Global_WindowsStorage_Untyped_rgshil
0x18001862f  nop     dword ptr [rax+rax+00h]
0x180018634  mov     [rsp+200h+phiconSmall], rdi; HICON *
0x180018639  mov     r8d, r15d; int
0x18001863c  mov     rdx, [rax+8]; struct IImageList2 *
0x180018640  call    ?ExtractFromOtherImagelist@CIconCache@@QEAAJPEAUIImageList2@@HHPEAPEAUHICON__@@@Z; CIconCache::ExtractFromOtherImagelist(IImageList2 *,int,int,HICON__ * *)
0x180018645  mov     ebx, eax
0x180018647  cmp     ebx, 1
0x18001864a  jnz     short loc_180018653
0x18001864c  mov     ebx, 80004005h
0x180018651  jmp     short loc_18001865B
0x180018653  test    ebx, ebx
0x180018655  jns     loc_1800186F4
0x18001865b  test    r12d, r12d
0x18001865e  jnz     loc_180018765
0x180018664  mov     al, sil
0x180018667  and     al, 3
0x180018669  cmp     al, 1
0x18001866b  jnz     short loc_1800186B8
0x18001866d  cmp     [rsp+200h+iIndex], r12d
0x180018672  jnz     short loc_1800186B8
0x180018674  test    sil, sil
0x180018677  jns     short loc_1800186B8
0x180018679  mov     rcx, [rsp+200h+pszIconFile+8]; pszPath
0x18001867e  call    cs:__imp_PathFindExtensionW
0x180018685  nop     dword ptr [rax+rax+00h]
0x18001868a  mov     rcx, rax; lpString1
0x18001868d  mov     dword ptr [rsp+200h+phiconSmall], 1; bIgnoreCase
0x180018695  or      edx, 0FFFFFFFFh; cchCount1
0x180018698  mov     r9d, edx; cchCount2
0x18001869b  lea     r8, String2; ".exe"
0x1800186a2  call    cs:__imp_CompareStringOrdinal
0x1800186a9  nop     dword ptr [rax+rax+00h]
0x1800186ae  cmp     eax, 2
0x1800186b1  lea     edx, [r12-0Fh]
0x1800186b6  jz      short loc_1800186BD
0x1800186b8  mov     edx, 0FFFFFFFEh; iIndex
0x1800186bd  mov     eax, [rsp+200h+var_1D0]
0x1800186c1  mov     [rsp+200h+nIconSize], eax; nIconSize
0x1800186c5  mov     [rsp+200h+phiconSmall], 0; phiconSmall
0x1800186ce  mov     r9, rdi; phiconLarge
0x1800186d1  xor     r8d, r8d; uFlags
0x1800186d4  lea     rcx, pszIconPath; "imageres.dll"
0x1800186db  call    cs:__imp_SHDefExtractIconW
0x1800186e2  nop     dword ptr [rax+rax+00h]
0x1800186e7  mov     ebx, eax
0x1800186e9  test    eax, eax
0x1800186eb  js      short loc_180018765
0x1800186ed  mov     ebx, 1
0x1800186f2  jmp     short loc_180018765
0x1800186f4  mov     [rsp+200h+var_1C8], 0
0x1800186fd  xor     edx, edx
0x1800186ff  lea     rcx, [rsp+200h+var_1C8]
0x180018704  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHICON__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::reset(HICON__ *)
0x180018709  mov     edx, esi; unsigned int
0x18001870b  lea     r8, [rsp+200h+var_1C8]; HICON *
0x180018710  mov     rcx, [rdi]; HICON
0x180018713  call    ?ApplyIconStamp@@YAJPEAUHICON__@@IPEAPEAU1@@Z; ApplyIconStamp(HICON__ *,uint,HICON__ * *)
0x180018718  mov     ebx, eax
0x18001871a  test    eax, eax
0x18001871c  js      short loc_180018745
0x18001871e  mov     rsi, [rsp+200h+var_1C8]
0x180018723  test    rsi, rsi
0x180018726  jz      short loc_18001875B
0x180018728  mov     rcx, [rdi]; hIcon
0x18001872b  call    cs:__imp_DestroyIcon
0x180018732  nop     dword ptr [rax+rax+00h]
0x180018737  mov     [rsp+200h+var_1C8], 0
0x180018740  mov     [rdi], rsi
0x180018743  jmp     short loc_18001875B
0x180018745  mov     rcx, [rdi]; hIcon
0x180018748  call    cs:__imp_DestroyIcon
0x18001874f  nop     dword ptr [rax+rax+00h]
0x180018754  mov     qword ptr [rdi], 0
0x18001875b  lea     rcx, [rsp+200h+var_1C8]
0x180018760  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180018765  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18001876c  nop     dword ptr [rax+rax+00h]
0x180018771  mov     rcx, rax; lpCriticalSection
0x180018774  call    cs:__imp_EnterCriticalSection
0x18001877b  nop     dword ptr [rax+rax+00h]
0x180018780  mov     rdx, [r13+38h]; struct _HashTable **
0x180018784  lea     rcx, [rsp+200h+pszIconFile]; this
0x180018789  call    ?Destruct@RECOVERY_ENTRY@@QEAAXPEAPEAU_HashTable@@@Z; RECOVERY_ENTRY::Destruct(_HashTable * *)
0x18001878e  call    cs:__imp_GetCurrentThreadId
0x180018795  nop     dword ptr [rax+rax+00h]
0x18001879a  cmp     cs:?g_dwThreadExtracting@@3KA, eax; ulong g_dwThreadExtracting
0x1800187a0  jnz     short loc_1800187A8
0x1800187a2  dec     cs:?g_fPausedExtracting@@3HA; int g_fPausedExtracting
0x1800187a8  mov     rcx, r13; this
0x1800187ab  call    ?Release@CIconCache@@UEAAKXZ; CIconCache::Release(void)
0x1800187b0  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800187b7  nop     dword ptr [rax+rax+00h]
0x1800187bc  mov     rcx, rax; lpCriticalSection
0x1800187bf  call    cs:__imp_LeaveCriticalSection
0x1800187c6  nop     dword ptr [rax+rax+00h]
0x1800187cb  mov     edx, ebx
0x1800187cd  lea     rcx, [rsp+200h+var_190]
0x1800187d2  call    ?Stop@?$ActivityBase@VIconCacheLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IconCacheLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800187d7  nop
0x1800187d8  lea     rcx, [rsp+200h+var_190]; this
0x1800187dd  call    ??1ExtractIconW@IconCacheTelemetry@@QEAA@XZ; IconCacheTelemetry::ExtractIconW::~ExtractIconW(void)
0x1800187e2  mov     eax, ebx
0x1800187e4  mov     rcx, [rbp+100h+var_40]
0x1800187eb  xor     rcx, rsp; StackCookie
0x1800187ee  call    __security_check_cookie
0x1800187f3  add     rsp, 1D0h
0x1800187fa  pop     r15
0x1800187fc  pop     r13
0x1800187fe  pop     r12
0x180018800  pop     rdi
0x180018801  pop     rsi
0x180018802  pop     rbx
0x180018803  pop     rbp
0x180018804  retn
```
