# FindOriginalFileNameFromResource

- ea: `0x18001a3f4`
- end: `0x18001a79a`
- name: `FindOriginalFileNameFromResource`
- size: `934`
- prototype: `__int64 __fastcall(HMODULE, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a7a0`

## callees

- `0x1800049d0`
- `0x18001a3f4`
- `0x18001bb64`
- `0x18001f038`
- `0x1800201d4`
- `0x18002084c`
- `0x180021ec0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a59f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a59f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a618`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a42b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a42b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001a472`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001a472`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18001a4ec`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18001a4ec`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a57a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a60a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a6a4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a57a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a60a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001a6a4`

## string_xrefs

- `0x18001a449`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a485`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a4c4`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a4fd`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a58b`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a5e1`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a62c`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a67b`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a6b5`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a707`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`
- `0x18001a75b`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`

## pseudocode

```c
__int64 __fastcall FindOriginalFileNameFromResource(HMODULE a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int LastError; // ebx
  DWORD FileVersionInfoSize; // eax
  const char *v7; // r9
  DWORD v8; // ebx
  HLOCAL v10; // rax
  void *v11; // rdi
  const char *v12; // r9
  const char *v13; // r9
  int v14; // eax
  unsigned __int64 v15; // r8
  const char *v16; // r9
  int v17; // eax
  const char *v18; // r9
  __int64 *hlocal_string_nothrow; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // r8
  __int64 *v22; // rax
  __int64 v23; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwHandle; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[8]; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubBlock[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( GetModuleFileNameW(a1, Filename, 0x104u) - 1 <= 0x102 )
  {
    dwHandle = 0;
    FileVersionInfoSize = GetFileVersionInfoSizeExW(0, Filename, &dwHandle);
    v8 = FileVersionInfoSize;
    if ( !FileVersionInfoSize )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2C,
               (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
               v7);
    v10 = LocalAlloc(0x40u, FileVersionInfoSize + 2LL);
    v11 = v10;
    v30[0] = v10;
    if ( v10 )
    {
      if ( GetFileVersionInfoExW(0, Filename, dwHandle, v8, v10) )
      {
        lpBuffer = 0;
        puLen = 0;
        wcscpy(SubBlock, L"\\StringFileInfo\\12341234\\OriginalFilename");
        if ( !VerQueryValueW(v11, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x39,
                        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                        v13);
          LocalFree(v11);
          return LastError;
        }
        lpDataa = *((unsigned __int16 *)lpBuffer + 1);
        v14 = StringCchPrintfW(
                SubBlock,
                0x2Au,
                L"\\StringFileInfo\\%04X%04X\\OriginalFilename",
                *(unsigned __int16 *)lpBuffer);
        LastError = v14;
        if ( v14 >= 0 )
        {
          if ( !VerQueryValueW(v11, SubBlock, &lpBuffer, &puLen) )
          {
            if ( GetLastError() == 1813 )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x40,
                            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                            v16);
              goto LABEL_26;
            }
            lpDataa = *((unsigned __int16 *)lpBuffer + 1);
            v17 = StringCchPrintfW(
                    SubBlock,
                    0x2Au,
                    L"\\StringFileInfo\\%04X%04X\\InternalName",
                    *(unsigned __int16 *)lpBuffer);
            LastError = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x43,
                (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                (const char *)(unsigned int)v17,
                lpDataa);
              goto LABEL_26;
            }
            if ( !VerQueryValueW(v11, SubBlock, &lpBuffer, &puLen) )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x44,
                            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                            v18);
              goto LABEL_26;
            }
          }
          hlocal_string_nothrow = (__int64 *)wil::make_hlocal_string_nothrow(
                                               (wil *)v29,
                                               (const unsigned __int16 *)lpBuffer,
                                               v15);
          v20 = *hlocal_string_nothrow;
          *hlocal_string_nothrow = 0;
          *a2 = v20;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v29);
          if ( *a2 )
          {
            if ( !a3
              || (v22 = (__int64 *)wil::make_hlocal_string_nothrow((wil *)v29, Filename, v21),
                  v23 = *v22,
                  *v22 = 0,
                  *a3 = v23,
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v29),
                  *a3) )
            {
              LastError = 0;
            }
            else
            {
              LastError = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x52,
                (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                (const char *)0x8007000ELL,
                lpDataa);
            }
          }
          else
          {
            LastError = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
              (const char *)0x8007000ELL,
              lpDataa);
          }
          goto LABEL_26;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
          (const char *)(unsigned int)v14,
          lpDataa);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x31,
                      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
                      v12);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
        (const char *)0x8007000ELL,
        lpData);
    }
LABEL_26:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
    return LastError;
  }
  LastError = -2147024774;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
    (const char *)0x8007007ALL,
    lpData);
  return LastError;
}

```

## disassembly

```asm
0x18001a3f4  push    rbp
0x18001a3f6  push    rbx
0x18001a3f7  push    rsi
0x18001a3f8  push    rdi
0x18001a3f9  push    r14
0x18001a3fb  lea     rbp, [rsp-1E0h]
0x18001a403  sub     rsp, 2E0h
0x18001a40a  mov     rax, cs:__security_cookie
0x18001a411  xor     rax, rsp
0x18001a414  mov     [rbp+200h+var_30], rax
0x18001a41b  mov     rsi, r8
0x18001a41e  mov     r14, rdx
0x18001a421  mov     r8d, 104h; nSize
0x18001a427  lea     rdx, [rbp+200h+Filename]; lpFilename
0x18001a42b  call    cs:__imp_GetModuleFileNameW
0x18001a431  dec     eax
0x18001a433  cmp     eax, 102h
0x18001a438  jbe     short loc_18001A45F
0x18001a43a  mov     rcx, [rbp+208h]; this
0x18001a441  mov     ebx, 8007007Ah
0x18001a446  mov     r9d, ebx; char *
0x18001a449  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a450  mov     edx, 28h ; '('; void *
0x18001a455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a45a  jmp     loc_18001A77B
0x18001a45f  mov     [rsp+300h+dwHandle], 0
0x18001a467  lea     r8, [rsp+300h+dwHandle]; lpdwHandle
0x18001a46c  lea     rdx, [rbp+200h+Filename]; lpwstrFilename
0x18001a470  xor     ecx, ecx; dwFlags
0x18001a472  call    cs:__imp_GetFileVersionInfoSizeExW
0x18001a478  mov     ebx, eax
0x18001a47a  test    eax, eax
0x18001a47c  jnz     short loc_18001A499
0x18001a47e  mov     rcx, [rbp+208h]; this
0x18001a485  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a48c  lea     edx, [rax+2Ch]; void *
0x18001a48f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a494  jmp     loc_18001A77D
0x18001a499  lea     rdx, [rbx+2]; uBytes
0x18001a49d  mov     ecx, 40h ; '@'; uFlags
0x18001a4a2  call    cs:__imp_LocalAlloc
0x18001a4a8  mov     rdi, rax
0x18001a4ab  mov     [rsp+300h+var_2B0], rax
0x18001a4b0  test    rax, rax
0x18001a4b3  jnz     short loc_18001A4D9
0x18001a4b5  mov     rcx, [rbp+208h]; this
0x18001a4bc  mov     ebx, 8007000Eh
0x18001a4c1  mov     r9d, ebx; char *
0x18001a4c4  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a4cb  lea     edx, [rax+2Fh]; void *
0x18001a4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4d3  nop
0x18001a4d4  jmp     loc_18001A771
0x18001a4d9  mov     qword ptr [rsp+300h+lpData], rdi; lpData
0x18001a4de  mov     r9d, ebx; dwLen
0x18001a4e1  mov     r8d, [rsp+300h+dwHandle]; dwHandle
0x18001a4e6  lea     rdx, [rbp+200h+Filename]; lpwstrFilename
0x18001a4ea  xor     ecx, ecx; dwFlags
0x18001a4ec  call    cs:__imp_GetFileVersionInfoExW
0x18001a4f2  test    eax, eax
0x18001a4f4  jnz     short loc_18001A513
0x18001a4f6  mov     rcx, [rbp+208h]; this
0x18001a4fd  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a504  lea     edx, [rax+31h]; void *
0x18001a507  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a50c  mov     ebx, eax
0x18001a50e  jmp     loc_18001A771
0x18001a513  mov     [rsp+300h+lpBuffer], 0
0x18001a51c  mov     [rsp+300h+puLen], 0
0x18001a524  movaps  xmm0, xmmword ptr cs:aStringfileinfo_0; "\\StringFileInfo\\12341234\\OriginalFil"...
0x18001a52b  movaps  xmmword ptr [rsp+300h+SubBlock], xmm0
0x18001a530  movaps  xmm1, xmmword ptr cs:aStringfileinfo_0+10h; "ileInfo\\12341234\\OriginalFilename"
0x18001a537  movaps  [rsp+300h+var_290], xmm1
0x18001a53c  movaps  xmm0, xmmword ptr cs:aStringfileinfo_0+20h; "12341234\\OriginalFilename"
0x18001a543  movaps  [rbp+200h+var_280], xmm0
0x18001a547  movaps  xmm1, xmmword ptr cs:aStringfileinfo_0+30h; "\\OriginalFilename"
0x18001a54e  movaps  [rbp+200h+var_270], xmm1
0x18001a552  movaps  xmm0, xmmword ptr cs:aStringfileinfo_0+40h; "lFilename"
0x18001a559  movaps  [rbp+200h+var_260], xmm0
0x18001a55d  mov     eax, dword ptr cs:aStringfileinfo_0+50h; "e"
0x18001a563  mov     [rbp+200h+var_250], eax
0x18001a566  lea     r9, [rsp+300h+puLen]; puLen
0x18001a56b  lea     r8, [rsp+300h+lpBuffer]; lplpBuffer
0x18001a570  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18001a577  mov     rcx, rdi; pBlock
0x18001a57a  call    cs:__imp_VerQueryValueW
0x18001a580  test    eax, eax
0x18001a582  jnz     short loc_18001A5AA
0x18001a584  mov     rcx, [rbp+208h]; this
0x18001a58b  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a592  lea     edx, [rax+39h]; void *
0x18001a595  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a59a  mov     ebx, eax
0x18001a59c  mov     rcx, rdi; hMem
0x18001a59f  call    cs:__imp_LocalFree
0x18001a5a5  jmp     loc_18001A77B
0x18001a5aa  mov     rax, [rsp+300h+lpBuffer]
0x18001a5af  movzx   ecx, word ptr [rax+2]
0x18001a5b3  movzx   r9d, word ptr [rax]
0x18001a5b7  mov     [rsp+300h+lpData], ecx; int
0x18001a5bb  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\OriginalFil"...
0x18001a5c2  mov     edx, 2Ah ; '*'; unsigned __int64
0x18001a5c7  lea     rcx, [rsp+300h+SubBlock]; unsigned __int16 *
0x18001a5cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a5d1  mov     ebx, eax
0x18001a5d3  test    eax, eax
0x18001a5d5  jns     short loc_18001A5F8
0x18001a5d7  mov     rcx, [rbp+208h]; this
0x18001a5de  mov     r9d, eax; char *
0x18001a5e1  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a5e8  mov     edx, 3Bh ; ';'; void *
0x18001a5ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5f2  nop
0x18001a5f3  jmp     loc_18001A771
0x18001a5f8  lea     r9, [rsp+300h+puLen]; puLen
0x18001a5fd  lea     r8, [rsp+300h+lpBuffer]; lplpBuffer
0x18001a602  lea     rdx, [rsp+300h+SubBlock]; lpSubBlock
0x18001a607  mov     rcx, rdi; pBlock
0x18001a60a  call    cs:__imp_VerQueryValueW
0x18001a610  test    eax, eax
0x18001a612  jnz     loc_18001A6CB
0x18001a618  call    cs:__imp_GetLastError
0x18001a61e  cmp     eax, 715h
0x18001a623  jnz     short loc_18001A644
0x18001a625  mov     rcx, [rbp+208h]; this
0x18001a62c  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a633  mov     edx, 40h ; '@'; void *
0x18001a638  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a63d  mov     ebx, eax
0x18001a63f  jmp     loc_18001A771
0x18001a644  mov     rax, [rsp+300h+lpBuffer]
0x18001a649  movzx   ecx, word ptr [rax+2]
0x18001a64d  movzx   r9d, word ptr [rax]
0x18001a651  mov     [rsp+300h+lpData], ecx; int
0x18001a655  lea     r8, aStringfileinfo_2; "\\StringFileInfo\\%04X%04X\\InternalNam"...
0x18001a65c  mov     edx, 2Ah ; '*'; unsigned __int64
0x18001a661  lea     rcx, [rsp+300h+SubBlock]; unsigned __int16 *
0x18001a666  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a66b  mov     ebx, eax
0x18001a66d  test    eax, eax
0x18001a66f  jns     short loc_18001A692
0x18001a671  mov     rcx, [rbp+208h]; this
0x18001a678  mov     r9d, eax; char *
0x18001a67b  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a682  mov     edx, 43h ; 'C'; void *
0x18001a687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a68c  nop
0x18001a68d  jmp     loc_18001A771
0x18001a692  lea     r9, [rsp+300h+puLen]; puLen
0x18001a697  lea     r8, [rsp+300h+lpBuffer]; lplpBuffer
0x18001a69c  lea     rdx, [rsp+300h+SubBlock]; lpSubBlock
0x18001a6a1  mov     rcx, rdi; pBlock
0x18001a6a4  call    cs:__imp_VerQueryValueW
0x18001a6aa  test    eax, eax
0x18001a6ac  jnz     short loc_18001A6CB
0x18001a6ae  mov     rcx, [rbp+208h]; this
0x18001a6b5  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a6bc  lea     edx, [rax+44h]; void *
0x18001a6bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a6c4  mov     ebx, eax
0x18001a6c6  jmp     loc_18001A771
0x18001a6cb  mov     rdx, [rsp+300h+lpBuffer]; unsigned __int16 *
0x18001a6d0  lea     rcx, [rsp+300h+var_2B8]; this
0x18001a6d5  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x18001a6da  nop
0x18001a6db  mov     rcx, [rax]
0x18001a6de  mov     qword ptr [rax], 0
0x18001a6e5  mov     [r14], rcx
0x18001a6e8  lea     rcx, [rsp+300h+var_2B8]
0x18001a6ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a6f2  cmp     qword ptr [r14], 0
0x18001a6f6  jnz     short loc_18001A71B
0x18001a6f8  mov     rcx, [rbp+208h]; this
0x18001a6ff  mov     ebx, 8007000Eh
0x18001a704  mov     r9d, ebx; char *
0x18001a707  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a70e  mov     edx, 4Dh ; 'M'; void *
0x18001a713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a718  nop
0x18001a719  jmp     short loc_18001A771
0x18001a71b  test    rsi, rsi
0x18001a71e  jz      short loc_18001A76F
0x18001a720  lea     rdx, [rbp+200h+Filename]; unsigned __int16 *
0x18001a724  lea     rcx, [rsp+300h+var_2B8]; this
0x18001a729  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x18001a72e  nop
0x18001a72f  mov     rcx, [rax]
0x18001a732  mov     qword ptr [rax], 0
0x18001a739  mov     [rsi], rcx
0x18001a73c  lea     rcx, [rsp+300h+var_2B8]
0x18001a741  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a746  cmp     qword ptr [rsi], 0
0x18001a74a  jnz     short loc_18001A76F
0x18001a74c  mov     rcx, [rbp+208h]; this
0x18001a753  mov     ebx, 8007000Eh
0x18001a758  mov     r9d, ebx; char *
0x18001a75b  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a762  mov     edx, 52h ; 'R'; void *
0x18001a767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a76c  nop
0x18001a76d  jmp     short loc_18001A771
0x18001a76f  xor     ebx, ebx
0x18001a771  lea     rcx, [rsp+300h+var_2B0]
0x18001a776  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a77b  mov     eax, ebx
0x18001a77d  mov     rcx, [rbp+200h+var_30]
0x18001a784  xor     rcx, rsp; StackCookie
0x18001a787  call    __security_check_cookie
0x18001a78c  add     rsp, 2E0h
0x18001a793  pop     r14
0x18001a795  pop     rdi
0x18001a796  pop     rsi
0x18001a797  pop     rbx
0x18001a798  pop     rbp
0x18001a799  retn
```
