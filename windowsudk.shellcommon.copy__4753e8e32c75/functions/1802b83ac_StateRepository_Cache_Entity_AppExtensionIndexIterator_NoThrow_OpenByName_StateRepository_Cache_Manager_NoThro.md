# StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *)

- ea: `0x1802b83ac`
- end: `0x1802b8673`
- name: `?OpenByName@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEB_W@Z`
- size: `711`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1802b42dc`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b83ac`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b858d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b858d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b855f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8616`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8630`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b855f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8616`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b8630`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b83ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b84cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8645`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b83ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b84cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b8645`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b8428`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b8428`

## string_xrefs

- `0x1802b8445`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b85aa`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b8460`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b84a3`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b853d`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b85ef`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b840a`: `AppExtension\Index\Name`
- `0x1802b85d1`: `AppExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(
        StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const wchar_t *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  char v21; // [rsp+30h] [rbp-D0h]
  int v22[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close();
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  *(_QWORD *)v19 = v22;
  *(_QWORD *)v22 = 0;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_Open(v7, L"AppExtension\\Index\\Name", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v19);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
LABEL_5:
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v9 )
      SRCacheContext_Close();
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v22 )
  {
    v11 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)0x80670012LL,
      v19[0]);
LABEL_10:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close();
    return v11;
  }
  memset_0(v24, 0, sizeof(v24));
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v8 < 0 )
  {
    v13 = 602;
    goto LABEL_15;
  }
  *(_QWORD *)v19 = this;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v19);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v13 = 605;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v8,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_5;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"AppExtension\\Index\\Name");
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_10;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v18 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x1802b83ac  mov     [rsp-8+arg_18], rbx
0x1802b83b1  push    rbp
0x1802b83b2  push    rsi
0x1802b83b3  push    rdi
0x1802b83b4  push    r14
0x1802b83b6  push    r15
0x1802b83b8  lea     rbp, [rsp-170h]
0x1802b83c0  sub     rsp, 270h
0x1802b83c7  mov     rax, cs:__security_cookie
0x1802b83ce  xor     rax, rsp
0x1802b83d1  mov     [rbp+190h+var_30], rax
0x1802b83d8  mov     rbx, rcx
0x1802b83db  xor     r15d, r15d
0x1802b83de  mov     rcx, [rcx]
0x1802b83e1  mov     r14, r8
0x1802b83e4  mov     rsi, rdx
0x1802b83e7  mov     [rbx], r15
0x1802b83ea  test    rcx, rcx
0x1802b83ed  jz      short loc_1802B83F5
0x1802b83ef  call    cs:__imp_SRCacheContext_Close
0x1802b83f5  mov     [rbx+8], r15d
0x1802b83f9  lea     rax, [rsp+290h+var_258]
0x1802b83fe  mov     [rbx+10h], r15
0x1802b8402  lea     r9, [rsp+290h+var_268]
0x1802b8407  mov     rcx, [rsi]
0x1802b840a  lea     rdx, aAppextensionIn; "AppExtension\\Index\\Name"
0x1802b8411  xor     r8d, r8d
0x1802b8414  mov     qword ptr [rsp+290h+var_270], rax; int
0x1802b8419  mov     qword ptr [rsp+290h+var_258], r15
0x1802b841e  mov     [rsp+290h+var_268], r15
0x1802b8423  mov     [rsp+290h+var_260], 1
0x1802b8428  call    cs:__imp_SRCacheContext_Open
0x1802b842e  lea     rcx, [rsp+290h+var_270]
0x1802b8433  mov     edi, eax
0x1802b8435  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b843a  test    edi, edi
0x1802b843c  jns     short loc_1802B8490
0x1802b843e  mov     rcx, [rbp+198h]; this
0x1802b8445  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b844c  mov     r9d, edi; char *
0x1802b844f  mov     edx, 18Ch; void *
0x1802b8454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8459  mov     rcx, [rbp+198h]; this
0x1802b8460  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8467  mov     r9d, edi; char *
0x1802b846a  mov     edx, 256h; void *
0x1802b846f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8474  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b8479  mov     qword ptr [rsp+290h+var_258], r15
0x1802b847e  test    rcx, rcx
0x1802b8481  jz      short loc_1802B8489
0x1802b8483  call    cs:__imp_SRCacheContext_Close
0x1802b8489  mov     eax, edi
0x1802b848b  jmp     loc_1802B864D
0x1802b8490  cmp     qword ptr [rsp+290h+var_258], r15
0x1802b8495  setnz   al
0x1802b8498  test    al, al
0x1802b849a  jnz     short loc_1802B84D8
0x1802b849c  mov     rcx, [rbp+198h]; this
0x1802b84a3  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b84aa  mov     ebx, 80670012h
0x1802b84af  mov     edx, 257h; void *
0x1802b84b4  mov     r9d, ebx; char *
0x1802b84b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b84bc  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b84c1  mov     qword ptr [rsp+290h+var_258], r15
0x1802b84c6  test    rcx, rcx
0x1802b84c9  jz      short loc_1802B84D1
0x1802b84cb  call    cs:__imp_SRCacheContext_Close
0x1802b84d1  mov     eax, ebx
0x1802b84d3  jmp     loc_1802B864D
0x1802b84d8  mov     edi, 200h
0x1802b84dd  lea     rcx, [rsp+290h+var_248]; void *
0x1802b84e2  mov     r8d, edi; Size
0x1802b84e5  xor     edx, edx; Val
0x1802b84e7  call    memset_0
0x1802b84ec  mov     r8d, edi; Size
0x1802b84ef  mov     [rsp+290h+var_250], r15
0x1802b84f4  xor     edx, edx; Val
0x1802b84f6  lea     rcx, [rsp+290h+var_248]; void *
0x1802b84fb  call    memset_0
0x1802b8500  lea     rax, [rsp+290h+var_248]
0x1802b8505  mov     [rbp+190h+var_48], r15
0x1802b850c  mov     rdx, r14; wchar_t *
0x1802b850f  mov     [rbp+190h+var_38], rax
0x1802b8516  lea     rcx, [rsp+290h+var_250]; this
0x1802b851b  mov     [rbp+190h+var_40], 100h
0x1802b8526  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b852b  mov     edi, eax
0x1802b852d  test    eax, eax
0x1802b852f  jns     short loc_1802B856A
0x1802b8531  mov     edx, 25Ah; void *
0x1802b8536  mov     rcx, [rbp+198h]; this
0x1802b853d  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8544  mov     r9d, edi; char *
0x1802b8547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b854c  mov     rcx, [rsp+290h+var_250]
0x1802b8551  mov     [rsp+290h+var_250], r15
0x1802b8556  test    rcx, rcx
0x1802b8559  jz      loc_1802B8474
0x1802b855f  call    cs:__imp_SRCache_Free
0x1802b8565  jmp     loc_1802B8474
0x1802b856a  mov     rdx, [rbp+190h+var_38]
0x1802b8571  lea     r9, [rsp+290h+var_268]
0x1802b8576  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b857b  xor     r8d, r8d
0x1802b857e  mov     qword ptr [rsp+290h+var_270], rbx; int
0x1802b8583  mov     [rsp+290h+var_268], r15
0x1802b8588  mov     [rsp+290h+var_260], 1
0x1802b858d  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b8593  lea     rcx, [rsp+290h+var_270]
0x1802b8598  mov     edi, eax
0x1802b859a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b859f  test    edi, edi
0x1802b85a1  jns     short loc_1802B85C8
0x1802b85a3  mov     rcx, [rbp+198h]; this
0x1802b85aa  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b85b1  mov     r9d, edi; char *
0x1802b85b4  mov     edx, 1B0h; void *
0x1802b85b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b85be  mov     edx, 25Dh
0x1802b85c3  jmp     loc_1802B8536
0x1802b85c8  cmp     [rbx], r15
0x1802b85cb  jz      short loc_1802B85D1
0x1802b85cd  mov     [rbx+10h], rsi
0x1802b85d1  lea     rdx, aAppextensionIn; "AppExtension\\Index\\Name"
0x1802b85d8  lea     rcx, [rsp+290h+var_258]; this
0x1802b85dd  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b85e2  mov     ebx, eax
0x1802b85e4  test    eax, eax
0x1802b85e6  jns     short loc_1802B8621
0x1802b85e8  mov     rcx, [rbp+198h]; this
0x1802b85ef  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b85f6  mov     r9d, eax; char *
0x1802b85f9  mov     edx, 263h; void *
0x1802b85fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8603  mov     rcx, [rsp+290h+var_250]
0x1802b8608  mov     [rsp+290h+var_250], r15
0x1802b860d  test    rcx, rcx
0x1802b8610  jz      loc_1802B84BC
0x1802b8616  call    cs:__imp_SRCache_Free
0x1802b861c  jmp     loc_1802B84BC
0x1802b8621  mov     rcx, [rsp+290h+var_250]
0x1802b8626  mov     [rsp+290h+var_250], r15
0x1802b862b  test    rcx, rcx
0x1802b862e  jz      short loc_1802B8636
0x1802b8630  call    cs:__imp_SRCache_Free
0x1802b8636  mov     rcx, qword ptr [rsp+290h+var_258]
0x1802b863b  mov     qword ptr [rsp+290h+var_258], r15
0x1802b8640  test    rcx, rcx
0x1802b8643  jz      short loc_1802B864B
0x1802b8645  call    cs:__imp_SRCacheContext_Close
0x1802b864b  xor     eax, eax
0x1802b864d  mov     rcx, [rbp+190h+var_30]
0x1802b8654  xor     rcx, rsp; StackCookie
0x1802b8657  call    __security_check_cookie
0x1802b865c  mov     rbx, [rsp+290h+arg_18]
0x1802b8664  add     rsp, 270h
0x1802b866b  pop     r15
0x1802b866d  pop     r14
0x1802b866f  pop     rdi
0x1802b8670  pop     rsi
0x1802b8671  pop     rbp
0x1802b8672  retn
```
