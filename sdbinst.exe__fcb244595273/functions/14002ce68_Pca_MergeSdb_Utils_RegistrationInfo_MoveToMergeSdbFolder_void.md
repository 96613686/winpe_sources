# Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder(void)

- ea: `0x14002ce68`
- end: `0x14002d106`
- name: `?MoveToMergeSdbFolder@RegistrationInfo@Utils@MergeSdb@Pca@@AEAAKXZ`
- size: `670`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140028714`

## callees

- `0x14001008c`
- `0x1400248cc`
- `0x140028350`
- `0x14002a044`
- `0x14002a3a8`
- `0x14002acfc`
- `0x14002cd38`
- `0x14002ce68`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002d024`
- `KERNEL32!GetLastError` at `0x14002d024`
- `KERNEL32!GetProcessHeap` at `0x14002cedb`
- `KERNEL32!GetProcessHeap` at `0x14002cf8e`
- `KERNEL32!GetProcessHeap` at `0x14002cfa8`
- `KERNEL32!GetProcessHeap` at `0x14002cfdc`
- `KERNEL32!GetProcessHeap` at `0x14002cff6`
- `KERNEL32!GetProcessHeap` at `0x14002d059`
- `KERNEL32!GetProcessHeap` at `0x14002d073`
- `KERNEL32!GetProcessHeap` at `0x14002cedb`
- `KERNEL32!GetProcessHeap` at `0x14002cf8e`
- `KERNEL32!GetProcessHeap` at `0x14002cfa8`
- `KERNEL32!GetProcessHeap` at `0x14002cfdc`
- `KERNEL32!GetProcessHeap` at `0x14002cff6`
- `KERNEL32!GetProcessHeap` at `0x14002d059`
- `KERNEL32!GetProcessHeap` at `0x14002d073`
- `KERNEL32!CopyFileW` at `0x14002d01a`
- `KERNEL32!CopyFileW` at `0x14002d01a`
- `KERNEL32!HeapFree` at `0x14002cee9`
- `KERNEL32!HeapFree` at `0x14002cf9c`
- `KERNEL32!HeapFree` at `0x14002cfb6`
- `KERNEL32!HeapFree` at `0x14002cfea`
- `KERNEL32!HeapFree` at `0x14002d004`
- `KERNEL32!HeapFree` at `0x14002d067`
- `KERNEL32!HeapFree` at `0x14002d081`
- `KERNEL32!HeapFree` at `0x14002cee9`
- `KERNEL32!HeapFree` at `0x14002cf9c`
- `KERNEL32!HeapFree` at `0x14002cfb6`
- `KERNEL32!HeapFree` at `0x14002cfea`
- `KERNEL32!HeapFree` at `0x14002d004`
- `KERNEL32!HeapFree` at `0x14002d067`
- `KERNEL32!HeapFree` at `0x14002d081`

## string_xrefs

- `0x14002d09e`: `Unable to copy ACLs from parent (%d)`
- `0x14002ceb3`: `Failed to get the sdb merge dir path (%d)`
- `0x14002cec0`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002cf19`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002cf73`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002d047`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002d0ab`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002d0e5`: `Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder`
- `0x14002d0d8`: `Failed to move merge sdb as registration state is invalid`
- `0x14002cf66`: `Failed to create merge sdb full path (%d)`
- `0x14002cf0c`: `Failed to ensure the merge sdb directory (%d)`
- `0x14002d03a`: `Failed to copy merge sdb to merge sdb directory (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder(
        Pca::MergeSdb::Utils::RegistrationInfo *this)
{
  int MergeSdbDirectoryPath; // eax
  unsigned int v3; // edi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // r14d
  WCHAR *v12; // rdi
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  unsigned __int16 *v17; // rdx
  DWORD LastError; // esi
  HANDLE v19; // rax
  HANDLE v20; // rax
  unsigned int v21; // eax
  LPCWSTR lpNewFileName; // [rsp+60h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+38h] BYREF
  void *v24; // [rsp+70h] [rbp+40h] BYREF

  if ( !*((_BYTE *)this + 16) || !*(_QWORD *)this || !*((_QWORD *)this + 13) )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
      1510,
      "Failed to move merge sdb as registration state is invalid");
    return 5023;
  }
  lpMem = 0;
  MergeSdbDirectoryPath = Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(&lpMem);
  v3 = MergeSdbDirectoryPath;
  if ( MergeSdbDirectoryPath )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
      1517,
      "Failed to get the sdb merge dir path (%d)",
      MergeSdbDirectoryPath);
    v4 = lpMem;
LABEL_6:
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    return v3;
  }
  v4 = lpMem;
  v7 = Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory((const unsigned __int16 *)lpMem);
  v3 = v7;
  if ( v7 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
      1522,
      "Failed to ensure the merge sdb directory (%d)",
      v7);
    goto LABEL_6;
  }
  lpNewFileName = 0;
  v24 = v4;
  v9 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],unsigned short const *>(
         &lpNewFileName,
         &v24,
         v8,
         (char *)this + 104);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v9;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
      1531,
      "Failed to create merge sdb full path (%d)",
      v11);
    v12 = (WCHAR *)lpNewFileName;
    goto LABEL_15;
  }
  v12 = (WCHAR *)lpNewFileName;
  if ( Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile(*(LPCWSTR *)this, lpNewFileName, v10) )
    goto LABEL_21;
  if ( CopyFileW(*(LPCWSTR *)this, v12, 0) )
  {
    v21 = Pca::MergeSdb::Utils::CopyAclsFromParentDir(v12, v17);
    v11 = v21;
    if ( v21 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
        1547,
        "Unable to copy ACLs from parent (%d)",
        v21);
LABEL_15:
      if ( v12 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
      }
      if ( v4 )
      {
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v4);
      }
      return v11;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      this,
      &lpNewFileName);
    v12 = (WCHAR *)lpNewFileName;
LABEL_21:
    if ( v12 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v12);
    }
    if ( v4 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v4);
    }
    return 0;
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder",
    1542,
    "Failed to copy merge sdb to merge sdb directory (%d)",
    LastError);
  if ( v12 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v12);
  }
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x14002ce68  push    rbp
0x14002ce6a  push    rbx
0x14002ce6b  push    rsi
0x14002ce6c  push    rdi
0x14002ce6d  push    r14
0x14002ce6f  mov     rbp, rsp
0x14002ce72  sub     rsp, 30h
0x14002ce76  mov     rsi, rcx
0x14002ce79  cmp     byte ptr [rcx+10h], 0
0x14002ce7d  jz      loc_14002D0D8
0x14002ce83  cmp     qword ptr [rcx], 0
0x14002ce87  jz      loc_14002D0D8
0x14002ce8d  cmp     qword ptr [rcx+68h], 0
0x14002ce92  jz      loc_14002D0D8
0x14002ce98  mov     [rbp+lpMem], 0
0x14002cea0  lea     rcx, [rbp+lpMem]
0x14002cea4  call    ?GetMergeSdbDirectoryPath@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002cea9  mov     edi, eax
0x14002ceab  test    eax, eax
0x14002cead  jz      short loc_14002CEF6
0x14002ceaf  mov     [rsp+30h+var_10], eax
0x14002ceb3  lea     r9, aFailedToGetThe_1; "Failed to get the sdb merge dir path (%"...
0x14002ceba  mov     r8d, 5EDh
0x14002cec0  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002cec7  mov     ecx, 1
0x14002cecc  call    AslLogCallPrintf
0x14002ced1  nop
0x14002ced2  mov     rbx, [rbp+lpMem]
0x14002ced6  test    rbx, rbx
0x14002ced9  jz      short loc_14002CEEF
0x14002cedb  call    cs:__imp_GetProcessHeap
0x14002cee1  mov     rcx, rax; hHeap
0x14002cee4  mov     r8, rbx; lpMem
0x14002cee7  xor     edx, edx; dwFlags
0x14002cee9  call    cs:__imp_HeapFree
0x14002ceef  mov     eax, edi
0x14002cef1  jmp     loc_14002D0FB
0x14002cef6  mov     rbx, [rbp+lpMem]
0x14002cefa  mov     rcx, rbx; unsigned __int16 *
0x14002cefd  call    ?EnsureDirectory@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEBG@Z; Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory(ushort const *)
0x14002cf02  mov     edi, eax
0x14002cf04  test    eax, eax
0x14002cf06  jz      short loc_14002CF2D
0x14002cf08  mov     [rsp+30h+var_10], eax
0x14002cf0c  lea     r9, aFailedToEnsure; "Failed to ensure the merge sdb director"...
0x14002cf13  mov     r8d, 5F2h
0x14002cf19  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002cf20  mov     ecx, 1
0x14002cf25  call    AslLogCallPrintf
0x14002cf2a  nop
0x14002cf2b  jmp     short loc_14002CED6
0x14002cf2d  mov     [rbp+lpNewFileName], 0
0x14002cf35  mov     [rbp+arg_10], rbx
0x14002cf39  lea     r9, [rsi+68h]
0x14002cf3d  lea     rdx, [rbp+arg_10]
0x14002cf41  lea     rcx, [rbp+lpNewFileName]
0x14002cf45  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@AEAY01$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ushort const (&)[2],ushort const * const &)
0x14002cf4a  mov     r14d, eax
0x14002cf4d  test    eax, eax
0x14002cf4f  jns     short loc_14002CFC4
0x14002cf51  and     eax, 1FFF0000h
0x14002cf56  cmp     eax, 70000h
0x14002cf5b  jnz     short loc_14002CF61
0x14002cf5d  movzx   r14d, r14w
0x14002cf61  mov     [rsp+30h+var_10], r14d
0x14002cf66  lea     r9, aFailedToCreate_3; "Failed to create merge sdb full path (%"...
0x14002cf6d  mov     r8d, 5FBh
0x14002cf73  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002cf7a  mov     ecx, 1
0x14002cf7f  call    AslLogCallPrintf
0x14002cf84  nop
0x14002cf85  mov     rdi, [rbp+lpNewFileName]
0x14002cf89  test    rdi, rdi
0x14002cf8c  jz      short loc_14002CFA3
0x14002cf8e  call    cs:__imp_GetProcessHeap
0x14002cf94  mov     rcx, rax; hHeap
0x14002cf97  mov     r8, rdi; lpMem
0x14002cf9a  xor     edx, edx; dwFlags
0x14002cf9c  call    cs:__imp_HeapFree
0x14002cfa2  nop
0x14002cfa3  test    rbx, rbx
0x14002cfa6  jz      short loc_14002CFBC
0x14002cfa8  call    cs:__imp_GetProcessHeap
0x14002cfae  mov     rcx, rax; hHeap
0x14002cfb1  mov     r8, rbx; lpMem
0x14002cfb4  xor     edx, edx; dwFlags
0x14002cfb6  call    cs:__imp_HeapFree
0x14002cfbc  mov     eax, r14d
0x14002cfbf  jmp     loc_14002D0FB
0x14002cfc4  mov     rdi, [rbp+lpNewFileName]
0x14002cfc8  mov     rdx, rdi; LPCWSTR
0x14002cfcb  mov     rcx, [rsi]; lpFileName
0x14002cfce  call    ?MergeSdbpUtilIsTheSameFile@Utils@MergeSdb@Pca@@YA_NPEBG0@Z; Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile(ushort const *,ushort const *)
0x14002cfd3  test    al, al
0x14002cfd5  jz      short loc_14002D011
0x14002cfd7  test    rdi, rdi
0x14002cfda  jz      short loc_14002CFF1
0x14002cfdc  call    cs:__imp_GetProcessHeap
0x14002cfe2  mov     rcx, rax; hHeap
0x14002cfe5  mov     r8, rdi; lpMem
0x14002cfe8  xor     edx, edx; dwFlags
0x14002cfea  call    cs:__imp_HeapFree
0x14002cff0  nop
0x14002cff1  test    rbx, rbx
0x14002cff4  jz      short loc_14002D00A
0x14002cff6  call    cs:__imp_GetProcessHeap
0x14002cffc  mov     rcx, rax; hHeap
0x14002cfff  mov     r8, rbx; lpMem
0x14002d002  xor     edx, edx; dwFlags
0x14002d004  call    cs:__imp_HeapFree
0x14002d00a  xor     eax, eax
0x14002d00c  jmp     loc_14002D0FB
0x14002d011  xor     r8d, r8d; bFailIfExists
0x14002d014  mov     rdx, rdi; lpNewFileName
0x14002d017  mov     rcx, [rsi]; lpExistingFileName
0x14002d01a  call    cs:__imp_CopyFileW
0x14002d020  test    eax, eax
0x14002d022  jnz     short loc_14002D08B
0x14002d024  call    cs:__imp_GetLastError
0x14002d02a  mov     esi, eax
0x14002d02c  mov     ecx, 1
0x14002d031  test    eax, eax
0x14002d033  cmovz   esi, ecx
0x14002d036  mov     [rsp+30h+var_10], esi
0x14002d03a  lea     r9, aFailedToCopyMe; "Failed to copy merge sdb to merge sdb d"...
0x14002d041  mov     r8d, 606h
0x14002d047  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002d04e  call    AslLogCallPrintf
0x14002d053  nop
0x14002d054  test    rdi, rdi
0x14002d057  jz      short loc_14002D06E
0x14002d059  call    cs:__imp_GetProcessHeap
0x14002d05f  mov     rcx, rax; hHeap
0x14002d062  mov     r8, rdi; lpMem
0x14002d065  xor     edx, edx; dwFlags
0x14002d067  call    cs:__imp_HeapFree
0x14002d06d  nop
0x14002d06e  test    rbx, rbx
0x14002d071  jz      short loc_14002D087
0x14002d073  call    cs:__imp_GetProcessHeap
0x14002d079  mov     rcx, rax; hHeap
0x14002d07c  mov     r8, rbx; lpMem
0x14002d07f  xor     edx, edx; dwFlags
0x14002d081  call    cs:__imp_HeapFree
0x14002d087  mov     eax, esi
0x14002d089  jmp     short loc_14002D0FB
0x14002d08b  mov     rcx, rdi; pObjectName
0x14002d08e  call    ?CopyAclsFromParentDir@Utils@MergeSdb@Pca@@YAKPEAG@Z; Pca::MergeSdb::Utils::CopyAclsFromParentDir(ushort *)
0x14002d093  mov     r14d, eax
0x14002d096  test    eax, eax
0x14002d098  jz      short loc_14002D0C2
0x14002d09a  mov     [rsp+30h+var_10], eax
0x14002d09e  lea     r9, aUnableToCopyAc; "Unable to copy ACLs from parent (%d)"
0x14002d0a5  mov     r8d, 60Bh
0x14002d0ab  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002d0b2  mov     ecx, 1
0x14002d0b7  call    AslLogCallPrintf
0x14002d0bc  nop
0x14002d0bd  jmp     loc_14002CF89
0x14002d0c2  lea     rdx, [rbp+lpNewFileName]
0x14002d0c6  mov     rcx, rsi
0x14002d0c9  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d0ce  nop
0x14002d0cf  mov     rdi, [rbp+lpNewFileName]
0x14002d0d3  jmp     loc_14002CFD7
0x14002d0d8  lea     r9, aFailedToMoveMe_0; "Failed to move merge sdb as registratio"...
0x14002d0df  mov     r8d, 5E6h
0x14002d0e5  lea     rdx, aPcaMergesdbUti_6; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002d0ec  mov     ecx, 1
0x14002d0f1  call    AslLogCallPrintf
0x14002d0f6  mov     eax, 139Fh
0x14002d0fb  add     rsp, 30h
0x14002d0ff  pop     r14
0x14002d101  pop     rdi
0x14002d102  pop     rsi
0x14002d103  pop     rbx
0x14002d104  pop     rbp
0x14002d105  retn
```
