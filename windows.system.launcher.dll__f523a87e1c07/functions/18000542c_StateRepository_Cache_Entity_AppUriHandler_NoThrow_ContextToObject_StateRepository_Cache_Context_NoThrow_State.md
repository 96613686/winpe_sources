# StateRepository::Cache::Entity::AppUriHandler_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,__int64)

- ea: `0x18000542c`
- end: `0x1800056c8`
- name: `?ContextToObject@AppUriHandler_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `668`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004fe4`
- `0x180005e40`
- `0x180006280`
- `0x180009ad8`

## callees

- `0x18000542c`
- `0x180010c04`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000555a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800055e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000555a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800055e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800054d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800055c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800054d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800055c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800054a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000550a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180005595`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800054a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000550a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180005595`

## string_xrefs

- `0x1800055de`: `AppUriHandlerGroup`
- `0x18000560e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180005654`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000543e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180005553`: `Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandler_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rcx
  int Field_String; // eax
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int Field_UInt32; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // rdx
  __int64 *v23; // [rsp+20h] [rbp-20h]
  int v24; // [rsp+20h] [rbp-20h]
  __int64 v25; // [rsp+28h] [rbp-18h] BYREF
  char v26; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  if ( !a3 || (a3 & 1) != 0 )
  {
    v8 = *a1;
    v23 = a2 + 1;
    v25 = 0;
    v26 = 1;
    Field_String = SRCacheContext_GetField_String(v8, L"HostName", &v25);
    v10 = Field_String;
    if ( Field_String < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        (int)v23);
    else
      v10 = 0;
    if ( v26 )
    {
      v11 = *v23;
      *v23 = v25;
      if ( v11 )
        SRCache_Free(v11);
    }
    if ( v10 < 0 )
    {
      v22 = 996;
      goto LABEL_34;
    }
    if ( !a3 )
      goto LABEL_21;
  }
  if ( (a3 & 2) != 0 )
  {
LABEL_21:
    v12 = *a1;
    v23 = a2 + 2;
    v25 = 0;
    v26 = 1;
    v13 = SRCacheContext_GetField_String(v12, L"Path", &v25);
    v10 = v13;
    if ( v13 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v13,
        (int)v23);
    else
      v10 = 0;
    if ( v26 )
    {
      v14 = *v23;
      *v23 = v25;
      if ( v14 )
        SRCache_Free(v14);
    }
    if ( v10 < 0 )
    {
      v22 = 1000;
      goto LABEL_34;
    }
    if ( !a3 )
      goto LABEL_22;
  }
  if ( (a3 & 4) != 0 )
  {
LABEL_22:
    Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Extension", a2 + 3);
    v10 = Field_UInt32;
    if ( Field_UInt32 >= 0 )
    {
      if ( !a3 )
        goto LABEL_24;
      goto LABEL_5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v23);
    v22 = 1004;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v10,
      (int)v23);
    return (unsigned int)v10;
  }
LABEL_5:
  if ( (a3 & 8) == 0 )
    goto LABEL_6;
LABEL_24:
  v16 = *a1;
  v23 = a2 + 4;
  v25 = 0;
  v26 = 1;
  v17 = SRCacheContext_GetField_String(v16, L"ProgID", &v25);
  v10 = v17;
  if ( v17 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      (int)v23);
  else
    v10 = 0;
  if ( v26 )
  {
    v18 = *v23;
    *v23 = v25;
    if ( v18 )
      SRCache_Free(v18);
  }
  if ( v10 < 0 )
  {
    v22 = 1008;
    goto LABEL_34;
  }
  if ( a3 )
  {
LABEL_6:
    if ( (a3 & 0x10) == 0 )
    {
LABEL_32:
      *a2 = a4;
      return 0;
    }
  }
  v19 = SRCacheContext_GetField_UInt32(*a1, L"AppUriHandlerGroup", a2 + 5);
  v20 = v19;
  if ( v19 >= 0 )
    goto LABEL_32;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x221,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)v19,
    (int)v23);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3F4,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
    (const char *)v20,
    v24);
  return v20;
}

```

## disassembly

```asm
0x18000542c  push    rbp
0x18000542e  push    rbx
0x18000542f  push    rsi
0x180005430  push    rdi
0x180005431  push    r13
0x180005433  push    r14
0x180005435  push    r15
0x180005437  mov     rbp, rsp
0x18000543a  sub     rsp, 40h
0x18000543e  lea     r13, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005445  mov     r15, r9
0x180005448  mov     rbx, r8
0x18000544b  mov     rsi, rdx
0x18000544e  mov     r14, rcx
0x180005451  test    r8, r8
0x180005454  jz      short loc_180005484
0x180005456  test    bl, 1
0x180005459  jnz     short loc_180005484
0x18000545b  test    bl, 2
0x18000545e  jnz     loc_1800054E8
0x180005464  test    bl, 4
0x180005467  jnz     loc_18000554C
0x18000546d  test    bl, 8
0x180005470  jnz     loc_180005573
0x180005476  test    bl, 10h
0x180005479  jz      loc_1800055F1
0x18000547f  jmp     loc_1800055D7
0x180005484  mov     rcx, [rcx]
0x180005487  lea     rax, [rdx+8]
0x18000548b  lea     rdx, aHostname; "HostName"
0x180005492  mov     [rbp+var_20], rax
0x180005496  lea     r8, [rbp+var_18]
0x18000549a  mov     [rbp+var_18], 0
0x1800054a2  mov     [rbp+var_10], 1
0x1800054a6  call    cs:__imp_SRCacheContext_GetField_String
0x1800054ac  mov     edi, eax
0x1800054ae  test    eax, eax
0x1800054b0  js      loc_180005673
0x1800054b6  xor     edi, edi
0x1800054b8  cmp     [rbp+var_10], 0
0x1800054bc  jz      short loc_1800054D7
0x1800054be  mov     rdx, [rbp+var_20]
0x1800054c2  mov     rax, [rbp+var_18]
0x1800054c6  mov     rcx, [rdx]
0x1800054c9  mov     [rdx], rax
0x1800054cc  test    rcx, rcx
0x1800054cf  jz      short loc_1800054D7
0x1800054d1  call    cs:__imp_SRCache_Free
0x1800054d7  test    edi, edi
0x1800054d9  js      loc_18000566C
0x1800054df  test    rbx, rbx
0x1800054e2  jnz     loc_18000545B
0x1800054e8  mov     rcx, [r14]
0x1800054eb  lea     rax, [rsi+10h]
0x1800054ef  lea     r8, [rbp+var_18]
0x1800054f3  mov     [rbp+var_20], rax
0x1800054f7  lea     rdx, aPath; "Path"
0x1800054fe  mov     [rbp+var_18], 0
0x180005506  mov     [rbp+var_10], 1
0x18000550a  call    cs:__imp_SRCacheContext_GetField_String
0x180005510  mov     edi, eax
0x180005512  test    eax, eax
0x180005514  js      loc_18000568C
0x18000551a  xor     edi, edi
0x18000551c  cmp     [rbp+var_10], 0
0x180005520  jz      short loc_18000553B
0x180005522  mov     rdx, [rbp+var_20]
0x180005526  mov     rax, [rbp+var_18]
0x18000552a  mov     rcx, [rdx]
0x18000552d  mov     [rdx], rax
0x180005530  test    rcx, rcx
0x180005533  jz      short loc_18000553B
0x180005535  call    cs:__imp_SRCache_Free
0x18000553b  test    edi, edi
0x18000553d  js      loc_180005605
0x180005543  test    rbx, rbx
0x180005546  jnz     loc_180005464
0x18000554c  mov     rcx, [r14]
0x18000554f  lea     r8, [rsi+18h]
0x180005553  lea     rdx, aExtension; "Extension"
0x18000555a  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180005560  mov     edi, eax
0x180005562  test    eax, eax
0x180005564  js      loc_180005621
0x18000556a  test    rbx, rbx
0x18000556d  jnz     loc_18000546D
0x180005573  mov     rcx, [r14]
0x180005576  lea     rax, [rsi+20h]
0x18000557a  lea     r8, [rbp+var_18]
0x18000557e  mov     [rbp+var_20], rax
0x180005582  lea     rdx, aProgid_0; "ProgID"
0x180005589  mov     [rbp+var_18], 0
0x180005591  mov     [rbp+var_10], 1
0x180005595  call    cs:__imp_SRCacheContext_GetField_String
0x18000559b  mov     edi, eax
0x18000559d  test    eax, eax
0x18000559f  js      loc_1800056A5
0x1800055a5  xor     edi, edi
0x1800055a7  cmp     [rbp+var_10], 0
0x1800055ab  jz      short loc_1800055C6
0x1800055ad  mov     rdx, [rbp+var_20]
0x1800055b1  mov     rax, [rbp+var_18]
0x1800055b5  mov     rcx, [rdx]
0x1800055b8  mov     [rdx], rax
0x1800055bb  test    rcx, rcx
0x1800055be  jz      short loc_1800055C6
0x1800055c0  call    cs:__imp_SRCache_Free
0x1800055c6  test    edi, edi
0x1800055c8  js      loc_1800056BE
0x1800055ce  test    rbx, rbx
0x1800055d1  jnz     loc_180005476
0x1800055d7  mov     rcx, [r14]
0x1800055da  lea     r8, [rsi+28h]
0x1800055de  lea     rdx, aAppurihandlerg_0; "AppUriHandlerGroup"
0x1800055e5  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800055eb  mov     ebx, eax
0x1800055ed  test    eax, eax
0x1800055ef  js      short loc_18000563C
0x1800055f1  mov     [rsi], r15
0x1800055f4  xor     eax, eax
0x1800055f6  add     rsp, 40h
0x1800055fa  pop     r15
0x1800055fc  pop     r14
0x1800055fe  pop     r13
0x180005600  pop     rdi
0x180005601  pop     rsi
0x180005602  pop     rbx
0x180005603  pop     rbp
0x180005604  retn
0x180005605  mov     edx, 3E8h; void *
0x18000560a  mov     rcx, [rbp+38h]; this
0x18000560e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005615  mov     r9d, edi; char *
0x180005618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000561d  mov     eax, edi
0x18000561f  jmp     short loc_1800055F6
0x180005621  mov     rcx, [rbp+38h]; this
0x180005625  mov     r9d, edi; char *
0x180005628  mov     r8, r13; unsigned int
0x18000562b  mov     edx, 221h; void *
0x180005630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005635  mov     edx, 3ECh
0x18000563a  jmp     short loc_18000560A
0x18000563c  mov     rcx, [rbp+38h]; this
0x180005640  mov     r9d, ebx; char *
0x180005643  mov     r8, r13; unsigned int
0x180005646  mov     edx, 221h; void *
0x18000564b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005650  mov     rcx, [rbp+38h]; this
0x180005654  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000565b  mov     r9d, ebx; char *
0x18000565e  mov     edx, 3F4h; void *
0x180005663  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005668  mov     eax, ebx
0x18000566a  jmp     short loc_1800055F6
0x18000566c  mov     edx, 3E4h
0x180005671  jmp     short loc_18000560A
0x180005673  mov     rcx, [rbp+38h]; this
0x180005677  mov     r9d, eax; char *
0x18000567a  mov     r8, r13; unsigned int
0x18000567d  mov     edx, 246h; void *
0x180005682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005687  jmp     loc_1800054B8
0x18000568c  mov     rcx, [rbp+38h]; this
0x180005690  mov     r9d, eax; char *
0x180005693  mov     r8, r13; unsigned int
0x180005696  mov     edx, 246h; void *
0x18000569b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056a0  jmp     loc_18000551C
0x1800056a5  mov     rcx, [rbp+38h]; this
0x1800056a9  mov     r9d, eax; char *
0x1800056ac  mov     r8, r13; unsigned int
0x1800056af  mov     edx, 246h; void *
0x1800056b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b9  jmp     loc_1800055A7
0x1800056be  mov     edx, 3F0h
0x1800056c3  jmp     loc_18000560A
```
