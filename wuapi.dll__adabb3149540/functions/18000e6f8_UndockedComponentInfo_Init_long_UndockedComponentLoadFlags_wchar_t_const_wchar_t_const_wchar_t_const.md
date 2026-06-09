# UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18000e6f8`
- end: `0x18000e8af`
- name: `?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x180003760`
- `0x18000ac10`
- `0x18000b1ec`
- `0x18000e6f8`
- `0x18000f5c0`
- `0x18000fabc`
- `0x18000fce0`

## pseudocode

```c
__int64 __fastcall UndockedComponentInfo::Init(__int64 a1, int a2, int a3, void *a4, _WORD *Src, void *a6)
{
  _QWORD *v6; // rdi
  void *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  void *v14; // rcx
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  int FileVersion; // ebx
  __int64 v19; // rdx
  void *v20; // rcx
  unsigned __int64 v21; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (_QWORD *)(a1 + 8);
  *(_DWORD *)a1 = a2;
  *(_DWORD *)(a1 + 4) = a3;
  v9 = *(void **)(a1 + 8);
  if ( v9 )
  {
    SusFree(v9);
    *v6 = 0;
  }
  v10 = SusStrCchDup<wchar_t const *,wchar_t *>(a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v10,
      v21);
    v12 = 15;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
      (const char *)v11,
      v21);
    return v11;
  }
  v14 = *(void **)(a1 + 16);
  if ( v14 )
  {
    SusFree(v14);
    *(_QWORD *)(a1 + 16) = 0;
  }
  v15 = SusStrCchDup<wchar_t const *,wchar_t *>(Src);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v15,
      v21);
    v12 = 17;
    goto LABEL_5;
  }
  v16 = *(void **)(a1 + 32);
  if ( v16 )
  {
    SusFree(v16);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v17 = SusStrCchDup<wchar_t const *,wchar_t *>(a6);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v17,
      v21);
    v12 = 19;
    goto LABEL_5;
  }
  if ( Src && *Src )
  {
    v21 = 0;
    FileVersion = GetFileVersion(Src, &v21);
    if ( FileVersion < 0 )
    {
      v19 = 24;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
        (const char *)(unsigned int)FileVersion,
        v21);
      return (unsigned int)FileVersion;
    }
    v20 = *(void **)(a1 + 24);
    if ( v20 )
    {
      SusFree(v20);
      *(_QWORD *)(a1 + 24) = 0;
    }
    FileVersion = ConvertFileVerToStringW(v21, (wchar_t **)(a1 + 24));
    if ( FileVersion < 0 )
    {
      v19 = 25;
      goto LABEL_18;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e6f8  mov     [rsp+arg_8], rbx
0x18000e6fd  push    rbp
0x18000e6fe  push    rsi
0x18000e6ff  push    rdi
0x18000e700  push    r14
0x18000e702  push    r15
0x18000e704  sub     rsp, 30h
0x18000e708  mov     rax, cs:__security_cookie
0x18000e70f  xor     rax, rsp
0x18000e712  mov     [rsp+58h+var_30], rax
0x18000e717  mov     rbx, [rsp+58h+Src]
0x18000e71f  lea     rdi, [rcx+8]
0x18000e723  mov     r14, [rsp+58h+arg_28]
0x18000e72b  mov     rsi, rcx
0x18000e72e  mov     [rcx], edx
0x18000e730  xor     r15d, r15d
0x18000e733  mov     [rcx+4], r8d
0x18000e737  mov     rbp, r9
0x18000e73a  mov     rcx, [rdi]; lpMem
0x18000e73d  test    rcx, rcx
0x18000e740  jz      short loc_18000E74A
0x18000e742  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e747  mov     [rdi], r15
0x18000e74a  mov     r8, rdi
0x18000e74d  mov     rcx, rbp; Src
0x18000e750  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e755  mov     edi, eax
0x18000e757  test    eax, eax
0x18000e759  jns     short loc_18000E794
0x18000e75b  mov     rcx, [rsp+58h]; this
0x18000e760  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e767  mov     r9d, eax; char *
0x18000e76a  mov     edx, 212h; void *
0x18000e76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e774  mov     edx, 0Fh; void *
0x18000e779  mov     rcx, [rsp+58h]; this
0x18000e77e  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e785  mov     r9d, edi; char *
0x18000e788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e78d  mov     eax, edi
0x18000e78f  jmp     loc_18000E891
0x18000e794  lea     rdi, [rsi+10h]
0x18000e798  mov     rcx, [rdi]; lpMem
0x18000e79b  test    rcx, rcx
0x18000e79e  jz      short loc_18000E7A8
0x18000e7a0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e7a5  mov     [rdi], r15
0x18000e7a8  mov     r8, rdi
0x18000e7ab  mov     rcx, rbx; Src
0x18000e7ae  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e7b3  mov     edi, eax
0x18000e7b5  test    eax, eax
0x18000e7b7  jns     short loc_18000E7D9
0x18000e7b9  mov     rcx, [rsp+58h]; this
0x18000e7be  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e7c5  mov     r9d, eax; char *
0x18000e7c8  mov     edx, 212h; void *
0x18000e7cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7d2  mov     edx, 11h
0x18000e7d7  jmp     short loc_18000E779
0x18000e7d9  lea     rdi, [rsi+20h]
0x18000e7dd  mov     rcx, [rdi]; lpMem
0x18000e7e0  test    rcx, rcx
0x18000e7e3  jz      short loc_18000E7ED
0x18000e7e5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e7ea  mov     [rdi], r15
0x18000e7ed  mov     r8, rdi
0x18000e7f0  mov     rcx, r14; Src
0x18000e7f3  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e7f8  mov     edi, eax
0x18000e7fa  test    eax, eax
0x18000e7fc  jns     short loc_18000E821
0x18000e7fe  mov     rcx, [rsp+58h]; this
0x18000e803  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e80a  mov     r9d, eax; char *
0x18000e80d  mov     edx, 212h; void *
0x18000e812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e817  mov     edx, 13h
0x18000e81c  jmp     loc_18000E779
0x18000e821  test    rbx, rbx
0x18000e824  jz      short loc_18000E88F
0x18000e826  cmp     [rbx], r15w
0x18000e82a  jz      short loc_18000E88F
0x18000e82c  lea     rdx, [rsp+58h+var_38]
0x18000e831  mov     [rsp+58h+var_38], r15; int
0x18000e836  mov     rcx, rbx
0x18000e839  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x18000e83e  mov     ebx, eax
0x18000e840  test    eax, eax
0x18000e842  jns     short loc_18000E861
0x18000e844  mov     edx, 18h; void *
0x18000e849  mov     rcx, [rsp+58h]; this
0x18000e84e  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e855  mov     r9d, ebx; char *
0x18000e858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e85d  mov     eax, ebx
0x18000e85f  jmp     short loc_18000E891
0x18000e861  lea     rbx, [rsi+18h]
0x18000e865  mov     rcx, [rbx]; lpMem
0x18000e868  test    rcx, rcx
0x18000e86b  jz      short loc_18000E875
0x18000e86d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e872  mov     [rbx], r15
0x18000e875  mov     rcx, [rsp+58h+var_38]; unsigned __int64
0x18000e87a  mov     rdx, rbx; wchar_t **
0x18000e87d  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x18000e882  mov     ebx, eax
0x18000e884  test    eax, eax
0x18000e886  jns     short loc_18000E88F
0x18000e888  mov     edx, 19h
0x18000e88d  jmp     short loc_18000E849
0x18000e88f  xor     eax, eax
0x18000e891  mov     rcx, [rsp+58h+var_30]
0x18000e896  xor     rcx, rsp; StackCookie
0x18000e899  call    __security_check_cookie
0x18000e89e  mov     rbx, [rsp+58h+arg_8]
0x18000e8a3  add     rsp, 30h
0x18000e8a7  pop     r15
0x18000e8a9  pop     r14
0x18000e8ab  pop     rdi
0x18000e8ac  pop     rsi
0x18000e8ad  pop     rbp
0x18000e8ae  retn
```
