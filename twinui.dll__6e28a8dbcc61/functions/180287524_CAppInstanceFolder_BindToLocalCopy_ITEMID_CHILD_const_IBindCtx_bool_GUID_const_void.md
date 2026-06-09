# CAppInstanceFolder::_BindToLocalCopy(_ITEMID_CHILD const *,IBindCtx *,bool,_GUID const &,void * *)

- ea: `0x180287524`
- end: `0x180287757`
- name: `?_BindToLocalCopy@CAppInstanceFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUIBindCtx@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `563`
- prototype: `int(CAppInstanceFolder *__hidden this, const struct _ITEMID_CHILD *, struct IBindCtx *, bool, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18010b500`
- `0x18010b85c`

## callees

- `0x18000b7e8`
- `0x18009f240`
- `0x1802860fc`
- `0x1802863b4`
- `0x180286f7c`
- `0x180287524`
- `0x18035b78c`
- `0x1803618cc`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802875c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802875c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180287626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028771c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180287626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18028771c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802876a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802876a6`
- `PROPSYS!PropVariantToUInt32` at `0x180287693`
- `PROPSYS!PropVariantToUInt32` at `0x180287693`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802875db`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802875db`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x180287578`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x180287578`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAppInstanceFolder::_BindToLocalCopy(
        CAppInstanceFolder *this,
        const ITEMIDLIST *a2,
        struct IBindCtx *a3,
        char a4,
        const struct _GUID *riid,
        void **ppv)
{
  HRESULT SyncEventForDownload; // ebx
  DWORD v11; // eax
  __int64 v12; // rdx
  unsigned int FileAttributesFromSFGAOFlags; // eax
  void *v15; // [rsp+30h] [rbp-40h] BYREF
  struct IShellItem *ppvItem; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  ULONG pulRet; // [rsp+90h] [rbp+20h] BYREF
  __int64 v22; // [rsp+98h] [rbp+28h] BYREF

  ppvItem = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvItem);
  SyncEventForDownload = SHCreateItemWithParent(
                           0,
                           (IShellFolder *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                           a2,
                           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                           (void **)&ppvItem);
  if ( SyncEventForDownload >= 0 )
  {
    hHandle = 0;
    SyncEventForDownload = _GetSyncEventForDownload(
                             ppvItem,
                             &PKEY_AppToAppItemLocalFileName,
                             L"StreamSync",
                             0,
                             &hHandle);
    if ( SyncEventForDownload >= 0 )
    {
      v11 = WaitForSingleObject(hHandle, -(a4 != 0));
      if ( v11 == 258 )
      {
        SyncEventForDownload = PSCreateMemoryPropertyStore(riid, ppv);
      }
      else
      {
        SyncEventForDownload = -2147467259;
        if ( !v11 )
        {
          v22 = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
          SyncEventForDownload = CItemIDFactory<APPINSTITEM,1346449985>::GetPropertyStorageFromIDList(a2, v12, &v22);
          if ( SyncEventForDownload >= 0 )
          {
            pv = 0;
            CoTaskMemFree(0);
            SyncEventForDownload = IPropertyStore_GetString(v22, &PKEY_AppToAppItemLocalFileName, &pv);
            if ( SyncEventForDownload >= 0 )
            {
              pulRet = 0;
              *(_OWORD *)propvarIn = 0;
              v20 = 0;
              SyncEventForDownload = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 40LL))(
                                       v22,
                                       &PKEY_SFGAOFlags,
                                       propvarIn);
              if ( SyncEventForDownload >= 0 )
              {
                SyncEventForDownload = LOWORD(propvarIn[0]) ? PropVariantToUInt32(propvarIn, &pulRet) : -2147023728;
                PropVariantClear(propvarIn);
                if ( SyncEventForDownload >= 0 )
                {
                  v15 = 0;
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v15);
                  FileAttributesFromSFGAOFlags = GetFileAttributesFromSFGAOFlags(pulRet);
                  SyncEventForDownload = SHSimpleItemFromAttributes(
                                           (PCWSTR)pv,
                                           FileAttributesFromSFGAOFlags,
                                           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                           &v15);
                  if ( SyncEventForDownload >= 0 )
                    SyncEventForDownload = (*(__int64 (__fastcall **)(void *, struct IBindCtx *, const GUID *, const struct _GUID *, void **))(*(_QWORD *)v15 + 24LL))(
                                             v15,
                                             a3,
                                             &BHID_SFObject,
                                             riid,
                                             ppv);
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v15);
                }
              }
            }
            CoTaskMemFree(pv);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        }
      }
    }
    CAutoHandle<void *>::~CAutoHandle<void *>(&hHandle);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvItem);
  return (unsigned int)SyncEventForDownload;
}

```

## disassembly

```asm
0x180287524  mov     [rsp-18h+arg_10], rbx
0x180287529  mov     [rsp-18h+arg_18], rsi
0x18028752e  push    rbp
0x18028752f  push    rdi
0x180287530  push    r14
0x180287532  mov     rbp, rsp
0x180287535  sub     rsp, 70h
0x180287539  mov     dil, r9b
0x18028753c  mov     r14, r8
0x18028753f  mov     rsi, rdx
0x180287542  mov     rbx, rcx
0x180287545  mov     [rbp+var_38], 0
0x18028754d  lea     rcx, [rbp+var_38]
0x180287551  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180287556  lea     rax, [rbx+20h]
0x18028755a  neg     rbx
0x18028755d  sbb     rdx, rdx
0x180287560  and     rdx, rax; psfParent
0x180287563  lea     rax, [rbp+var_38]
0x180287567  mov     [rsp+70h+ppvItem], rax; ppvItem
0x18028756c  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180287573  mov     r8, rsi; pidl
0x180287576  xor     ecx, ecx; pidlParent
0x180287578  call    cs:__imp_SHCreateItemWithParent
0x18028757e  mov     ebx, eax
0x180287580  test    eax, eax
0x180287582  js      loc_180287737
0x180287588  mov     [rbp+hHandle], 0
0x180287590  lea     rax, [rbp+hHandle]
0x180287594  mov     [rsp+70h+ppvItem], rax; void **
0x180287599  xor     r9d, r9d; bool
0x18028759c  lea     r8, aStreamsync; "StreamSync"
0x1802875a3  lea     rdx, PKEY_AppToAppItemLocalFileName; struct _tagpropertykey *
0x1802875aa  mov     rcx, [rbp+var_38]; struct IShellItem *
0x1802875ae  call    ?_GetSyncEventForDownload@@YAJPEAUIShellItem@@AEBU_tagpropertykey@@PEBG_NPEAPEAX@Z; _GetSyncEventForDownload(IShellItem *,_tagpropertykey const &,ushort const *,bool,void * *)
0x1802875b3  mov     ebx, eax
0x1802875b5  test    eax, eax
0x1802875b7  js      loc_18028772D
0x1802875bd  neg     dil
0x1802875c0  sbb     edx, edx; dwMilliseconds
0x1802875c2  mov     rcx, [rbp+hHandle]; hHandle
0x1802875c6  call    cs:__imp_WaitForSingleObject
0x1802875cc  cmp     eax, 102h
0x1802875d1  jnz     short loc_1802875E8
0x1802875d3  mov     rdx, [rbp+ppv]; ppv
0x1802875d7  mov     rcx, [rbp+riid]; riid
0x1802875db  call    cs:__imp_PSCreateMemoryPropertyStore
0x1802875e1  mov     ebx, eax
0x1802875e3  jmp     loc_18028772D
0x1802875e8  mov     ebx, 80004005h
0x1802875ed  test    eax, eax
0x1802875ef  jnz     loc_18028772D
0x1802875f5  mov     [rbp+arg_8], 0
0x1802875fd  lea     rcx, [rbp+arg_8]
0x180287601  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180287606  lea     r8, [rbp+arg_8]
0x18028760a  mov     rcx, rsi
0x18028760d  call    ?GetPropertyStorageFromIDList@?$CItemIDFactory@UAPPINSTITEM@@$0FAEBDCEB@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CItemIDFactory<APPINSTITEM,1346449985>::GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x180287612  mov     ebx, eax
0x180287614  test    eax, eax
0x180287616  js      loc_180287723
0x18028761c  mov     [rbp+pv], 0
0x180287624  xor     ecx, ecx; pv
0x180287626  call    cs:__imp_CoTaskMemFree
0x18028762c  lea     r8, [rbp+pv]
0x180287630  lea     rdx, PKEY_AppToAppItemLocalFileName
0x180287637  mov     rcx, [rbp+arg_8]
0x18028763b  call    IPropertyStore_GetString
0x180287640  mov     ebx, eax
0x180287642  test    eax, eax
0x180287644  js      loc_180287718
0x18028764a  mov     rcx, [rbp+arg_8]
0x18028764e  mov     [rbp+pulRet], 0
0x180287655  xorps   xmm0, xmm0
0x180287658  xor     eax, eax
0x18028765a  movups  xmmword ptr [rbp+propvarIn], xmm0
0x18028765e  mov     [rbp+var_10], rax
0x180287662  mov     rax, [rcx]
0x180287665  lea     r8, [rbp+propvarIn]
0x180287669  lea     rdx, PKEY_SFGAOFlags
0x180287670  mov     rax, [rax+28h]
0x180287674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180287679  mov     ebx, eax
0x18028767b  test    eax, eax
0x18028767d  js      loc_180287718
0x180287683  xor     eax, eax
0x180287685  cmp     ax, word ptr [rbp+propvarIn]
0x180287689  jz      short loc_18028769D
0x18028768b  lea     rdx, [rbp+pulRet]; pulRet
0x18028768f  lea     rcx, [rbp+propvarIn]; propvarIn
0x180287693  call    cs:__imp_PropVariantToUInt32
0x180287699  mov     ebx, eax
0x18028769b  jmp     short loc_1802876A2
0x18028769d  mov     ebx, 80070490h
0x1802876a2  lea     rcx, [rbp+propvarIn]; pvar
0x1802876a6  call    cs:__imp_PropVariantClear
0x1802876ac  test    ebx, ebx
0x1802876ae  js      short loc_180287718
0x1802876b0  mov     [rbp+var_40], 0
0x1802876b8  lea     rcx, [rbp+var_40]
0x1802876bc  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802876c1  mov     ecx, [rbp+pulRet]; unsigned int
0x1802876c4  call    ?GetFileAttributesFromSFGAOFlags@@YAKK@Z; GetFileAttributesFromSFGAOFlags(ulong)
0x1802876c9  mov     edx, eax; unsigned int
0x1802876cb  lea     r9, [rbp+var_40]; void **
0x1802876cf  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x1802876d6  mov     rcx, [rbp+pv]; pszPath
0x1802876da  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x1802876df  mov     ebx, eax
0x1802876e1  test    eax, eax
0x1802876e3  js      short loc_18028770E
0x1802876e5  mov     rcx, [rbp+var_40]
0x1802876e9  mov     rax, [rcx]
0x1802876ec  mov     rdx, [rbp+ppv]
0x1802876f0  mov     [rsp+70h+ppvItem], rdx
0x1802876f5  mov     r9, [rbp+riid]
0x1802876f9  lea     r8, BHID_SFObject
0x180287700  mov     rdx, r14
0x180287703  mov     rax, [rax+18h]
0x180287707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028770c  mov     ebx, eax
0x18028770e  lea     rcx, [rbp+var_40]
0x180287712  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180287717  nop
0x180287718  mov     rcx, [rbp+pv]; pv
0x18028771c  call    cs:__imp_CoTaskMemFree
0x180287722  nop
0x180287723  lea     rcx, [rbp+arg_8]
0x180287727  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18028772c  nop
0x18028772d  lea     rcx, [rbp+hHandle]
0x180287731  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180287736  nop
0x180287737  lea     rcx, [rbp+var_38]
0x18028773b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180287740  mov     eax, ebx
0x180287742  lea     r11, [rsp+70h+var_s0]
0x180287747  mov     rbx, [r11+30h]
0x18028774b  mov     rsi, [r11+38h]
0x18028774f  mov     rsp, r11
0x180287752  pop     r14
0x180287754  pop     rdi
0x180287755  pop     rbp
0x180287756  retn
```
