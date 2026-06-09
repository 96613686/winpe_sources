# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18001c214`
- end: `0x18001c4ac`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `664`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800093ec`

## callees

- `0x18000a124`
- `0x18000aa58`
- `0x180018700`
- `0x18001c214`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c272`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001c272`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c3a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001c3a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c2cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c3ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c45d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c2cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c3ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c45d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001c487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c368`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c472`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c368`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001c472`

## string_xrefs

- `0x18001c28f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c3bd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001c2af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001c341`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001c3dd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001c26b`: `User\Index\UserSid`
- `0x18001c430`: `User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
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
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  int *v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  char v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v22 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v18 = 0;
  v20 = v18;
  v21 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v7 = 185;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
LABEL_4:
    v8 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v18 )
  {
    v6 = -2140733422;
    v7 = 186;
    goto LABEL_3;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v10,
      v18[0]);
LABEL_11:
    v11 = v23;
    v23 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_4;
  }
  v20 = (int *)&v19;
  v19 = 0;
  v21 = 0;
  v22 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v13 = 193;
    goto LABEL_15;
  }
  if ( v19 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData(
           (StateRepository::Cache::Context_NoThrow *)&v19,
           v12,
           a3);
    if ( v6 < 0 )
    {
      v13 = 196;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"User\\Index\\UserSid");
  if ( v6 < 0 )
  {
    v13 = 199;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v14 = v19;
    v19 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    goto LABEL_11;
  }
  v15 = v19;
  v19 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v23;
  v23 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x18001c214  push    rbp
0x18001c216  push    rbx
0x18001c217  push    rsi
0x18001c218  push    rdi
0x18001c219  push    r14
0x18001c21b  lea     rbp, [rsp-180h]
0x18001c223  sub     rsp, 280h
0x18001c22a  mov     rax, cs:__security_cookie
0x18001c231  xor     rax, rsp
0x18001c234  mov     [rbp+1A0h+var_30], rax
0x18001c23b  xor     r14d, r14d
0x18001c23e  mov     [rsp+2A0h+var_260], 1
0x18001c243  mov     [r8], r14
0x18001c246  lea     rax, [rsp+2A0h+var_280]
0x18001c24b  mov     rcx, [rcx]
0x18001c24e  lea     r9, [rsp+2A0h+var_268]
0x18001c253  mov     rdi, r8
0x18001c256  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18001c25b  mov     rsi, rdx
0x18001c25e  mov     [rsp+2A0h+var_270], rax
0x18001c263  xor     r8d, r8d
0x18001c266  mov     [rsp+2A0h+var_268], r14
0x18001c26b  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18001c272  call    cs:__imp_SRCacheContext_Open
0x18001c278  lea     rcx, [rsp+2A0h+var_270]
0x18001c27d  mov     ebx, eax
0x18001c27f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c284  test    ebx, ebx
0x18001c286  jns     short loc_18001C2DA
0x18001c288  mov     rcx, [rbp+1A8h]; this
0x18001c28f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c296  mov     r9d, ebx; char *
0x18001c299  mov     edx, 18Ch; void *
0x18001c29e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2a3  mov     edx, 0B9h; void *
0x18001c2a8  mov     rcx, [rbp+1A8h]; this
0x18001c2af  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c2b6  mov     r9d, ebx; char *
0x18001c2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2be  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c2c3  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001c2c8  test    rcx, rcx
0x18001c2cb  jz      short loc_18001C2D3
0x18001c2cd  call    cs:__imp_SRCacheContext_Close
0x18001c2d3  mov     eax, ebx
0x18001c2d5  jmp     loc_18001C48F
0x18001c2da  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18001c2df  setnz   al
0x18001c2e2  test    al, al
0x18001c2e4  jnz     short loc_18001C2F2
0x18001c2e6  mov     ebx, 80670012h
0x18001c2eb  mov     edx, 0BAh
0x18001c2f0  jmp     short loc_18001C2A8
0x18001c2f2  xor     edx, edx; Val
0x18001c2f4  mov     [rsp+2A0h+var_250], r14
0x18001c2f9  mov     r8d, 200h; Size
0x18001c2ff  lea     rcx, [rsp+2A0h+var_248]; void *
0x18001c304  call    memset_0
0x18001c309  lea     rax, [rsp+2A0h+var_248]
0x18001c30e  mov     [rbp+1A0h+var_48], r14
0x18001c315  mov     rdx, rsi; unsigned __int16 *
0x18001c318  mov     [rbp+1A0h+var_38], rax
0x18001c31f  lea     rcx, [rsp+2A0h+var_250]; this
0x18001c324  mov     [rbp+1A0h+var_40], 100h
0x18001c32f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001c334  mov     ebx, eax
0x18001c336  test    eax, eax
0x18001c338  jns     short loc_18001C373
0x18001c33a  mov     rcx, [rbp+1A8h]; this
0x18001c341  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c348  mov     r9d, eax; char *
0x18001c34b  mov     edx, 0BDh; void *
0x18001c350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c355  mov     rcx, [rsp+2A0h+var_250]
0x18001c35a  mov     [rsp+2A0h+var_250], r14
0x18001c35f  test    rcx, rcx
0x18001c362  jz      loc_18001C2BE
0x18001c368  call    cs:__imp_SRCache_Free
0x18001c36e  jmp     loc_18001C2BE
0x18001c373  mov     rdx, [rbp+1A0h+var_38]
0x18001c37a  lea     rax, [rsp+2A0h+var_278]
0x18001c37f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c384  lea     r9, [rsp+2A0h+var_268]
0x18001c389  xor     r8d, r8d
0x18001c38c  mov     [rsp+2A0h+var_270], rax
0x18001c391  mov     [rsp+2A0h+var_278], r14
0x18001c396  mov     [rsp+2A0h+var_268], r14
0x18001c39b  mov     [rsp+2A0h+var_260], 1
0x18001c3a0  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001c3a6  lea     rcx, [rsp+2A0h+var_270]
0x18001c3ab  mov     ebx, eax
0x18001c3ad  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001c3b2  test    ebx, ebx
0x18001c3b4  jns     short loc_18001C40A
0x18001c3b6  mov     rcx, [rbp+1A8h]; this
0x18001c3bd  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c3c4  mov     r9d, ebx; char *
0x18001c3c7  mov     edx, 1B0h; void *
0x18001c3cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3d1  mov     edx, 0C1h; void *
0x18001c3d6  mov     rcx, [rbp+1A8h]; this
0x18001c3dd  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001c3e4  mov     r9d, ebx; char *
0x18001c3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3ec  mov     rcx, [rsp+2A0h+var_278]
0x18001c3f1  mov     [rsp+2A0h+var_278], r14
0x18001c3f6  test    rcx, rcx
0x18001c3f9  jz      loc_18001C355
0x18001c3ff  call    cs:__imp_SRCacheContext_Close
0x18001c405  jmp     loc_18001C355
0x18001c40a  cmp     [rsp+2A0h+var_278], r14
0x18001c40f  setnz   al
0x18001c412  test    al, al
0x18001c414  jz      short loc_18001C430
0x18001c416  mov     r8, rdi; __int64 *
0x18001c419  lea     rcx, [rsp+2A0h+var_278]; this
0x18001c41e  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18001c423  mov     ebx, eax
0x18001c425  test    eax, eax
0x18001c427  jns     short loc_18001C430
0x18001c429  mov     edx, 0C4h
0x18001c42e  jmp     short loc_18001C3D6
0x18001c430  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18001c437  lea     rcx, [rsp+2A0h+var_280]; this
0x18001c43c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001c441  mov     ebx, eax
0x18001c443  test    eax, eax
0x18001c445  jns     short loc_18001C44E
0x18001c447  mov     edx, 0C7h
0x18001c44c  jmp     short loc_18001C3D6
0x18001c44e  mov     rcx, [rsp+2A0h+var_278]
0x18001c453  mov     [rsp+2A0h+var_278], r14
0x18001c458  test    rcx, rcx
0x18001c45b  jz      short loc_18001C463
0x18001c45d  call    cs:__imp_SRCacheContext_Close
0x18001c463  mov     rcx, [rsp+2A0h+var_250]
0x18001c468  mov     [rsp+2A0h+var_250], r14
0x18001c46d  test    rcx, rcx
0x18001c470  jz      short loc_18001C478
0x18001c472  call    cs:__imp_SRCache_Free
0x18001c478  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001c47d  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001c482  test    rcx, rcx
0x18001c485  jz      short loc_18001C48D
0x18001c487  call    cs:__imp_SRCacheContext_Close
0x18001c48d  xor     eax, eax
0x18001c48f  mov     rcx, [rbp+1A0h+var_30]
0x18001c496  xor     rcx, rsp; StackCookie
0x18001c499  call    __security_check_cookie
0x18001c49e  add     rsp, 280h
0x18001c4a5  pop     r14
0x18001c4a7  pop     rdi
0x18001c4a8  pop     rsi
0x18001c4a9  pop     rbx
0x18001c4aa  pop     rbp
0x18001c4ab  retn
```
