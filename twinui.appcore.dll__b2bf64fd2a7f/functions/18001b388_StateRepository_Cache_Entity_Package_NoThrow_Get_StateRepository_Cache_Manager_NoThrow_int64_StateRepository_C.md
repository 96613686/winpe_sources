# StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x18001b388`
- end: `0x18001b475`
- name: `?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `237`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b894`
- `0x180038c20`
- `0x180038f40`

## callees

- `0x18001b388`
- `0x18001bd8c`
- `0x18001cc38`
- `0x180036e98`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b41a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b45a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b41a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b45a`

## string_xrefs

- `0x18001b3ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b3f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  int v8; // ebx
  bool *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v16; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x453,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v8;
  }
  v10 = a5;
  v16 = 0;
  v8 = StateRepository::Cache::Entity::Package_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v8 < 0 )
  {
    v11 = 1110;
    goto LABEL_6;
  }
  if ( *v10 )
  {
    v8 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v16, a4, a3, a2);
    if ( v8 < 0 )
    {
      v11 = 1115;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v8,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v8;
    }
  }
  v13 = v16;
  v16 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  return 0;
}

```

## disassembly

```asm
0x18001b388  mov     [rsp+arg_0], rbx
0x18001b38d  mov     [rsp+arg_10], rbp
0x18001b392  push    rsi
0x18001b393  push    rdi
0x18001b394  push    r14; int
0x18001b396  sub     rsp, 20h
0x18001b39a  mov     rbp, r9
0x18001b39d  mov     r14, r8
0x18001b3a0  mov     rdi, rdx
0x18001b3a3  test    rdx, rdx
0x18001b3a6  jnz     short loc_18001B3CD
0x18001b3a8  mov     rcx, [rsp+38h]; this
0x18001b3ad  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b3b4  mov     ebx, 80070057h
0x18001b3b9  mov     edx, 453h; void *
0x18001b3be  mov     r9d, ebx; char *
0x18001b3c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3c6  mov     eax, ebx
0x18001b3c8  jmp     loc_18001B462
0x18001b3cd  mov     rsi, [rsp+38h+arg_20]
0x18001b3d2  lea     r8, [rsp+38h+arg_8]; struct StateRepository::Cache::Context_NoThrow *
0x18001b3d7  mov     r9, rsi; bool *
0x18001b3da  mov     [rsp+38h+arg_8], 0
0x18001b3e3  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001b3e8  mov     ebx, eax
0x18001b3ea  test    eax, eax
0x18001b3ec  jns     short loc_18001B422
0x18001b3ee  mov     edx, 456h; void *
0x18001b3f3  mov     rcx, [rsp+38h]; this
0x18001b3f8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b3ff  mov     r9d, ebx; char *
0x18001b402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b407  mov     rcx, [rsp+38h+arg_8]
0x18001b40c  mov     [rsp+38h+arg_8], 0
0x18001b415  test    rcx, rcx
0x18001b418  jz      short loc_18001B3C6
0x18001b41a  call    cs:__imp_SRCacheContext_Close
0x18001b420  jmp     short loc_18001B3C6
0x18001b422  cmp     byte ptr [rsi], 0
0x18001b425  jz      short loc_18001B447
0x18001b427  mov     r9, rdi
0x18001b42a  lea     rcx, [rsp+38h+arg_8]
0x18001b42f  mov     r8, r14
0x18001b432  mov     rdx, rbp
0x18001b435  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18001b43a  mov     ebx, eax
0x18001b43c  test    eax, eax
0x18001b43e  jns     short loc_18001B447
0x18001b440  mov     edx, 45Bh
0x18001b445  jmp     short loc_18001B3F3
0x18001b447  mov     rcx, [rsp+38h+arg_8]
0x18001b44c  mov     [rsp+38h+arg_8], 0
0x18001b455  test    rcx, rcx
0x18001b458  jz      short loc_18001B460
0x18001b45a  call    cs:__imp_SRCacheContext_Close
0x18001b460  xor     eax, eax
0x18001b462  mov     rbx, [rsp+38h+arg_0]
0x18001b467  mov     rbp, [rsp+38h+arg_10]
0x18001b46c  add     rsp, 20h
0x18001b470  pop     r14
0x18001b472  pop     rdi
0x18001b473  pop     rsi
0x18001b474  retn
```
