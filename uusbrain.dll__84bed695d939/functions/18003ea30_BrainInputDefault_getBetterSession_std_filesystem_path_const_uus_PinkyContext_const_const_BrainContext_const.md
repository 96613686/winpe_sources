# BrainInputDefault::getBetterSession(std::filesystem::path const &,uus::PinkyContext const * const,BrainContext const &)

- ea: `0x18003ea30`
- end: `0x18003eb71`
- name: `?getBetterSession@BrainInputDefault@@UEBAPEAXAEBVpath@filesystem@std@@QEBUPinkyContext@uus@@AEBUBrainContext@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(BrainInputDefault *this, const struct std::filesystem::path *, const struct uus::PinkyContext *, const struct BrainContext *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x180026a00`
- `0x180026cd8`
- `0x180029344`
- `0x180029644`
- `0x18003ce48`
- `0x18003d338`
- `0x18003ea30`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003eaf9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003eaf9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eaba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eaba`

## string_xrefs

- `0x18003eb3e`: `Undocked Update Stack brain was not found in package.`
- `0x18003ea58`: `uusbrain.dll`

## pseudocode

```c
__int64 __fastcall BrainInputDefault::getBetterSession(
        BrainInputDefault *this,
        const struct std::filesystem::path *a2,
        const struct uus::PinkyContext *a3,
        const struct BrainContext *a4)
{
  unsigned __int8 v6; // r8
  const CHAR *v7; // rdx
  FARPROC ProcAddress; // rax
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rbx
  int pExceptionObject[6]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp-40h] BYREF
  char v16[32]; // [rsp+48h] [rbp-38h] BYREF
  char v17; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  uus::Utility::FindFileInPackage(v16, a2, L"uusbrain.dll", 3);
  if ( !v17 )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "Undocked Update Stack brain was not found in package.");
    throw (std::runtime_error *)pExceptionObject;
  }
  hModule = 0;
  if ( a3 )
    v6 = (*((_DWORD *)a3 + 3) & 4) != 0;
  else
    v6 = 0;
  uus::Utility::LoadDll(&hModule, v16, v6);
  v7 = (const CHAR *)&BrainInputDefault::nameGetSessionForBrain;
  if ( (unsigned __int64)qword_1800639C8 > 0xF )
    v7 = BrainInputDefault::nameGetSessionForBrain;
  ProcAddress = GetProcAddress(hModule, v7);
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainInputDefault.cpp",
      v9);
  v14 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *, const struct uus::PinkyContext *, const struct BrainContext *))ProcAddress)(
          &v14,
          a3,
          a4);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainInputDefault.cpp",
      (const char *)(unsigned int)v10,
      pExceptionObject[0]);
  v11 = v14;
  if ( hModule )
    FreeLibrary(hModule);
  if ( v17 )
    std::wstring::_Tidy_deallocate(v16);
  return v11;
}

```

## disassembly

```asm
0x18003ea30  push    rbp
0x18003ea32  push    rbx
0x18003ea33  push    rdi
0x18003ea34  mov     rbp, rsp
0x18003ea37  sub     rsp, 80h
0x18003ea3e  mov     rax, cs:__security_cookie
0x18003ea45  xor     rax, rsp
0x18003ea48  mov     [rbp+var_10], rax
0x18003ea4c  mov     rdi, r9
0x18003ea4f  mov     rbx, r8
0x18003ea52  mov     r9d, 3
0x18003ea58  lea     r8, aUusbrainDll_0; "uusbrain.dll"
0x18003ea5f  lea     rcx, [rbp+var_38]
0x18003ea63  call    ?FindFileInPackage@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_WI@Z; uus::Utility::FindFileInPackage(std::filesystem::path const &,wchar_t const *,uint)
0x18003ea68  nop
0x18003ea69  cmp     [rbp+var_18], 0
0x18003ea6d  jz      loc_18003EB3E
0x18003ea73  mov     [rbp+hModule], 0
0x18003ea7b  test    rbx, rbx
0x18003ea7e  jz      short loc_18003EA8E
0x18003ea80  mov     r8d, [rbx+0Ch]
0x18003ea84  shr     r8d, 2
0x18003ea88  and     r8b, 1
0x18003ea8c  jmp     short loc_18003EA91
0x18003ea8e  xor     r8b, r8b
0x18003ea91  lea     rdx, [rbp+var_38]
0x18003ea95  lea     rcx, [rbp+hModule]
0x18003ea99  call    ?LoadDll@Utility@uus@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@_N@Z; uus::Utility::LoadDll(std::filesystem::path const &,bool)
0x18003ea9e  nop
0x18003ea9f  lea     rdx, ?nameGetSessionForBrain@BrainInputDefault@@0V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const BrainInputDefault::nameGetSessionForBrain
0x18003eaa6  cmp     cs:qword_1800639C8, 0Fh
0x18003eaae  cmova   rdx, cs:?nameGetSessionForBrain@BrainInputDefault@@0V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; lpProcName
0x18003eab6  mov     rcx, [rbp+hModule]; hModule
0x18003eaba  call    cs:__imp_GetProcAddress
0x18003eac0  mov     rcx, [rbp+18h]; this
0x18003eac4  test    rax, rax
0x18003eac7  jz      loc_18003EB5F
0x18003eacd  mov     [rbp+var_48], 0
0x18003ead5  mov     r8, rdi
0x18003ead8  mov     rdx, rbx
0x18003eadb  lea     rcx, [rbp+var_48]
0x18003eadf  call    _guard_dispatch_icall
0x18003eae4  mov     rcx, [rbp+18h]; this
0x18003eae8  test    eax, eax
0x18003eaea  js      short loc_18003EB29
0x18003eaec  mov     rbx, [rbp+var_48]
0x18003eaf0  mov     rcx, [rbp+hModule]; hLibModule
0x18003eaf4  test    rcx, rcx
0x18003eaf7  jz      short loc_18003EB00
0x18003eaf9  call    cs:__imp_FreeLibrary
0x18003eaff  nop
0x18003eb00  cmp     [rbp+var_18], 0
0x18003eb04  jz      short loc_18003EB0F
0x18003eb06  lea     rcx, [rbp+var_38]
0x18003eb0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eb0f  mov     rax, rbx
0x18003eb12  mov     rcx, [rbp+var_10]
0x18003eb16  xor     rcx, rsp; StackCookie
0x18003eb19  call    __security_check_cookie
0x18003eb1e  add     rsp, 80h
0x18003eb25  pop     rdi
0x18003eb26  pop     rbx
0x18003eb27  pop     rbp
0x18003eb28  retn
0x18003eb29  mov     r9d, eax; char *
0x18003eb2c  lea     r8, aCW1SSrcBrainLi_0; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainIn"...
0x18003eb33  mov     edx, 15h; void *
0x18003eb38  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003eb3e  lea     rdx, aUndockedUpdate; "Undocked Update Stack brain was not fou"...
0x18003eb45  lea     rcx, [rbp+pExceptionObject]; this
0x18003eb49  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003eb4e  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003eb55  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003eb59  call    _CxxThrowException
0x18003eb5f  lea     r8, aCW1SSrcBrainLi_0; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainIn"...
0x18003eb66  mov     edx, 11h; void *
0x18003eb6b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
