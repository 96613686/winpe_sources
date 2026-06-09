# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,__int64 &)

- ea: `0x1801dc598`
- end: `0x1801dc83e`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEA_J@Z`
- size: `678`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1801dd69c`

## callees

- `0x180026ecc`
- `0x18012de40`
- `0x18012eb08`
- `0x1801d14a0`
- `0x1801d314c`
- `0x1801d3218`
- `0x1801dc598`
- `0x1801e4978`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1801dc790`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1801dc790`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dc6db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dc803`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dc6db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dc803`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801dc5f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801dc5f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801dc719`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801dc719`

## string_xrefs

- `0x1801dc619`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801dc73c`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801dc7a9`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801dc651`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1801dc6b4`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1801dc75f`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const wchar_t *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  int *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  char v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h]
  __int64 v24; // [rsp+260h] [rbp+160h]
  _BYTE *v25; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v20 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v17 = 0;
  v18 = (int *)&v17;
  v19 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v16[0]);
    v7 = 1128;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v16[0]);
    goto LABEL_22;
  }
  if ( !v17 )
  {
    v6 = -2140733422;
    v7 = 1129;
    goto LABEL_5;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    goto LABEL_8;
  }
  v18 = v16;
  *(_QWORD *)v16 = 0;
  v19 = 0;
  v20 = 1;
  v6 = SRCacheContext_OpenSubContext(v17, v25, 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v16[0]);
    v10 = 1136;
LABEL_12:
    v11 = v6;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v11,
      v16[0]);
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v16, 0);
LABEL_8:
    v9 = v21;
    v21 = 0;
    if ( v9 )
      SRCache_Free();
    goto LABEL_22;
  }
  if ( *(_QWORD *)v16 )
  {
    v12 = SRCacheContext_EnumerateData(*(_QWORD *)v16, 0, a3);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v16[0]);
      v10 = 1139;
      goto LABEL_12;
    }
  }
  v13 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)&v17,
          L"Package\\Index\\PackageFullName");
  v6 = v13;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v10 = 1142;
    goto LABEL_13;
  }
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v16, 0);
  v14 = v21;
  v21 = 0;
  if ( v14 )
    SRCache_Free();
  v6 = 0;
LABEL_22:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v17, 0);
  return v6;
}

```

## disassembly

```asm
0x1801dc598  push    rbp
0x1801dc59a  push    rbx
0x1801dc59b  push    rsi
0x1801dc59c  push    rdi
0x1801dc59d  push    r14
0x1801dc59f  lea     rbp, [rsp-180h]
0x1801dc5a7  sub     rsp, 280h
0x1801dc5ae  mov     rax, cs:__security_cookie
0x1801dc5b5  xor     rax, rsp
0x1801dc5b8  mov     [rbp+1A0h+var_30], rax
0x1801dc5bf  xor     r14d, r14d
0x1801dc5c2  mov     [rsp+2A0h+var_260], 1
0x1801dc5c7  mov     [r8], r14
0x1801dc5ca  lea     rax, [rsp+2A0h+var_278]
0x1801dc5cf  mov     rcx, [rcx]
0x1801dc5d2  lea     r9, [rsp+2A0h+var_268]
0x1801dc5d7  mov     rdi, r8
0x1801dc5da  mov     [rsp+2A0h+var_278], r14
0x1801dc5df  mov     rsi, rdx
0x1801dc5e2  mov     [rsp+2A0h+var_270], rax
0x1801dc5e7  xor     r8d, r8d
0x1801dc5ea  mov     [rsp+2A0h+var_268], r14
0x1801dc5ef  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x1801dc5f6  call    cs:__imp_SRCacheContext_Open
0x1801dc5fd  nop     dword ptr [rax+rax+00h]
0x1801dc602  lea     rcx, [rsp+2A0h+var_270]
0x1801dc607  mov     ebx, eax
0x1801dc609  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801dc60e  test    ebx, ebx
0x1801dc610  jns     short loc_1801DC634
0x1801dc612  mov     rcx, [rbp+1A8h]; this
0x1801dc619  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc620  mov     r9d, ebx; char *
0x1801dc623  mov     edx, 18Ch; void *
0x1801dc628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc62d  mov     edx, 468h
0x1801dc632  jmp     short loc_1801DC64A
0x1801dc634  cmp     [rsp+2A0h+var_278], r14
0x1801dc639  setnz   al
0x1801dc63c  test    al, al
0x1801dc63e  jnz     short loc_1801DC665
0x1801dc640  mov     ebx, 80670012h
0x1801dc645  mov     edx, 469h; void *
0x1801dc64a  mov     rcx, [rbp+1A8h]; this
0x1801dc651  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc658  mov     r9d, ebx; char *
0x1801dc65b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc660  jmp     loc_1801DC812
0x1801dc665  xor     edx, edx; Val
0x1801dc667  mov     [rsp+2A0h+var_250], r14
0x1801dc66c  mov     r8d, 200h; Size
0x1801dc672  lea     rcx, [rsp+2A0h+var_248]; void *
0x1801dc677  call    memset_0
0x1801dc67c  lea     rax, [rsp+2A0h+var_248]
0x1801dc681  mov     [rbp+1A0h+var_48], r14
0x1801dc688  mov     rdx, rsi; wchar_t *
0x1801dc68b  mov     [rbp+1A0h+var_38], rax
0x1801dc692  lea     rcx, [rsp+2A0h+var_250]; this
0x1801dc697  mov     [rbp+1A0h+var_40], 100h
0x1801dc6a2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1801dc6a7  mov     ebx, eax
0x1801dc6a9  test    eax, eax
0x1801dc6ab  jns     short loc_1801DC6EC
0x1801dc6ad  mov     rcx, [rbp+1A8h]; this
0x1801dc6b4  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc6bb  mov     r9d, eax; char *
0x1801dc6be  mov     edx, 46Ch; void *
0x1801dc6c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc6c8  mov     rcx, [rsp+2A0h+var_250]
0x1801dc6cd  mov     [rsp+2A0h+var_250], r14
0x1801dc6d2  test    rcx, rcx
0x1801dc6d5  jz      loc_1801DC812
0x1801dc6db  call    cs:__imp_SRCache_Free
0x1801dc6e2  nop     dword ptr [rax+rax+00h]
0x1801dc6e7  jmp     loc_1801DC812
0x1801dc6ec  mov     rdx, [rbp+1A0h+var_38]
0x1801dc6f3  lea     rax, [rsp+2A0h+var_280]
0x1801dc6f8  mov     rcx, [rsp+2A0h+var_278]
0x1801dc6fd  lea     r9, [rsp+2A0h+var_268]
0x1801dc702  xor     r8d, r8d
0x1801dc705  mov     [rsp+2A0h+var_270], rax
0x1801dc70a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x1801dc70f  mov     [rsp+2A0h+var_268], r14
0x1801dc714  mov     [rsp+2A0h+var_260], 1
0x1801dc719  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801dc720  nop     dword ptr [rax+rax+00h]
0x1801dc725  lea     rcx, [rsp+2A0h+var_270]
0x1801dc72a  mov     ebx, eax
0x1801dc72c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801dc731  test    ebx, ebx
0x1801dc733  jns     short loc_1801DC77C
0x1801dc735  mov     rcx, [rbp+1A8h]; this
0x1801dc73c  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc743  mov     r9d, ebx; char *
0x1801dc746  mov     edx, 1B0h; void *
0x1801dc74b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc750  mov     edx, 470h; void *
0x1801dc755  mov     r9d, ebx; char *
0x1801dc758  mov     rcx, [rbp+1A8h]; this
0x1801dc75f  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc76b  xor     edx, edx
0x1801dc76d  lea     rcx, [rsp+2A0h+var_280]
0x1801dc772  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801dc777  jmp     loc_1801DC6C8
0x1801dc77c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1801dc781  test    rcx, rcx
0x1801dc784  setnz   al
0x1801dc787  test    al, al
0x1801dc789  jz      short loc_1801DC7C4
0x1801dc78b  mov     r8, rdi
0x1801dc78e  xor     edx, edx
0x1801dc790  call    cs:__imp_SRCacheContext_EnumerateData
0x1801dc797  nop     dword ptr [rax+rax+00h]
0x1801dc79c  mov     ebx, eax
0x1801dc79e  test    eax, eax
0x1801dc7a0  jns     short loc_1801DC7C4
0x1801dc7a2  mov     rcx, [rbp+1A8h]; this
0x1801dc7a9  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dc7b0  mov     r9d, eax; char *
0x1801dc7b3  mov     edx, 2A6h; void *
0x1801dc7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc7bd  mov     edx, 473h
0x1801dc7c2  jmp     short loc_1801DC755
0x1801dc7c4  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x1801dc7cb  lea     rcx, [rsp+2A0h+var_278]; this
0x1801dc7d0  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1801dc7d5  mov     ebx, eax
0x1801dc7d7  test    eax, eax
0x1801dc7d9  jns     short loc_1801DC7E8
0x1801dc7db  mov     r9d, eax
0x1801dc7de  mov     edx, 476h
0x1801dc7e3  jmp     loc_1801DC758
0x1801dc7e8  xor     edx, edx
0x1801dc7ea  lea     rcx, [rsp+2A0h+var_280]
0x1801dc7ef  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801dc7f4  mov     rcx, [rsp+2A0h+var_250]
0x1801dc7f9  mov     [rsp+2A0h+var_250], r14
0x1801dc7fe  test    rcx, rcx
0x1801dc801  jz      short loc_1801DC80F
0x1801dc803  call    cs:__imp_SRCache_Free
0x1801dc80a  nop     dword ptr [rax+rax+00h]
0x1801dc80f  mov     ebx, r14d
0x1801dc812  xor     edx, edx
0x1801dc814  lea     rcx, [rsp+2A0h+var_278]
0x1801dc819  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801dc81e  mov     eax, ebx
0x1801dc820  mov     rcx, [rbp+1A0h+var_30]
0x1801dc827  xor     rcx, rsp; StackCookie
0x1801dc82a  call    __security_check_cookie
0x1801dc82f  add     rsp, 280h
0x1801dc836  pop     r14
0x1801dc838  pop     rdi
0x1801dc839  pop     rsi
0x1801dc83a  pop     rbx
0x1801dc83b  pop     rbp
0x1801dc83c  retn
```
