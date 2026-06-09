# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,char const *,char * *)

- ea: `0x180041af8`
- end: `0x180041cb0`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEBDPEAPEAD@Z`
- size: `440`
- prototype: `int(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const char *, char **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003f6b4`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000b1bc`
- `0x18002d674`
- `0x18002ea14`
- `0x180041af8`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bd0`

## string_xrefs

- `0x180041bac`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x180041c42`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x180041c85`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JsonUtil::GetStringPropertyWithDefault(
        JsonUtil *this,
        struct ABI::Windows::Data::Json::IJsonObject *a2,
        wchar_t *a3,
        char *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(JsonUtil *, _QWORD, HSTRING *); // rbx
  __int64 v10; // rax
  const WCHAR *StringRawBuffer; // rax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  char *v15; // rcx
  int v17[8]; // [rsp+20h] [rbp-48h] BYREF
  char *v18; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v18 = (char *)a2;
  if ( !this )
  {
    v7 = 54;
LABEL_22:
    v8 = -2147024809;
    goto LABEL_23;
  }
  if ( !a2 || !*(_WORD *)a2 )
  {
    v7 = 55;
    goto LABEL_22;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v7 = 56;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
      (const char *)v8,
      v17[0]);
    return v8;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(JsonUtil *, _QWORD, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v17, &v18);
  v8 = v9(this, *(_QWORD *)(v10 + 24), &string);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2089484279 )
  {
    v18 = 0;
    if ( (v8 & 0x80000000) != 0 )
    {
      v14 = SusStrCchDup<char const *,char *>(a3);
      v8 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x212,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
          (const char *)(unsigned int)v14,
          v17[0]);
        v13 = 72;
        goto LABEL_16;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
      {
        v12 = ConvertWideToAnsi_Alloc(StringRawBuffer, &v18);
        v8 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
            (const char *)(unsigned int)v12,
            v17[0]);
          v13 = 68;
LABEL_16:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
            (const char *)v8,
            v17[0]);
          v15 = v18;
          goto LABEL_18;
        }
      }
    }
    v15 = 0;
    *(_QWORD *)a4 = v18;
    v8 = 0;
LABEL_18:
    if ( v15 )
      CSusBaseAllocTag<942762101>::operator delete(v15);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)v8,
    v17[0]);
LABEL_20:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x180041af8  push    rbp
0x180041afa  push    rbx
0x180041afb  push    rsi
0x180041afc  push    rdi
0x180041afd  push    r14
0x180041aff  push    r15
0x180041b01  mov     rbp, rsp
0x180041b04  sub     rsp, 68h
0x180041b08  mov     rax, cs:__security_cookie
0x180041b0f  xor     rax, rsp
0x180041b12  mov     [rbp+var_18], rax
0x180041b16  mov     rdi, r9
0x180041b19  mov     r14, r8
0x180041b1c  mov     rsi, rcx
0x180041b1f  mov     [rbp+var_28], rdx
0x180041b23  xor     r15d, r15d
0x180041b26  test    rcx, rcx
0x180041b29  jnz     short loc_180041B33
0x180041b2b  lea     edx, [rcx+36h]
0x180041b2e  jmp     loc_180041C7D
0x180041b33  test    rdx, rdx
0x180041b36  jz      loc_180041C78
0x180041b3c  cmp     [rdx], r15w
0x180041b40  jz      loc_180041C78
0x180041b46  test    rdi, rdi
0x180041b49  jnz     short loc_180041B58
0x180041b4b  mov     ebx, 80004003h
0x180041b50  lea     edx, [rdi+38h]
0x180041b53  jmp     loc_180041C82
0x180041b58  mov     [rbp+string], r15
0x180041b5c  mov     rax, [rcx]
0x180041b5f  mov     rbx, [rax+50h]
0x180041b63  xor     ecx, ecx; string
0x180041b65  call    cs:__imp_WindowsDeleteString
0x180041b6b  mov     [rbp+string], r15
0x180041b6f  lea     rdx, [rbp+var_28]
0x180041b73  lea     rcx, [rbp+var_48]
0x180041b77  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x180041b7c  nop
0x180041b7d  lea     r8, [rbp+string]
0x180041b81  mov     rdx, [rax+18h]
0x180041b85  mov     rcx, rsi
0x180041b88  mov     rax, rbx
0x180041b8b  call    _guard_dispatch_icall
0x180041b90  mov     ebx, eax
0x180041b92  mov     ecx, 80000000h
0x180041b97  add     eax, ecx
0x180041b99  test    ecx, eax
0x180041b9b  jnz     short loc_180041BC2
0x180041b9d  cmp     ebx, 83750009h
0x180041ba3  jz      short loc_180041BC2
0x180041ba5  mov     rcx, [rbp+30h]; this
0x180041ba9  mov     r9d, ebx; char *
0x180041bac  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041bb3  mov     edx, 3Dh ; '='; void *
0x180041bb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041bbd  jmp     loc_180041C6C
0x180041bc2  mov     [rbp+var_28], r15
0x180041bc6  test    ebx, ebx
0x180041bc8  js      short loc_180041C0C
0x180041bca  xor     edx, edx; length
0x180041bcc  mov     rcx, [rbp+string]; string
0x180041bd0  call    cs:__imp_WindowsGetStringRawBuffer
0x180041bd6  test    rax, rax
0x180041bd9  jz      short loc_180041C54
0x180041bdb  lea     rdx, [rbp+var_28]; char **
0x180041bdf  mov     rcx, rax; lpWideCharStr
0x180041be2  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x180041be7  mov     ebx, eax
0x180041be9  test    eax, eax
0x180041beb  jns     short loc_180041C54
0x180041bed  mov     rcx, [rbp+30h]; this
0x180041bf1  mov     r9d, eax; char *
0x180041bf4  lea     r8, aCW1SSrcClientL_15; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041bfb  mov     edx, 54h ; 'T'; void *
0x180041c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c05  mov     edx, 44h ; 'D'
0x180041c0a  jmp     short loc_180041C3B
0x180041c0c  lea     r8, [rbp+var_28]
0x180041c10  mov     rcx, r14; Src
0x180041c13  call    ??$SusStrCchDup@PEBDPEAD@@YAJPEBDIPEAPEAD@Z; SusStrCchDup<char const *,char *>(char const *,uint,char * *)
0x180041c18  mov     ebx, eax
0x180041c1a  test    eax, eax
0x180041c1c  jns     short loc_180041C54
0x180041c1e  mov     rcx, [rbp+30h]; this
0x180041c22  mov     r9d, eax; char *
0x180041c25  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041c2c  mov     edx, 212h; void *
0x180041c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c36  mov     edx, 48h ; 'H'; void *
0x180041c3b  mov     rcx, [rbp+30h]; this
0x180041c3f  mov     r9d, ebx; char *
0x180041c42  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c4e  mov     rcx, [rbp+var_28]
0x180041c52  jmp     short loc_180041C61
0x180041c54  mov     rax, [rbp+var_28]
0x180041c58  mov     rcx, r15; lpMem
0x180041c5b  mov     [rdi], rax
0x180041c5e  mov     ebx, r15d
0x180041c61  test    rcx, rcx
0x180041c64  jz      short loc_180041C6C
0x180041c66  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180041c6b  nop
0x180041c6c  mov     rcx, [rbp+string]; string
0x180041c70  call    cs:__imp_WindowsDeleteString
0x180041c76  jmp     short loc_180041C95
0x180041c78  mov     edx, 37h ; '7'; void *
0x180041c7d  mov     ebx, 80070057h
0x180041c82  mov     r9d, ebx; char *
0x180041c85  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041c8c  mov     rcx, [rbp+30h]; this
0x180041c90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c95  mov     eax, ebx
0x180041c97  mov     rcx, [rbp+var_18]
0x180041c9b  xor     rcx, rsp; StackCookie
0x180041c9e  call    __security_check_cookie
0x180041ca3  add     rsp, 68h
0x180041ca7  pop     r15
0x180041ca9  pop     r14
0x180041cab  pop     rdi
0x180041cac  pop     rsi
0x180041cad  pop     rbx
0x180041cae  pop     rbp
0x180041caf  retn
```
