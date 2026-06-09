# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180084268`
- end: `0x18008454c`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180067484`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180084268`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800844ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800844ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800842d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008436b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800843b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008451e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800842d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008436b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800843b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008451e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180084466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180084466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180084310`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180084310`

## string_xrefs

- `0x18008432d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180084483`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800842ac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180084348`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18008438b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180084416`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800844c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v19[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v20 = v19;
  *(_QWORD *)v19 = 0;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_Open(v9, L"Application\\Index\\Package", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
LABEL_8:
    v11 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v19 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v12 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v10 < 0 )
  {
    v13 = 1001;
    goto LABEL_17;
  }
  v20 = (int *)this;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v13 = 1004;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v19,
          L"Application\\Index\\Package");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_13;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = *(_QWORD *)v19;
  *(_QWORD *)v19 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x180084268  mov     [rsp-8+arg_18], rbx
0x18008426d  push    rbp
0x18008426e  push    rsi
0x18008426f  push    rdi
0x180084270  push    r14
0x180084272  push    r15
0x180084274  lea     rbp, [rsp-170h]
0x18008427c  sub     rsp, 270h
0x180084283  mov     rax, cs:__security_cookie
0x18008428a  xor     rax, rsp
0x18008428d  mov     [rbp+190h+var_30], rax
0x180084294  xor     r15d, r15d
0x180084297  mov     r14, r8
0x18008429a  mov     rsi, rdx
0x18008429d  mov     rbx, rcx
0x1800842a0  test    r8, r8
0x1800842a3  jnz     short loc_1800842CC
0x1800842a5  mov     rcx, [rbp+198h]; this
0x1800842ac  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800842b3  mov     ebx, 80070057h
0x1800842b8  mov     edx, 3DFh; void *
0x1800842bd  mov     r9d, ebx; char *
0x1800842c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800842c5  mov     eax, ebx
0x1800842c7  jmp     loc_180084526
0x1800842cc  mov     rcx, [rcx]
0x1800842cf  mov     [rbx], r15
0x1800842d2  test    rcx, rcx
0x1800842d5  jz      short loc_1800842DD
0x1800842d7  call    cs:__imp_SRCacheContext_Close
0x1800842dd  mov     [rbx+8], r15d
0x1800842e1  lea     rax, [rsp+290h+var_270]
0x1800842e6  mov     [rbx+10h], r15
0x1800842ea  lea     r9, [rsp+290h+var_260]
0x1800842ef  mov     rcx, [rsi]
0x1800842f2  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x1800842f9  xor     r8d, r8d
0x1800842fc  mov     [rsp+290h+var_268], rax
0x180084301  mov     qword ptr [rsp+290h+var_270], r15; int
0x180084306  mov     [rsp+290h+var_260], r15
0x18008430b  mov     [rsp+290h+var_258], 1
0x180084310  call    cs:__imp_SRCacheContext_Open
0x180084316  lea     rcx, [rsp+290h+var_268]
0x18008431b  mov     edi, eax
0x18008431d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180084322  test    edi, edi
0x180084324  jns     short loc_180084378
0x180084326  mov     rcx, [rbp+198h]; this
0x18008432d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180084334  mov     r9d, edi; char *
0x180084337  mov     edx, 18Ch; void *
0x18008433c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084341  mov     rcx, [rbp+198h]; this
0x180084348  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008434f  mov     r9d, edi; char *
0x180084352  mov     edx, 3E5h; void *
0x180084357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008435c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084361  mov     qword ptr [rsp+290h+var_270], r15
0x180084366  test    rcx, rcx
0x180084369  jz      short loc_180084371
0x18008436b  call    cs:__imp_SRCacheContext_Close
0x180084371  mov     eax, edi
0x180084373  jmp     loc_180084526
0x180084378  cmp     qword ptr [rsp+290h+var_270], r15
0x18008437d  setnz   al
0x180084380  test    al, al
0x180084382  jnz     short loc_1800843C2
0x180084384  mov     rcx, [rbp+198h]; this
0x18008438b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180084392  mov     ebx, 80670012h
0x180084397  mov     edx, 3E6h; void *
0x18008439c  mov     r9d, ebx; char *
0x18008439f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800843a4  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800843a9  mov     qword ptr [rsp+290h+var_270], r15
0x1800843ae  test    rcx, rcx
0x1800843b1  jz      loc_1800842C5
0x1800843b7  call    cs:__imp_SRCacheContext_Close
0x1800843bd  jmp     loc_1800842C5
0x1800843c2  xor     edx, edx; Val
0x1800843c4  mov     [rsp+290h+var_250], r15
0x1800843c9  mov     r8d, 200h; Size
0x1800843cf  lea     rcx, [rsp+290h+var_248]; void *
0x1800843d4  call    memset_0
0x1800843d9  lea     rax, [rsp+290h+var_248]
0x1800843de  mov     [rbp+190h+var_48], r15
0x1800843e5  mov     rdx, r14; unsigned __int64
0x1800843e8  mov     [rbp+190h+var_38], rax
0x1800843ef  lea     rcx, [rsp+290h+var_250]; this
0x1800843f4  mov     [rbp+190h+var_40], 100h
0x1800843ff  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180084404  mov     edi, eax
0x180084406  test    eax, eax
0x180084408  jns     short loc_180084443
0x18008440a  mov     edx, 3E9h; void *
0x18008440f  mov     rcx, [rbp+198h]; this
0x180084416  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008441d  mov     r9d, edi; char *
0x180084420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084425  mov     rcx, [rsp+290h+var_250]
0x18008442a  mov     [rsp+290h+var_250], r15
0x18008442f  test    rcx, rcx
0x180084432  jz      loc_18008435C
0x180084438  call    cs:__imp_SRCache_Free
0x18008443e  jmp     loc_18008435C
0x180084443  mov     rdx, [rbp+190h+var_38]
0x18008444a  lea     r9, [rsp+290h+var_260]
0x18008444f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084454  xor     r8d, r8d
0x180084457  mov     [rsp+290h+var_268], rbx
0x18008445c  mov     [rsp+290h+var_260], r15
0x180084461  mov     [rsp+290h+var_258], 1
0x180084466  call    cs:__imp_SRCacheContext_OpenSubContext
0x18008446c  lea     rcx, [rsp+290h+var_268]
0x180084471  mov     edi, eax
0x180084473  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180084478  test    edi, edi
0x18008447a  jns     short loc_1800844A1
0x18008447c  mov     rcx, [rbp+198h]; this
0x180084483  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008448a  mov     r9d, edi; char *
0x18008448d  mov     edx, 1B0h; void *
0x180084492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084497  mov     edx, 3ECh
0x18008449c  jmp     loc_18008440F
0x1800844a1  cmp     [rbx], r15
0x1800844a4  jz      short loc_1800844AA
0x1800844a6  mov     [rbx+10h], rsi
0x1800844aa  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x1800844b1  lea     rcx, [rsp+290h+var_270]; this
0x1800844b6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800844bb  mov     ebx, eax
0x1800844bd  test    eax, eax
0x1800844bf  jns     short loc_1800844FA
0x1800844c1  mov     rcx, [rbp+198h]; this
0x1800844c8  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800844cf  mov     r9d, eax; char *
0x1800844d2  mov     edx, 3F2h; void *
0x1800844d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800844dc  mov     rcx, [rsp+290h+var_250]
0x1800844e1  mov     [rsp+290h+var_250], r15
0x1800844e6  test    rcx, rcx
0x1800844e9  jz      loc_1800843A4
0x1800844ef  call    cs:__imp_SRCache_Free
0x1800844f5  jmp     loc_1800843A4
0x1800844fa  mov     rcx, [rsp+290h+var_250]
0x1800844ff  mov     [rsp+290h+var_250], r15
0x180084504  test    rcx, rcx
0x180084507  jz      short loc_18008450F
0x180084509  call    cs:__imp_SRCache_Free
0x18008450f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180084514  mov     qword ptr [rsp+290h+var_270], r15
0x180084519  test    rcx, rcx
0x18008451c  jz      short loc_180084524
0x18008451e  call    cs:__imp_SRCacheContext_Close
0x180084524  xor     eax, eax
0x180084526  mov     rcx, [rbp+190h+var_30]
0x18008452d  xor     rcx, rsp; StackCookie
0x180084530  call    __security_check_cookie
0x180084535  mov     rbx, [rsp+290h+arg_18]
0x18008453d  add     rsp, 270h
0x180084544  pop     r15
0x180084546  pop     r14
0x180084548  pop     rdi
0x180084549  pop     rsi
0x18008454a  pop     rbp
0x18008454b  retn
```
