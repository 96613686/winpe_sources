# XE_StaticPackage<1>::Init(XEPackage const *,ushort)

- ea: `0x1004641d0`
- end: `0x100464320`
- name: `?Init@?$XE_StaticPackage@$00@@UEAAHPEBUXEPackage@@G@Z`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x100404bf2`
- `0x1004641d0`
- `0x1005b83b0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x100464227`
- `KERNEL32!LoadLibraryExW` at `0x1004642b5`
- `KERNEL32!LoadLibraryExW` at `0x100464227`
- `KERNEL32!LoadLibraryExW` at `0x1004642b5`
- `KERNEL32!FreeLibrary` at `0x100464292`
- `KERNEL32!FreeLibrary` at `0x100464292`
- `KERNEL32!GetProcAddress` at `0x10046424d`
- `KERNEL32!GetProcAddress` at `0x100464260`
- `KERNEL32!GetProcAddress` at `0x1004642d1`
- `KERNEL32!GetProcAddress` at `0x10046424d`
- `KERNEL32!GetProcAddress` at `0x100464260`
- `KERNEL32!GetProcAddress` at `0x1004642d1`
- `KERNEL32!GetModuleFileNameW` at `0x100464212`
- `KERNEL32!GetModuleFileNameW` at `0x100464212`

## string_xrefs

- `0x10046423e`: `PathRemoveFileSpecW`
- `0x1004642a8`: `user32.dll`
- `0x10046421a`: `shlwapi.dll`
- `0x100464253`: `PathAppendW`

## pseudocode

```c
__int64 __fastcall XE_StaticPackage<1>::Init(__int64 a1, __int64 a2, unsigned __int16 a3)
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
  if ( !v12 || !(unsigned int)qword_100714F40(a1 + 560) )
    return 0;
  XE_PackageManagerUtilities::SetPackageId(a3, 0, *(struct XEPackageMetadata **)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x1004641d0  mov     [rsp+arg_10], rbx
0x1004641d5  mov     [rsp+arg_18], rsi
0x1004641da  push    rdi
0x1004641db  push    r12
0x1004641dd  push    r14
0x1004641df  sub     rsp, 20h
0x1004641e3  movzx   r12d, r8w
0x1004641e7  mov     rbx, rcx
0x1004641ea  mov     r8d, 208h; Size
0x1004641f0  add     rcx, 18h; void *
0x1004641f4  xor     edx, edx; Val
0x1004641f6  xor     edi, edi
0x1004641f8  call    memset_0
0x1004641fd  mov     rax, [rbx+8]
0x100464201  lea     rdx, [rbx+18h]; lpFilename
0x100464205  mov     r8d, 104h; nSize
0x10046420b  mov     rcx, [rax]
0x10046420e  mov     rcx, [rcx+48h]; hModule
0x100464212  call    cs:__imp_GetModuleFileNameW
0x100464218  xor     edx, edx; hFile
0x10046421a  lea     rcx, LibFileName; "shlwapi.dll"
0x100464221  mov     r8d, 800h; dwFlags
0x100464227  call    cs:__imp_LoadLibraryExW
0x10046422d  mov     rsi, rax
0x100464230  test    rax, rax
0x100464233  jz      loc_10046430A
0x100464239  mov     [rsp+38h+arg_0], rbp
0x10046423e  lea     rdx, aPathremovefile_0; "PathRemoveFileSpecW"
0x100464245  mov     rcx, rax; hModule
0x100464248  mov     [rsp+38h+arg_8], r15
0x10046424d  call    cs:__imp_GetProcAddress
0x100464253  lea     rdx, aPathappendw; "PathAppendW"
0x10046425a  mov     rcx, rsi; hModule
0x10046425d  mov     r15, rax
0x100464260  call    cs:__imp_GetProcAddress
0x100464266  mov     rbp, rax
0x100464269  test    r15, r15
0x10046426c  jz      short loc_10046428F
0x10046426e  test    rax, rax
0x100464271  jz      short loc_10046428F
0x100464273  lea     rcx, [rbx+18h]
0x100464277  call    r15
0x10046427a  mov     edi, eax
0x10046427c  test    eax, eax
0x10046427e  jz      short loc_10046428F
0x100464280  lea     rdx, aResources; "\\Resources"
0x100464287  lea     rcx, [rbx+18h]
0x10046428b  call    rbp
0x10046428d  mov     edi, eax
0x10046428f  mov     rcx, rsi; hLibModule
0x100464292  call    cs:__imp_FreeLibrary
0x100464298  mov     r15, [rsp+38h+arg_8]
0x10046429d  mov     rbp, [rsp+38h+arg_0]
0x1004642a2  test    edi, edi
0x1004642a4  jz      short loc_10046430A
0x1004642a6  xor     edx, edx; hFile
0x1004642a8  lea     rcx, aUser32Dll; "user32.dll"
0x1004642af  mov     r8d, 800h; dwFlags
0x1004642b5  call    cs:__imp_LoadLibraryExW
0x1004642bb  mov     [rbx+240h], rax
0x1004642c2  test    rax, rax
0x1004642c5  jz      short loc_10046430A
0x1004642c7  lea     rdx, aLoadstringw; "LoadStringW"
0x1004642ce  mov     rcx, rax; hModule
0x1004642d1  call    cs:__imp_GetProcAddress
0x1004642d7  mov     [rbx+238h], rax
0x1004642de  test    rax, rax
0x1004642e1  jz      short loc_10046430A
0x1004642e3  lea     rcx, [rbx+230h]
0x1004642ea  call    cs:qword_100714F40
0x1004642f0  test    eax, eax
0x1004642f2  jz      short loc_10046430A
0x1004642f4  mov     r8, [rbx+8]; struct XEPackageMetadata *
0x1004642f8  xor     edx, edx; int
0x1004642fa  movzx   ecx, r12w; unsigned __int16
0x1004642fe  call    ?SetPackageId@XE_PackageManagerUtilities@@SAXGHPEAUXEPackageMetadata@@@Z; XE_PackageManagerUtilities::SetPackageId(ushort,int,XEPackageMetadata *)
0x100464303  mov     eax, 1
0x100464308  jmp     short loc_10046430C
0x10046430a  xor     eax, eax
0x10046430c  mov     rbx, [rsp+38h+arg_10]
0x100464311  mov     rsi, [rsp+38h+arg_18]
0x100464316  add     rsp, 20h
0x10046431a  pop     r14
0x10046431c  pop     r12
0x10046431e  pop     rdi
0x10046431f  retn
```
