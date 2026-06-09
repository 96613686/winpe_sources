# StateRepository::Cache::Entity::ApplicationUser_NoThrow::ExistsByUserAndApplication(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x180078a70`
- end: `0x180078d8e`
- name: `?ExistsByUserAndApplication@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `798`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180078874`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180034c24`
- `0x180037224`
- `0x180078a70`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078d52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078d52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078b6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078ccb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078d3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078d67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078b6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078ccb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078d3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078d67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180078c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180078c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180078b0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180078b0b`

## string_xrefs

- `0x180078b28`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180078c89`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180078ab9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180078b48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180078be1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180078ca9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::ExistsByUserAndApplication(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rdx
  int IsEmpty; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 v13; // dx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  char v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h]
  __int64 v30; // [rsp+260h] [rbp+160h]
  _BYTE *v31; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = 178;
LABEL_3:
    IsEmpty = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      v21);
    return (unsigned int)IsEmpty;
  }
  if ( !a3 )
  {
    v7 = 179;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  v24 = &v22;
  v22 = 0;
  v25 = 0;
  v26 = 1;
  IsEmpty = SRCacheContext_Open(v10, L"ApplicationUser\\Index\\UserAndApplication", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v21);
    v11 = 183;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v21);
LABEL_10:
    v12 = v22;
    v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)IsEmpty;
  }
  if ( !v22 )
  {
    IsEmpty = -2140733422;
    v11 = 184;
    goto LABEL_9;
  }
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v29 = 0;
  v31 = v28;
  v30 = 256;
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a2);
  if ( IsEmpty < 0 )
  {
    v14 = 187;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v21);
LABEL_17:
    v15 = v27;
    v27 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_10;
  }
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, v13);
  if ( IsEmpty < 0 )
  {
    v14 = 188;
    goto LABEL_16;
  }
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v27, a3);
  if ( IsEmpty < 0 )
  {
    v14 = 189;
    goto LABEL_16;
  }
  v24 = &v23;
  v23 = 0;
  v25 = 0;
  v26 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v22, v31, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v21);
    v16 = 193;
    goto LABEL_25;
  }
  if ( v23 )
  {
    LOBYTE(v21) = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty(
                (StateRepository::Cache::Context_NoThrow *)&v23,
                (bool *)&v21);
    if ( IsEmpty < 0 )
    {
      v16 = 197;
      goto LABEL_25;
    }
    *a4 = (_BYTE)v21 == 0;
  }
  IsEmpty = StateRepository::Cache::Context_NoThrow::AddToCache(
              (StateRepository::Cache::Context_NoThrow *)&v22,
              L"ApplicationUser\\Index\\UserAndApplication");
  if ( IsEmpty < 0 )
  {
    v16 = 201;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v21);
    v17 = v23;
    v23 = 0;
    if ( v17 )
      SRCacheContext_Close(v17);
    goto LABEL_17;
  }
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v27;
  v27 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = v22;
  v22 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x180078a70  push    rbp
0x180078a72  push    rbx
0x180078a73  push    rsi
0x180078a74  push    rdi
0x180078a75  push    r14
0x180078a77  push    r15
0x180078a79  lea     rbp, [rsp-188h]
0x180078a81  sub     rsp, 288h
0x180078a88  mov     rax, cs:__security_cookie
0x180078a8f  xor     rax, rsp
0x180078a92  mov     [rbp+1B0h+var_40], rax
0x180078a99  xor     r15d, r15d
0x180078a9c  mov     rsi, r9
0x180078a9f  mov     [r9], r15b
0x180078aa2  mov     rdi, r8
0x180078aa5  mov     r14, rdx
0x180078aa8  test    rdx, rdx
0x180078aab  jnz     short loc_180078AD4
0x180078aad  mov     edx, 0B2h; void *
0x180078ab2  mov     rcx, [rbp+1B8h]; this
0x180078ab9  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078ac0  mov     ebx, 80070057h
0x180078ac5  mov     r9d, ebx; char *
0x180078ac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078acd  mov     eax, ebx
0x180078acf  jmp     loc_180078D6F
0x180078ad4  test    rdi, rdi
0x180078ad7  jnz     short loc_180078AE0
0x180078ad9  mov     edx, 0B3h
0x180078ade  jmp     short loc_180078AB2
0x180078ae0  mov     rcx, [rcx]
0x180078ae3  lea     rax, [rsp+2B0h+var_288]
0x180078ae8  lea     r9, [rsp+2B0h+var_270]
0x180078aed  mov     [rsp+2B0h+var_278], rax
0x180078af2  xor     r8d, r8d
0x180078af5  mov     [rsp+2B0h+var_288], r15
0x180078afa  lea     rdx, aApplicationuse; "ApplicationUser\\Index\\UserAndApplicat"...
0x180078b01  mov     [rsp+2B0h+var_270], r15
0x180078b06  mov     [rsp+2B0h+var_268], 1
0x180078b0b  call    cs:__imp_SRCacheContext_Open
0x180078b11  lea     rcx, [rsp+2B0h+var_278]
0x180078b16  mov     ebx, eax
0x180078b18  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180078b1d  test    ebx, ebx
0x180078b1f  jns     short loc_180078B75
0x180078b21  mov     rcx, [rbp+1B8h]; this
0x180078b28  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078b2f  mov     r9d, ebx; char *
0x180078b32  mov     edx, 18Ch; void *
0x180078b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078b3c  mov     edx, 0B7h; void *
0x180078b41  mov     rcx, [rbp+1B8h]; this
0x180078b48  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078b4f  mov     r9d, ebx; char *
0x180078b52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078b57  mov     rcx, [rsp+2B0h+var_288]
0x180078b5c  mov     [rsp+2B0h+var_288], r15
0x180078b61  test    rcx, rcx
0x180078b64  jz      loc_180078ACD
0x180078b6a  call    cs:__imp_SRCacheContext_Close
0x180078b70  jmp     loc_180078ACD
0x180078b75  cmp     [rsp+2B0h+var_288], r15
0x180078b7a  setnz   al
0x180078b7d  test    al, al
0x180078b7f  jnz     short loc_180078B8D
0x180078b81  mov     ebx, 80670012h
0x180078b86  mov     edx, 0B8h
0x180078b8b  jmp     short loc_180078B41
0x180078b8d  xor     edx, edx; Val
0x180078b8f  mov     [rsp+2B0h+var_260], r15
0x180078b94  mov     r8d, 200h; Size
0x180078b9a  lea     rcx, [rsp+2B0h+var_258]; void *
0x180078b9f  call    memset_0
0x180078ba4  lea     rax, [rsp+2B0h+var_258]
0x180078ba9  mov     [rbp+1B0h+var_58], r15
0x180078bb0  mov     rdx, r14; unsigned __int64
0x180078bb3  mov     [rbp+1B0h+var_48], rax
0x180078bba  lea     rcx, [rsp+2B0h+var_260]; this
0x180078bbf  mov     [rbp+1B0h+var_50], 100h
0x180078bca  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180078bcf  mov     ebx, eax
0x180078bd1  test    eax, eax
0x180078bd3  jns     short loc_180078C0E
0x180078bd5  mov     edx, 0BBh; void *
0x180078bda  mov     rcx, [rbp+1B8h]; this
0x180078be1  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078be8  mov     r9d, ebx; char *
0x180078beb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078bf0  mov     rcx, [rsp+2B0h+var_260]
0x180078bf5  mov     [rsp+2B0h+var_260], r15
0x180078bfa  test    rcx, rcx
0x180078bfd  jz      loc_180078B57
0x180078c03  call    cs:__imp_SRCache_Free
0x180078c09  jmp     loc_180078B57
0x180078c0e  lea     rcx, [rsp+2B0h+var_260]; this
0x180078c13  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x180078c18  mov     ebx, eax
0x180078c1a  test    eax, eax
0x180078c1c  jns     short loc_180078C25
0x180078c1e  mov     edx, 0BCh
0x180078c23  jmp     short loc_180078BDA
0x180078c25  mov     rdx, rdi; unsigned __int64
0x180078c28  lea     rcx, [rsp+2B0h+var_260]; this
0x180078c2d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180078c32  mov     ebx, eax
0x180078c34  test    eax, eax
0x180078c36  jns     short loc_180078C3F
0x180078c38  mov     edx, 0BDh
0x180078c3d  jmp     short loc_180078BDA
0x180078c3f  mov     rdx, [rbp+1B0h+var_48]
0x180078c46  lea     rax, [rsp+2B0h+var_280]
0x180078c4b  mov     rcx, [rsp+2B0h+var_288]
0x180078c50  lea     r9, [rsp+2B0h+var_270]
0x180078c55  xor     r8d, r8d
0x180078c58  mov     [rsp+2B0h+var_278], rax
0x180078c5d  mov     [rsp+2B0h+var_280], r15
0x180078c62  mov     [rsp+2B0h+var_270], r15
0x180078c67  mov     [rsp+2B0h+var_268], 1
0x180078c6c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180078c72  lea     rcx, [rsp+2B0h+var_278]
0x180078c77  mov     ebx, eax
0x180078c79  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180078c7e  test    ebx, ebx
0x180078c80  jns     short loc_180078CD6
0x180078c82  mov     rcx, [rbp+1B8h]; this
0x180078c89  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078c90  mov     r9d, ebx; char *
0x180078c93  mov     edx, 1B0h; void *
0x180078c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078c9d  mov     edx, 0C1h; void *
0x180078ca2  mov     rcx, [rbp+1B8h]; this
0x180078ca9  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078cb0  mov     r9d, ebx; char *
0x180078cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078cb8  mov     rcx, [rsp+2B0h+var_280]
0x180078cbd  mov     [rsp+2B0h+var_280], r15
0x180078cc2  test    rcx, rcx
0x180078cc5  jz      loc_180078BF0
0x180078ccb  call    cs:__imp_SRCacheContext_Close
0x180078cd1  jmp     loc_180078BF0
0x180078cd6  cmp     [rsp+2B0h+var_280], r15
0x180078cdb  setnz   al
0x180078cde  test    al, al
0x180078ce0  jz      short loc_180078D0D
0x180078ce2  lea     rdx, [rsp+2B0h+var_290]; bool *
0x180078ce7  mov     byte ptr [rsp+2B0h+var_290], r15b
0x180078cec  lea     rcx, [rsp+2B0h+var_280]; this
0x180078cf1  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x180078cf6  mov     ebx, eax
0x180078cf8  test    eax, eax
0x180078cfa  jns     short loc_180078D03
0x180078cfc  mov     edx, 0C5h
0x180078d01  jmp     short loc_180078CA2
0x180078d03  cmp     byte ptr [rsp+2B0h+var_290], r15b
0x180078d08  setz    al
0x180078d0b  mov     [rsi], al
0x180078d0d  lea     rdx, aApplicationuse; "ApplicationUser\\Index\\UserAndApplicat"...
0x180078d14  lea     rcx, [rsp+2B0h+var_288]; this
0x180078d19  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180078d1e  mov     ebx, eax
0x180078d20  test    eax, eax
0x180078d22  jns     short loc_180078D2E
0x180078d24  mov     edx, 0C9h
0x180078d29  jmp     loc_180078CA2
0x180078d2e  mov     rcx, [rsp+2B0h+var_280]
0x180078d33  mov     [rsp+2B0h+var_280], r15
0x180078d38  test    rcx, rcx
0x180078d3b  jz      short loc_180078D43
0x180078d3d  call    cs:__imp_SRCacheContext_Close
0x180078d43  mov     rcx, [rsp+2B0h+var_260]
0x180078d48  mov     [rsp+2B0h+var_260], r15
0x180078d4d  test    rcx, rcx
0x180078d50  jz      short loc_180078D58
0x180078d52  call    cs:__imp_SRCache_Free
0x180078d58  mov     rcx, [rsp+2B0h+var_288]
0x180078d5d  mov     [rsp+2B0h+var_288], r15
0x180078d62  test    rcx, rcx
0x180078d65  jz      short loc_180078D6D
0x180078d67  call    cs:__imp_SRCacheContext_Close
0x180078d6d  xor     eax, eax
0x180078d6f  mov     rcx, [rbp+1B0h+var_40]
0x180078d76  xor     rcx, rsp; StackCookie
0x180078d79  call    __security_check_cookie
0x180078d7e  add     rsp, 288h
0x180078d85  pop     r15
0x180078d87  pop     r14
0x180078d89  pop     rdi
0x180078d8a  pop     rsi
0x180078d8b  pop     rbx
0x180078d8c  pop     rbp
0x180078d8d  retn
```
