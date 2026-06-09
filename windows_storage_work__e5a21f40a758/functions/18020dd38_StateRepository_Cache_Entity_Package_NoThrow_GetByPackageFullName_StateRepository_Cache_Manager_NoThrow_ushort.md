# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18020dd38`
- end: `0x18020e059`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `801`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18020d6c0`
- `0x18020dca0`

## callees

- `0x1800432f0`
- `0x1800a0e00`
- `0x18020dd38`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020de51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020de51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020dff9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e04e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020dff9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e04e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020ddba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020de75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020ddba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020de75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df04`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020df6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020dd96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020dd96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18020de97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18020de97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18020deb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18020deb3`

## string_xrefs

- `0x18020dee6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020dfa3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020dfbe`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020dec6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020dfde`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020e00b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020e030`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  int *v25; // [rsp+30h] [rbp-D0h]
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  char v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+258h] [rbp+158h]
  __int64 v31; // [rsp+260h] [rbp+160h]
  _BYTE *v32; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v27 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v23 = 0;
  v25 = v23;
  v26 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v26);
  if ( v27 )
  {
    v7 = *(_QWORD *)v25;
    *(_QWORD *)v25 = v26;
    if ( v7 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v23[0]);
    v22 = 1128;
    goto LABEL_30;
  }
  if ( !*(_QWORD *)v23 )
  {
    v6 = -2140733422;
    v22 = 1129;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v23[0]);
LABEL_19:
    v17 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
    if ( v17 )
      SRCacheContext_Close(v17, v14);
    return v6;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v23[0]);
LABEL_17:
    v16 = v28;
    v28 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_19;
  }
  v25 = (int *)&v24;
  v24 = 0;
  v26 = 0;
  v27 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v23, v32, 0, &v26);
  if ( v27 )
  {
    v9 = *(_QWORD *)v25;
    *(_QWORD *)v25 = v26;
    if ( v9 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v23[0]);
    v13 = 1136;
    goto LABEL_15;
  }
  if ( v24 )
  {
    v10 = SRCacheContext_EnumerateData(v24, 0, a3);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v23[0]);
      v13 = 1139;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)v6,
        v23[0]);
      v15 = v24;
      v24 = 0;
      if ( v15 )
        SRCacheContext_Close(v15, v14);
      goto LABEL_17;
    }
  }
  v11 = SRCacheContext_AddToCache(*(_QWORD *)v23, L"Package\\Index\\PackageFullName");
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v23[0]);
    v13 = 1142;
    goto LABEL_15;
  }
  v19 = v24;
  v24 = 0;
  if ( v19 )
    ((void (*)(void))SRCacheContext_Close)();
  v20 = v28;
  v28 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v23;
  *(_QWORD *)v23 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v12);
  return 0;
}

```

## disassembly

```asm
0x18020dd38  push    rbp
0x18020dd3a  push    rbx
0x18020dd3b  push    rsi
0x18020dd3c  push    rdi
0x18020dd3d  push    r14
0x18020dd3f  lea     rbp, [rsp-180h]
0x18020dd47  sub     rsp, 280h
0x18020dd4e  mov     rax, cs:__security_cookie
0x18020dd55  xor     rax, rsp
0x18020dd58  mov     [rbp+1A0h+var_30], rax
0x18020dd5f  xor     r14d, r14d
0x18020dd62  mov     [rsp+2A0h+var_260], 1
0x18020dd67  mov     [r8], r14
0x18020dd6a  lea     rax, [rsp+2A0h+var_280]
0x18020dd6f  mov     rcx, [rcx]
0x18020dd72  lea     r9, [rsp+2A0h+var_268]
0x18020dd77  mov     rdi, r8
0x18020dd7a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18020dd7f  mov     rsi, rdx
0x18020dd82  mov     [rsp+2A0h+var_270], rax
0x18020dd87  xor     r8d, r8d
0x18020dd8a  mov     [rsp+2A0h+var_268], r14
0x18020dd8f  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18020dd96  call    cs:__imp_SRCacheContext_Open
0x18020dd9c  mov     ebx, eax
0x18020dd9e  cmp     [rsp+2A0h+var_260], r14b
0x18020dda3  jz      short loc_18020DDC0
0x18020dda5  mov     r8, [rsp+2A0h+var_270]
0x18020ddaa  mov     rdx, [rsp+2A0h+var_268]
0x18020ddaf  mov     rcx, [r8]
0x18020ddb2  mov     [r8], rdx
0x18020ddb5  test    rcx, rcx
0x18020ddb8  jz      short loc_18020DDC0
0x18020ddba  call    cs:__imp_SRCacheContext_Close
0x18020ddc0  test    ebx, ebx
0x18020ddc2  js      loc_18020DFD7
0x18020ddc8  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18020ddcd  setnz   al
0x18020ddd0  test    al, al
0x18020ddd2  jz      loc_18020DF92
0x18020ddd8  xor     edx, edx; Val
0x18020ddda  mov     [rsp+2A0h+var_250], r14
0x18020dddf  mov     r8d, 200h; Size
0x18020dde5  lea     rcx, [rsp+2A0h+var_248]; void *
0x18020ddea  call    memset_0
0x18020ddef  lea     rax, [rsp+2A0h+var_248]
0x18020ddf4  mov     [rbp+1A0h+var_48], r14
0x18020ddfb  mov     rdx, rsi; unsigned __int16 *
0x18020ddfe  mov     [rbp+1A0h+var_38], rax
0x18020de05  lea     rcx, [rsp+2A0h+var_250]; this
0x18020de0a  mov     [rbp+1A0h+var_40], 100h
0x18020de15  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18020de1a  mov     ebx, eax
0x18020de1c  test    eax, eax
0x18020de1e  js      loc_18020DFB7
0x18020de24  mov     rdx, [rbp+1A0h+var_38]
0x18020de2b  lea     rax, [rsp+2A0h+var_278]
0x18020de30  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020de35  lea     r9, [rsp+2A0h+var_268]
0x18020de3a  xor     r8d, r8d
0x18020de3d  mov     [rsp+2A0h+var_270], rax
0x18020de42  mov     [rsp+2A0h+var_278], r14
0x18020de47  mov     [rsp+2A0h+var_268], r14
0x18020de4c  mov     [rsp+2A0h+var_260], 1
0x18020de51  call    cs:__imp_SRCacheContext_OpenSubContext
0x18020de57  mov     ebx, eax
0x18020de59  cmp     [rsp+2A0h+var_260], r14b
0x18020de5e  jz      short loc_18020DE7B
0x18020de60  mov     r8, [rsp+2A0h+var_270]
0x18020de65  mov     rdx, [rsp+2A0h+var_268]
0x18020de6a  mov     rcx, [r8]
0x18020de6d  mov     [r8], rdx
0x18020de70  test    rcx, rcx
0x18020de73  jz      short loc_18020DE7B
0x18020de75  call    cs:__imp_SRCacheContext_Close
0x18020de7b  test    ebx, ebx
0x18020de7d  js      loc_18020E004
0x18020de83  mov     rcx, [rsp+2A0h+var_278]
0x18020de88  test    rcx, rcx
0x18020de8b  setnz   al
0x18020de8e  test    al, al
0x18020de90  jz      short loc_18020DEA7
0x18020de92  mov     r8, rdi
0x18020de95  xor     edx, edx
0x18020de97  call    cs:__imp_SRCacheContext_EnumerateData
0x18020de9d  mov     ebx, eax
0x18020de9f  test    eax, eax
0x18020dea1  js      loc_18020E029
0x18020dea7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020deac  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18020deb3  call    cs:__imp_SRCacheContext_AddToCache
0x18020deb9  mov     ebx, eax
0x18020debb  test    eax, eax
0x18020debd  jns     short loc_18020DF36
0x18020debf  mov     rcx, [rbp+1A8h]; this
0x18020dec6  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020decd  mov     r9d, eax; char *
0x18020ded0  mov     edx, 1A6h; void *
0x18020ded5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020deda  mov     edx, 476h; void *
0x18020dedf  mov     rcx, [rbp+1A8h]; this
0x18020dee6  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020deed  mov     r9d, ebx; char *
0x18020def0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020def5  mov     rcx, [rsp+2A0h+var_278]
0x18020defa  mov     [rsp+2A0h+var_278], r14
0x18020deff  test    rcx, rcx
0x18020df02  jz      short loc_18020DF0A
0x18020df04  call    cs:__imp_SRCacheContext_Close
0x18020df0a  mov     rcx, [rsp+2A0h+var_250]
0x18020df0f  mov     [rsp+2A0h+var_250], r14
0x18020df14  test    rcx, rcx
0x18020df17  jnz     loc_18020DFF9
0x18020df1d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020df22  mov     qword ptr [rsp+2A0h+var_280], r14
0x18020df27  test    rcx, rcx
0x18020df2a  jz      short loc_18020DF32
0x18020df2c  call    cs:__imp_SRCacheContext_Close
0x18020df32  mov     eax, ebx
0x18020df34  jmp     short loc_18020DF75
0x18020df36  mov     rcx, [rsp+2A0h+var_278]
0x18020df3b  mov     [rsp+2A0h+var_278], r14
0x18020df40  test    rcx, rcx
0x18020df43  jz      short loc_18020DF4B
0x18020df45  call    cs:__imp_SRCacheContext_Close
0x18020df4b  mov     rcx, [rsp+2A0h+var_250]
0x18020df50  mov     [rsp+2A0h+var_250], r14
0x18020df55  test    rcx, rcx
0x18020df58  jnz     loc_18020E04E
0x18020df5e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020df63  mov     qword ptr [rsp+2A0h+var_280], r14
0x18020df68  test    rcx, rcx
0x18020df6b  jz      short loc_18020DF73
0x18020df6d  call    cs:__imp_SRCacheContext_Close
0x18020df73  xor     eax, eax
0x18020df75  mov     rcx, [rbp+1A0h+var_30]
0x18020df7c  xor     rcx, rsp; StackCookie
0x18020df7f  call    __security_check_cookie
0x18020df84  add     rsp, 280h
0x18020df8b  pop     r14
0x18020df8d  pop     rdi
0x18020df8e  pop     rsi
0x18020df8f  pop     rbx
0x18020df90  pop     rbp
0x18020df91  retn
0x18020df92  mov     ebx, 80670012h
0x18020df97  mov     edx, 469h; void *
0x18020df9c  mov     rcx, [rbp+1A8h]; this
0x18020dfa3  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020dfaa  mov     r9d, ebx; char *
0x18020dfad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020dfb2  jmp     loc_18020DF1D
0x18020dfb7  mov     rcx, [rbp+1A8h]; this
0x18020dfbe  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020dfc5  mov     r9d, ebx; char *
0x18020dfc8  mov     edx, 46Ch; void *
0x18020dfcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020dfd2  jmp     loc_18020DF0A
0x18020dfd7  mov     rcx, [rbp+1A8h]; this
0x18020dfde  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020dfe5  mov     r9d, ebx; char *
0x18020dfe8  mov     edx, 18Ch; void *
0x18020dfed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020dff2  mov     edx, 468h
0x18020dff7  jmp     short loc_18020DF9C
0x18020dff9  call    cs:__imp_SRCache_Free
0x18020dfff  jmp     loc_18020DF1D
0x18020e004  mov     rcx, [rbp+1A8h]; this
0x18020e00b  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e012  mov     r9d, ebx; char *
0x18020e015  mov     edx, 1B0h; void *
0x18020e01a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e01f  mov     edx, 470h
0x18020e024  jmp     loc_18020DEDF
0x18020e029  mov     rcx, [rbp+1A8h]; this
0x18020e030  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e037  mov     r9d, ebx; char *
0x18020e03a  mov     edx, 2A6h; void *
0x18020e03f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e044  mov     edx, 473h
0x18020e049  jmp     loc_18020DEDF
0x18020e04e  call    cs:__imp_SRCache_Free
0x18020e054  jmp     loc_18020DF5E
```
