# StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180077420`
- end: `0x18007765d`
- name: `?Open@AppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180077420`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180077579`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007761a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180077579`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007761a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800774de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007762f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800774de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007762f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800775a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800775a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180077483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180077483`

## string_xrefs

- `0x1800774a0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800775c4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800774c0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandlerGroup.hpp`
- `0x180077557`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandlerGroup.hpp`
- `0x18007746f`: `AppUriHandlerGroup\Data`
- `0x1800775e5`: `AppUriHandlerGroup\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"AppUriHandlerGroup\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandlerGroup.hpp",
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
    v9 = 246;
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
    v12 = 249;
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
    v12 = 250;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"AppUriHandlerGroup\\Data");
  if ( v8 < 0 )
  {
    v12 = 252;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x180077420  mov     [rsp-8+arg_10], rbx
0x180077425  push    rbp
0x180077426  push    rsi
0x180077427  push    rdi
0x180077428  push    r14
0x18007742a  push    r15
0x18007742c  lea     rbp, [rsp-170h]
0x180077434  sub     rsp, 270h
0x18007743b  mov     rax, cs:__security_cookie
0x180077442  xor     rax, rsp
0x180077445  mov     [rbp+190h+var_30], rax
0x18007744c  mov     rcx, [rcx]
0x18007744f  lea     rax, [rsp+290h+var_270]
0x180077454  mov     rsi, r9
0x180077457  mov     [rsp+290h+var_268], rax
0x18007745c  mov     rdi, r8
0x18007745f  mov     [rsp+290h+var_258], 1
0x180077464  mov     r14, rdx
0x180077467  lea     r9, [rsp+290h+var_260]
0x18007746c  xor     r15d, r15d
0x18007746f  lea     rdx, aAppurihandlerg; "AppUriHandlerGroup\\Data"
0x180077476  xor     r8d, r8d
0x180077479  mov     qword ptr [rsp+290h+var_270], r15; int
0x18007747e  mov     [rsp+290h+var_260], r15
0x180077483  call    cs:__imp_SRCacheContext_Open
0x180077489  lea     rcx, [rsp+290h+var_268]
0x18007748e  mov     ebx, eax
0x180077490  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180077495  test    ebx, ebx
0x180077497  jns     short loc_1800774EB
0x180077499  mov     rcx, [rbp+198h]; this
0x1800774a0  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800774a7  mov     r9d, ebx; char *
0x1800774aa  mov     edx, 18Ch; void *
0x1800774af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800774b4  mov     edx, 0F5h; void *
0x1800774b9  mov     rcx, [rbp+198h]; this
0x1800774c0  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800774c7  mov     r9d, ebx; char *
0x1800774ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800774cf  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800774d4  mov     qword ptr [rsp+290h+var_270], r15
0x1800774d9  test    rcx, rcx
0x1800774dc  jz      short loc_1800774E4
0x1800774de  call    cs:__imp_SRCacheContext_Close
0x1800774e4  mov     eax, ebx
0x1800774e6  jmp     loc_180077637
0x1800774eb  cmp     qword ptr [rsp+290h+var_270], r15
0x1800774f0  setnz   al
0x1800774f3  test    al, al
0x1800774f5  jnz     short loc_180077503
0x1800774f7  mov     ebx, 80670012h
0x1800774fc  mov     edx, 0F6h
0x180077501  jmp     short loc_1800774B9
0x180077503  xor     edx, edx; Val
0x180077505  mov     [rsp+290h+var_250], r15
0x18007750a  mov     r8d, 200h; Size
0x180077510  lea     rcx, [rsp+290h+var_248]; void *
0x180077515  call    memset_0
0x18007751a  lea     rax, [rsp+290h+var_248]
0x18007751f  mov     [rbp+190h+var_48], r15
0x180077526  mov     rdx, r14; unsigned __int64
0x180077529  mov     [rbp+190h+var_38], rax
0x180077530  lea     rcx, [rsp+290h+var_250]; this
0x180077535  mov     [rbp+190h+var_40], 100h
0x180077540  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180077545  mov     ebx, eax
0x180077547  test    eax, eax
0x180077549  jns     short loc_180077584
0x18007754b  mov     edx, 0F9h; void *
0x180077550  mov     rcx, [rbp+198h]; this
0x180077557  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007755e  mov     r9d, ebx; char *
0x180077561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077566  mov     rcx, [rsp+290h+var_250]
0x18007756b  mov     [rsp+290h+var_250], r15
0x180077570  test    rcx, rcx
0x180077573  jz      loc_1800774CF
0x180077579  call    cs:__imp_SRCache_Free
0x18007757f  jmp     loc_1800774CF
0x180077584  mov     rdx, [rbp+190h+var_38]
0x18007758b  lea     r9, [rsp+290h+var_260]
0x180077590  mov     rcx, qword ptr [rsp+290h+var_270]
0x180077595  xor     r8d, r8d
0x180077598  mov     [rsp+290h+var_268], rdi
0x18007759d  mov     [rsp+290h+var_260], r15
0x1800775a2  mov     [rsp+290h+var_258], 1
0x1800775a7  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800775ad  lea     rcx, [rsp+290h+var_268]
0x1800775b2  mov     ebx, eax
0x1800775b4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800775b9  test    ebx, ebx
0x1800775bb  jns     short loc_1800775E2
0x1800775bd  mov     rcx, [rbp+198h]; this
0x1800775c4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800775cb  mov     r9d, ebx; char *
0x1800775ce  mov     edx, 1B0h; void *
0x1800775d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800775d8  mov     edx, 0FAh
0x1800775dd  jmp     loc_180077550
0x1800775e2  cmp     [rdi], r15
0x1800775e5  lea     rdx, aAppurihandlerg; "AppUriHandlerGroup\\Data"
0x1800775ec  lea     rcx, [rsp+290h+var_270]; this
0x1800775f1  setnz   al
0x1800775f4  mov     [rsi], al
0x1800775f6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800775fb  mov     ebx, eax
0x1800775fd  test    eax, eax
0x1800775ff  jns     short loc_18007760B
0x180077601  mov     edx, 0FCh
0x180077606  jmp     loc_180077550
0x18007760b  mov     rcx, [rsp+290h+var_250]
0x180077610  mov     [rsp+290h+var_250], r15
0x180077615  test    rcx, rcx
0x180077618  jz      short loc_180077620
0x18007761a  call    cs:__imp_SRCache_Free
0x180077620  mov     rcx, qword ptr [rsp+290h+var_270]
0x180077625  mov     qword ptr [rsp+290h+var_270], r15
0x18007762a  test    rcx, rcx
0x18007762d  jz      short loc_180077635
0x18007762f  call    cs:__imp_SRCacheContext_Close
0x180077635  xor     eax, eax
0x180077637  mov     rcx, [rbp+190h+var_30]
0x18007763e  xor     rcx, rsp; StackCookie
0x180077641  call    __security_check_cookie
0x180077646  mov     rbx, [rsp+290h+arg_10]
0x18007764e  add     rsp, 270h
0x180077655  pop     r15
0x180077657  pop     r14
0x180077659  pop     rdi
0x18007765a  pop     rsi
0x18007765b  pop     rbp
0x18007765c  retn
```
