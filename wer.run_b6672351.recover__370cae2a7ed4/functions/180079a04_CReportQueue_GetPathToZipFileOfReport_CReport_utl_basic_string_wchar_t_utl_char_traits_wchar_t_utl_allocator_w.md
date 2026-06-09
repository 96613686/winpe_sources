# CReportQueue::GetPathToZipFileOfReport(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180079a04`
- end: `0x180079bee`
- name: `?GetPathToZipFileOfReport@CReportQueue@@QEAAJPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18003cef0`

## callees

- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180025560`
- `0x18003fb94`
- `0x180040814`
- `0x1800479ac`
- `0x18004dfbc`
- `0x180051244`
- `0x180079a04`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079b19`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079b64`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079b19`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079b64`

## string_xrefs

- `0x180079a28`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079a6c`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079af1`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079b4a`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079b7c`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079bc0`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

## pseudocode

```c
__int64 __fastcall CReportQueue::GetPathToZipFileOfReport(wchar_t *a1, CReport *a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int UniqueIdentifier; // eax
  wchar_t *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  LPCWSTR pszPath[4]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  wchar_t *v16; // [rsp+90h] [rbp+28h] BYREF

  v16 = a1;
  if ( a2 )
  {
    if ( !a3 )
    {
      v5 = 235;
      goto LABEL_3;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
    UniqueIdentifier = CReport::GetUniqueIdentifier(a2, v14);
    v6 = UniqueIdentifier;
    if ( UniqueIdentifier < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)UniqueIdentifier,
        (int)pszPath[0]);
LABEL_22:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v14);
      return v6;
    }
    v16 = 0;
    if ( ((int)CReport::GetStorePath(a2, (const wchar_t **)&v16) < 0 || (v8 = v16) == 0)
      && ((int)CReport::GetReservedStorePath(a2, (const wchar_t **)&v16) < 0 || (v8 = v16) == 0) )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xFA,
             (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
             (const char *)3,
             (unsigned int)pszPath[0]);
      goto LABEL_22;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pszPath);
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           pszPath,
           L"%s\\%s.zip",
           v8,
           v14[0]);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v9,
        (int)pszPath[0]);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
      v6 = v10;
      goto LABEL_22;
    }
    if ( !PathFileExistsW(pszPath[0]) )
    {
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              pszPath,
              L"%s\\%s.cab",
              v8,
              v14[0]);
      v6 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
          (const char *)(unsigned int)v11,
          (int)pszPath[0]);
LABEL_19:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
        goto LABEL_22;
      }
      if ( !PathFileExistsW(pszPath[0]) )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x107,
               (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
               (const char *)2,
               (unsigned int)pszPath[0]);
        goto LABEL_19;
      }
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a3, pszPath);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v14);
    return 0;
  }
  v5 = 234;
LABEL_3:
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
    (const char *)0x80070057LL,
    (int)pszPath[0]);
  return v6;
}

```

## disassembly

```asm
0x180079a04  mov     [rsp-20h+arg_0], rcx
0x180079a09  push    rbp
0x180079a0a  push    rbx
0x180079a0b  push    rsi
0x180079a0c  push    rdi
0x180079a0d  mov     rbp, rsp
0x180079a10  sub     rsp, 68h
0x180079a14  mov     rsi, r8
0x180079a17  mov     rdi, rdx
0x180079a1a  test    rdx, rdx
0x180079a1d  jnz     short loc_180079A41
0x180079a1f  mov     edx, 0EAh; void *
0x180079a24  mov     rcx, [rbp+20h]; this
0x180079a28  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079a2f  mov     ebx, 80070057h
0x180079a34  mov     r9d, ebx; char *
0x180079a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079a3c  jmp     loc_180079BE2
0x180079a41  test    rsi, rsi
0x180079a44  jnz     short loc_180079A4D
0x180079a46  mov     edx, 0EBh
0x180079a4b  jmp     short loc_180079A24
0x180079a4d  lea     rcx, [rbp+var_28]; void *
0x180079a51  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079a56  lea     rdx, [rbp+var_28]
0x180079a5a  mov     rcx, rdi
0x180079a5d  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180079a62  mov     ebx, eax
0x180079a64  test    eax, eax
0x180079a66  jns     short loc_180079A85
0x180079a68  mov     rcx, [rbp+20h]; this
0x180079a6c  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079a73  mov     r9d, eax; char *
0x180079a76  mov     edx, 0F1h; void *
0x180079a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079a80  jmp     loc_180079BD9
0x180079a85  lea     rdx, [rbp+arg_0]; wchar_t **
0x180079a89  mov     [rbp+arg_0], 0
0x180079a91  mov     rcx, rdi; this
0x180079a94  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x180079a99  test    eax, eax
0x180079a9b  js      short loc_180079AA6
0x180079a9d  mov     rbx, [rbp+arg_0]
0x180079aa1  test    rbx, rbx
0x180079aa4  jnz     short loc_180079AC7
0x180079aa6  lea     rdx, [rbp+arg_0]; wchar_t **
0x180079aaa  mov     rcx, rdi; this
0x180079aad  call    ?GetReservedStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetReservedStorePath(wchar_t const * *)
0x180079ab2  test    eax, eax
0x180079ab4  js      loc_180079BBC
0x180079aba  mov     rbx, [rbp+arg_0]
0x180079abe  test    rbx, rbx
0x180079ac1  jz      loc_180079BBC
0x180079ac7  lea     rcx, [rbp+pszPath]; void *
0x180079acb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079ad0  mov     r9, [rbp+var_28]
0x180079ad4  lea     rdx, aSSZip; "%s\\%s.zip"
0x180079adb  mov     r8, rbx
0x180079ade  lea     rcx, [rbp+pszPath]
0x180079ae2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180079ae7  mov     edi, eax
0x180079ae9  test    eax, eax
0x180079aeb  jns     short loc_180079B15
0x180079aed  mov     rcx, [rbp+20h]; this
0x180079af1  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079af8  mov     r9d, eax; char *
0x180079afb  mov     edx, 0FFh; void *
0x180079b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b05  lea     rcx, [rbp+pszPath]; void *
0x180079b09  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079b0e  mov     ebx, edi
0x180079b10  jmp     loc_180079BD9
0x180079b15  mov     rcx, [rbp+pszPath]; pszPath
0x180079b19  call    cs:__imp_PathFileExistsW
0x180079b20  nop     dword ptr [rax+rax+00h]
0x180079b25  test    eax, eax
0x180079b27  jnz     short loc_180079B9A
0x180079b29  mov     r9, [rbp+var_28]
0x180079b2d  lea     rdx, aSSCab_0; "%s\\%s.cab"
0x180079b34  mov     r8, rbx
0x180079b37  lea     rcx, [rbp+pszPath]
0x180079b3b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180079b40  mov     ebx, eax
0x180079b42  test    eax, eax
0x180079b44  jns     short loc_180079B60
0x180079b46  mov     rcx, [rbp+20h]; this
0x180079b4a  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079b51  mov     r9d, eax; char *
0x180079b54  mov     edx, 103h; void *
0x180079b59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b5e  jmp     short loc_180079B8F
0x180079b60  mov     rcx, [rbp+pszPath]; pszPath
0x180079b64  call    cs:__imp_PathFileExistsW
0x180079b6b  nop     dword ptr [rax+rax+00h]
0x180079b70  test    eax, eax
0x180079b72  jnz     short loc_180079B9A
0x180079b74  mov     rcx, [rbp+20h]; this
0x180079b78  lea     r9d, [rax+2]; char *
0x180079b7c  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079b83  mov     edx, 107h; void *
0x180079b88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180079b8d  mov     ebx, eax
0x180079b8f  lea     rcx, [rbp+pszPath]; void *
0x180079b93  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079b98  jmp     short loc_180079BD9
0x180079b9a  lea     rdx, [rbp+pszPath]
0x180079b9e  mov     rcx, rsi
0x180079ba1  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180079ba6  lea     rcx, [rbp+pszPath]; void *
0x180079baa  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079baf  lea     rcx, [rbp+var_28]; void *
0x180079bb3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079bb8  xor     eax, eax
0x180079bba  jmp     short loc_180079BE4
0x180079bbc  mov     rcx, [rbp+20h]; this
0x180079bc0  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079bc7  mov     r9d, 3; char *
0x180079bcd  mov     edx, 0FAh; void *
0x180079bd2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180079bd7  mov     ebx, eax
0x180079bd9  lea     rcx, [rbp+var_28]; void *
0x180079bdd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079be2  mov     eax, ebx
0x180079be4  add     rsp, 68h
0x180079be8  pop     rdi
0x180079be9  pop     rsi
0x180079bea  pop     rbx
0x180079beb  pop     rbp
0x180079bec  retn
```
