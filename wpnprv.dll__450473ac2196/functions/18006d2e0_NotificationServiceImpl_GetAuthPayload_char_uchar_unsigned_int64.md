# NotificationServiceImpl::GetAuthPayload(char * *,uchar * *,unsigned __int64 *)

- ea: `0x18006d2e0`
- end: `0x18006d575`
- name: `?GetAuthPayload@NotificationServiceImpl@@UEAAJPEAPEADPEAPEAEPEA_K@Z`
- size: `661`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this, char **, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180008b67`
- `0x18000c97c`
- `0x18000fddc`
- `0x18000fe0c`
- `0x18000fe2c`
- `0x18001c680`
- `0x180020924`
- `0x180033298`
- `0x180033884`
- `0x1800453f8`
- `0x1800454e0`
- `0x18006a104`
- `0x18006a598`
- `0x18006d2e0`
- `0x1800722c0`
- `0x180075894`
- `0x180075a7c`
- `0x180075a98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d4ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006d4ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d4de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d4de`

## string_xrefs

- `0x18006d354`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d375`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d396`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d3c5`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d3ed`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d41c`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d450`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d48b`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006d4bc`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::GetAuthPayload(
        NotificationServiceImpl *this,
        char **a2,
        unsigned __int8 **a3,
        unsigned __int64 *a4)
{
  int refreshed; // eax
  char *v9; // r13
  const char *v10; // r9
  int v11; // eax
  char *v12; // r12
  char *v13; // rbx
  int v14; // eax
  SIZE_T v15; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r8
  void *v23; // rax
  const void *v24; // rdx
  size_t v25; // r8
  const char *v26; // r9
  __int64 result; // rax
  char *v28[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v30; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  wil::ScopeExit__lambda_dfdb8d5e644d94b9755ff55617f68a48___(&v30);
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x80070057LL,
        (int)v28[0]);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x80070057LL,
        (int)v28[0]);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x240,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x80070057LL,
        (int)v28[0]);
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    refreshed = NotificationServiceImpl::RefreshAuthPayload((NotificationServiceImpl *)((char *)this - 8));
    if ( refreshed < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)refreshed,
        (int)v28[0]);
    if ( !*((_QWORD *)this + 25) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        (int)v28[0]);
    v9 = (char *)this + 232;
    if ( (unsigned __int8)wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::empty((char *)this + 232) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        (int)v28[0]);
    v28[0] = 0;
    v11 = StringCchLengthA(v10, 0x64u, (unsigned __int64 *)v28);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v11,
        (int)v28[0]);
    v12 = v28[0];
    wil::make_unique_nothrow<char [0]>(v28, v28[0] + 1);
    v13 = v28[0];
    if ( !v28[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        0);
    v14 = StringCchCopyA(v28[0], (unsigned __int64)(v12 + 1), *((const char **)this + 25));
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v14,
        (int)v28[0]);
    wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(v28);
    v15 = *((_QWORD *)this + 30);
    ProcessHeap = GetProcessHeap();
    v17 = HeapAlloc(ProcessHeap, 0, v15);
    wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(
      v28,
      v17,
      v15);
    v18 = wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::size(v9);
    v21 = wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::get(
            v20,
            v19,
            v18);
    v23 = (void *)wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::get(
                    v28,
                    v21,
                    v22);
    memcpy_0(v23, v24, v25);
    *a2 = v13;
    *a4 = (unsigned __int64)v28[1];
    *a3 = (unsigned __int8 *)wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::release(v28);
    wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(v28);
    wil::details::ScopeExitFn__lambda_785f71f0232c9392361b8da55dfbe788___::_ScopeExitFn__lambda_785f71f0232c9392361b8da55dfbe788___(&v30);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x25D,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x18006d2e0  mov     [rsp+arg_0], rbx
0x18006d2e5  mov     [rsp+arg_10], rsi
0x18006d2ea  push    rdi
0x18006d2eb  push    r12
0x18006d2ed  push    r13
0x18006d2ef  push    r14
0x18006d2f1  push    r15
0x18006d2f3  sub     rsp, 30h
0x18006d2f7  mov     rsi, r9
0x18006d2fa  mov     r14, r8
0x18006d2fd  mov     r15, rdx
0x18006d300  mov     rdi, rcx
0x18006d303  lea     rax, WPP_GLOBAL_Control
0x18006d30a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d311  cmp     rcx, rax
0x18006d314  jz      short loc_18006D337
0x18006d316  test    byte ptr [rcx+1Ch], 2
0x18006d31a  jz      short loc_18006D337
0x18006d31c  cmp     byte ptr [rcx+19h], 6
0x18006d320  jb      short loc_18006D337
0x18006d322  mov     edx, 33h ; '3'
0x18006d327  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006d32e  mov     rcx, [rcx+10h]
0x18006d332  call    WPP_SF_
0x18006d337  lea     rcx, [rsp+58h+arg_8]
0x18006d33c  call    wil__ScopeExit__lambda_dfdb8d5e644d94b9755ff55617f68a48___
0x18006d341  nop
0x18006d342  mov     rcx, [rsp+58h]; this
0x18006d347  xor     ebx, ebx
0x18006d349  test    r15, r15
0x18006d34c  jnz     short loc_18006D365
0x18006d34e  mov     r9d, 80070057h; char *
0x18006d354  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d35b  mov     edx, 23Eh; void *
0x18006d360  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d365  mov     rcx, [rsp+58h]; this
0x18006d36a  test    r14, r14
0x18006d36d  jnz     short loc_18006D386
0x18006d36f  mov     r9d, 80070057h; char *
0x18006d375  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d37c  mov     edx, 23Fh; void *
0x18006d381  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d386  mov     rcx, [rsp+58h]; this
0x18006d38b  test    rsi, rsi
0x18006d38e  jnz     short loc_18006D3A7
0x18006d390  mov     r9d, 80070057h; char *
0x18006d396  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d39d  mov     edx, 240h; void *
0x18006d3a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d3a7  mov     [r15], rbx
0x18006d3aa  mov     [r14], rbx
0x18006d3ad  mov     [rsi], rbx
0x18006d3b0  lea     rcx, [rdi-8]; this
0x18006d3b4  call    ?RefreshAuthPayload@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::RefreshAuthPayload(void)
0x18006d3b9  mov     rcx, [rsp+58h]; this
0x18006d3be  test    eax, eax
0x18006d3c0  jns     short loc_18006D3D6
0x18006d3c2  mov     r9d, eax; char *
0x18006d3c5  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d3cc  mov     edx, 247h; void *
0x18006d3d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d3d6  mov     rcx, [rsp+58h]; this
0x18006d3db  mov     r9, [rdi+0C8h]
0x18006d3e2  test    r9, r9
0x18006d3e5  jnz     short loc_18006D3FE
0x18006d3e7  mov     r9d, 8000FFFFh; char *
0x18006d3ed  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d3f4  mov     edx, 249h; void *
0x18006d3f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d3fe  lea     r13, [rdi+0E8h]
0x18006d405  mov     rcx, r13
0x18006d408  call    ?empty@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEBA_NXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::empty(void)
0x18006d40d  mov     rcx, [rsp+58h]; this
0x18006d412  test    al, al
0x18006d414  jz      short loc_18006D42D
0x18006d416  mov     r9d, 8000FFFFh; char *
0x18006d41c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d423  mov     edx, 24Ah; void *
0x18006d428  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d42d  mov     [rsp+58h+var_38], rbx; int
0x18006d432  lea     r8, [rsp+58h+var_38]; unsigned __int64 *
0x18006d437  mov     edx, 64h ; 'd'; unsigned __int64
0x18006d43c  mov     rcx, r9; char *
0x18006d43f  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18006d444  mov     rcx, [rsp+58h]; this
0x18006d449  test    eax, eax
0x18006d44b  jns     short loc_18006D461
0x18006d44d  mov     r9d, eax; char *
0x18006d450  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d457  mov     edx, 24Dh; void *
0x18006d45c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d461  mov     r12, [rsp+58h+var_38]
0x18006d466  lea     rdx, [r12+1]
0x18006d46b  lea     rcx, [rsp+58h+var_38]
0x18006d470  call    ??$make_unique_nothrow@$$BY0A@D@wil@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<char [0]>(unsigned __int64)
0x18006d475  nop
0x18006d476  mov     rcx, [rsp+58h]; this
0x18006d47b  mov     rbx, [rsp+58h+var_38]
0x18006d480  test    rbx, rbx
0x18006d483  jnz     short loc_18006D49C
0x18006d485  mov     r9d, 8000FFFFh; char *
0x18006d48b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d492  mov     edx, 250h; void *
0x18006d497  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d49c  mov     r8, [rdi+0C8h]; char *
0x18006d4a3  lea     rdx, [r12+1]; unsigned __int64
0x18006d4a8  mov     rcx, rbx; char *
0x18006d4ab  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006d4b0  mov     rcx, [rsp+58h]; this
0x18006d4b5  test    eax, eax
0x18006d4b7  jns     short loc_18006D4CD
0x18006d4b9  mov     r9d, eax; char *
0x18006d4bc  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006d4c3  mov     edx, 251h; void *
0x18006d4c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d4cd  lea     rcx, [rsp+58h+var_38]
0x18006d4d2  call    ??0?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(void)
0x18006d4d7  mov     rdi, [rdi+0F0h]
0x18006d4de  call    cs:__imp_GetProcessHeap
0x18006d4e4  mov     r8, rdi; dwBytes
0x18006d4e7  xor     edx, edx; dwFlags
0x18006d4e9  mov     rcx, rax; hHeap
0x18006d4ec  call    cs:__imp_HeapAlloc
0x18006d4f2  mov     r8, rdi
0x18006d4f5  mov     rdx, rax
0x18006d4f8  lea     rcx, [rsp+58h+var_38]
0x18006d4fd  call    ?reset@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAAXPEAE_K@Z; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(uchar *,unsigned __int64)
0x18006d502  mov     rcx, r13
0x18006d505  call    ?size@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEBA_KXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::size(void)
0x18006d50a  mov     r8, rax
0x18006d50d  call    ?get@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEBAPEAEXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::get(void)
0x18006d512  mov     rdx, rax
0x18006d515  lea     rcx, [rsp+58h+var_38]
0x18006d51a  call    ?get@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEBAPEAEXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::get(void)
0x18006d51f  mov     rcx, rax; void *
0x18006d522  call    memcpy_0
0x18006d527  mov     [r15], rbx
0x18006d52a  mov     rax, [rsp+58h+var_30]
0x18006d52f  mov     [rsi], rax
0x18006d532  lea     rcx, [rsp+58h+var_38]
0x18006d537  call    ?release@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAAPEAEXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::release(void)
0x18006d53c  mov     [r14], rax
0x18006d53f  lea     rcx, [rsp+58h+var_38]
0x18006d544  call    ??1?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(void)
0x18006d549  nop
0x18006d54a  lea     rcx, [rsp+58h+arg_8]
0x18006d54f  call    wil__details__ScopeExitFn__lambda_785f71f0232c9392361b8da55dfbe788______ScopeExitFn__lambda_785f71f0232c9392361b8da55dfbe788___
0x18006d554  xor     eax, eax
0x18006d556  jmp     short loc_18006D55C
0x18006d558  mov     eax, [rsp+58h+arg_8]
0x18006d55c  mov     rbx, [rsp+58h+arg_0]
0x18006d561  mov     rsi, [rsp+58h+arg_10]
0x18006d566  add     rsp, 30h
0x18006d56a  pop     r15
0x18006d56c  pop     r14
0x18006d56e  pop     r13
0x18006d570  pop     r12
0x18006d572  pop     rdi
0x18006d573  retn
```
