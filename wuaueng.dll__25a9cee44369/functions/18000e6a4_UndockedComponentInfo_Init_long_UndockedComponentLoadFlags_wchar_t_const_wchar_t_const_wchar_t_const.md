# UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18000e6a4`
- end: `0x18000e85b`
- name: `?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64, int, int, void *, _WORD *Src, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180003760`
- `0x18000abbc`
- `0x18000b198`
- `0x18000e6a4`
- `0x18000f570`
- `0x18000fa6c`
- `0x18000fc90`

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
0x18000e6a4  mov     [rsp+arg_8], rbx
0x18000e6a9  push    rbp
0x18000e6aa  push    rsi
0x18000e6ab  push    rdi
0x18000e6ac  push    r14
0x18000e6ae  push    r15
0x18000e6b0  sub     rsp, 30h
0x18000e6b4  mov     rax, cs:__security_cookie
0x18000e6bb  xor     rax, rsp
0x18000e6be  mov     [rsp+58h+var_30], rax
0x18000e6c3  mov     rbx, [rsp+58h+Src]
0x18000e6cb  lea     rdi, [rcx+8]
0x18000e6cf  mov     r14, [rsp+58h+arg_28]
0x18000e6d7  mov     rsi, rcx
0x18000e6da  mov     [rcx], edx
0x18000e6dc  xor     r15d, r15d
0x18000e6df  mov     [rcx+4], r8d
0x18000e6e3  mov     rbp, r9
0x18000e6e6  mov     rcx, [rdi]; lpMem
0x18000e6e9  test    rcx, rcx
0x18000e6ec  jz      short loc_18000E6F6
0x18000e6ee  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e6f3  mov     [rdi], r15
0x18000e6f6  mov     r8, rdi
0x18000e6f9  mov     rcx, rbp; Src
0x18000e6fc  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e701  mov     edi, eax
0x18000e703  test    eax, eax
0x18000e705  jns     short loc_18000E740
0x18000e707  mov     rcx, [rsp+58h]; this
0x18000e70c  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e713  mov     r9d, eax; char *
0x18000e716  mov     edx, 212h; void *
0x18000e71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e720  mov     edx, 0Fh; void *
0x18000e725  mov     rcx, [rsp+58h]; this
0x18000e72a  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e731  mov     r9d, edi; char *
0x18000e734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e739  mov     eax, edi
0x18000e73b  jmp     loc_18000E83D
0x18000e740  lea     rdi, [rsi+10h]
0x18000e744  mov     rcx, [rdi]; lpMem
0x18000e747  test    rcx, rcx
0x18000e74a  jz      short loc_18000E754
0x18000e74c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e751  mov     [rdi], r15
0x18000e754  mov     r8, rdi
0x18000e757  mov     rcx, rbx; Src
0x18000e75a  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e75f  mov     edi, eax
0x18000e761  test    eax, eax
0x18000e763  jns     short loc_18000E785
0x18000e765  mov     rcx, [rsp+58h]; this
0x18000e76a  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e771  mov     r9d, eax; char *
0x18000e774  mov     edx, 212h; void *
0x18000e779  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e77e  mov     edx, 11h
0x18000e783  jmp     short loc_18000E725
0x18000e785  lea     rdi, [rsi+20h]
0x18000e789  mov     rcx, [rdi]; lpMem
0x18000e78c  test    rcx, rcx
0x18000e78f  jz      short loc_18000E799
0x18000e791  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e796  mov     [rdi], r15
0x18000e799  mov     r8, rdi
0x18000e79c  mov     rcx, r14; Src
0x18000e79f  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000e7a4  mov     edi, eax
0x18000e7a6  test    eax, eax
0x18000e7a8  jns     short loc_18000E7CD
0x18000e7aa  mov     rcx, [rsp+58h]; this
0x18000e7af  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e7b6  mov     r9d, eax; char *
0x18000e7b9  mov     edx, 212h; void *
0x18000e7be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7c3  mov     edx, 13h
0x18000e7c8  jmp     loc_18000E725
0x18000e7cd  test    rbx, rbx
0x18000e7d0  jz      short loc_18000E83B
0x18000e7d2  cmp     [rbx], r15w
0x18000e7d6  jz      short loc_18000E83B
0x18000e7d8  lea     rdx, [rsp+58h+var_38]
0x18000e7dd  mov     [rsp+58h+var_38], r15; int
0x18000e7e2  mov     rcx, rbx
0x18000e7e5  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x18000e7ea  mov     ebx, eax
0x18000e7ec  test    eax, eax
0x18000e7ee  jns     short loc_18000E80D
0x18000e7f0  mov     edx, 18h; void *
0x18000e7f5  mov     rcx, [rsp+58h]; this
0x18000e7fa  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e801  mov     r9d, ebx; char *
0x18000e804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e809  mov     eax, ebx
0x18000e80b  jmp     short loc_18000E83D
0x18000e80d  lea     rbx, [rsi+18h]
0x18000e811  mov     rcx, [rbx]; lpMem
0x18000e814  test    rcx, rcx
0x18000e817  jz      short loc_18000E821
0x18000e819  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e81e  mov     [rbx], r15
0x18000e821  mov     rcx, [rsp+58h+var_38]; unsigned __int64
0x18000e826  mov     rdx, rbx; wchar_t **
0x18000e829  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x18000e82e  mov     ebx, eax
0x18000e830  test    eax, eax
0x18000e832  jns     short loc_18000E83B
0x18000e834  mov     edx, 19h
0x18000e839  jmp     short loc_18000E7F5
0x18000e83b  xor     eax, eax
0x18000e83d  mov     rcx, [rsp+58h+var_30]
0x18000e842  xor     rcx, rsp; StackCookie
0x18000e845  call    __security_check_cookie
0x18000e84a  mov     rbx, [rsp+58h+arg_8]
0x18000e84f  add     rsp, 30h
0x18000e853  pop     r15
0x18000e855  pop     r14
0x18000e857  pop     rdi
0x18000e858  pop     rsi
0x18000e859  pop     rbp
0x18000e85a  retn
```
