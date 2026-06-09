# wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)

- ea: `0x180020620`
- end: `0x180020714`
- name: `?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `39`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e9f8`
- `0x18001ef40`
- `0x180020840`
- `0x180020d90`
- `0x180021750`
- `0x18002eb80`
- `0x18002f450`
- `0x18002fc10`
- `0x180033800`
- `0x180054240`
- `0x180057580`
- `0x1800586a8`
- `0x18005a26c`
- `0x180069a40`
- `0x18006b0c0`
- `0x1800803f0`
- `0x180083f90`
- `0x1800845d0`
- `0x180084d40`
- `0x1800864b4`
- `0x180086a40`
- `0x180087800`
- `0x180089730`
- `0x18008b9a0`
- `0x18008be40`
- `0x18008c150`
- `0x18008c410`
- `0x18008c7d0`
- `0x18008d0b0`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800aef20`
- `0x1800ca920`
- `0x1800ccf00`
- `0x1800cd8f0`
- `0x1800d1cc0`
- `0x1800d2e90`
- `0x1800d3158`
- `0x1800d4e70`

## callees

- `0x180020620`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002068f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002069e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002068f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002069e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020709`

## pseudocode

```c
void __fastcall wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        _QWORD **a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  char *v3; // rcx
  void *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  HSTRING v12; // rcx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    v3 = (char *)v2[39];
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
    v4 = (void *)v2[38];
    if ( v4 )
      CloseHandle(v4);
    v5 = (char *)v2[37];
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    v6 = (char *)v2[36];
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    v7 = (HSTRING)v2[9];
    if ( v7 )
      WindowsDeleteString(v7);
    v8 = (HSTRING)v2[8];
    if ( v8 )
      WindowsDeleteString(v8);
    v9 = (HSTRING)v2[7];
    if ( v9 )
      WindowsDeleteString(v9);
    v10 = (HSTRING)v2[6];
    if ( v10 )
      WindowsDeleteString(v10);
    v11 = (HSTRING)v2[5];
    if ( v11 )
      WindowsDeleteString(v11);
    v12 = (HSTRING)v2[4];
    if ( v12 )
      WindowsDeleteString(v12);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180020620  push    rbx
0x180020622  sub     rsp, 20h
0x180020626  mov     rbx, [rcx]
0x180020629  mov     [rcx], rdx
0x18002062c  test    rbx, rbx
0x18002062f  jz      loc_1800206ED
0x180020635  mov     rcx, [rbx+138h]; hObject
0x18002063c  lea     rax, [rcx-1]
0x180020640  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020644  jbe     loc_1800206F3
0x18002064a  mov     rcx, [rbx+130h]; hObject
0x180020651  test    rcx, rcx
0x180020654  jz      short loc_18002065C
0x180020656  call    cs:__imp_CloseHandle
0x18002065c  mov     rcx, [rbx+128h]; hObject
0x180020663  lea     rax, [rcx-1]
0x180020667  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002066b  jbe     loc_1800206FE
0x180020671  mov     rcx, [rbx+120h]; hObject
0x180020678  lea     rax, [rcx-1]
0x18002067c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020680  jbe     loc_180020709
0x180020686  mov     rcx, [rbx+48h]; string
0x18002068a  test    rcx, rcx
0x18002068d  jz      short loc_180020695
0x18002068f  call    cs:__imp_WindowsDeleteString
0x180020695  mov     rcx, [rbx+40h]; string
0x180020699  test    rcx, rcx
0x18002069c  jz      short loc_1800206A4
0x18002069e  call    cs:__imp_WindowsDeleteString
0x1800206a4  mov     rcx, [rbx+38h]; string
0x1800206a8  test    rcx, rcx
0x1800206ab  jz      short loc_1800206B3
0x1800206ad  call    cs:__imp_WindowsDeleteString
0x1800206b3  mov     rcx, [rbx+30h]; string
0x1800206b7  test    rcx, rcx
0x1800206ba  jz      short loc_1800206C2
0x1800206bc  call    cs:__imp_WindowsDeleteString
0x1800206c2  mov     rcx, [rbx+28h]; string
0x1800206c6  test    rcx, rcx
0x1800206c9  jz      short loc_1800206D1
0x1800206cb  call    cs:__imp_WindowsDeleteString
0x1800206d1  mov     rcx, [rbx+20h]; string
0x1800206d5  test    rcx, rcx
0x1800206d8  jz      short loc_1800206E0
0x1800206da  call    cs:__imp_WindowsDeleteString
0x1800206e0  mov     edx, 140h
0x1800206e5  mov     rcx, rbx; Block
0x1800206e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800206ed  add     rsp, 20h
0x1800206f1  pop     rbx
0x1800206f2  retn
0x1800206f3  call    cs:__imp_CloseHandle
0x1800206f9  jmp     loc_18002064A
0x1800206fe  call    cs:__imp_CloseHandle
0x180020704  jmp     loc_180020671
0x180020709  call    cs:__imp_CloseHandle
0x18002070f  jmp     loc_180020686
```
