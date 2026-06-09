# StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x18000811c`
- end: `0x1800084d9`
- name: `?OpenByProgID@AppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `957`
- prototype: `int(StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006234`
- `0x180006280`

## callees

- `0x18000811c`
- `0x180010c04`
- `0x18001aa80`
- `0x180034470`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800082d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008389`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800082d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008389`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008163`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800081c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800082ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000834b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000839e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008163`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800081c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800082ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000834b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000839e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008327`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180008327`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000819d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000819d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000836e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000836e`

## string_xrefs

- `0x18000817f`: `AppUriHandler\Index\ProgID`
- `0x180008367`: `AppUriHandler\Index\ProgID`
- `0x1800082ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180008437`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000829f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800083e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000840b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800084b2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByProgID(
        StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  bool v11; // r8
  unsigned __int16 *v12; // rdx
  unsigned __int64 v13; // rdi
  __int64 v14; // r15
  const unsigned __int16 *i; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned __int16 *v26; // rdx
  unsigned __int64 j; // rcx
  int v28[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  char v31; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v33[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+248h] [rbp+148h]
  unsigned __int64 v35; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v36; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v29 = v28;
  *(_QWORD *)v28 = 0;
  v30 = 0;
  v31 = 1;
  v8 = SRCacheContext_Open(v7, L"AppUriHandler\\Index\\ProgID", 0, &v30);
  if ( v31 )
  {
    v9 = *(_QWORD *)v29;
    *(_QWORD *)v29 = v30;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v25 = 769;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
LABEL_22:
    v19 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    return (unsigned int)v8;
  }
  v10 = *(_QWORD *)v28;
  if ( !*(_QWORD *)v28 )
  {
    v8 = -2140733422;
    v25 = 770;
    goto LABEL_42;
  }
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v34 = 0;
  v12 = (unsigned __int16 *)v33;
  v36 = (unsigned __int16 *)v33;
  v35 = 256;
  if ( a3 )
  {
    v13 = 0;
    v14 = 0;
    for ( i = a3; *i; ++i )
    {
      if ( ++v13 >= 0x7FFFFFFF )
      {
        v8 = -2147024809;
        v16 = 309;
        goto LABEL_19;
      }
      if ( *i == 94 )
        ++v14;
    }
    v8 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(
           (StateRepository::Cache::Key_NoThrow *)&v32,
           v14 + v13 + 1,
           v11);
    if ( v8 < 0 )
    {
      v16 = 310;
      goto LABEL_19;
    }
    if ( v14 )
    {
      v26 = &v36[v34];
      for ( j = 0; j < v13; ++v26 )
      {
        if ( *a3 == 94 )
          *v26++ = 94;
        ++j;
        *v26 = *a3++;
      }
      *v26 = 0;
    }
    else
    {
      v8 = StringCchCatW(v36, v35, a3);
      if ( v8 < 0 )
      {
        v16 = 313;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v8,
          v28[0]);
        v17 = 773;
        goto LABEL_20;
      }
    }
    v34 += v13;
    v10 = *(_QWORD *)v28;
    v12 = v36;
  }
  v29 = (int *)this;
  v30 = 0;
  v31 = 1;
  v8 = SRCacheContext_OpenSubContext(v10, v12, 0, &v30);
  if ( v31 )
  {
    v21 = *(_QWORD *)v29;
    *(_QWORD *)v29 = v30;
    if ( v21 )
      SRCacheContext_Close(v21);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v17 = 776;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v18 = v32;
    v32 = 0;
    if ( v18 )
      SRCache_Free(v18);
    goto LABEL_22;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v22 = SRCacheContext_AddToCache(*(_QWORD *)v28, L"AppUriHandler\\Index\\ProgID");
  v8 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      v28[0]);
    v17 = 782;
    goto LABEL_20;
  }
  v23 = v32;
  v32 = 0;
  if ( v23 )
    SRCache_Free(v23);
  v24 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v24 )
    SRCacheContext_Close(v24);
  return 0;
}

```

## disassembly

```asm
0x18000811c  mov     [rsp-8+arg_18], rbx
0x180008121  push    rbp
0x180008122  push    rsi
0x180008123  push    rdi
0x180008124  push    r12
0x180008126  push    r13
0x180008128  push    r14
0x18000812a  push    r15
0x18000812c  lea     rbp, [rsp-170h]
0x180008134  sub     rsp, 270h
0x18000813b  mov     rax, cs:__security_cookie
0x180008142  xor     rax, rsp
0x180008145  mov     [rbp+1A0h+var_40], rax
0x18000814c  mov     rsi, rcx
0x18000814f  xor     r13d, r13d
0x180008152  mov     rcx, [rcx]
0x180008155  mov     r14, r8
0x180008158  mov     r12, rdx
0x18000815b  mov     [rsi], r13
0x18000815e  test    rcx, rcx
0x180008161  jz      short loc_180008169
0x180008163  call    cs:__imp_SRCacheContext_Close
0x180008169  mov     [rsi+8], r13d
0x18000816d  lea     rax, [rsp+2A0h+var_280]
0x180008172  mov     [rsi+10h], r13
0x180008176  lea     r9, [rsp+2A0h+var_270]
0x18000817b  mov     rcx, [r12]
0x18000817f  lea     rdx, aAppurihandlerI_0; "AppUriHandler\\Index\\ProgID"
0x180008186  xor     r8d, r8d
0x180008189  mov     [rsp+2A0h+var_278], rax
0x18000818e  mov     qword ptr [rsp+2A0h+var_280], r13; int
0x180008193  mov     [rsp+2A0h+var_270], r13
0x180008198  mov     [rsp+2A0h+var_268], 1
0x18000819d  call    cs:__imp_SRCacheContext_Open
0x1800081a3  mov     ebx, eax
0x1800081a5  cmp     [rsp+2A0h+var_268], r13b
0x1800081aa  jz      short loc_1800081C7
0x1800081ac  mov     r8, [rsp+2A0h+var_278]
0x1800081b1  mov     rdx, [rsp+2A0h+var_270]
0x1800081b6  mov     rcx, [r8]
0x1800081b9  mov     [r8], rdx
0x1800081bc  test    rcx, rcx
0x1800081bf  jz      short loc_1800081C7
0x1800081c1  call    cs:__imp_SRCacheContext_Close
0x1800081c7  test    ebx, ebx
0x1800081c9  js      loc_180008404
0x1800081cf  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x1800081d4  test    rbx, rbx
0x1800081d7  setnz   al
0x1800081da  test    al, al
0x1800081dc  jz      loc_180008426
0x1800081e2  xor     edx, edx; Val
0x1800081e4  mov     [rsp+2A0h+var_260], r13
0x1800081e9  mov     r8d, 200h; Size
0x1800081ef  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800081f4  call    memset_0
0x1800081f9  mov     [rbp+1A0h+var_58], r13
0x180008200  lea     rdx, [rsp+2A0h+var_258]
0x180008205  mov     [rbp+1A0h+var_48], rdx
0x18000820c  mov     [rbp+1A0h+var_50], 100h
0x180008217  test    r14, r14
0x18000821a  jz      loc_18000830D
0x180008220  mov     rdi, r13
0x180008223  mov     r15, r13
0x180008226  mov     rax, r14
0x180008229  mov     ecx, 5Eh ; '^'
0x18000822e  cmp     [rax], r13w
0x180008232  jz      short loc_180008253
0x180008234  inc     rdi
0x180008237  cmp     rdi, 7FFFFFFFh
0x18000823e  jnb     loc_1800083D0
0x180008244  cmp     [rax], cx
0x180008247  jz      loc_18000844B
0x18000824d  add     rax, 2
0x180008251  jmp     short loc_18000822E
0x180008253  lea     rdx, [rdi+1]
0x180008257  add     rdx, r15; unsigned __int64
0x18000825a  lea     rcx, [rsp+2A0h+var_260]; this
0x18000825f  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180008264  mov     ebx, eax
0x180008266  test    eax, eax
0x180008268  js      loc_180008453
0x18000826e  test    r15, r15
0x180008271  jnz     loc_18000845D
0x180008277  mov     rdx, [rbp+1A0h+var_50]; unsigned __int64
0x18000827e  mov     r8, r14; unsigned __int16 *
0x180008281  mov     rcx, [rbp+1A0h+var_48]; unsigned __int16 *
0x180008288  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000828d  mov     ebx, eax
0x18000828f  test    eax, eax
0x180008291  jns     short loc_1800082FA
0x180008293  mov     edx, 139h; void *
0x180008298  mov     rcx, [rbp+1A8h]; this
0x18000829f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800082a6  mov     r9d, ebx; char *
0x1800082a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082ae  mov     edx, 305h; void *
0x1800082b3  mov     rcx, [rbp+1A8h]; this
0x1800082ba  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800082c1  mov     r9d, ebx; char *
0x1800082c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082c9  mov     rcx, [rsp+2A0h+var_260]
0x1800082ce  mov     [rsp+2A0h+var_260], r13
0x1800082d3  test    rcx, rcx
0x1800082d6  jz      short loc_1800082DE
0x1800082d8  call    cs:__imp_SRCache_Free
0x1800082de  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800082e3  mov     qword ptr [rsp+2A0h+var_280], r13
0x1800082e8  test    rcx, rcx
0x1800082eb  jz      short loc_1800082F3
0x1800082ed  call    cs:__imp_SRCacheContext_Close
0x1800082f3  mov     eax, ebx
0x1800082f5  jmp     loc_1800083A6
0x1800082fa  add     [rbp+1A0h+var_58], rdi
0x180008301  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180008306  mov     rdx, [rbp+1A0h+var_48]
0x18000830d  lea     r9, [rsp+2A0h+var_270]
0x180008312  mov     [rsp+2A0h+var_278], rsi
0x180008317  xor     r8d, r8d
0x18000831a  mov     [rsp+2A0h+var_270], r13
0x18000831f  mov     rcx, rbx
0x180008322  mov     [rsp+2A0h+var_268], 1
0x180008327  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000832d  mov     ebx, eax
0x18000832f  cmp     [rsp+2A0h+var_268], r13b
0x180008334  jz      short loc_180008351
0x180008336  mov     r8, [rsp+2A0h+var_278]
0x18000833b  mov     rdx, [rsp+2A0h+var_270]
0x180008340  mov     rcx, [r8]
0x180008343  mov     [r8], rdx
0x180008346  test    rcx, rcx
0x180008349  jz      short loc_180008351
0x18000834b  call    cs:__imp_SRCacheContext_Close
0x180008351  test    ebx, ebx
0x180008353  js      loc_1800084AB
0x180008359  cmp     [rsi], r13
0x18000835c  jnz     loc_1800084D0
0x180008362  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180008367  lea     rdx, aAppurihandlerI_0; "AppUriHandler\\Index\\ProgID"
0x18000836e  call    cs:__imp_SRCacheContext_AddToCache
0x180008374  mov     ebx, eax
0x180008376  test    eax, eax
0x180008378  js      short loc_1800083DF
0x18000837a  mov     rcx, [rsp+2A0h+var_260]
0x18000837f  mov     [rsp+2A0h+var_260], r13
0x180008384  test    rcx, rcx
0x180008387  jz      short loc_18000838F
0x180008389  call    cs:__imp_SRCache_Free
0x18000838f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180008394  mov     qword ptr [rsp+2A0h+var_280], r13
0x180008399  test    rcx, rcx
0x18000839c  jz      short loc_1800083A4
0x18000839e  call    cs:__imp_SRCacheContext_Close
0x1800083a4  xor     eax, eax
0x1800083a6  mov     rcx, [rbp+1A0h+var_40]
0x1800083ad  xor     rcx, rsp; StackCookie
0x1800083b0  call    __security_check_cookie
0x1800083b5  mov     rbx, [rsp+2A0h+arg_18]
0x1800083bd  add     rsp, 270h
0x1800083c4  pop     r15
0x1800083c6  pop     r14
0x1800083c8  pop     r13
0x1800083ca  pop     r12
0x1800083cc  pop     rdi
0x1800083cd  pop     rsi
0x1800083ce  pop     rbp
0x1800083cf  retn
0x1800083d0  mov     ebx, 80070057h
0x1800083d5  mov     edx, 135h
0x1800083da  jmp     loc_180008298
0x1800083df  mov     rcx, [rbp+1A8h]; this
0x1800083e6  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800083ed  mov     r9d, ebx; char *
0x1800083f0  mov     edx, 1A6h; void *
0x1800083f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083fa  mov     edx, 30Eh
0x1800083ff  jmp     loc_1800082B3
0x180008404  mov     rcx, [rbp+1A8h]; this
0x18000840b  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008412  mov     r9d, ebx; char *
0x180008415  mov     edx, 18Ch; void *
0x18000841a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000841f  mov     edx, 301h
0x180008424  jmp     short loc_180008430
0x180008426  mov     ebx, 80670012h
0x18000842b  mov     edx, 302h; void *
0x180008430  mov     rcx, [rbp+1A8h]; this
0x180008437  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000843e  mov     r9d, ebx; char *
0x180008441  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008446  jmp     loc_1800082DE
0x18000844b  inc     r15
0x18000844e  jmp     loc_18000824D
0x180008453  mov     edx, 136h
0x180008458  jmp     loc_180008298
0x18000845d  mov     rcx, [rbp+1A0h+var_58]
0x180008464  mov     rax, [rbp+1A0h+var_48]
0x18000846b  lea     rdx, [rax+rcx*2]
0x18000846f  mov     rcx, r13
0x180008472  test    rdi, rdi
0x180008475  jz      short loc_1800084A2
0x180008477  mov     r8d, 5Eh ; '^'
0x18000847d  cmp     [r14], r8w
0x180008481  jnz     short loc_18000848B
0x180008483  mov     [rdx], r8w
0x180008487  add     rdx, 2
0x18000848b  movzx   eax, word ptr [r14]
0x18000848f  inc     rcx
0x180008492  mov     [rdx], ax
0x180008495  add     r14, 2
0x180008499  add     rdx, 2
0x18000849d  cmp     rcx, rdi
0x1800084a0  jb      short loc_18000847D
0x1800084a2  mov     [rdx], r13w
0x1800084a6  jmp     loc_1800082FA
0x1800084ab  mov     rcx, [rbp+1A8h]; this
0x1800084b2  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800084b9  mov     r9d, ebx; char *
0x1800084bc  mov     edx, 1B0h; void *
0x1800084c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084c6  mov     edx, 308h
0x1800084cb  jmp     loc_1800082B3
0x1800084d0  mov     [rsi+10h], r12
0x1800084d4  jmp     loc_180008362
```
