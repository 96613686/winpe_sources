# CDataPackageView::GetDataInfo(DATAPACKAGE_USAGE_SCENARIO,ushort * *)

- ea: `0x18002e070`
- end: `0x18002e7dd`
- name: `?GetDataInfo@CDataPackageView@@UEAAJW4DATAPACKAGE_USAGE_SCENARIO@@PEAPEAG@Z`
- size: `1901`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e7f0`

## callees

- `0x180002ad0`
- `0x180007028`
- `0x180022124`
- `0x18002e070`
- `0x180034480`
- `0x180043b6c`
- `0x180048954`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e7ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e7ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e55f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e55f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDataPackageView::GetDataInfo(__int64 a1, int a2, _QWORD *a3)
{
  char v5; // r9
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // ebx
  _WORD *Reserved1; // rsi
  __int64 v13; // rcx
  int StorageItemsAsync; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // r14d
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  int v27; // eax
  PCWSTR StringRawBuffer; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  PVOID v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // r14d
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, _QWORD, HSTRING *); // rbx
  int v53; // eax
  int v54; // eax
  PCWSTR v55; // rax
  int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v61[8]; // [rsp+28h] [rbp-58h] BYREF
  HSTRING v62; // [rsp+30h] [rbp-50h] BYREF
  __int64 v63; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v64; // [rsp+40h] [rbp-40h] BYREF
  __int64 v65; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  v5 = 0;
  v61[0] = 0;
  if ( ((a2 - 1) & 0xFFFFFFFD) == 0 )
  {
    string = 0;
    v6 = WindowsCreateStringReference(L"Shell IDList Array", 0x12u, &hstringHeader, &string);
    if ( v6 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
      JUMPOUT(0x18002E7DCLL);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _BYTE *))(**(_QWORD **)(a1 + 112) + 80LL))(
           *(_QWORD *)(a1 + 112),
           string,
           v61);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13E8,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v9,
        v60);
      return v10;
    }
    v5 = v61[0];
  }
  Reserved1 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v13 = a1 - 40;
  if ( v5 )
  {
    v63 = 0;
    StorageItemsAsync = CDataPackageView::GetStorageItemsAsync(v13, &v63);
    v10 = StorageItemsAsync;
    if ( StorageItemsAsync < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F0,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)StorageItemsAsync,
        v60);
      v15 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return v10;
    }
    v60 = 0;
    v16 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>(
            v63,
            &v60);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F3,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v16,
        v60);
      v17 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v10;
    }
    v64 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 56LL))(v60, &v64);
    v10 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F6,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v19,
        v60);
      v20 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      return v10;
    }
    v22 = 0;
    if ( v64 )
    {
      while ( 1 )
      {
        v65 = 0;
        v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v60 + 48LL))(v60, v22, &v65);
        v10 = v23;
        if ( v23 < 0 )
          break;
        v62 = 0;
        v24 = v65;
        v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v65 + 96LL);
        WindowsDeleteString(0);
        v62 = 0;
        v26 = v25(v24, &v62);
        v10 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13FE,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v26,
            v60);
          WindowsDeleteString(v62);
          v62 = 0;
          v40 = v65;
          if ( v65 )
          {
            v65 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          }
          v41 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
          }
          v42 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
          goto LABEL_66;
        }
        if ( Reserved1 )
        {
          if ( *Reserved1 )
          {
            v27 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                    &hstringHeader,
                    L"|");
            v10 = v27;
            if ( v27 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1402,
                (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
                (const char *)(unsigned int)v27,
                v60);
              WindowsDeleteString(v62);
              v62 = 0;
              v33 = v65;
              if ( v65 )
              {
                v65 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              v34 = v60;
              if ( v60 )
              {
                v60 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
              v35 = v63;
              if ( v63 )
              {
                v63 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
              goto LABEL_44;
            }
          }
        }
        StringRawBuffer = WindowsGetStringRawBuffer(v62, 0);
        v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                &hstringHeader,
                StringRawBuffer);
        v10 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1404,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v29,
            v60);
          WindowsDeleteString(v62);
          v62 = 0;
          v37 = v65;
          if ( v65 )
          {
            v65 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          }
          v38 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          v39 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          }
          goto LABEL_44;
        }
        WindowsDeleteString(v62);
        v62 = 0;
        v30 = v65;
        if ( v65 )
        {
          v65 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
        ++v22;
        Reserved1 = hstringHeader.Reserved.Reserved1;
        if ( v22 >= v64 )
          goto LABEL_34;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13FB,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v23,
        v60);
      v43 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
      v45 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      }
LABEL_66:
      if ( !Reserved1 )
        return v10;
      v36 = Reserved1;
      goto LABEL_68;
    }
LABEL_34:
    v31 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v63;
    if ( v63 )
    {
      v63 = 0;
LABEL_86:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
  }
  else
  {
    v60 = 0;
    v46 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v13 + 152) + 72LL))(*(_QWORD *)(v13 + 152), &v60);
    v10 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x140A,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v46,
        v60);
      v47 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      return v10;
    }
    v64 = 0;
    v48 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 56LL))(v60, &v64);
    v10 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x140D,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v48,
        v60);
      v49 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      return v10;
    }
    v50 = 0;
    if ( v64 )
    {
      while ( 1 )
      {
        v62 = 0;
        v51 = v60;
        v52 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v60 + 48LL);
        WindowsDeleteString(0);
        v62 = 0;
        v53 = v52(v51, v50, &v62);
        v10 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1412,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v53,
            v60);
          WindowsDeleteString(v62);
          v62 = 0;
          v59 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          }
          goto LABEL_66;
        }
        if ( Reserved1 )
        {
          if ( *Reserved1 )
          {
            v54 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                    &hstringHeader,
                    L"|");
            v10 = v54;
            if ( v54 < 0 )
              break;
          }
        }
        v55 = WindowsGetStringRawBuffer(v62, 0);
        v56 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                &hstringHeader,
                v55);
        v10 = v56;
        if ( v56 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1418,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v56,
            v60);
          WindowsDeleteString(v62);
          v62 = 0;
          v58 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          goto LABEL_44;
        }
        WindowsDeleteString(v62);
        ++v50;
        Reserved1 = hstringHeader.Reserved.Reserved1;
        if ( v50 >= v64 )
          goto LABEL_84;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1416,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v54,
        v60);
      WindowsDeleteString(v62);
      v62 = 0;
      v57 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
LABEL_44:
      v36 = hstringHeader.Reserved.Reserved1;
      if ( !hstringHeader.Reserved.Reserved1 )
        return v10;
LABEL_68:
      CoTaskMemFree(v36);
      return v10;
    }
LABEL_84:
    v32 = v60;
    if ( v60 )
    {
      v60 = 0;
      goto LABEL_86;
    }
  }
  *a3 = Reserved1;
  return 0;
}

```

## disassembly

```asm
0x18002e070  mov     [rsp-28h+arg_8], rbx
0x18002e075  mov     [rsp-28h+arg_18], rsi
0x18002e07a  push    rbp
0x18002e07b  push    rdi
0x18002e07c  push    r12
0x18002e07e  push    r14
0x18002e080  push    r15
0x18002e082  mov     rbp, rsp
0x18002e085  sub     rsp, 80h
0x18002e08c  mov     rax, cs:__security_cookie
0x18002e093  xor     rax, rsp
0x18002e096  mov     [rbp+var_10], rax
0x18002e09a  mov     r15, r8
0x18002e09d  mov     rdi, rcx
0x18002e0a0  xor     r12d, r12d
0x18002e0a3  mov     [r8], r12
0x18002e0a6  mov     r9b, r12b
0x18002e0a9  mov     [rbp+var_58], r12b
0x18002e0ad  lea     eax, [rdx-1]
0x18002e0b0  test    eax, 0FFFFFFFDh
0x18002e0b5  jnz     short loc_18002E11E
0x18002e0b7  mov     [rbp+string], r12
0x18002e0bb  lea     r9, [rbp+string]; string
0x18002e0bf  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002e0c3  lea     edx, [r12+12h]; length
0x18002e0c8  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x18002e0cf  call    cs:__imp_WindowsCreateStringReference
0x18002e0d5  test    eax, eax
0x18002e0d7  js      loc_18002E7D5
0x18002e0dd  mov     rcx, [rdi+70h]
0x18002e0e1  mov     rax, [rcx]
0x18002e0e4  lea     r8, [rbp+var_58]
0x18002e0e8  mov     rdx, [rbp+string]
0x18002e0ec  mov     rax, [rax+50h]
0x18002e0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0f5  mov     ebx, eax
0x18002e0f7  test    eax, eax
0x18002e0f9  jns     short loc_18002E11A
0x18002e0fb  mov     rcx, [rbp+28h]; this
0x18002e0ff  mov     r9d, eax; char *
0x18002e102  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e109  mov     edx, 13E8h; void *
0x18002e10e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e113  mov     eax, ebx
0x18002e115  jmp     loc_18002E6DB
0x18002e11a  mov     r9b, [rbp+var_58]
0x18002e11e  mov     rsi, r12
0x18002e121  mov     qword ptr [rbp+hstringHeader.Reserved], r12
0x18002e125  mov     qword ptr [rbp+hstringHeader.Reserved+8], r12
0x18002e129  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r12
0x18002e12d  lea     rcx, [rdi-28h]
0x18002e131  test    r9b, r9b
0x18002e134  jz      loc_18002E56A
0x18002e13a  mov     [rbp+var_48], r12
0x18002e13e  lea     rdx, [rbp+var_48]
0x18002e142  call    ?GetStorageItemsAsync@CDataPackageView@@UEAAJPEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Z; CDataPackageView::GetStorageItemsAsync(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> * *)
0x18002e147  mov     ebx, eax
0x18002e149  test    eax, eax
0x18002e14b  jns     short loc_18002E185
0x18002e14d  mov     rcx, [rbp+28h]; this
0x18002e151  mov     r9d, eax; char *
0x18002e154  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e15b  mov     edx, 13F0h; void *
0x18002e160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e165  nop
0x18002e166  mov     rcx, [rbp+var_48]
0x18002e16a  test    rcx, rcx
0x18002e16d  jz      short loc_18002E180
0x18002e16f  mov     [rbp+var_48], r12
0x18002e173  mov     rax, [rcx]
0x18002e176  mov     rax, [rax+10h]
0x18002e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e17f  nop
0x18002e180  jmp     loc_18002E611
0x18002e185  mov     [rbp+var_60], r12
0x18002e189  lea     rdx, [rbp+var_60]
0x18002e18d  mov     rcx, [rbp+var_48]
0x18002e191  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@23@U?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *>>>,tagCOWAIT_FLAGS,void *)
0x18002e196  mov     ebx, eax
0x18002e198  test    eax, eax
0x18002e19a  jns     short loc_18002E1EE
0x18002e19c  mov     rcx, [rbp+28h]; this
0x18002e1a0  mov     r9d, eax; char *
0x18002e1a3  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e1aa  mov     edx, 13F3h; void *
0x18002e1af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e1b4  nop
0x18002e1b5  mov     rcx, [rbp+var_60]
0x18002e1b9  test    rcx, rcx
0x18002e1bc  jz      short loc_18002E1CF
0x18002e1be  mov     [rbp+var_60], r12
0x18002e1c2  mov     rax, [rcx]
0x18002e1c5  mov     rax, [rax+10h]
0x18002e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1ce  nop
0x18002e1cf  mov     rcx, [rbp+var_48]
0x18002e1d3  test    rcx, rcx
0x18002e1d6  jz      short loc_18002E1E9
0x18002e1d8  mov     [rbp+var_48], r12
0x18002e1dc  mov     rax, [rcx]
0x18002e1df  mov     rax, [rax+10h]
0x18002e1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1e8  nop
0x18002e1e9  jmp     loc_18002E611
0x18002e1ee  mov     [rbp+var_40], r12d
0x18002e1f2  mov     rcx, [rbp+var_60]
0x18002e1f6  mov     rax, [rcx]
0x18002e1f9  lea     rdx, [rbp+var_40]
0x18002e1fd  mov     rax, [rax+38h]
0x18002e201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e206  mov     ebx, eax
0x18002e208  test    eax, eax
0x18002e20a  jns     short loc_18002E25E
0x18002e20c  mov     rcx, [rbp+28h]; this
0x18002e210  mov     r9d, eax; char *
0x18002e213  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e21a  mov     edx, 13F6h; void *
0x18002e21f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e224  nop
0x18002e225  mov     rcx, [rbp+var_60]
0x18002e229  test    rcx, rcx
0x18002e22c  jz      short loc_18002E23F
0x18002e22e  mov     [rbp+var_60], r12
0x18002e232  mov     rax, [rcx]
0x18002e235  mov     rax, [rax+10h]
0x18002e239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e23e  nop
0x18002e23f  mov     rcx, [rbp+var_48]
0x18002e243  test    rcx, rcx
0x18002e246  jz      short loc_18002E259
0x18002e248  mov     [rbp+var_48], r12
0x18002e24c  mov     rax, [rcx]
0x18002e24f  mov     rax, [rax+10h]
0x18002e253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e258  nop
0x18002e259  jmp     loc_18002E611
0x18002e25e  mov     r14d, r12d
0x18002e261  cmp     [rbp+var_40], r12d
0x18002e265  jbe     loc_18002E344
0x18002e26b  mov     [rbp+var_38], r12
0x18002e26f  mov     rcx, [rbp+var_60]
0x18002e273  mov     rax, [rcx]
0x18002e276  lea     r8, [rbp+var_38]
0x18002e27a  mov     edx, r14d
0x18002e27d  mov     rax, [rax+30h]
0x18002e281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e286  mov     ebx, eax
0x18002e288  test    eax, eax
0x18002e28a  js      loc_18002E4EC
0x18002e290  mov     [rbp+var_50], r12
0x18002e294  mov     rdi, [rbp+var_38]
0x18002e298  mov     rax, [rdi]
0x18002e29b  mov     rbx, [rax+60h]
0x18002e29f  xor     ecx, ecx; string
0x18002e2a1  call    cs:__imp_WindowsDeleteString
0x18002e2a7  mov     [rbp+var_50], r12
0x18002e2ab  lea     rdx, [rbp+var_50]
0x18002e2af  mov     rcx, rdi
0x18002e2b2  mov     rax, rbx
0x18002e2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2ba  mov     ebx, eax
0x18002e2bc  test    eax, eax
0x18002e2be  js      loc_18002E475
0x18002e2c4  test    rsi, rsi
0x18002e2c7  jz      short loc_18002E2E9
0x18002e2c9  cmp     [rsi], r12w
0x18002e2cd  jz      short loc_18002E2E9
0x18002e2cf  lea     rdx, asc_180095B20; "|"
0x18002e2d6  lea     rcx, [rbp+hstringHeader]
0x18002e2da  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18002e2df  mov     ebx, eax
0x18002e2e1  test    eax, eax
0x18002e2e3  js      loc_18002E374
0x18002e2e9  xor     edx, edx; length
0x18002e2eb  mov     rcx, [rbp+var_50]; string
0x18002e2ef  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e2f5  mov     rdx, rax
0x18002e2f8  lea     rcx, [rbp+hstringHeader]
0x18002e2fc  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18002e301  mov     ebx, eax
0x18002e303  test    eax, eax
0x18002e305  js      loc_18002E3FB
0x18002e30b  mov     rcx, [rbp+var_50]; string
0x18002e30f  call    cs:__imp_WindowsDeleteString
0x18002e315  mov     [rbp+var_50], r12
0x18002e319  mov     rcx, [rbp+var_38]
0x18002e31d  test    rcx, rcx
0x18002e320  jz      short loc_18002E333
0x18002e322  mov     [rbp+var_38], r12
0x18002e326  mov     rax, [rcx]
0x18002e329  mov     rax, [rax+10h]
0x18002e32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e332  nop
0x18002e333  inc     r14d
0x18002e336  mov     rsi, qword ptr [rbp+hstringHeader.Reserved]
0x18002e33a  cmp     r14d, [rbp+var_40]
0x18002e33e  jb      loc_18002E26B
0x18002e344  mov     rcx, [rbp+var_60]
0x18002e348  test    rcx, rcx
0x18002e34b  jz      short loc_18002E35E
0x18002e34d  mov     [rbp+var_60], r12
0x18002e351  mov     rax, [rcx]
0x18002e354  mov     rax, [rax+10h]
0x18002e358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e35d  nop
0x18002e35e  mov     rcx, [rbp+var_48]
0x18002e362  test    rcx, rcx
0x18002e365  jz      loc_18002E6D6
0x18002e36b  mov     [rbp+var_48], r12
0x18002e36f  jmp     loc_18002E6C9
0x18002e374  mov     rcx, [rbp+28h]; this
0x18002e378  mov     r9d, ebx; char *
0x18002e37b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e382  mov     edx, 1402h; void *
0x18002e387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e38c  nop
0x18002e38d  mov     rcx, [rbp+var_50]; string
0x18002e391  call    cs:__imp_WindowsDeleteString
0x18002e397  mov     [rbp+var_50], r12
0x18002e39b  mov     rcx, [rbp+var_38]
0x18002e39f  test    rcx, rcx
0x18002e3a2  jz      short loc_18002E3B5
0x18002e3a4  mov     [rbp+var_38], r12
0x18002e3a8  mov     rax, [rcx]
0x18002e3ab  mov     rax, [rax+10h]
0x18002e3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3b4  nop
0x18002e3b5  mov     rcx, [rbp+var_60]
0x18002e3b9  test    rcx, rcx
0x18002e3bc  jz      short loc_18002E3CF
0x18002e3be  mov     [rbp+var_60], r12
0x18002e3c2  mov     rax, [rcx]
0x18002e3c5  mov     rax, [rax+10h]
0x18002e3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ce  nop
0x18002e3cf  mov     rcx, [rbp+var_48]
0x18002e3d3  test    rcx, rcx
0x18002e3d6  jz      short loc_18002E3E9
0x18002e3d8  mov     [rbp+var_48], r12
0x18002e3dc  mov     rax, [rcx]
0x18002e3df  mov     rax, [rax+10h]
0x18002e3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3e8  nop
0x18002e3e9  mov     rcx, qword ptr [rbp+hstringHeader.Reserved]
0x18002e3ed  test    rcx, rcx
0x18002e3f0  jz      loc_18002E113
0x18002e3f6  jmp     loc_18002E55F
0x18002e3fb  mov     rcx, [rbp+28h]; this
0x18002e3ff  mov     r9d, ebx; char *
0x18002e402  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e409  mov     edx, 1404h; void *
0x18002e40e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e413  nop
0x18002e414  mov     rcx, [rbp+var_50]; string
0x18002e418  call    cs:__imp_WindowsDeleteString
0x18002e41e  mov     [rbp+var_50], r12
0x18002e422  mov     rcx, [rbp+var_38]
0x18002e426  test    rcx, rcx
0x18002e429  jz      short loc_18002E43C
0x18002e42b  mov     [rbp+var_38], r12
0x18002e42f  mov     rax, [rcx]
0x18002e432  mov     rax, [rax+10h]
0x18002e436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e43b  nop
0x18002e43c  mov     rcx, [rbp+var_60]
0x18002e440  test    rcx, rcx
0x18002e443  jz      short loc_18002E456
0x18002e445  mov     [rbp+var_60], r12
0x18002e449  mov     rax, [rcx]
0x18002e44c  mov     rax, [rax+10h]
0x18002e450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e455  nop
0x18002e456  mov     rcx, [rbp+var_48]
0x18002e45a  test    rcx, rcx
0x18002e45d  jz      short loc_18002E470
0x18002e45f  mov     [rbp+var_48], r12
0x18002e463  mov     rax, [rcx]
0x18002e466  mov     rax, [rax+10h]
0x18002e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e46f  nop
0x18002e470  jmp     loc_18002E3E9
0x18002e475  mov     rcx, [rbp+28h]; this
0x18002e479  mov     r9d, ebx; char *
0x18002e47c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18002e483  mov     edx, 13FEh; void *
0x18002e488  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e48d  nop
0x18002e48e  mov     rcx, [rbp+var_50]; string
0x18002e492  call    cs:__imp_WindowsDeleteString
0x18002e498  mov     [rbp+var_50], r12
0x18002e49c  mov     rcx, [rbp+var_38]
0x18002e4a0  test    rcx, rcx
0x18002e4a3  jz      short loc_18002E4B6
0x18002e4a5  mov     [rbp+var_38], r12
0x18002e4a9  mov     rax, [rcx]
0x18002e4ac  mov     rax, [rax+10h]
0x18002e4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4b5  nop
0x18002e4b6  mov     rcx, [rbp+var_60]
0x18002e4ba  test    rcx, rcx
  ... truncated ...
```
