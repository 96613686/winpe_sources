# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18020e1f0`
- end: `0x18020e4f9`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `777`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18020d6c0`
- `0x18020e0f8`

## callees

- `0x1800432f0`
- `0x1800a0e00`
- `0x18020e1f0`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18020e2ec`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18020e2ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020e340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18020e340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e4be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e4ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e4be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18020e4ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e36a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e3f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e41d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e36a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e3f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18020e41d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020e25b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18020e25b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18020e38d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18020e38d`

## string_xrefs

- `0x18020e4a3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18020e3c0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020e466`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18020e3a0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020e481`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18020e4d0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
    goto LABEL_26;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v23 = 1193;
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
    goto LABEL_24;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v30);
  if ( v8 < 0 )
  {
LABEL_24:
    v16 = 1196;
    goto LABEL_14;
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
      SRCache_Free(v18);
    goto LABEL_16;
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
    SRCache_Free(v21);
  v22 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v15);
  return 0;
}

```

## disassembly

```asm
0x18020e1f0  mov     [rsp-8+arg_10], rbx
0x18020e1f5  push    rbp
0x18020e1f6  push    rsi
0x18020e1f7  push    rdi
0x18020e1f8  push    r14
0x18020e1fa  push    r15
0x18020e1fc  lea     rbp, [rsp-180h]
0x18020e204  sub     rsp, 280h
0x18020e20b  mov     rax, cs:__security_cookie
0x18020e212  xor     rax, rsp
0x18020e215  mov     [rbp+1A0h+var_28], rax
0x18020e21c  mov     rcx, [rcx]
0x18020e21f  lea     rax, [rsp+2A0h+var_280]
0x18020e224  mov     r14, r9
0x18020e227  mov     qword ptr [rbp+1A0h+var_50], rax
0x18020e22e  mov     rdi, r8
0x18020e231  mov     [rbp+1A0h+var_40], 1
0x18020e238  mov     rsi, rdx
0x18020e23b  lea     r9, [rbp+1A0h+var_48]
0x18020e242  xor     r15d, r15d
0x18020e245  lea     rdx, aPackageData; "Package\\Data"
0x18020e24c  xor     r8d, r8d
0x18020e24f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18020e254  mov     [rbp+1A0h+var_48], r15
0x18020e25b  call    cs:__imp_SRCacheContext_Open
0x18020e261  mov     ebx, eax
0x18020e263  cmp     [rbp+1A0h+var_40], r15b
0x18020e26a  jz      short loc_18020E28B
0x18020e26c  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18020e273  mov     rdx, [rbp+1A0h+var_48]
0x18020e27a  mov     rcx, [r8]
0x18020e27d  mov     [r8], rdx
0x18020e280  test    rcx, rcx
0x18020e283  jz      short loc_18020E28B
0x18020e285  call    cs:__imp_SRCacheContext_Close
0x18020e28b  test    ebx, ebx
0x18020e28d  js      loc_18020E47A
0x18020e293  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18020e298  setnz   al
0x18020e29b  test    al, al
0x18020e29d  jz      loc_18020E455
0x18020e2a3  xor     edx, edx; Val
0x18020e2a5  mov     [rsp+2A0h+var_270], r15
0x18020e2aa  mov     r8d, 200h; Size
0x18020e2b0  lea     rcx, [rsp+2A0h+var_268]; void *
0x18020e2b5  call    memset_0
0x18020e2ba  mov     r9d, 10h
0x18020e2c0  mov     [rbp+1A0h+var_68], r15
0x18020e2c7  lea     rax, [rsp+2A0h+var_268]
0x18020e2cc  mov     [rbp+1A0h+var_60], 100h
0x18020e2d7  lea     rdx, [rbp+1A0h+var_50]
0x18020e2de  mov     [rbp+1A0h+var_58], rax
0x18020e2e5  mov     rcx, rsi
0x18020e2e8  lea     r8d, [r9+1]
0x18020e2ec  call    cs:__imp__o__ui64tow_s
0x18020e2f2  test    eax, eax
0x18020e2f4  jnz     loc_18020E49C
0x18020e2fa  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18020e301  lea     rcx, [rsp+2A0h+var_270]; this
0x18020e306  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18020e30b  mov     ebx, eax
0x18020e30d  test    eax, eax
0x18020e30f  js      loc_18020E44B
0x18020e315  mov     rdx, [rbp+1A0h+var_58]
0x18020e31c  lea     r9, [rbp+1A0h+var_48]
0x18020e323  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020e328  xor     r8d, r8d
0x18020e32b  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18020e332  mov     [rbp+1A0h+var_48], r15
0x18020e339  mov     [rbp+1A0h+var_40], 1
0x18020e340  call    cs:__imp_SRCacheContext_OpenSubContext
0x18020e346  mov     ebx, eax
0x18020e348  cmp     [rbp+1A0h+var_40], r15b
0x18020e34f  jz      short loc_18020E370
0x18020e351  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18020e358  mov     rdx, [rbp+1A0h+var_48]
0x18020e35f  mov     rcx, [r8]
0x18020e362  mov     [r8], rdx
0x18020e365  test    rcx, rcx
0x18020e368  jz      short loc_18020E370
0x18020e36a  call    cs:__imp_SRCacheContext_Close
0x18020e370  test    ebx, ebx
0x18020e372  js      loc_18020E4C9
0x18020e378  cmp     [rdi], r15
0x18020e37b  lea     rdx, aPackageData; "Package\\Data"
0x18020e382  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020e387  setnz   al
0x18020e38a  mov     [r14], al
0x18020e38d  call    cs:__imp_SRCacheContext_AddToCache
0x18020e393  mov     ebx, eax
0x18020e395  test    eax, eax
0x18020e397  jns     short loc_18020E3FB
0x18020e399  mov     rcx, [rbp+1A8h]; this
0x18020e3a0  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e3a7  mov     r9d, eax; char *
0x18020e3aa  mov     edx, 1A6h; void *
0x18020e3af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e3b4  mov     edx, 4AFh; void *
0x18020e3b9  mov     rcx, [rbp+1A8h]; this
0x18020e3c0  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e3c7  mov     r9d, ebx; char *
0x18020e3ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e3cf  mov     rcx, [rsp+2A0h+var_270]
0x18020e3d4  mov     [rsp+2A0h+var_270], r15
0x18020e3d9  test    rcx, rcx
0x18020e3dc  jnz     loc_18020E4BE
0x18020e3e2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020e3e7  mov     qword ptr [rsp+2A0h+var_280], r15
0x18020e3ec  test    rcx, rcx
0x18020e3ef  jz      short loc_18020E3F7
0x18020e3f1  call    cs:__imp_SRCacheContext_Close
0x18020e3f7  mov     eax, ebx
0x18020e3f9  jmp     short loc_18020E425
0x18020e3fb  mov     rcx, [rsp+2A0h+var_270]
0x18020e400  mov     [rsp+2A0h+var_270], r15
0x18020e405  test    rcx, rcx
0x18020e408  jnz     loc_18020E4EE
0x18020e40e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18020e413  mov     qword ptr [rsp+2A0h+var_280], r15
0x18020e418  test    rcx, rcx
0x18020e41b  jz      short loc_18020E423
0x18020e41d  call    cs:__imp_SRCacheContext_Close
0x18020e423  xor     eax, eax
0x18020e425  mov     rcx, [rbp+1A0h+var_28]
0x18020e42c  xor     rcx, rsp; StackCookie
0x18020e42f  call    __security_check_cookie
0x18020e434  mov     rbx, [rsp+2A0h+arg_10]
0x18020e43c  add     rsp, 280h
0x18020e443  pop     r15
0x18020e445  pop     r14
0x18020e447  pop     rdi
0x18020e448  pop     rsi
0x18020e449  pop     rbp
0x18020e44a  retn
0x18020e44b  mov     edx, 4ACh
0x18020e450  jmp     loc_18020E3B9
0x18020e455  mov     ebx, 80670012h
0x18020e45a  mov     edx, 4A9h; void *
0x18020e45f  mov     rcx, [rbp+1A8h]; this
0x18020e466  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e46d  mov     r9d, ebx; char *
0x18020e470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e475  jmp     loc_18020E3E2
0x18020e47a  mov     rcx, [rbp+1A8h]; this
0x18020e481  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e488  mov     r9d, ebx; char *
0x18020e48b  mov     edx, 18Ch; void *
0x18020e490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e495  mov     edx, 4A8h
0x18020e49a  jmp     short loc_18020E45F
0x18020e49c  mov     rcx, [rbp+1A8h]; this
0x18020e4a3  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e4aa  mov     ebx, 8000FFFFh
0x18020e4af  mov     edx, 166h; void *
0x18020e4b4  mov     r9d, ebx; char *
0x18020e4b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e4bc  jmp     short loc_18020E44B
0x18020e4be  call    cs:__imp_SRCache_Free
0x18020e4c4  jmp     loc_18020E3E2
0x18020e4c9  mov     rcx, [rbp+1A8h]; this
0x18020e4d0  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18020e4d7  mov     r9d, ebx; char *
0x18020e4da  mov     edx, 1B0h; void *
0x18020e4df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020e4e4  mov     edx, 4ADh
0x18020e4e9  jmp     loc_18020E3B9
0x18020e4ee  call    cs:__imp_SRCache_Free
0x18020e4f4  jmp     loc_18020E40E
```
