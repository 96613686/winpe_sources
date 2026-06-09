# CStorageItemsDataFormat::_CreateStorageItemVectorFromFileGroupDescriptor(IDataObject *,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> * *)

- ea: `0x180052598`
- end: `0x180052a81`
- name: `?_CreateStorageItemVectorFromFileGroupDescriptor@CStorageItemsDataFormat@@AEAAJPEAUIDataObject@@PEAPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1257`
- prototype: `__int64 __fastcall(__int64, struct IDataObject *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022204`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x18000775c`
- `0x18002ef80`
- `0x180037db4`
- `0x18004eb30`
- `0x1800522e0`
- `0x180052598`
- `0x180053328`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005281c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800528e2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005281c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800528e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052805`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800528cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052805`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800528cb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180052957`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180052957`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800526c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800526c5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180052782`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800527cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005282b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180052782`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800527cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005282b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800526e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800526e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18005276f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18005276f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180052a27`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180052a27`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x1800527d8`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x1800527d8`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1800529f0`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180052a32`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1800529f0`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180052a32`

## pseudocode

```c
__int64 __fastcall CStorageItemsDataFormat::_CreateStorageItemVectorFromFileGroupDescriptor(
        __int64 a1,
        struct IDataObject *a2,
        _QWORD *a3)
{
  int Descriptor; // ebx
  unsigned int v6; // r14d
  unsigned int *v7; // rax
  unsigned int v8; // eax
  unsigned int i; // edi
  char v10; // al
  LPWSTR ExtensionW; // rax
  int v12; // edx
  __int64 v13; // rcx
  struct _FILEDESCRIPTORW *v14; // r8
  __int64 v15; // rdx
  WCHAR *cFileName; // rax
  WCHAR dwFlags; // r9
  WCHAR *v18; // rcx
  __int64 v19; // rdi
  LPWSTR FileNameW; // rax
  __int64 v21; // r8
  WCHAR *v22; // rdx
  WCHAR v23; // cx
  WCHAR *v24; // rcx
  WCHAR *v25; // rax
  unsigned int StringW; // eax
  const unsigned __int16 *v27; // rsi
  CStorageItemsDataFormat *v28; // rcx
  unsigned int v29; // eax
  IStream *pstm; // rbx
  BOOL v31; // edi
  __int64 v32; // rcx
  LPSTREAM v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[4]; // [rsp+30h] [rbp-D0h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  STGMEDIUM v41; // [rsp+48h] [rbp-B8h] BYREF
  STGMEDIUM hMem; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+8Ch] [rbp-74h]
  int v46; // [rsp+90h] [rbp-70h]
  __int16 v47; // [rsp+98h] [rbp-68h] BYREF
  int v48; // [rsp+9Ah] [rbp-66h]
  __int16 v49; // [rsp+9Eh] [rbp-62h]
  __int64 v50; // [rsp+A0h] [rbp-60h]
  int v51; // [rsp+A8h] [rbp-58h]
  unsigned int v52; // [rsp+ACh] [rbp-54h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  _FILEDESCRIPTORW v54; // [rsp+C0h] [rbp-40h] BYREF
  struct _FILEDESCRIPTORW v55; // [rsp+310h] [rbp+210h] BYREF

  *a3 = 0;
  v40 = 0;
  Descriptor = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
                 a1,
                 &v40);
  if ( Descriptor < 0 )
    goto LABEL_66;
  v43 = 0;
  v44 = 1;
  v45 = 1;
  v46 = 1;
  memset(&hMem, 0, sizeof(hMem));
  Descriptor = CFileGroupDescriptorReader::Initialize((HGLOBAL *)&hMem, a2);
  v6 = 0;
  if ( Descriptor < 0 )
    goto LABEL_62;
  do
  {
    v7 = (unsigned int *)v43;
    if ( (_QWORD)v43 || (v7 = (unsigned int *)*((_QWORD *)&v43 + 1)) != 0 )
      v8 = *v7;
    else
      v8 = 0;
    if ( v6 >= v8 )
      break;
    memset_0(&v54, 0, sizeof(v54));
    Descriptor = CFileGroupDescriptorReader::GetDescriptor((CFileGroupDescriptorReader *)&hMem, v6, &v54);
    if ( Descriptor < 0 )
      goto LABEL_62;
    for ( i = 0; ; ++i )
    {
      v10 = 0;
      if ( i >= v6 )
        break;
      memset_0(&v55, 0, sizeof(v55));
      if ( CFileGroupDescriptorReader::GetDescriptor((CFileGroupDescriptorReader *)&hMem, i, &v55) >= 0
        && CompareStringOrdinal(v55.cFileName, -1, v54.cFileName, -1, 1) == 2 )
      {
        v10 = 1;
        break;
      }
    }
    if ( v10 )
    {
      ExtensionW = PathFindExtensionW(v54.cFileName);
      *ExtensionW = 0;
      v12 = v46++;
      bIgnoreCase[0] = v12;
      Descriptor = StringCchPrintfW(
                     (unsigned __int16 *)&v55,
                     0x104u,
                     L"%s (%d).%s",
                     v54.cFileName,
                     *(_QWORD *)bIgnoreCase,
                     ExtensionW + 1);
      if ( Descriptor >= 0 )
      {
        v13 = 2147483646;
        v14 = &v55;
        v15 = 260;
        cFileName = v54.cFileName;
        do
        {
          if ( !v13 )
            break;
          dwFlags = v14->dwFlags;
          if ( !LOWORD(v14->dwFlags) )
            break;
          v14 = (struct _FILEDESCRIPTORW *)((char *)v14 + 2);
          *cFileName++ = dwFlags;
          --v13;
          --v15;
        }
        while ( v15 );
        v18 = cFileName - 1;
        if ( v15 )
          v18 = cFileName;
        *v18 = 0;
      }
    }
    if ( !PathIsRelativeW(v54.cFileName) )
    {
      v19 = 2147483646;
      FileNameW = PathFindFileNameW(v54.cFileName);
      v21 = 260;
      v22 = v54.cFileName;
      do
      {
        if ( !v19 )
          break;
        v23 = *FileNameW;
        if ( !*FileNameW )
          break;
        ++FileNameW;
        *v22++ = v23;
        --v19;
        --v21;
      }
      while ( v21 );
      v24 = v22 - 1;
      if ( v21 )
        v24 = v22;
      *v24 = 0;
    }
    if ( Descriptor < 0 )
      goto LABEL_62;
    v25 = PathFindFileNameW(v54.cFileName);
    PathCleanupSpec(0, v25);
    if ( (v54.dwFlags & 4) != 0 && (v54.dwFileAttributes & 0x10) != 0 )
    {
      Descriptor = -2147221398;
      *(_QWORD *)Buffer = 0;
      StringW = LoadStringW(&_ImageBase, 1u, Buffer, 0);
      if ( StringW )
      {
        RoOriginateErrorW(2147745898LL, StringW, *(_QWORD *)Buffer);
        goto LABEL_62;
      }
      goto LABEL_59;
    }
    v27 = PathFindFileNameW(v54.cFileName);
    v47 = word_1800AA616;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 1;
    v52 = v6;
    v53 = 13;
    v41.tymed = 0;
    *(_OWORD *)&v41.hBitmap = 0;
    Descriptor = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a2->lpVtbl->GetData)(
                   a2,
                   &v47,
                   &v41);
    if ( Descriptor >= 0 )
    {
      ppstm = 0;
      switch ( v41.tymed )
      {
        case 1u:
          v31 = v41.pUnkForRelease == 0;
          Descriptor = CreateStreamOnHGlobal(v41.hBitmap, v31, &ppstm);
          if ( Descriptor < 0 )
            goto LABEL_56;
          if ( v31 )
          {
            v41.tymed = 0;
            *(_OWORD *)&v41.hBitmap = 0;
          }
          break;
        case 4u:
          pstm = v41.pstm;
          if ( v41.hBitmap )
          {
            (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v41.hBitmap + 8LL))(v41.hBitmap);
            v28 = ppstm;
            ppstm = pstm;
            if ( v28 )
              (*(void (__fastcall **)(CStorageItemsDataFormat *))(*(_QWORD *)v28 + 16LL))(v28);
          }
          break;
        case 8u:
          Descriptor = _GetContentStreamInStorage(v41.pstg, &ppstm);
          if ( Descriptor < 0 )
          {
LABEL_56:
            v33 = ppstm;
            if ( ppstm )
            {
              ppstm = 0;
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v33 + 16LL))(v33);
            }
            goto LABEL_58;
          }
          break;
        default:
          Descriptor = -2147221399;
          *(_QWORD *)Buffer = 0;
          v29 = LoadStringW(&_ImageBase, 2u, Buffer, 0);
          if ( v29 )
            RoOriginateErrorW(2147745897LL, v29, *(_QWORD *)Buffer);
          goto LABEL_56;
      }
      *(_QWORD *)Buffer = 0;
      Descriptor = CStorageItemsDataFormat::_CreateStorageItemForContents(
                     v28,
                     ppstm,
                     &v54,
                     v27,
                     (struct Windows::Storage::IStorageItem **)Buffer);
      if ( Descriptor >= 0 )
        Descriptor = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 104LL))(v40, *(_QWORD *)Buffer);
      v32 = *(_QWORD *)Buffer;
      if ( *(_QWORD *)Buffer )
      {
        *(_QWORD *)Buffer = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      goto LABEL_56;
    }
LABEL_58:
    ReleaseStgMedium(&v41);
LABEL_59:
    ++v6;
  }
  while ( Descriptor >= 0 );
  if ( Descriptor >= 0 )
  {
    v34 = v40;
    v40 = 0;
    *a3 = v34;
  }
LABEL_62:
  if ( hMem.tymed == 1 && hMem.hBitmap )
    GlobalUnlock(hMem.hBitmap);
  ReleaseStgMedium(&hMem);
LABEL_66:
  v35 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x180052598  mov     [rsp-8+arg_0], rbx
0x18005259d  push    rbp
0x18005259e  push    rsi
0x18005259f  push    rdi
0x1800525a0  push    r12
0x1800525a2  push    r13
0x1800525a4  push    r14
0x1800525a6  push    r15
0x1800525a8  lea     rbp, [rsp-470h]
0x1800525b0  sub     rsp, 570h
0x1800525b7  mov     rax, cs:__security_cookie
0x1800525be  xor     rax, rsp
0x1800525c1  mov     [rbp+4A0h+var_40], rax
0x1800525c8  mov     r15, r8
0x1800525cb  mov     r12, rdx
0x1800525ce  xor     r13d, r13d
0x1800525d1  mov     [r8], r13
0x1800525d4  mov     [rsp+5A0h+var_560], r13
0x1800525d9  lea     rdx, [rsp+5A0h+var_560]
0x1800525de  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)
0x1800525e3  mov     ebx, eax
0x1800525e5  test    eax, eax
0x1800525e7  js      loc_180052A39
0x1800525ed  xorps   xmm0, xmm0
0x1800525f0  movdqu  [rsp+5A0h+var_528], xmm0
0x1800525f6  lea     esi, [r13+1]
0x1800525fa  mov     [rbp+4A0h+var_518], esi
0x1800525fd  mov     [rbp+4A0h+var_514], esi
0x180052600  mov     [rbp+4A0h+var_510], esi
0x180052603  xor     eax, eax
0x180052605  movups  xmmword ptr [rsp+5A0h+hMem], xmm0
0x18005260a  mov     [rsp+5A0h+var_530], rax
0x18005260f  mov     rdx, r12; struct IDataObject *
0x180052612  lea     rcx, [rsp+5A0h+hMem]; this
0x180052617  call    ?Initialize@CFileGroupDescriptorReader@@QEAAJPEAUIDataObject@@@Z; CFileGroupDescriptorReader::Initialize(IDataObject *)
0x18005261c  mov     ebx, eax
0x18005261e  mov     r14d, r13d
0x180052621  test    eax, eax
0x180052623  js      loc_180052A17
0x180052629  mov     rax, qword ptr [rsp+5A0h+var_528]
0x18005262e  test    rax, rax
0x180052631  jnz     short loc_18005263C
0x180052633  mov     rax, qword ptr [rbp+4A0h+var_528+8]
0x180052637  test    rax, rax
0x18005263a  jz      short loc_180052640
0x18005263c  mov     eax, [rax]
0x18005263e  jmp     short loc_180052643
0x180052640  mov     eax, r13d
0x180052643  cmp     r14d, eax
0x180052646  jnb     loc_180052A06
0x18005264c  xor     edx, edx; Val
0x18005264e  mov     r8d, 250h; Size
0x180052654  lea     rcx, [rbp+4A0h+var_4E0]; void *
0x180052658  call    memset_0
0x18005265d  lea     r8, [rbp+4A0h+var_4E0]; struct _FILEDESCRIPTORW *
0x180052661  mov     edx, r14d; unsigned int
0x180052664  lea     rcx, [rsp+5A0h+hMem]; this
0x180052669  call    ?GetDescriptor@CFileGroupDescriptorReader@@QEBAJIPEAU_FILEDESCRIPTORW@@@Z; CFileGroupDescriptorReader::GetDescriptor(uint,_FILEDESCRIPTORW *)
0x18005266e  mov     ebx, eax
0x180052670  test    eax, eax
0x180052672  js      loc_180052A17
0x180052678  mov     edi, r13d
0x18005267b  mov     al, r13b
0x18005267e  cmp     edi, r14d
0x180052681  jnb     short loc_1800526D7
0x180052683  xor     edx, edx; Val
0x180052685  mov     r8d, 250h; Size
0x18005268b  lea     rcx, [rbp+4A0h+var_290]; void *
0x180052692  call    memset_0
0x180052697  lea     r8, [rbp+4A0h+var_290]; struct _FILEDESCRIPTORW *
0x18005269e  mov     edx, edi; unsigned int
0x1800526a0  lea     rcx, [rsp+5A0h+hMem]; this
0x1800526a5  call    ?GetDescriptor@CFileGroupDescriptorReader@@QEBAJIPEAU_FILEDESCRIPTORW@@@Z; CFileGroupDescriptorReader::GetDescriptor(uint,_FILEDESCRIPTORW *)
0x1800526aa  test    eax, eax
0x1800526ac  js      short loc_1800526D0
0x1800526ae  mov     [rsp+5A0h+bIgnoreCase], esi; bIgnoreCase
0x1800526b2  or      eax, 0FFFFFFFFh
0x1800526b5  mov     r9d, eax; cchCount2
0x1800526b8  lea     r8, [rbp+4A0h+var_4E0.cFileName]; lpString2
0x1800526bc  mov     edx, eax; cchCount1
0x1800526be  lea     rcx, [rbp+4A0h+var_290.cFileName]; lpString1
0x1800526c5  call    cs:__imp_CompareStringOrdinal
0x1800526cb  cmp     eax, 2
0x1800526ce  jz      short loc_1800526D4
0x1800526d0  add     edi, esi
0x1800526d2  jmp     short loc_18005267B
0x1800526d4  mov     al, sil
0x1800526d7  test    al, al
0x1800526d9  jz      loc_18005276B
0x1800526df  lea     rcx, [rbp+4A0h+var_4E0.cFileName]; pszPath
0x1800526e3  call    cs:__imp_PathFindExtensionW
0x1800526e9  mov     [rax], r13w
0x1800526ed  mov     edx, [rbp+4A0h+var_510]
0x1800526f0  lea     ecx, [rdx+1]
0x1800526f3  mov     [rbp+4A0h+var_510], ecx
0x1800526f6  add     rax, 2
0x1800526fa  mov     [rsp+5A0h+var_578], rax
0x1800526ff  mov     [rsp+5A0h+bIgnoreCase], edx
0x180052703  lea     r9, [rbp+4A0h+var_4E0.cFileName]
0x180052707  lea     r8, aSDS; "%s (%d).%s"
0x18005270e  mov     edi, 104h
0x180052713  mov     edx, edi; unsigned __int64
0x180052715  lea     rcx, [rbp+4A0h+var_290]; unsigned __int16 *
0x18005271c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052721  mov     ebx, eax
0x180052723  test    eax, eax
0x180052725  js      short loc_18005276B
0x180052727  mov     ecx, 7FFFFFFEh
0x18005272c  lea     r8, [rbp+4A0h+var_290]
0x180052733  mov     edx, edi
0x180052735  lea     rax, [rbp+4A0h+var_4E0.cFileName]
0x180052739  test    rcx, rcx
0x18005273c  jz      short loc_18005275C
0x18005273e  movzx   r9d, word ptr [r8]
0x180052742  test    r9w, r9w
0x180052746  jz      short loc_18005275C
0x180052748  add     r8, 2
0x18005274c  mov     [rax], r9w
0x180052750  add     rax, 2
0x180052754  sub     rcx, rsi
0x180052757  sub     rdx, rsi
0x18005275a  jnz     short loc_180052739
0x18005275c  lea     rcx, [rax-2]
0x180052760  test    rdx, rdx
0x180052763  cmovnz  rcx, rax
0x180052767  mov     [rcx], r13w
0x18005276b  lea     rcx, [rbp+4A0h+var_4E0.cFileName]; pszPath
0x18005276f  call    cs:__imp_PathIsRelativeW
0x180052775  test    eax, eax
0x180052777  jnz     short loc_1800527C1
0x180052779  mov     edi, 7FFFFFFEh
0x18005277e  lea     rcx, [rbp+4A0h+var_4E0.cFileName]; pszPath
0x180052782  call    cs:__imp_PathFindFileNameW
0x180052788  mov     r8d, 104h
0x18005278e  lea     rdx, [rbp+4A0h+var_4E0.cFileName]
0x180052792  test    rdi, rdi
0x180052795  jz      short loc_1800527B2
0x180052797  movzx   ecx, word ptr [rax]
0x18005279a  test    cx, cx
0x18005279d  jz      short loc_1800527B2
0x18005279f  add     rax, 2
0x1800527a3  mov     [rdx], cx
0x1800527a6  add     rdx, 2
0x1800527aa  sub     rdi, rsi
0x1800527ad  sub     r8, rsi
0x1800527b0  jnz     short loc_180052792
0x1800527b2  lea     rcx, [rdx-2]
0x1800527b6  test    r8, r8
0x1800527b9  cmovnz  rcx, rdx
0x1800527bd  mov     [rcx], r13w
0x1800527c1  test    ebx, ebx
0x1800527c3  js      loc_180052A17
0x1800527c9  lea     rcx, [rbp+4A0h+var_4E0.cFileName]; pszPath
0x1800527cd  call    cs:__imp_PathFindFileNameW
0x1800527d3  mov     rdx, rax; pszSpec
0x1800527d6  xor     ecx, ecx; pszDir
0x1800527d8  call    cs:__imp_PathCleanupSpec
0x1800527de  test    byte ptr [rbp+4A0h+var_4E0.dwFlags], 4
0x1800527e2  jz      short loc_180052827
0x1800527e4  test    byte ptr [rbp+4A0h+var_4E0.dwFileAttributes], 10h
0x1800527e8  jz      short loc_180052827
0x1800527ea  mov     ebx, 8004006Ah
0x1800527ef  mov     qword ptr [rsp+5A0h+Buffer], r13
0x1800527f4  xor     r9d, r9d; cchBufferMax
0x1800527f7  lea     r8, [rsp+5A0h+Buffer]; lpBuffer
0x1800527fc  mov     edx, esi; uID
0x1800527fe  lea     rcx, __ImageBase; hInstance
0x180052805  call    cs:__imp_LoadStringW
0x18005280b  test    eax, eax
0x18005280d  jz      loc_1800529FB
0x180052813  mov     r8, qword ptr [rsp+5A0h+Buffer]
0x180052818  mov     edx, eax
0x18005281a  mov     ecx, ebx
0x18005281c  call    cs:__imp_RoOriginateErrorW
0x180052822  jmp     loc_180052A17
0x180052827  lea     rcx, [rbp+4A0h+var_4E0.cFileName]; pszPath
0x18005282b  call    cs:__imp_PathFindFileNameW
0x180052831  mov     rsi, rax
0x180052834  movzx   ecx, cs:word_1800AA616
0x18005283b  mov     [rbp+4A0h+var_508], cx
0x18005283f  xor     eax, eax
0x180052841  mov     [rbp+4A0h+var_506], eax
0x180052844  mov     [rbp+4A0h+var_502], ax
0x180052848  mov     [rbp+4A0h+var_500], r13
0x18005284c  mov     [rbp+4A0h+var_4F8], 1
0x180052853  mov     [rbp+4A0h+var_4F4], r14d
0x180052857  mov     [rbp+4A0h+var_4F0], 0Dh
0x18005285f  mov     [rsp+5A0h+var_558.tymed], r13d
0x180052864  xorps   xmm0, xmm0
0x180052867  movdqu  xmmword ptr [rsp+5A0h+var_558.8], xmm0
0x18005286d  mov     rax, [r12]
0x180052871  lea     r8, [rsp+5A0h+var_558]
0x180052876  lea     rdx, [rbp+4A0h+var_508]
0x18005287a  mov     rcx, r12
0x18005287d  mov     rax, [rax+18h]
0x180052881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052886  mov     ebx, eax
0x180052888  test    eax, eax
0x18005288a  js      loc_1800529EB
0x180052890  mov     [rsp+5A0h+ppstm], r13
0x180052895  mov     eax, [rsp+5A0h+var_558.tymed]
0x180052899  sub     eax, 1
0x18005289c  jz      loc_18005293F
0x1800528a2  sub     eax, 3
0x1800528a5  jz      short loc_180052907
0x1800528a7  cmp     eax, 4
0x1800528aa  jz      short loc_1800528ED
0x1800528ac  mov     edi, 80040069h
0x1800528b1  mov     ebx, edi
0x1800528b3  mov     qword ptr [rsp+5A0h+Buffer], r13
0x1800528b8  xor     r9d, r9d; cchBufferMax
0x1800528bb  lea     r8, [rsp+5A0h+Buffer]; lpBuffer
0x1800528c0  lea     edx, [r9+2]; uID
0x1800528c4  lea     rcx, __ImageBase; hInstance
0x1800528cb  call    cs:__imp_LoadStringW
0x1800528d1  test    eax, eax
0x1800528d3  jz      loc_1800529CF
0x1800528d9  mov     r8, qword ptr [rsp+5A0h+Buffer]
0x1800528de  mov     edx, eax
0x1800528e0  mov     ecx, edi
0x1800528e2  call    cs:__imp_RoOriginateErrorW
0x1800528e8  jmp     loc_1800529CF
0x1800528ed  lea     rdx, [rsp+5A0h+ppstm]; struct IStream **
0x1800528f2  mov     rcx, qword ptr [rsp+5A0h+var_558.8]; struct IStorage *
0x1800528f7  call    ?_GetContentStreamInStorage@@YAJPEAUIStorage@@PEAPEAUIStream@@@Z; _GetContentStreamInStorage(IStorage *,IStream * *)
0x1800528fc  mov     ebx, eax
0x1800528fe  test    eax, eax
0x180052900  jns     short loc_180052975
0x180052902  jmp     loc_1800529CF
0x180052907  mov     rbx, qword ptr [rsp+5A0h+var_558.8]
0x18005290c  test    rbx, rbx
0x18005290f  jz      short loc_180052975
0x180052911  mov     rax, [rbx]
0x180052914  mov     rcx, rbx
0x180052917  mov     rax, [rax+8]
0x18005291b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052920  nop
0x180052921  mov     rcx, [rsp+5A0h+ppstm]
0x180052926  mov     [rsp+5A0h+ppstm], rbx
0x18005292b  test    rcx, rcx
0x18005292e  jz      short loc_18005293D
0x180052930  mov     rax, [rcx]
0x180052933  mov     rax, [rax+10h]
0x180052937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005293c  nop
0x18005293d  jmp     short loc_180052975
0x18005293f  mov     edi, r13d
0x180052942  cmp     [rsp+5A0h+var_558.pUnkForRelease], r13
0x180052947  setz    dil
0x18005294b  lea     r8, [rsp+5A0h+ppstm]; ppstm
0x180052950  mov     edx, edi; fDeleteOnRelease
0x180052952  mov     rcx, qword ptr [rsp+5A0h+var_558.8]; hGlobal
0x180052957  call    cs:__imp_CreateStreamOnHGlobal
0x18005295d  mov     ebx, eax
0x18005295f  test    eax, eax
0x180052961  js      short loc_1800529CF
0x180052963  test    edi, edi
0x180052965  jz      short loc_180052975
0x180052967  mov     [rsp+5A0h+var_558.tymed], r13d
0x18005296c  xorps   xmm0, xmm0
0x18005296f  movdqu  xmmword ptr [rsp+5A0h+var_558.8], xmm0
0x180052975  mov     qword ptr [rsp+5A0h+Buffer], r13
0x18005297a  lea     rax, [rsp+5A0h+Buffer]
0x18005297f  mov     qword ptr [rsp+5A0h+bIgnoreCase], rax; struct Windows::Storage::IStorageItem **
0x180052984  mov     r9, rsi; unsigned __int16 *
0x180052987  lea     r8, [rbp+4A0h+var_4E0]; struct _FILEDESCRIPTORW *
0x18005298b  mov     rdx, [rsp+5A0h+ppstm]; struct IStream *
0x180052990  call    ?_CreateStorageItemForContents@CStorageItemsDataFormat@@AEAAJPEAUIStream@@AEBU_FILEDESCRIPTORW@@PEBGPEAPEAUIStorageItem@Storage@Windows@@@Z; CStorageItemsDataFormat::_CreateStorageItemForContents(IStream *,_FILEDESCRIPTORW const &,ushort const *,Windows::Storage::IStorageItem * *)
0x180052995  mov     ebx, eax
0x180052997  test    eax, eax
0x180052999  js      short loc_1800529B3
0x18005299b  mov     rcx, [rsp+5A0h+var_560]
0x1800529a0  mov     rax, [rcx]
0x1800529a3  mov     rdx, qword ptr [rsp+5A0h+Buffer]
0x1800529a8  mov     rax, [rax+68h]
0x1800529ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529b1  mov     ebx, eax
0x1800529b3  mov     rcx, qword ptr [rsp+5A0h+Buffer]
0x1800529b8  test    rcx, rcx
0x1800529bb  jz      short loc_1800529CF
0x1800529bd  mov     qword ptr [rsp+5A0h+Buffer], r13
0x1800529c2  mov     rax, [rcx]
0x1800529c5  mov     rax, [rax+10h]
0x1800529c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529ce  nop
0x1800529cf  mov     rcx, [rsp+5A0h+ppstm]
0x1800529d4  test    rcx, rcx
0x1800529d7  jz      short loc_1800529EB
0x1800529d9  mov     [rsp+5A0h+ppstm], r13
0x1800529de  mov     rax, [rcx]
0x1800529e1  mov     rax, [rax+10h]
0x1800529e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529ea  nop
0x1800529eb  lea     rcx, [rsp+5A0h+var_558]; LPSTGMEDIUM
0x1800529f0  call    cs:__imp_ReleaseStgMedium
0x1800529f6  mov     esi, 1
0x1800529fb  add     r14d, esi
0x1800529fe  test    ebx, ebx
0x180052a00  jns     loc_180052629
0x180052a06  test    ebx, ebx
  ... truncated ...
```
