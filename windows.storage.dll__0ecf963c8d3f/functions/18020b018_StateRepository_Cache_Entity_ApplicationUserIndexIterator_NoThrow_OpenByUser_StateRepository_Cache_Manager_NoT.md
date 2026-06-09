# StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::OpenByUser(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18020b018`
- end: `0x18020b354`
- name: `?OpenByUser@ApplicationUserIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18020ca14`
- `0x18035d2a0`

## callees

- `0x1800432f0`
- `0x1800a0e00`
- `0x18020b018`
- `0x18020b35c`
- `0x180291fc8`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18020b1c5`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18020b1c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020b26c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020b26c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b236`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b2f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b311`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b236`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b2f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020b311`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b087`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b125`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b171`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b087`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b125`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b171`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020b326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020b0c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020b0c8`

## string_xrefs

- `0x18020b1d6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18020b05c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18020b102`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18020b145`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18020b214`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18020b2d0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18020b0e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020b28b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::OpenByUser(
        StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)v28 = v22;
  *(_QWORD *)v22 = 0;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_Open(v9, L"ApplicationUser\\Index\\User", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
LABEL_8:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)_o__ui64tow_s(a3, v28, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_18:
    v15 = 850;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v10 < 0 )
    goto LABEL_18;
  *(_QWORD *)v28 = this;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v15 = 853;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"ApplicationUser\\Index\\User");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v17,
      v22[0]);
    v19 = v23;
    v23 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = v23;
  v23 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x18020b018  mov     [rsp-8+arg_18], rbx
0x18020b01d  push    rbp
0x18020b01e  push    rsi
0x18020b01f  push    rdi
0x18020b020  push    r14
0x18020b022  push    r15
0x18020b024  lea     rbp, [rsp-180h]
0x18020b02c  sub     rsp, 280h
0x18020b033  mov     rax, cs:__security_cookie
0x18020b03a  xor     rax, rsp
0x18020b03d  mov     [rbp+1A0h+var_28], rax
0x18020b044  xor     r15d, r15d
0x18020b047  mov     r14, r8
0x18020b04a  mov     rsi, rdx
0x18020b04d  mov     rbx, rcx
0x18020b050  test    r8, r8
0x18020b053  jnz     short loc_18020B07C
0x18020b055  mov     rcx, [rbp+1A8h]; this
0x18020b05c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b063  mov     ebx, 80070057h
0x18020b068  mov     edx, 348h; void *
0x18020b06d  mov     r9d, ebx; char *
0x18020b070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b075  mov     eax, ebx
0x18020b077  jmp     loc_18020B32E
0x18020b07c  mov     rcx, [rcx]
0x18020b07f  mov     [rbx], r15
0x18020b082  test    rcx, rcx
0x18020b085  jz      short loc_18020B08D
0x18020b087  call    cs:__imp_SRCacheContext_Close
0x18020b08d  mov     [rbx+8], r15d
0x18020b091  lea     rax, [rsp+2A0h+var_280]
0x18020b096  mov     [rbx+10h], r15
0x18020b09a  lea     r9, [rbp+1A0h+var_48]
0x18020b0a1  mov     rcx, [rsi]
0x18020b0a4  lea     rdx, aApplicationuse_1; "ApplicationUser\\Index\\User"
0x18020b0ab  xor     r8d, r8d
0x18020b0ae  mov     qword ptr [rbp+1A0h+var_50], rax
0x18020b0b5  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18020b0ba  mov     [rbp+1A0h+var_48], r15
0x18020b0c1  mov     [rbp+1A0h+var_40], 1
0x18020b0c8  call    cs:__imp_SRCacheContext_Open
0x18020b0ce  lea     rcx, [rbp+1A0h+var_50]
0x18020b0d5  mov     edi, eax
0x18020b0d7  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18020b0dc  test    edi, edi
0x18020b0de  jns     short loc_18020B132
0x18020b0e0  mov     rcx, [rbp+1A8h]; this
0x18020b0e7  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b0ee  mov     r9d, edi; char *
0x18020b0f1  mov     edx, 18Ch; void *
0x18020b0f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b0fb  mov     rcx, [rbp+1A8h]; this
0x18020b102  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b109  mov     r9d, edi; char *
0x18020b10c  mov     edx, 34Eh; void *
0x18020b111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b116  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020b11b  mov     qword ptr [rsp+2A0h+var_280], r15
0x18020b120  test    rcx, rcx
0x18020b123  jz      short loc_18020B12B
0x18020b125  call    cs:__imp_SRCacheContext_Close
0x18020b12b  mov     eax, edi
0x18020b12d  jmp     loc_18020B32E
0x18020b132  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18020b137  setnz   al
0x18020b13a  test    al, al
0x18020b13c  jnz     short loc_18020B17C
0x18020b13e  mov     rcx, [rbp+1A8h]; this
0x18020b145  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b14c  mov     ebx, 80670012h
0x18020b151  mov     edx, 34Fh; void *
0x18020b156  mov     r9d, ebx; char *
0x18020b159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b15e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020b163  mov     qword ptr [rsp+2A0h+var_280], r15
0x18020b168  test    rcx, rcx
0x18020b16b  jz      loc_18020B075
0x18020b171  call    cs:__imp_SRCacheContext_Close
0x18020b177  jmp     loc_18020B075
0x18020b17c  xor     edx, edx; Val
0x18020b17e  mov     [rsp+2A0h+var_270], r15
0x18020b183  mov     r8d, 200h; Size
0x18020b189  lea     rcx, [rsp+2A0h+var_268]; void *
0x18020b18e  call    memset_0
0x18020b193  mov     r9d, 10h
0x18020b199  mov     [rbp+1A0h+var_68], r15
0x18020b1a0  lea     rax, [rsp+2A0h+var_268]
0x18020b1a5  mov     [rbp+1A0h+var_60], 100h
0x18020b1b0  lea     rdx, [rbp+1A0h+var_50]
0x18020b1b7  mov     [rbp+1A0h+var_58], rax
0x18020b1be  mov     rcx, r14
0x18020b1c1  lea     r8d, [r9+1]
0x18020b1c5  call    cs:__imp__o__ui64tow_s
0x18020b1cb  test    eax, eax
0x18020b1cd  jz      short loc_18020B1F1
0x18020b1cf  mov     rcx, [rbp+1A8h]; this
0x18020b1d6  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b1dd  mov     edi, 8000FFFFh
0x18020b1e2  mov     edx, 166h; void *
0x18020b1e7  mov     r9d, edi; char *
0x18020b1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b1ef  jmp     short loc_18020B208
0x18020b1f1  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18020b1f8  lea     rcx, [rsp+2A0h+var_270]; this
0x18020b1fd  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18020b202  mov     edi, eax
0x18020b204  test    eax, eax
0x18020b206  jns     short loc_18020B241
0x18020b208  mov     edx, 352h; void *
0x18020b20d  mov     rcx, [rbp+1A8h]; this
0x18020b214  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b21b  mov     r9d, edi; char *
0x18020b21e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b223  mov     rcx, [rsp+2A0h+var_270]
0x18020b228  mov     [rsp+2A0h+var_270], r15
0x18020b22d  test    rcx, rcx
0x18020b230  jz      loc_18020B116
0x18020b236  call    cs:__imp_SRCache_Free
0x18020b23c  jmp     loc_18020B116
0x18020b241  mov     rdx, [rbp+1A0h+var_58]
0x18020b248  lea     r9, [rbp+1A0h+var_48]
0x18020b24f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020b254  xor     r8d, r8d
0x18020b257  mov     qword ptr [rbp+1A0h+var_50], rbx
0x18020b25e  mov     [rbp+1A0h+var_48], r15
0x18020b265  mov     [rbp+1A0h+var_40], 1
0x18020b26c  call    cs:__imp_SRCacheContext_OpenSubContext
0x18020b272  lea     rcx, [rbp+1A0h+var_50]
0x18020b279  mov     edi, eax
0x18020b27b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18020b280  test    edi, edi
0x18020b282  jns     short loc_18020B2A9
0x18020b284  mov     rcx, [rbp+1A8h]; this
0x18020b28b  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b292  mov     r9d, edi; char *
0x18020b295  mov     edx, 1B0h; void *
0x18020b29a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b29f  mov     edx, 355h
0x18020b2a4  jmp     loc_18020B20D
0x18020b2a9  cmp     [rbx], r15
0x18020b2ac  jz      short loc_18020B2B2
0x18020b2ae  mov     [rbx+10h], rsi
0x18020b2b2  lea     rdx, aApplicationuse_1; "ApplicationUser\\Index\\User"
0x18020b2b9  lea     rcx, [rsp+2A0h+var_280]; this
0x18020b2be  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18020b2c3  mov     ebx, eax
0x18020b2c5  test    eax, eax
0x18020b2c7  jns     short loc_18020B302
0x18020b2c9  mov     rcx, [rbp+1A8h]; this
0x18020b2d0  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020b2d7  mov     r9d, eax; char *
0x18020b2da  mov     edx, 35Bh; void *
0x18020b2df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020b2e4  mov     rcx, [rsp+2A0h+var_270]
0x18020b2e9  mov     [rsp+2A0h+var_270], r15
0x18020b2ee  test    rcx, rcx
0x18020b2f1  jz      loc_18020B15E
0x18020b2f7  call    cs:__imp_SRCache_Free
0x18020b2fd  jmp     loc_18020B15E
0x18020b302  mov     rcx, [rsp+2A0h+var_270]
0x18020b307  mov     [rsp+2A0h+var_270], r15
0x18020b30c  test    rcx, rcx
0x18020b30f  jz      short loc_18020B317
0x18020b311  call    cs:__imp_SRCache_Free
0x18020b317  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020b31c  mov     qword ptr [rsp+2A0h+var_280], r15
0x18020b321  test    rcx, rcx
0x18020b324  jz      short loc_18020B32C
0x18020b326  call    cs:__imp_SRCacheContext_Close
0x18020b32c  xor     eax, eax
0x18020b32e  mov     rcx, [rbp+1A0h+var_28]
0x18020b335  xor     rcx, rsp; StackCookie
0x18020b338  call    __security_check_cookie
0x18020b33d  mov     rbx, [rsp+2A0h+arg_18]
0x18020b345  add     rsp, 280h
0x18020b34c  pop     r15
0x18020b34e  pop     r14
0x18020b350  pop     rdi
0x18020b351  pop     rsi
0x18020b352  pop     rbp
0x18020b353  retn
```
