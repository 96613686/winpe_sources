# XE_StaticPackage<60>::Init(XEPackage const *,ushort)

- ea: `0x10041c720`
- end: `0x10041c870`
- name: `?Init@?$XE_StaticPackage@$0DM@@@UEAAHPEBUXEPackage@@G@Z`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x10041c720`
- `0x100463170`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x10041c777`
- `KERNEL32!LoadLibraryExW` at `0x10041c805`
- `KERNEL32!LoadLibraryExW` at `0x10041c777`
- `KERNEL32!LoadLibraryExW` at `0x10041c805`
- `KERNEL32!FreeLibrary` at `0x10041c7e2`
- `KERNEL32!FreeLibrary` at `0x10041c7e2`
- `KERNEL32!GetProcAddress` at `0x10041c79d`
- `KERNEL32!GetProcAddress` at `0x10041c7b0`
- `KERNEL32!GetProcAddress` at `0x10041c821`
- `KERNEL32!GetProcAddress` at `0x10041c79d`
- `KERNEL32!GetProcAddress` at `0x10041c7b0`
- `KERNEL32!GetProcAddress` at `0x10041c821`
- `KERNEL32!GetModuleFileNameW` at `0x10041c762`
- `KERNEL32!GetModuleFileNameW` at `0x10041c762`

## string_xrefs

- `0x10041c7f8`: `user32.dll`
- `0x10041c76a`: `shlwapi.dll`
- `0x10041c7a3`: `PathAppendW`
- `0x10041c78e`: `PathRemoveFileSpecW`

## pseudocode

```c
__int64 __fastcall XE_StaticPackage<60>::Init(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  int v5; // edi
  HMODULE Library; // rax
  HMODULE v7; // rsi
  FARPROC ProcAddress; // r15
  FARPROC v9; // rax
  __int64 (__fastcall *v10)(__int64, const wchar_t *); // rbp
  HMODULE v11; // rax
  FARPROC v12; // rax

  v5 = 0;
  memset_0((void *)(a1 + 24), 0, 0x208u);
  GetModuleFileNameW(*(HMODULE *)(**(_QWORD **)(a1 + 8) + 72LL), (LPWSTR)(a1 + 24), 0x104u);
  Library = LoadLibraryExW(L"shlwapi.dll", 0, 0x800u);
  v7 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "PathRemoveFileSpecW");
  v9 = GetProcAddress(v7, "PathAppendW");
  v10 = (__int64 (__fastcall *)(__int64, const wchar_t *))v9;
  if ( ProcAddress )
  {
    if ( v9 )
    {
      v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a1 + 24);
      if ( v5 )
        v5 = v10(a1 + 24, L"\\Resources");
    }
  }
  FreeLibrary(v7);
  if ( !v5 )
    return 0;
  v11 = LoadLibraryExW(L"user32.dll", 0, 0x800u);
  *(_QWORD *)(a1 + 576) = v11;
  if ( !v11 )
    return 0;
  v12 = GetProcAddress(v11, "LoadStringW");
  *(_QWORD *)(a1 + 568) = v12;
  if ( !v12 || !(unsigned int)qword_100517120(a1 + 560) )
    return 0;
  XE_PackageManagerUtilities::SetPackageId(a3, 0, *(struct XEPackageMetadata **)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x10041c720  mov     [rsp+arg_10], rbx
0x10041c725  mov     [rsp+arg_18], rsi
0x10041c72a  push    rdi
0x10041c72b  push    r12
0x10041c72d  push    r14
0x10041c72f  sub     rsp, 20h
0x10041c733  movzx   r12d, r8w
0x10041c737  mov     rbx, rcx
0x10041c73a  mov     r8d, 208h; Size
0x10041c740  add     rcx, 18h; void *
0x10041c744  xor     edx, edx; Val
0x10041c746  xor     edi, edi
0x10041c748  call    memset_0
0x10041c74d  mov     rax, [rbx+8]
0x10041c751  lea     rdx, [rbx+18h]; lpFilename
0x10041c755  mov     r8d, 104h; nSize
0x10041c75b  mov     rcx, [rax]
0x10041c75e  mov     rcx, [rcx+48h]; hModule
0x10041c762  call    cs:__imp_GetModuleFileNameW
0x10041c768  xor     edx, edx; hFile
0x10041c76a  lea     rcx, LibFileName; "shlwapi.dll"
0x10041c771  mov     r8d, 800h; dwFlags
0x10041c777  call    cs:__imp_LoadLibraryExW
0x10041c77d  mov     rsi, rax
0x10041c780  test    rax, rax
0x10041c783  jz      loc_10041C85A
0x10041c789  mov     [rsp+38h+arg_0], rbp
0x10041c78e  lea     rdx, aPathremovefile; "PathRemoveFileSpecW"
0x10041c795  mov     rcx, rax; hModule
0x10041c798  mov     [rsp+38h+arg_8], r15
0x10041c79d  call    cs:__imp_GetProcAddress
0x10041c7a3  lea     rdx, aPathappendw; "PathAppendW"
0x10041c7aa  mov     rcx, rsi; hModule
0x10041c7ad  mov     r15, rax
0x10041c7b0  call    cs:__imp_GetProcAddress
0x10041c7b6  mov     rbp, rax
0x10041c7b9  test    r15, r15
0x10041c7bc  jz      short loc_10041C7DF
0x10041c7be  test    rax, rax
0x10041c7c1  jz      short loc_10041C7DF
0x10041c7c3  lea     rcx, [rbx+18h]
0x10041c7c7  call    r15
0x10041c7ca  mov     edi, eax
0x10041c7cc  test    eax, eax
0x10041c7ce  jz      short loc_10041C7DF
0x10041c7d0  lea     rdx, aResources; "\\Resources"
0x10041c7d7  lea     rcx, [rbx+18h]
0x10041c7db  call    rbp
0x10041c7dd  mov     edi, eax
0x10041c7df  mov     rcx, rsi; hLibModule
0x10041c7e2  call    cs:__imp_FreeLibrary
0x10041c7e8  mov     r15, [rsp+38h+arg_8]
0x10041c7ed  mov     rbp, [rsp+38h+arg_0]
0x10041c7f2  test    edi, edi
0x10041c7f4  jz      short loc_10041C85A
0x10041c7f6  xor     edx, edx; hFile
0x10041c7f8  lea     rcx, aUser32Dll_0; "user32.dll"
0x10041c7ff  mov     r8d, 800h; dwFlags
0x10041c805  call    cs:__imp_LoadLibraryExW
0x10041c80b  mov     [rbx+240h], rax
0x10041c812  test    rax, rax
0x10041c815  jz      short loc_10041C85A
0x10041c817  lea     rdx, aLoadstringw; "LoadStringW"
0x10041c81e  mov     rcx, rax; hModule
0x10041c821  call    cs:__imp_GetProcAddress
0x10041c827  mov     [rbx+238h], rax
0x10041c82e  test    rax, rax
0x10041c831  jz      short loc_10041C85A
0x10041c833  lea     rcx, [rbx+230h]
0x10041c83a  call    cs:qword_100517120
0x10041c840  test    eax, eax
0x10041c842  jz      short loc_10041C85A
0x10041c844  mov     r8, [rbx+8]; struct XEPackageMetadata *
0x10041c848  xor     edx, edx; int
0x10041c84a  movzx   ecx, r12w; unsigned __int16
0x10041c84e  call    ?SetPackageId@XE_PackageManagerUtilities@@SAXGHPEAUXEPackageMetadata@@@Z; XE_PackageManagerUtilities::SetPackageId(ushort,int,XEPackageMetadata *)
0x10041c853  mov     eax, 1
0x10041c858  jmp     short loc_10041C85C
0x10041c85a  xor     eax, eax
0x10041c85c  mov     rbx, [rsp+38h+arg_10]
0x10041c861  mov     rsi, [rsp+38h+arg_18]
0x10041c866  add     rsp, 20h
0x10041c86a  pop     r14
0x10041c86c  pop     r12
0x10041c86e  pop     rdi
0x10041c86f  retn
```
