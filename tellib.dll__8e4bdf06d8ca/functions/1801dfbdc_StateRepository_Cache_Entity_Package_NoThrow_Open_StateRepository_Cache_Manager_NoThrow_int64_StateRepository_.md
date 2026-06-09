# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1801dfbdc`
- end: `0x1801dfe82`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1801db674`

## callees

- `0x180026ecc`
- `0x18012de40`
- `0x18012eb08`
- `0x1801d14a0`
- `0x1801d314c`
- `0x1801d3218`
- `0x1801dfbdc`
- `0x1801e4978`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801dfd0a`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801dfd0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dfd85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dfe48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dfd85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801dfe48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801dfc47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801dfc47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801dfdc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1801dfdc5`

## string_xrefs

- `0x1801dfd21`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1801dfc6c`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801dfdea`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801dfca5`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1801dfd62`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+238h] [rbp+138h]
  __int64 v20; // [rsp+240h] [rbp+140h]
  _BYTE *v21; // [rsp+248h] [rbp+148h]
  wchar_t v22[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h] BYREF
  char v24; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v22 = v16;
  *(_QWORD *)v16 = 0;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 1192;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    goto LABEL_20;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 1193;
    goto LABEL_5;
  }
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 256;
  v21 = v18;
  if ( (unsigned int)_o__ui64tow_s(a2, v22, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v16[0]);
LABEL_9:
    v10 = 1196;
LABEL_10:
    v11 = (unsigned int)v8;
    goto LABEL_11;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v17, v22);
  if ( v8 < 0 )
    goto LABEL_9;
  *(_QWORD *)v22 = a3;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v21, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v10 = 1197;
    goto LABEL_10;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v13 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v16,
          L"Package\\Data");
  v8 = v13;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v10 = 1199;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v11,
      v16[0]);
    v12 = v17;
    v17 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_20;
  }
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCache_Free();
  v8 = 0;
LABEL_20:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v16, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801dfbdc  push    rbp
0x1801dfbde  push    rbx
0x1801dfbdf  push    rsi
0x1801dfbe0  push    rdi
0x1801dfbe1  push    r14
0x1801dfbe3  lea     rbp, [rsp-180h]
0x1801dfbeb  sub     rsp, 280h
0x1801dfbf2  mov     rax, cs:__security_cookie
0x1801dfbf9  xor     rax, rsp
0x1801dfbfc  mov     [rbp+1A0h+var_28], rax
0x1801dfc03  mov     rcx, [rcx]
0x1801dfc06  lea     rax, [rsp+2A0h+var_280]
0x1801dfc0b  mov     rsi, r9
0x1801dfc0e  mov     qword ptr [rbp+1A0h+var_50], rax
0x1801dfc15  mov     rdi, r8
0x1801dfc18  mov     qword ptr [rsp+2A0h+var_280], 0; int
0x1801dfc21  mov     r14, rdx
0x1801dfc24  mov     [rbp+1A0h+var_48], 0
0x1801dfc2f  lea     r9, [rbp+1A0h+var_48]
0x1801dfc36  mov     [rbp+1A0h+var_40], 1
0x1801dfc3d  xor     r8d, r8d
0x1801dfc40  lea     rdx, aPackageData; "Package\\Data"
0x1801dfc47  call    cs:__imp_SRCacheContext_Open
0x1801dfc4e  nop     dword ptr [rax+rax+00h]
0x1801dfc53  lea     rcx, [rbp+1A0h+var_50]
0x1801dfc5a  mov     ebx, eax
0x1801dfc5c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801dfc61  test    ebx, ebx
0x1801dfc63  jns     short loc_1801DFC87
0x1801dfc65  mov     rcx, [rbp+1A8h]; this
0x1801dfc6c  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dfc73  mov     r9d, ebx; char *
0x1801dfc76  mov     edx, 18Ch; void *
0x1801dfc7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dfc80  mov     edx, 4A8h
0x1801dfc85  jmp     short loc_1801DFC9E
0x1801dfc87  cmp     qword ptr [rsp+2A0h+var_280], 0
0x1801dfc8d  setnz   al
0x1801dfc90  test    al, al
0x1801dfc92  jnz     short loc_1801DFCB9
0x1801dfc94  mov     ebx, 80670012h
0x1801dfc99  mov     edx, 4A9h; void *
0x1801dfc9e  mov     rcx, [rbp+1A8h]; this
0x1801dfca5  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dfcac  mov     r9d, ebx; char *
0x1801dfcaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dfcb4  jmp     loc_1801DFE56
0x1801dfcb9  xor     edx, edx; Val
0x1801dfcbb  mov     [rsp+2A0h+var_270], 0
0x1801dfcc4  mov     r8d, 200h; Size
0x1801dfcca  lea     rcx, [rsp+2A0h+var_268]; void *
0x1801dfccf  call    memset_0
0x1801dfcd4  mov     r9d, 10h
0x1801dfcda  mov     [rbp+1A0h+var_68], 0
0x1801dfce5  lea     rax, [rsp+2A0h+var_268]
0x1801dfcea  mov     [rbp+1A0h+var_60], 100h
0x1801dfcf5  lea     rdx, [rbp+1A0h+var_50]
0x1801dfcfc  mov     [rbp+1A0h+var_58], rax
0x1801dfd03  mov     rcx, r14
0x1801dfd06  lea     r8d, [r9+1]
0x1801dfd0a  call    cs:__imp__o__ui64tow_s
0x1801dfd11  nop     dword ptr [rax+rax+00h]
0x1801dfd16  test    eax, eax
0x1801dfd18  jz      short loc_1801DFD3C
0x1801dfd1a  mov     rcx, [rbp+1A8h]; this
0x1801dfd21  lea     r8, aOnecorePrivate_2; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dfd28  mov     ebx, 8000FFFFh
0x1801dfd2d  mov     edx, 166h; void *
0x1801dfd32  mov     r9d, ebx; char *
0x1801dfd35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dfd3a  jmp     short loc_1801DFD53
0x1801dfd3c  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1801dfd43  lea     rcx, [rsp+2A0h+var_270]; this
0x1801dfd48  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1801dfd4d  mov     ebx, eax
0x1801dfd4f  test    eax, eax
0x1801dfd51  jns     short loc_1801DFD96
0x1801dfd53  mov     edx, 4ACh; void *
0x1801dfd58  mov     r9d, ebx; char *
0x1801dfd5b  mov     rcx, [rbp+1A8h]; this
0x1801dfd62  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dfd69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dfd6e  mov     rcx, [rsp+2A0h+var_270]
0x1801dfd73  mov     [rsp+2A0h+var_270], 0
0x1801dfd7c  test    rcx, rcx
0x1801dfd7f  jz      loc_1801DFE56
0x1801dfd85  call    cs:__imp_SRCache_Free
0x1801dfd8c  nop     dword ptr [rax+rax+00h]
0x1801dfd91  jmp     loc_1801DFE56
0x1801dfd96  mov     rdx, [rbp+1A0h+var_58]
0x1801dfd9d  lea     r9, [rbp+1A0h+var_48]
0x1801dfda4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1801dfda9  xor     r8d, r8d
0x1801dfdac  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1801dfdb3  mov     [rbp+1A0h+var_48], 0
0x1801dfdbe  mov     [rbp+1A0h+var_40], 1
0x1801dfdc5  call    cs:__imp_SRCacheContext_OpenSubContext
0x1801dfdcc  nop     dword ptr [rax+rax+00h]
0x1801dfdd1  lea     rcx, [rbp+1A0h+var_50]
0x1801dfdd8  mov     ebx, eax
0x1801dfdda  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801dfddf  test    ebx, ebx
0x1801dfde1  jns     short loc_1801DFE08
0x1801dfde3  mov     rcx, [rbp+1A8h]; this
0x1801dfdea  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1801dfdf1  mov     r9d, ebx; char *
0x1801dfdf4  mov     edx, 1B0h; void *
0x1801dfdf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dfdfe  mov     edx, 4ADh
0x1801dfe03  jmp     loc_1801DFD58
0x1801dfe08  cmp     qword ptr [rdi], 0
0x1801dfe0c  lea     rdx, aPackageData; "Package\\Data"
0x1801dfe13  lea     rcx, [rsp+2A0h+var_280]; this
0x1801dfe18  setnz   al
0x1801dfe1b  mov     [rsi], al
0x1801dfe1d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1801dfe22  mov     ebx, eax
0x1801dfe24  test    eax, eax
0x1801dfe26  jns     short loc_1801DFE35
0x1801dfe28  mov     r9d, eax
0x1801dfe2b  mov     edx, 4AFh
0x1801dfe30  jmp     loc_1801DFD5B
0x1801dfe35  mov     rcx, [rsp+2A0h+var_270]
0x1801dfe3a  mov     [rsp+2A0h+var_270], 0
0x1801dfe43  test    rcx, rcx
0x1801dfe46  jz      short loc_1801DFE54
0x1801dfe48  call    cs:__imp_SRCache_Free
0x1801dfe4f  nop     dword ptr [rax+rax+00h]
0x1801dfe54  xor     ebx, ebx
0x1801dfe56  xor     edx, edx
0x1801dfe58  lea     rcx, [rsp+2A0h+var_280]
0x1801dfe5d  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801dfe62  mov     eax, ebx
0x1801dfe64  mov     rcx, [rbp+1A0h+var_28]
0x1801dfe6b  xor     rcx, rsp; StackCookie
0x1801dfe6e  call    __security_check_cookie
0x1801dfe73  add     rsp, 280h
0x1801dfe7a  pop     r14
0x1801dfe7c  pop     rdi
0x1801dfe7d  pop     rsi
0x1801dfe7e  pop     rbx
0x1801dfe7f  pop     rbp
0x1801dfe80  retn
```
