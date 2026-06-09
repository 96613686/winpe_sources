# Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder(void)

- ea: `0x14002a1ac`
- end: `0x14002a334`
- name: `?DeleteFromMergeSdbFolder@RegistrationInfo@Utils@MergeSdb@Pca@@AEAAKXZ`
- size: `392`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140028714`

## callees

- `0x14001008c`
- `0x14002a1ac`
- `0x14002a3a8`
- `0x14002acfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002a2b5`
- `KERNEL32!GetLastError` at `0x14002a2b5`
- `KERNEL32!DeleteFileW` at `0x14002a2ab`
- `KERNEL32!DeleteFileW` at `0x14002a2ab`
- `KERNEL32!GetProcessHeap` at `0x14002a217`
- `KERNEL32!GetProcessHeap` at `0x14002a28d`
- `KERNEL32!GetProcessHeap` at `0x14002a2ea`
- `KERNEL32!GetProcessHeap` at `0x14002a217`
- `KERNEL32!GetProcessHeap` at `0x14002a28d`
- `KERNEL32!GetProcessHeap` at `0x14002a2ea`
- `KERNEL32!HeapFree` at `0x14002a225`
- `KERNEL32!HeapFree` at `0x14002a29b`
- `KERNEL32!HeapFree` at `0x14002a2f8`
- `KERNEL32!HeapFree` at `0x14002a225`
- `KERNEL32!HeapFree` at `0x14002a29b`
- `KERNEL32!HeapFree` at `0x14002a2f8`
- `msvcrt!_wcsnicmp` at `0x14002a27e`
- `msvcrt!_wcsnicmp` at `0x14002a27e`

## string_xrefs

- `0x14002a1f0`: `Failed to get the sdb merge dir path (%d)`
- `0x14002a2cb`: `Failed to delete file from the merge sdb directory (%d)`
- `0x14002a308`: `Failed to move merge sdb as registration state is invalid`
- `0x14002a249`: `Failed to ensure the merge sdb directory (%d)`
- `0x14002a1fd`: `Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder`
- `0x14002a256`: `Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder`
- `0x14002a2d8`: `Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder`
- `0x14002a315`: `Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder(
        Pca::MergeSdb::Utils::RegistrationInfo *this)
{
  int MergeSdbDirectoryPath; // eax
  unsigned int v3; // esi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  int v7; // eax
  size_t v8; // r8
  HANDLE v9; // rax
  DWORD LastError; // edi
  HANDLE v11; // rax
  LPVOID lpMem; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 16) || !*(_QWORD *)this || !*((_QWORD *)this + 13) )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder",
      1564,
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
      "Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder",
      1571,
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
      "Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder",
      1576,
      "Failed to ensure the merge sdb directory (%d)",
      v7);
    goto LABEL_6;
  }
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)v4 + v8) );
  if ( _wcsnicmp((const wchar_t *)v4, *(const wchar_t **)this, v8) )
    goto LABEL_14;
  if ( DeleteFileW(*(LPCWSTR *)this) )
  {
    *((_BYTE *)this + 16) = 0;
LABEL_14:
    if ( v4 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v4);
    }
    return 0;
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder",
    1588,
    "Failed to delete file from the merge sdb directory (%d)",
    LastError);
  if ( v4 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x14002a1ac  push    rbx
0x14002a1ae  push    rbp
0x14002a1af  push    rsi
0x14002a1b0  push    rdi
0x14002a1b1  sub     rsp, 38h
0x14002a1b5  mov     rdi, rcx
0x14002a1b8  xor     ebp, ebp
0x14002a1ba  cmp     [rcx+10h], bpl
0x14002a1be  jz      loc_14002A308
0x14002a1c4  cmp     [rcx], rbp
0x14002a1c7  jz      loc_14002A308
0x14002a1cd  cmp     [rcx+68h], rbp
0x14002a1d1  jz      loc_14002A308
0x14002a1d7  mov     [rsp+58h+lpMem], rbp
0x14002a1dc  lea     rcx, [rsp+58h+lpMem]
0x14002a1e1  call    ?GetMergeSdbDirectoryPath@RegistrationInfo@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002a1e6  mov     esi, eax
0x14002a1e8  test    eax, eax
0x14002a1ea  jz      short loc_14002A232
0x14002a1ec  mov     [rsp+58h+var_38], eax
0x14002a1f0  lea     r9, aFailedToGetThe_1; "Failed to get the sdb merge dir path (%"...
0x14002a1f7  mov     r8d, 623h
0x14002a1fd  lea     rdx, aPcaMergesdbUti_25; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a204  lea     ecx, [rbp+1]
0x14002a207  call    AslLogCallPrintf
0x14002a20c  nop
0x14002a20d  mov     rbx, [rsp+58h+lpMem]
0x14002a212  test    rbx, rbx
0x14002a215  jz      short loc_14002A22B
0x14002a217  call    cs:__imp_GetProcessHeap
0x14002a21d  mov     rcx, rax; hHeap
0x14002a220  mov     r8, rbx; lpMem
0x14002a223  xor     edx, edx; dwFlags
0x14002a225  call    cs:__imp_HeapFree
0x14002a22b  mov     eax, esi
0x14002a22d  jmp     loc_14002A32B
0x14002a232  mov     rbx, [rsp+58h+lpMem]
0x14002a237  mov     rcx, rbx; unsigned __int16 *
0x14002a23a  call    ?EnsureDirectory@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEBG@Z; Pca::MergeSdb::Utils::RegistrationInfo::EnsureDirectory(ushort const *)
0x14002a23f  mov     esi, eax
0x14002a241  test    eax, eax
0x14002a243  jz      short loc_14002A26A
0x14002a245  mov     [rsp+58h+var_38], eax
0x14002a249  lea     r9, aFailedToEnsure; "Failed to ensure the merge sdb director"...
0x14002a250  mov     r8d, 628h
0x14002a256  lea     rdx, aPcaMergesdbUti_25; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a25d  mov     ecx, 1
0x14002a262  call    AslLogCallPrintf
0x14002a267  nop
0x14002a268  jmp     short loc_14002A212
0x14002a26a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002a26e  inc     r8; MaxCount
0x14002a271  cmp     [rbx+r8*2], bp
0x14002a276  jnz     short loc_14002A26E
0x14002a278  mov     rdx, [rdi]; String2
0x14002a27b  mov     rcx, rbx; String1
0x14002a27e  call    cs:__imp__wcsnicmp
0x14002a284  test    eax, eax
0x14002a286  jz      short loc_14002A2A8
0x14002a288  test    rbx, rbx
0x14002a28b  jz      short loc_14002A2A1
0x14002a28d  call    cs:__imp_GetProcessHeap
0x14002a293  mov     rcx, rax; hHeap
0x14002a296  mov     r8, rbx; lpMem
0x14002a299  xor     edx, edx; dwFlags
0x14002a29b  call    cs:__imp_HeapFree
0x14002a2a1  xor     eax, eax
0x14002a2a3  jmp     loc_14002A32B
0x14002a2a8  mov     rcx, [rdi]; lpFileName
0x14002a2ab  call    cs:__imp_DeleteFileW
0x14002a2b1  test    eax, eax
0x14002a2b3  jnz     short loc_14002A302
0x14002a2b5  call    cs:__imp_GetLastError
0x14002a2bb  mov     edi, eax
0x14002a2bd  mov     ecx, 1
0x14002a2c2  test    eax, eax
0x14002a2c4  cmovz   edi, ecx
0x14002a2c7  mov     [rsp+58h+var_38], edi
0x14002a2cb  lea     r9, aFailedToDelete_2; "Failed to delete file from the merge sd"...
0x14002a2d2  mov     r8d, 634h
0x14002a2d8  lea     rdx, aPcaMergesdbUti_25; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a2df  call    AslLogCallPrintf
0x14002a2e4  nop
0x14002a2e5  test    rbx, rbx
0x14002a2e8  jz      short loc_14002A2FE
0x14002a2ea  call    cs:__imp_GetProcessHeap
0x14002a2f0  mov     rcx, rax; hHeap
0x14002a2f3  mov     r8, rbx; lpMem
0x14002a2f6  xor     edx, edx; dwFlags
0x14002a2f8  call    cs:__imp_HeapFree
0x14002a2fe  mov     eax, edi
0x14002a300  jmp     short loc_14002A32B
0x14002a302  mov     [rdi+10h], bpl
0x14002a306  jmp     short loc_14002A288
0x14002a308  lea     r9, aFailedToMoveMe_0; "Failed to move merge sdb as registratio"...
0x14002a30f  mov     r8d, 61Ch
0x14002a315  lea     rdx, aPcaMergesdbUti_25; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002a31c  mov     ecx, 1
0x14002a321  call    AslLogCallPrintf
0x14002a326  mov     eax, 139Fh
0x14002a32b  add     rsp, 38h
0x14002a32f  pop     rdi
0x14002a330  pop     rsi
0x14002a331  pop     rbp
0x14002a332  pop     rbx
0x14002a333  retn
```
