# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18000e5c0`
- end: `0x18000e8a9`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000dae4`

## callees

- `0x18000e5c0`
- `0x18000eccc`
- `0x18000f4d0`
- `0x1800210f8`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e61e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e61e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000e7da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000e7da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e6cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e829`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e6cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e829`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e778`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e778`

## string_xrefs

- `0x18000e617`: `User\Index\UserSid`
- `0x18000e771`: `User\Index\UserSid`
- `0x18000e6a9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000e7b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000e889`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000e795`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e7f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e844`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e869`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  int *v17; // [rsp+30h] [rbp-D0h]
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+258h] [rbp+158h]
  __int64 v23; // [rsp+260h] [rbp+160h]
  _BYTE *v24; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v19 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v16 = 0;
  v17 = (int *)&v16;
  v18 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v18);
  if ( v19 )
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v17, v18);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v15[0]);
    v14 = 185;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v15[0]);
    goto LABEL_9;
  }
  if ( !v16 )
  {
    v6 = -2140733422;
    v14 = 186;
    goto LABEL_24;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v7,
      v15[0]);
    goto LABEL_7;
  }
  v17 = v15;
  *(_QWORD *)v15 = 0;
  v18 = 0;
  v19 = 1;
  v6 = SRCacheContext_OpenSubContext(v16, v24, 0, &v18);
  if ( v19 )
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v17, v18);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v15[0]);
    v11 = 193;
    goto LABEL_16;
  }
  if ( *(_QWORD *)v15 )
  {
    v12 = SRCacheContext_EnumerateData(*(_QWORD *)v15, 0, a3);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v15[0]);
      v11 = 196;
      goto LABEL_16;
    }
  }
  v10 = SRCacheContext_AddToCache(v16, L"User\\Index\\UserSid");
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v15[0]);
    v11 = 199;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v15[0]);
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v15, 0);
LABEL_7:
    v8 = v20;
    v20 = 0;
    if ( v8 )
      SRCache_Free();
    goto LABEL_9;
  }
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v15, 0);
  v13 = v20;
  v20 = 0;
  if ( v13 )
    SRCache_Free();
  v6 = 0;
LABEL_9:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v16, 0);
  return v6;
}

```

## disassembly

```asm
0x18000e5c0  push    rbp
0x18000e5c2  push    rbx
0x18000e5c3  push    rsi
0x18000e5c4  push    rdi
0x18000e5c5  push    r14
0x18000e5c7  lea     rbp, [rsp-180h]
0x18000e5cf  sub     rsp, 280h
0x18000e5d6  mov     rax, cs:__security_cookie
0x18000e5dd  xor     rax, rsp
0x18000e5e0  mov     [rbp+1A0h+var_30], rax
0x18000e5e7  xor     r14d, r14d
0x18000e5ea  mov     [rsp+2A0h+var_260], 1
0x18000e5ef  mov     [r8], r14
0x18000e5f2  lea     rax, [rsp+2A0h+var_278]
0x18000e5f7  mov     rcx, [rcx]
0x18000e5fa  lea     r9, [rsp+2A0h+var_268]
0x18000e5ff  mov     rdi, r8
0x18000e602  mov     [rsp+2A0h+var_278], r14
0x18000e607  mov     rsi, rdx
0x18000e60a  mov     [rsp+2A0h+var_270], rax
0x18000e60f  xor     r8d, r8d
0x18000e612  mov     [rsp+2A0h+var_268], r14
0x18000e617  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000e61e  call    cs:__imp_SRCacheContext_Open
0x18000e625  nop     dword ptr [rax+rax+00h]
0x18000e62a  mov     ebx, eax
0x18000e62c  cmp     [rsp+2A0h+var_260], r14b
0x18000e631  jz      short loc_18000E642
0x18000e633  mov     rdx, [rsp+2A0h+var_268]
0x18000e638  mov     rcx, [rsp+2A0h+var_270]
0x18000e63d  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e642  test    ebx, ebx
0x18000e644  js      loc_18000E862
0x18000e64a  cmp     [rsp+2A0h+var_278], r14
0x18000e64f  setnz   al
0x18000e652  test    al, al
0x18000e654  jz      loc_18000E89D
0x18000e65a  xor     edx, edx; Val
0x18000e65c  mov     [rsp+2A0h+var_250], r14
0x18000e661  mov     r8d, 200h; Size
0x18000e667  lea     rcx, [rsp+2A0h+var_248]; void *
0x18000e66c  call    memset_0
0x18000e671  lea     rax, [rsp+2A0h+var_248]
0x18000e676  mov     [rbp+1A0h+var_48], r14
0x18000e67d  mov     rdx, rsi; unsigned __int16 *
0x18000e680  mov     [rbp+1A0h+var_38], rax
0x18000e687  lea     rcx, [rsp+2A0h+var_250]; this
0x18000e68c  mov     [rbp+1A0h+var_40], 100h
0x18000e697  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000e69c  mov     ebx, eax
0x18000e69e  test    eax, eax
0x18000e6a0  jns     short loc_18000E704
0x18000e6a2  mov     rcx, [rbp+1A8h]; this
0x18000e6a9  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e6b0  mov     r9d, eax; char *
0x18000e6b3  mov     edx, 0BDh; void *
0x18000e6b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6bd  mov     rcx, [rsp+2A0h+var_250]
0x18000e6c2  mov     [rsp+2A0h+var_250], r14
0x18000e6c7  test    rcx, rcx
0x18000e6ca  jz      short loc_18000E6D8
0x18000e6cc  call    cs:__imp_SRCache_Free
0x18000e6d3  nop     dword ptr [rax+rax+00h]
0x18000e6d8  xor     edx, edx
0x18000e6da  lea     rcx, [rsp+2A0h+var_278]
0x18000e6df  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e6e4  mov     eax, ebx
0x18000e6e6  mov     rcx, [rbp+1A0h+var_30]
0x18000e6ed  xor     rcx, rsp; StackCookie
0x18000e6f0  call    __security_check_cookie
0x18000e6f5  add     rsp, 280h
0x18000e6fc  pop     r14
0x18000e6fe  pop     rdi
0x18000e6ff  pop     rsi
0x18000e700  pop     rbx
0x18000e701  pop     rbp
0x18000e702  retn
0x18000e704  mov     rdx, [rbp+1A0h+var_38]
0x18000e70b  lea     rax, [rsp+2A0h+var_280]
0x18000e710  mov     rcx, [rsp+2A0h+var_278]
0x18000e715  lea     r9, [rsp+2A0h+var_268]
0x18000e71a  xor     r8d, r8d
0x18000e71d  mov     [rsp+2A0h+var_270], rax
0x18000e722  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18000e727  mov     [rsp+2A0h+var_268], r14
0x18000e72c  mov     [rsp+2A0h+var_260], 1
0x18000e731  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000e738  nop     dword ptr [rax+rax+00h]
0x18000e73d  mov     ebx, eax
0x18000e73f  cmp     [rsp+2A0h+var_260], r14b
0x18000e744  jz      short loc_18000E755
0x18000e746  mov     rdx, [rsp+2A0h+var_268]
0x18000e74b  mov     rcx, [rsp+2A0h+var_270]
0x18000e750  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e755  test    ebx, ebx
0x18000e757  js      loc_18000E83D
0x18000e75d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000e762  test    rcx, rcx
0x18000e765  setnz   al
0x18000e768  test    al, al
0x18000e76a  jnz     short loc_18000E7D5
0x18000e76c  mov     rcx, [rsp+2A0h+var_278]
0x18000e771  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000e778  call    cs:__imp_SRCacheContext_AddToCache
0x18000e77f  nop     dword ptr [rax+rax+00h]
0x18000e784  mov     ebx, eax
0x18000e786  test    eax, eax
0x18000e788  jns     loc_18000E80E
0x18000e78e  mov     rcx, [rbp+1A8h]; this
0x18000e795  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e79c  mov     r9d, eax; char *
0x18000e79f  mov     edx, 1A6h; void *
0x18000e7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7a9  mov     edx, 0C7h; void *
0x18000e7ae  mov     rcx, [rbp+1A8h]; this
0x18000e7b5  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e7bc  mov     r9d, ebx; char *
0x18000e7bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7c4  xor     edx, edx
0x18000e7c6  lea     rcx, [rsp+2A0h+var_280]
0x18000e7cb  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e7d0  jmp     loc_18000E6BD
0x18000e7d5  mov     r8, rdi
0x18000e7d8  xor     edx, edx
0x18000e7da  call    cs:__imp_SRCacheContext_EnumerateData
0x18000e7e1  nop     dword ptr [rax+rax+00h]
0x18000e7e6  mov     ebx, eax
0x18000e7e8  test    eax, eax
0x18000e7ea  jns     short loc_18000E76C
0x18000e7ec  mov     rcx, [rbp+1A8h]; this
0x18000e7f3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e7fa  mov     r9d, eax; char *
0x18000e7fd  mov     edx, 2A6h; void *
0x18000e802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e807  mov     edx, 0C4h
0x18000e80c  jmp     short loc_18000E7AE
0x18000e80e  xor     edx, edx
0x18000e810  lea     rcx, [rsp+2A0h+var_280]
0x18000e815  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e81a  mov     rcx, [rsp+2A0h+var_250]
0x18000e81f  mov     [rsp+2A0h+var_250], r14
0x18000e824  test    rcx, rcx
0x18000e827  jz      short loc_18000E835
0x18000e829  call    cs:__imp_SRCache_Free
0x18000e830  nop     dword ptr [rax+rax+00h]
0x18000e835  mov     ebx, r14d
0x18000e838  jmp     loc_18000E6D8
0x18000e83d  mov     rcx, [rbp+1A8h]; this
0x18000e844  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e84b  mov     r9d, ebx; char *
0x18000e84e  mov     edx, 1B0h; void *
0x18000e853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e858  mov     edx, 0C1h
0x18000e85d  jmp     loc_18000E7AE
0x18000e862  mov     rcx, [rbp+1A8h]; this
0x18000e869  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e870  mov     r9d, ebx; char *
0x18000e873  mov     edx, 18Ch; void *
0x18000e878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e87d  mov     edx, 0B9h; void *
0x18000e882  mov     rcx, [rbp+1A8h]; this
0x18000e889  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e890  mov     r9d, ebx; char *
0x18000e893  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e898  jmp     loc_18000E6D8
0x18000e89d  mov     ebx, 80670012h
0x18000e8a2  mov     edx, 0BAh
0x18000e8a7  jmp     short loc_18000E882
```
