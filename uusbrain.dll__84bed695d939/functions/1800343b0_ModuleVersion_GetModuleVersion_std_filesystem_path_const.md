# ModuleVersion::GetModuleVersion(std::filesystem::path const &)

- ea: `0x1800343b0`
- end: `0x1800344fc`
- name: `?GetModuleVersion@ModuleVersion@@SA_KAEBVpath@filesystem@std@@@Z`
- size: `332`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lptstrFilename)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800368cc`
- `0x18003ecb0`

## callees

- `0x18000f724`
- `0x18000f7a0`
- `0x1800343b0`
- `0x18003ddc4`
- `0x18003de7c`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180034427`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180034427`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800343e8`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800343e8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180034457`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180034457`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall ModuleVersion::GetModuleVersion(const WCHAR *lptstrFilename)
{
  const WCHAR *v1; // rbx
  DWORD FileVersionInfoSizeW; // edi
  unsigned int v3; // r8d
  const char *v4; // r9
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned __int64 v7; // rbx
  LPVOID lpData[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  LPVOID lpBuffer; // [rsp+38h] [rbp-18h] BYREF
  unsigned int puLen; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwHandle; // [rsp+44h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v1 = lptstrFilename;
  dwHandle = 0;
  if ( *((_QWORD *)lptstrFilename + 3) > 7u )
    lptstrFilename = *(const WCHAR **)lptstrFilename;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
  if ( !FileVersionInfoSizeW )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x4F,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\ModuleVersion.hpp",
      "File version info size is 0",
      (const char *)lpData[0]);
  *(_OWORD *)lpData = 0;
  v10 = 0;
  std::vector<char>::vector<char>(lpData, FileVersionInfoSizeW);
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(const WCHAR **)v1;
  if ( !GetFileVersionInfoW(v1, 0, FileVersionInfoSizeW, lpData[0]) )
    wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x55, v3, v4);
  lpBuffer = 0;
  puLen = 0;
  if ( !VerQueryValueW(lpData[0], L"\\", &lpBuffer, &puLen) )
    wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x5C, v5, v6);
  if ( !puLen )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x60,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\ModuleVersion.hpp",
      "Fixed file info for version is 0",
      (const char *)lpData[0]);
  v7 = *((unsigned int *)lpBuffer + 3) | ((unsigned __int64)*((unsigned int *)lpBuffer + 2) << 32);
  std::vector<char>::~vector<char>(lpData);
  return v7;
}

```

## disassembly

```asm
0x1800343b0  mov     [rsp-8+arg_8], rbx
0x1800343b5  mov     [rsp-8+arg_10], rdi
0x1800343ba  push    rbp
0x1800343bb  mov     rbp, rsp
0x1800343be  sub     rsp, 50h
0x1800343c2  mov     rax, cs:__security_cookie
0x1800343c9  xor     rax, rsp
0x1800343cc  mov     [rbp+var_8], rax
0x1800343d0  mov     rbx, rcx
0x1800343d3  mov     [rbp+dwHandle], 0
0x1800343da  cmp     qword ptr [rcx+18h], 7
0x1800343df  jbe     short loc_1800343E4
0x1800343e1  mov     rcx, [rcx]; lptstrFilename
0x1800343e4  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x1800343e8  call    cs:__imp_GetFileVersionInfoSizeW
0x1800343ee  mov     edi, eax
0x1800343f0  test    eax, eax
0x1800343f2  jz      loc_1800344C1
0x1800343f8  xorps   xmm0, xmm0
0x1800343fb  xor     eax, eax
0x1800343fd  movups  xmmword ptr [rbp+lpData], xmm0
0x180034401  mov     [rbp+var_20], rax
0x180034405  mov     edx, edi
0x180034407  lea     rcx, [rbp+lpData]
0x18003440b  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180034410  nop
0x180034411  cmp     qword ptr [rbx+18h], 7
0x180034416  jbe     short loc_18003441B
0x180034418  mov     rbx, [rbx]
0x18003441b  mov     r9, [rbp+lpData]; lpData
0x18003441f  mov     r8d, edi; dwLen
0x180034422  xor     edx, edx; dwHandle
0x180034424  mov     rcx, rbx; lptstrFilename
0x180034427  call    cs:__imp_GetFileVersionInfoW
0x18003442d  test    eax, eax
0x18003442f  jz      loc_1800344DE
0x180034435  mov     [rbp+lpBuffer], 0
0x18003443d  mov     [rbp+puLen], 0
0x180034444  lea     r9, [rbp+puLen]; puLen
0x180034448  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18003444c  lea     rdx, SubBlock; "\\"
0x180034453  mov     rcx, [rbp+lpData]; pBlock
0x180034457  call    cs:__imp_VerQueryValueW
0x18003445d  test    eax, eax
0x18003445f  jz      loc_1800344ED
0x180034465  cmp     [rbp+puLen], 0
0x180034469  jz      short loc_1800344A4
0x18003446b  mov     rcx, [rbp+lpBuffer]
0x18003446f  mov     ebx, [rcx+8]
0x180034472  shl     rbx, 20h
0x180034476  mov     ecx, [rcx+0Ch]
0x180034479  or      rbx, rcx
0x18003447c  lea     rcx, [rbp+lpData]
0x180034480  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180034485  mov     rax, rbx
0x180034488  mov     rcx, [rbp+var_8]
0x18003448c  xor     rcx, rsp; StackCookie
0x18003448f  call    __security_check_cookie
0x180034494  mov     rbx, [rsp+50h+arg_8]
0x180034499  mov     rdi, [rsp+50h+arg_10]
0x18003449e  add     rsp, 50h
0x1800344a2  pop     rbp
0x1800344a3  retn
0x1800344a4  mov     rcx, [rbp+8]; this
0x1800344a8  lea     r9, aFixedFileInfoF; "Fixed file info for version is 0"
0x1800344af  lea     r8, aCW1SSrcIncModu; "C:\\__w\\1\\s\\src\\inc\\ModuleVersion."...
0x1800344b6  mov     edx, 60h ; '`'; void *
0x1800344bb  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800344c1  mov     rcx, [rbp+8]; this
0x1800344c5  lea     r9, aFileVersionInf; "File version info size is 0"
0x1800344cc  lea     r8, aCW1SSrcIncModu; "C:\\__w\\1\\s\\src\\inc\\ModuleVersion."...
0x1800344d3  mov     edx, 4Fh ; 'O'; void *
0x1800344d8  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800344de  mov     rcx, [rbp+8]; this
0x1800344e2  mov     edx, 55h ; 'U'; void *
0x1800344e7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800344ed  mov     rcx, [rbp+8]; this
0x1800344f1  mov     edx, 5Ch ; '\'; void *
0x1800344f6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
