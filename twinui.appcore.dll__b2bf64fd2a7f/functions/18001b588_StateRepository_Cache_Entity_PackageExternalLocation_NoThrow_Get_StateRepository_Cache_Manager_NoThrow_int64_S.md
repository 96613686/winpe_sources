# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18001b588`
- end: `0x18001b6ae`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037d54`

## callees

- `0x1800164ec`
- `0x180017e48`
- `0x18001b588`
- `0x18001bfd0`
- `0x18001cc38`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b618`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b693`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b618`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b693`

## string_xrefs

- `0x18001b5b1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001b5f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001b661`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        bool *a5)
{
  int Field; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-18h] BYREF
  char v15; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF

  v17 = a3;
  if ( !a2 )
  {
    Field = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      (int)v13);
    return (unsigned int)Field;
  }
  v9 = a5;
  v17 = 0;
  Field = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
            a1,
            a2,
            (struct StateRepository::Cache::Context_NoThrow *)&v17,
            a5);
  if ( Field < 0 )
  {
    v10 = 164;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v14 = 0;
    v13 = a4 + 3;
    v15 = 1;
    Field = StateRepository::Cache::Context_NoThrow::GetField(
              (StateRepository::Cache::Context_NoThrow *)&v17,
              L"Path",
              &v14);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)(unsigned int)Field,
        (int)v13);
      v10 = 169;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)(unsigned int)Field,
        (int)v13);
      v11 = v17;
      v17 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return (unsigned int)Field;
    }
    *a4 = a2;
  }
  v12 = v17;
  v17 = 0;
  if ( v12 )
    SRCacheContext_Close(v12);
  return 0;
}

```

## disassembly

```asm
0x18001b588  mov     [rsp-18h+arg_0], rbx
0x18001b58d  mov     [rsp-18h+arg_8], rsi
0x18001b592  mov     [rsp-18h+arg_10], r8
0x18001b597  push    rbp
0x18001b598  push    rdi
0x18001b599  push    r14
0x18001b59b  mov     rbp, rsp
0x18001b59e  sub     rsp, 40h
0x18001b5a2  mov     rsi, r9
0x18001b5a5  mov     rdi, rdx
0x18001b5a8  test    rdx, rdx
0x18001b5ab  jnz     short loc_18001B5D1
0x18001b5ad  mov     rcx, [rbp+18h]; this
0x18001b5b1  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b5b8  mov     ebx, 80070057h
0x18001b5bd  mov     edx, 0A1h; void *
0x18001b5c2  mov     r9d, ebx; char *
0x18001b5c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5ca  mov     eax, ebx
0x18001b5cc  jmp     loc_18001B69B
0x18001b5d1  mov     r14, [rbp+arg_20]
0x18001b5d5  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18001b5d9  mov     r9, r14; bool *
0x18001b5dc  mov     [rbp+arg_10], 0
0x18001b5e4  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001b5e9  mov     ebx, eax
0x18001b5eb  test    eax, eax
0x18001b5ed  jns     short loc_18001B620
0x18001b5ef  mov     edx, 0A4h; void *
0x18001b5f4  mov     rcx, [rbp+18h]; this
0x18001b5f8  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b5ff  mov     r9d, ebx; char *
0x18001b602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b607  mov     rcx, [rbp+arg_10]
0x18001b60b  mov     [rbp+arg_10], 0
0x18001b613  test    rcx, rcx
0x18001b616  jz      short loc_18001B5CA
0x18001b618  call    cs:__imp_SRCacheContext_Close
0x18001b61e  jmp     short loc_18001B5CA
0x18001b620  cmp     byte ptr [r14], 0
0x18001b624  jz      short loc_18001B682
0x18001b626  lea     rax, [rsi+18h]
0x18001b62a  mov     [rbp+var_18], 0
0x18001b632  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001b636  mov     [rbp+var_20], rax
0x18001b63a  lea     rdx, aPath; "Path"
0x18001b641  mov     [rbp+var_10], 1
0x18001b645  lea     rcx, [rbp+arg_10]; this
0x18001b649  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001b64e  lea     rcx, [rbp+var_20]
0x18001b652  mov     ebx, eax
0x18001b654  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18001b659  test    ebx, ebx
0x18001b65b  jns     short loc_18001B67F
0x18001b65d  mov     rcx, [rbp+18h]; this
0x18001b661  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b668  mov     r9d, ebx; char *
0x18001b66b  mov     edx, 269h; void *
0x18001b670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b675  mov     edx, 0A9h
0x18001b67a  jmp     loc_18001B5F4
0x18001b67f  mov     [rsi], rdi
0x18001b682  mov     rcx, [rbp+arg_10]
0x18001b686  mov     [rbp+arg_10], 0
0x18001b68e  test    rcx, rcx
0x18001b691  jz      short loc_18001B699
0x18001b693  call    cs:__imp_SRCacheContext_Close
0x18001b699  xor     eax, eax
0x18001b69b  mov     rbx, [rsp+40h+arg_0]
0x18001b6a0  mov     rsi, [rsp+40h+arg_8]
0x18001b6a5  add     rsp, 40h
0x18001b6a9  pop     r14
0x18001b6ab  pop     rdi
0x18001b6ac  pop     rbp
0x18001b6ad  retn
```
