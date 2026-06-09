# StateRepository::Cache::Entity::AppUriHandler_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180005f98`
- end: `0x18000622b`
- name: `?Open@AppUriHandler_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `659`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004fe4`
- `0x180005e40`
- `0x180006280`
- `0x180009ad8`

## callees

- `0x180005150`
- `0x180005f98`
- `0x180010c04`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000610e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006172`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000610e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006172`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000601f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800060d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006123`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000601f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800060d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006123`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006187`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800060ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800060ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005ffb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005ffb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800060f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800060f3`

## string_xrefs

- `0x180006154`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x1800061e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180005fe7`: `AppUriHandler\Data`
- `0x1800060e1`: `AppUriHandler\Data`
- `0x180006134`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800061bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000620d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandler_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v21 = v20;
  v23 = 1;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v8 = SRCacheContext_Open(v4, L"AppUriHandler\\Data", 0, &v22);
  if ( v23 )
  {
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = v22;
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
      v20[0]);
    v19 = 409;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    goto LABEL_20;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v19 = 410;
    goto LABEL_25;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v16 = 413;
  }
  else
  {
    v21 = (int *)a3;
    v22 = 0;
    v23 = 1;
    v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
    if ( v23 )
    {
      v10 = *(_QWORD *)v21;
      *(_QWORD *)v21 = v22;
      if ( v10 )
        SRCacheContext_Close(v10);
    }
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v20[0]);
      v16 = 414;
    }
    else
    {
      v11 = *(_QWORD *)v20;
      *a4 = *(_QWORD *)a3 != 0;
      v12 = SRCacheContext_AddToCache(v11, L"AppUriHandler\\Data");
      v8 = v12;
      if ( v12 >= 0 )
      {
        v13 = v24;
        v24 = 0;
        if ( v13 )
          SRCache_Free(v13);
        v14 = *(_QWORD *)v20;
        *(_QWORD *)v20 = 0;
        if ( v14 )
          SRCacheContext_Close(v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v20[0]);
      v16 = 416;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
    (const char *)(unsigned int)v8,
    v20[0]);
  v17 = v24;
  v24 = 0;
  if ( v17 )
    SRCache_Free(v17);
LABEL_20:
  v18 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005f98  mov     [rsp-8+arg_10], rbx
0x180005f9d  push    rbp
0x180005f9e  push    rsi
0x180005f9f  push    rdi
0x180005fa0  push    r14
0x180005fa2  push    r15
0x180005fa4  lea     rbp, [rsp-170h]
0x180005fac  sub     rsp, 270h
0x180005fb3  mov     rax, cs:__security_cookie
0x180005fba  xor     rax, rsp
0x180005fbd  mov     [rbp+190h+var_30], rax
0x180005fc4  mov     rcx, [rcx]
0x180005fc7  lea     rax, [rsp+290h+var_270]
0x180005fcc  mov     r14, r9
0x180005fcf  mov     [rsp+290h+var_268], rax
0x180005fd4  mov     rdi, r8
0x180005fd7  mov     [rsp+290h+var_258], 1
0x180005fdc  mov     rsi, rdx
0x180005fdf  lea     r9, [rsp+290h+var_260]
0x180005fe4  xor     r15d, r15d
0x180005fe7  lea     rdx, aAppurihandlerD; "AppUriHandler\\Data"
0x180005fee  xor     r8d, r8d
0x180005ff1  mov     qword ptr [rsp+290h+var_270], r15; int
0x180005ff6  mov     [rsp+290h+var_260], r15
0x180005ffb  call    cs:__imp_SRCacheContext_Open
0x180006001  mov     ebx, eax
0x180006003  cmp     [rsp+290h+var_258], r15b
0x180006008  jz      short loc_180006025
0x18000600a  mov     r8, [rsp+290h+var_268]
0x18000600f  mov     rdx, [rsp+290h+var_260]
0x180006014  mov     rcx, [r8]
0x180006017  mov     [r8], rdx
0x18000601a  test    rcx, rcx
0x18000601d  jz      short loc_180006025
0x18000601f  call    cs:__imp_SRCacheContext_Close
0x180006025  test    ebx, ebx
0x180006027  js      loc_1800061B5
0x18000602d  cmp     qword ptr [rsp+290h+var_270], r15
0x180006032  setnz   al
0x180006035  test    al, al
0x180006037  jz      loc_1800061D7
0x18000603d  xor     edx, edx; Val
0x18000603f  mov     [rsp+290h+var_250], r15
0x180006044  mov     r8d, 200h; Size
0x18000604a  lea     rcx, [rsp+290h+var_248]; void *
0x18000604f  call    memset_0
0x180006054  lea     rax, [rsp+290h+var_248]
0x180006059  mov     [rbp+190h+var_48], r15
0x180006060  mov     rdx, rsi; unsigned __int64
0x180006063  mov     [rbp+190h+var_38], rax
0x18000606a  lea     rcx, [rsp+290h+var_250]; this
0x18000606f  mov     [rbp+190h+var_40], 100h
0x18000607a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18000607f  mov     ebx, eax
0x180006081  test    eax, eax
0x180006083  js      loc_1800061FC
0x180006089  mov     rdx, [rbp+190h+var_38]
0x180006090  lea     r9, [rsp+290h+var_260]
0x180006095  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000609a  xor     r8d, r8d
0x18000609d  mov     [rsp+290h+var_268], rdi
0x1800060a2  mov     [rsp+290h+var_260], r15
0x1800060a7  mov     [rsp+290h+var_258], 1
0x1800060ac  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800060b2  mov     ebx, eax
0x1800060b4  cmp     [rsp+290h+var_258], r15b
0x1800060b9  jz      short loc_1800060D6
0x1800060bb  mov     r8, [rsp+290h+var_268]
0x1800060c0  mov     rdx, [rsp+290h+var_260]
0x1800060c5  mov     rcx, [r8]
0x1800060c8  mov     [r8], rdx
0x1800060cb  test    rcx, rcx
0x1800060ce  jz      short loc_1800060D6
0x1800060d0  call    cs:__imp_SRCacheContext_Close
0x1800060d6  test    ebx, ebx
0x1800060d8  js      loc_180006206
0x1800060de  cmp     [rdi], r15
0x1800060e1  lea     rdx, aAppurihandlerD; "AppUriHandler\\Data"
0x1800060e8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800060ed  setnz   al
0x1800060f0  mov     [r14], al
0x1800060f3  call    cs:__imp_SRCacheContext_AddToCache
0x1800060f9  mov     ebx, eax
0x1800060fb  test    eax, eax
0x1800060fd  js      short loc_18000612D
0x1800060ff  mov     rcx, [rsp+290h+var_250]
0x180006104  mov     [rsp+290h+var_250], r15
0x180006109  test    rcx, rcx
0x18000610c  jz      short loc_180006114
0x18000610e  call    cs:__imp_SRCache_Free
0x180006114  mov     rcx, qword ptr [rsp+290h+var_270]
0x180006119  mov     qword ptr [rsp+290h+var_270], r15
0x18000611e  test    rcx, rcx
0x180006121  jz      short loc_180006129
0x180006123  call    cs:__imp_SRCacheContext_Close
0x180006129  xor     eax, eax
0x18000612b  jmp     short loc_18000618F
0x18000612d  mov     rcx, [rbp+198h]; this
0x180006134  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000613b  mov     r9d, ebx; char *
0x18000613e  mov     edx, 1A6h; void *
0x180006143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006148  mov     edx, 1A0h; void *
0x18000614d  mov     rcx, [rbp+198h]; this
0x180006154  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000615b  mov     r9d, ebx; char *
0x18000615e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006163  mov     rcx, [rsp+290h+var_250]
0x180006168  mov     [rsp+290h+var_250], r15
0x18000616d  test    rcx, rcx
0x180006170  jz      short loc_180006178
0x180006172  call    cs:__imp_SRCache_Free
0x180006178  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000617d  mov     qword ptr [rsp+290h+var_270], r15
0x180006182  test    rcx, rcx
0x180006185  jz      short loc_18000618D
0x180006187  call    cs:__imp_SRCacheContext_Close
0x18000618d  mov     eax, ebx
0x18000618f  mov     rcx, [rbp+190h+var_30]
0x180006196  xor     rcx, rsp; StackCookie
0x180006199  call    __security_check_cookie
0x18000619e  mov     rbx, [rsp+290h+arg_10]
0x1800061a6  add     rsp, 270h
0x1800061ad  pop     r15
0x1800061af  pop     r14
0x1800061b1  pop     rdi
0x1800061b2  pop     rsi
0x1800061b3  pop     rbp
0x1800061b4  retn
0x1800061b5  mov     rcx, [rbp+198h]; this
0x1800061bc  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800061c3  mov     r9d, ebx; char *
0x1800061c6  mov     edx, 18Ch; void *
0x1800061cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061d0  mov     edx, 199h
0x1800061d5  jmp     short loc_1800061E1
0x1800061d7  mov     ebx, 80670012h
0x1800061dc  mov     edx, 19Ah; void *
0x1800061e1  mov     rcx, [rbp+198h]; this
0x1800061e8  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800061ef  mov     r9d, ebx; char *
0x1800061f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061f7  jmp     loc_180006178
0x1800061fc  mov     edx, 19Dh
0x180006201  jmp     loc_18000614D
0x180006206  mov     rcx, [rbp+198h]; this
0x18000620d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006214  mov     r9d, ebx; char *
0x180006217  mov     edx, 1B0h; void *
0x18000621c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006221  mov     edx, 19Eh
0x180006226  jmp     loc_18000614D
```
