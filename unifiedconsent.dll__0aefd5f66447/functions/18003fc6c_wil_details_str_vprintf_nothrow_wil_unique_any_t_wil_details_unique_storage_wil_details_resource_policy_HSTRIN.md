# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x18003fc6c`
- end: `0x18003fe7e`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003fbf8`

## callees

- `0x18000339c`
- `0x1800033f0`
- `0x18000c784`
- `0x18000e460`
- `0x18003fc6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fdac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fdac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fdc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fe4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fdc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fe4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18003fcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18003fcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18003fd58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18003fd58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003fdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003fe3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003fdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003fe3f`

## string_xrefs

- `0x18003fcc7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003fe27`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003fe69`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *a1,
        const wchar_t *a2,
        va_list *a3)
{
  signed int v6; // eax
  size_t v7; // rdi
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  size_t v11; // rbx
  WCHAR *v12; // rdi
  unsigned __int64 v13; // rsi
  int v14; // eax
  HSTRING_BUFFER v15; // rax
  HRESULT v16; // eax
  HSTRING v17; // rcx
  HSTRING v18; // rbx
  HSTRING v19; // rsi
  DWORD LastError; // edi
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  HSTRING v23; // [rsp+28h] [rbp-18h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-10h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v6 = vscwprintf(a2, *a3);
  v7 = v6;
  charBuffer = 0;
  v23 = 0;
  bufferHandle = 0;
  v8 = WindowsPreallocateStringBuffer(v6, &charBuffer, &bufferHandle);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156A,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      (int)string);
    v10 = 1997;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v9,
      (int)string);
    if ( bufferHandle )
      WindowsDeleteStringBuffer(bufferHandle);
    if ( v23 )
      WindowsDeleteString(v23);
    return v9;
  }
  v11 = v7;
  v12 = charBuffer;
  v13 = v11 + 1;
  if ( v11 == -1 )
  {
    v9 = -2147024809;
    if ( v13 )
      goto LABEL_28;
LABEL_29:
    v10 = 2001;
    goto LABEL_30;
  }
  if ( v13 > 0x7FFFFFFF )
  {
    v9 = -2147024809;
LABEL_28:
    *v12 = 0;
    goto LABEL_29;
  }
  v14 = vsnwprintf(charBuffer, v11, a2, *a3);
  if ( v14 < 0 || v14 > v11 )
  {
    v12[v11] = 0;
    v9 = -2147024774;
    if ( (v13 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_28;
    goto LABEL_29;
  }
  if ( v14 == v11 )
    v12[v11] = 0;
  v15 = bufferHandle;
  charBuffer = 0;
  if ( bufferHandle )
  {
    string = 0;
    v16 = WindowsPromoteStringBuffer(bufferHandle, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x152F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v16,
        (int)string);
    v17 = string;
    v15 = 0;
    bufferHandle = 0;
  }
  else
  {
    v17 = v23;
    string = v23;
    v23 = 0;
  }
  v18 = v17;
  if ( a1 == &string )
  {
    if ( v17 )
    {
      WindowsDeleteString(v17);
      v15 = bufferHandle;
    }
  }
  else
  {
    v19 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      WindowsDeleteString(v19);
      SetLastError(LastError);
      v15 = bufferHandle;
    }
    *a1 = v18;
    string = 0;
  }
  if ( v15 )
    WindowsDeleteStringBuffer(v15);
  if ( v23 )
    WindowsDeleteString(v23);
  return 0;
}

```

## disassembly

```asm
0x18003fc6c  push    rbp
0x18003fc6e  push    rbx
0x18003fc6f  push    rsi
0x18003fc70  push    rdi
0x18003fc71  push    r12
0x18003fc73  push    r14
0x18003fc75  push    r15
0x18003fc77  mov     rbp, rsp
0x18003fc7a  sub     rsp, 40h
0x18003fc7e  mov     r12, rdx
0x18003fc81  mov     r14, rcx
0x18003fc84  mov     rdx, [r8]; ArgList
0x18003fc87  mov     rcx, r12; Format
0x18003fc8a  mov     r15, r8
0x18003fc8d  call    _vscwprintf
0x18003fc92  movsxd  rdi, eax
0x18003fc95  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18003fc99  mov     ecx, edi; length
0x18003fc9b  mov     [rbp+charBuffer], 0
0x18003fca3  lea     rdx, [rbp+charBuffer]; charBuffer
0x18003fca7  mov     [rbp+var_18], 0
0x18003fcaf  mov     [rbp+bufferHandle], 0
0x18003fcb7  call    cs:__imp_WindowsPreallocateStringBuffer
0x18003fcbd  mov     ebx, eax
0x18003fcbf  test    eax, eax
0x18003fcc1  jns     short loc_18003FCE5
0x18003fcc3  mov     rcx, [rbp+38h]; this
0x18003fcc7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003fcce  mov     r9d, eax; char *
0x18003fcd1  mov     edx, 156Ah; void *
0x18003fcd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fcdb  mov     edx, 7CDh
0x18003fce0  jmp     loc_18003FE23
0x18003fce5  mov     rbx, rdi
0x18003fce8  mov     rdi, [rbp+charBuffer]
0x18003fcec  lea     rsi, [rbx+1]
0x18003fcf0  test    rsi, rsi
0x18003fcf3  jz      loc_18003FE0F
0x18003fcf9  cmp     rsi, 7FFFFFFFh
0x18003fd00  jbe     short loc_18003FD0C
0x18003fd02  mov     ebx, 80070057h
0x18003fd07  jmp     loc_18003FE19
0x18003fd0c  mov     r9, [r15]; Args
0x18003fd0f  mov     r8, r12; Format
0x18003fd12  mov     rdx, rbx; BufferCount
0x18003fd15  mov     rcx, rdi; Buffer
0x18003fd18  call    _vsnwprintf
0x18003fd1d  test    eax, eax
0x18003fd1f  js      loc_18003FDF3
0x18003fd25  cdqe
0x18003fd27  cmp     rax, rbx
0x18003fd2a  ja      loc_18003FDF3
0x18003fd30  jnz     short loc_18003FD38
0x18003fd32  xor     eax, eax
0x18003fd34  mov     [rdi+rbx*2], ax
0x18003fd38  mov     rax, [rbp+bufferHandle]
0x18003fd3c  mov     [rbp+charBuffer], 0
0x18003fd44  test    rax, rax
0x18003fd47  jz      short loc_18003FD72
0x18003fd49  lea     rdx, [rbp+string]; string
0x18003fd4d  mov     [rbp+string], 0
0x18003fd55  mov     rcx, rax; bufferHandle
0x18003fd58  call    cs:__imp_WindowsPromoteStringBuffer
0x18003fd5e  test    eax, eax
0x18003fd60  js      loc_18003FE65
0x18003fd66  mov     rcx, [rbp+string]
0x18003fd6a  xor     eax, eax
0x18003fd6c  mov     [rbp+bufferHandle], rax
0x18003fd70  jmp     short loc_18003FD82
0x18003fd72  mov     rcx, [rbp+var_18]; string
0x18003fd76  mov     [rbp+string], rcx
0x18003fd7a  mov     [rbp+var_18], 0
0x18003fd82  lea     r8, [rbp+string]
0x18003fd86  mov     rbx, rcx
0x18003fd89  mov     rdx, rcx
0x18003fd8c  cmp     r14, r8
0x18003fd8f  jz      short loc_18003FDC3
0x18003fd91  mov     rsi, [r14]
0x18003fd94  test    rsi, rsi
0x18003fd97  jz      short loc_18003FDB6
0x18003fd99  call    cs:__imp_GetLastError
0x18003fd9f  mov     rcx, rsi; string
0x18003fda2  mov     edi, eax
0x18003fda4  call    cs:__imp_WindowsDeleteString
0x18003fdaa  mov     ecx, edi; dwErrCode
0x18003fdac  call    cs:__imp_SetLastError
0x18003fdb2  mov     rax, [rbp+bufferHandle]
0x18003fdb6  mov     [r14], rbx
0x18003fdb9  mov     [rbp+string], 0
0x18003fdc1  jmp     short loc_18003FDD2
0x18003fdc3  test    rdx, rdx
0x18003fdc6  jz      short loc_18003FDD2
0x18003fdc8  call    cs:__imp_WindowsDeleteString
0x18003fdce  mov     rax, [rbp+bufferHandle]
0x18003fdd2  test    rax, rax
0x18003fdd5  jz      short loc_18003FDE0
0x18003fdd7  mov     rcx, rax; bufferHandle
0x18003fdda  call    cs:__imp_WindowsDeleteStringBuffer
0x18003fde0  mov     rcx, [rbp+var_18]; string
0x18003fde4  test    rcx, rcx
0x18003fde7  jz      short loc_18003FDEF
0x18003fde9  call    cs:__imp_WindowsDeleteString
0x18003fdef  xor     eax, eax
0x18003fdf1  jmp     short loc_18003FE56
0x18003fdf3  xor     eax, eax
0x18003fdf5  mov     [rdi+rbx*2], ax
0x18003fdf9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003fe03  mov     ebx, 8007007Ah
0x18003fe08  test    rax, rsi
0x18003fe0b  jbe     short loc_18003FE1E
0x18003fe0d  jmp     short loc_18003FE19
0x18003fe0f  mov     ebx, 80070057h
0x18003fe14  test    rsi, rsi
0x18003fe17  jz      short loc_18003FE1E
0x18003fe19  xor     eax, eax
0x18003fe1b  mov     [rdi], ax
0x18003fe1e  mov     edx, 7D1h; void *
0x18003fe23  mov     rcx, [rbp+38h]; this
0x18003fe27  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003fe2e  mov     r9d, ebx; char *
0x18003fe31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe36  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18003fe3a  test    rcx, rcx
0x18003fe3d  jz      short loc_18003FE45
0x18003fe3f  call    cs:__imp_WindowsDeleteStringBuffer
0x18003fe45  mov     rcx, [rbp+var_18]; string
0x18003fe49  test    rcx, rcx
0x18003fe4c  jz      short loc_18003FE54
0x18003fe4e  call    cs:__imp_WindowsDeleteString
0x18003fe54  mov     eax, ebx
0x18003fe56  add     rsp, 40h
0x18003fe5a  pop     r15
0x18003fe5c  pop     r14
0x18003fe5e  pop     r12
0x18003fe60  pop     rdi
0x18003fe61  pop     rsi
0x18003fe62  pop     rbx
0x18003fe63  pop     rbp
0x18003fe64  retn
0x18003fe65  mov     rcx, [rbp+38h]; this
0x18003fe69  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003fe70  mov     r9d, eax; char *
0x18003fe73  mov     edx, 152Fh; void *
0x18003fe78  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
