# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1802b7e54`
- end: `0x1802b80fa`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1802b53fc`

## callees

- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d868`
- `0x1802b1bf4`
- `0x1802b2c38`
- `0x1802b2c78`
- `0x1802b7e54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7f9b`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802b7f9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b8042`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802b8042`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b800c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b80b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b800c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b80b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7f1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b80cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b7f1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b80cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7ebf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802b7ebf`

## string_xrefs

- `0x1802b7efe`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1802b7fea`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1802b7fac`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1802b7ede`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1802b8061`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+238h] [rbp+138h]
  __int64 v20; // [rsp+240h] [rbp+140h]
  _BYTE *v21; // [rsp+248h] [rbp+148h]
  wchar_t v22[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h] BYREF
  char v24; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v22 = v16;
  v24 = 1;
  *(_QWORD *)v16 = 0;
  v23 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 1193;
    goto LABEL_3;
  }
  memset_0(v18, 0, sizeof(v18));
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 256;
  v21 = v18;
  if ( (unsigned int)_o__ui64tow_s(a2, v22, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v16[0]);
LABEL_12:
    v12 = 1196;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v17, v22);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v22 = a3;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v21, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 1197;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Package\\Data");
  if ( v8 < 0 )
  {
    v12 = 1199;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v17;
    v17 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x1802b7e54  mov     [rsp-8+arg_10], rbx
0x1802b7e59  push    rbp
0x1802b7e5a  push    rsi
0x1802b7e5b  push    rdi
0x1802b7e5c  push    r14
0x1802b7e5e  push    r15
0x1802b7e60  lea     rbp, [rsp-180h]
0x1802b7e68  sub     rsp, 280h
0x1802b7e6f  mov     rax, cs:__security_cookie
0x1802b7e76  xor     rax, rsp
0x1802b7e79  mov     [rbp+1A0h+var_28], rax
0x1802b7e80  mov     rcx, [rcx]
0x1802b7e83  lea     rax, [rsp+2A0h+var_280]
0x1802b7e88  mov     rsi, r9
0x1802b7e8b  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802b7e92  mov     rdi, r8
0x1802b7e95  mov     [rbp+1A0h+var_40], 1
0x1802b7e9c  mov     r14, rdx
0x1802b7e9f  lea     r9, [rbp+1A0h+var_48]
0x1802b7ea6  xor     r15d, r15d
0x1802b7ea9  lea     rdx, aPackageData; "Package\\Data"
0x1802b7eb0  xor     r8d, r8d
0x1802b7eb3  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1802b7eb8  mov     [rbp+1A0h+var_48], r15
0x1802b7ebf  call    cs:__imp_SRCacheContext_Open
0x1802b7ec5  lea     rcx, [rbp+1A0h+var_50]
0x1802b7ecc  mov     ebx, eax
0x1802b7ece  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b7ed3  test    ebx, ebx
0x1802b7ed5  jns     short loc_1802B7F29
0x1802b7ed7  mov     rcx, [rbp+1A8h]; this
0x1802b7ede  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7ee5  mov     r9d, ebx; char *
0x1802b7ee8  mov     edx, 18Ch; void *
0x1802b7eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7ef2  mov     edx, 4A8h; void *
0x1802b7ef7  mov     rcx, [rbp+1A8h]; this
0x1802b7efe  lea     r8, aOnecoreInterna_23; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7f05  mov     r9d, ebx; char *
0x1802b7f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7f0d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b7f12  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b7f17  test    rcx, rcx
0x1802b7f1a  jz      short loc_1802B7F22
0x1802b7f1c  call    cs:__imp_SRCacheContext_Close
0x1802b7f22  mov     eax, ebx
0x1802b7f24  jmp     loc_1802B80D4
0x1802b7f29  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1802b7f2e  setnz   al
0x1802b7f31  test    al, al
0x1802b7f33  jnz     short loc_1802B7F41
0x1802b7f35  mov     ebx, 80670012h
0x1802b7f3a  mov     edx, 4A9h
0x1802b7f3f  jmp     short loc_1802B7EF7
0x1802b7f41  mov     ebx, 200h
0x1802b7f46  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7f4b  mov     r8d, ebx; Size
0x1802b7f4e  xor     edx, edx; Val
0x1802b7f50  call    memset_0
0x1802b7f55  mov     r8d, ebx; Size
0x1802b7f58  mov     [rsp+2A0h+var_270], r15
0x1802b7f5d  xor     edx, edx; Val
0x1802b7f5f  lea     rcx, [rsp+2A0h+var_268]; void *
0x1802b7f64  call    memset_0
0x1802b7f69  mov     r9d, 10h
0x1802b7f6f  mov     [rbp+1A0h+var_68], r15
0x1802b7f76  lea     rax, [rsp+2A0h+var_268]
0x1802b7f7b  mov     [rbp+1A0h+var_60], 100h
0x1802b7f86  lea     rdx, [rbp+1A0h+var_50]
0x1802b7f8d  mov     [rbp+1A0h+var_58], rax
0x1802b7f94  mov     rcx, r14
0x1802b7f97  lea     r8d, [r9+1]
0x1802b7f9b  call    cs:__imp__o__ui64tow_s
0x1802b7fa1  test    eax, eax
0x1802b7fa3  jz      short loc_1802B7FC7
0x1802b7fa5  mov     rcx, [rbp+1A8h]; this
0x1802b7fac  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7fb3  mov     ebx, 8000FFFFh
0x1802b7fb8  mov     edx, 166h; void *
0x1802b7fbd  mov     r9d, ebx; char *
0x1802b7fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7fc5  jmp     short loc_1802B7FDE
0x1802b7fc7  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x1802b7fce  lea     rcx, [rsp+2A0h+var_270]; this
0x1802b7fd3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x1802b7fd8  mov     ebx, eax
0x1802b7fda  test    eax, eax
0x1802b7fdc  jns     short loc_1802B8017
0x1802b7fde  mov     edx, 4ACh; void *
0x1802b7fe3  mov     rcx, [rbp+1A8h]; this
0x1802b7fea  lea     r8, aOnecoreInterna_23; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b7ff1  mov     r9d, ebx; char *
0x1802b7ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b7ff9  mov     rcx, [rsp+2A0h+var_270]
0x1802b7ffe  mov     [rsp+2A0h+var_270], r15
0x1802b8003  test    rcx, rcx
0x1802b8006  jz      loc_1802B7F0D
0x1802b800c  call    cs:__imp_SRCache_Free
0x1802b8012  jmp     loc_1802B7F0D
0x1802b8017  mov     rdx, [rbp+1A0h+var_58]
0x1802b801e  lea     r9, [rbp+1A0h+var_48]
0x1802b8025  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b802a  xor     r8d, r8d
0x1802b802d  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1802b8034  mov     [rbp+1A0h+var_48], r15
0x1802b803b  mov     [rbp+1A0h+var_40], 1
0x1802b8042  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802b8048  lea     rcx, [rbp+1A0h+var_50]
0x1802b804f  mov     ebx, eax
0x1802b8051  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802b8056  test    ebx, ebx
0x1802b8058  jns     short loc_1802B807F
0x1802b805a  mov     rcx, [rbp+1A8h]; this
0x1802b8061  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b8068  mov     r9d, ebx; char *
0x1802b806b  mov     edx, 1B0h; void *
0x1802b8070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b8075  mov     edx, 4ADh
0x1802b807a  jmp     loc_1802B7FE3
0x1802b807f  cmp     [rdi], r15
0x1802b8082  lea     rdx, aPackageData; "Package\\Data"
0x1802b8089  lea     rcx, [rsp+2A0h+var_280]; this
0x1802b808e  setnz   al
0x1802b8091  mov     [rsi], al
0x1802b8093  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802b8098  mov     ebx, eax
0x1802b809a  test    eax, eax
0x1802b809c  jns     short loc_1802B80A8
0x1802b809e  mov     edx, 4AFh
0x1802b80a3  jmp     loc_1802B7FE3
0x1802b80a8  mov     rcx, [rsp+2A0h+var_270]
0x1802b80ad  mov     [rsp+2A0h+var_270], r15
0x1802b80b2  test    rcx, rcx
0x1802b80b5  jz      short loc_1802B80BD
0x1802b80b7  call    cs:__imp_SRCache_Free
0x1802b80bd  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802b80c2  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802b80c7  test    rcx, rcx
0x1802b80ca  jz      short loc_1802B80D2
0x1802b80cc  call    cs:__imp_SRCacheContext_Close
0x1802b80d2  xor     eax, eax
0x1802b80d4  mov     rcx, [rbp+1A0h+var_28]
0x1802b80db  xor     rcx, rsp; StackCookie
0x1802b80de  call    __security_check_cookie
0x1802b80e3  mov     rbx, [rsp+2A0h+arg_10]
0x1802b80eb  add     rsp, 280h
0x1802b80f2  pop     r15
0x1802b80f4  pop     r14
0x1802b80f6  pop     rdi
0x1802b80f7  pop     rsi
0x1802b80f8  pop     rbp
0x1802b80f9  retn
```
