# ToastHelper::LoadStringResource(uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180030a2c`
- end: `0x180030b03`
- name: `?LoadStringResource@ToastHelper@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(UINT uID, LPWSTR lpBuffer)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002fc48`
- `0x1800303d0`
- `0x180030688`

## callees

- `0x180016644`
- `0x18001f038`
- `0x180030a2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030acb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180030a59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180030ac1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180030a59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180030ac1`

## string_xrefs

- `0x180030a81`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
__int64 __fastcall ToastHelper::LoadStringResource(UINT uID, WCHAR *lpBuffer)
{
  int StringW; // eax
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // edi
  const char *v10; // r9
  signed int v11; // eax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v14; // [rsp+48h] [rbp+20h] BYREF

  v14 = 0;
  StringW = LoadStringW(&_ImageBase, uID, (LPWSTR)&v14, 0);
  if ( StringW <= 0 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      return v6;
    v7 = 63;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
      (const char *)v6,
      v12);
    return v6;
  }
  try
  {
    v9 = StringW + 1;
    std::wstring::resize(lpBuffer, StringW + 1);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x46,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
                           v10);
  }
  if ( *((_QWORD *)lpBuffer + 3) > 7u )
    lpBuffer = *(WCHAR **)lpBuffer;
  if ( LoadStringW(&_ImageBase, uID, lpBuffer, v9) <= 0 )
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      return v6;
    v7 = 73;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180030a2c  mov     rax, rsp
0x180030a2f  mov     [rax+8], rbx
0x180030a33  mov     [rax+10h], rsi
0x180030a37  push    rdi; int
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbx, rdx
0x180030a3f  mov     esi, ecx
0x180030a41  mov     qword ptr [rax+20h], 0
0x180030a49  xor     r9d, r9d; cchBufferMax
0x180030a4c  lea     r8, [rax+20h]; lpBuffer
0x180030a50  mov     edx, ecx; uID
0x180030a52  lea     rcx, __ImageBase; hInstance
0x180030a59  call    cs:__imp_LoadStringW
0x180030a5f  test    eax, eax
0x180030a61  jg      short loc_180030A99
0x180030a63  call    cs:__imp_GetLastError
0x180030a69  mov     ebx, eax
0x180030a6b  test    eax, eax
0x180030a6d  jle     short loc_180030A78
0x180030a6f  movzx   ebx, ax
0x180030a72  or      ebx, 80070000h
0x180030a78  test    ebx, ebx
0x180030a7a  jns     short loc_180030A95
0x180030a7c  mov     edx, 3Fh ; '?'; void *
0x180030a81  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030a88  mov     r9d, ebx; char *
0x180030a8b  mov     rcx, [rsp+28h]; this
0x180030a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a95  mov     eax, ebx
0x180030a97  jmp     short loc_180030AF3
0x180030a99  lea     edi, [rax+1]
0x180030a9c  movsxd  rdx, edi
0x180030a9f  mov     rcx, rbx
0x180030aa2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180030aa7  nop
0x180030aa8  cmp     qword ptr [rbx+18h], 7
0x180030aad  jbe     short loc_180030AB2
0x180030aaf  mov     rbx, [rbx]
0x180030ab2  mov     r9d, edi; cchBufferMax
0x180030ab5  mov     r8, rbx; lpBuffer
0x180030ab8  mov     edx, esi; uID
0x180030aba  lea     rcx, __ImageBase; hInstance
0x180030ac1  call    cs:__imp_LoadStringW
0x180030ac7  test    eax, eax
0x180030ac9  jg      short loc_180030AEB
0x180030acb  call    cs:__imp_GetLastError
0x180030ad1  mov     ebx, eax
0x180030ad3  test    eax, eax
0x180030ad5  jle     short loc_180030AE0
0x180030ad7  movzx   ebx, ax
0x180030ada  or      ebx, 80070000h
0x180030ae0  test    ebx, ebx
0x180030ae2  jns     short loc_180030A95
0x180030ae4  mov     edx, 49h ; 'I'
0x180030ae9  jmp     short loc_180030A81
0x180030aeb  xor     eax, eax
0x180030aed  jmp     short loc_180030AF3
0x180030aef  mov     eax, [rsp+28h+arg_10]
0x180030af3  mov     rbx, [rsp+28h+arg_0]
0x180030af8  mov     rsi, [rsp+28h+arg_8]
0x180030afd  add     rsp, 20h
0x180030b01  pop     rdi
0x180030b02  retn
```
