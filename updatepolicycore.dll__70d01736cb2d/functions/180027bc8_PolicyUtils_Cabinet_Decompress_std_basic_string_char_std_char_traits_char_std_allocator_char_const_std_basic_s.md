# PolicyUtils::Cabinet::Decompress(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180027bc8`
- end: `0x180027e00`
- name: `?Decompress@Cabinet@PolicyUtils@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00AEAV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018bc4`

## callees

- `0x18000aac0`
- `0x1800163c8`
- `0x18001a24c`
- `0x180021e00`
- `0x1800278a8`
- `0x180027bc8`
- `0x18002ffd0`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x180027c4f`
- `Cabinet!__imp_FDICreate` at `0x180027c4f`
- `Cabinet!__imp_FDICopy` at `0x180027d2a`
- `Cabinet!__imp_FDICopy` at `0x180027d2a`
- `Cabinet!__imp_FDIDestroy` at `0x180027db9`
- `Cabinet!__imp_FDIDestroy` at `0x180027db9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PolicyUtils::Cabinet::Decompress(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  const int *v8; // rdx
  int v9; // eax
  void *v10; // r8
  unsigned int v11; // ebx
  CHAR *v12; // r8
  CHAR *v13; // rdx
  const int *v14; // rdx
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  const int *v18; // rdx
  unsigned int v19; // eax
  int v20; // r9d
  int pfnwrite; // [rsp+20h] [rbp-A9h]
  HFDI hfdi; // [rsp+68h] [rbp-61h]
  _BYTE pvUser[32]; // [rsp+70h] [rbp-59h] BYREF
  _QWORD *v25; // [rsp+90h] [rbp-39h]
  __int64 v26; // [rsp+98h] [rbp-31h]
  char v27; // [rsp+A0h] [rbp-29h]
  int v28; // [rsp+A1h] [rbp-28h]
  __int16 v29; // [rsp+A5h] [rbp-24h]
  char v30; // [rsp+A7h] [rbp-22h]
  ERF perf; // [rsp+A8h] [rbp-21h] BYREF
  LPSTR pszCabPath[4]; // [rsp+B8h] [rbp-11h] BYREF
  LPSTR pszCabinet[4]; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  hfdi = FDICreate(
           PolicyUtils::Cabinet::FdiCbAlloc,
           PolicyUtils::Cabinet::FdiCbFree,
           PolicyUtils::Cabinet::FdiCbFileOpen,
           PolicyUtils::Cabinet::FdiCbFileRead,
           PolicyUtils::Cabinet::FdiCbFileWrite,
           PolicyUtils::Cabinet::FdiCbFileClose,
           PolicyUtils::Cabinet::FdiCbFileSeek,
           -1,
           &perf);
  if ( hfdi )
  {
    std::string::string(pvUser, a3);
    v25 = a4;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    std::string::string(pszCabinet, a2);
    std::string::string(pszCabPath, a1);
    v12 = (CHAR *)pszCabPath;
    if ( pszCabPath[3] > (LPSTR)0xF )
      v12 = pszCabPath[0];
    v13 = (CHAR *)pszCabinet;
    if ( pszCabinet[3] > (LPSTR)0xF )
      v13 = pszCabinet[0];
    if ( FDICopy(hfdi, v13, v12, 0, PolicyUtils::Cabinet::FdiCbNotify, 0, pvUser) )
    {
      if ( v27 )
      {
        if ( *v25 != v25[1] )
        {
          v11 = 0;
          goto LABEL_18;
        }
        v11 = -2147024883;
        v17 = 257;
      }
      else
      {
        v11 = -2147024894;
        v17 = 256;
      }
      v16 = v11;
    }
    else
    {
      v15 = PolicyUtils::Cabinet::EvaluateERFError((PolicyUtils::Cabinet *)&perf, v14);
      v11 = v15;
      if ( v15 >= 0 )
      {
LABEL_18:
        std::string::~string(pszCabPath);
        std::string::~string(pszCabinet);
        std::string::~string(pvUser);
        goto LABEL_19;
      }
      v16 = (unsigned int)v15;
      v17 = 253;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Utils\\PolicyUtils.cpp",
      (const char *)v16,
      pfnwrite);
    goto LABEL_18;
  }
  v9 = PolicyUtils::Cabinet::EvaluateERFError((PolicyUtils::Cabinet *)&perf, v8);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Utils\\PolicyUtils.cpp",
      (const char *)(unsigned int)v9,
      pfnwrite);
LABEL_19:
    v10 = hfdi;
  }
  if ( v10 )
  {
    FDIDestroy(v10);
    v19 = PolicyUtils::Cabinet::EvaluateERFError((PolicyUtils::Cabinet *)&perf, v18);
    if ( !v20 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Utils\\PolicyUtils.cpp",
        (const char *)v19,
        pfnwrite);
  }
  return v11;
}

```

## disassembly

```asm
0x180027bc8  push    rbp
0x180027bca  push    rbx
0x180027bcb  push    rsi
0x180027bcc  push    rdi
0x180027bcd  push    r14
0x180027bcf  lea     rbp, [rsp-37h]
0x180027bd4  sub     rsp, 100h
0x180027bdb  mov     rax, cs:__security_cookie
0x180027be2  xor     rax, rsp
0x180027be5  mov     [rbp+57h+var_28], rax
0x180027be9  mov     r14, r9
0x180027bec  mov     rsi, r8
0x180027bef  mov     rdi, rdx
0x180027bf2  mov     rbx, rcx
0x180027bf5  xor     eax, eax
0x180027bf7  mov     qword ptr [rbp+57h+var_78.erfOper], rax
0x180027bfb  mov     [rbp+57h+var_78.fError], eax
0x180027bfe  lea     rax, [rbp+57h+var_78]
0x180027c02  mov     [rsp+120h+perf], rax; perf
0x180027c07  mov     [rsp+120h+cpuType], 0FFFFFFFFh; cpuType
0x180027c0f  lea     rax, ?FdiCbFileSeek@Cabinet@PolicyUtils@@YAJ_JJH@Z; PolicyUtils::Cabinet::FdiCbFileSeek(__int64,long,int)
0x180027c16  mov     [rsp+120h+pfnseek], rax; pfnseek
0x180027c1b  lea     rax, ?FdiCbFileClose@Cabinet@PolicyUtils@@YAH_J@Z; PolicyUtils::Cabinet::FdiCbFileClose(__int64)
0x180027c22  mov     [rsp+120h+pfnclose], rax; pfnclose
0x180027c27  lea     rax, ?FdiCbFileWrite@Cabinet@PolicyUtils@@YAI_JPEAXI@Z; PolicyUtils::Cabinet::FdiCbFileWrite(__int64,void *,uint)
0x180027c2e  mov     [rsp+120h+pfnwrite], rax; int
0x180027c33  lea     r9, ?FdiCbFileRead@Cabinet@PolicyUtils@@YAI_JPEAXI@Z; pfnread
0x180027c3a  lea     r8, ?FdiCbFileOpen@Cabinet@PolicyUtils@@YA_JPEADHH@Z; pfnopen
0x180027c41  lea     rdx, ?FdiCbFree@Cabinet@PolicyUtils@@YAXPEAX@Z; pfnfree
0x180027c48  lea     rcx, ?FdiCbAlloc@Cabinet@PolicyUtils@@YAPEAXK@Z; pfnalloc
0x180027c4f  call    cs:__imp_FDICreate
0x180027c55  mov     r8, rax
0x180027c58  mov     [rbp+57h+hfdi], rax
0x180027c5c  lea     rax, [rbp+57h+hfdi]
0x180027c60  mov     [rbp+57h+var_D0], rax
0x180027c64  lea     rax, [rbp+57h+var_78]
0x180027c68  mov     [rbp+57h+var_C8], rax
0x180027c6c  mov     [rbp+57h+var_C0], 1
0x180027c70  test    r8, r8
0x180027c73  jnz     short loc_180027CA8
0x180027c75  lea     rcx, [rbp+57h+var_78]; this
0x180027c79  call    ?EvaluateERFError@Cabinet@PolicyUtils@@YAJAEBH@Z; PolicyUtils::Cabinet::EvaluateERFError(int const &)
0x180027c7e  mov     ebx, eax
0x180027c80  lea     rdi, aCW1SSrcClientP; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180027c87  test    eax, eax
0x180027c89  jns     loc_180027DB1
0x180027c8f  mov     rcx, [rbp+5Fh]; this
0x180027c93  mov     r9d, eax; char *
0x180027c96  mov     r8, rdi; unsigned int
0x180027c99  mov     edx, 0F4h; void *
0x180027c9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ca3  jmp     loc_180027DAD
0x180027ca8  mov     rdx, rsi
0x180027cab  lea     rcx, [rbp+57h+pvUser]
0x180027caf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180027cb4  mov     [rbp+57h+var_90], r14
0x180027cb8  mov     [rbp+57h+var_88], 0
0x180027cc0  mov     [rbp+57h+var_80], 0
0x180027cc4  xor     eax, eax
0x180027cc6  mov     [rbp+57h+var_7F], eax
0x180027cc9  mov     [rbp+57h+var_7B], ax
0x180027ccd  mov     [rbp+57h+var_79], al
0x180027cd0  mov     rdx, rdi
0x180027cd3  lea     rcx, [rbp+57h+pszCabinet]
0x180027cd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180027cdc  nop
0x180027cdd  mov     rdx, rbx
0x180027ce0  lea     rcx, [rbp+57h+pszCabPath]
0x180027ce4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180027ce9  lea     r8, [rbp+57h+pszCabPath]
0x180027ced  cmp     [rbp+57h+var_50], 0Fh
0x180027cf2  cmova   r8, [rbp+57h+pszCabPath]; pszCabPath
0x180027cf7  lea     rdx, [rbp+57h+pszCabinet]
0x180027cfb  cmp     [rbp+57h+var_30], 0Fh
0x180027d00  cmova   rdx, [rbp+57h+pszCabinet]; pszCabinet
0x180027d05  lea     rax, [rbp+57h+pvUser]
0x180027d09  mov     [rsp+120h+pfnseek], rax; pvUser
0x180027d0e  mov     [rsp+120h+pfnclose], 0; pfnfdid
0x180027d17  lea     rax, ?FdiCbNotify@Cabinet@PolicyUtils@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; PolicyUtils::Cabinet::FdiCbNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x180027d1e  mov     [rsp+120h+pfnwrite], rax; int
0x180027d23  xor     r9d, r9d; flags
0x180027d26  mov     rcx, [rbp+57h+hfdi]; hfdi
0x180027d2a  call    cs:__imp_FDICopy
0x180027d30  lea     rdi, aCW1SSrcClientP; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180027d37  test    eax, eax
0x180027d39  jnz     short loc_180027D54
0x180027d3b  lea     rcx, [rbp+57h+var_78]; this
0x180027d3f  call    ?EvaluateERFError@Cabinet@PolicyUtils@@YAJAEBH@Z; PolicyUtils::Cabinet::EvaluateERFError(int const &)
0x180027d44  mov     ebx, eax
0x180027d46  test    eax, eax
0x180027d48  jns     short loc_180027D90
0x180027d4a  mov     r9d, eax
0x180027d4d  mov     edx, 0FDh
0x180027d52  jmp     short loc_180027D80
0x180027d54  cmp     [rbp+57h+var_80], 0
0x180027d58  jnz     short loc_180027D66
0x180027d5a  mov     ebx, 80070002h
0x180027d5f  mov     edx, 100h
0x180027d64  jmp     short loc_180027D7D
0x180027d66  mov     rcx, [rbp+57h+var_90]
0x180027d6a  mov     rax, [rcx+8]
0x180027d6e  cmp     [rcx], rax
0x180027d71  jnz     short loc_180027D8E
0x180027d73  mov     ebx, 8007000Dh
0x180027d78  mov     edx, 101h; void *
0x180027d7d  mov     r9d, ebx; char *
0x180027d80  mov     rcx, [rbp+5Fh]; this
0x180027d84  mov     r8, rdi; unsigned int
0x180027d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d8c  jmp     short loc_180027D90
0x180027d8e  xor     ebx, ebx
0x180027d90  lea     rcx, [rbp+57h+pszCabPath]
0x180027d94  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180027d99  nop
0x180027d9a  lea     rcx, [rbp+57h+pszCabinet]
0x180027d9e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180027da3  nop
0x180027da4  lea     rcx, [rbp+57h+pvUser]
0x180027da8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180027dad  mov     r8, [rbp+57h+hfdi]
0x180027db1  test    r8, r8
0x180027db4  jz      short loc_180027DE4
0x180027db6  mov     rcx, r8; hfdi
0x180027db9  call    cs:__imp_FDIDestroy
0x180027dbf  mov     r9d, eax
0x180027dc2  lea     rcx, [rbp+57h+var_78]; this
0x180027dc6  call    ?EvaluateERFError@Cabinet@PolicyUtils@@YAJAEBH@Z; PolicyUtils::Cabinet::EvaluateERFError(int const &)
0x180027dcb  test    r9d, r9d
0x180027dce  jnz     short loc_180027DE4
0x180027dd0  mov     rcx, [rbp+5Fh]; this
0x180027dd4  mov     r9d, eax; char *
0x180027dd7  mov     r8, rdi; unsigned int
0x180027dda  mov     edx, 0F0h; void *
0x180027ddf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027de4  mov     eax, ebx
0x180027de6  mov     rcx, [rbp+57h+var_28]
0x180027dea  xor     rcx, rsp; StackCookie
0x180027ded  call    __security_check_cookie
0x180027df2  add     rsp, 100h
0x180027df9  pop     r14
0x180027dfb  pop     rdi
0x180027dfc  pop     rsi
0x180027dfd  pop     rbx
0x180027dfe  pop     rbp
0x180027dff  retn
```
