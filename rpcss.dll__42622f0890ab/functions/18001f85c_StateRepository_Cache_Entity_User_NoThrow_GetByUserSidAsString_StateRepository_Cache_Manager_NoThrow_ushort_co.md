# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18001f85c`
- end: `0x18001fb6f`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `787`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002000c`

## callees

- `0x18001f85c`
- `0x1800211f0`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f983`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f9f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fa7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001facc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001faf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f983`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001f9f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fa7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001facc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001faf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001f8ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001f8ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001fa8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001fa8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f96e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fae1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f96e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fae1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001f9d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001f9d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001fa22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001fa22`

## string_xrefs

- `0x18001f8b3`: `User\Index\UserSid`
- `0x18001fa1b`: `User\Index\UserSid`
- `0x18001f94b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001fa59`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001fb4f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001fa39`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001faa2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001fb0a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001fb2f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v25 = 0;
  v27 = v25;
  v28 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v24 = 185;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v25[0]);
LABEL_10:
    v12 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v10);
    return v6;
  }
  if ( !*(_QWORD *)v25 )
  {
    v6 = -2140733422;
    v24 = 186;
    goto LABEL_33;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v9,
      v25[0]);
LABEL_8:
    v11 = v30;
    v30 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_10;
  }
  v27 = (int *)&v26;
  v26 = 0;
  v28 = 0;
  v29 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
  if ( v29 )
  {
    v14 = v28;
    v15 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v15 )
      SRCacheContext_Close(v15, v14);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v18 = 193;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v25[0]);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close(v19, v10);
    goto LABEL_8;
  }
  if ( v26 )
  {
    v20 = SRCacheContext_EnumerateData(v26, 0, a3);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v20,
        v25[0]);
      v18 = 196;
      goto LABEL_20;
    }
  }
  v16 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"User\\Index\\UserSid");
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      v25[0]);
    v18 = 199;
    goto LABEL_20;
  }
  v21 = v26;
  v26 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v17);
  v22 = v30;
  v30 = 0;
  if ( v22 )
    SRCache_Free();
  v23 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v23 )
    SRCacheContext_Close(v23, v17);
  return 0;
}

```

## disassembly

```asm
0x18001f85c  push    rbp
0x18001f85e  push    rbx
0x18001f85f  push    rsi
0x18001f860  push    rdi
0x18001f861  push    r14
0x18001f863  lea     rbp, [rsp-180h]
0x18001f86b  sub     rsp, 280h
0x18001f872  mov     rax, cs:__security_cookie
0x18001f879  xor     rax, rsp
0x18001f87c  mov     [rbp+1A0h+var_30], rax
0x18001f883  xor     r14d, r14d
0x18001f886  mov     [rsp+2A0h+var_260], 1
0x18001f88b  mov     [r8], r14
0x18001f88e  lea     rax, [rsp+2A0h+var_280]
0x18001f893  mov     rcx, [rcx]
0x18001f896  lea     r9, [rsp+2A0h+var_268]
0x18001f89b  mov     rdi, r8
0x18001f89e  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18001f8a3  mov     rsi, rdx
0x18001f8a6  mov     [rsp+2A0h+var_270], rax
0x18001f8ab  xor     r8d, r8d
0x18001f8ae  mov     [rsp+2A0h+var_268], r14
0x18001f8b3  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18001f8ba  call    cs:__imp_SRCacheContext_Open
0x18001f8c0  mov     ebx, eax
0x18001f8c2  cmp     [rsp+2A0h+var_260], r14b
0x18001f8c7  jz      short loc_18001F8E4
0x18001f8c9  mov     r8, [rsp+2A0h+var_270]
0x18001f8ce  mov     rdx, [rsp+2A0h+var_268]
0x18001f8d3  mov     rcx, [r8]
0x18001f8d6  mov     [r8], rdx
0x18001f8d9  test    rcx, rcx
0x18001f8dc  jz      short loc_18001F8E4
0x18001f8de  call    cs:__imp_SRCacheContext_Close
0x18001f8e4  test    ebx, ebx
0x18001f8e6  js      loc_18001FB28
0x18001f8ec  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18001f8f1  setnz   al
0x18001f8f4  test    al, al
0x18001f8f6  jz      loc_18001FB63
0x18001f8fc  xor     edx, edx; Val
0x18001f8fe  mov     [rsp+2A0h+var_250], r14
0x18001f903  mov     r8d, 200h; Size
0x18001f909  lea     rcx, [rsp+2A0h+var_248]; void *
0x18001f90e  call    memset_0
0x18001f913  lea     rax, [rsp+2A0h+var_248]
0x18001f918  mov     [rbp+1A0h+var_48], r14
0x18001f91f  mov     rdx, rsi; unsigned __int16 *
0x18001f922  mov     [rbp+1A0h+var_38], rax
0x18001f929  lea     rcx, [rsp+2A0h+var_250]; this
0x18001f92e  mov     [rbp+1A0h+var_40], 100h
0x18001f939  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001f93e  mov     ebx, eax
0x18001f940  test    eax, eax
0x18001f942  jns     short loc_18001F9A8
0x18001f944  mov     rcx, [rbp+1A8h]; this
0x18001f94b  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f952  mov     r9d, eax; char *
0x18001f955  mov     edx, 0BDh; void *
0x18001f95a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f95f  mov     rcx, [rsp+2A0h+var_250]
0x18001f964  mov     [rsp+2A0h+var_250], r14
0x18001f969  test    rcx, rcx
0x18001f96c  jz      short loc_18001F974
0x18001f96e  call    cs:__imp_SRCache_Free
0x18001f974  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f979  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001f97e  test    rcx, rcx
0x18001f981  jz      short loc_18001F989
0x18001f983  call    cs:__imp_SRCacheContext_Close
0x18001f989  mov     eax, ebx
0x18001f98b  mov     rcx, [rbp+1A0h+var_30]
0x18001f992  xor     rcx, rsp; StackCookie
0x18001f995  call    __security_check_cookie
0x18001f99a  add     rsp, 280h
0x18001f9a1  pop     r14
0x18001f9a3  pop     rdi
0x18001f9a4  pop     rsi
0x18001f9a5  pop     rbx
0x18001f9a6  pop     rbp
0x18001f9a7  retn
0x18001f9a8  mov     rdx, [rbp+1A0h+var_38]
0x18001f9af  lea     rax, [rsp+2A0h+var_278]
0x18001f9b4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001f9b9  lea     r9, [rsp+2A0h+var_268]
0x18001f9be  xor     r8d, r8d
0x18001f9c1  mov     [rsp+2A0h+var_270], rax
0x18001f9c6  mov     [rsp+2A0h+var_278], r14
0x18001f9cb  mov     [rsp+2A0h+var_268], r14
0x18001f9d0  mov     [rsp+2A0h+var_260], 1
0x18001f9d5  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001f9db  mov     ebx, eax
0x18001f9dd  cmp     [rsp+2A0h+var_260], r14b
0x18001f9e2  jz      short loc_18001F9FF
0x18001f9e4  mov     r8, [rsp+2A0h+var_270]
0x18001f9e9  mov     rdx, [rsp+2A0h+var_268]
0x18001f9ee  mov     rcx, [r8]
0x18001f9f1  mov     [r8], rdx
0x18001f9f4  test    rcx, rcx
0x18001f9f7  jz      short loc_18001F9FF
0x18001f9f9  call    cs:__imp_SRCacheContext_Close
0x18001f9ff  test    ebx, ebx
0x18001fa01  js      loc_18001FB03
0x18001fa07  mov     rcx, [rsp+2A0h+var_278]
0x18001fa0c  test    rcx, rcx
0x18001fa0f  setnz   al
0x18001fa12  test    al, al
0x18001fa14  jnz     short loc_18001FA86
0x18001fa16  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001fa1b  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18001fa22  call    cs:__imp_SRCacheContext_AddToCache
0x18001fa28  mov     ebx, eax
0x18001fa2a  test    eax, eax
0x18001fa2c  jns     loc_18001FABD
0x18001fa32  mov     rcx, [rbp+1A8h]; this
0x18001fa39  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fa40  mov     r9d, eax; char *
0x18001fa43  mov     edx, 1A6h; void *
0x18001fa48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa4d  mov     edx, 0C7h; void *
0x18001fa52  mov     rcx, [rbp+1A8h]; this
0x18001fa59  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fa60  mov     r9d, ebx; char *
0x18001fa63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa68  mov     rcx, [rsp+2A0h+var_278]
0x18001fa6d  mov     [rsp+2A0h+var_278], r14
0x18001fa72  test    rcx, rcx
0x18001fa75  jz      loc_18001F95F
0x18001fa7b  call    cs:__imp_SRCacheContext_Close
0x18001fa81  jmp     loc_18001F95F
0x18001fa86  mov     r8, rdi
0x18001fa89  xor     edx, edx
0x18001fa8b  call    cs:__imp_SRCacheContext_EnumerateData
0x18001fa91  mov     ebx, eax
0x18001fa93  test    eax, eax
0x18001fa95  jns     loc_18001FA16
0x18001fa9b  mov     rcx, [rbp+1A8h]; this
0x18001faa2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001faa9  mov     r9d, eax; char *
0x18001faac  mov     edx, 2A6h; void *
0x18001fab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fab6  mov     edx, 0C4h
0x18001fabb  jmp     short loc_18001FA52
0x18001fabd  mov     rcx, [rsp+2A0h+var_278]
0x18001fac2  mov     [rsp+2A0h+var_278], r14
0x18001fac7  test    rcx, rcx
0x18001faca  jz      short loc_18001FAD2
0x18001facc  call    cs:__imp_SRCacheContext_Close
0x18001fad2  mov     rcx, [rsp+2A0h+var_250]
0x18001fad7  mov     [rsp+2A0h+var_250], r14
0x18001fadc  test    rcx, rcx
0x18001fadf  jz      short loc_18001FAE7
0x18001fae1  call    cs:__imp_SRCache_Free
0x18001fae7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001faec  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001faf1  test    rcx, rcx
0x18001faf4  jz      short loc_18001FAFC
0x18001faf6  call    cs:__imp_SRCacheContext_Close
0x18001fafc  xor     eax, eax
0x18001fafe  jmp     loc_18001F98B
0x18001fb03  mov     rcx, [rbp+1A8h]; this
0x18001fb0a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fb11  mov     r9d, ebx; char *
0x18001fb14  mov     edx, 1B0h; void *
0x18001fb19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb1e  mov     edx, 0C1h
0x18001fb23  jmp     loc_18001FA52
0x18001fb28  mov     rcx, [rbp+1A8h]; this
0x18001fb2f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fb36  mov     r9d, ebx; char *
0x18001fb39  mov     edx, 18Ch; void *
0x18001fb3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb43  mov     edx, 0B9h; void *
0x18001fb48  mov     rcx, [rbp+1A8h]; this
0x18001fb4f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fb56  mov     r9d, ebx; char *
0x18001fb59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb5e  jmp     loc_18001F974
0x18001fb63  mov     ebx, 80670012h
0x18001fb68  mov     edx, 0BAh
0x18001fb6d  jmp     short loc_18001FB48
```
