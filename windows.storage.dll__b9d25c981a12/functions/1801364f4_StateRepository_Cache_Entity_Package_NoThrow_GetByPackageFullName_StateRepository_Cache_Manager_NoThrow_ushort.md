# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x1801364f4`
- end: `0x18013682e`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `826`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18013645c`
- `0x180136898`

## callees

- `0x180038f50`
- `0x180134e90`
- `0x1801364f4`
- `0x180136834`
- `0x1803b1f60`
- `0x1803b2ac0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180136619`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180136619`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013680c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013681d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013680c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013681d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18013657c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180136701`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18013672f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18013657c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180136701`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18013672f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180136552`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180136552`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180136659`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180136659`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18013667b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18013667b`

## string_xrefs

- `0x1801366b4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18013676c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180136787`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180136694`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801367a7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801367c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1801367ee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  int *v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  char v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v22 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v19 = 0;
  v20 = (int *)&v19;
  v21 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v21);
  if ( v22 )
  {
    v7 = *(_QWORD *)v20;
    *(_QWORD *)v20 = v21;
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
      v18[0]);
    v17 = 1128;
    goto LABEL_26;
  }
  if ( !v19 )
  {
    v6 = -2140733422;
    v17 = 1129;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v18[0]);
LABEL_17:
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v19, 0);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
LABEL_15:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_17;
  }
  v20 = v18;
  *(_QWORD *)v18 = 0;
  v21 = 0;
  v22 = 1;
  v6 = SRCacheContext_OpenSubContext(v19, v27, 0, &v21);
  if ( v22 )
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v20, v21);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v18[0]);
    v11 = 1136;
    goto LABEL_14;
  }
  if ( *(_QWORD *)v18 )
  {
    v9 = SRCacheContext_EnumerateData(*(_QWORD *)v18, 0, a3);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v9,
        v18[0]);
      v11 = 1139;
      goto LABEL_14;
    }
  }
  v10 = SRCacheContext_AddToCache(v19, L"Package\\Index\\PackageFullName");
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v18[0]);
    v11 = 1142;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v18[0]);
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v18, 0);
    goto LABEL_15;
  }
  v14 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x1801364f4  push    rbp
0x1801364f6  push    rbx
0x1801364f7  push    rsi
0x1801364f8  push    rdi
0x1801364f9  push    r14
0x1801364fb  lea     rbp, [rsp-180h]
0x180136503  sub     rsp, 280h
0x18013650a  mov     rax, cs:__security_cookie
0x180136511  xor     rax, rsp
0x180136514  mov     [rbp+1A0h+var_30], rax
0x18013651b  xor     r14d, r14d
0x18013651e  mov     [rsp+2A0h+var_260], 1
0x180136523  mov     [r8], r14
0x180136526  lea     rax, [rsp+2A0h+var_278]
0x18013652b  mov     rcx, [rcx]
0x18013652e  lea     r9, [rsp+2A0h+var_268]
0x180136533  mov     rdi, r8
0x180136536  mov     [rsp+2A0h+var_278], r14
0x18013653b  mov     rsi, rdx
0x18013653e  mov     [rsp+2A0h+var_270], rax
0x180136543  xor     r8d, r8d
0x180136546  mov     [rsp+2A0h+var_268], r14
0x18013654b  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x180136552  call    cs:__imp_SRCacheContext_Open
0x180136559  nop     dword ptr [rax+rax+00h]
0x18013655e  mov     ebx, eax
0x180136560  cmp     [rsp+2A0h+var_260], r14b
0x180136565  jz      short loc_180136588
0x180136567  mov     r8, [rsp+2A0h+var_270]
0x18013656c  mov     rdx, [rsp+2A0h+var_268]
0x180136571  mov     rcx, [r8]
0x180136574  mov     [r8], rdx
0x180136577  test    rcx, rcx
0x18013657a  jz      short loc_180136588
0x18013657c  call    cs:__imp_SRCacheContext_Close
0x180136583  nop     dword ptr [rax+rax+00h]
0x180136588  test    ebx, ebx
0x18013658a  js      loc_1801367A0
0x180136590  cmp     [rsp+2A0h+var_278], r14
0x180136595  setnz   al
0x180136598  test    al, al
0x18013659a  jz      loc_18013675B
0x1801365a0  xor     edx, edx; Val
0x1801365a2  mov     [rsp+2A0h+var_250], r14
0x1801365a7  mov     r8d, 200h; Size
0x1801365ad  lea     rcx, [rsp+2A0h+var_248]; void *
0x1801365b2  call    memset_0
0x1801365b7  lea     rax, [rsp+2A0h+var_248]
0x1801365bc  mov     [rbp+1A0h+var_48], r14
0x1801365c3  mov     rdx, rsi; unsigned __int16 *
0x1801365c6  mov     [rbp+1A0h+var_38], rax
0x1801365cd  lea     rcx, [rsp+2A0h+var_250]; this
0x1801365d2  mov     [rbp+1A0h+var_40], 100h
0x1801365dd  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1801365e2  mov     ebx, eax
0x1801365e4  test    eax, eax
0x1801365e6  js      loc_180136780
0x1801365ec  mov     rdx, [rbp+1A0h+var_38]
0x1801365f3  lea     rax, [rsp+2A0h+var_280]
0x1801365f8  mov     rcx, [rsp+2A0h+var_278]
0x1801365fd  lea     r9, [rsp+2A0h+var_268]
0x180136602  xor     r8d, r8d
0x180136605  mov     [rsp+2A0h+var_270], rax
0x18013660a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18013660f  mov     [rsp+2A0h+var_268], r14
0x180136614  mov     [rsp+2A0h+var_260], 1
0x180136619  call    cs:__imp_SRCacheContext_OpenSubContext
0x180136620  nop     dword ptr [rax+rax+00h]
0x180136625  mov     ebx, eax
0x180136627  cmp     [rsp+2A0h+var_260], r14b
0x18013662c  jz      short loc_18013663D
0x18013662e  mov     rdx, [rsp+2A0h+var_268]
0x180136633  mov     rcx, [rsp+2A0h+var_270]
0x180136638  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18013663d  test    ebx, ebx
0x18013663f  js      loc_1801367C2
0x180136645  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18013664a  test    rcx, rcx
0x18013664d  setnz   al
0x180136650  test    al, al
0x180136652  jz      short loc_18013666F
0x180136654  mov     r8, rdi
0x180136657  xor     edx, edx
0x180136659  call    cs:__imp_SRCacheContext_EnumerateData
0x180136660  nop     dword ptr [rax+rax+00h]
0x180136665  mov     ebx, eax
0x180136667  test    eax, eax
0x180136669  js      loc_1801367E7
0x18013666f  mov     rcx, [rsp+2A0h+var_278]
0x180136674  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18013667b  call    cs:__imp_SRCacheContext_AddToCache
0x180136682  nop     dword ptr [rax+rax+00h]
0x180136687  mov     ebx, eax
0x180136689  test    eax, eax
0x18013668b  jns     short loc_1801366F2
0x18013668d  mov     rcx, [rbp+1A8h]; this
0x180136694  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18013669b  mov     r9d, eax; char *
0x18013669e  mov     edx, 1A6h; void *
0x1801366a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801366a8  mov     edx, 476h; void *
0x1801366ad  mov     rcx, [rbp+1A8h]; this
0x1801366b4  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801366bb  mov     r9d, ebx; char *
0x1801366be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801366c3  xor     edx, edx
0x1801366c5  lea     rcx, [rsp+2A0h+var_280]
0x1801366ca  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801366cf  mov     rcx, [rsp+2A0h+var_250]
0x1801366d4  mov     [rsp+2A0h+var_250], r14
0x1801366d9  test    rcx, rcx
0x1801366dc  jnz     loc_18013680C
0x1801366e2  xor     edx, edx
0x1801366e4  lea     rcx, [rsp+2A0h+var_278]
0x1801366e9  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x1801366ee  mov     eax, ebx
0x1801366f0  jmp     short loc_18013673D
0x1801366f2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1801366f7  mov     qword ptr [rsp+2A0h+var_280], r14
0x1801366fc  test    rcx, rcx
0x1801366ff  jz      short loc_18013670D
0x180136701  call    cs:__imp_SRCacheContext_Close
0x180136708  nop     dword ptr [rax+rax+00h]
0x18013670d  mov     rcx, [rsp+2A0h+var_250]
0x180136712  mov     [rsp+2A0h+var_250], r14
0x180136717  test    rcx, rcx
0x18013671a  jnz     loc_18013681D
0x180136720  mov     rcx, [rsp+2A0h+var_278]
0x180136725  mov     [rsp+2A0h+var_278], r14
0x18013672a  test    rcx, rcx
0x18013672d  jz      short loc_18013673B
0x18013672f  call    cs:__imp_SRCacheContext_Close
0x180136736  nop     dword ptr [rax+rax+00h]
0x18013673b  xor     eax, eax
0x18013673d  mov     rcx, [rbp+1A0h+var_30]
0x180136744  xor     rcx, rsp; StackCookie
0x180136747  call    __security_check_cookie
0x18013674c  add     rsp, 280h
0x180136753  pop     r14
0x180136755  pop     rdi
0x180136756  pop     rsi
0x180136757  pop     rbx
0x180136758  pop     rbp
0x180136759  retn
0x18013675b  mov     ebx, 80670012h
0x180136760  mov     edx, 469h; void *
0x180136765  mov     rcx, [rbp+1A8h]; this
0x18013676c  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x180136773  mov     r9d, ebx; char *
0x180136776  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013677b  jmp     loc_1801366E2
0x180136780  mov     rcx, [rbp+1A8h]; this
0x180136787  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18013678e  mov     r9d, eax; char *
0x180136791  mov     edx, 46Ch; void *
0x180136796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013679b  jmp     loc_1801366CF
0x1801367a0  mov     rcx, [rbp+1A8h]; this
0x1801367a7  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801367ae  mov     r9d, ebx; char *
0x1801367b1  mov     edx, 18Ch; void *
0x1801367b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801367bb  mov     edx, 468h
0x1801367c0  jmp     short loc_180136765
0x1801367c2  mov     rcx, [rbp+1A8h]; this
0x1801367c9  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801367d0  mov     r9d, ebx; char *
0x1801367d3  mov     edx, 1B0h; void *
0x1801367d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801367dd  mov     edx, 470h
0x1801367e2  jmp     loc_1801366AD
0x1801367e7  mov     rcx, [rbp+1A8h]; this
0x1801367ee  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801367f5  mov     r9d, ebx; char *
0x1801367f8  mov     edx, 2A6h; void *
0x1801367fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136802  mov     edx, 473h
0x180136807  jmp     loc_1801366AD
0x18013680c  call    cs:__imp_SRCache_Free
0x180136813  nop     dword ptr [rax+rax+00h]
0x180136818  jmp     loc_1801366E2
0x18013681d  call    cs:__imp_SRCache_Free
0x180136824  nop     dword ptr [rax+rax+00h]
0x180136829  jmp     loc_180136720
```
