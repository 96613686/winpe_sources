# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800a39ec`
- end: `0x1800a3c81`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800cd338`

## callees

- `0x1800211f0`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x1800a39ec`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a3b22`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a3b22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3ab4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3c53`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3ab4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3c53`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a3a57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a3a57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a3b93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a3c3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a3b93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a3c3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a3bc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a3bc9`

## string_xrefs

- `0x1800a3b33`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800a3a76`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a3be8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a3a96`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800a3b71`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+238h] [rbp+138h]
  __int64 v22; // [rsp+240h] [rbp+140h]
  _BYTE *v23; // [rsp+248h] [rbp+148h]
  unsigned __int16 v24[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h] BYREF
  char v26; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v24 = v18;
  v26 = 1;
  *(_QWORD *)v18 = 0;
  v25 = 0;
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v9 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
LABEL_4:
    v11 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v18 )
  {
    v8 = -2140733422;
    v9 = 392;
    goto LABEL_3;
  }
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  v22 = 256;
  v23 = v20;
  if ( (unsigned int)_o__ui64tow_s(a2, v24, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v18[0]);
LABEL_12:
    v13 = 395;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v19, v24);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v24 = a3;
  v25 = 0;
  v26 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v23, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v13 = 396;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v13 = 398;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v14 = v19;
    v19 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_4;
  }
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17, v15);
  return 0;
}

```

## disassembly

```asm
0x1800a39ec  mov     [rsp-8+arg_10], rbx
0x1800a39f1  push    rbp
0x1800a39f2  push    rsi
0x1800a39f3  push    rdi
0x1800a39f4  push    r14
0x1800a39f6  push    r15
0x1800a39f8  lea     rbp, [rsp-180h]
0x1800a3a00  sub     rsp, 280h
0x1800a3a07  mov     rax, cs:__security_cookie
0x1800a3a0e  xor     rax, rsp
0x1800a3a11  mov     [rbp+1A0h+var_28], rax
0x1800a3a18  mov     rcx, [rcx]
0x1800a3a1b  lea     rax, [rsp+2A0h+var_280]
0x1800a3a20  mov     rsi, r9
0x1800a3a23  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800a3a2a  mov     rdi, r8
0x1800a3a2d  mov     [rbp+1A0h+var_40], 1
0x1800a3a34  mov     r14, rdx
0x1800a3a37  lea     r9, [rbp+1A0h+var_48]
0x1800a3a3e  xor     r15d, r15d
0x1800a3a41  lea     rdx, aActivationData; "Activation\\Data"
0x1800a3a48  xor     r8d, r8d
0x1800a3a4b  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800a3a50  mov     [rbp+1A0h+var_48], r15
0x1800a3a57  call    cs:__imp_SRCacheContext_Open
0x1800a3a5d  lea     rcx, [rbp+1A0h+var_50]
0x1800a3a64  mov     ebx, eax
0x1800a3a66  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a3a6b  test    ebx, ebx
0x1800a3a6d  jns     short loc_1800A3AC1
0x1800a3a6f  mov     rcx, [rbp+1A8h]; this
0x1800a3a76  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3a7d  mov     r9d, ebx; char *
0x1800a3a80  mov     edx, 18Ch; void *
0x1800a3a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3a8a  mov     edx, 187h; void *
0x1800a3a8f  mov     rcx, [rbp+1A8h]; this
0x1800a3a96  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3a9d  mov     r9d, ebx; char *
0x1800a3aa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3aa5  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a3aaa  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a3aaf  test    rcx, rcx
0x1800a3ab2  jz      short loc_1800A3ABA
0x1800a3ab4  call    cs:__imp_SRCacheContext_Close
0x1800a3aba  mov     eax, ebx
0x1800a3abc  jmp     loc_1800A3C5B
0x1800a3ac1  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800a3ac6  setnz   al
0x1800a3ac9  test    al, al
0x1800a3acb  jnz     short loc_1800A3AD9
0x1800a3acd  mov     ebx, 80670012h
0x1800a3ad2  mov     edx, 188h
0x1800a3ad7  jmp     short loc_1800A3A8F
0x1800a3ad9  xor     edx, edx; Val
0x1800a3adb  mov     [rsp+2A0h+var_270], r15
0x1800a3ae0  mov     r8d, 200h; Size
0x1800a3ae6  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800a3aeb  call    memset_0
0x1800a3af0  mov     r9d, 10h
0x1800a3af6  mov     [rbp+1A0h+var_68], r15
0x1800a3afd  lea     rax, [rsp+2A0h+var_268]
0x1800a3b02  mov     [rbp+1A0h+var_60], 100h
0x1800a3b0d  lea     rdx, [rbp+1A0h+var_50]
0x1800a3b14  mov     [rbp+1A0h+var_58], rax
0x1800a3b1b  mov     rcx, r14
0x1800a3b1e  lea     r8d, [r9+1]
0x1800a3b22  call    cs:__imp__o__ui64tow_s
0x1800a3b28  test    eax, eax
0x1800a3b2a  jz      short loc_1800A3B4E
0x1800a3b2c  mov     rcx, [rbp+1A8h]; this
0x1800a3b33  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3b3a  mov     ebx, 8000FFFFh
0x1800a3b3f  mov     edx, 166h; void *
0x1800a3b44  mov     r9d, ebx; char *
0x1800a3b47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3b4c  jmp     short loc_1800A3B65
0x1800a3b4e  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800a3b55  lea     rcx, [rsp+2A0h+var_270]; this
0x1800a3b5a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a3b5f  mov     ebx, eax
0x1800a3b61  test    eax, eax
0x1800a3b63  jns     short loc_1800A3B9E
0x1800a3b65  mov     edx, 18Bh; void *
0x1800a3b6a  mov     rcx, [rbp+1A8h]; this
0x1800a3b71  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3b78  mov     r9d, ebx; char *
0x1800a3b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3b80  mov     rcx, [rsp+2A0h+var_270]
0x1800a3b85  mov     [rsp+2A0h+var_270], r15
0x1800a3b8a  test    rcx, rcx
0x1800a3b8d  jz      loc_1800A3AA5
0x1800a3b93  call    cs:__imp_SRCache_Free
0x1800a3b99  jmp     loc_1800A3AA5
0x1800a3b9e  mov     rdx, [rbp+1A0h+var_58]
0x1800a3ba5  lea     r9, [rbp+1A0h+var_48]
0x1800a3bac  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a3bb1  xor     r8d, r8d
0x1800a3bb4  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1800a3bbb  mov     [rbp+1A0h+var_48], r15
0x1800a3bc2  mov     [rbp+1A0h+var_40], 1
0x1800a3bc9  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800a3bcf  lea     rcx, [rbp+1A0h+var_50]
0x1800a3bd6  mov     ebx, eax
0x1800a3bd8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a3bdd  test    ebx, ebx
0x1800a3bdf  jns     short loc_1800A3C06
0x1800a3be1  mov     rcx, [rbp+1A8h]; this
0x1800a3be8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3bef  mov     r9d, ebx; char *
0x1800a3bf2  mov     edx, 1B0h; void *
0x1800a3bf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3bfc  mov     edx, 18Ch
0x1800a3c01  jmp     loc_1800A3B6A
0x1800a3c06  cmp     [rdi], r15
0x1800a3c09  lea     rdx, aActivationData; "Activation\\Data"
0x1800a3c10  lea     rcx, [rsp+2A0h+var_280]; this
0x1800a3c15  setnz   al
0x1800a3c18  mov     [rsi], al
0x1800a3c1a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a3c1f  mov     ebx, eax
0x1800a3c21  test    eax, eax
0x1800a3c23  jns     short loc_1800A3C2F
0x1800a3c25  mov     edx, 18Eh
0x1800a3c2a  jmp     loc_1800A3B6A
0x1800a3c2f  mov     rcx, [rsp+2A0h+var_270]
0x1800a3c34  mov     [rsp+2A0h+var_270], r15
0x1800a3c39  test    rcx, rcx
0x1800a3c3c  jz      short loc_1800A3C44
0x1800a3c3e  call    cs:__imp_SRCache_Free
0x1800a3c44  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a3c49  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a3c4e  test    rcx, rcx
0x1800a3c51  jz      short loc_1800A3C59
0x1800a3c53  call    cs:__imp_SRCacheContext_Close
0x1800a3c59  xor     eax, eax
0x1800a3c5b  mov     rcx, [rbp+1A0h+var_28]
0x1800a3c62  xor     rcx, rsp; StackCookie
0x1800a3c65  call    __security_check_cookie
0x1800a3c6a  mov     rbx, [rsp+2A0h+arg_10]
0x1800a3c72  add     rsp, 280h
0x1800a3c79  pop     r15
0x1800a3c7b  pop     r14
0x1800a3c7d  pop     rdi
0x1800a3c7e  pop     rsi
0x1800a3c7f  pop     rbp
0x1800a3c80  retn
```
