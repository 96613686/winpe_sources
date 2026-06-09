# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180066864`
- end: `0x180066afe`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180065128`
- `0x180065450`
- `0x180066144`
- `0x180067b6c`

## callees

- `0x180004cf0`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034540`
- `0x180066864`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800669b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180066ac4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800669b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180066ac4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006691d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066a4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066aaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066ad9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006691d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066a4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066aaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066ad9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800669f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800669f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800668c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800668c2`

## string_xrefs

- `0x1800668df`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180066a0d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800668ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180066991`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180066a2d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  int *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  char v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h]
  __int64 v25; // [rsp+260h] [rbp+160h]
  _BYTE *v26; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v21 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v17 = 0;
  v19 = v17;
  v20 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v7 = 193;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
LABEL_4:
    v8 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v17 )
  {
    v6 = -2140733422;
    v7 = 194;
    goto LABEL_3;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v10,
      v17[0]);
LABEL_11:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCache_Free(v11);
    goto LABEL_4;
  }
  v19 = (int *)&v18;
  v18 = 0;
  v20 = 0;
  v21 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v26, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v12 = 201;
    goto LABEL_15;
  }
  if ( v18 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v18, 0, a3);
    if ( v6 < 0 )
    {
      v12 = 204;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"PackageFamily\\Index\\PackageFamilyName");
  if ( v6 < 0 )
  {
    v12 = 207;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v13 = v18;
    v18 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_11;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v22;
  v22 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180066864  push    rbp
0x180066866  push    rbx
0x180066867  push    rsi
0x180066868  push    rdi
0x180066869  push    r14
0x18006686b  lea     rbp, [rsp-180h]
0x180066873  sub     rsp, 280h
0x18006687a  mov     rax, cs:__security_cookie
0x180066881  xor     rax, rsp
0x180066884  mov     [rbp+1A0h+var_30], rax
0x18006688b  xor     r14d, r14d
0x18006688e  mov     [rsp+2A0h+var_260], 1
0x180066893  mov     [r8], r14
0x180066896  lea     rax, [rsp+2A0h+var_280]
0x18006689b  mov     rcx, [rcx]
0x18006689e  lea     r9, [rsp+2A0h+var_268]
0x1800668a3  mov     rdi, r8
0x1800668a6  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x1800668ab  mov     rsi, rdx
0x1800668ae  mov     [rsp+2A0h+var_270], rax
0x1800668b3  xor     r8d, r8d
0x1800668b6  mov     [rsp+2A0h+var_268], r14
0x1800668bb  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x1800668c2  call    cs:__imp_SRCacheContext_Open
0x1800668c8  lea     rcx, [rsp+2A0h+var_270]
0x1800668cd  mov     ebx, eax
0x1800668cf  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800668d4  test    ebx, ebx
0x1800668d6  jns     short loc_18006692A
0x1800668d8  mov     rcx, [rbp+1A8h]; this
0x1800668df  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800668e6  mov     r9d, ebx; char *
0x1800668e9  mov     edx, 18Ch; void *
0x1800668ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800668f3  mov     edx, 0C1h; void *
0x1800668f8  mov     rcx, [rbp+1A8h]; this
0x1800668ff  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180066906  mov     r9d, ebx; char *
0x180066909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006690e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180066913  mov     qword ptr [rsp+2A0h+var_280], r14
0x180066918  test    rcx, rcx
0x18006691b  jz      short loc_180066923
0x18006691d  call    cs:__imp_SRCacheContext_Close
0x180066923  mov     eax, ebx
0x180066925  jmp     loc_180066AE1
0x18006692a  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18006692f  setnz   al
0x180066932  test    al, al
0x180066934  jnz     short loc_180066942
0x180066936  mov     ebx, 80670012h
0x18006693b  mov     edx, 0C2h
0x180066940  jmp     short loc_1800668F8
0x180066942  xor     edx, edx; Val
0x180066944  mov     [rsp+2A0h+var_250], r14
0x180066949  mov     r8d, 200h; Size
0x18006694f  lea     rcx, [rsp+2A0h+var_248]; void *
0x180066954  call    memset_0
0x180066959  lea     rax, [rsp+2A0h+var_248]
0x18006695e  mov     [rbp+1A0h+var_48], r14
0x180066965  mov     rdx, rsi; unsigned __int16 *
0x180066968  mov     [rbp+1A0h+var_38], rax
0x18006696f  lea     rcx, [rsp+2A0h+var_250]; this
0x180066974  mov     [rbp+1A0h+var_40], 100h
0x18006697f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180066984  mov     ebx, eax
0x180066986  test    eax, eax
0x180066988  jns     short loc_1800669C3
0x18006698a  mov     rcx, [rbp+1A8h]; this
0x180066991  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180066998  mov     r9d, eax; char *
0x18006699b  mov     edx, 0C5h; void *
0x1800669a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800669a5  mov     rcx, [rsp+2A0h+var_250]
0x1800669aa  mov     [rsp+2A0h+var_250], r14
0x1800669af  test    rcx, rcx
0x1800669b2  jz      loc_18006690E
0x1800669b8  call    cs:__imp_SRCache_Free
0x1800669be  jmp     loc_18006690E
0x1800669c3  mov     rdx, [rbp+1A0h+var_38]
0x1800669ca  lea     rax, [rsp+2A0h+var_278]
0x1800669cf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800669d4  lea     r9, [rsp+2A0h+var_268]
0x1800669d9  xor     r8d, r8d
0x1800669dc  mov     [rsp+2A0h+var_270], rax
0x1800669e1  mov     [rsp+2A0h+var_278], r14
0x1800669e6  mov     [rsp+2A0h+var_268], r14
0x1800669eb  mov     [rsp+2A0h+var_260], 1
0x1800669f0  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800669f6  lea     rcx, [rsp+2A0h+var_270]
0x1800669fb  mov     ebx, eax
0x1800669fd  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180066a02  test    ebx, ebx
0x180066a04  jns     short loc_180066A5A
0x180066a06  mov     rcx, [rbp+1A8h]; this
0x180066a0d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180066a14  mov     r9d, ebx; char *
0x180066a17  mov     edx, 1B0h; void *
0x180066a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066a21  mov     edx, 0C9h; void *
0x180066a26  mov     rcx, [rbp+1A8h]; this
0x180066a2d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180066a34  mov     r9d, ebx; char *
0x180066a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066a3c  mov     rcx, [rsp+2A0h+var_278]
0x180066a41  mov     [rsp+2A0h+var_278], r14
0x180066a46  test    rcx, rcx
0x180066a49  jz      loc_1800669A5
0x180066a4f  call    cs:__imp_SRCacheContext_Close
0x180066a55  jmp     loc_1800669A5
0x180066a5a  cmp     [rsp+2A0h+var_278], r14
0x180066a5f  setnz   al
0x180066a62  test    al, al
0x180066a64  jz      short loc_180066A82
0x180066a66  mov     r8, rdi; __int64 *
0x180066a69  lea     rcx, [rsp+2A0h+var_278]; this
0x180066a6e  xor     edx, edx; int
0x180066a70  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180066a75  mov     ebx, eax
0x180066a77  test    eax, eax
0x180066a79  jns     short loc_180066A82
0x180066a7b  mov     edx, 0CCh
0x180066a80  jmp     short loc_180066A26
0x180066a82  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180066a89  lea     rcx, [rsp+2A0h+var_280]; this
0x180066a8e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180066a93  mov     ebx, eax
0x180066a95  test    eax, eax
0x180066a97  jns     short loc_180066AA0
0x180066a99  mov     edx, 0CFh
0x180066a9e  jmp     short loc_180066A26
0x180066aa0  mov     rcx, [rsp+2A0h+var_278]
0x180066aa5  mov     [rsp+2A0h+var_278], r14
0x180066aaa  test    rcx, rcx
0x180066aad  jz      short loc_180066AB5
0x180066aaf  call    cs:__imp_SRCacheContext_Close
0x180066ab5  mov     rcx, [rsp+2A0h+var_250]
0x180066aba  mov     [rsp+2A0h+var_250], r14
0x180066abf  test    rcx, rcx
0x180066ac2  jz      short loc_180066ACA
0x180066ac4  call    cs:__imp_SRCache_Free
0x180066aca  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180066acf  mov     qword ptr [rsp+2A0h+var_280], r14
0x180066ad4  test    rcx, rcx
0x180066ad7  jz      short loc_180066ADF
0x180066ad9  call    cs:__imp_SRCacheContext_Close
0x180066adf  xor     eax, eax
0x180066ae1  mov     rcx, [rbp+1A0h+var_30]
0x180066ae8  xor     rcx, rsp; StackCookie
0x180066aeb  call    __security_check_cookie
0x180066af0  add     rsp, 280h
0x180066af7  pop     r14
0x180066af9  pop     rdi
0x180066afa  pop     rsi
0x180066afb  pop     rbx
0x180066afc  pop     rbp
0x180066afd  retn
```
