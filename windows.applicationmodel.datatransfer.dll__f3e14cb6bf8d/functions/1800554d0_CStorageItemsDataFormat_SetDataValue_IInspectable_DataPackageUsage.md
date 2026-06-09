# CStorageItemsDataFormat::_SetDataValue(IInspectable *,DataPackageUsage)

- ea: `0x1800554d0`
- end: `0x18005586a`
- name: `?_SetDataValue@CStorageItemsDataFormat@@MEAAJPEAUIInspectable@@W4DataPackageUsage@@@Z`
- size: `922`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180008b68`
- `0x18000ce4c`
- `0x18000d02c`
- `0x180022204`
- `0x18004c4d8`
- `0x180051bc0`
- `0x180051c38`
- `0x1800554d0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800557bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800557bc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800557f8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800557f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800557e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800557e6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055741`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055788`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055741`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055788`
- `api-ms-win-shell-dataobject-l1-1-0!SHCreateDataObject` at `0x1800556b2`
- `api-ms-win-shell-dataobject-l1-1-0!SHCreateDataObject` at `0x1800556b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CStorageItemsDataFormat::_SetDataValue(
        CDataFormat *a1,
        int (__fastcall ***a2)(_QWORD, GUID *, IDataObject **),
        char a3)
{
  int v6; // edi
  IDataObject *v7; // rcx
  struct Windows::Foundation::IPropertyValue *v8; // rcx
  int (__fastcall *v9)(_QWORD, GUID *, __int64); // rbx
  __int64 v10; // rax
  bool v11; // r8
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  HGLOBAL v14; // rbx
  HGLOBAL v15; // rcx
  void *v16; // rax
  HGLOBAL v17; // rcx
  HSTRING v18; // rcx
  unsigned int StringW; // eax
  __int64 v20; // rcx
  struct Windows::Foundation::IPropertyValue *v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // [rsp+30h] [rbp-49h] BYREF
  __int64 v25; // [rsp+38h] [rbp-41h] BYREF
  __int64 v26; // [rsp+40h] [rbp-39h] BYREF
  __int128 v27; // [rsp+48h] [rbp-31h]
  void **v28; // [rsp+58h] [rbp-21h] BYREF
  HSTRING string[2]; // [rsp+60h] [rbp-19h]
  HGLOBAL hMem; // [rsp+70h] [rbp-9h]
  __int16 v31; // [rsp+78h] [rbp-1h] BYREF
  int v32; // [rsp+7Ah] [rbp+1h]
  __int16 v33; // [rsp+7Eh] [rbp+5h]
  __int64 v34; // [rsp+80h] [rbp+7h]
  int v35; // [rsp+88h] [rbp+Fh]
  int v36; // [rsp+8Ch] [rbp+13h]
  __int64 v37; // [rsp+90h] [rbp+17h]
  IDataObject *Buffer; // [rsp+E8h] [rbp+6Fh] BYREF
  struct Windows::Foundation::IPropertyValue *v39; // [rsp+F8h] [rbp+7Fh] BYREF

  v24 = 0;
  if ( (**a2)(a2, &GUID_bb8b8418_65d1_544b_b083_6d172f568c73, (IDataObject **)&v24) < 0 )
  {
    v39 = 0;
    if ( (**a2)(a2, &GUID_9ac00304_83ea_5688_87b6_ae38aab65d0b, (IDataObject **)&v39) < 0 )
    {
      Buffer = 0;
      v6 = (**a2)(a2, &GUID_4669befc_ae5c_52b1_8a97_5466ce61e94e, &Buffer);
      if ( v6 >= 0 )
        v6 = CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::StorageFile *>(a1);
      v7 = Buffer;
      if ( Buffer )
      {
        Buffer = 0;
        ((void (__fastcall *)(IDataObject *))v7->lpVtbl->Release)(v7);
      }
    }
    else
    {
      v6 = CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::StorageFile *>(a1);
    }
    v8 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IPropertyValue *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  else
  {
    v6 = CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::IStorageItem *>(a1);
  }
  if ( v6 < 0 )
  {
    v39 = 0;
    v9 = (int (__fastcall *)(_QWORD, GUID *, __int64))**a2;
    v10 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v39);
    if ( v9(a2, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, v10) < 0 )
    {
      v25 = 0;
      v12 = (__int64 (__fastcall *)(_QWORD, GUID *, __int64))**a2;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v25);
      v6 = v12(a2, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, v13);
      if ( v6 < 0 )
        goto LABEL_28;
      *(_OWORD *)string = 0;
      v28 = &CGlobalMemoryFormat::`vftable';
      hMem = 0;
      CGlobalMemoryFormat::_ClearData((CGlobalMemoryFormat *)&v28);
      CDataFormat::_ClearDelegate((CDataFormat *)&v28);
      v6 = ((__int64 (__fastcall *)(void ***, _QWORD, _QWORD))v28[7])(&v28, a2, 0);
      if ( v6 >= 0 )
      {
        Buffer = 0;
        v6 = SHCreateDataObject(0, 0, 0, 0, &GUID_0000010e_0000_0000_c000_000000000046, (void **)&Buffer);
        if ( v6 >= 0 )
        {
          v14 = hMem;
          hMem = 0;
          v31 = word_1800AA61E;
          v32 = 0;
          v33 = 0;
          v34 = 0;
          v35 = 1;
          v36 = -1;
          v37 = 1;
          v26 = 1;
          v27 = (unsigned __int64)v14;
          v6 = ((__int64 (__fastcall *)(IDataObject *, __int16 *, __int64 *, __int64))Buffer->lpVtbl->SetData)(
                 Buffer,
                 &v31,
                 &v26,
                 1);
          CDataFormat::_ClearDelegate((CDataFormat *)&v28);
          ((void (__fastcall *)(void ***))v28[5])(&v28);
          v15 = hMem;
          hMem = 0;
          GlobalFree(v15);
          v16 = 0;
          if ( v6 < 0 )
            v16 = v14;
          hMem = v16;
          if ( v6 >= 0 )
            v6 = CStorageItemsDataFormat::ConstructFromDataObject((__int64)a1, Buffer, 0, a3);
        }
        if ( Buffer )
          ((void (__fastcall *)(IDataObject *))Buffer->lpVtbl->Release)(Buffer);
      }
      v17 = hMem;
      hMem = 0;
      GlobalFree(v17);
      v28 = &CDataFormat::`vftable';
      v18 = string[1];
      if ( string[1] )
      {
        string[1] = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
      }
      if ( string[0] )
        WindowsDeleteString(string[0]);
      if ( v6 < 0 )
      {
LABEL_28:
        if ( v6 == -2147467262 )
          v6 = -2147316576;
        Buffer = 0;
        StringW = LoadStringW(&_ImageBase, 0x14u, (LPWSTR)&Buffer, 0);
        if ( StringW )
          RoOriginateErrorW((unsigned int)v6, StringW, Buffer);
      }
      v20 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
    else
    {
      v6 = CStorageItemsDataFormat::SetFromPropertyValueWithObjArray(a1, v39, v11);
    }
    v21 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IPropertyValue *))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  v22 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800554d0  mov     [rsp-8+arg_0], rbx
0x1800554d5  push    rbp
0x1800554d6  push    rsi
0x1800554d7  push    rdi
0x1800554d8  push    r12
0x1800554da  push    r13
0x1800554dc  push    r14
0x1800554de  push    r15
0x1800554e0  lea     rbp, [rsp-27h]
0x1800554e5  sub     rsp, 0A0h
0x1800554ec  mov     r15d, r8d
0x1800554ef  mov     rsi, rdx
0x1800554f2  mov     r14, rcx
0x1800554f5  xor     r12d, r12d
0x1800554f8  mov     [rbp+57h+var_A0], r12
0x1800554fc  mov     rax, [rdx]
0x1800554ff  lea     r8, [rbp+57h+var_A0]
0x180055503  lea     rdx, _GUID_bb8b8418_65d1_544b_b083_6d172f568c73
0x18005550a  mov     rcx, rsi
0x18005550d  mov     rax, [rax]
0x180055510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055515  test    eax, eax
0x180055517  js      short loc_18005552F
0x180055519  mov     r8b, 1
0x18005551c  mov     rdx, [rbp+57h+var_A0]
0x180055520  mov     rcx, r14; this
0x180055523  call    ??$SetFromStorageItems@PEAUIStorageItem@Storage@Windows@@@CStorageItemsDataFormat@@QEAAJPEAU?$IIterable@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@_N@Z; CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::IStorageItem *>(Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageItem *> *,bool)
0x180055528  mov     edi, eax
0x18005552a  jmp     loc_1800555C5
0x18005552f  mov     [rbp+57h+arg_18], r12
0x180055533  mov     rax, [rsi]
0x180055536  lea     r8, [rbp+57h+arg_18]
0x18005553a  lea     rdx, _GUID_9ac00304_83ea_5688_87b6_ae38aab65d0b
0x180055541  mov     rcx, rsi
0x180055544  mov     rax, [rax]
0x180055547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005554c  test    eax, eax
0x18005554e  js      short loc_180055560
0x180055550  mov     rdx, [rbp+57h+arg_18]
0x180055554  mov     rcx, r14; this
0x180055557  call    ??$SetFromStorageItems@PEAVStorageFile@Storage@Windows@@@CStorageItemsDataFormat@@QEAAJPEAU?$IIterable@PEAVStorageFile@Storage@Windows@@@Collections@Foundation@Windows@@_N@Z; CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::StorageFile *>(Windows::Foundation::Collections::IIterable<Windows::Storage::StorageFile *> *,bool)
0x18005555c  mov     edi, eax
0x18005555e  jmp     short loc_1800555AB
0x180055560  mov     [rbp+57h+Buffer], r12
0x180055564  mov     rax, [rsi]
0x180055567  lea     r8, [rbp+57h+Buffer]
0x18005556b  lea     rdx, _GUID_4669befc_ae5c_52b1_8a97_5466ce61e94e
0x180055572  mov     rcx, rsi
0x180055575  mov     rax, [rax]
0x180055578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005557d  mov     edi, eax
0x18005557f  test    eax, eax
0x180055581  js      short loc_180055591
0x180055583  mov     rdx, [rbp+57h+Buffer]
0x180055587  mov     rcx, r14; this
0x18005558a  call    ??$SetFromStorageItems@PEAVStorageFile@Storage@Windows@@@CStorageItemsDataFormat@@QEAAJPEAU?$IIterable@PEAVStorageFile@Storage@Windows@@@Collections@Foundation@Windows@@_N@Z; CStorageItemsDataFormat::SetFromStorageItems<Windows::Storage::StorageFile *>(Windows::Foundation::Collections::IIterable<Windows::Storage::StorageFile *> *,bool)
0x18005558f  mov     edi, eax
0x180055591  mov     rcx, [rbp+57h+Buffer]
0x180055595  test    rcx, rcx
0x180055598  jz      short loc_1800555AB
0x18005559a  mov     [rbp+57h+Buffer], r12
0x18005559e  mov     rax, [rcx]
0x1800555a1  mov     rax, [rax+10h]
0x1800555a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555aa  nop
0x1800555ab  mov     rcx, [rbp+57h+arg_18]
0x1800555af  test    rcx, rcx
0x1800555b2  jz      short loc_1800555C5
0x1800555b4  mov     [rbp+57h+arg_18], r12
0x1800555b8  mov     rax, [rcx]
0x1800555bb  mov     rax, [rax+10h]
0x1800555bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555c4  nop
0x1800555c5  test    edi, edi
0x1800555c7  jns     loc_180055833
0x1800555cd  mov     [rbp+57h+arg_18], r12
0x1800555d1  mov     rax, [rsi]
0x1800555d4  mov     rbx, [rax]
0x1800555d7  lea     rcx, [rbp+57h+arg_18]
0x1800555db  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x1800555e0  mov     r8, rax
0x1800555e3  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800555ea  mov     rcx, rsi
0x1800555ed  mov     rax, rbx
0x1800555f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555f5  test    eax, eax
0x1800555f7  js      short loc_18005560C
0x1800555f9  mov     rdx, [rbp+57h+arg_18]; struct Windows::Foundation::IPropertyValue *
0x1800555fd  mov     rcx, r14; this
0x180055600  call    ?SetFromPropertyValueWithObjArray@CStorageItemsDataFormat@@QEAAJPEAUIPropertyValue@Foundation@Windows@@_N@Z; CStorageItemsDataFormat::SetFromPropertyValueWithObjArray(Windows::Foundation::IPropertyValue *,bool)
0x180055605  mov     edi, eax
0x180055607  jmp     loc_180055819
0x18005560c  mov     [rbp+57h+var_98], r12
0x180055610  mov     rax, [rsi]
0x180055613  mov     rbx, [rax]
0x180055616  lea     rcx, [rbp+57h+var_98]
0x18005561a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18005561f  mov     r8, rax
0x180055622  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180055629  mov     rcx, rsi
0x18005562c  mov     rax, rbx
0x18005562f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055634  mov     edi, eax
0x180055636  lea     r13, __ImageBase
0x18005563d  test    eax, eax
0x18005563f  js      loc_1800557C6
0x180055645  xorps   xmm0, xmm0
0x180055648  movdqu  xmmword ptr [rbp+57h+string], xmm0
0x18005564d  lea     rax, rva ??_7CGlobalMemoryFormat@@6B@[r13]; const CGlobalMemoryFormat::`vftable' ...
0x180055654  mov     [rbp+57h+var_78], rax
0x180055658  mov     [rbp+57h+hMem], r12
0x18005565c  lea     rcx, [rbp+57h+var_78]; this
0x180055660  call    ?_ClearData@CGlobalMemoryFormat@@MEAAXXZ; CGlobalMemoryFormat::_ClearData(void)
0x180055665  lea     rcx, [rbp+57h+var_78]; this
0x180055669  call    ?_ClearDelegate@CDataFormat@@IEAAXXZ; CDataFormat::_ClearDelegate(void)
0x18005566e  mov     rax, [rbp+57h+var_78]
0x180055672  xor     r8d, r8d
0x180055675  mov     rdx, rsi
0x180055678  lea     rcx, [rbp+57h+var_78]
0x18005567c  mov     rax, [rax+38h]
0x180055680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055685  mov     edi, eax
0x180055687  test    eax, eax
0x180055689  js      loc_180055780
0x18005568f  mov     [rbp+57h+Buffer], r12
0x180055693  lea     rax, [rbp+57h+Buffer]
0x180055697  mov     [rsp+0D0h+ppv], rax; ppv
0x18005569c  lea     rax, _GUID_0000010e_0000_0000_c000_000000000046
0x1800556a3  mov     [rsp+0D0h+riid], rax; riid
0x1800556a8  xor     r9d, r9d; pdtInner
0x1800556ab  xor     r8d, r8d; apidl
0x1800556ae  xor     edx, edx; cidl
0x1800556b0  xor     ecx, ecx; pidlFolder
0x1800556b2  call    cs:__imp_SHCreateDataObject
0x1800556b8  mov     edi, eax
0x1800556ba  test    eax, eax
0x1800556bc  js      loc_18005576A
0x1800556c2  mov     rbx, [rbp+57h+hMem]
0x1800556c6  mov     [rbp+57h+hMem], r12
0x1800556ca  movzx   eax, cs:word_1800AA61E
0x1800556d1  mov     [rbp+57h+var_58], ax
0x1800556d5  xor     eax, eax
0x1800556d7  mov     [rbp+57h+var_56], eax
0x1800556da  mov     [rbp+57h+var_52], ax
0x1800556de  mov     [rbp+57h+var_50], r12
0x1800556e2  lea     edx, [rax+1]
0x1800556e5  mov     [rbp+57h+var_48], edx
0x1800556e8  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x1800556ef  mov     [rbp+57h+var_40], rdx
0x1800556f3  mov     [rbp+57h+var_90], rdx
0x1800556f7  xorps   xmm0, xmm0
0x1800556fa  movups  [rbp+57h+var_88], xmm0
0x1800556fe  mov     qword ptr [rbp+57h+var_88], rbx
0x180055702  mov     rcx, [rbp+57h+Buffer]
0x180055706  mov     rax, [rcx]
0x180055709  mov     r9d, edx
0x18005570c  lea     r8, [rbp+57h+var_90]
0x180055710  lea     rdx, [rbp+57h+var_58]
0x180055714  mov     rax, [rax+38h]
0x180055718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005571d  mov     edi, eax
0x18005571f  lea     rcx, [rbp+57h+var_78]; this
0x180055723  call    ?_ClearDelegate@CDataFormat@@IEAAXXZ; CDataFormat::_ClearDelegate(void)
0x180055728  mov     rax, [rbp+57h+var_78]
0x18005572c  lea     rcx, [rbp+57h+var_78]
0x180055730  mov     rax, [rax+28h]
0x180055734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055739  mov     rcx, [rbp+57h+hMem]; hMem
0x18005573d  mov     [rbp+57h+hMem], r12
0x180055741  call    cs:__imp_GlobalFree
0x180055747  mov     rax, r12
0x18005574a  test    edi, edi
0x18005574c  cmovs   rax, rbx
0x180055750  mov     [rbp+57h+hMem], rax
0x180055754  js      short loc_18005576A
0x180055756  mov     r9d, r15d
0x180055759  xor     r8d, r8d
0x18005575c  mov     rdx, [rbp+57h+Buffer]
0x180055760  mov     rcx, r14
0x180055763  call    ?ConstructFromDataObject@CStorageItemsDataFormat@@QEAAJPEAUIDataObject@@_NW4DataPackageUsage@@@Z; CStorageItemsDataFormat::ConstructFromDataObject(IDataObject *,bool,DataPackageUsage)
0x180055768  mov     edi, eax
0x18005576a  mov     rcx, [rbp+57h+Buffer]
0x18005576e  test    rcx, rcx
0x180055771  jz      short loc_180055780
0x180055773  mov     rax, [rcx]
0x180055776  mov     rax, [rax+10h]
0x18005577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005577f  nop
0x180055780  mov     rcx, [rbp+57h+hMem]; hMem
0x180055784  mov     [rbp+57h+hMem], r12
0x180055788  call    cs:__imp_GlobalFree
0x18005578e  lea     rax, ??_7CDataFormat@@6B@; const CDataFormat::`vftable'
0x180055795  mov     [rbp+57h+var_78], rax
0x180055799  mov     rcx, [rbp+57h+string+8]
0x18005579d  test    rcx, rcx
0x1800557a0  jz      short loc_1800557B3
0x1800557a2  mov     [rbp+57h+string+8], r12
0x1800557a6  mov     rax, [rcx]
0x1800557a9  mov     rax, [rax+10h]
0x1800557ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557b2  nop
0x1800557b3  mov     rcx, [rbp+57h+string]; string
0x1800557b7  test    rcx, rcx
0x1800557ba  jz      short loc_1800557C2
0x1800557bc  call    cs:__imp_WindowsDeleteString
0x1800557c2  test    edi, edi
0x1800557c4  jns     short loc_1800557FF
0x1800557c6  mov     eax, 80028CA0h
0x1800557cb  cmp     edi, 80004002h
0x1800557d1  cmovz   edi, eax
0x1800557d4  mov     [rbp+57h+Buffer], r12
0x1800557d8  xor     r9d, r9d; cchBufferMax
0x1800557db  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800557df  lea     edx, [r9+14h]; uID
0x1800557e3  mov     rcx, r13; hInstance
0x1800557e6  call    cs:__imp_LoadStringW
0x1800557ec  test    eax, eax
0x1800557ee  jz      short loc_1800557FF
0x1800557f0  mov     r8, [rbp+57h+Buffer]
0x1800557f4  mov     edx, eax
0x1800557f6  mov     ecx, edi
0x1800557f8  call    cs:__imp_RoOriginateErrorW
0x1800557fe  nop
0x1800557ff  mov     rcx, [rbp+57h+var_98]
0x180055803  test    rcx, rcx
0x180055806  jz      short loc_180055819
0x180055808  mov     [rbp+57h+var_98], r12
0x18005580c  mov     rax, [rcx]
0x18005580f  mov     rax, [rax+10h]
0x180055813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055818  nop
0x180055819  mov     rcx, [rbp+57h+arg_18]
0x18005581d  test    rcx, rcx
0x180055820  jz      short loc_180055833
0x180055822  mov     [rbp+57h+arg_18], r12
0x180055826  mov     rax, [rcx]
0x180055829  mov     rax, [rax+10h]
0x18005582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055832  nop
0x180055833  mov     rcx, [rbp+57h+var_A0]
0x180055837  test    rcx, rcx
0x18005583a  jz      short loc_18005584D
0x18005583c  mov     [rbp+57h+var_A0], r12
0x180055840  mov     rax, [rcx]
0x180055843  mov     rax, [rax+10h]
0x180055847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005584c  nop
0x18005584d  mov     eax, edi
0x18005584f  mov     rbx, [rsp+0D0h+arg_0]
0x180055857  add     rsp, 0A0h
0x18005585e  pop     r15
0x180055860  pop     r14
0x180055862  pop     r13
0x180055864  pop     r12
0x180055866  pop     rdi
0x180055867  pop     rsi
0x180055868  pop     rbp
0x180055869  retn
```
