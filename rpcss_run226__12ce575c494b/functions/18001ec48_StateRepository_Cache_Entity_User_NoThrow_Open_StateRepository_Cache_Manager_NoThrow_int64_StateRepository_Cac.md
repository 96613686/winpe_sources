# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001ec48`
- end: `0x18001ef3d`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002000c`

## callees

- `0x18001ec48`
- `0x1800211f0`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001ed44`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001ed44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ecdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001edc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ee4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ee79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ecdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001edc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ee4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ee79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001ecb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001ecb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ee36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ee64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ee36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001ee64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001ed98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001ed98`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001ede5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001ede5`

## string_xrefs

- `0x18001ef1a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001ee18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001eeb8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001edf8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001eed3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001eef8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v31);
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
    v23 = 267;
    goto LABEL_25;
  }
  if ( !*(_QWORD *)v24 )
  {
    v8 = -2140733422;
    v23 = 268;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
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
    v16 = 271;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
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
    v16 = 272;
    goto LABEL_14;
  }
  v13 = *(_QWORD *)v24;
  *a4 = *(_QWORD *)a3 != 0;
  v14 = SRCacheContext_AddToCache(v13, L"User\\Data");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      v24[0]);
    v16 = 274;
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
0x18001ec48  mov     [rsp-8+arg_10], rbx
0x18001ec4d  push    rbp
0x18001ec4e  push    rsi
0x18001ec4f  push    rdi
0x18001ec50  push    r14
0x18001ec52  push    r15
0x18001ec54  lea     rbp, [rsp-180h]
0x18001ec5c  sub     rsp, 280h
0x18001ec63  mov     rax, cs:__security_cookie
0x18001ec6a  xor     rax, rsp
0x18001ec6d  mov     [rbp+1A0h+var_28], rax
0x18001ec74  mov     rcx, [rcx]
0x18001ec77  lea     rax, [rsp+2A0h+var_280]
0x18001ec7c  mov     r14, r9
0x18001ec7f  mov     qword ptr [rbp+1A0h+var_50], rax
0x18001ec86  mov     rdi, r8
0x18001ec89  mov     [rbp+1A0h+var_40], 1
0x18001ec90  mov     rsi, rdx
0x18001ec93  lea     r9, [rbp+1A0h+var_48]
0x18001ec9a  xor     r15d, r15d
0x18001ec9d  lea     rdx, aUserData; "User\\Data"
0x18001eca4  xor     r8d, r8d
0x18001eca7  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18001ecac  mov     [rbp+1A0h+var_48], r15
0x18001ecb3  call    cs:__imp_SRCacheContext_Open
0x18001ecb9  mov     ebx, eax
0x18001ecbb  cmp     [rbp+1A0h+var_40], r15b
0x18001ecc2  jz      short loc_18001ECE3
0x18001ecc4  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18001eccb  mov     rdx, [rbp+1A0h+var_48]
0x18001ecd2  mov     rcx, [r8]
0x18001ecd5  mov     [r8], rdx
0x18001ecd8  test    rcx, rcx
0x18001ecdb  jz      short loc_18001ECE3
0x18001ecdd  call    cs:__imp_SRCacheContext_Close
0x18001ece3  test    ebx, ebx
0x18001ece5  js      loc_18001EEF1
0x18001eceb  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18001ecf0  setnz   al
0x18001ecf3  test    al, al
0x18001ecf5  jz      loc_18001EEA7
0x18001ecfb  xor     edx, edx; Val
0x18001ecfd  mov     [rsp+2A0h+var_270], r15
0x18001ed02  mov     r8d, 200h; Size
0x18001ed08  lea     rcx, [rsp+2A0h+var_268]; void *
0x18001ed0d  call    memset_0
0x18001ed12  mov     r9d, 10h
0x18001ed18  mov     [rbp+1A0h+var_68], r15
0x18001ed1f  lea     rax, [rsp+2A0h+var_268]
0x18001ed24  mov     [rbp+1A0h+var_60], 100h
0x18001ed2f  lea     rdx, [rbp+1A0h+var_50]
0x18001ed36  mov     [rbp+1A0h+var_58], rax
0x18001ed3d  mov     rcx, rsi
0x18001ed40  lea     r8d, [r9+1]
0x18001ed44  call    cs:__imp__o__ui64tow_s
0x18001ed4a  test    eax, eax
0x18001ed4c  jnz     loc_18001EF13
0x18001ed52  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18001ed59  lea     rcx, [rsp+2A0h+var_270]; this
0x18001ed5e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001ed63  mov     ebx, eax
0x18001ed65  test    eax, eax
0x18001ed67  js      loc_18001EF33
0x18001ed6d  mov     rdx, [rbp+1A0h+var_58]
0x18001ed74  lea     r9, [rbp+1A0h+var_48]
0x18001ed7b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001ed80  xor     r8d, r8d
0x18001ed83  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18001ed8a  mov     [rbp+1A0h+var_48], r15
0x18001ed91  mov     [rbp+1A0h+var_40], 1
0x18001ed98  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001ed9e  mov     ebx, eax
0x18001eda0  cmp     [rbp+1A0h+var_40], r15b
0x18001eda7  jz      short loc_18001EDC8
0x18001eda9  mov     r8, qword ptr [rbp+1A0h+var_50]
0x18001edb0  mov     rdx, [rbp+1A0h+var_48]
0x18001edb7  mov     rcx, [r8]
0x18001edba  mov     [r8], rdx
0x18001edbd  test    rcx, rcx
0x18001edc0  jz      short loc_18001EDC8
0x18001edc2  call    cs:__imp_SRCacheContext_Close
0x18001edc8  test    ebx, ebx
0x18001edca  js      loc_18001EECC
0x18001edd0  cmp     [rdi], r15
0x18001edd3  lea     rdx, aUserData; "User\\Data"
0x18001edda  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001eddf  setnz   al
0x18001ede2  mov     [r14], al
0x18001ede5  call    cs:__imp_SRCacheContext_AddToCache
0x18001edeb  mov     ebx, eax
0x18001eded  test    eax, eax
0x18001edef  jns     short loc_18001EE55
0x18001edf1  mov     rcx, [rbp+1A8h]; this
0x18001edf8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001edff  mov     r9d, eax; char *
0x18001ee02  mov     edx, 1A6h; void *
0x18001ee07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee0c  mov     edx, 112h; void *
0x18001ee11  mov     rcx, [rbp+1A8h]; this
0x18001ee18  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ee1f  mov     r9d, ebx; char *
0x18001ee22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee27  mov     rcx, [rsp+2A0h+var_270]
0x18001ee2c  mov     [rsp+2A0h+var_270], r15
0x18001ee31  test    rcx, rcx
0x18001ee34  jz      short loc_18001EE3C
0x18001ee36  call    cs:__imp_SRCache_Free
0x18001ee3c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001ee41  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001ee46  test    rcx, rcx
0x18001ee49  jz      short loc_18001EE51
0x18001ee4b  call    cs:__imp_SRCacheContext_Close
0x18001ee51  mov     eax, ebx
0x18001ee53  jmp     short loc_18001EE81
0x18001ee55  mov     rcx, [rsp+2A0h+var_270]
0x18001ee5a  mov     [rsp+2A0h+var_270], r15
0x18001ee5f  test    rcx, rcx
0x18001ee62  jz      short loc_18001EE6A
0x18001ee64  call    cs:__imp_SRCache_Free
0x18001ee6a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001ee6f  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001ee74  test    rcx, rcx
0x18001ee77  jz      short loc_18001EE7F
0x18001ee79  call    cs:__imp_SRCacheContext_Close
0x18001ee7f  xor     eax, eax
0x18001ee81  mov     rcx, [rbp+1A0h+var_28]
0x18001ee88  xor     rcx, rsp; StackCookie
0x18001ee8b  call    __security_check_cookie
0x18001ee90  mov     rbx, [rsp+2A0h+arg_10]
0x18001ee98  add     rsp, 280h
0x18001ee9f  pop     r15
0x18001eea1  pop     r14
0x18001eea3  pop     rdi
0x18001eea4  pop     rsi
0x18001eea5  pop     rbp
0x18001eea6  retn
0x18001eea7  mov     ebx, 80670012h
0x18001eeac  mov     edx, 10Ch; void *
0x18001eeb1  mov     rcx, [rbp+1A8h]; this
0x18001eeb8  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001eebf  mov     r9d, ebx; char *
0x18001eec2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eec7  jmp     loc_18001EE3C
0x18001eecc  mov     rcx, [rbp+1A8h]; this
0x18001eed3  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001eeda  mov     r9d, ebx; char *
0x18001eedd  mov     edx, 1B0h; void *
0x18001eee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eee7  mov     edx, 110h
0x18001eeec  jmp     loc_18001EE11
0x18001eef1  mov     rcx, [rbp+1A8h]; this
0x18001eef8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001eeff  mov     r9d, ebx; char *
0x18001ef02  mov     edx, 18Ch; void *
0x18001ef07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef0c  mov     edx, 10Bh
0x18001ef11  jmp     short loc_18001EEB1
0x18001ef13  mov     rcx, [rbp+1A8h]; this
0x18001ef1a  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ef21  mov     ebx, 8000FFFFh
0x18001ef26  mov     edx, 166h; void *
0x18001ef2b  mov     r9d, ebx; char *
0x18001ef2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef33  mov     edx, 10Fh
0x18001ef38  jmp     loc_18001EE11
```
