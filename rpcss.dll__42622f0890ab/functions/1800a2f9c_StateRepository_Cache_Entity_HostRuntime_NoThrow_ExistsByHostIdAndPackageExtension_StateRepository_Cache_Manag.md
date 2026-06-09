# StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64,bool &)

- ea: `0x1800a2f9c`
- end: `0x1800a334a`
- name: `?ExistsByHostIdAndPackageExtension@HostRuntime_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBG_JAEA_N@Z`
- size: `942`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800722a0`

## callees

- `0x1800211f0`
- `0x1800217e4`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x180079db0`
- `0x1800a2f9c`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a31a4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a31a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3287`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a32f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3323`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3092`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3287`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a32f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a3323`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a3031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a3031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a312b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a330e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a312b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a330e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a3226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a3226`

## string_xrefs

- `0x1800a3158`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800a31b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800a3050`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a3245`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a2fe0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800a3070`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800a3109`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800a3265`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800a301c`: `HostRuntime\Index\HostIdAndPackageExtension`
- `0x1800a32c9`: `HostRuntime\Index\HostIdAndPackageExtension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        bool *a4)
{
  int IsEmpty; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+248h] [rbp+148h]
  __int64 v29; // [rsp+250h] [rbp+150h]
  _BYTE *v30; // [rsp+258h] [rbp+158h]
  unsigned __int16 v31[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v32; // [rsp+268h] [rbp+168h] BYREF
  char v33; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a3 )
  {
    IsEmpty = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)0x80070057LL,
      v23);
    return (unsigned int)IsEmpty;
  }
  v9 = *(_QWORD *)a1;
  *(_QWORD *)v31 = &v24;
  v24 = 0;
  v32 = 0;
  v33 = 1;
  IsEmpty = SRCacheContext_Open(v9, L"HostRuntime\\Index\\HostIdAndPackageExtension", 0, &v32);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v31);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v23);
    v10 = 107;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)IsEmpty,
      v23);
LABEL_7:
    v12 = v24;
    v24 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)IsEmpty;
  }
  if ( !v24 )
  {
    IsEmpty = -2140733422;
    v10 = 108;
    goto LABEL_6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  if ( IsEmpty < 0 )
  {
    v14 = 111;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)IsEmpty,
      v23);
LABEL_14:
    v15 = v26;
    v26 = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_7;
  }
  v16 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v26, v28 + 2, v13);
  IsEmpty = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v16,
      v23);
    v14 = 112;
    goto LABEL_13;
  }
  *(_DWORD *)&v30[2 * v28++] = 94;
  if ( (unsigned int)_o__ui64tow_s(a3, v31, 17) )
  {
    IsEmpty = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v23);
LABEL_21:
    v14 = 113;
    goto LABEL_13;
  }
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, v31);
  if ( IsEmpty < 0 )
    goto LABEL_21;
  *(_QWORD *)v31 = v25;
  v25[0] = 0;
  v32 = 0;
  v33 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v24, v30, 0, &v32);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v31);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v23);
    v17 = 117;
    goto LABEL_24;
  }
  if ( v25[0] )
  {
    LOBYTE(v23) = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty(
                (StateRepository::Cache::Context_NoThrow *)v25,
                (bool *)&v23);
    if ( IsEmpty < 0 )
    {
      v17 = 121;
      goto LABEL_24;
    }
    *a4 = (_BYTE)v23 == 0;
  }
  IsEmpty = StateRepository::Cache::Context_NoThrow::AddToCache(
              (StateRepository::Cache::Context_NoThrow *)&v24,
              L"HostRuntime\\Index\\HostIdAndPackageExtension");
  if ( IsEmpty < 0 )
  {
    v17 = 125;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)IsEmpty,
      v23);
    v18 = v25[0];
    v25[0] = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v11);
    goto LABEL_14;
  }
  v20 = v25[0];
  v25[0] = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v19);
  v21 = v26;
  v26 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = v24;
  v24 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v19);
  return 0;
}

```

## disassembly

```asm
0x1800a2f9c  push    rbp
0x1800a2f9e  push    rbx
0x1800a2f9f  push    rsi
0x1800a2fa0  push    rdi
0x1800a2fa1  push    r14
0x1800a2fa3  push    r15
0x1800a2fa5  lea     rbp, [rsp-198h]
0x1800a2fad  sub     rsp, 298h
0x1800a2fb4  mov     rax, cs:__security_cookie
0x1800a2fbb  xor     rax, rsp
0x1800a2fbe  mov     [rbp+1C0h+var_38], rax
0x1800a2fc5  xor     r15d, r15d
0x1800a2fc8  mov     rdi, r9
0x1800a2fcb  mov     [r9], r15b
0x1800a2fce  mov     rsi, r8
0x1800a2fd1  mov     r14, rdx
0x1800a2fd4  test    r8, r8
0x1800a2fd7  jnz     short loc_1800A2FFE
0x1800a2fd9  mov     rcx, [rbp+1C8h]; this
0x1800a2fe0  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a2fe7  mov     ebx, 80070057h
0x1800a2fec  lea     edx, [rsi+67h]; void *
0x1800a2fef  mov     r9d, ebx; char *
0x1800a2ff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ff7  mov     eax, ebx
0x1800a2ff9  jmp     loc_1800A332B
0x1800a2ffe  mov     rcx, [rcx]
0x1800a3001  lea     rax, [rsp+2C0h+var_298]
0x1800a3006  lea     r9, [rbp+1C0h+var_58]
0x1800a300d  mov     qword ptr [rbp+1C0h+var_60], rax
0x1800a3014  xor     r8d, r8d
0x1800a3017  mov     [rsp+2C0h+var_298], r15
0x1800a301c  lea     rdx, aHostruntimeInd; "HostRuntime\\Index\\HostIdAndPackageExt"...
0x1800a3023  mov     [rbp+1C0h+var_58], r15
0x1800a302a  mov     [rbp+1C0h+var_50], 1
0x1800a3031  call    cs:__imp_SRCacheContext_Open
0x1800a3037  lea     rcx, [rbp+1C0h+var_60]
0x1800a303e  mov     ebx, eax
0x1800a3040  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a3045  test    ebx, ebx
0x1800a3047  jns     short loc_1800A309D
0x1800a3049  mov     rcx, [rbp+1C8h]; this
0x1800a3050  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3057  mov     r9d, ebx; char *
0x1800a305a  mov     edx, 18Ch; void *
0x1800a305f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3064  mov     edx, 6Bh ; 'k'; void *
0x1800a3069  mov     rcx, [rbp+1C8h]; this
0x1800a3070  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3077  mov     r9d, ebx; char *
0x1800a307a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a307f  mov     rcx, [rsp+2C0h+var_298]
0x1800a3084  mov     [rsp+2C0h+var_298], r15
0x1800a3089  test    rcx, rcx
0x1800a308c  jz      loc_1800A2FF7
0x1800a3092  call    cs:__imp_SRCacheContext_Close
0x1800a3098  jmp     loc_1800A2FF7
0x1800a309d  cmp     [rsp+2C0h+var_298], r15
0x1800a30a2  setnz   al
0x1800a30a5  test    al, al
0x1800a30a7  jnz     short loc_1800A30B5
0x1800a30a9  mov     ebx, 80670012h
0x1800a30ae  mov     edx, 6Ch ; 'l'
0x1800a30b3  jmp     short loc_1800A3069
0x1800a30b5  xor     edx, edx; Val
0x1800a30b7  mov     [rsp+2C0h+var_280], r15
0x1800a30bc  mov     r8d, 200h; Size
0x1800a30c2  lea     rcx, [rsp+2C0h+var_278]; void *
0x1800a30c7  call    memset_0
0x1800a30cc  lea     rax, [rsp+2C0h+var_278]
0x1800a30d1  mov     [rbp+1C0h+var_78], r15
0x1800a30d8  mov     rdx, r14; unsigned __int16 *
0x1800a30db  mov     [rbp+1C0h+var_68], rax
0x1800a30e2  lea     rcx, [rsp+2C0h+var_280]; this
0x1800a30e7  mov     [rbp+1C0h+var_70], 100h
0x1800a30f2  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a30f7  mov     ebx, eax
0x1800a30f9  test    eax, eax
0x1800a30fb  jns     short loc_1800A3136
0x1800a30fd  mov     edx, 6Fh ; 'o'; void *
0x1800a3102  mov     rcx, [rbp+1C8h]; this
0x1800a3109  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a3110  mov     r9d, ebx; char *
0x1800a3113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3118  mov     rcx, [rsp+2C0h+var_280]
0x1800a311d  mov     [rsp+2C0h+var_280], r15
0x1800a3122  test    rcx, rcx
0x1800a3125  jz      loc_1800A307F
0x1800a312b  call    cs:__imp_SRCache_Free
0x1800a3131  jmp     loc_1800A307F
0x1800a3136  mov     rdx, [rbp+1C0h+var_78]
0x1800a313d  lea     rcx, [rsp+2C0h+var_280]; this
0x1800a3142  add     rdx, 2; unsigned __int64
0x1800a3146  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x1800a314b  mov     ebx, eax
0x1800a314d  test    eax, eax
0x1800a314f  jns     short loc_1800A3173
0x1800a3151  mov     rcx, [rbp+1C8h]; this
0x1800a3158  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a315f  mov     r9d, eax; char *
0x1800a3162  mov     edx, 16Dh; void *
0x1800a3167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a316c  mov     edx, 70h ; 'p'
0x1800a3171  jmp     short loc_1800A3102
0x1800a3173  mov     r8, [rbp+1C0h+var_78]
0x1800a317a  mov     r9d, 10h
0x1800a3180  mov     rdx, [rbp+1C0h+var_68]
0x1800a3187  mov     rcx, rsi
0x1800a318a  mov     dword ptr [rdx+r8*2], 5Eh ; '^'
0x1800a3192  lea     r8d, [r9+1]
0x1800a3196  inc     [rbp+1C0h+var_78]
0x1800a319d  lea     rdx, [rbp+1C0h+var_60]
0x1800a31a4  call    cs:__imp__o__ui64tow_s
0x1800a31aa  test    eax, eax
0x1800a31ac  jz      short loc_1800A31D0
0x1800a31ae  mov     rcx, [rbp+1C8h]; this
0x1800a31b5  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a31bc  mov     ebx, 8000FFFFh
0x1800a31c1  mov     edx, 166h; void *
0x1800a31c6  mov     r9d, ebx; char *
0x1800a31c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a31ce  jmp     short loc_1800A31E7
0x1800a31d0  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x1800a31d7  lea     rcx, [rsp+2C0h+var_280]; this
0x1800a31dc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a31e1  mov     ebx, eax
0x1800a31e3  test    eax, eax
0x1800a31e5  jns     short loc_1800A31F1
0x1800a31e7  mov     edx, 71h ; 'q'
0x1800a31ec  jmp     loc_1800A3102
0x1800a31f1  mov     rdx, [rbp+1C0h+var_68]
0x1800a31f8  lea     rax, [rsp+2C0h+var_290]
0x1800a31fd  mov     rcx, [rsp+2C0h+var_298]
0x1800a3202  lea     r9, [rbp+1C0h+var_58]
0x1800a3209  xor     r8d, r8d
0x1800a320c  mov     qword ptr [rbp+1C0h+var_60], rax
0x1800a3213  mov     [rsp+2C0h+var_290], r15
0x1800a3218  mov     [rbp+1C0h+var_58], r15
0x1800a321f  mov     [rbp+1C0h+var_50], 1
0x1800a3226  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800a322c  lea     rcx, [rbp+1C0h+var_60]
0x1800a3233  mov     ebx, eax
0x1800a3235  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a323a  test    ebx, ebx
0x1800a323c  jns     short loc_1800A3292
0x1800a323e  mov     rcx, [rbp+1C8h]; this
0x1800a3245  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a324c  mov     r9d, ebx; char *
0x1800a324f  mov     edx, 1B0h; void *
0x1800a3254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3259  mov     edx, 75h ; 'u'; void *
0x1800a325e  mov     rcx, [rbp+1C8h]; this
0x1800a3265  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a326c  mov     r9d, ebx; char *
0x1800a326f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3274  mov     rcx, [rsp+2C0h+var_290]
0x1800a3279  mov     [rsp+2C0h+var_290], r15
0x1800a327e  test    rcx, rcx
0x1800a3281  jz      loc_1800A3118
0x1800a3287  call    cs:__imp_SRCacheContext_Close
0x1800a328d  jmp     loc_1800A3118
0x1800a3292  cmp     [rsp+2C0h+var_290], r15
0x1800a3297  setnz   al
0x1800a329a  test    al, al
0x1800a329c  jz      short loc_1800A32C9
0x1800a329e  lea     rdx, [rsp+2C0h+var_2A0]; bool *
0x1800a32a3  mov     byte ptr [rsp+2C0h+var_2A0], r15b
0x1800a32a8  lea     rcx, [rsp+2C0h+var_290]; this
0x1800a32ad  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x1800a32b2  mov     ebx, eax
0x1800a32b4  test    eax, eax
0x1800a32b6  jns     short loc_1800A32BF
0x1800a32b8  mov     edx, 79h ; 'y'
0x1800a32bd  jmp     short loc_1800A325E
0x1800a32bf  cmp     byte ptr [rsp+2C0h+var_2A0], r15b
0x1800a32c4  setz    al
0x1800a32c7  mov     [rdi], al
0x1800a32c9  lea     rdx, aHostruntimeInd; "HostRuntime\\Index\\HostIdAndPackageExt"...
0x1800a32d0  lea     rcx, [rsp+2C0h+var_298]; this
0x1800a32d5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a32da  mov     ebx, eax
0x1800a32dc  test    eax, eax
0x1800a32de  jns     short loc_1800A32EA
0x1800a32e0  mov     edx, 7Dh ; '}'
0x1800a32e5  jmp     loc_1800A325E
0x1800a32ea  mov     rcx, [rsp+2C0h+var_290]
0x1800a32ef  mov     [rsp+2C0h+var_290], r15
0x1800a32f4  test    rcx, rcx
0x1800a32f7  jz      short loc_1800A32FF
0x1800a32f9  call    cs:__imp_SRCacheContext_Close
0x1800a32ff  mov     rcx, [rsp+2C0h+var_280]
0x1800a3304  mov     [rsp+2C0h+var_280], r15
0x1800a3309  test    rcx, rcx
0x1800a330c  jz      short loc_1800A3314
0x1800a330e  call    cs:__imp_SRCache_Free
0x1800a3314  mov     rcx, [rsp+2C0h+var_298]
0x1800a3319  mov     [rsp+2C0h+var_298], r15
0x1800a331e  test    rcx, rcx
0x1800a3321  jz      short loc_1800A3329
0x1800a3323  call    cs:__imp_SRCacheContext_Close
0x1800a3329  xor     eax, eax
0x1800a332b  mov     rcx, [rbp+1C0h+var_38]
0x1800a3332  xor     rcx, rsp; StackCookie
0x1800a3335  call    __security_check_cookie
0x1800a333a  add     rsp, 298h
0x1800a3341  pop     r15
0x1800a3343  pop     r14
0x1800a3345  pop     rdi
0x1800a3346  pop     rsi
0x1800a3347  pop     rbx
0x1800a3348  pop     rbp
0x1800a3349  retn
```
