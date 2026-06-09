# StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x180020620`
- end: `0x180020a42`
- name: `?GetByPackageAndPackageRelativeApplicationId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `1058`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180094190`

## callees

- `0x180020620`
- `0x1800211f0`
- `0x1800217e4`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180020725`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180020725`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800206be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020800`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002087e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800208f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020911`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002093b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800206be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020800`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002087e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800208f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020911`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002093b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020694`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020694`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002088b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002088b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800208e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800208e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800207d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800207d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180020829`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180020829`

## string_xrefs

- `0x1800209fa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180020a24`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180020860`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800208c5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180020969`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800209d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180020840`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002089e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002098e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800209b3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+238h] [rbp+138h]
  __int64 v34; // [rsp+240h] [rbp+140h]
  _BYTE *v35; // [rsp+248h] [rbp+148h]
  unsigned __int16 v36[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v37; // [rsp+258h] [rbp+158h] BYREF
  char v38; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v29[0]);
    return (unsigned int)v8;
  }
  v7 = *(_QWORD *)a1;
  *(_QWORD *)v36 = v29;
  *(_QWORD *)v29 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_Open(v7, L"Application\\Index\\PackageAndPackageRelativeApplicationId", 0, &v37);
  if ( v38 )
  {
    v9 = v37;
    v10 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
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
      v29[0]);
    v28 = 363;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v29[0]);
LABEL_26:
    v23 = *(_QWORD *)v29;
    *(_QWORD *)v29 = 0;
    if ( v23 )
      SRCacheContext_Close(v23, v18);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v29 )
  {
    v8 = -2140733422;
    v28 = 364;
    goto LABEL_39;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v34 = 256;
  v35 = v32;
  if ( (unsigned int)_o__ui64tow_s(a2, v36, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v29[0]);
    goto LABEL_42;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v36);
  if ( v8 < 0 )
  {
LABEL_42:
    v21 = 367;
    goto LABEL_23;
  }
  v12 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v31, v33 + 2, v11);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v12,
      v29[0]);
    v21 = 368;
    goto LABEL_23;
  }
  *(_DWORD *)&v35[2 * v33++] = 94;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a3);
  if ( v8 < 0 )
  {
    v21 = 369;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v29[0]);
LABEL_24:
    v22 = v31;
    v31 = 0;
    if ( v22 )
      SRCache_Free();
    goto LABEL_26;
  }
  *(_QWORD *)v36 = &v30;
  v30 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v29, v35, 0, &v37);
  if ( v38 )
  {
    v13 = v37;
    v14 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v29[0]);
    v17 = 373;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v29[0]);
    v19 = v30;
    v30 = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v18);
    goto LABEL_24;
  }
  if ( v30 )
  {
    v20 = SRCacheContext_EnumerateData(v30, 0, a4);
    v8 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v20,
        v29[0]);
      v17 = 376;
      goto LABEL_18;
    }
  }
  v15 = SRCacheContext_AddToCache(*(_QWORD *)v29, L"Application\\Index\\PackageAndPackageRelativeApplicationId");
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      v29[0]);
    v17 = 379;
    goto LABEL_18;
  }
  v25 = v30;
  v30 = 0;
  if ( v25 )
    SRCacheContext_Close(v25, v16);
  v26 = v31;
  v31 = 0;
  if ( v26 )
    SRCache_Free();
  v27 = *(_QWORD *)v29;
  *(_QWORD *)v29 = 0;
  if ( v27 )
    SRCacheContext_Close(v27, v16);
  return 0;
}

```

## disassembly

```asm
0x180020620  push    rbp
0x180020622  push    rbx
0x180020623  push    rsi
0x180020624  push    rdi
0x180020625  push    r14
0x180020627  push    r15
0x180020629  lea     rbp, [rsp-188h]
0x180020631  sub     rsp, 288h
0x180020638  mov     rax, cs:__security_cookie
0x18002063f  xor     rax, rsp
0x180020642  mov     [rbp+1B0h+var_38], rax
0x180020649  xor     r15d, r15d
0x18002064c  mov     rsi, r9
0x18002064f  mov     [r9], r15
0x180020652  mov     r14, r8
0x180020655  mov     rdi, rdx
0x180020658  test    rdx, rdx
0x18002065b  jz      loc_180020962
0x180020661  mov     rcx, [rcx]
0x180020664  lea     rax, [rsp+2B0h+var_290]
0x180020669  lea     r9, [rbp+1B0h+var_58]
0x180020670  mov     qword ptr [rbp+1B0h+var_60], rax
0x180020677  xor     r8d, r8d
0x18002067a  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18002067f  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x180020686  mov     [rbp+1B0h+var_58], r15
0x18002068d  mov     [rbp+1B0h+var_50], 1
0x180020694  call    cs:__imp_SRCacheContext_Open
0x18002069a  mov     ebx, eax
0x18002069c  cmp     [rbp+1B0h+var_50], r15b
0x1800206a3  jz      short loc_1800206C4
0x1800206a5  mov     r8, qword ptr [rbp+1B0h+var_60]
0x1800206ac  mov     rdx, [rbp+1B0h+var_58]
0x1800206b3  mov     rcx, [r8]
0x1800206b6  mov     [r8], rdx
0x1800206b9  test    rcx, rcx
0x1800206bc  jz      short loc_1800206C4
0x1800206be  call    cs:__imp_SRCacheContext_Close
0x1800206c4  test    ebx, ebx
0x1800206c6  js      loc_1800209AC
0x1800206cc  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800206d1  setnz   al
0x1800206d4  test    al, al
0x1800206d6  jz      loc_1800209E7
0x1800206dc  xor     edx, edx; Val
0x1800206de  mov     [rsp+2B0h+var_280], r15
0x1800206e3  mov     r8d, 200h; Size
0x1800206e9  lea     rcx, [rsp+2B0h+var_278]; void *
0x1800206ee  call    memset_0
0x1800206f3  mov     r9d, 10h
0x1800206f9  mov     [rbp+1B0h+var_78], r15
0x180020700  lea     rax, [rsp+2B0h+var_278]
0x180020705  mov     [rbp+1B0h+var_70], 100h
0x180020710  lea     rdx, [rbp+1B0h+var_60]
0x180020717  mov     [rbp+1B0h+var_68], rax
0x18002071e  mov     rcx, rdi
0x180020721  lea     r8d, [r9+1]
0x180020725  call    cs:__imp__o__ui64tow_s
0x18002072b  test    eax, eax
0x18002072d  jnz     loc_1800209F3
0x180020733  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x18002073a  lea     rcx, [rsp+2B0h+var_280]; this
0x18002073f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180020744  mov     ebx, eax
0x180020746  test    eax, eax
0x180020748  js      loc_180020A13
0x18002074e  mov     rdx, [rbp+1B0h+var_78]
0x180020755  lea     rcx, [rsp+2B0h+var_280]; this
0x18002075a  add     rdx, 2; unsigned __int64
0x18002075e  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x180020763  mov     ebx, eax
0x180020765  test    eax, eax
0x180020767  js      loc_180020A1D
0x18002076d  mov     r8, [rbp+1B0h+var_78]
0x180020774  mov     rdx, r14; unsigned __int16 *
0x180020777  mov     rcx, [rbp+1B0h+var_68]
0x18002077e  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x180020786  lea     rcx, [rsp+2B0h+var_280]; this
0x18002078b  inc     [rbp+1B0h+var_78]
0x180020792  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180020797  mov     ebx, eax
0x180020799  test    eax, eax
0x18002079b  js      loc_1800208B9
0x1800207a1  mov     rdx, [rbp+1B0h+var_68]
0x1800207a8  lea     rax, [rsp+2B0h+var_288]
0x1800207ad  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800207b2  lea     r9, [rbp+1B0h+var_58]
0x1800207b9  xor     r8d, r8d
0x1800207bc  mov     qword ptr [rbp+1B0h+var_60], rax
0x1800207c3  mov     [rsp+2B0h+var_288], r15
0x1800207c8  mov     [rbp+1B0h+var_58], r15
0x1800207cf  mov     [rbp+1B0h+var_50], 1
0x1800207d6  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800207dc  mov     ebx, eax
0x1800207de  cmp     [rbp+1B0h+var_50], r15b
0x1800207e5  jz      short loc_180020806
0x1800207e7  mov     r8, qword ptr [rbp+1B0h+var_60]
0x1800207ee  mov     rdx, [rbp+1B0h+var_58]
0x1800207f5  mov     rcx, [r8]
0x1800207f8  mov     [r8], rdx
0x1800207fb  test    rcx, rcx
0x1800207fe  jz      short loc_180020806
0x180020800  call    cs:__imp_SRCacheContext_Close
0x180020806  test    ebx, ebx
0x180020808  js      loc_180020987
0x18002080e  mov     rcx, [rsp+2B0h+var_288]
0x180020813  test    rcx, rcx
0x180020816  setnz   al
0x180020819  test    al, al
0x18002081b  jnz     short loc_180020886
0x18002081d  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180020822  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x180020829  call    cs:__imp_SRCacheContext_AddToCache
0x18002082f  mov     ebx, eax
0x180020831  test    eax, eax
0x180020833  jns     loc_180020902
0x180020839  mov     rcx, [rbp+1B8h]; this
0x180020840  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020847  mov     r9d, eax; char *
0x18002084a  mov     edx, 1A6h; void *
0x18002084f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020854  mov     edx, 17Bh; void *
0x180020859  mov     rcx, [rbp+1B8h]; this
0x180020860  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020867  mov     r9d, ebx; char *
0x18002086a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002086f  mov     rcx, [rsp+2B0h+var_288]
0x180020874  mov     [rsp+2B0h+var_288], r15
0x180020879  test    rcx, rcx
0x18002087c  jz      short loc_1800208D4
0x18002087e  call    cs:__imp_SRCacheContext_Close
0x180020884  jmp     short loc_1800208D4
0x180020886  mov     r8, rsi
0x180020889  xor     edx, edx
0x18002088b  call    cs:__imp_SRCacheContext_EnumerateData
0x180020891  mov     ebx, eax
0x180020893  test    eax, eax
0x180020895  jns     short loc_18002081D
0x180020897  mov     rcx, [rbp+1B8h]; this
0x18002089e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800208a5  mov     r9d, eax; char *
0x1800208a8  mov     edx, 2A6h; void *
0x1800208ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208b2  mov     edx, 178h
0x1800208b7  jmp     short loc_180020859
0x1800208b9  mov     edx, 171h; void *
0x1800208be  mov     rcx, [rbp+1B8h]; this
0x1800208c5  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800208cc  mov     r9d, ebx; char *
0x1800208cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208d4  mov     rcx, [rsp+2B0h+var_280]
0x1800208d9  mov     [rsp+2B0h+var_280], r15
0x1800208de  test    rcx, rcx
0x1800208e1  jz      short loc_1800208E9
0x1800208e3  call    cs:__imp_SRCache_Free
0x1800208e9  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800208ee  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800208f3  test    rcx, rcx
0x1800208f6  jz      short loc_1800208FE
0x1800208f8  call    cs:__imp_SRCacheContext_Close
0x1800208fe  mov     eax, ebx
0x180020900  jmp     short loc_180020943
0x180020902  mov     rcx, [rsp+2B0h+var_288]
0x180020907  mov     [rsp+2B0h+var_288], r15
0x18002090c  test    rcx, rcx
0x18002090f  jz      short loc_180020917
0x180020911  call    cs:__imp_SRCacheContext_Close
0x180020917  mov     rcx, [rsp+2B0h+var_280]
0x18002091c  mov     [rsp+2B0h+var_280], r15
0x180020921  test    rcx, rcx
0x180020924  jz      short loc_18002092C
0x180020926  call    cs:__imp_SRCache_Free
0x18002092c  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180020931  mov     qword ptr [rsp+2B0h+var_290], r15
0x180020936  test    rcx, rcx
0x180020939  jz      short loc_180020941
0x18002093b  call    cs:__imp_SRCacheContext_Close
0x180020941  xor     eax, eax
0x180020943  mov     rcx, [rbp+1B0h+var_38]
0x18002094a  xor     rcx, rsp; StackCookie
0x18002094d  call    __security_check_cookie
0x180020952  add     rsp, 288h
0x180020959  pop     r15
0x18002095b  pop     r14
0x18002095d  pop     rdi
0x18002095e  pop     rsi
0x18002095f  pop     rbx
0x180020960  pop     rbp
0x180020961  retn
0x180020962  mov     rcx, [rbp+1B8h]; this
0x180020969  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020970  mov     ebx, 80070057h
0x180020975  mov     edx, 167h; void *
0x18002097a  mov     r9d, ebx; char *
0x18002097d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020982  jmp     loc_1800208FE
0x180020987  mov     rcx, [rbp+1B8h]; this
0x18002098e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020995  mov     r9d, ebx; char *
0x180020998  mov     edx, 1B0h; void *
0x18002099d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209a2  mov     edx, 175h
0x1800209a7  jmp     loc_180020859
0x1800209ac  mov     rcx, [rbp+1B8h]; this
0x1800209b3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800209ba  mov     r9d, ebx; char *
0x1800209bd  mov     edx, 18Ch; void *
0x1800209c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209c7  mov     edx, 16Bh; void *
0x1800209cc  mov     rcx, [rbp+1B8h]; this
0x1800209d3  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800209da  mov     r9d, ebx; char *
0x1800209dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209e2  jmp     loc_1800208E9
0x1800209e7  mov     ebx, 80670012h
0x1800209ec  mov     edx, 16Ch
0x1800209f1  jmp     short loc_1800209CC
0x1800209f3  mov     rcx, [rbp+1B8h]; this
0x1800209fa  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020a01  mov     ebx, 8000FFFFh
0x180020a06  mov     edx, 166h; void *
0x180020a0b  mov     r9d, ebx; char *
0x180020a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a13  mov     edx, 16Fh
0x180020a18  jmp     loc_1800208BE
0x180020a1d  mov     rcx, [rbp+1B8h]; this
0x180020a24  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020a2b  mov     r9d, ebx; char *
0x180020a2e  mov     edx, 16Dh; void *
0x180020a33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a38  mov     edx, 170h
0x180020a3d  jmp     loc_1800208BE
```
