# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x18001b008`
- end: `0x18001b0e0`
- name: `?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180037230`

## callees

- `0x18001b008`
- `0x18001bb48`
- `0x18001cc38`
- `0x180036e14`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b0cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b0cf`

## string_xrefs

- `0x18001b025`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001b070`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 325;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(&v16, a4, v10, a2);
    if ( v7 < 0 )
    {
      v11 = 330;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
        (const char *)(unsigned int)v7,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v7;
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
0x18001b008  mov     [rsp+arg_10], r8
0x18001b00d  push    rbx
0x18001b00e  push    rbp
0x18001b00f  push    rsi
0x18001b010  push    rdi
0x18001b011  sub     rsp, 28h
0x18001b015  mov     rbp, r9
0x18001b018  mov     rdi, rdx
0x18001b01b  test    rdx, rdx
0x18001b01e  jnz     short loc_18001B045
0x18001b020  mov     rcx, [rsp+48h]; this
0x18001b025  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b02c  mov     ebx, 80070057h
0x18001b031  mov     edx, 142h; void *
0x18001b036  mov     r9d, ebx; char *
0x18001b039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b03e  mov     eax, ebx
0x18001b040  jmp     loc_18001B0D7
0x18001b045  mov     rsi, [rsp+48h+arg_20]
0x18001b04a  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18001b04f  mov     r9, rsi; bool *
0x18001b052  mov     [rsp+48h+arg_10], 0
0x18001b05b  call    ?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001b060  mov     ebx, eax
0x18001b062  test    eax, eax
0x18001b064  jns     short loc_18001B09A
0x18001b066  mov     edx, 145h; void *
0x18001b06b  mov     rcx, [rsp+48h]; this
0x18001b070  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b077  mov     r9d, ebx; char *
0x18001b07a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b07f  mov     rcx, [rsp+48h+arg_10]
0x18001b084  mov     [rsp+48h+arg_10], 0
0x18001b08d  test    rcx, rcx
0x18001b090  jz      short loc_18001B03E
0x18001b092  call    cs:__imp_SRCacheContext_Close
0x18001b098  jmp     short loc_18001B03E
0x18001b09a  cmp     byte ptr [rsi], 0
0x18001b09d  jz      short loc_18001B0BC
0x18001b09f  mov     r9, rdi
0x18001b0a2  lea     rcx, [rsp+48h+arg_10]
0x18001b0a7  mov     rdx, rbp
0x18001b0aa  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x18001b0af  mov     ebx, eax
0x18001b0b1  test    eax, eax
0x18001b0b3  jns     short loc_18001B0BC
0x18001b0b5  mov     edx, 14Ah
0x18001b0ba  jmp     short loc_18001B06B
0x18001b0bc  mov     rcx, [rsp+48h+arg_10]
0x18001b0c1  mov     [rsp+48h+arg_10], 0
0x18001b0ca  test    rcx, rcx
0x18001b0cd  jz      short loc_18001B0D5
0x18001b0cf  call    cs:__imp_SRCacheContext_Close
0x18001b0d5  xor     eax, eax
0x18001b0d7  add     rsp, 28h
0x18001b0db  pop     rdi
0x18001b0dc  pop     rsi
0x18001b0dd  pop     rbp
0x18001b0de  pop     rbx
0x18001b0df  retn
```
