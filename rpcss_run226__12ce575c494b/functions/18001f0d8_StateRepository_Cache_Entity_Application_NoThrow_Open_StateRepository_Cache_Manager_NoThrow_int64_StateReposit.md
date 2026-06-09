# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001f0d8`
- end: `0x18001f3cd`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180094190`

## callees

- `0x18001f0d8`
- `0x1800211f0`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001f1d4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001f1d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f16d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f2db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f16d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f2db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001f143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001f143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f2c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f2f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f2c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f2f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001f228`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001f228`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001f275`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001f275`

## string_xrefs

- `0x18001f3aa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001f2a8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001f348`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001f288`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001f363`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001f388`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+238h] [rbp+138h]
  __int64 v28; // [rsp+240h] [rbp+140h]
  _BYTE *v29; // [rsp+248h] [rbp+148h]
  unsigned __int16 v30[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v31; // [rsp+258h] [rbp+158h] BYREF
  char v32; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v30 = v24;
  v32 = 1;
  *(_QWORD *)v24 = 0;
  v31 = 0;
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v31);
  if ( v32 )
  {
    v9 = v31;
    v10 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v10 )
      SRCacheContext_Close(v10, v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v23 = 433;
    goto LABEL_25;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v23 = 434;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
LABEL_16:
    v19 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v17);
    return (unsigned int)v8;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v28 = 256;
  v29 = v26;
  if ( (unsigned int)_o__ui64tow_s(a2, v30, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v24[0]);
    goto LABEL_29;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v30);
  if ( v8 < 0 )
  {
LABEL_29:
    v16 = 437;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_16;
  }
  *(_QWORD *)v30 = a3;
  v31 = 0;
  v32 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v24, v29, 0, &v31);
  if ( v32 )
  {
    v11 = v31;
    v12 = **(_QWORD **)v30;
    **(_QWORD **)v30 = v31;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
    v16 = 438;
    goto LABEL_14;
  }
  v13 = *(_QWORD *)v24;
  *a4 = *(_QWORD *)a3 != 0;
  v14 = SRCacheContext_AddToCache(v13, L"Application\\Data");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      v24[0]);
    v16 = 440;
    goto LABEL_14;
  }
  v21 = v25;
  v25 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v15);
  return 0;
}

```

## disassembly

```asm
0x18001f0d8  mov     [rsp-8+arg_10], rbx
0x18001f0dd  push    rbp
0x18001f0de  push    rsi
0x18001f0df  push    rdi
0x18001f0e0  push    r14
0x18001f0e2  push    r15
0x18001f0e4  lea     rbp, [rsp-180h]
0x18001f0ec  sub     rsp, 280h
0x18001f0f3  mov     rax, cs:__security_cookie
0x18001f0fa  xor     rax, rsp
0x18001f0fd  mov     [rbp+1A0h+var_28], rax
0x18001f104  mov     rcx, [rcx]
0x18001f107  lea     rax, [rsp+2A0h+var_280]
0x18001f10c  mov     r14, r9
0x18001f10f  mov     qword ptr [rbp+1A0h+var_50], rax
0x18001f116  mov     rdi, r8
0x18001f119  mov     [rbp+1A0h+var_40], 1
0x18001f120  mov     rsi, rdx
0x18001f123  lea     r9, [rbp+1A0h+var_48]
0x18001f12a  xor     r15d, r15d
0x18001f12d  lea     rdx, aApplicationDat; "Application\\Data"
0x18001f134  xor     r8d, r8d
0x18001f137  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18001f13c  mov     [rbp+1A0h+var_48], r15
0x18001f143  call    cs:__imp_SRCacheContext_Open
0x18001f149  mov     ebx, eax
0x18001f14b  cmp     [rbp+1A0h+var_40], r15b
0x18001f152  jz      short loc_18001F173
0x18001f154  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18001f15b  mov     rdx, [rbp+1A0h+var_48]
0x18001f162  mov     rcx, [r8]
0x18001f165  mov     [r8], rdx
0x18001f168  test    rcx, rcx
0x18001f16b  jz      short loc_18001F173
0x18001f16d  call    cs:__imp_SRCacheContext_Close
0x18001f173  test    ebx, ebx
0x18001f175  js      loc_18001F381
0x18001f17b  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18001f180  setnz   al
0x18001f183  test    al, al
0x18001f185  jz      loc_18001F337
0x18001f18b  xor     edx, edx; Val
0x18001f18d  mov     [rsp+2A0h+var_270], r15
0x18001f192  mov     r8d, 200h; Size
0x18001f198  lea     rcx, [rsp+2A0h+var_268]; void *
0x18001f19d  call    memset_0
0x18001f1a2  mov     r9d, 10h
0x18001f1a8  mov     [rbp+1A0h+var_68], r15
0x18001f1af  lea     rax, [rsp+2A0h+var_268]
0x18001f1b4  mov     [rbp+1A0h+var_60], 100h
0x18001f1bf  lea     rdx, [rbp+1A0h+var_50]
0x18001f1c6  mov     [rbp+1A0h+var_58], rax
0x18001f1cd  mov     rcx, rsi
0x18001f1d0  lea     r8d, [r9+1]
0x18001f1d4  call    cs:__imp__o__ui64tow_s
0x18001f1da  test    eax, eax
0x18001f1dc  jnz     loc_18001F3A3
0x18001f1e2  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18001f1e9  lea     rcx, [rsp+2A0h+var_270]; this
0x18001f1ee  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001f1f3  mov     ebx, eax
0x18001f1f5  test    eax, eax
0x18001f1f7  js      loc_18001F3C3
0x18001f1fd  mov     rdx, [rbp+1A0h+var_58]
0x18001f204  lea     r9, [rbp+1A0h+var_48]
0x18001f20b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f210  xor     r8d, r8d
0x18001f213  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18001f21a  mov     [rbp+1A0h+var_48], r15
0x18001f221  mov     [rbp+1A0h+var_40], 1
0x18001f228  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001f22e  mov     ebx, eax
0x18001f230  cmp     [rbp+1A0h+var_40], r15b
0x18001f237  jz      short loc_18001F258
0x18001f239  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18001f240  mov     rdx, [rbp+1A0h+var_48]
0x18001f247  mov     rcx, [r8]
0x18001f24a  mov     [r8], rdx
0x18001f24d  test    rcx, rcx
0x18001f250  jz      short loc_18001F258
0x18001f252  call    cs:__imp_SRCacheContext_Close
0x18001f258  test    ebx, ebx
0x18001f25a  js      loc_18001F35C
0x18001f260  cmp     [rdi], r15
0x18001f263  lea     rdx, aApplicationDat; "Application\\Data"
0x18001f26a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f26f  setnz   al
0x18001f272  mov     [r14], al
0x18001f275  call    cs:__imp_SRCacheContext_AddToCache
0x18001f27b  mov     ebx, eax
0x18001f27d  test    eax, eax
0x18001f27f  jns     short loc_18001F2E5
0x18001f281  mov     rcx, [rbp+1A8h]; this
0x18001f288  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f28f  mov     r9d, eax; char *
0x18001f292  mov     edx, 1A6h; void *
0x18001f297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f29c  mov     edx, 1B8h; void *
0x18001f2a1  mov     rcx, [rbp+1A8h]; this
0x18001f2a8  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f2af  mov     r9d, ebx; char *
0x18001f2b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f2b7  mov     rcx, [rsp+2A0h+var_270]
0x18001f2bc  mov     [rsp+2A0h+var_270], r15
0x18001f2c1  test    rcx, rcx
0x18001f2c4  jz      short loc_18001F2CC
0x18001f2c6  call    cs:__imp_SRCache_Free
0x18001f2cc  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f2d1  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001f2d6  test    rcx, rcx
0x18001f2d9  jz      short loc_18001F2E1
0x18001f2db  call    cs:__imp_SRCacheContext_Close
0x18001f2e1  mov     eax, ebx
0x18001f2e3  jmp     short loc_18001F311
0x18001f2e5  mov     rcx, [rsp+2A0h+var_270]
0x18001f2ea  mov     [rsp+2A0h+var_270], r15
0x18001f2ef  test    rcx, rcx
0x18001f2f2  jz      short loc_18001F2FA
0x18001f2f4  call    cs:__imp_SRCache_Free
0x18001f2fa  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f2ff  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001f304  test    rcx, rcx
0x18001f307  jz      short loc_18001F30F
0x18001f309  call    cs:__imp_SRCacheContext_Close
0x18001f30f  xor     eax, eax
0x18001f311  mov     rcx, [rbp+1A0h+var_28]
0x18001f318  xor     rcx, rsp; StackCookie
0x18001f31b  call    __security_check_cookie
0x18001f320  mov     rbx, [rsp+2A0h+arg_10]
0x18001f328  add     rsp, 280h
0x18001f32f  pop     r15
0x18001f331  pop     r14
0x18001f333  pop     rdi
0x18001f334  pop     rsi
0x18001f335  pop     rbp
0x18001f336  retn
0x18001f337  mov     ebx, 80670012h
0x18001f33c  mov     edx, 1B2h; void *
0x18001f341  mov     rcx, [rbp+1A8h]; this
0x18001f348  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f34f  mov     r9d, ebx; char *
0x18001f352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f357  jmp     loc_18001F2CC
0x18001f35c  mov     rcx, [rbp+1A8h]; this
0x18001f363  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f36a  mov     r9d, ebx; char *
0x18001f36d  mov     edx, 1B0h; void *
0x18001f372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f377  mov     edx, 1B6h
0x18001f37c  jmp     loc_18001F2A1
0x18001f381  mov     rcx, [rbp+1A8h]; this
0x18001f388  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f38f  mov     r9d, ebx; char *
0x18001f392  mov     edx, 18Ch; void *
0x18001f397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f39c  mov     edx, 1B1h
0x18001f3a1  jmp     short loc_18001F341
0x18001f3a3  mov     rcx, [rbp+1A8h]; this
0x18001f3aa  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f3b1  mov     ebx, 8000FFFFh
0x18001f3b6  mov     edx, 166h; void *
0x18001f3bb  mov     r9d, ebx; char *
0x18001f3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3c3  mov     edx, 1B5h
0x18001f3c8  jmp     loc_18001F2A1
```
