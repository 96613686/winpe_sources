# XEPackage0::HistoryTarget::OpenWriter(XE_CXFileWriter *,XE_ErrorContext *,wchar_t *,uint,uint)

- ea: `0x1005d69b0`
- end: `0x1005d6ca4`
- name: `?OpenWriter@HistoryTarget@XEPackage0@@AEAAHPEAVXE_CXFileWriter@@PEAVXE_ErrorContext@@PEA_WII@Z`
- size: `756`
- prototype: `int(XEPackage0::HistoryTarget *__hidden this, struct XE_CXFileWriter *, struct XE_ErrorContext *, wchar_t *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1005d65f0`
- `0x1005d6e30`
- `0x1005d74f0`

## callees

- `0x100403070`
- `0x100442a60`
- `0x10044acd0`
- `0x100450160`
- `0x100458050`
- `0x1005d69b0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1005d6c79`
- `KERNEL32!LocalFree` at `0x1005d6c79`
- `KERNEL32!GetLastError` at `0x1005d6b28`
- `KERNEL32!GetLastError` at `0x1005d6bc6`
- `KERNEL32!GetLastError` at `0x1005d6b28`
- `KERNEL32!GetLastError` at `0x1005d6bc6`
- `KERNEL32!FormatMessageW` at `0x1005d6bbc`
- `KERNEL32!FormatMessageW` at `0x1005d6bf3`
- `KERNEL32!FormatMessageW` at `0x1005d6bbc`
- `KERNEL32!FormatMessageW` at `0x1005d6bf3`

## string_xrefs

- `0x1005d6b00`: `Failed to use the paths specified by the directory location and directory name parameters for the compressed history target.`
- `0x1005d6c62`: `Failed to create or write to file '%ws'. Consult local XE log for detailed information. Last OS error code reported: %I32u %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XEPackage0::HistoryTarget::OpenWriter(
        XEPackage0::HistoryTarget *this,
        struct XE_CXFileWriter *a2,
        struct XE_ErrorContext *a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int a6)
{
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rbx
  wchar_t *v11; // rdi
  unsigned int v12; // eax
  int v13; // eax
  DWORD LastError; // edi
  DWORD v16; // eax
  HLOCAL v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rbx
  wchar_t *v20; // rbp
  unsigned int v21; // eax
  int v22; // eax
  const wchar_t *v23; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-A88h]
  WCHAR Buffer[4]; // [rsp+50h] [rbp-A58h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A50h]
  wchar_t FileName[264]; // [rsp+60h] [rbp-A48h] BYREF
  wchar_t v28[512]; // [rsp+270h] [rbp-838h] BYREF
  _BYTE v29[1024]; // [rsp+670h] [rbp-438h] BYREF

  v26 = -2;
  if ( a5 || a6 )
    v8 = StringCchPrintf_lW(
           FileName,
           260,
           L"%s\\%s_%s_%d_%d.xcx",
           g_crtLocale,
           (char *)this + 9356,
           (char *)this + 9876,
           a4,
           a5,
           a6);
  else
    v8 = StringCchPrintf_lW(FileName, 260, L"%s\\%s_%s.xcx", g_crtLocale, (char *)this + 9356, (char *)this + 9876, a4);
  if ( v8 >= 0 )
  {
    if ( (unsigned int)XE_CXFileWriter::OpenWriter(a2, (char *)FileName) )
      return 1;
    LastError = GetLastError();
    if ( a3 && *(_QWORD *)a3 && !*(_QWORD *)(*(_QWORD *)a3 + 16LL) )
    {
      *(_QWORD *)(*(_QWORD *)a3 + 16LL) = qword_100714F08(0, 1024);
      if ( *(_QWORD *)(*(_QWORD *)a3 + 16LL) )
        *(_DWORD *)(*(_QWORD *)a3 + 24LL) = 512;
      else
        qword_100714EF0(1, 18, 0);
      *(_QWORD *)Buffer = 0;
      v16 = qword_100715058();
      if ( !FormatMessageW(0x1300u, 0, LastError, v16, Buffer, 0, 0) && GetLastError() == 1815 )
        FormatMessageW(0x1300u, 0, LastError, 0, Buffer, 0, 0);
      v17 = *(HLOCAL *)Buffer;
      v18 = *(_QWORD *)a3;
      v19 = *(unsigned int *)(*(_QWORD *)a3 + 24LL);
      v20 = *(wchar_t **)(v18 + 16);
      v21 = qword_100715058();
      if ( v19 )
      {
        v22 = qword_1007152E0(word_10078FA84 & 0x3FF, v21, 1254, v29, 512);
        _mm_lfence();
        LODWORD(lpBuffer) = LastError;
        v23 = (const wchar_t *)v29;
        if ( !v22 )
          v23 = L"Failed to create or write to file '%ws'. Consult local XE log for detailed information. Last OS error co"
                 "de reported: %I32u %ws";
        StringCchPrintfW(v20, (unsigned int)v19, v23, FileName, lpBuffer, v17);
      }
      if ( *(_QWORD *)Buffer )
        LocalFree(*(HLOCAL *)Buffer);
    }
    return 0;
  }
  if ( !a3 )
    return 0;
  if ( !(unsigned int)XE_ErrorContext::AllocateErrorMessage(a3, 0x200u) )
    return 0;
  v9 = *(_QWORD *)a3;
  v10 = *(unsigned int *)(*(_QWORD *)a3 + 24LL);
  v11 = *(wchar_t **)(v9 + 16);
  v12 = qword_100715058();
  if ( !v10 )
    return 0;
  v13 = qword_1007152E0(word_10078FA84 & 0x3FF, v12, 13869, v28, 512);
  _mm_lfence();
  if ( v13 )
    StringCchPrintfW(v11, (unsigned int)v10, v28);
  else
    StringCchPrintfW(
      v11,
      (unsigned int)v10,
      L"Failed to use the paths specified by the directory location and directory name parameters for the compressed history target.");
  return 0;
}

```

## disassembly

```asm
0x1005d69b0  push    rbx
0x1005d69b2  push    rbp
0x1005d69b3  push    rsi
0x1005d69b4  push    rdi
0x1005d69b5  sub     rsp, 0A88h
0x1005d69bc  mov     [rsp+0AA8h+var_A50], 0FFFFFFFFFFFFFFFEh
0x1005d69c5  mov     rax, cs:__security_cookie
0x1005d69cc  xor     rax, rsp
0x1005d69cf  mov     [rsp+0AA8h+var_38], rax
0x1005d69d7  mov     rbx, r8
0x1005d69da  mov     rdi, rdx
0x1005d69dd  mov     edx, [rsp+0AA8h+arg_28]
0x1005d69e4  mov     r8d, [rsp+0AA8h+arg_20]
0x1005d69ec  test    r8d, r8d
0x1005d69ef  jnz     short loc_1005D6A31
0x1005d69f1  test    edx, edx
0x1005d69f3  jnz     short loc_1005D6A31
0x1005d69f5  lea     rax, [rcx+2694h]
0x1005d69fc  add     rcx, 248Ch
0x1005d6a03  mov     [rsp+0AA8h+Arguments], r9
0x1005d6a08  mov     qword ptr [rsp+0AA8h+nSize], rax
0x1005d6a0d  mov     [rsp+0AA8h+lpBuffer], rcx
0x1005d6a12  mov     r9, cs:?g_crtLocale@@3PEAU__crt_locale_pointers@@EA; struct __crt_locale_pointers *
0x1005d6a19  lea     r8, aSSSXcx; "%s\\%s_%s.xcx"
0x1005d6a20  mov     edx, 104h; unsigned __int64
0x1005d6a25  lea     rcx, [rsp+0AA8h+FileName]; Buffer
0x1005d6a2a  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1005d6a2f  jmp     short loc_1005D6A74
0x1005d6a31  lea     rax, [rcx+2694h]
0x1005d6a38  add     rcx, 248Ch
0x1005d6a3f  mov     [rsp+0AA8h+var_A68], edx
0x1005d6a43  mov     [rsp+0AA8h+var_A70], r8d
0x1005d6a48  mov     [rsp+0AA8h+Arguments], r9
0x1005d6a4d  mov     qword ptr [rsp+0AA8h+nSize], rax
0x1005d6a52  mov     [rsp+0AA8h+lpBuffer], rcx
0x1005d6a57  mov     r9, cs:?g_crtLocale@@3PEAU__crt_locale_pointers@@EA; struct __crt_locale_pointers *
0x1005d6a5e  lea     r8, aSSSDDXcx; "%s\\%s_%s_%d_%d.xcx"
0x1005d6a65  mov     edx, 104h; unsigned __int64
0x1005d6a6a  lea     rcx, [rsp+0AA8h+FileName]; Buffer
0x1005d6a6f  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1005d6a74  test    eax, eax
0x1005d6a76  jns     loc_1005D6B13
0x1005d6a7c  test    rbx, rbx
0x1005d6a7f  jz      loc_1005D6C7F
0x1005d6a85  mov     edx, 200h; unsigned int
0x1005d6a8a  mov     rcx, rbx; this
0x1005d6a8d  call    ?AllocateErrorMessage@XE_ErrorContext@@QEAAHI@Z; XE_ErrorContext::AllocateErrorMessage(uint)
0x1005d6a92  test    eax, eax
0x1005d6a94  jz      loc_1005D6C7F
0x1005d6a9a  mov     rax, [rbx]
0x1005d6a9d  mov     ebx, [rax+18h]
0x1005d6aa0  mov     rdi, [rax+10h]
0x1005d6aa4  call    cs:qword_100715058
0x1005d6aaa  test    rbx, rbx
0x1005d6aad  jz      loc_1005D6C7F
0x1005d6ab3  movzx   ecx, cs:word_10078FA84
0x1005d6aba  mov     edx, 3FFh
0x1005d6abf  and     cx, dx
0x1005d6ac2  mov     dword ptr [rsp+0AA8h+lpBuffer], 200h
0x1005d6aca  lea     r9, [rsp+0AA8h+var_838]
0x1005d6ad2  mov     r8d, 362Dh
0x1005d6ad8  mov     edx, eax
0x1005d6ada  call    cs:qword_1007152E0
0x1005d6ae0  lfence
0x1005d6ae3  mov     edx, ebx; unsigned __int64
0x1005d6ae5  mov     rcx, rdi; Buffer
0x1005d6ae8  test    eax, eax
0x1005d6aea  jz      short loc_1005D6B00
0x1005d6aec  lea     r8, [rsp+0AA8h+var_838]; wchar_t *
0x1005d6af4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1005d6af9  xor     eax, eax
0x1005d6afb  jmp     loc_1005D6C88
0x1005d6b00  lea     r8, aFailedToUseThe; "Failed to use the paths specified by th"...
0x1005d6b07  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1005d6b0c  xor     eax, eax
0x1005d6b0e  jmp     loc_1005D6C88
0x1005d6b13  lea     rdx, [rsp+0AA8h+FileName]; lpFileName
0x1005d6b18  mov     rcx, rdi; this
0x1005d6b1b  call    ?OpenWriter@XE_CXFileWriter@@QEAAHPEB_W@Z; XE_CXFileWriter::OpenWriter(wchar_t const *)
0x1005d6b20  test    eax, eax
0x1005d6b22  jnz     loc_1005D6C83
0x1005d6b28  call    cs:__imp_GetLastError
0x1005d6b2e  mov     edi, eax
0x1005d6b30  test    rbx, rbx
0x1005d6b33  jz      loc_1005D6C7F
0x1005d6b39  mov     rcx, [rbx]
0x1005d6b3c  test    rcx, rcx
0x1005d6b3f  jz      loc_1005D6C7F
0x1005d6b45  cmp     qword ptr [rcx+10h], 0
0x1005d6b4a  jnz     loc_1005D6C7F
0x1005d6b50  mov     edx, 400h
0x1005d6b55  xor     ecx, ecx
0x1005d6b57  call    cs:qword_100714F08
0x1005d6b5d  mov     rcx, [rbx]
0x1005d6b60  mov     [rcx+10h], rax
0x1005d6b64  mov     rax, [rbx]
0x1005d6b67  cmp     qword ptr [rax+10h], 0
0x1005d6b6c  jz      short loc_1005D6B77
0x1005d6b6e  mov     dword ptr [rax+18h], 200h
0x1005d6b75  jmp     short loc_1005D6B88
0x1005d6b77  mov     edx, 12h
0x1005d6b7c  lea     ecx, [rdx-11h]
0x1005d6b7f  xor     r8d, r8d
0x1005d6b82  call    cs:qword_100714EF0
0x1005d6b88  xor     esi, esi
0x1005d6b8a  mov     qword ptr [rsp+0AA8h+Buffer], rsi
0x1005d6b8f  cmp     qword ptr [rsp+0AA8h+Buffer], rsi
0x1005d6b94  jnz     short loc_1005D6BF9
0x1005d6b96  call    cs:qword_100715058
0x1005d6b9c  mov     r9d, eax; dwLanguageId
0x1005d6b9f  mov     [rsp+0AA8h+Arguments], rsi; Arguments
0x1005d6ba4  mov     [rsp+0AA8h+nSize], esi; nSize
0x1005d6ba8  lea     rax, [rsp+0AA8h+Buffer]
0x1005d6bad  mov     [rsp+0AA8h+lpBuffer], rax; lpBuffer
0x1005d6bb2  mov     r8d, edi; dwMessageId
0x1005d6bb5  xor     edx, edx; lpSource
0x1005d6bb7  mov     ecx, 1300h; dwFlags
0x1005d6bbc  call    cs:__imp_FormatMessageW
0x1005d6bc2  test    eax, eax
0x1005d6bc4  jnz     short loc_1005D6BF9
0x1005d6bc6  call    cs:__imp_GetLastError
0x1005d6bcc  cmp     eax, 717h
0x1005d6bd1  jnz     short loc_1005D6BF9
0x1005d6bd3  mov     [rsp+0AA8h+Arguments], rsi; Arguments
0x1005d6bd8  mov     [rsp+0AA8h+nSize], esi; nSize
0x1005d6bdc  lea     rax, [rsp+0AA8h+Buffer]
0x1005d6be1  mov     [rsp+0AA8h+lpBuffer], rax; lpBuffer
0x1005d6be6  xor     r9d, r9d; dwLanguageId
0x1005d6be9  mov     r8d, edi; dwMessageId
0x1005d6bec  xor     edx, edx; lpSource
0x1005d6bee  mov     ecx, 1300h; dwFlags
0x1005d6bf3  call    cs:__imp_FormatMessageW
0x1005d6bf9  mov     rsi, qword ptr [rsp+0AA8h+Buffer]
0x1005d6bfe  mov     rax, [rbx]
0x1005d6c01  mov     ebx, [rax+18h]
0x1005d6c04  mov     rbp, [rax+10h]
0x1005d6c08  call    cs:qword_100715058
0x1005d6c0e  test    rbx, rbx
0x1005d6c11  jz      short loc_1005D6C6F
0x1005d6c13  movzx   ecx, cs:word_10078FA84
0x1005d6c1a  mov     edx, 3FFh
0x1005d6c1f  and     cx, dx
0x1005d6c22  mov     dword ptr [rsp+0AA8h+lpBuffer], 200h
0x1005d6c2a  lea     r9, [rsp+0AA8h+var_438]
0x1005d6c32  mov     r8d, 4E6h
0x1005d6c38  mov     edx, eax
0x1005d6c3a  call    cs:qword_1007152E0
0x1005d6c40  lfence
0x1005d6c43  mov     qword ptr [rsp+0AA8h+nSize], rsi
0x1005d6c48  lea     r9, [rsp+0AA8h+FileName]
0x1005d6c4d  mov     edx, ebx; unsigned __int64
0x1005d6c4f  mov     rcx, rbp; Buffer
0x1005d6c52  mov     dword ptr [rsp+0AA8h+lpBuffer], edi
0x1005d6c56  test    eax, eax
0x1005d6c58  lea     r8, [rsp+0AA8h+var_438]
0x1005d6c60  jnz     short loc_1005D6C69
0x1005d6c62  lea     r8, aFailedToCreate_5; "Failed to create or write to file '%ws'"...
0x1005d6c69  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1005d6c6e  nop
0x1005d6c6f  mov     rcx, qword ptr [rsp+0AA8h+Buffer]; hMem
0x1005d6c74  test    rcx, rcx
0x1005d6c77  jz      short loc_1005D6C7F
0x1005d6c79  call    cs:__imp_LocalFree
0x1005d6c7f  xor     eax, eax
0x1005d6c81  jmp     short loc_1005D6C88
0x1005d6c83  mov     eax, 1
0x1005d6c88  mov     rcx, [rsp+0AA8h+var_38]
0x1005d6c90  xor     rcx, rsp; StackCookie
0x1005d6c93  call    __security_check_cookie
0x1005d6c98  add     rsp, 0A88h
0x1005d6c9f  pop     rdi
0x1005d6ca0  pop     rsi
0x1005d6ca1  pop     rbp
0x1005d6ca2  pop     rbx
0x1005d6ca3  retn
```
