# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000edf0`
- end: `0x18000f0ab`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `699`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18000caf8`
- `0x18000dae4`
- `0x18000ecf8`
- `0x180087818`

## callees

- `0x18000eccc`
- `0x18000edf0`
- `0x18000f4d0`
- `0x18000f748`
- `0x1800210f8`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000ef01`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000ef01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ee8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f00e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ee8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000f00e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000ee5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000ee5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000efc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000efef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000efc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000efef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ef5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ef5b`

## string_xrefs

- `0x18000f088`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000efa1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000f061`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000ef74`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000f041`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // esi
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h]
  _QWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+248h] [rbp+148h]
  __int64 v24; // [rsp+250h] [rbp+150h]
  _BYTE *v25; // [rsp+258h] [rbp+158h]
  unsigned __int16 v26[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v27; // [rsp+268h] [rbp+168h] BYREF
  char v28; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  *(_QWORD *)v26 = v20;
  v20[0] = 0;
  v27 = 0;
  v28 = 1;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v27);
  if ( v28 )
  {
    v9 = **(_QWORD **)v26;
    **(_QWORD **)v26 = v27;
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
      v19);
    v18 = 1192;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v19);
LABEL_15:
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v20, 0);
    return (unsigned int)v8;
  }
  if ( !v20[0] )
  {
    v8 = -2140733422;
    v18 = 1193;
    goto LABEL_22;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 256;
  v25 = v22;
  if ( (unsigned int)_o__ui64tow_s(a2, v26, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v19);
    goto LABEL_25;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, v26);
  if ( v8 < 0 )
  {
LABEL_25:
    v12 = 1196;
    goto LABEL_11;
  }
  v19 = v5;
  v10 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, v20, v25);
  v8 = v10;
  if ( v10 < 0 )
  {
    v13 = (unsigned int)v10;
    v12 = 1197;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v13,
      v19);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_15;
  }
  v11 = SRCacheContext_AddToCache(v20[0], L"Package\\Data");
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v5);
    v12 = 1199;
LABEL_11:
    v13 = (unsigned int)v8;
    goto LABEL_13;
  }
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = v20[0];
  v20[0] = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x18000edf0  push    rbp
0x18000edf2  push    rbx
0x18000edf3  push    rsi
0x18000edf4  push    rdi
0x18000edf5  push    r14
0x18000edf7  lea     rbp, [rsp-190h]
0x18000edff  sub     rsp, 290h
0x18000ee06  mov     rax, cs:__security_cookie
0x18000ee0d  xor     rax, rsp
0x18000ee10  mov     [rbp+1B0h+var_28], rax
0x18000ee17  mov     rcx, [rcx]
0x18000ee1a  lea     rax, [rsp+2B0h+var_280]
0x18000ee1f  mov     rsi, r9
0x18000ee22  mov     qword ptr [rbp+1B0h+var_50], rax
0x18000ee29  mov     rdi, r8
0x18000ee2c  mov     [rsp+2B0h+var_280], 0
0x18000ee35  mov     r14, rdx
0x18000ee38  mov     [rbp+1B0h+var_48], 0
0x18000ee43  lea     r9, [rbp+1B0h+var_48]
0x18000ee4a  mov     [rbp+1B0h+var_40], 1
0x18000ee51  xor     r8d, r8d
0x18000ee54  lea     rdx, aPackageData; "Package\\Data"
0x18000ee5b  call    cs:__imp_SRCacheContext_Open
0x18000ee62  nop     dword ptr [rax+rax+00h]
0x18000ee67  cmp     [rbp+1B0h+var_40], 0
0x18000ee6e  mov     ebx, eax
0x18000ee70  jz      short loc_18000EE97
0x18000ee72  mov     r8, qword ptr [rbp+1B0h+var_50]
0x18000ee79  mov     rdx, [rbp+1B0h+var_48]
0x18000ee80  mov     rcx, [r8]
0x18000ee83  mov     [r8], rdx
0x18000ee86  test    rcx, rcx
0x18000ee89  jz      short loc_18000EE97
0x18000ee8b  call    cs:__imp_SRCacheContext_Close
0x18000ee92  nop     dword ptr [rax+rax+00h]
0x18000ee97  test    ebx, ebx
0x18000ee99  js      loc_18000F03A
0x18000ee9f  cmp     [rsp+2B0h+var_280], 0
0x18000eea5  setnz   al
0x18000eea8  test    al, al
0x18000eeaa  jz      loc_18000F075
0x18000eeb0  xor     edx, edx; Val
0x18000eeb2  mov     [rsp+2B0h+var_270], 0
0x18000eebb  mov     r8d, 200h; Size
0x18000eec1  lea     rcx, [rsp+2B0h+var_268]; void *
0x18000eec6  call    memset_0
0x18000eecb  mov     r9d, 10h
0x18000eed1  mov     [rbp+1B0h+var_68], 0
0x18000eedc  lea     rax, [rsp+2B0h+var_268]
0x18000eee1  mov     [rbp+1B0h+var_60], 100h
0x18000eeec  lea     rdx, [rbp+1B0h+var_50]
0x18000eef3  mov     [rbp+1B0h+var_58], rax
0x18000eefa  mov     rcx, r14
0x18000eefd  lea     r8d, [r9+1]
0x18000ef01  call    cs:__imp__o__ui64tow_s
0x18000ef08  nop     dword ptr [rax+rax+00h]
0x18000ef0d  test    eax, eax
0x18000ef0f  jnz     loc_18000F081
0x18000ef15  lea     rdx, [rbp+1B0h+var_50]; unsigned __int16 *
0x18000ef1c  lea     rcx, [rsp+2B0h+var_270]; this
0x18000ef21  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000ef26  mov     ebx, eax
0x18000ef28  test    eax, eax
0x18000ef2a  js      loc_18000F0A1
0x18000ef30  mov     r8, [rbp+1B0h+var_58]
0x18000ef37  lea     rdx, [rsp+2B0h+var_280]
0x18000ef3c  mov     rcx, rdi
0x18000ef3f  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x18000ef44  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18000ef49  mov     ebx, eax
0x18000ef4b  test    eax, eax
0x18000ef4d  js      short loc_18000EF92
0x18000ef4f  mov     rcx, [rsp+2B0h+var_280]
0x18000ef54  lea     rdx, aPackageData; "Package\\Data"
0x18000ef5b  call    cs:__imp_SRCacheContext_AddToCache
0x18000ef62  nop     dword ptr [rax+rax+00h]
0x18000ef67  mov     ebx, eax
0x18000ef69  test    eax, eax
0x18000ef6b  jns     short loc_18000EFDC
0x18000ef6d  mov     rcx, [rbp+1B8h]; this
0x18000ef74  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ef7b  mov     r9d, eax; char *
0x18000ef7e  mov     edx, 1A6h; void *
0x18000ef83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef88  mov     edx, 4AFh
0x18000ef8d  mov     r9d, ebx
0x18000ef90  jmp     short loc_18000EF9A
0x18000ef92  mov     r9d, eax; char *
0x18000ef95  mov     edx, 4ADh; void *
0x18000ef9a  mov     rcx, [rbp+1B8h]; this
0x18000efa1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000efa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efad  mov     rcx, [rsp+2B0h+var_270]
0x18000efb2  mov     [rsp+2B0h+var_270], 0
0x18000efbb  test    rcx, rcx
0x18000efbe  jz      short loc_18000EFCC
0x18000efc0  call    cs:__imp_SRCache_Free
0x18000efc7  nop     dword ptr [rax+rax+00h]
0x18000efcc  xor     edx, edx
0x18000efce  lea     rcx, [rsp+2B0h+var_280]
0x18000efd3  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000efd8  mov     eax, ebx
0x18000efda  jmp     short loc_18000F01C
0x18000efdc  mov     rcx, [rsp+2B0h+var_270]
0x18000efe1  mov     [rsp+2B0h+var_270], 0
0x18000efea  test    rcx, rcx
0x18000efed  jz      short loc_18000EFFB
0x18000efef  call    cs:__imp_SRCache_Free
0x18000eff6  nop     dword ptr [rax+rax+00h]
0x18000effb  mov     rcx, [rsp+2B0h+var_280]
0x18000f000  mov     [rsp+2B0h+var_280], 0
0x18000f009  test    rcx, rcx
0x18000f00c  jz      short loc_18000F01A
0x18000f00e  call    cs:__imp_SRCacheContext_Close
0x18000f015  nop     dword ptr [rax+rax+00h]
0x18000f01a  xor     eax, eax
0x18000f01c  mov     rcx, [rbp+1B0h+var_28]
0x18000f023  xor     rcx, rsp; StackCookie
0x18000f026  call    __security_check_cookie
0x18000f02b  add     rsp, 290h
0x18000f032  pop     r14
0x18000f034  pop     rdi
0x18000f035  pop     rsi
0x18000f036  pop     rbx
0x18000f037  pop     rbp
0x18000f038  retn
0x18000f03a  mov     rcx, [rbp+1B8h]; this
0x18000f041  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f048  mov     r9d, ebx; char *
0x18000f04b  mov     edx, 18Ch; void *
0x18000f050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f055  mov     edx, 4A8h; void *
0x18000f05a  mov     rcx, [rbp+1B8h]; this
0x18000f061  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f068  mov     r9d, ebx; char *
0x18000f06b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f070  jmp     loc_18000EFCC
0x18000f075  mov     ebx, 80670012h
0x18000f07a  mov     edx, 4A9h
0x18000f07f  jmp     short loc_18000F05A
0x18000f081  mov     rcx, [rbp+1B8h]; this
0x18000f088  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000f08f  mov     ebx, 8000FFFFh
0x18000f094  mov     edx, 166h; void *
0x18000f099  mov     r9d, ebx; char *
0x18000f09c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f0a1  mov     edx, 4ACh
0x18000f0a6  jmp     loc_18000EF8D
```
