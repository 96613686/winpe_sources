# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x1400183a0`
- end: `0x140018520`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z`
- size: `384`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001565c`
- `0x14001601c`
- `0x1400164c8`
- `0x1400168cc`
- `0x140017f58`

## callees

- `0x140002ac0`
- `0x14000ce5c`
- `0x14000d4cc`
- `0x1400182f0`
- `0x1400183a0`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001840d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400184e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001840d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400184e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140018475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140018475`

## string_xrefs

- `0x140018454`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x1400184b2`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x1400184f5`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

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
      SusFree(v13);
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
0x1400183a0  push    rbp
0x1400183a2  push    rbx
0x1400183a3  push    rsi
0x1400183a4  push    rdi
0x1400183a5  push    r14
0x1400183a7  push    r15
0x1400183a9  mov     rbp, rsp
0x1400183ac  sub     rsp, 68h
0x1400183b0  mov     rax, cs:__security_cookie
0x1400183b7  xor     rax, rsp
0x1400183ba  mov     [rbp+var_18], rax
0x1400183be  mov     rdi, r9
0x1400183c1  mov     r14, r8
0x1400183c4  mov     rsi, rcx
0x1400183c7  mov     [rbp+var_28], rdx
0x1400183cb  xor     r15d, r15d
0x1400183ce  test    rcx, rcx
0x1400183d1  jnz     short loc_1400183DB
0x1400183d3  lea     edx, [rcx+17h]
0x1400183d6  jmp     loc_1400184ED
0x1400183db  test    rdx, rdx
0x1400183de  jz      loc_1400184E8
0x1400183e4  cmp     [rdx], r15w
0x1400183e8  jz      loc_1400184E8
0x1400183ee  test    rdi, rdi
0x1400183f1  jnz     short loc_140018400
0x1400183f3  mov     ebx, 80004003h
0x1400183f8  lea     edx, [rdi+19h]
0x1400183fb  jmp     loc_1400184F2
0x140018400  mov     [rbp+string], r15
0x140018404  mov     rax, [rcx]
0x140018407  mov     rbx, [rax+50h]
0x14001840b  xor     ecx, ecx; string
0x14001840d  call    cs:__imp_WindowsDeleteString
0x140018413  mov     [rbp+string], r15
0x140018417  lea     rdx, [rbp+var_28]
0x14001841b  lea     rcx, [rbp+var_48]
0x14001841f  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140018424  nop
0x140018425  lea     r8, [rbp+string]
0x140018429  mov     rdx, [rax+18h]
0x14001842d  mov     rcx, rsi
0x140018430  mov     rax, rbx
0x140018433  call    _guard_dispatch_icall
0x140018438  mov     ebx, eax
0x14001843a  mov     ecx, 80000000h
0x14001843f  add     eax, ecx
0x140018441  test    ecx, eax
0x140018443  jnz     short loc_140018467
0x140018445  cmp     ebx, 83750009h
0x14001844b  jz      short loc_140018467
0x14001844d  mov     rcx, [rbp+30h]; this
0x140018451  mov     r9d, ebx; char *
0x140018454  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001845b  mov     edx, 1Eh; void *
0x140018460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018465  jmp     short loc_1400184DC
0x140018467  mov     [rbp+var_28], r15
0x14001846b  test    ebx, ebx
0x14001846d  js      short loc_140018494
0x14001846f  xor     edx, edx; length
0x140018471  mov     rcx, [rbp+string]; string
0x140018475  call    cs:__imp_WindowsGetStringRawBuffer
0x14001847b  lea     rdx, [rbp+var_28]
0x14001847f  mov     rcx, rax
0x140018482  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x140018487  mov     ebx, eax
0x140018489  test    eax, eax
0x14001848b  jns     short loc_1400184C4
0x14001848d  mov     edx, 25h ; '%'
0x140018492  jmp     short loc_1400184AB
0x140018494  lea     rdx, [rbp+var_28]
0x140018498  mov     rcx, r14
0x14001849b  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1400184a0  mov     ebx, eax
0x1400184a2  test    eax, eax
0x1400184a4  jns     short loc_1400184C4
0x1400184a6  mov     edx, 29h ; ')'; void *
0x1400184ab  mov     rcx, [rbp+30h]; this
0x1400184af  mov     r9d, ebx; char *
0x1400184b2  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400184b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400184be  mov     rcx, [rbp+var_28]
0x1400184c2  jmp     short loc_1400184D1
0x1400184c4  mov     rax, [rbp+var_28]
0x1400184c8  mov     rcx, r15; lpMem
0x1400184cb  mov     [rdi], rax
0x1400184ce  mov     ebx, r15d
0x1400184d1  test    rcx, rcx
0x1400184d4  jz      short loc_1400184DC
0x1400184d6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400184db  nop
0x1400184dc  mov     rcx, [rbp+string]; string
0x1400184e0  call    cs:__imp_WindowsDeleteString
0x1400184e6  jmp     short loc_140018505
0x1400184e8  mov     edx, 18h; void *
0x1400184ed  mov     ebx, 80070057h
0x1400184f2  mov     r9d, ebx; char *
0x1400184f5  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400184fc  mov     rcx, [rbp+30h]; this
0x140018500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018505  mov     eax, ebx
0x140018507  mov     rcx, [rbp+var_18]
0x14001850b  xor     rcx, rsp; StackCookie
0x14001850e  call    __security_check_cookie
0x140018513  add     rsp, 68h
0x140018517  pop     r15
0x140018519  pop     r14
0x14001851b  pop     rdi
0x14001851c  pop     rsi
0x14001851d  pop     rbx
0x14001851e  pop     rbp
0x14001851f  retn
```
