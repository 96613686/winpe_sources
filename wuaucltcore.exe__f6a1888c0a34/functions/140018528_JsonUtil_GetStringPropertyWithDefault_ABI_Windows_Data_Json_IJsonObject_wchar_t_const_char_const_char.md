# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,char const *,char * *)

- ea: `0x140018528`
- end: `0x1400186e0`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEBDPEAPEAD@Z`
- size: `440`
- prototype: `int(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const char *, char **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001601c`

## callees

- `0x140002ac0`
- `0x14000cd5c`
- `0x14000d4cc`
- `0x1400182f0`
- `0x140018528`
- `0x1400189f4`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400186a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400186a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140018600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140018600`

## string_xrefs

- `0x1400185dc`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x140018672`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x1400186b5`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

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
      SusFree(v15);
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
0x140018528  push    rbp
0x14001852a  push    rbx
0x14001852b  push    rsi
0x14001852c  push    rdi
0x14001852d  push    r14
0x14001852f  push    r15
0x140018531  mov     rbp, rsp
0x140018534  sub     rsp, 68h
0x140018538  mov     rax, cs:__security_cookie
0x14001853f  xor     rax, rsp
0x140018542  mov     [rbp+var_18], rax
0x140018546  mov     rdi, r9
0x140018549  mov     r14, r8
0x14001854c  mov     rsi, rcx
0x14001854f  mov     [rbp+var_28], rdx
0x140018553  xor     r15d, r15d
0x140018556  test    rcx, rcx
0x140018559  jnz     short loc_140018563
0x14001855b  lea     edx, [rcx+36h]
0x14001855e  jmp     loc_1400186AD
0x140018563  test    rdx, rdx
0x140018566  jz      loc_1400186A8
0x14001856c  cmp     [rdx], r15w
0x140018570  jz      loc_1400186A8
0x140018576  test    rdi, rdi
0x140018579  jnz     short loc_140018588
0x14001857b  mov     ebx, 80004003h
0x140018580  lea     edx, [rdi+38h]
0x140018583  jmp     loc_1400186B2
0x140018588  mov     [rbp+string], r15
0x14001858c  mov     rax, [rcx]
0x14001858f  mov     rbx, [rax+50h]
0x140018593  xor     ecx, ecx; string
0x140018595  call    cs:__imp_WindowsDeleteString
0x14001859b  mov     [rbp+string], r15
0x14001859f  lea     rdx, [rbp+var_28]
0x1400185a3  lea     rcx, [rbp+var_48]
0x1400185a7  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1400185ac  nop
0x1400185ad  lea     r8, [rbp+string]
0x1400185b1  mov     rdx, [rax+18h]
0x1400185b5  mov     rcx, rsi
0x1400185b8  mov     rax, rbx
0x1400185bb  call    _guard_dispatch_icall
0x1400185c0  mov     ebx, eax
0x1400185c2  mov     ecx, 80000000h
0x1400185c7  add     eax, ecx
0x1400185c9  test    ecx, eax
0x1400185cb  jnz     short loc_1400185F2
0x1400185cd  cmp     ebx, 83750009h
0x1400185d3  jz      short loc_1400185F2
0x1400185d5  mov     rcx, [rbp+30h]; this
0x1400185d9  mov     r9d, ebx; char *
0x1400185dc  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400185e3  mov     edx, 3Dh ; '='; void *
0x1400185e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400185ed  jmp     loc_14001869C
0x1400185f2  mov     [rbp+var_28], r15
0x1400185f6  test    ebx, ebx
0x1400185f8  js      short loc_14001863C
0x1400185fa  xor     edx, edx; length
0x1400185fc  mov     rcx, [rbp+string]; string
0x140018600  call    cs:__imp_WindowsGetStringRawBuffer
0x140018606  test    rax, rax
0x140018609  jz      short loc_140018684
0x14001860b  lea     rdx, [rbp+var_28]; char **
0x14001860f  mov     rcx, rax; lpWideCharStr
0x140018612  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x140018617  mov     ebx, eax
0x140018619  test    eax, eax
0x14001861b  jns     short loc_140018684
0x14001861d  mov     rcx, [rbp+30h]; this
0x140018621  mov     r9d, eax; char *
0x140018624  lea     r8, aCW1SSrcClientL_6; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001862b  mov     edx, 54h ; 'T'; void *
0x140018630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018635  mov     edx, 44h ; 'D'
0x14001863a  jmp     short loc_14001866B
0x14001863c  lea     r8, [rbp+var_28]
0x140018640  mov     rcx, r14; Src
0x140018643  call    ??$SusStrCchDup@PEBDPEAD@@YAJPEBDIPEAPEAD@Z; SusStrCchDup<char const *,char *>(char const *,uint,char * *)
0x140018648  mov     ebx, eax
0x14001864a  test    eax, eax
0x14001864c  jns     short loc_140018684
0x14001864e  mov     rcx, [rbp+30h]; this
0x140018652  mov     r9d, eax; char *
0x140018655  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001865c  mov     edx, 212h; void *
0x140018661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018666  mov     edx, 48h ; 'H'; void *
0x14001866b  mov     rcx, [rbp+30h]; this
0x14001866f  mov     r9d, ebx; char *
0x140018672  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001867e  mov     rcx, [rbp+var_28]
0x140018682  jmp     short loc_140018691
0x140018684  mov     rax, [rbp+var_28]
0x140018688  mov     rcx, r15; lpMem
0x14001868b  mov     [rdi], rax
0x14001868e  mov     ebx, r15d
0x140018691  test    rcx, rcx
0x140018694  jz      short loc_14001869C
0x140018696  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001869b  nop
0x14001869c  mov     rcx, [rbp+string]; string
0x1400186a0  call    cs:__imp_WindowsDeleteString
0x1400186a6  jmp     short loc_1400186C5
0x1400186a8  mov     edx, 37h ; '7'; void *
0x1400186ad  mov     ebx, 80070057h
0x1400186b2  mov     r9d, ebx; char *
0x1400186b5  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400186bc  mov     rcx, [rbp+30h]; this
0x1400186c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400186c5  mov     eax, ebx
0x1400186c7  mov     rcx, [rbp+var_18]
0x1400186cb  xor     rcx, rsp; StackCookie
0x1400186ce  call    __security_check_cookie
0x1400186d3  add     rsp, 68h
0x1400186d7  pop     r15
0x1400186d9  pop     r14
0x1400186db  pop     rdi
0x1400186dc  pop     rsi
0x1400186dd  pop     rbx
0x1400186de  pop     rbp
0x1400186df  retn
```
