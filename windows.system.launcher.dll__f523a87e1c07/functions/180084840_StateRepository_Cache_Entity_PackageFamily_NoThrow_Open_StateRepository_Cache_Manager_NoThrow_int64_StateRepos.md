# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180084840`
- end: `0x180084a7d`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d7aec`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180084840`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084999`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084a3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084999`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084a3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800848fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084a4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800848fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084a4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800849c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800849c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800848a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800848a3`

## string_xrefs

- `0x1800848c0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800849e4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800848e0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180084977`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageFamily\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 257;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 258;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 261;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 262;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageFamily\\Data");
  if ( v8 < 0 )
  {
    v12 = 264;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x180084840  mov     [rsp-8+arg_10], rbx
0x180084845  push    rbp
0x180084846  push    rsi
0x180084847  push    rdi
0x180084848  push    r14
0x18008484a  push    r15
0x18008484c  lea     rbp, [rsp-170h]
0x180084854  sub     rsp, 270h
0x18008485b  mov     rax, cs:__security_cookie
0x180084862  xor     rax, rsp
0x180084865  mov     [rbp+190h+var_30], rax
0x18008486c  mov     rcx, [rcx]
0x18008486f  lea     rax, [rsp+290h+var_270]
0x180084874  mov     rsi, r9
0x180084877  mov     [rsp+290h+var_268], rax
0x18008487c  mov     rdi, r8
0x18008487f  mov     [rsp+290h+var_258], 1
0x180084884  mov     r14, rdx
0x180084887  lea     r9, [rsp+290h+var_260]
0x18008488c  xor     r15d, r15d
0x18008488f  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x180084896  xor     r8d, r8d
0x180084899  mov     qword ptr [rsp+290h+var_270], r15; int
0x18008489e  mov     [rsp+290h+var_260], r15
0x1800848a3  call    cs:__imp_SRCacheContext_Open
0x1800848a9  lea     rcx, [rsp+290h+var_268]
0x1800848ae  mov     ebx, eax
0x1800848b0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800848b5  test    ebx, ebx
0x1800848b7  jns     short loc_18008490B
0x1800848b9  mov     rcx, [rbp+198h]; this
0x1800848c0  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800848c7  mov     r9d, ebx; char *
0x1800848ca  mov     edx, 18Ch; void *
0x1800848cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800848d4  mov     edx, 101h; void *
0x1800848d9  mov     rcx, [rbp+198h]; this
0x1800848e0  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800848e7  mov     r9d, ebx; char *
0x1800848ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800848ef  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800848f4  mov     qword ptr [rsp+290h+var_270], r15
0x1800848f9  test    rcx, rcx
0x1800848fc  jz      short loc_180084904
0x1800848fe  call    cs:__imp_SRCacheContext_Close
0x180084904  mov     eax, ebx
0x180084906  jmp     loc_180084A57
0x18008490b  cmp     qword ptr [rsp+290h+var_270], r15
0x180084910  setnz   al
0x180084913  test    al, al
0x180084915  jnz     short loc_180084923
0x180084917  mov     ebx, 80670012h
0x18008491c  mov     edx, 102h
0x180084921  jmp     short loc_1800848D9
0x180084923  xor     edx, edx; Val
0x180084925  mov     [rsp+290h+var_250], r15
0x18008492a  mov     r8d, 200h; Size
0x180084930  lea     rcx, [rsp+290h+var_248]; void *
0x180084935  call    memset_0
0x18008493a  lea     rax, [rsp+290h+var_248]
0x18008493f  mov     [rbp+190h+var_48], r15
0x180084946  mov     rdx, r14; unsigned __int64
0x180084949  mov     [rbp+190h+var_38], rax
0x180084950  lea     rcx, [rsp+290h+var_250]; this
0x180084955  mov     [rbp+190h+var_40], 100h
0x180084960  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180084965  mov     ebx, eax
0x180084967  test    eax, eax
0x180084969  jns     short loc_1800849A4
0x18008496b  mov     edx, 105h; void *
0x180084970  mov     rcx, [rbp+198h]; this
0x180084977  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008497e  mov     r9d, ebx; char *
0x180084981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084986  mov     rcx, [rsp+290h+var_250]
0x18008498b  mov     [rsp+290h+var_250], r15
0x180084990  test    rcx, rcx
0x180084993  jz      loc_1800848EF
0x180084999  call    cs:__imp_SRCache_Free
0x18008499f  jmp     loc_1800848EF
0x1800849a4  mov     rdx, [rbp+190h+var_38]
0x1800849ab  lea     r9, [rsp+290h+var_260]
0x1800849b0  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800849b5  xor     r8d, r8d
0x1800849b8  mov     [rsp+290h+var_268], rdi
0x1800849bd  mov     [rsp+290h+var_260], r15
0x1800849c2  mov     [rsp+290h+var_258], 1
0x1800849c7  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800849cd  lea     rcx, [rsp+290h+var_268]
0x1800849d2  mov     ebx, eax
0x1800849d4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800849d9  test    ebx, ebx
0x1800849db  jns     short loc_180084A02
0x1800849dd  mov     rcx, [rbp+198h]; this
0x1800849e4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800849eb  mov     r9d, ebx; char *
0x1800849ee  mov     edx, 1B0h; void *
0x1800849f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800849f8  mov     edx, 106h
0x1800849fd  jmp     loc_180084970
0x180084a02  cmp     [rdi], r15
0x180084a05  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x180084a0c  lea     rcx, [rsp+290h+var_270]; this
0x180084a11  setnz   al
0x180084a14  mov     [rsi], al
0x180084a16  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180084a1b  mov     ebx, eax
0x180084a1d  test    eax, eax
0x180084a1f  jns     short loc_180084A2B
0x180084a21  mov     edx, 108h
0x180084a26  jmp     loc_180084970
0x180084a2b  mov     rcx, [rsp+290h+var_250]
0x180084a30  mov     [rsp+290h+var_250], r15
0x180084a35  test    rcx, rcx
0x180084a38  jz      short loc_180084A40
0x180084a3a  call    cs:__imp_SRCache_Free
0x180084a40  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084a45  mov     qword ptr [rsp+290h+var_270], r15
0x180084a4a  test    rcx, rcx
0x180084a4d  jz      short loc_180084A55
0x180084a4f  call    cs:__imp_SRCacheContext_Close
0x180084a55  xor     eax, eax
0x180084a57  mov     rcx, [rbp+190h+var_30]
0x180084a5e  xor     rcx, rsp; StackCookie
0x180084a61  call    __security_check_cookie
0x180084a66  mov     rbx, [rsp+290h+arg_10]
0x180084a6e  add     rsp, 270h
0x180084a75  pop     r15
0x180084a77  pop     r14
0x180084a79  pop     rdi
0x180084a7a  pop     rsi
0x180084a7b  pop     rbp
0x180084a7c  retn
```
