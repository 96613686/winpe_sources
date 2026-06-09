# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)

- ea: `0x18001b47c`
- end: `0x18001b582`
- name: `?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800093ec`

## callees

- `0x18000a7fc`
- `0x180018a54`
- `0x18001b47c`
- `0x18001cc38`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b50c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b567`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b50c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b567`

## string_xrefs

- `0x18001b4a5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18001b4ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x18001b538`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  unsigned int v7; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  int Field; // eax
  __int64 v13; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      savedregs);
    return v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = 274;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    Field = StateRepository::Cache::Context_NoThrow::GetField(
              (StateRepository::Cache::Context_NoThrow *)&v16,
              L"Application",
              (unsigned int *)(a4 + 24));
    v7 = Field;
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)(unsigned int)Field,
        savedregs);
      v10 = 279;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v7,
        savedregs);
      v11 = v16;
      v16 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return v7;
    }
    *(_QWORD *)a4 = a2;
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
0x18001b47c  mov     [rsp-18h+arg_0], rbx
0x18001b481  mov     [rsp-18h+arg_8], rsi
0x18001b486  mov     [rsp-18h+arg_10], r8
0x18001b48b  push    rbp
0x18001b48c  push    rdi
0x18001b48d  push    r14; int
0x18001b48f  mov     rbp, rsp
0x18001b492  sub     rsp, 20h
0x18001b496  mov     rsi, r9
0x18001b499  mov     rdi, rdx
0x18001b49c  test    rdx, rdx
0x18001b49f  jnz     short loc_18001B4C5
0x18001b4a1  mov     rcx, [rbp+18h]; this
0x18001b4a5  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b4ac  mov     ebx, 80070057h
0x18001b4b1  mov     edx, 10Fh; void *
0x18001b4b6  mov     r9d, ebx; char *
0x18001b4b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4be  mov     eax, ebx
0x18001b4c0  jmp     loc_18001B56F
0x18001b4c5  mov     r14, [rbp+arg_20]
0x18001b4c9  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18001b4cd  mov     r9, r14; bool *
0x18001b4d0  mov     [rbp+arg_10], 0
0x18001b4d8  call    ?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001b4dd  mov     ebx, eax
0x18001b4df  test    eax, eax
0x18001b4e1  jns     short loc_18001B514
0x18001b4e3  mov     edx, 112h; void *
0x18001b4e8  mov     rcx, [rbp+18h]; this
0x18001b4ec  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b4f3  mov     r9d, ebx; char *
0x18001b4f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4fb  mov     rcx, [rbp+arg_10]
0x18001b4ff  mov     [rbp+arg_10], 0
0x18001b507  test    rcx, rcx
0x18001b50a  jz      short loc_18001B4BE
0x18001b50c  call    cs:__imp_SRCacheContext_Close
0x18001b512  jmp     short loc_18001B4BE
0x18001b514  cmp     byte ptr [r14], 0
0x18001b518  jz      short loc_18001B556
0x18001b51a  lea     r8, [rsi+18h]; unsigned int *
0x18001b51e  lea     rdx, aApplication; "Application"
0x18001b525  lea     rcx, [rbp+arg_10]; this
0x18001b529  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001b52e  mov     ebx, eax
0x18001b530  test    eax, eax
0x18001b532  jns     short loc_18001B553
0x18001b534  mov     rcx, [rbp+18h]; this
0x18001b538  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b53f  mov     r9d, eax; char *
0x18001b542  mov     edx, 45Dh; void *
0x18001b547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b54c  mov     edx, 117h
0x18001b551  jmp     short loc_18001B4E8
0x18001b553  mov     [rsi], rdi
0x18001b556  mov     rcx, [rbp+arg_10]
0x18001b55a  mov     [rbp+arg_10], 0
0x18001b562  test    rcx, rcx
0x18001b565  jz      short loc_18001B56D
0x18001b567  call    cs:__imp_SRCacheContext_Close
0x18001b56d  xor     eax, eax
0x18001b56f  mov     rbx, [rsp+20h+arg_0]
0x18001b574  mov     rsi, [rsp+20h+arg_8]
0x18001b579  add     rsp, 20h
0x18001b57d  pop     r14
0x18001b57f  pop     rdi
0x18001b580  pop     rbp
0x18001b581  retn
```
