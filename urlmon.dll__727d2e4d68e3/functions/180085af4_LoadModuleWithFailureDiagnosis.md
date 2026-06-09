# LoadModuleWithFailureDiagnosis

- ea: `0x180085af4`
- end: `0x180085cc8`
- name: `LoadModuleWithFailureDiagnosis`
- size: `468`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800850e0`
- `0x180085af4`

## callees

- `0x180085af4`
- `0x1800aed1c`
- `0x180113c5c`
- `0x1801285fe`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180085b11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180085b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c32`
- `imagehlp!ImageNtHeader` at `0x180085bbe`
- `imagehlp!ImageNtHeader` at `0x180085bbe`
- `imagehlp!UnMapAndLoad` at `0x180085c00`
- `imagehlp!UnMapAndLoad` at `0x180085c00`
- `imagehlp!ImageDirectoryEntryToData` at `0x180085b92`
- `imagehlp!ImageDirectoryEntryToData` at `0x180085b92`
- `imagehlp!MapAndLoad` at `0x180085b61`
- `imagehlp!MapAndLoad` at `0x180085b61`
- `imagehlp!ImageRvaToVa` at `0x180085bd8`
- `imagehlp!ImageRvaToVa` at `0x180085bd8`

## pseudocode

```c
HMODULE __fastcall LoadModuleWithFailureDiagnosis(const CHAR *a1)
{
  HMODULE result; // rax
  signed int LastError; // eax
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  ULONG v6; // ebx
  struct _IMAGE_NT_HEADERS64 *v7; // rax
  PVOID v8; // rax
  signed int v9; // eax
  _LOADED_IMAGE LoadedImage; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  ULONG Size; // [rsp+A8h] [rbp+10h] BYREF

  result = LoadLibraryExA(a1, 0, 0x800u);
  if ( !result )
  {
    LastError = GetLastError();
    if ( LastError == 126 )
    {
      memset_0(&LoadedImage, 0, sizeof(LoadedImage));
      if ( MapAndLoad(a1, 0, &LoadedImage, 1, 1) )
      {
        Size = 0;
        v4 = ImageDirectoryEntryToData(LoadedImage.MappedAddress, 0, 1u, &Size);
        v5 = v4;
        if ( v4 && Size && v4[3] )
        {
          do
          {
            v6 = v5[3];
            v7 = ImageNtHeader(LoadedImage.MappedAddress);
            v8 = ImageRvaToVa(v7, LoadedImage.MappedAddress, v6, 0);
            if ( v8 )
              LoadModuleWithFailureDiagnosis(v8);
            v5 += 5;
          }
          while ( v5[3] );
        }
        UnMapAndLoad(&LoadedImage);
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
          "%hs",
          a1);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
        (const char *)(unsigned int)v9,
        (int)"%hs",
        a1);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
      (const char *)(unsigned int)LastError,
      (int)"%hs",
      a1);
  }
  return result;
}

```

## disassembly

```asm
0x180085af4  mov     [rsp+arg_0], rbx
0x180085af9  mov     [rsp+arg_10], rsi
0x180085afe  push    rdi
0x180085aff  sub     rsp, 90h
0x180085b06  xor     edx, edx; hFile
0x180085b08  mov     r8d, 800h; dwFlags
0x180085b0e  mov     rsi, rcx
0x180085b11  call    cs:__imp_LoadLibraryExA
0x180085b18  nop     dword ptr [rax+rax+00h]
0x180085b1d  test    rax, rax
0x180085b20  jnz     loc_180085CB2
0x180085b26  call    cs:__imp_GetLastError
0x180085b2d  nop     dword ptr [rax+rax+00h]
0x180085b32  cmp     eax, 7Eh ; '~'
0x180085b35  jnz     loc_180085C78
0x180085b3b  xor     edx, edx; Val
0x180085b3d  lea     r8d, [rax-26h]; Size
0x180085b41  lea     rcx, [rsp+98h+LoadedImage]; void *
0x180085b46  call    memset_0
0x180085b4b  mov     ebx, 1
0x180085b50  lea     r8, [rsp+98h+LoadedImage]; LoadedImage
0x180085b55  mov     r9d, ebx; DotDll
0x180085b58  mov     [rsp+98h+ReadOnly], ebx; ReadOnly
0x180085b5c  xor     edx, edx; DllPath
0x180085b5e  mov     rcx, rsi; ImageName
0x180085b61  call    cs:__imp_MapAndLoad
0x180085b68  nop     dword ptr [rax+rax+00h]
0x180085b6d  test    eax, eax
0x180085b6f  jz      loc_180085C32
0x180085b75  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180085b7a  lea     r9, [rsp+98h+Size]; Size
0x180085b82  mov     r8d, ebx; DirectoryEntry
0x180085b85  mov     [rsp+98h+Size], 0
0x180085b90  xor     edx, edx; MappedAsImage
0x180085b92  call    cs:__imp_ImageDirectoryEntryToData
0x180085b99  nop     dword ptr [rax+rax+00h]
0x180085b9e  mov     rdi, rax
0x180085ba1  test    rax, rax
0x180085ba4  jz      short loc_180085BFB
0x180085ba6  cmp     [rsp+98h+Size], 0
0x180085bae  jz      short loc_180085BFB
0x180085bb0  cmp     dword ptr [rax+0Ch], 0
0x180085bb4  jz      short loc_180085BFB
0x180085bb6  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180085bbb  mov     ebx, [rdi+0Ch]
0x180085bbe  call    cs:__imp_ImageNtHeader
0x180085bc5  nop     dword ptr [rax+rax+00h]
0x180085bca  mov     rdx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180085bcf  xor     r9d, r9d; LastRvaSection
0x180085bd2  mov     rcx, rax; NtHeaders
0x180085bd5  mov     r8d, ebx; Rva
0x180085bd8  call    cs:__imp_ImageRvaToVa
0x180085bdf  nop     dword ptr [rax+rax+00h]
0x180085be4  test    rax, rax
0x180085be7  jz      short loc_180085BF1
0x180085be9  mov     rcx, rax
0x180085bec  call    LoadModuleWithFailureDiagnosis
0x180085bf1  add     rdi, 14h
0x180085bf5  cmp     dword ptr [rdi+0Ch], 0
0x180085bf9  jnz     short loc_180085BB6
0x180085bfb  lea     rcx, [rsp+98h+LoadedImage]; LoadedImage
0x180085c00  call    cs:__imp_UnMapAndLoad
0x180085c07  nop     dword ptr [rax+rax+00h]
0x180085c0c  mov     rcx, [rsp+98h]; this
0x180085c14  lea     r9, aHs; "%hs"
0x180085c1b  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180085c22  mov     qword ptr [rsp+98h+ReadOnly], rsi; char *
0x180085c27  mov     edx, 2Fh ; '/'; void *
0x180085c2c  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180085c32  call    cs:__imp_GetLastError
0x180085c39  nop     dword ptr [rax+rax+00h]
0x180085c3e  test    eax, eax
0x180085c40  jle     short loc_180085C4A
0x180085c42  movzx   eax, ax
0x180085c45  or      eax, 80070000h
0x180085c4a  mov     rcx, [rsp+98h]; this
0x180085c52  lea     rdx, aHs; "%hs"
0x180085c59  mov     [rsp+98h+var_70], rsi; char *
0x180085c5e  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180085c65  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x180085c6a  mov     r9d, eax; char *
0x180085c6d  mov     edx, 33h ; '3'; void *
0x180085c72  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180085c78  test    eax, eax
0x180085c7a  jle     short loc_180085C84
0x180085c7c  movzx   eax, ax
0x180085c7f  or      eax, 80070000h
0x180085c84  mov     rcx, [rsp+98h]; this
0x180085c8c  lea     rdx, aHs; "%hs"
0x180085c93  mov     [rsp+98h+var_70], rsi; char *
0x180085c98  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180085c9f  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x180085ca4  mov     r9d, eax; char *
0x180085ca7  mov     edx, 38h ; '8'; void *
0x180085cac  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180085cb2  lea     r11, [rsp+98h+var_8]
0x180085cba  mov     rbx, [r11+10h]
0x180085cbe  mov     rsi, [r11+20h]
0x180085cc2  mov     rsp, r11
0x180085cc5  pop     rdi
0x180085cc6  retn
```
