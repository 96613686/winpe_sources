# EnsureDatabaseFilesAccessibleForEdp(wchar_t const *)

- ea: `0x180142978`
- end: `0x180142ba4`
- name: `?EnsureDatabaseFilesAccessibleForEdp@@YAJPEB_W@Z`
- size: `556`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801303ac`

## callees

- `0x18003b678`
- `0x180064924`
- `0x18008f4a4`
- `0x18012bee4`
- `0x180142794`
- `0x180142978`
- `0x180142c70`
- `0x180142e10`
- `0x180147154`
- `0x1801590dc`
- `0x180188d90`
- `0x180189280`
- `0x1801895b0`
- `0x180189cce`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142b2c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180142a59`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180142a59`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180142ada`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180142ada`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801429fe`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801429fe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180142b16`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180142b16`

## string_xrefs

- `0x180142a6b`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`
- `0x180142a22`: `onecoreuap\base\appmodel\search\common\edphelper\edphelper.cpp`
- `0x180142aec`: `onecoreuap\base\appmodel\search\common\edphelper\edphelper.cpp`
- `0x180142b37`: `onecoreuap\base\appmodel\search\common\edphelper\edphelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnsureDatabaseFilesAccessibleForEdp(LPCWSTR lpFileName)
{
  char *FirstFileW; // rbx
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  __int64 result; // rax
  void *Block; // [rsp+20h] [rbp-408h] BYREF
  char *v9; // [rsp+28h] [rbp-400h] BYREF
  _QWORD pSecurityDescriptor[10]; // [rsp+30h] [rbp-3F8h] BYREF
  _BYTE v11[8]; // [rsp+80h] [rbp-3A8h] BYREF
  LPCWSTR lpFileNamea; // [rsp+88h] [rbp-3A0h]
  _BYTE v13[160]; // [rsp+120h] [rbp-308h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+1C0h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  try
  {
    TLMString<64,64,32767>::TLMString<64,64,32767>(v11, lpFileName);
    AppendBackSlashIf((struct CLMString *)v11);
    CLMString::Append((CLMString *)v11, L"*.*", 0xFFFFFFFF);
    FirstFileW = (char *)FindFirstFileW(lpFileNamea, &FindFileData);
    v9 = FirstFileW;
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\edphelper\\edphelper.cpp",
        v3);
    SecUtil::CSecurityDescriptor::CSecurityDescriptor(pSecurityDescriptor);
    Block = operator new[](8u);
    if ( !InitializeAcl((PACL)Block, 8u, 2u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
        v4);
    AuthorSecurityDescriptorForEdp(
      (struct SecUtil::CSecurityDescriptor *)pSecurityDescriptor,
      (struct SecUtil::CACL *)&Block);
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        TLMString<64,64,32767>::TLMString<64,64,32767>(v13, lpFileName);
        AppendBackSlashIf((struct CLMString *)v13);
        CLMString::Append((CLMString *)v13, FindFileData.cFileName, 0xFFFFFFFF);
        if ( !SetFileSecurityW(lpFileName, 4u, pSecurityDescriptor) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x13B,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\edphelper\\edphelper.cpp",
            v5);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v13);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() != 18 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\edphelper\\edphelper.cpp",
        v6);
    operator delete(Block);
    SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v9);
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      321,
      "onecoreuap\\base\\appmodel\\search\\common\\edphelper\\edphelper.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x180142978  mov     [rsp+arg_8], rbx
0x18014297d  push    rdi
0x18014297e  sub     rsp, 420h
0x180142985  mov     rax, cs:__security_cookie
0x18014298c  xor     rax, rsp
0x18014298f  mov     [rsp+428h+var_18], rax
0x180142997  mov     rdi, rcx
0x18014299a  xor     edx, edx; Val
0x18014299c  mov     r8d, 250h; Size
0x1801429a2  lea     rcx, [rsp+428h+FindFileData]; void *
0x1801429aa  call    memset_0
0x1801429af  mov     [rsp+428h+var_400], 0FFFFFFFFFFFFFFFFh
0x1801429b8  mov     rdx, rdi
0x1801429bb  lea     rcx, [rsp+428h+var_3A8]
0x1801429c3  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x1801429c8  nop
0x1801429c9  lea     rcx, [rsp+428h+var_3A8]; struct CLMString *
0x1801429d1  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x1801429d6  or      r8d, 0FFFFFFFFh; unsigned int
0x1801429da  lea     rdx, asc_1802EFE28; "*.*"
0x1801429e1  lea     rcx, [rsp+428h+var_3A8]; this
0x1801429e9  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801429ee  lea     rdx, [rsp+428h+FindFileData]; lpFindFileData
0x1801429f6  mov     rcx, [rsp+428h+lpFileName]; lpFileName
0x1801429fe  call    cs:__imp_FindFirstFileW
0x180142a04  mov     rbx, rax
0x180142a07  mov     [rsp+428h+var_400], rax
0x180142a0c  dec     rax
0x180142a0f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180142a13  setnbe  al
0x180142a16  mov     rcx, [rsp+428h]; this
0x180142a1e  test    al, al
0x180142a20  jz      short loc_180142A33
0x180142a22  lea     r8, aOnecoreuapBase_184; "onecoreuap\\base\\appmodel\\search\\com"...
0x180142a29  mov     edx, 12Ch; void *
0x180142a2e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142a33  lea     rcx, [rsp+428h+pSecurityDescriptor]; pSecurityDescriptor
0x180142a38  call    ??0CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)
0x180142a3d  nop
0x180142a3e  mov     ecx, 8; unsigned __int64
0x180142a43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180142a48  mov     [rsp+428h+Block], rax
0x180142a4d  mov     edx, 8; nAclLength
0x180142a52  lea     r8d, [rdx-6]; dwAclRevision
0x180142a56  mov     rcx, rax; pAcl
0x180142a59  call    cs:__imp_InitializeAcl
0x180142a5f  test    eax, eax
0x180142a61  jnz     short loc_180142A7D
0x180142a63  mov     rcx, [rsp+428h]; this
0x180142a6b  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180142a72  mov     edx, 16Ah; void *
0x180142a77  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142a7d  lea     rdx, [rsp+428h+Block]; struct SecUtil::CACL *
0x180142a82  lea     rcx, [rsp+428h+pSecurityDescriptor]; this
0x180142a87  call    ?AuthorSecurityDescriptorForEdp@@YAXAEAVCSecurityDescriptor@SecUtil@@AEAVCACL@2@@Z; AuthorSecurityDescriptorForEdp(SecUtil::CSecurityDescriptor &,SecUtil::CACL &)
0x180142a8c  test    byte ptr [rsp+428h+FindFileData.dwFileAttributes], 10h
0x180142a94  jnz     short loc_180142B0B
0x180142a96  mov     rdx, rdi
0x180142a99  lea     rcx, [rsp+428h+var_308]
0x180142aa1  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x180142aa6  nop
0x180142aa7  lea     rcx, [rsp+428h+var_308]; struct CLMString *
0x180142aaf  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180142ab4  or      r8d, 0FFFFFFFFh; unsigned int
0x180142ab8  lea     rdx, [rsp+428h+FindFileData.cFileName]; wchar_t *
0x180142ac0  lea     rcx, [rsp+428h+var_308]; this
0x180142ac8  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180142acd  lea     r8, [rsp+428h+pSecurityDescriptor]; pSecurityDescriptor
0x180142ad2  mov     edx, 4; SecurityInformation
0x180142ad7  mov     rcx, rdi; lpFileName
0x180142ada  call    cs:__imp_SetFileSecurityW
0x180142ae0  mov     rcx, [rsp+428h]; this
0x180142ae8  test    eax, eax
0x180142aea  jnz     short loc_180142AFE
0x180142aec  lea     r8, aOnecoreuapBase_184; "onecoreuap\\base\\appmodel\\search\\com"...
0x180142af3  mov     edx, 13Bh; void *
0x180142af8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142afe  lea     rcx, [rsp+428h+var_308]
0x180142b06  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180142b0b  lea     rdx, [rsp+428h+FindFileData]; lpFindFileData
0x180142b13  mov     rcx, rbx; hFindFile
0x180142b16  call    cs:__imp_FindNextFileW
0x180142b1c  test    eax, eax
0x180142b1e  jnz     loc_180142A8C
0x180142b24  mov     rbx, [rsp+428h]
0x180142b2c  call    cs:__imp_GetLastError
0x180142b32  cmp     eax, 12h
0x180142b35  jz      short loc_180142B4C
0x180142b37  lea     r8, aOnecoreuapBase_184; "onecoreuap\\base\\appmodel\\search\\com"...
0x180142b3e  mov     edx, 13Fh; void *
0x180142b43  mov     rcx, rbx; this
0x180142b46  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142b4c  mov     rcx, [rsp+428h+Block]; Block
0x180142b51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180142b56  nop
0x180142b57  lea     rcx, [rsp+428h+pSecurityDescriptor]; this
0x180142b5c  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x180142b61  nop
0x180142b62  lea     rcx, [rsp+428h+var_3A8]
0x180142b6a  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180142b6f  nop
0x180142b70  lea     rcx, [rsp+428h+var_400]
0x180142b75  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180142b7a  nop
0x180142b7b  xor     eax, eax
0x180142b7d  jmp     short loc_180142B83
0x180142b7f  mov     eax, dword ptr [rsp+428h+Block]
0x180142b83  mov     rcx, [rsp+428h+var_18]
0x180142b8b  xor     rcx, rsp; StackCookie
0x180142b8e  call    __security_check_cookie
0x180142b93  mov     rbx, [rsp+428h+arg_8]
0x180142b9b  add     rsp, 420h
0x180142ba2  pop     rdi
0x180142ba3  retn
```
