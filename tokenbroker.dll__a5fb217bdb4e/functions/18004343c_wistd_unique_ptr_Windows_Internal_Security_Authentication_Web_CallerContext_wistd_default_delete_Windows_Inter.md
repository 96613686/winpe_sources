# wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::~unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>(void)

- ea: `0x18004343c`
- end: `0x180043534`
- name: `??1?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAA@XZ`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021750`
- `0x180114e10`
- `0x180114e30`
- `0x180114f90`
- `0x180115768`
- `0x180115864`
- `0x18011605b`
- `0x1801160e2`
- `0x180116a72`
- `0x1801180fa`
- `0x180119119`

## callees

- `0x18004343c`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004351e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004351e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043529`

## pseudocode

```c
void __fastcall wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::~unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  char *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    v2 = (char *)v1[39];
    if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v2);
    v3 = (void *)v1[38];
    if ( v3 )
      CloseHandle(v3);
    v4 = (char *)v1[37];
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    v5 = (char *)v1[36];
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    v6 = (HSTRING)v1[9];
    if ( v6 )
      WindowsDeleteString(v6);
    v7 = (HSTRING)v1[8];
    if ( v7 )
      WindowsDeleteString(v7);
    v8 = (HSTRING)v1[7];
    if ( v8 )
      WindowsDeleteString(v8);
    v9 = (HSTRING)v1[6];
    if ( v9 )
      WindowsDeleteString(v9);
    v10 = (HSTRING)v1[5];
    if ( v10 )
      WindowsDeleteString(v10);
    v11 = (HSTRING)v1[4];
    if ( v11 )
      WindowsDeleteString(v11);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18004343c  push    rbx
0x18004343e  sub     rsp, 20h
0x180043442  mov     rbx, [rcx]
0x180043445  mov     qword ptr [rcx], 0
0x18004344c  test    rbx, rbx
0x18004344f  jz      loc_18004350D
0x180043455  mov     rcx, [rbx+138h]; hObject
0x18004345c  lea     rax, [rcx-1]
0x180043460  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043464  jbe     loc_180043513
0x18004346a  mov     rcx, [rbx+130h]; hObject
0x180043471  test    rcx, rcx
0x180043474  jz      short loc_18004347C
0x180043476  call    cs:__imp_CloseHandle
0x18004347c  mov     rcx, [rbx+128h]; hObject
0x180043483  lea     rax, [rcx-1]
0x180043487  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004348b  jbe     loc_18004351E
0x180043491  mov     rcx, [rbx+120h]; hObject
0x180043498  lea     rax, [rcx-1]
0x18004349c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800434a0  jbe     loc_180043529
0x1800434a6  mov     rcx, [rbx+48h]; string
0x1800434aa  test    rcx, rcx
0x1800434ad  jz      short loc_1800434B5
0x1800434af  call    cs:__imp_WindowsDeleteString
0x1800434b5  mov     rcx, [rbx+40h]; string
0x1800434b9  test    rcx, rcx
0x1800434bc  jz      short loc_1800434C4
0x1800434be  call    cs:__imp_WindowsDeleteString
0x1800434c4  mov     rcx, [rbx+38h]; string
0x1800434c8  test    rcx, rcx
0x1800434cb  jz      short loc_1800434D3
0x1800434cd  call    cs:__imp_WindowsDeleteString
0x1800434d3  mov     rcx, [rbx+30h]; string
0x1800434d7  test    rcx, rcx
0x1800434da  jz      short loc_1800434E2
0x1800434dc  call    cs:__imp_WindowsDeleteString
0x1800434e2  mov     rcx, [rbx+28h]; string
0x1800434e6  test    rcx, rcx
0x1800434e9  jz      short loc_1800434F1
0x1800434eb  call    cs:__imp_WindowsDeleteString
0x1800434f1  mov     rcx, [rbx+20h]; string
0x1800434f5  test    rcx, rcx
0x1800434f8  jz      short loc_180043500
0x1800434fa  call    cs:__imp_WindowsDeleteString
0x180043500  mov     edx, 140h
0x180043505  mov     rcx, rbx; Block
0x180043508  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004350d  add     rsp, 20h
0x180043511  pop     rbx
0x180043512  retn
0x180043513  call    cs:__imp_CloseHandle
0x180043519  jmp     loc_18004346A
0x18004351e  call    cs:__imp_CloseHandle
0x180043524  jmp     loc_180043491
0x180043529  call    cs:__imp_CloseHandle
0x18004352f  jmp     loc_1800434A6
```
