# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x180041970`
- end: `0x180041af0`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z`
- size: `384`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003ecf4`
- `0x18003f6b4`
- `0x18003fb60`
- `0x18003ff64`
- `0x1800415f0`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000b334`
- `0x18002d674`
- `0x180041970`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a45`

## string_xrefs

- `0x180041a24`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x180041a82`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x180041ac5`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JsonUtil::GetStringPropertyWithDefault(
        JsonUtil *this,
        struct ABI::Windows::Data::Json::IJsonObject *a2,
        const wchar_t *a3,
        wchar_t *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  __int64 (__fastcall *v9)(JsonUtil *, _QWORD, HSTRING *); // rbx
  __int64 v10; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rdx
  struct ABI::Windows::Data::Json::IJsonObject *v13; // rcx
  int v15[8]; // [rsp+20h] [rbp-48h] BYREF
  struct ABI::Windows::Data::Json::IJsonObject *v16; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v16 = a2;
  if ( !this )
  {
    v7 = 23;
LABEL_21:
    v8 = -2147024809;
    goto LABEL_22;
  }
  if ( !a2 || !*(_WORD *)a2 )
  {
    v7 = 24;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v7 = 25;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
      (const char *)(unsigned int)v8,
      v15[0]);
    return (unsigned int)v8;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(JsonUtil *, _QWORD, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, &v16);
  v8 = v9(this, *(_QWORD *)(v10 + 24), &string);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2089484279 )
  {
    v16 = 0;
    if ( v8 < 0 )
    {
      v8 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a3, &v16);
      if ( v8 < 0 )
      {
        v12 = 41;
        goto LABEL_15;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v8 = DuplicateOptionalString<wchar_t const *,wchar_t *>(StringRawBuffer, &v16);
      if ( v8 < 0 )
      {
        v12 = 37;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
          (const char *)(unsigned int)v8,
          v15[0]);
        v13 = v16;
        goto LABEL_17;
      }
    }
    v13 = 0;
    *(_QWORD *)a4 = v16;
    v8 = 0;
LABEL_17:
    if ( v13 )
      CSusBaseAllocTag<942762101>::operator delete(v13);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)(unsigned int)v8,
    v15[0]);
LABEL_19:
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180041970  push    rbp
0x180041972  push    rbx
0x180041973  push    rsi
0x180041974  push    rdi
0x180041975  push    r14
0x180041977  push    r15
0x180041979  mov     rbp, rsp
0x18004197c  sub     rsp, 68h
0x180041980  mov     rax, cs:__security_cookie
0x180041987  xor     rax, rsp
0x18004198a  mov     [rbp+var_18], rax
0x18004198e  mov     rdi, r9
0x180041991  mov     r14, r8
0x180041994  mov     rsi, rcx
0x180041997  mov     [rbp+var_28], rdx
0x18004199b  xor     r15d, r15d
0x18004199e  test    rcx, rcx
0x1800419a1  jnz     short loc_1800419AB
0x1800419a3  lea     edx, [rcx+17h]
0x1800419a6  jmp     loc_180041ABD
0x1800419ab  test    rdx, rdx
0x1800419ae  jz      loc_180041AB8
0x1800419b4  cmp     [rdx], r15w
0x1800419b8  jz      loc_180041AB8
0x1800419be  test    rdi, rdi
0x1800419c1  jnz     short loc_1800419D0
0x1800419c3  mov     ebx, 80004003h
0x1800419c8  lea     edx, [rdi+19h]
0x1800419cb  jmp     loc_180041AC2
0x1800419d0  mov     [rbp+string], r15
0x1800419d4  mov     rax, [rcx]
0x1800419d7  mov     rbx, [rax+50h]
0x1800419db  xor     ecx, ecx; string
0x1800419dd  call    cs:__imp_WindowsDeleteString
0x1800419e3  mov     [rbp+string], r15
0x1800419e7  lea     rdx, [rbp+var_28]
0x1800419eb  lea     rcx, [rbp+var_48]
0x1800419ef  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x1800419f4  nop
0x1800419f5  lea     r8, [rbp+string]
0x1800419f9  mov     rdx, [rax+18h]
0x1800419fd  mov     rcx, rsi
0x180041a00  mov     rax, rbx
0x180041a03  call    _guard_dispatch_icall
0x180041a08  mov     ebx, eax
0x180041a0a  mov     ecx, 80000000h
0x180041a0f  add     eax, ecx
0x180041a11  test    ecx, eax
0x180041a13  jnz     short loc_180041A37
0x180041a15  cmp     ebx, 83750009h
0x180041a1b  jz      short loc_180041A37
0x180041a1d  mov     rcx, [rbp+30h]; this
0x180041a21  mov     r9d, ebx; char *
0x180041a24  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041a2b  mov     edx, 1Eh; void *
0x180041a30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a35  jmp     short loc_180041AAC
0x180041a37  mov     [rbp+var_28], r15
0x180041a3b  test    ebx, ebx
0x180041a3d  js      short loc_180041A64
0x180041a3f  xor     edx, edx; length
0x180041a41  mov     rcx, [rbp+string]; string
0x180041a45  call    cs:__imp_WindowsGetStringRawBuffer
0x180041a4b  lea     rdx, [rbp+var_28]
0x180041a4f  mov     rcx, rax
0x180041a52  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180041a57  mov     ebx, eax
0x180041a59  test    eax, eax
0x180041a5b  jns     short loc_180041A94
0x180041a5d  mov     edx, 25h ; '%'
0x180041a62  jmp     short loc_180041A7B
0x180041a64  lea     rdx, [rbp+var_28]
0x180041a68  mov     rcx, r14
0x180041a6b  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180041a70  mov     ebx, eax
0x180041a72  test    eax, eax
0x180041a74  jns     short loc_180041A94
0x180041a76  mov     edx, 29h ; ')'; void *
0x180041a7b  mov     rcx, [rbp+30h]; this
0x180041a7f  mov     r9d, ebx; char *
0x180041a82  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041a89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a8e  mov     rcx, [rbp+var_28]
0x180041a92  jmp     short loc_180041AA1
0x180041a94  mov     rax, [rbp+var_28]
0x180041a98  mov     rcx, r15; lpMem
0x180041a9b  mov     [rdi], rax
0x180041a9e  mov     ebx, r15d
0x180041aa1  test    rcx, rcx
0x180041aa4  jz      short loc_180041AAC
0x180041aa6  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180041aab  nop
0x180041aac  mov     rcx, [rbp+string]; string
0x180041ab0  call    cs:__imp_WindowsDeleteString
0x180041ab6  jmp     short loc_180041AD5
0x180041ab8  mov     edx, 18h; void *
0x180041abd  mov     ebx, 80070057h
0x180041ac2  mov     r9d, ebx; char *
0x180041ac5  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180041acc  mov     rcx, [rbp+30h]; this
0x180041ad0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041ad5  mov     eax, ebx
0x180041ad7  mov     rcx, [rbp+var_18]
0x180041adb  xor     rcx, rsp; StackCookie
0x180041ade  call    __security_check_cookie
0x180041ae3  add     rsp, 68h
0x180041ae7  pop     r15
0x180041ae9  pop     r14
0x180041aeb  pop     rdi
0x180041aec  pop     rsi
0x180041aed  pop     rbx
0x180041aee  pop     rbp
0x180041aef  retn
```
