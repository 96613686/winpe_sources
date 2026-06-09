# Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)

- ea: `0x180101104`
- end: `0x180101247`
- name: `?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ`
- size: `323`
- prototype: `void __fastcall(Microsoft::Diagnostics::OptionalApiHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802e7d84`

## callees

- `0x18001cf30`
- `0x18003fd8c`
- `0x180101104`
- `0x180101300`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010116c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010121a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010116c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801011fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010121a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101142`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101142`

## string_xrefs

- `0x18010112e`: `cryptxml.dll`
- `0x18010117b`: `CryptXmlOpenToDecode`
- `0x180101165`: `CryptXmlClose`
- `0x1801011b5`: `CryptXmlVerifySignature`
- `0x180101198`: `CryptXmlGetDocContext`
- `0x1801011ef`: `CryptXmlGetReference`
- `0x1801011d2`: `CryptXmlGetSignature`
- `0x18010120c`: `CryptXmlGetStatus`

## pseudocode

```c
void __fastcall Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(HMODULE *this)
{
  HMODULE *v2; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  FARPROC v8; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  _BYTE v16[24]; // [rsp+20h] [rbp-18h] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v16, this + 31);
  if ( !*((_BYTE *)this + 3) )
  {
    v2 = this + 54;
    Library = LoadLibraryExW(L"cryptxml.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      this + 54,
      Library);
    if ( this[54] )
    {
      ProcAddress = GetProcAddress(this[54], "CryptXmlClose");
      v5 = *v2;
      this[58] = (HMODULE)ProcAddress;
      v6 = GetProcAddress(v5, "CryptXmlOpenToDecode");
      v7 = *v2;
      this[59] = (HMODULE)v6;
      v8 = GetProcAddress(v7, "CryptXmlGetDocContext");
      v9 = *v2;
      this[60] = (HMODULE)v8;
      v10 = GetProcAddress(v9, "CryptXmlVerifySignature");
      v11 = *v2;
      this[61] = (HMODULE)v10;
      v12 = GetProcAddress(v11, "CryptXmlGetSignature");
      v13 = *v2;
      this[62] = (HMODULE)v12;
      v14 = GetProcAddress(v13, "CryptXmlGetReference");
      v15 = *v2;
      this[63] = (HMODULE)v14;
      this[64] = (HMODULE)GetProcAddress(v15, "CryptXmlGetStatus");
    }
    *((_BYTE *)this + 3) = 1;
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v16);
}

```

## disassembly

```asm
0x180101104  mov     [rsp+arg_0], rbx
0x180101109  push    rdi
0x18010110a  sub     rsp, 30h
0x18010110e  mov     rbx, rcx
0x180101111  lea     rdx, [rcx+0F8h]
0x180101118  lea     rcx, [rsp+38h+var_18]
0x18010111d  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180101122  cmp     byte ptr [rbx+3], 0
0x180101126  jnz     loc_180101231
0x18010112c  xor     edx, edx; hFile
0x18010112e  lea     rcx, aCryptxmlDll; "cryptxml.dll"
0x180101135  mov     r8d, 800h; dwFlags
0x18010113b  lea     rdi, [rbx+1B0h]
0x180101142  call    cs:__imp_LoadLibraryExW
0x180101149  nop     dword ptr [rax+rax+00h]
0x18010114e  mov     rdx, rax
0x180101151  mov     rcx, rdi
0x180101154  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180101159  mov     rcx, [rdi]; hModule
0x18010115c  test    rcx, rcx
0x18010115f  jz      loc_18010122D
0x180101165  lea     rdx, aCryptxmlclose; "CryptXmlClose"
0x18010116c  call    cs:__imp_GetProcAddress
0x180101173  nop     dword ptr [rax+rax+00h]
0x180101178  mov     rcx, [rdi]; hModule
0x18010117b  lea     rdx, aCryptxmlopento; "CryptXmlOpenToDecode"
0x180101182  mov     [rbx+1D0h], rax
0x180101189  call    cs:__imp_GetProcAddress
0x180101190  nop     dword ptr [rax+rax+00h]
0x180101195  mov     rcx, [rdi]; hModule
0x180101198  lea     rdx, aCryptxmlgetdoc; "CryptXmlGetDocContext"
0x18010119f  mov     [rbx+1D8h], rax
0x1801011a6  call    cs:__imp_GetProcAddress
0x1801011ad  nop     dword ptr [rax+rax+00h]
0x1801011b2  mov     rcx, [rdi]; hModule
0x1801011b5  lea     rdx, aCryptxmlverify; "CryptXmlVerifySignature"
0x1801011bc  mov     [rbx+1E0h], rax
0x1801011c3  call    cs:__imp_GetProcAddress
0x1801011ca  nop     dword ptr [rax+rax+00h]
0x1801011cf  mov     rcx, [rdi]; hModule
0x1801011d2  lea     rdx, aCryptxmlgetsig; "CryptXmlGetSignature"
0x1801011d9  mov     [rbx+1E8h], rax
0x1801011e0  call    cs:__imp_GetProcAddress
0x1801011e7  nop     dword ptr [rax+rax+00h]
0x1801011ec  mov     rcx, [rdi]; hModule
0x1801011ef  lea     rdx, aCryptxmlgetref; "CryptXmlGetReference"
0x1801011f6  mov     [rbx+1F0h], rax
0x1801011fd  call    cs:__imp_GetProcAddress
0x180101204  nop     dword ptr [rax+rax+00h]
0x180101209  mov     rcx, [rdi]; hModule
0x18010120c  lea     rdx, aCryptxmlgetsta; "CryptXmlGetStatus"
0x180101213  mov     [rbx+1F8h], rax
0x18010121a  call    cs:__imp_GetProcAddress
0x180101221  nop     dword ptr [rax+rax+00h]
0x180101226  mov     [rbx+200h], rax
0x18010122d  mov     byte ptr [rbx+3], 1
0x180101231  lea     rcx, [rsp+38h+var_18]
0x180101236  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18010123b  mov     rbx, [rsp+38h+arg_0]
0x180101240  add     rsp, 30h
0x180101244  pop     rdi
0x180101245  retn
```
