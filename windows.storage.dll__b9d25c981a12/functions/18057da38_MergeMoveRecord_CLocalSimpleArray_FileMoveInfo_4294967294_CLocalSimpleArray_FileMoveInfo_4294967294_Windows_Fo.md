# MergeMoveRecord(CLocalSimpleArray<FileMoveInfo,4294967294> *,CLocalSimpleArray<FileMoveInfo,4294967294> *,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::StorageLibraryChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::StorageLibraryChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::StorageLibraryChange *>,0> *)

- ea: `0x18057da38`
- end: `0x18057df19`
- name: `?MergeMoveRecord@@YAJPEAV?$CLocalSimpleArray@UFileMoveInfo@@$0PPPPPPPO@@@0PEAV?$AgileVector@PEAVStorageLibraryChange@Storage@Windows@@U?$DefaultEqualityPredicate@PEAVStorageLibraryChange@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVStorageLibraryChange@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@Windows@@@Z`
- size: `1249`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18057e518`
- `0x180599320`

## callees

- `0x180009fc0`
- `0x180033d90`
- `0x180038f50`
- `0x1803b1f60`
- `0x18057abd4`
- `0x18057b134`
- `0x18057b788`
- `0x18057da38`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18057dc43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18057dc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18057dc43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18057dc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057db35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dc10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dcfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057ddea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057ddfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057de37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057de4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057db35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dc10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dcfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057dda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057ddea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057ddfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057de37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18057de4f`

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
0x18057da38  mov     [rsp-8+arg_18], rbx
0x18057da3d  push    rbp
0x18057da3e  push    rsi
0x18057da3f  push    rdi
0x18057da40  push    r12
0x18057da42  push    r13
0x18057da44  push    r14
0x18057da46  push    r15
0x18057da48  lea     rbp, [rsp-27h]
0x18057da4d  sub     rsp, 0C0h
0x18057da54  mov     rax, cs:__security_cookie
0x18057da5b  xor     rax, rsp
0x18057da5e  mov     [rbp+57h+var_38], rax
0x18057da62  mov     r14, r8
0x18057da65  mov     r12, rdx
0x18057da68  mov     rdx, rcx
0x18057da6b  mov     [rbp+57h+var_78], rcx
0x18057da6f  xor     esi, esi
0x18057da71  mov     [rbp+57h+var_B8], rsi
0x18057da75  mov     [rbp+57h+var_B0], rsi
0x18057da79  mov     [rbp+57h+var_A8], rsi
0x18057da7d  mov     [rbp+57h+var_A0], rsi
0x18057da81  mov     r15d, esi
0x18057da84  mov     eax, r15d
0x18057da87  cmp     rax, [rdx+8]
0x18057da8b  jnb     loc_18057DE90
0x18057da91  lea     rcx, [rax+rax*4]
0x18057da95  mov     rax, [rdx]
0x18057da98  lea     rbx, [rax+rcx*4]
0x18057da9c  mov     [rbp+57h+var_C0], rsi
0x18057daa0  lea     r9, [rbp+57h+var_C0]
0x18057daa4  mov     r8, rbx
0x18057daa7  mov     rcx, r12
0x18057daaa  call    ??$BinarySearchEx@VFileMoveInfoCompareHelper@@@?$CTSimpleFixedArray@UFileMoveInfo@@V?$CSimpleArrayStandardCompareHelper@UFileMoveInfo@@@@@@QEBAJAEBVFileMoveInfoCompareHelper@@AEBUFileMoveInfo@@PEA_K@Z; CTSimpleFixedArray<FileMoveInfo,CSimpleArrayStandardCompareHelper<FileMoveInfo>>::BinarySearchEx<FileMoveInfoCompareHelper>(FileMoveInfoCompareHelper const &,FileMoveInfo const &,unsigned __int64 *)
0x18057daaf  test    eax, eax
0x18057dab1  js      loc_18057DD0E
0x18057dab7  mov     rdi, [r12]
0x18057dabb  mov     [rbp+57h+var_80], rdi
0x18057dabf  lea     r13, [rbx+10h]
0x18057dac3  mov     r8, r13
0x18057dac6  lea     rcx, [rbp+57h+var_B8]
0x18057daca  call    ??$_AddSortedEx@V?$CSimpleArrayStandardCompareHelper@I@@AEBI@?$CTSimpleArray@I$0PPPPPPPO@V?$CTPolicyLocalMem@I@@V?$CSimpleArrayStandardCompareHelper@I@@V?$CSimpleArrayStandardMergeHelper@I@@@@QEAAJAEBV?$CSimpleArrayStandardCompareHelper@I@@AEBIPEA_K@Z; CTSimpleArray<uint,4294967294,CTPolicyLocalMem<uint>,CSimpleArrayStandardCompareHelper<uint>,CSimpleArrayStandardMergeHelper<uint>>::_AddSortedEx<CSimpleArrayStandardCompareHelper<uint>,uint const &>(CSimpleArrayStandardCompareHelper<uint> const &,uint const &,unsigned __int64 *)
0x18057dacf  mov     ebx, eax
0x18057dad1  test    eax, eax
0x18057dad3  js      loc_18057DE65
0x18057dad9  mov     rax, [rbp+57h+var_C0]
0x18057dadd  lea     rax, [rax+rax*4]
0x18057dae1  mov     [rbp+57h+var_98], rax
0x18057dae5  mov     [rbp+57h+string], rsi
0x18057dae9  mov     [rbp+57h+var_68], rsi
0x18057daed  mov     [rbp+57h+var_58], 0
0x18057daf5  mov     rax, [r14]
0x18057daf8  mov     rbx, [rax+30h]
0x18057dafc  lea     rcx, [rbp+57h+var_58]
0x18057db00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057db05  lea     r8, [rbp+57h+var_58]
0x18057db09  mov     rax, [rbp+57h+var_98]
0x18057db0d  mov     edx, [rdi+rax*4+10h]
0x18057db11  mov     rcx, r14
0x18057db14  mov     rax, rbx
0x18057db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057db1c  mov     ebx, eax
0x18057db1e  test    eax, eax
0x18057db20  js      loc_18057DE10
0x18057db26  mov     rdi, [rbp+57h+var_58]
0x18057db2a  mov     rax, [rdi]
0x18057db2d  mov     rbx, [rax+38h]
0x18057db31  mov     rcx, [rbp+57h+string]; string
0x18057db35  call    cs:__imp_WindowsDeleteString
0x18057db3c  nop     dword ptr [rax+rax+00h]
0x18057db41  mov     [rbp+57h+string], 0
0x18057db49  lea     rdx, [rbp+57h+string]
0x18057db4d  mov     rcx, rdi
0x18057db50  mov     rax, rbx
0x18057db53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057db58  mov     ebx, eax
0x18057db5a  xor     edi, edi
0x18057db5c  test    eax, eax
0x18057db5e  js      loc_18057DDC3
0x18057db64  mov     [rbp+57h+var_70], dil
0x18057db68  mov     rcx, [rbp+57h+var_58]
0x18057db6c  mov     rax, [rcx]
0x18057db6f  lea     r8, [rbp+57h+var_70]
0x18057db73  lea     edx, [rdi+1]
0x18057db76  mov     rax, [rax+48h]
0x18057db7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057db7f  mov     ebx, eax
0x18057db81  test    eax, eax
0x18057db83  js      loc_18057DDBC
0x18057db89  cmp     [rbp+57h+var_70], dil
0x18057db8d  jz      short loc_18057DB98
0x18057db8f  mov     [rbp+57h+var_40], 1
0x18057db96  jmp     short loc_18057DBCE
0x18057db98  mov     [rbp+57h+var_6F], dil
0x18057db9c  mov     rcx, [rbp+57h+var_58]
0x18057dba0  mov     rax, [rcx]
0x18057dba3  lea     r8, [rbp+57h+var_6F]
0x18057dba7  mov     edx, 2
0x18057dbac  mov     rax, [rax+48h]
0x18057dbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057dbb5  mov     ebx, eax
0x18057dbb7  test    eax, eax
0x18057dbb9  js      loc_18057DDB5
0x18057dbbf  cmp     [rbp+57h+var_6F], dil
0x18057dbc3  mov     eax, 2
0x18057dbc8  cmovnz  esi, eax
0x18057dbcb  mov     [rbp+57h+var_40], esi
0x18057dbce  xor     esi, esi
0x18057dbd0  mov     [rbp+57h+var_50], rsi
0x18057dbd4  mov     rax, [r14]
0x18057dbd7  mov     rbx, [rax+30h]
0x18057dbdb  lea     rcx, [rbp+57h+var_50]
0x18057dbdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dbe4  lea     r8, [rbp+57h+var_50]
0x18057dbe8  mov     edx, [r13+0]
0x18057dbec  mov     rcx, r14
0x18057dbef  mov     rax, rbx
0x18057dbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057dbf7  mov     ebx, eax
0x18057dbf9  test    eax, eax
0x18057dbfb  js      loc_18057DD5B
0x18057dc01  mov     rdi, [rbp+57h+var_50]
0x18057dc05  mov     rax, [rdi]
0x18057dc08  mov     rbx, [rax+38h]
0x18057dc0c  mov     rcx, [rbp+57h+var_68]; string
0x18057dc10  call    cs:__imp_WindowsDeleteString
0x18057dc17  nop     dword ptr [rax+rax+00h]
0x18057dc1c  mov     [rbp+57h+var_68], rsi
0x18057dc20  lea     rdx, [rbp+57h+var_68]
0x18057dc24  mov     rcx, rdi
0x18057dc27  mov     rax, rbx
0x18057dc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057dc2f  mov     ebx, eax
0x18057dc31  test    eax, eax
0x18057dc33  js      loc_18057DD54
0x18057dc39  mov     [rbp+57h+var_48], rsi
0x18057dc3d  xor     edx, edx; length
0x18057dc3f  mov     rcx, [rbp+57h+var_68]; string
0x18057dc43  call    cs:__imp_WindowsGetStringRawBuffer
0x18057dc4a  nop     dword ptr [rax+rax+00h]
0x18057dc4f  mov     qword ptr [rbp+57h+var_90], rax
0x18057dc53  xor     edx, edx; length
0x18057dc55  mov     rcx, [rbp+57h+string]; string
0x18057dc59  call    cs:__imp_WindowsGetStringRawBuffer
0x18057dc60  nop     dword ptr [rax+rax+00h]
0x18057dc65  mov     [rbp+57h+var_88], rax
0x18057dc69  mov     dword ptr [rbp+57h+var_C0], 2
0x18057dc70  lea     rcx, [rbp+57h+var_48]
0x18057dc74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dc79  lea     rax, [rbp+57h+var_90]
0x18057dc7d  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18057dc82  lea     r9, [rbp+57h+var_88]
0x18057dc86  lea     r8, [rbp+57h+var_40]
0x18057dc8a  lea     rdx, [rbp+57h+var_C0]
0x18057dc8e  lea     rcx, [rbp+57h+var_48]
0x18057dc92  call    ??$MakeAndInitialize@VCStorageLibraryChange@@UIStorageLibraryChange@Storage@Windows@@AEAW4StorageLibraryChangeType@34@AEAW4StorageItemTypes@34@AEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@4@AEAV784@@Details@WRL@Microsoft@@YAJPEAPEAUIStorageLibraryChange@Storage@Windows@@AEAW4StorageLibraryChangeType@45@AEAW4StorageItemTypes@45@AEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@5@3@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageLibraryChange,Windows::Storage::IStorageLibraryChange,Windows::Storage::StorageLibraryChangeType &,Windows::Storage::StorageItemTypes &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &>(Windows::Storage::IStorageLibraryChange * *,Windows::Storage::StorageLibraryChangeType &,Windows::Storage::StorageItemTypes &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &)
0x18057dc97  mov     ebx, eax
0x18057dc99  test    eax, eax
0x18057dc9b  js      loc_18057DD30
0x18057dca1  mov     rax, [r14]
0x18057dca4  mov     r8, [rbp+57h+var_48]
0x18057dca8  mov     rdx, [rbp+57h+var_80]
0x18057dcac  mov     rcx, [rbp+57h+var_98]
0x18057dcb0  mov     edx, [rdx+rcx*4+10h]
0x18057dcb4  mov     rcx, r14
0x18057dcb7  mov     rax, [rax+50h]
0x18057dcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057dcc0  mov     ebx, eax
0x18057dcc2  test    eax, eax
0x18057dcc4  js      short loc_18057DD29
0x18057dcc6  lea     rcx, [rbp+57h+var_48]
0x18057dcca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dccf  nop
0x18057dcd0  lea     rcx, [rbp+57h+var_50]
0x18057dcd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dcd9  nop
0x18057dcda  lea     rcx, [rbp+57h+var_58]
0x18057dcde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dce3  nop
0x18057dce4  mov     rcx, [rbp+57h+var_68]; string
0x18057dce8  call    cs:__imp_WindowsDeleteString
0x18057dcef  nop     dword ptr [rax+rax+00h]
0x18057dcf4  mov     [rbp+57h+var_68], rsi
0x18057dcf8  mov     rcx, [rbp+57h+string]; string
0x18057dcfc  call    cs:__imp_WindowsDeleteString
0x18057dd03  nop     dword ptr [rax+rax+00h]
0x18057dd08  mov     [rbp+57h+string], rsi
0x18057dd0c  jmp     short loc_18057DD1D
0x18057dd0e  mov     rax, [r12+8]
0x18057dd13  cmp     [rbp+57h+var_C0], rax
0x18057dd17  jnb     loc_18057DE90
0x18057dd1d  inc     r15d
0x18057dd20  mov     rdx, [rbp+57h+var_78]
0x18057dd24  jmp     loc_18057DA84
0x18057dd29  mov     edx, 54h ; 'T'
0x18057dd2e  jmp     short loc_18057DD35
0x18057dd30  mov     edx, 52h ; 'R'; void *
0x18057dd35  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057dd3c  mov     r9d, ebx; char *
0x18057dd3f  mov     rcx, [rbp+5Fh]; this
0x18057dd43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057dd48  nop
0x18057dd49  lea     rcx, [rbp+57h+var_48]
0x18057dd4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dd52  jmp     short loc_18057DD74
0x18057dd54  mov     edx, 4Fh ; 'O'
0x18057dd59  jmp     short loc_18057DD60
0x18057dd5b  mov     edx, 4Eh ; 'N'; void *
0x18057dd60  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057dd67  mov     r9d, ebx; char *
0x18057dd6a  mov     rcx, [rbp+5Fh]; this
0x18057dd6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057dd73  nop
0x18057dd74  lea     rcx, [rbp+57h+var_50]
0x18057dd78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dd7d  nop
0x18057dd7e  lea     rcx, [rbp+57h+var_58]
0x18057dd82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dd87  nop
0x18057dd88  mov     rcx, [rbp+57h+var_68]; string
0x18057dd8c  call    cs:__imp_WindowsDeleteString
0x18057dd93  nop     dword ptr [rax+rax+00h]
0x18057dd98  mov     [rbp+57h+var_68], rsi
0x18057dd9c  mov     rcx, [rbp+57h+string]; string
0x18057dda0  call    cs:__imp_WindowsDeleteString
0x18057dda7  nop     dword ptr [rax+rax+00h]
0x18057ddac  mov     [rbp+57h+string], rsi
0x18057ddb0  jmp     loc_18057DE7E
0x18057ddb5  mov     edx, 46h ; 'F'
0x18057ddba  jmp     short loc_18057DDC8
0x18057ddbc  mov     edx, 3Eh ; '>'
0x18057ddc1  jmp     short loc_18057DDC8
0x18057ddc3  mov     edx, 3Bh ; ';'; void *
0x18057ddc8  mov     rcx, [rbp+5Fh]; this
0x18057ddcc  mov     r9d, ebx; char *
0x18057ddcf  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057ddd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057dddb  nop
0x18057dddc  lea     rcx, [rbp+57h+var_58]
0x18057dde0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057dde5  nop
0x18057dde6  mov     rcx, [rbp+57h+var_68]; string
0x18057ddea  call    cs:__imp_WindowsDeleteString
0x18057ddf1  nop     dword ptr [rax+rax+00h]
0x18057ddf6  mov     [rbp+57h+var_68], rdi
0x18057ddfa  mov     rcx, [rbp+57h+string]; string
0x18057ddfe  call    cs:__imp_WindowsDeleteString
0x18057de05  nop     dword ptr [rax+rax+00h]
0x18057de0a  mov     [rbp+57h+string], rdi
0x18057de0e  jmp     short loc_18057DE7E
0x18057de10  mov     rcx, [rbp+5Fh]; this
0x18057de14  mov     r9d, ebx; char *
0x18057de17  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057de1e  mov     edx, 3Ah ; ':'; void *
0x18057de23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057de28  nop
0x18057de29  lea     rcx, [rbp+57h+var_58]
0x18057de2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18057de32  nop
0x18057de33  mov     rcx, [rbp+57h+var_68]; string
0x18057de37  call    cs:__imp_WindowsDeleteString
0x18057de3e  nop     dword ptr [rax+rax+00h]
0x18057de43  mov     [rbp+57h+var_68], 0
0x18057de4b  mov     rcx, [rbp+57h+string]; string
0x18057de4f  call    cs:__imp_WindowsDeleteString
0x18057de56  nop     dword ptr [rax+rax+00h]
0x18057de5b  mov     [rbp+57h+string], 0
0x18057de63  jmp     short loc_18057DE7E
0x18057de65  mov     rcx, [rbp+5Fh]; this
0x18057de69  mov     r9d, ebx; char *
0x18057de6c  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057de73  mov     edx, 32h ; '2'; void *
0x18057de78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057de7d  nop
0x18057de7e  mov     rcx, [rbp+57h+var_B8]; void *
0x18057de82  test    rcx, rcx
0x18057de85  jz      short loc_18057DE8C
0x18057de87  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18057de8c  mov     eax, ebx
0x18057de8e  jmp     short loc_18057DEF1
0x18057de90  mov     rdi, [rbp+57h+var_B0]
0x18057de94  mov     rbx, [rbp+57h+var_B8]
0x18057de98  test    rdi, rdi
0x18057de9b  jz      short loc_18057DEE2
0x18057de9d  dec     rdi
0x18057dea0  mov     rax, [r14]
0x18057dea3  mov     edx, [rbx+rdi*4]
0x18057dea6  mov     rcx, r14
0x18057dea9  mov     rax, [rax+60h]
0x18057dead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057deb2  mov     esi, eax
0x18057deb4  test    eax, eax
0x18057deb6  jns     short loc_18057DE98
0x18057deb8  mov     rcx, [rbp+5Fh]; this
0x18057debc  mov     r9d, eax; char *
0x18057debf  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x18057dec6  mov     edx, 64h ; 'd'; void *
0x18057decb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18057ded0  nop
0x18057ded1  test    rbx, rbx
  ... truncated ...
```
