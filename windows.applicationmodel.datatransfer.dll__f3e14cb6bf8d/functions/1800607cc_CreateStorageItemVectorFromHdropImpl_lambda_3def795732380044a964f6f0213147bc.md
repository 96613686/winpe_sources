# CreateStorageItemVectorFromHdropImpl__lambda_3def795732380044a964f6f0213147bc_

- ea: `0x1800607cc`
- end: `0x180060a16`
- name: `_CreateStorageItemVectorFromHdropImpl__lambda_3def795732380044a964f6f0213147bc___`
- size: `586`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180061350`

## callees

- `0x180002ad0`
- `0x18000775c`
- `0x180008b68`
- `0x1800607cc`
- `0x180081010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800608f9`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800608f9`
- `api-ms-win-shell-dataobject-l1-1-1!DragQueryFileW` at `0x180060894`
- `api-ms-win-shell-dataobject-l1-1-1!DragQueryFileW` at `0x1800608ca`
- `api-ms-win-shell-dataobject-l1-1-1!DragQueryFileW` at `0x180060894`
- `api-ms-win-shell-dataobject-l1-1-1!DragQueryFileW` at `0x1800608ca`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1800609ad`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1800609ad`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x18006092e`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x18006092e`

## pseudocode

```c
__int64 __fastcall CreateStorageItemVectorFromHdropImpl__lambda_3def795732380044a964f6f0213147bc_(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3)
{
  HRESULT StorageItemFromShellItem_FullTrustCaller; // ebx
  UINT FileW; // edi
  UINT v8; // esi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+3Ah] [rbp-C6h]
  __int16 v20; // [rsp+3Eh] [rbp-C2h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+4Ch] [rbp-B4h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  STGMEDIUM hDrop; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szFile[264]; // [rsp+70h] [rbp-90h] BYREF

  *a2 = 0;
  v15 = 0;
  StorageItemFromShellItem_FullTrustCaller = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
                                               a1,
                                               &v15);
  if ( StorageItemFromShellItem_FullTrustCaller >= 0 )
  {
    memset(&hDrop, 0, sizeof(hDrop));
    v18 = 15;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 1;
    v23 = -1;
    v24 = 1;
    StorageItemFromShellItem_FullTrustCaller = (*(__int64 (__fastcall **)(__int64, __int16 *, STGMEDIUM *))(*(_QWORD *)a1 + 24LL))(
                                                 a1,
                                                 &v18,
                                                 &hDrop);
    if ( StorageItemFromShellItem_FullTrustCaller >= 0 )
    {
      FileW = DragQueryFileW((HDROP)hDrop.hBitmap, 0xFFFFFFFF, 0, 0);
      if ( FileW )
      {
        StorageItemFromShellItem_FullTrustCaller = 0;
        if ( FileW >= 0x10 )
          FileW = 16;
        v8 = 0;
        while ( v8 < FileW )
        {
          if ( !DragQueryFileW((HDROP)hDrop.hBitmap, v8, szFile, 0x104u) )
          {
            StorageItemFromShellItem_FullTrustCaller = -2147467259;
            break;
          }
          v9 = v15;
          ppv = 0;
          StorageItemFromShellItem_FullTrustCaller = SHCreateItemFromParsingName(
                                                       szFile,
                                                       0,
                                                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                                       &ppv);
          if ( StorageItemFromShellItem_FullTrustCaller >= 0 )
          {
            v16 = 0;
            v10 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v16);
            StorageItemFromShellItem_FullTrustCaller = CreateStorageItemFromShellItem_FullTrustCaller(
                                                         ppv,
                                                         *a3 | 1u,
                                                         &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                                                         v10);
            if ( StorageItemFromShellItem_FullTrustCaller >= 0 )
              StorageItemFromShellItem_FullTrustCaller = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v9)[13])(
                                                           v9,
                                                           v16);
            v11 = v16;
            if ( v16 )
            {
              v16 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          v12 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
          }
          ++v8;
          if ( StorageItemFromShellItem_FullTrustCaller < 0 )
            break;
        }
      }
      else
      {
        StorageItemFromShellItem_FullTrustCaller = -2147023728;
      }
      ReleaseStgMedium(&hDrop);
      if ( StorageItemFromShellItem_FullTrustCaller >= 0 )
        StorageItemFromShellItem_FullTrustCaller = (**v15)(v15, &GUID_802508e2_9c2c_5b91_89a8_39bcf7223344, a2);
    }
  }
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
  }
  return (unsigned int)StorageItemFromShellItem_FullTrustCaller;
}

```

## disassembly

```asm
0x1800607cc  push    rbp
0x1800607ce  push    rbx
0x1800607cf  push    rsi
0x1800607d0  push    rdi
0x1800607d1  push    r12
0x1800607d3  push    r14
0x1800607d5  push    r15
0x1800607d7  lea     rbp, [rsp-190h]
0x1800607df  sub     rsp, 290h
0x1800607e6  mov     rax, cs:__security_cookie
0x1800607ed  xor     rax, rsp
0x1800607f0  mov     [rbp+1C0h+var_40], rax
0x1800607f7  mov     r12, r8
0x1800607fa  mov     r15, rdx
0x1800607fd  mov     rdi, rcx
0x180060800  mov     qword ptr [rdx], 0
0x180060807  mov     [rsp+2C0h+var_2A0], 0
0x180060810  lea     rdx, [rsp+2C0h+var_2A0]
0x180060815  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)
0x18006081a  mov     ebx, eax
0x18006081c  test    eax, eax
0x18006081e  js      loc_1800609D3
0x180060824  xorps   xmm0, xmm0
0x180060827  xor     eax, eax
0x180060829  movups  xmmword ptr [rsp+2C0h+hDrop], xmm0
0x18006082e  mov     [rsp+2C0h+var_258], rax
0x180060833  mov     eax, 0Fh
0x180060838  mov     [rsp+2C0h+var_288], ax
0x18006083d  xor     eax, eax
0x18006083f  mov     [rsp+2C0h+var_286], eax
0x180060843  mov     [rsp+2C0h+var_282], ax
0x180060848  mov     [rsp+2C0h+var_280], rax
0x18006084d  mov     eax, 1
0x180060852  mov     [rsp+2C0h+var_278], eax
0x180060856  mov     [rsp+2C0h+var_274], 0FFFFFFFFh
0x18006085e  mov     [rsp+2C0h+var_270], rax
0x180060863  mov     rax, [rdi]
0x180060866  lea     r8, [rsp+2C0h+hDrop]
0x18006086b  lea     rdx, [rsp+2C0h+var_288]
0x180060870  mov     rcx, rdi
0x180060873  mov     rax, [rax+18h]
0x180060877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006087c  mov     ebx, eax
0x18006087e  test    eax, eax
0x180060880  js      loc_1800609D3
0x180060886  xor     r9d, r9d; cch
0x180060889  xor     r8d, r8d; lpszFile
0x18006088c  or      edx, 0FFFFFFFFh; iFile
0x18006088f  mov     rcx, [rsp+2C0h+hDrop+8]; hDrop
0x180060894  call    cs:__imp_DragQueryFileW
0x18006089a  mov     edi, eax
0x18006089c  test    eax, eax
0x18006089e  jz      loc_1800609A3
0x1800608a4  xor     ebx, ebx
0x1800608a6  lea     eax, [rbx+10h]
0x1800608a9  cmp     edi, eax
0x1800608ab  cmovnb  edi, eax
0x1800608ae  xor     esi, esi
0x1800608b0  cmp     esi, edi
0x1800608b2  jnb     loc_1800609A8
0x1800608b8  mov     r9d, 104h; cch
0x1800608be  lea     r8, [rsp+2C0h+szFile]; lpszFile
0x1800608c3  mov     edx, esi; iFile
0x1800608c5  mov     rcx, [rsp+2C0h+hDrop+8]; hDrop
0x1800608ca  call    cs:__imp_DragQueryFileW
0x1800608d0  test    eax, eax
0x1800608d2  jz      loc_18006099C
0x1800608d8  mov     r14, [rsp+2C0h+var_2A0]
0x1800608dd  mov     [rsp+2C0h+ppv], 0
0x1800608e6  lea     r9, [rsp+2C0h+ppv]; ppv
0x1800608eb  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800608f2  xor     edx, edx; pbc
0x1800608f4  lea     rcx, [rsp+2C0h+szFile]; pszPath
0x1800608f9  call    cs:__imp_SHCreateItemFromParsingName
0x1800608ff  mov     ebx, eax
0x180060901  test    eax, eax
0x180060903  js      short loc_180060970
0x180060905  mov     [rsp+2C0h+var_298], 0
0x18006090e  lea     rcx, [rsp+2C0h+var_298]
0x180060913  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180060918  mov     edx, [r12]
0x18006091c  or      edx, 1
0x18006091f  mov     r9, rax
0x180060922  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180060929  mov     rcx, [rsp+2C0h+ppv]
0x18006092e  call    cs:__imp_CreateStorageItemFromShellItem_FullTrustCaller
0x180060934  mov     ebx, eax
0x180060936  test    eax, eax
0x180060938  js      short loc_180060950
0x18006093a  mov     rax, [r14]
0x18006093d  mov     rdx, [rsp+2C0h+var_298]
0x180060942  mov     rcx, r14
0x180060945  mov     rax, [rax+68h]
0x180060949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006094e  mov     ebx, eax
0x180060950  mov     rcx, [rsp+2C0h+var_298]
0x180060955  test    rcx, rcx
0x180060958  jz      short loc_180060970
0x18006095a  mov     [rsp+2C0h+var_298], 0
0x180060963  mov     rax, [rcx]
0x180060966  mov     rax, [rax+10h]
0x18006096a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006096f  nop
0x180060970  mov     rcx, [rsp+2C0h+ppv]
0x180060975  test    rcx, rcx
0x180060978  jz      short loc_180060990
0x18006097a  mov     [rsp+2C0h+ppv], 0
0x180060983  mov     rax, [rcx]
0x180060986  mov     rax, [rax+10h]
0x18006098a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006098f  nop
0x180060990  inc     esi
0x180060992  test    ebx, ebx
0x180060994  jns     loc_1800608B0
0x18006099a  jmp     short loc_1800609A8
0x18006099c  mov     ebx, 80004005h
0x1800609a1  jmp     short loc_1800609A8
0x1800609a3  mov     ebx, 80070490h
0x1800609a8  lea     rcx, [rsp+2C0h+hDrop]; LPSTGMEDIUM
0x1800609ad  call    cs:__imp_ReleaseStgMedium
0x1800609b3  test    ebx, ebx
0x1800609b5  js      short loc_1800609D3
0x1800609b7  mov     rcx, [rsp+2C0h+var_2A0]
0x1800609bc  mov     rax, [rcx]
0x1800609bf  mov     r8, r15
0x1800609c2  lea     rdx, _GUID_802508e2_9c2c_5b91_89a8_39bcf7223344
0x1800609c9  mov     rax, [rax]
0x1800609cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609d1  mov     ebx, eax
0x1800609d3  mov     rcx, [rsp+2C0h+var_2A0]
0x1800609d8  test    rcx, rcx
0x1800609db  jz      short loc_1800609F3
0x1800609dd  mov     [rsp+2C0h+var_2A0], 0
0x1800609e6  mov     rax, [rcx]
0x1800609e9  mov     rax, [rax+10h]
0x1800609ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609f2  nop
0x1800609f3  mov     eax, ebx
0x1800609f5  mov     rcx, [rbp+1C0h+var_40]
0x1800609fc  xor     rcx, rsp; StackCookie
0x1800609ff  call    __security_check_cookie
0x180060a04  add     rsp, 290h
0x180060a0b  pop     r15
0x180060a0d  pop     r14
0x180060a0f  pop     r12
0x180060a11  pop     rdi
0x180060a12  pop     rsi
0x180060a13  pop     rbx
0x180060a14  pop     rbp
0x180060a15  retn
```
