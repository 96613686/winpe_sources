# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180020b3c`
- end: `0x180020e31`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18002000c`
- `0x180020a48`
- `0x1800219c0`
- `0x180021c10`

## callees

- `0x180020b3c`
- `0x1800211f0`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180020c38`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180020c38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020bd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020cb6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020d3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020bd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020cb6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020d3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020ba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020ba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020d2a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020d58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020d2a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180020d58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180020c8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180020c8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180020cd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180020cd9`

## string_xrefs

- `0x180020e0e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180020d0c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180020de7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180020cec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180020da2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180020dc7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v31);
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
    v23 = 1192;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v24[0]);
LABEL_16:
    v19 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v17);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v23 = 1193;
    goto LABEL_26;
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
    v16 = 1196;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v16 = 1197;
    goto LABEL_14;
  }
  v13 = *(_QWORD *)v24;
  *a4 = *(_QWORD *)a3 != 0;
  v14 = SRCacheContext_AddToCache(v13, L"Package\\Data");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      v24[0]);
    v16 = 1199;
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
0x180020b3c  mov     [rsp-8+arg_10], rbx
0x180020b41  push    rbp
0x180020b42  push    rsi
0x180020b43  push    rdi
0x180020b44  push    r14
0x180020b46  push    r15
0x180020b48  lea     rbp, [rsp-180h]
0x180020b50  sub     rsp, 280h
0x180020b57  mov     rax, cs:__security_cookie
0x180020b5e  xor     rax, rsp
0x180020b61  mov     [rbp+1A0h+var_28], rax
0x180020b68  mov     rcx, [rcx]
0x180020b6b  lea     rax, [rsp+2A0h+var_280]
0x180020b70  mov     r14, r9
0x180020b73  mov     qword ptr [rbp+1A0h+var_50], rax
0x180020b7a  mov     rdi, r8
0x180020b7d  mov     [rbp+1A0h+var_40], 1
0x180020b84  mov     rsi, rdx
0x180020b87  lea     r9, [rbp+1A0h+var_48]
0x180020b8e  xor     r15d, r15d
0x180020b91  lea     rdx, aPackageData; "Package\\Data"
0x180020b98  xor     r8d, r8d
0x180020b9b  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180020ba0  mov     [rbp+1A0h+var_48], r15
0x180020ba7  call    cs:__imp_SRCacheContext_Open
0x180020bad  mov     ebx, eax
0x180020baf  cmp     [rbp+1A0h+var_40], r15b
0x180020bb6  jz      short loc_180020BD7
0x180020bb8  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180020bbf  mov     rdx, [rbp+1A0h+var_48]
0x180020bc6  mov     rcx, [r8]
0x180020bc9  mov     [r8], rdx
0x180020bcc  test    rcx, rcx
0x180020bcf  jz      short loc_180020BD7
0x180020bd1  call    cs:__imp_SRCacheContext_Close
0x180020bd7  test    ebx, ebx
0x180020bd9  js      loc_180020DC0
0x180020bdf  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180020be4  setnz   al
0x180020be7  test    al, al
0x180020be9  jz      loc_180020DFB
0x180020bef  xor     edx, edx; Val
0x180020bf1  mov     [rsp+2A0h+var_270], r15
0x180020bf6  mov     r8d, 200h; Size
0x180020bfc  lea     rcx, [rsp+2A0h+var_268]; void *
0x180020c01  call    memset_0
0x180020c06  mov     r9d, 10h
0x180020c0c  mov     [rbp+1A0h+var_68], r15
0x180020c13  lea     rax, [rsp+2A0h+var_268]
0x180020c18  mov     [rbp+1A0h+var_60], 100h
0x180020c23  lea     rdx, [rbp+1A0h+var_50]
0x180020c2a  mov     [rbp+1A0h+var_58], rax
0x180020c31  mov     rcx, rsi
0x180020c34  lea     r8d, [r9+1]
0x180020c38  call    cs:__imp__o__ui64tow_s
0x180020c3e  test    eax, eax
0x180020c40  jnz     loc_180020E07
0x180020c46  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180020c4d  lea     rcx, [rsp+2A0h+var_270]; this
0x180020c52  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180020c57  mov     ebx, eax
0x180020c59  test    eax, eax
0x180020c5b  js      loc_180020E27
0x180020c61  mov     rdx, [rbp+1A0h+var_58]
0x180020c68  lea     r9, [rbp+1A0h+var_48]
0x180020c6f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180020c74  xor     r8d, r8d
0x180020c77  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180020c7e  mov     [rbp+1A0h+var_48], r15
0x180020c85  mov     [rbp+1A0h+var_40], 1
0x180020c8c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180020c92  mov     ebx, eax
0x180020c94  cmp     [rbp+1A0h+var_40], r15b
0x180020c9b  jz      short loc_180020CBC
0x180020c9d  mov     r8, qword ptr [rbp+1A0h+var_50]
0x180020ca4  mov     rdx, [rbp+1A0h+var_48]
0x180020cab  mov     rcx, [r8]
0x180020cae  mov     [r8], rdx
0x180020cb1  test    rcx, rcx
0x180020cb4  jz      short loc_180020CBC
0x180020cb6  call    cs:__imp_SRCacheContext_Close
0x180020cbc  test    ebx, ebx
0x180020cbe  js      loc_180020D9B
0x180020cc4  cmp     [rdi], r15
0x180020cc7  lea     rdx, aPackageData; "Package\\Data"
0x180020cce  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180020cd3  setnz   al
0x180020cd6  mov     [r14], al
0x180020cd9  call    cs:__imp_SRCacheContext_AddToCache
0x180020cdf  mov     ebx, eax
0x180020ce1  test    eax, eax
0x180020ce3  jns     short loc_180020D49
0x180020ce5  mov     rcx, [rbp+1A8h]; this
0x180020cec  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020cf3  mov     r9d, eax; char *
0x180020cf6  mov     edx, 1A6h; void *
0x180020cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d00  mov     edx, 4AFh; void *
0x180020d05  mov     rcx, [rbp+1A8h]; this
0x180020d0c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020d13  mov     r9d, ebx; char *
0x180020d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d1b  mov     rcx, [rsp+2A0h+var_270]
0x180020d20  mov     [rsp+2A0h+var_270], r15
0x180020d25  test    rcx, rcx
0x180020d28  jz      short loc_180020D30
0x180020d2a  call    cs:__imp_SRCache_Free
0x180020d30  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180020d35  mov     qword ptr [rsp+2A0h+var_280], r15
0x180020d3a  test    rcx, rcx
0x180020d3d  jz      short loc_180020D45
0x180020d3f  call    cs:__imp_SRCacheContext_Close
0x180020d45  mov     eax, ebx
0x180020d47  jmp     short loc_180020D75
0x180020d49  mov     rcx, [rsp+2A0h+var_270]
0x180020d4e  mov     [rsp+2A0h+var_270], r15
0x180020d53  test    rcx, rcx
0x180020d56  jz      short loc_180020D5E
0x180020d58  call    cs:__imp_SRCache_Free
0x180020d5e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180020d63  mov     qword ptr [rsp+2A0h+var_280], r15
0x180020d68  test    rcx, rcx
0x180020d6b  jz      short loc_180020D73
0x180020d6d  call    cs:__imp_SRCacheContext_Close
0x180020d73  xor     eax, eax
0x180020d75  mov     rcx, [rbp+1A0h+var_28]
0x180020d7c  xor     rcx, rsp; StackCookie
0x180020d7f  call    __security_check_cookie
0x180020d84  mov     rbx, [rsp+2A0h+arg_10]
0x180020d8c  add     rsp, 280h
0x180020d93  pop     r15
0x180020d95  pop     r14
0x180020d97  pop     rdi
0x180020d98  pop     rsi
0x180020d99  pop     rbp
0x180020d9a  retn
0x180020d9b  mov     rcx, [rbp+1A8h]; this
0x180020da2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020da9  mov     r9d, ebx; char *
0x180020dac  mov     edx, 1B0h; void *
0x180020db1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020db6  mov     edx, 4ADh
0x180020dbb  jmp     loc_180020D05
0x180020dc0  mov     rcx, [rbp+1A8h]; this
0x180020dc7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020dce  mov     r9d, ebx; char *
0x180020dd1  mov     edx, 18Ch; void *
0x180020dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ddb  mov     edx, 4A8h; void *
0x180020de0  mov     rcx, [rbp+1A8h]; this
0x180020de7  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020dee  mov     r9d, ebx; char *
0x180020df1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020df6  jmp     loc_180020D30
0x180020dfb  mov     ebx, 80670012h
0x180020e00  mov     edx, 4A9h
0x180020e05  jmp     short loc_180020DE0
0x180020e07  mov     rcx, [rbp+1A8h]; this
0x180020e0e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180020e15  mov     ebx, 8000FFFFh
0x180020e1a  mov     edx, 166h; void *
0x180020e1f  mov     r9d, ebx; char *
0x180020e22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e27  mov     edx, 4ACh
0x180020e2c  jmp     loc_180020D05
```
