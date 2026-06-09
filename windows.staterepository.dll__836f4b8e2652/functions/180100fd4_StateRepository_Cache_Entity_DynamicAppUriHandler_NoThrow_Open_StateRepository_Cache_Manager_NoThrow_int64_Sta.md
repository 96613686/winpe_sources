# StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180100fd4`
- end: `0x180101211`
- name: `?Open@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180269ab8`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x180100fd4`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18010115b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18010115b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801011e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801011e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010112d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801011ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010112d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801011ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180101037`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180101037`

## string_xrefs

- `0x180101054`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180101178`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180101023`: `DynamicAppUriHandler\Data`
- `0x180101199`: `DynamicAppUriHandler\Data`
- `0x180101074`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x18010110b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandler.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"DynamicAppUriHandler\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 394;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandler.hpp",
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
    v9 = 395;
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
    v12 = 398;
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 399;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"DynamicAppUriHandler\\Data");
  if ( v8 < 0 )
  {
    v12 = 401;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandler.hpp",
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
0x180100fd4  mov     [rsp-8+arg_10], rbx
0x180100fd9  push    rbp
0x180100fda  push    rsi
0x180100fdb  push    rdi
0x180100fdc  push    r14
0x180100fde  push    r15
0x180100fe0  lea     rbp, [rsp-170h]
0x180100fe8  sub     rsp, 270h
0x180100fef  mov     rax, cs:__security_cookie
0x180100ff6  xor     rax, rsp
0x180100ff9  mov     [rbp+190h+var_30], rax
0x180101000  mov     rcx, [rcx]
0x180101003  lea     rax, [rsp+290h+var_270]
0x180101008  mov     rsi, r9
0x18010100b  mov     [rsp+290h+var_268], rax
0x180101010  mov     rdi, r8
0x180101013  mov     [rsp+290h+var_258], 1
0x180101018  mov     r14, rdx
0x18010101b  lea     r9, [rsp+290h+var_260]
0x180101020  xor     r15d, r15d
0x180101023  lea     rdx, aDynamicappurih_25; "DynamicAppUriHandler\\Data"
0x18010102a  xor     r8d, r8d
0x18010102d  mov     qword ptr [rsp+290h+var_270], r15; int
0x180101032  mov     [rsp+290h+var_260], r15
0x180101037  call    cs:__imp_SRCacheContext_Open
0x18010103d  lea     rcx, [rsp+290h+var_268]
0x180101042  mov     ebx, eax
0x180101044  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180101049  test    ebx, ebx
0x18010104b  jns     short loc_18010109F
0x18010104d  mov     rcx, [rbp+198h]; this
0x180101054  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18010105b  mov     r9d, ebx; char *
0x18010105e  mov     edx, 18Ch; void *
0x180101063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101068  mov     edx, 18Ah; void *
0x18010106d  mov     rcx, [rbp+198h]; this
0x180101074  lea     r8, aOnecoreBaseApp_344; "onecore\\base\\appmodel\\StateRepositor"...
0x18010107b  mov     r9d, ebx; char *
0x18010107e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101083  mov     rcx, qword ptr [rsp+290h+var_270]
0x180101088  mov     qword ptr [rsp+290h+var_270], r15
0x18010108d  test    rcx, rcx
0x180101090  jz      short loc_180101098
0x180101092  call    cs:__imp_SRCacheContext_Close
0x180101098  mov     eax, ebx
0x18010109a  jmp     loc_1801011EB
0x18010109f  cmp     qword ptr [rsp+290h+var_270], r15
0x1801010a4  setnz   al
0x1801010a7  test    al, al
0x1801010a9  jnz     short loc_1801010B7
0x1801010ab  mov     ebx, 80670012h
0x1801010b0  mov     edx, 18Bh
0x1801010b5  jmp     short loc_18010106D
0x1801010b7  xor     edx, edx; Val
0x1801010b9  mov     [rsp+290h+var_250], r15
0x1801010be  mov     r8d, 200h; Size
0x1801010c4  lea     rcx, [rsp+290h+var_248]; void *
0x1801010c9  call    memset_0
0x1801010ce  lea     rax, [rsp+290h+var_248]
0x1801010d3  mov     [rbp+190h+var_48], r15
0x1801010da  mov     rdx, r14; unsigned __int64
0x1801010dd  mov     [rbp+190h+var_38], rax
0x1801010e4  lea     rcx, [rsp+290h+var_250]; this
0x1801010e9  mov     [rbp+190h+var_40], 100h
0x1801010f4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801010f9  mov     ebx, eax
0x1801010fb  test    eax, eax
0x1801010fd  jns     short loc_180101138
0x1801010ff  mov     edx, 18Eh; void *
0x180101104  mov     rcx, [rbp+198h]; this
0x18010110b  lea     r8, aOnecoreBaseApp_344; "onecore\\base\\appmodel\\StateRepositor"...
0x180101112  mov     r9d, ebx; char *
0x180101115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010111a  mov     rcx, [rsp+290h+var_250]
0x18010111f  mov     [rsp+290h+var_250], r15
0x180101124  test    rcx, rcx
0x180101127  jz      loc_180101083
0x18010112d  call    cs:__imp_SRCache_Free
0x180101133  jmp     loc_180101083
0x180101138  mov     rdx, [rbp+190h+var_38]
0x18010113f  lea     r9, [rsp+290h+var_260]
0x180101144  mov     rcx, qword ptr [rsp+290h+var_270]
0x180101149  xor     r8d, r8d
0x18010114c  mov     [rsp+290h+var_268], rdi
0x180101151  mov     [rsp+290h+var_260], r15
0x180101156  mov     [rsp+290h+var_258], 1
0x18010115b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180101161  lea     rcx, [rsp+290h+var_268]
0x180101166  mov     ebx, eax
0x180101168  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18010116d  test    ebx, ebx
0x18010116f  jns     short loc_180101196
0x180101171  mov     rcx, [rbp+198h]; this
0x180101178  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18010117f  mov     r9d, ebx; char *
0x180101182  mov     edx, 1B0h; void *
0x180101187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010118c  mov     edx, 18Fh
0x180101191  jmp     loc_180101104
0x180101196  cmp     [rdi], r15
0x180101199  lea     rdx, aDynamicappurih_25; "DynamicAppUriHandler\\Data"
0x1801011a0  lea     rcx, [rsp+290h+var_270]; this
0x1801011a5  setnz   al
0x1801011a8  mov     [rsi], al
0x1801011aa  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801011af  mov     ebx, eax
0x1801011b1  test    eax, eax
0x1801011b3  jns     short loc_1801011BF
0x1801011b5  mov     edx, 191h
0x1801011ba  jmp     loc_180101104
0x1801011bf  mov     rcx, [rsp+290h+var_250]
0x1801011c4  mov     [rsp+290h+var_250], r15
0x1801011c9  test    rcx, rcx
0x1801011cc  jz      short loc_1801011D4
0x1801011ce  call    cs:__imp_SRCache_Free
0x1801011d4  mov     rcx, qword ptr [rsp+290h+var_270]
0x1801011d9  mov     qword ptr [rsp+290h+var_270], r15
0x1801011de  test    rcx, rcx
0x1801011e1  jz      short loc_1801011E9
0x1801011e3  call    cs:__imp_SRCacheContext_Close
0x1801011e9  xor     eax, eax
0x1801011eb  mov     rcx, [rbp+190h+var_30]
0x1801011f2  xor     rcx, rsp; StackCookie
0x1801011f5  call    __security_check_cookie
0x1801011fa  mov     rbx, [rsp+290h+arg_10]
0x180101202  add     rsp, 270h
0x180101209  pop     r15
0x18010120b  pop     r14
0x18010120d  pop     rdi
0x18010120e  pop     rsi
0x18010120f  pop     rbp
0x180101210  retn
```
