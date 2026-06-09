# MergeMoveRecord(CLocalSimpleArray<FileMoveInfo,4294967294> *,CLocalSimpleArray<FileMoveInfo,4294967294> *,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::StorageLibraryChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::StorageLibraryChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::StorageLibraryChange *>,0> *)

- ea: `0x180564700`
- end: `0x180564b98`
- name: `?MergeMoveRecord@@YAJPEAV?$CLocalSimpleArray@UFileMoveInfo@@$0PPPPPPPO@@@0PEAV?$AgileVector@PEAVStorageLibraryChange@Storage@Windows@@U?$DefaultEqualityPredicate@PEAVStorageLibraryChange@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVStorageLibraryChange@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@Windows@@@Z`
- size: `1176`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180565184`
- `0x18057e010`

## callees

- `0x18000d6cc`
- `0x18003e390`
- `0x1800432f0`
- `0x1803a4cb0`
- `0x180561914`
- `0x180561e60`
- `0x1805624b0`
- `0x180564700`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805648ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18056490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805648ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18056490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805647fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805648d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805649a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564ac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805647fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805648d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805649a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564a90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564ac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180564ad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MergeMoveRecord(_QWORD *a1, __int64 *a2, __int64 a3)
{
  _QWORD *v5; // rdx
  int v6; // esi
  unsigned int i; // r15d
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdi
  unsigned int *v11; // r13
  int v12; // eax
  int v13; // ebx
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v25; // rdi
  unsigned int *v26; // rbx
  int v27; // eax
  unsigned int v28; // esi
  int v29; // [rsp+20h] [rbp-79h]
  unsigned __int64 v30; // [rsp+30h] [rbp-69h] BYREF
  void *v31; // [rsp+38h] [rbp-61h] BYREF
  __int64 v32; // [rsp+40h] [rbp-59h]
  __int64 v33; // [rsp+48h] [rbp-51h]
  __int64 v34; // [rsp+50h] [rbp-49h]
  __int64 v35; // [rsp+58h] [rbp-41h]
  int v36[2]; // [rsp+60h] [rbp-39h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-31h] BYREF
  __int64 v38; // [rsp+70h] [rbp-29h]
  _QWORD *v39; // [rsp+78h] [rbp-21h]
  char v40; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v41[7]; // [rsp+81h] [rbp-18h] BYREF
  HSTRING v42; // [rsp+88h] [rbp-11h] BYREF
  HSTRING string; // [rsp+90h] [rbp-9h] BYREF
  __int64 v44; // [rsp+98h] [rbp-1h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v46; // [rsp+A8h] [rbp+Fh] BYREF
  int v47; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a1;
  v39 = a1;
  v6 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  for ( i = 0; (unsigned __int64)i < v5[1]; ++i )
  {
    v8 = *v5 + 20LL * i;
    v30 = 0;
    if ( (int)CTSimpleFixedArray<FileMoveInfo,CSimpleArrayStandardCompareHelper<FileMoveInfo>>::BinarySearchEx<FileMoveInfoCompareHelper>(
                a2,
                v5,
                v8,
                &v30) < 0 )
    {
      if ( v30 >= a2[1] )
        break;
    }
    else
    {
      v10 = *a2;
      v38 = *a2;
      v11 = (unsigned int *)(v8 + 16);
      v12 = CTSimpleArray<unsigned int,4294967294,CTPolicyLocalMem<unsigned int>,CSimpleArrayStandardCompareHelper<unsigned int>,CSimpleArrayStandardMergeHelper<unsigned int>>::_AddSortedEx<CSimpleArrayStandardCompareHelper<unsigned int>,unsigned int const &>(
              &v31,
              v9,
              v8 + 16);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
          (const char *)(unsigned int)v12,
          v29);
        goto LABEL_34;
      }
      v35 = 5 * v30;
      string = 0;
      v42 = 0;
      v44 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      v15 = v14(a3, *(unsigned int *)(v10 + 4 * v35 + 16), &v44);
      v13 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
          (const char *)(unsigned int)v15,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        WindowsDeleteString(v42);
        v42 = 0;
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_34;
      }
      v16 = v44;
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v13 = v17(v16, &string);
      if ( v13 < 0 )
      {
        v23 = 59;
        goto LABEL_31;
      }
      v40 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v44 + 72LL))(v44, 1, &v40);
      if ( v13 < 0 )
      {
        v23 = 62;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
          (const char *)(unsigned int)v13,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        WindowsDeleteString(v42);
        v42 = 0;
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_34;
      }
      if ( v40 )
      {
        v47 = 1;
      }
      else
      {
        v41[0] = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v44 + 72LL))(v44, 2, v41);
        if ( v13 < 0 )
        {
          v23 = 70;
          goto LABEL_31;
        }
        if ( v41[0] )
          v6 = 2;
        v47 = v6;
      }
      v6 = 0;
      v45 = 0;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v13 = v18(a3, *v11, &v45);
      if ( v13 < 0 )
      {
        v22 = 78;
        goto LABEL_26;
      }
      v19 = v45;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 56LL);
      WindowsDeleteString(v42);
      v42 = 0;
      v13 = v20(v19, &v42);
      if ( v13 < 0 )
      {
        v22 = 79;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
          (const char *)(unsigned int)v13,
          v29);
        goto LABEL_27;
      }
      v46 = 0;
      *(_QWORD *)v36 = WindowsGetStringRawBuffer(v42, 0);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LODWORD(v30) = 2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v13 = Microsoft::WRL::Details::MakeAndInitialize<CStorageLibraryChange,Windows::Storage::IStorageLibraryChange,enum Windows::Storage::StorageLibraryChangeType &,enum Windows::Storage::StorageItemTypes &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>> &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>> &>(
              (unsigned int)&v46,
              (unsigned int)&v30,
              (unsigned int)&v47,
              (unsigned int)&StringRawBuffer,
              (__int64)v36);
      if ( v13 < 0 )
      {
        v21 = 82;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
          (const char *)(unsigned int)v13,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_27:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        WindowsDeleteString(v42);
        v42 = 0;
        WindowsDeleteString(string);
        string = 0;
LABEL_34:
        if ( v31 )
          CTContainer_PolicyLocalMem::DestroyMem(v31);
        return (unsigned int)v13;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a3 + 80LL))(
              a3,
              *(unsigned int *)(v38 + 4 * v35 + 16),
              v46);
      if ( v13 < 0 )
      {
        v21 = 84;
        goto LABEL_23;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      WindowsDeleteString(v42);
      v42 = 0;
      WindowsDeleteString(string);
      string = 0;
    }
    v5 = v39;
  }
  v25 = v32;
  v26 = (unsigned int *)v31;
  while ( v25 )
  {
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 96LL))(a3, v26[--v25]);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
        (const char *)(unsigned int)v27,
        v29);
      if ( v26 )
        CTContainer_PolicyLocalMem::DestroyMem(v26);
      return v28;
    }
  }
  if ( v26 )
    CTContainer_PolicyLocalMem::DestroyMem(v26);
  return 0;
}

```

## disassembly

```asm
0x180564700  mov     [rsp-8+arg_18], rbx
0x180564705  push    rbp
0x180564706  push    rsi
0x180564707  push    rdi
0x180564708  push    r12
0x18056470a  push    r13
0x18056470c  push    r14
0x18056470e  push    r15
0x180564710  lea     rbp, [rsp-27h]
0x180564715  sub     rsp, 0C0h
0x18056471c  mov     rax, cs:__security_cookie
0x180564723  xor     rax, rsp
0x180564726  mov     [rbp+57h+var_38], rax
0x18056472a  mov     r14, r8
0x18056472d  mov     r12, rdx
0x180564730  mov     rdx, rcx
0x180564733  mov     [rbp+57h+var_78], rcx
0x180564737  xor     esi, esi
0x180564739  mov     [rbp+57h+var_B8], rsi
0x18056473d  mov     [rbp+57h+var_B0], rsi
0x180564741  mov     [rbp+57h+var_A8], rsi
0x180564745  mov     [rbp+57h+var_A0], rsi
0x180564749  mov     r15d, esi
0x18056474c  mov     eax, r15d
0x18056474f  cmp     rax, [rdx+8]
0x180564753  jnb     loc_180564B10
0x180564759  lea     rcx, [rax+rax*4]
0x18056475d  mov     rax, [rdx]
0x180564760  lea     rbx, [rax+rcx*4]
0x180564764  mov     [rbp+57h+var_C0], rsi
0x180564768  lea     r9, [rbp+57h+var_C0]
0x18056476c  mov     r8, rbx
0x18056476f  mov     rcx, r12
0x180564772  call    ??$BinarySearchEx@VFileMoveInfoCompareHelper@@@?$CTSimpleFixedArray@UFileMoveInfo@@V?$CSimpleArrayStandardCompareHelper@UFileMoveInfo@@@@@@QEBAJAEBVFileMoveInfoCompareHelper@@AEBUFileMoveInfo@@PEA_K@Z; CTSimpleFixedArray<FileMoveInfo,CSimpleArrayStandardCompareHelper<FileMoveInfo>>::BinarySearchEx<FileMoveInfoCompareHelper>(FileMoveInfoCompareHelper const &,FileMoveInfo const &,unsigned __int64 *)
0x180564777  test    eax, eax
0x180564779  js      loc_1805649B2
0x18056477f  mov     rdi, [r12]
0x180564783  mov     [rbp+57h+var_80], rdi
0x180564787  lea     r13, [rbx+10h]
0x18056478b  mov     r8, r13
0x18056478e  lea     rcx, [rbp+57h+var_B8]
0x180564792  call    ??$_AddSortedEx@V?$CSimpleArrayStandardCompareHelper@I@@AEBI@?$CTSimpleArray@I$0PPPPPPPO@V?$CTPolicyLocalMem@I@@V?$CSimpleArrayStandardCompareHelper@I@@V?$CSimpleArrayStandardMergeHelper@I@@@@QEAAJAEBV?$CSimpleArrayStandardCompareHelper@I@@AEBIPEA_K@Z; CTSimpleArray<uint,4294967294,CTPolicyLocalMem<uint>,CSimpleArrayStandardCompareHelper<uint>,CSimpleArrayStandardMergeHelper<uint>>::_AddSortedEx<CSimpleArrayStandardCompareHelper<uint>,uint const &>(CSimpleArrayStandardCompareHelper<uint> const &,uint const &,unsigned __int64 *)
0x180564797  mov     ebx, eax
0x180564799  test    eax, eax
0x18056479b  js      loc_180564AE5
0x1805647a1  mov     rax, [rbp+57h+var_C0]
0x1805647a5  lea     rax, [rax+rax*4]
0x1805647a9  mov     [rbp+57h+var_98], rax
0x1805647ad  mov     [rbp+57h+string], rsi
0x1805647b1  mov     [rbp+57h+var_68], rsi
0x1805647b5  mov     [rbp+57h+var_58], 0
0x1805647bd  mov     rax, [r14]
0x1805647c0  mov     rbx, [rax+30h]
0x1805647c4  lea     rcx, [rbp+57h+var_58]
0x1805647c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805647cd  lea     r8, [rbp+57h+var_58]
0x1805647d1  mov     rax, [rbp+57h+var_98]
0x1805647d5  mov     edx, [rdi+rax*4+10h]
0x1805647d9  mov     rcx, r14
0x1805647dc  mov     rax, rbx
0x1805647df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805647e4  mov     ebx, eax
0x1805647e6  test    eax, eax
0x1805647e8  js      loc_180564A9C
0x1805647ee  mov     rdi, [rbp+57h+var_58]
0x1805647f2  mov     rax, [rdi]
0x1805647f5  mov     rbx, [rax+38h]
0x1805647f9  mov     rcx, [rbp+57h+string]; string
0x1805647fd  call    cs:__imp_WindowsDeleteString
0x180564803  mov     [rbp+57h+string], 0
0x18056480b  lea     rdx, [rbp+57h+string]
0x18056480f  mov     rcx, rdi
0x180564812  mov     rax, rbx
0x180564815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056481a  mov     ebx, eax
0x18056481c  xor     edi, edi
0x18056481e  test    eax, eax
0x180564820  js      loc_180564A5B
0x180564826  mov     [rbp+57h+var_70], dil
0x18056482a  mov     rcx, [rbp+57h+var_58]
0x18056482e  mov     rax, [rcx]
0x180564831  lea     r8, [rbp+57h+var_70]
0x180564835  lea     edx, [rdi+1]
0x180564838  mov     rax, [rax+48h]
0x18056483c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180564841  mov     ebx, eax
0x180564843  test    eax, eax
0x180564845  js      loc_180564A54
0x18056484b  cmp     [rbp+57h+var_70], dil
0x18056484f  jz      short loc_18056485A
0x180564851  mov     [rbp+57h+var_40], 1
0x180564858  jmp     short loc_180564890
0x18056485a  mov     [rbp+57h+var_6F], dil
0x18056485e  mov     rcx, [rbp+57h+var_58]
0x180564862  mov     rax, [rcx]
0x180564865  lea     r8, [rbp+57h+var_6F]
0x180564869  mov     edx, 2
0x18056486e  mov     rax, [rax+48h]
0x180564872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180564877  mov     ebx, eax
0x180564879  test    eax, eax
0x18056487b  js      loc_180564A4D
0x180564881  cmp     [rbp+57h+var_6F], dil
0x180564885  mov     eax, 2
0x18056488a  cmovnz  esi, eax
0x18056488d  mov     [rbp+57h+var_40], esi
0x180564890  xor     esi, esi
0x180564892  mov     [rbp+57h+var_50], rsi
0x180564896  mov     rax, [r14]
0x180564899  mov     rbx, [rax+30h]
0x18056489d  lea     rcx, [rbp+57h+var_50]
0x1805648a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805648a6  lea     r8, [rbp+57h+var_50]
0x1805648aa  mov     edx, [r13+0]
0x1805648ae  mov     rcx, r14
0x1805648b1  mov     rax, rbx
0x1805648b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805648b9  mov     ebx, eax
0x1805648bb  test    eax, eax
0x1805648bd  js      loc_1805649FF
0x1805648c3  mov     rdi, [rbp+57h+var_50]
0x1805648c7  mov     rax, [rdi]
0x1805648ca  mov     rbx, [rax+38h]
0x1805648ce  mov     rcx, [rbp+57h+var_68]; string
0x1805648d2  call    cs:__imp_WindowsDeleteString
0x1805648d8  mov     [rbp+57h+var_68], rsi
0x1805648dc  lea     rdx, [rbp+57h+var_68]
0x1805648e0  mov     rcx, rdi
0x1805648e3  mov     rax, rbx
0x1805648e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805648eb  mov     ebx, eax
0x1805648ed  test    eax, eax
0x1805648ef  js      loc_1805649F8
0x1805648f5  mov     [rbp+57h+var_48], rsi
0x1805648f9  xor     edx, edx; length
0x1805648fb  mov     rcx, [rbp+57h+var_68]; string
0x1805648ff  call    cs:__imp_WindowsGetStringRawBuffer
0x180564905  mov     qword ptr [rbp+57h+var_90], rax
0x180564909  xor     edx, edx; length
0x18056490b  mov     rcx, [rbp+57h+string]; string
0x18056490f  call    cs:__imp_WindowsGetStringRawBuffer
0x180564915  mov     [rbp+57h+var_88], rax
0x180564919  mov     dword ptr [rbp+57h+var_C0], 2
0x180564920  lea     rcx, [rbp+57h+var_48]
0x180564924  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564929  lea     rax, [rbp+57h+var_90]
0x18056492d  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180564932  lea     r9, [rbp+57h+var_88]
0x180564936  lea     r8, [rbp+57h+var_40]
0x18056493a  lea     rdx, [rbp+57h+var_C0]
0x18056493e  lea     rcx, [rbp+57h+var_48]
0x180564942  call    ??$MakeAndInitialize@VCStorageLibraryChange@@UIStorageLibraryChange@Storage@Windows@@AEAW4StorageLibraryChangeType@34@AEAW4StorageItemTypes@34@AEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@4@AEAV784@@Details@WRL@Microsoft@@YAJPEAPEAUIStorageLibraryChange@Storage@Windows@@AEAW4StorageLibraryChangeType@45@AEAW4StorageItemTypes@45@AEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@5@3@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageLibraryChange,Windows::Storage::IStorageLibraryChange,Windows::Storage::StorageLibraryChangeType &,Windows::Storage::StorageItemTypes &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &>(Windows::Storage::IStorageLibraryChange * *,Windows::Storage::StorageLibraryChangeType &,Windows::Storage::StorageItemTypes &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &)
0x180564947  mov     ebx, eax
0x180564949  test    eax, eax
0x18056494b  js      loc_1805649D4
0x180564951  mov     rax, [r14]
0x180564954  mov     r8, [rbp+57h+var_48]
0x180564958  mov     rdx, [rbp+57h+var_80]
0x18056495c  mov     rcx, [rbp+57h+var_98]
0x180564960  mov     edx, [rdx+rcx*4+10h]
0x180564964  mov     rcx, r14
0x180564967  mov     rax, [rax+50h]
0x18056496b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180564970  mov     ebx, eax
0x180564972  test    eax, eax
0x180564974  js      short loc_1805649CD
0x180564976  lea     rcx, [rbp+57h+var_48]
0x18056497a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18056497f  nop
0x180564980  lea     rcx, [rbp+57h+var_50]
0x180564984  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564989  nop
0x18056498a  lea     rcx, [rbp+57h+var_58]
0x18056498e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564993  nop
0x180564994  mov     rcx, [rbp+57h+var_68]; string
0x180564998  call    cs:__imp_WindowsDeleteString
0x18056499e  mov     [rbp+57h+var_68], rsi
0x1805649a2  mov     rcx, [rbp+57h+string]; string
0x1805649a6  call    cs:__imp_WindowsDeleteString
0x1805649ac  mov     [rbp+57h+string], rsi
0x1805649b0  jmp     short loc_1805649C1
0x1805649b2  mov     rax, [r12+8]
0x1805649b7  cmp     [rbp+57h+var_C0], rax
0x1805649bb  jnb     loc_180564B10
0x1805649c1  inc     r15d
0x1805649c4  mov     rdx, [rbp+57h+var_78]
0x1805649c8  jmp     loc_18056474C
0x1805649cd  mov     edx, 54h ; 'T'
0x1805649d2  jmp     short loc_1805649D9
0x1805649d4  mov     edx, 52h ; 'R'; void *
0x1805649d9  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1805649e0  mov     r9d, ebx; char *
0x1805649e3  mov     rcx, [rbp+5Fh]; this
0x1805649e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805649ec  nop
0x1805649ed  lea     rcx, [rbp+57h+var_48]
0x1805649f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805649f6  jmp     short loc_180564A18
0x1805649f8  mov     edx, 4Fh ; 'O'
0x1805649fd  jmp     short loc_180564A04
0x1805649ff  mov     edx, 4Eh ; 'N'; void *
0x180564a04  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x180564a0b  mov     r9d, ebx; char *
0x180564a0e  mov     rcx, [rbp+5Fh]; this
0x180564a12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180564a17  nop
0x180564a18  lea     rcx, [rbp+57h+var_50]
0x180564a1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564a21  nop
0x180564a22  lea     rcx, [rbp+57h+var_58]
0x180564a26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564a2b  nop
0x180564a2c  mov     rcx, [rbp+57h+var_68]; string
0x180564a30  call    cs:__imp_WindowsDeleteString
0x180564a36  mov     [rbp+57h+var_68], rsi
0x180564a3a  mov     rcx, [rbp+57h+string]; string
0x180564a3e  call    cs:__imp_WindowsDeleteString
0x180564a44  mov     [rbp+57h+string], rsi
0x180564a48  jmp     loc_180564AFE
0x180564a4d  mov     edx, 46h ; 'F'
0x180564a52  jmp     short loc_180564A60
0x180564a54  mov     edx, 3Eh ; '>'
0x180564a59  jmp     short loc_180564A60
0x180564a5b  mov     edx, 3Bh ; ';'; void *
0x180564a60  mov     rcx, [rbp+5Fh]; this
0x180564a64  mov     r9d, ebx; char *
0x180564a67  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x180564a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180564a73  nop
0x180564a74  lea     rcx, [rbp+57h+var_58]
0x180564a78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564a7d  nop
0x180564a7e  mov     rcx, [rbp+57h+var_68]; string
0x180564a82  call    cs:__imp_WindowsDeleteString
0x180564a88  mov     [rbp+57h+var_68], rdi
0x180564a8c  mov     rcx, [rbp+57h+string]; string
0x180564a90  call    cs:__imp_WindowsDeleteString
0x180564a96  mov     [rbp+57h+string], rdi
0x180564a9a  jmp     short loc_180564AFE
0x180564a9c  mov     rcx, [rbp+5Fh]; this
0x180564aa0  mov     r9d, ebx; char *
0x180564aa3  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x180564aaa  mov     edx, 3Ah ; ':'; void *
0x180564aaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180564ab4  nop
0x180564ab5  lea     rcx, [rbp+57h+var_58]
0x180564ab9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180564abe  nop
0x180564abf  mov     rcx, [rbp+57h+var_68]; string
0x180564ac3  call    cs:__imp_WindowsDeleteString
0x180564ac9  mov     [rbp+57h+var_68], 0
0x180564ad1  mov     rcx, [rbp+57h+string]; string
0x180564ad5  call    cs:__imp_WindowsDeleteString
0x180564adb  mov     [rbp+57h+string], 0
0x180564ae3  jmp     short loc_180564AFE
0x180564ae5  mov     rcx, [rbp+5Fh]; this
0x180564ae9  mov     r9d, ebx; char *
0x180564aec  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x180564af3  mov     edx, 32h ; '2'; void *
0x180564af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180564afd  nop
0x180564afe  mov     rcx, [rbp+57h+var_B8]; void *
0x180564b02  test    rcx, rcx
0x180564b05  jz      short loc_180564B0C
0x180564b07  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180564b0c  mov     eax, ebx
0x180564b0e  jmp     short loc_180564B71
0x180564b10  mov     rdi, [rbp+57h+var_B0]
0x180564b14  mov     rbx, [rbp+57h+var_B8]
0x180564b18  test    rdi, rdi
0x180564b1b  jz      short loc_180564B62
0x180564b1d  dec     rdi
0x180564b20  mov     rax, [r14]
0x180564b23  mov     edx, [rbx+rdi*4]
0x180564b26  mov     rcx, r14
0x180564b29  mov     rax, [rax+60h]
0x180564b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180564b32  mov     esi, eax
0x180564b34  test    eax, eax
0x180564b36  jns     short loc_180564B18
0x180564b38  mov     rcx, [rbp+5Fh]; this
0x180564b3c  mov     r9d, eax; char *
0x180564b3f  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x180564b46  mov     edx, 64h ; 'd'; void *
0x180564b4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180564b50  nop
0x180564b51  test    rbx, rbx
0x180564b54  jz      short loc_180564B5E
0x180564b56  mov     rcx, rbx; void *
0x180564b59  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180564b5e  mov     eax, esi
0x180564b60  jmp     short loc_180564B71
0x180564b62  test    rbx, rbx
0x180564b65  jz      short loc_180564B6F
0x180564b67  mov     rcx, rbx; void *
0x180564b6a  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180564b6f  xor     eax, eax
0x180564b71  mov     rcx, [rbp+57h+var_38]
0x180564b75  xor     rcx, rsp; StackCookie
  ... truncated ...
```
