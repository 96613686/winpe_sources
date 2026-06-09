# StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x1800088c0`
- end: `0x180008c52`
- name: `?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `914`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180037230`
- `0x180039b88`

## callees

- `0x1800088c0`
- `0x180008c58`
- `0x180008eb0`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008981`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008981`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008a6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008a6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800089a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008af8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800089a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008a92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008af8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008b8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008bd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008c3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008bd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008c3d`

## string_xrefs

- `0x180008904`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800089d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008aca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008b0a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008baf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008be8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800089b6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008aa7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Get(
        __int64 *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v25[0]);
    return 2147942487LL;
  }
  v9 = *a1;
  v27 = v25;
  v26 = 0;
  *(_QWORD *)v25 = 0;
  v28 = 0;
  v29 = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Data", 0, &v28);
  if ( v29 )
  {
    v11 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v11 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v25[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v25[0]);
LABEL_16:
    v17 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v17 )
      SRCacheContext_Close(v17);
    v18 = 342;
    goto LABEL_19;
  }
  if ( !*(_QWORD *)v25 )
  {
    v10 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      0);
    goto LABEL_16;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v10 = v12;
  if ( v12 < 0 )
  {
    v14 = (unsigned int)v12;
    v15 = 437;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v14,
      v25[0]);
    v16 = v30;
    v30 = 0;
    if ( !v16 )
      goto LABEL_16;
LABEL_32:
    SRCache_Free();
    goto LABEL_16;
  }
  v27 = (int *)&v26;
  v28 = 0;
  v29 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
  if ( v29 )
  {
    v13 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v13 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v25[0]);
    v14 = (unsigned int)v10;
    v15 = 438;
    goto LABEL_15;
  }
  *a5 = v26 != 0;
  v24 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v25,
          L"Application\\Data");
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v24,
      v25[0]);
    v23 = v30;
    v30 = 0;
    if ( !v23 )
      goto LABEL_16;
    goto LABEL_32;
  }
  v20 = v30;
  v30 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  if ( *a5 )
  {
    v10 = StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
            (StateRepository::Cache::Context_NoThrow *)&v26,
            a4,
            a3,
            a2);
    if ( v10 < 0 )
    {
      v18 = 347;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
        (const char *)(unsigned int)v10,
        v25[0]);
      v19 = v26;
      v26 = 0;
      if ( v19 )
        SRCacheContext_Close(v19);
      return (unsigned int)v10;
    }
  }
  v22 = v26;
  v26 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
  return 0;
}

```

## disassembly

```asm
0x1800088c0  push    rbp
0x1800088c2  push    rsi
0x1800088c3  push    rdi
0x1800088c4  push    r14
0x1800088c6  push    r15
0x1800088c8  lea     rbp, [rsp-190h]
0x1800088d0  sub     rsp, 290h
0x1800088d7  mov     rax, cs:__security_cookie
0x1800088de  xor     rax, rsp
0x1800088e1  mov     [rbp+1B0h+var_40], rax
0x1800088e8  mov     rsi, [rbp+1B0h+arg_20]
0x1800088ef  mov     r15, r9
0x1800088f2  mov     r14, r8
0x1800088f5  mov     rdi, rdx
0x1800088f8  test    rdx, rdx
0x1800088fb  jnz     short loc_18000893E
0x1800088fd  mov     rcx, [rbp+1B8h]; this
0x180008904  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000890b  mov     r9d, 80070057h; char *
0x180008911  mov     edx, 153h; void *
0x180008916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000891b  mov     eax, 80070057h
0x180008920  mov     rcx, [rbp+1B0h+var_40]
0x180008927  xor     rcx, rsp; StackCookie
0x18000892a  call    __security_check_cookie
0x18000892f  add     rsp, 290h
0x180008936  pop     r15
0x180008938  pop     r14
0x18000893a  pop     rdi
0x18000893b  pop     rsi
0x18000893c  pop     rbp
0x18000893d  retn
0x18000893e  mov     rcx, [rcx]
0x180008941  lea     rax, [rsp+2B0h+var_290]
0x180008946  mov     [rsp+2B0h+var_28], rbx
0x18000894e  lea     r9, [rsp+2B0h+var_278]
0x180008953  mov     [rsp+2B0h+var_30], r12
0x18000895b  lea     rdx, aApplicationDat; "Application\\Data"
0x180008962  xor     r12d, r12d
0x180008965  mov     [rsp+2B0h+var_280], rax
0x18000896a  xor     r8d, r8d
0x18000896d  mov     [rsp+2B0h+var_288], r12
0x180008972  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x180008977  mov     [rsp+2B0h+var_278], r12
0x18000897c  mov     [rsp+2B0h+var_270], 1
0x180008981  call    cs:__imp_SRCacheContext_Open
0x180008987  mov     ebx, eax
0x180008989  cmp     [rsp+2B0h+var_270], r12b
0x18000898e  jz      short loc_1800089AB
0x180008990  mov     rdx, [rsp+2B0h+var_280]
0x180008995  mov     rax, [rsp+2B0h+var_278]
0x18000899a  mov     rcx, [rdx]
0x18000899d  mov     [rdx], rax
0x1800089a0  test    rcx, rcx
0x1800089a3  jz      short loc_1800089AB
0x1800089a5  call    cs:__imp_SRCacheContext_Close
0x1800089ab  test    ebx, ebx
0x1800089ad  jns     short loc_1800089EA
0x1800089af  mov     rcx, [rbp+1B8h]; this
0x1800089b6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800089bd  mov     r9d, ebx; char *
0x1800089c0  mov     edx, 18Ch; void *
0x1800089c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089ca  mov     rcx, [rbp+1B8h]; this
0x1800089d1  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800089d8  mov     r9d, ebx; char *
0x1800089db  mov     edx, 1B1h; void *
0x1800089e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089e5  jmp     loc_180008AE9
0x1800089ea  cmp     qword ptr [rsp+2B0h+var_290], r12
0x1800089ef  setnz   al
0x1800089f2  test    al, al
0x1800089f4  jz      loc_180008BE1
0x1800089fa  xor     edx, edx; Val
0x1800089fc  mov     [rsp+2B0h+var_260], r12
0x180008a01  mov     r8d, 200h; Size
0x180008a07  lea     rcx, [rsp+2B0h+var_258]; void *
0x180008a0c  call    memset_0
0x180008a11  lea     rax, [rsp+2B0h+var_258]
0x180008a16  mov     [rbp+1B0h+var_58], r12
0x180008a1d  mov     rdx, rdi; unsigned __int64
0x180008a20  mov     [rbp+1B0h+var_48], rax
0x180008a27  lea     rcx, [rsp+2B0h+var_260]; this
0x180008a2c  mov     [rbp+1B0h+var_50], 100h
0x180008a37  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180008a3c  mov     ebx, eax
0x180008a3e  test    eax, eax
0x180008a40  js      loc_180008C06
0x180008a46  mov     rdx, [rbp+1B0h+var_48]
0x180008a4d  lea     rax, [rsp+2B0h+var_288]
0x180008a52  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008a57  lea     r9, [rsp+2B0h+var_278]
0x180008a5c  xor     r8d, r8d
0x180008a5f  mov     [rsp+2B0h+var_280], rax
0x180008a64  mov     [rsp+2B0h+var_278], r12
0x180008a69  mov     [rsp+2B0h+var_270], 1
0x180008a6e  call    cs:__imp_SRCacheContext_OpenSubContext
0x180008a74  mov     ebx, eax
0x180008a76  cmp     [rsp+2B0h+var_270], r12b
0x180008a7b  jz      short loc_180008A98
0x180008a7d  mov     rdx, [rsp+2B0h+var_280]
0x180008a82  mov     rax, [rsp+2B0h+var_278]
0x180008a87  mov     rcx, [rdx]
0x180008a8a  mov     [rdx], rax
0x180008a8d  test    rcx, rcx
0x180008a90  jz      short loc_180008A98
0x180008a92  call    cs:__imp_SRCacheContext_Close
0x180008a98  test    ebx, ebx
0x180008a9a  jns     loc_180008C13
0x180008aa0  mov     rcx, [rbp+1B8h]; this
0x180008aa7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008aae  mov     r9d, ebx; char *
0x180008ab1  mov     edx, 1B0h; void *
0x180008ab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008abb  mov     r9d, ebx; char *
0x180008abe  mov     edx, 1B6h; void *
0x180008ac3  mov     rcx, [rbp+1B8h]; this
0x180008aca  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ad6  mov     rcx, [rsp+2B0h+var_260]
0x180008adb  mov     [rsp+2B0h+var_260], r12
0x180008ae0  test    rcx, rcx
0x180008ae3  jnz     loc_180008BD6
0x180008ae9  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008aee  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x180008af3  test    rcx, rcx
0x180008af6  jz      short loc_180008AFE
0x180008af8  call    cs:__imp_SRCacheContext_Close
0x180008afe  mov     edx, 156h; void *
0x180008b03  mov     rcx, [rbp+1B8h]; this
0x180008b0a  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008b11  mov     r9d, ebx; char *
0x180008b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b19  mov     rcx, [rsp+2B0h+var_288]
0x180008b1e  mov     [rsp+2B0h+var_288], r12
0x180008b23  test    rcx, rcx
0x180008b26  jz      short loc_180008B2E
0x180008b28  call    cs:__imp_SRCacheContext_Close
0x180008b2e  mov     eax, ebx
0x180008b30  jmp     short loc_180008B93
0x180008b32  mov     rcx, [rsp+2B0h+var_260]
0x180008b37  mov     [rsp+2B0h+var_260], r12
0x180008b3c  test    rcx, rcx
0x180008b3f  jnz     loc_180008C3D
0x180008b45  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180008b4a  mov     qword ptr [rsp+2B0h+var_290], r12
0x180008b4f  test    rcx, rcx
0x180008b52  jz      short loc_180008B5A
0x180008b54  call    cs:__imp_SRCacheContext_Close
0x180008b5a  cmp     [rsi], r12b
0x180008b5d  jz      short loc_180008B7C
0x180008b5f  mov     r9, rdi
0x180008b62  lea     rcx, [rsp+2B0h+var_288]
0x180008b67  mov     r8, r14
0x180008b6a  mov     rdx, r15
0x180008b6d  call    ?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)
0x180008b72  mov     ebx, eax
0x180008b74  test    eax, eax
0x180008b76  js      loc_180008C48
0x180008b7c  mov     rcx, [rsp+2B0h+var_288]
0x180008b81  mov     [rsp+2B0h+var_288], r12
0x180008b86  test    rcx, rcx
0x180008b89  jz      short loc_180008B91
0x180008b8b  call    cs:__imp_SRCacheContext_Close
0x180008b91  xor     eax, eax
0x180008b93  mov     rbx, [rsp+2B0h+var_28]
0x180008b9b  mov     r12, [rsp+2B0h+var_30]
0x180008ba3  jmp     loc_180008920
0x180008ba8  mov     rcx, [rbp+1B8h]; this
0x180008baf  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008bb6  mov     r9d, eax; char *
0x180008bb9  mov     edx, 1B8h; void *
0x180008bbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bc3  mov     rcx, [rsp+2B0h+var_260]
0x180008bc8  mov     [rsp+2B0h+var_260], r12
0x180008bcd  test    rcx, rcx
0x180008bd0  jz      loc_180008AE9
0x180008bd6  call    cs:__imp_SRCache_Free
0x180008bdc  jmp     loc_180008AE9
0x180008be1  mov     rcx, [rbp+1B8h]; this
0x180008be8  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008bef  mov     ebx, 80670012h
0x180008bf4  mov     edx, 1B2h; void *
0x180008bf9  mov     r9d, ebx; char *
0x180008bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c01  jmp     loc_180008AE9
0x180008c06  mov     r9d, eax
0x180008c09  mov     edx, 1B5h
0x180008c0e  jmp     loc_180008AC3
0x180008c13  cmp     [rsp+2B0h+var_288], r12
0x180008c18  lea     rdx, aApplicationDat; "Application\\Data"
0x180008c1f  lea     rcx, [rsp+2B0h+var_290]; this
0x180008c24  setnz   al
0x180008c27  mov     [rsi], al
0x180008c29  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180008c2e  mov     ebx, eax
0x180008c30  test    eax, eax
0x180008c32  jns     loc_180008B32
0x180008c38  jmp     loc_180008BA8
0x180008c3d  call    cs:__imp_SRCache_Free
0x180008c43  jmp     loc_180008B45
0x180008c48  mov     edx, 15Bh
0x180008c4d  jmp     loc_180008B03
```
