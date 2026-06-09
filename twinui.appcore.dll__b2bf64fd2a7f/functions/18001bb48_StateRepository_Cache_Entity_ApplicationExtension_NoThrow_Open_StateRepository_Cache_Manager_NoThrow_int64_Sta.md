# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001bb48`
- end: `0x18001bd85`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001b008`

## callees

- `0x180008c58`
- `0x18000aa58`
- `0x18001bb48`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180036d30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001bbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001bbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bccf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bccf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bc06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bd57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bc06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bd57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bca1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bd42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bca1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bd42`

## string_xrefs

- `0x18001bbc8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bcec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bbe8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001bc7f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001bb97`: `ApplicationExtension\Data`
- `0x18001bd0d`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
    v9 = 365;
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
    v12 = 368;
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
    v12 = 369;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18001bb48  mov     [rsp-8+arg_10], rbx
0x18001bb4d  push    rbp
0x18001bb4e  push    rsi
0x18001bb4f  push    rdi
0x18001bb50  push    r14
0x18001bb52  push    r15
0x18001bb54  lea     rbp, [rsp-170h]
0x18001bb5c  sub     rsp, 270h
0x18001bb63  mov     rax, cs:__security_cookie
0x18001bb6a  xor     rax, rsp
0x18001bb6d  mov     [rbp+190h+var_30], rax
0x18001bb74  mov     rcx, [rcx]
0x18001bb77  lea     rax, [rsp+290h+var_270]
0x18001bb7c  mov     rsi, r9
0x18001bb7f  mov     [rsp+290h+var_268], rax
0x18001bb84  mov     rdi, r8
0x18001bb87  mov     [rsp+290h+var_258], 1
0x18001bb8c  mov     r14, rdx
0x18001bb8f  lea     r9, [rsp+290h+var_260]
0x18001bb94  xor     r15d, r15d
0x18001bb97  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x18001bb9e  xor     r8d, r8d
0x18001bba1  mov     qword ptr [rsp+290h+var_270], r15; int
0x18001bba6  mov     [rsp+290h+var_260], r15
0x18001bbab  call    cs:__imp_SRCacheContext_Open
0x18001bbb1  lea     rcx, [rsp+290h+var_268]
0x18001bbb6  mov     ebx, eax
0x18001bbb8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001bbbd  test    ebx, ebx
0x18001bbbf  jns     short loc_18001BC13
0x18001bbc1  mov     rcx, [rbp+198h]; this
0x18001bbc8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bbcf  mov     r9d, ebx; char *
0x18001bbd2  mov     edx, 18Ch; void *
0x18001bbd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbdc  mov     edx, 16Ch; void *
0x18001bbe1  mov     rcx, [rbp+198h]; this
0x18001bbe8  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bbef  mov     r9d, ebx; char *
0x18001bbf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbf7  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bbfc  mov     qword ptr [rsp+290h+var_270], r15
0x18001bc01  test    rcx, rcx
0x18001bc04  jz      short loc_18001BC0C
0x18001bc06  call    cs:__imp_SRCacheContext_Close
0x18001bc0c  mov     eax, ebx
0x18001bc0e  jmp     loc_18001BD5F
0x18001bc13  cmp     qword ptr [rsp+290h+var_270], r15
0x18001bc18  setnz   al
0x18001bc1b  test    al, al
0x18001bc1d  jnz     short loc_18001BC2B
0x18001bc1f  mov     ebx, 80670012h
0x18001bc24  mov     edx, 16Dh
0x18001bc29  jmp     short loc_18001BBE1
0x18001bc2b  xor     edx, edx; Val
0x18001bc2d  mov     [rsp+290h+var_250], r15
0x18001bc32  mov     r8d, 200h; Size
0x18001bc38  lea     rcx, [rsp+290h+var_248]; void *
0x18001bc3d  call    memset_0
0x18001bc42  lea     rax, [rsp+290h+var_248]
0x18001bc47  mov     [rbp+190h+var_48], r15
0x18001bc4e  mov     rdx, r14; unsigned __int64
0x18001bc51  mov     [rbp+190h+var_38], rax
0x18001bc58  lea     rcx, [rsp+290h+var_250]; this
0x18001bc5d  mov     [rbp+190h+var_40], 100h
0x18001bc68  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001bc6d  mov     ebx, eax
0x18001bc6f  test    eax, eax
0x18001bc71  jns     short loc_18001BCAC
0x18001bc73  mov     edx, 170h; void *
0x18001bc78  mov     rcx, [rbp+198h]; this
0x18001bc7f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bc86  mov     r9d, ebx; char *
0x18001bc89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc8e  mov     rcx, [rsp+290h+var_250]
0x18001bc93  mov     [rsp+290h+var_250], r15
0x18001bc98  test    rcx, rcx
0x18001bc9b  jz      loc_18001BBF7
0x18001bca1  call    cs:__imp_SRCache_Free
0x18001bca7  jmp     loc_18001BBF7
0x18001bcac  mov     rdx, [rbp+190h+var_38]
0x18001bcb3  lea     r9, [rsp+290h+var_260]
0x18001bcb8  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bcbd  xor     r8d, r8d
0x18001bcc0  mov     [rsp+290h+var_268], rdi
0x18001bcc5  mov     [rsp+290h+var_260], r15
0x18001bcca  mov     [rsp+290h+var_258], 1
0x18001bccf  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001bcd5  lea     rcx, [rsp+290h+var_268]
0x18001bcda  mov     ebx, eax
0x18001bcdc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001bce1  test    ebx, ebx
0x18001bce3  jns     short loc_18001BD0A
0x18001bce5  mov     rcx, [rbp+198h]; this
0x18001bcec  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bcf3  mov     r9d, ebx; char *
0x18001bcf6  mov     edx, 1B0h; void *
0x18001bcfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd00  mov     edx, 171h
0x18001bd05  jmp     loc_18001BC78
0x18001bd0a  cmp     [rdi], r15
0x18001bd0d  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x18001bd14  lea     rcx, [rsp+290h+var_270]; this
0x18001bd19  setnz   al
0x18001bd1c  mov     [rsi], al
0x18001bd1e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001bd23  mov     ebx, eax
0x18001bd25  test    eax, eax
0x18001bd27  jns     short loc_18001BD33
0x18001bd29  mov     edx, 173h
0x18001bd2e  jmp     loc_18001BC78
0x18001bd33  mov     rcx, [rsp+290h+var_250]
0x18001bd38  mov     [rsp+290h+var_250], r15
0x18001bd3d  test    rcx, rcx
0x18001bd40  jz      short loc_18001BD48
0x18001bd42  call    cs:__imp_SRCache_Free
0x18001bd48  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bd4d  mov     qword ptr [rsp+290h+var_270], r15
0x18001bd52  test    rcx, rcx
0x18001bd55  jz      short loc_18001BD5D
0x18001bd57  call    cs:__imp_SRCacheContext_Close
0x18001bd5d  xor     eax, eax
0x18001bd5f  mov     rcx, [rbp+190h+var_30]
0x18001bd66  xor     rcx, rsp; StackCookie
0x18001bd69  call    __security_check_cookie
0x18001bd6e  mov     rbx, [rsp+290h+arg_10]
0x18001bd76  add     rsp, 270h
0x18001bd7d  pop     r15
0x18001bd7f  pop     r14
0x18001bd81  pop     rdi
0x18001bd82  pop     rsi
0x18001bd83  pop     rbp
0x18001bd84  retn
```
