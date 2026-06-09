# StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)

- ea: `0x18007c510`
- end: `0x18007c805`
- name: `?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z`
- size: `757`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ced8`
- `0x18007b390`
- `0x18017d590`
- `0x18021dda8`
- `0x180317cb0`
- `0x180439400`

## callees

- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007c510`
- `0x18007f9a0`
- `0x18007fd1c`
- `0x1800d1d80`
- `0x1803b1f60`

## import_xrefs

- `ntdll!RtlAreLongPathsEnabled` at `0x18007c5c0`
- `ntdll!RtlAreLongPathsEnabled` at `0x18007c5c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007c78e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007c78e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c7ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c7ab`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18007c776`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18007c776`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18007c7cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18007c7cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x18007c6bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x18007c6bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c6f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007c58f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007c62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007c58f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007c62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18007c561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18007c561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c57d`

## string_xrefs

- `0x18007c601`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007c675`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007c53f`: `ValidateCanonicalPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageItemHelpers::ValidateCanonicalPath(HSTRING a1, char a2)
{
  wchar_t *StringRawBuffer; // rbp
  UINT32 StringLen; // ebx
  int v6; // esi
  WCHAR *v7; // rbx
  UINT32 v9; // ebx
  int v10; // edi
  __int64 v11; // rcx
  int v12; // ecx
  LPVOID pv; // [rsp+20h] [rbp-128h] BYREF
  BOOL hasEmbedNull[2]; // [rsp+28h] [rbp-120h] BYREF
  _BYTE v15[192]; // [rsp+30h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  WinRTStorageTelemetry::WatchCurrentThread(v15, "ValidateCanonicalPath", 0);
  hasEmbedNull[0] = 0;
  WindowsStringHasEmbeddedNull(a1, hasEmbedNull);
  if ( hasEmbedNull[0] )
  {
    v6 = -2147024809;
  }
  else
  {
    StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(a1, 0);
    StringLen = WindowsGetStringLen(a1);
    v6 = 0;
    if ( !StringLen )
      v6 = -2147024809;
    CheckAndReportError(v6, 0xC629u);
    if ( StringLen )
    {
      if ( (unsigned __int8)RtlAreLongPathsEnabled() )
        goto LABEL_6;
      v9 = WindowsGetStringLen(a1);
      v6 = 0;
      if ( v9 >= 0x104 )
        v6 = -2147024690;
      CheckAndReportErrorForPath(v6, 0xC62Au, StringRawBuffer, 260);
      if ( v9 < 0x104 )
      {
LABEL_6:
        wil::make_cotaskmem_string_nothrow((wil *)&pv, StringRawBuffer, 0xFFFFFFFFFFFFFFFFuLL);
        v7 = (WCHAR *)pv;
        if ( !pv )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1FE6,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
            (const char *)0x8007000ELL,
            0);
          StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v15);
          return 2147942414LL;
        }
        v10 = 0;
        if ( v6 >= 0 )
        {
          while ( 1 )
          {
            v11 = v7[v10];
            if ( !(_WORD)v11 )
              break;
            if ( (_WORD)v11 == 47 )
            {
              if ( (a2 & 2) != 0 )
              {
                v6 = 0;
                v7[v10] = 92;
              }
              else
              {
                v6 = -2147024735;
              }
              ++v10;
              if ( v6 < 0 )
                break;
            }
            else
            {
              if ( !(unsigned int)PathIsValidCharW(v11, 508) )
              {
                v6 = -2147024735;
                v12 = -2147024735;
                goto LABEL_18;
              }
              v6 = 0;
              ++v10;
            }
          }
        }
        CheckAndReportErrorForPath(v6, 0xC62Au, StringRawBuffer, 260);
        if ( v6 >= 0 )
        {
          *(_QWORD *)hasEmbedNull = 0;
          if ( PathAllocCanonicalize(v7, 1u, (PWSTR *)hasEmbedNull) < 0 || StrCmpICW(*(LPCWSTR *)hasEmbedNull, v7) )
            v6 = -2147024809;
          else
            v6 = 0;
          if ( *(_QWORD *)hasEmbedNull )
            LocalFree(*(HLOCAL *)hasEmbedNull);
          if ( v6 >= 0 && (a2 & 1) == 0 && PathIsRelativeW(v7) )
          {
            v6 = -2147024809;
            v12 = -2147024809;
LABEL_18:
            CheckAndReportErrorForPath(v12, 0xC62Au, StringRawBuffer, 260);
          }
        }
        CoTaskMemFree(v7);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FE2,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
          (const char *)(unsigned int)v6,
          (int)pv);
      }
    }
  }
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007c510  push    rbx
0x18007c512  push    rbp
0x18007c513  push    rsi
0x18007c514  push    rdi
0x18007c515  push    r12
0x18007c517  push    r13
0x18007c519  push    r14
0x18007c51b  push    r15
0x18007c51d  sub     rsp, 108h
0x18007c524  mov     rax, cs:__security_cookie
0x18007c52b  xor     rax, rsp
0x18007c52e  mov     [rsp+148h+var_58], rax
0x18007c536  mov     r15d, edx
0x18007c539  mov     rdi, rcx
0x18007c53c  xor     r8d, r8d
0x18007c53f  lea     rdx, aValidatecanoni; "ValidateCanonicalPath"
0x18007c546  lea     rcx, [rsp+148h+var_118]
0x18007c54b  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x18007c550  nop
0x18007c551  xor     r12d, r12d
0x18007c554  mov     [rsp+148h+hasEmbedNull], r12d
0x18007c559  lea     rdx, [rsp+148h+hasEmbedNull]; hasEmbedNull
0x18007c55e  mov     rcx, rdi; string
0x18007c561  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18007c568  nop     dword ptr [rax+rax+00h]
0x18007c56d  cmp     [rsp+148h+hasEmbedNull], r12d
0x18007c572  jnz     loc_18007C7FA
0x18007c578  xor     edx, edx; length
0x18007c57a  mov     rcx, rdi; string
0x18007c57d  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c584  nop     dword ptr [rax+rax+00h]
0x18007c589  mov     rbp, rax
0x18007c58c  mov     rcx, rdi; string
0x18007c58f  call    cs:__imp_WindowsGetStringLen
0x18007c596  nop     dword ptr [rax+rax+00h]
0x18007c59b  mov     ebx, eax
0x18007c59d  mov     esi, r12d
0x18007c5a0  mov     r14d, 80070057h
0x18007c5a6  test    eax, eax
0x18007c5a8  cmovz   esi, r14d
0x18007c5ac  mov     edx, 0C629h; unsigned int
0x18007c5b1  mov     ecx, esi; int
0x18007c5b3  call    ?CheckAndReportError@@YAJJIZZ; CheckAndReportError(long,uint,...)
0x18007c5b8  test    ebx, ebx
0x18007c5ba  jz      loc_18007C6FD
0x18007c5c0  call    cs:__imp_RtlAreLongPathsEnabled
0x18007c5c7  nop     dword ptr [rax+rax+00h]
0x18007c5cc  test    al, al
0x18007c5ce  jz      short loc_18007C627
0x18007c5d0  mov     r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18007c5d7  mov     rdx, rbp; unsigned __int16 *
0x18007c5da  lea     rcx, [rsp+148h+pv]; this
0x18007c5df  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18007c5e4  nop
0x18007c5e5  mov     rbx, [rsp+148h+pv]
0x18007c5ea  test    rbx, rbx
0x18007c5ed  jnz     loc_18007C688
0x18007c5f3  mov     rcx, [rsp+148h]; this
0x18007c5fb  mov     r9d, 8007000Eh; char *
0x18007c601  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18007c608  mov     edx, 1FE6h; void *
0x18007c60d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c612  nop
0x18007c613  lea     rcx, [rsp+148h+var_118]; this
0x18007c618  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007c61d  mov     eax, 8007000Eh
0x18007c622  jmp     loc_18007C709
0x18007c627  mov     rcx, rdi; string
0x18007c62a  call    cs:__imp_WindowsGetStringLen
0x18007c631  nop     dword ptr [rax+rax+00h]
0x18007c636  mov     ebx, eax
0x18007c638  mov     esi, r12d
0x18007c63b  mov     eax, 800700CEh
0x18007c640  cmp     ebx, 104h
0x18007c646  cmovnb  esi, eax
0x18007c649  mov     r9d, 104h
0x18007c64f  mov     r8, rbp; String1
0x18007c652  mov     edx, 0C62Ah; unsigned int
0x18007c657  mov     ecx, esi; int
0x18007c659  call    ?CheckAndReportErrorForPath@@YAJJIPEBGZZ; CheckAndReportErrorForPath(long,uint,ushort const *,...)
0x18007c65e  cmp     ebx, 104h
0x18007c664  jb      loc_18007C5D0
0x18007c66a  mov     rcx, [rsp+148h]; this
0x18007c672  mov     r9d, esi; char *
0x18007c675  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18007c67c  mov     edx, 1FE2h; void *
0x18007c681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c686  jmp     short loc_18007C6FD
0x18007c688  mov     edi, r12d
0x18007c68b  test    esi, esi
0x18007c68d  js      loc_18007C74B
0x18007c693  nop     dword ptr [rax+00h]
0x18007c697  nop     word ptr [rax+rax+00000000h]
0x18007c6a0  movsxd  rax, edi
0x18007c6a3  movzx   ecx, word ptr [rbx+rax*2]
0x18007c6a7  test    cx, cx
0x18007c6aa  jz      loc_18007C74B
0x18007c6b0  cmp     cx, 2Fh ; '/'
0x18007c6b4  jz      short loc_18007C72E
0x18007c6b6  mov     edx, 1FCh
0x18007c6bb  call    cs:__imp_PathIsValidCharW
0x18007c6c2  nop     dword ptr [rax+rax+00h]
0x18007c6c7  test    eax, eax
0x18007c6c9  jz      short loc_18007C6D2
0x18007c6cb  mov     esi, r12d
0x18007c6ce  inc     edi
0x18007c6d0  jmp     short loc_18007C6A0
0x18007c6d2  mov     esi, 800700A1h
0x18007c6d7  mov     ecx, esi; int
0x18007c6d9  mov     r9d, 104h
0x18007c6df  mov     r8, rbp; String1
0x18007c6e2  mov     edx, 0C62Ah; unsigned int
0x18007c6e7  call    ?CheckAndReportErrorForPath@@YAJJIPEBGZZ; CheckAndReportErrorForPath(long,uint,ushort const *,...)
0x18007c6ec  nop
0x18007c6ed  mov     rcx, rbx; pv
0x18007c6f0  call    cs:__imp_CoTaskMemFree
0x18007c6f7  nop     dword ptr [rax+rax+00h]
0x18007c6fc  nop
0x18007c6fd  lea     rcx, [rsp+148h+var_118]; this
0x18007c702  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007c707  mov     eax, esi
0x18007c709  mov     rcx, [rsp+148h+var_58]
0x18007c711  xor     rcx, rsp; StackCookie
0x18007c714  call    __security_check_cookie
0x18007c719  add     rsp, 108h
0x18007c720  pop     r15
0x18007c722  pop     r14
0x18007c724  pop     r13
0x18007c726  pop     r12
0x18007c728  pop     rdi
0x18007c729  pop     rsi
0x18007c72a  pop     rbp
0x18007c72b  pop     rbx
0x18007c72c  retn
0x18007c72e  test    r15b, 2
0x18007c732  jz      loc_18007C7F0
0x18007c738  mov     esi, r12d
0x18007c73b  mov     word ptr [rbx+rax*2], 5Ch ; '\'
0x18007c741  inc     edi
0x18007c743  test    esi, esi
0x18007c745  jns     loc_18007C6A0
0x18007c74b  mov     r9d, 104h
0x18007c751  mov     r8, rbp; String1
0x18007c754  mov     edx, 0C62Ah; unsigned int
0x18007c759  mov     ecx, esi; int
0x18007c75b  call    ?CheckAndReportErrorForPath@@YAJJIPEBGZZ; CheckAndReportErrorForPath(long,uint,ushort const *,...)
0x18007c760  test    esi, esi
0x18007c762  js      short loc_18007C6ED
0x18007c764  mov     qword ptr [rsp+148h+hasEmbedNull], r12
0x18007c769  lea     r8, [rsp+148h+hasEmbedNull]; ppszPathOut
0x18007c76e  mov     edx, 1; dwFlags
0x18007c773  mov     rcx, rbx; pszPathIn
0x18007c776  call    cs:__imp_PathAllocCanonicalize
0x18007c77d  nop     dword ptr [rax+rax+00h]
0x18007c782  test    eax, eax
0x18007c784  js      short loc_18007C7EB
0x18007c786  mov     rdx, rbx; pszStr2
0x18007c789  mov     rcx, qword ptr [rsp+148h+hasEmbedNull]; pszStr1
0x18007c78e  call    cs:__imp_StrCmpICW
0x18007c795  nop     dword ptr [rax+rax+00h]
0x18007c79a  test    eax, eax
0x18007c79c  jnz     short loc_18007C7EB
0x18007c79e  mov     esi, r12d
0x18007c7a1  mov     rcx, qword ptr [rsp+148h+hasEmbedNull]; hMem
0x18007c7a6  test    rcx, rcx
0x18007c7a9  jz      short loc_18007C7B7
0x18007c7ab  call    cs:__imp_LocalFree
0x18007c7b2  nop     dword ptr [rax+rax+00h]
0x18007c7b7  test    esi, esi
0x18007c7b9  js      loc_18007C6ED
0x18007c7bf  test    r15b, 1
0x18007c7c3  jnz     loc_18007C6ED
0x18007c7c9  mov     rcx, rbx; pszPath
0x18007c7cc  call    cs:__imp_PathIsRelativeW
0x18007c7d3  nop     dword ptr [rax+rax+00h]
0x18007c7d8  test    eax, eax
0x18007c7da  jz      loc_18007C6ED
0x18007c7e0  mov     esi, r14d
0x18007c7e3  mov     ecx, r14d
0x18007c7e6  jmp     loc_18007C6D9
0x18007c7eb  mov     esi, r14d
0x18007c7ee  jmp     short loc_18007C7A1
0x18007c7f0  mov     esi, 800700A1h
0x18007c7f5  jmp     loc_18007C741
0x18007c7fa  mov     esi, 80070057h
0x18007c7ff  jmp     loc_18007C6FD
```
