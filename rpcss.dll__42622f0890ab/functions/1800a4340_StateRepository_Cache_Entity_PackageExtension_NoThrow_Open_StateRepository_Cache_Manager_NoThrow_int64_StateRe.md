# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800a4340`
- end: `0x1800a45d5`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800cd4e0`

## callees

- `0x1800211f0`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x1800a4340`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a4476`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800a4476`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4408`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a45a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a4408`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a45a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a43ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800a43ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a44e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4592`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a44e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800a4592`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a451d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800a451d`

## string_xrefs

- `0x1800a4487`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800a43ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a453c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800a4395`: `PackageExtension\Data`
- `0x1800a455d`: `PackageExtension\Data`
- `0x1800a43ea`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800a44c5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageExtension\\Data", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
    v9 = 318;
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
    v13 = 321;
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
    v13 = 322;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 324;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
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
0x1800a4340  mov     [rsp-8+arg_10], rbx
0x1800a4345  push    rbp
0x1800a4346  push    rsi
0x1800a4347  push    rdi
0x1800a4348  push    r14
0x1800a434a  push    r15
0x1800a434c  lea     rbp, [rsp-180h]
0x1800a4354  sub     rsp, 280h
0x1800a435b  mov     rax, cs:__security_cookie
0x1800a4362  xor     rax, rsp
0x1800a4365  mov     [rbp+1A0h+var_28], rax
0x1800a436c  mov     rcx, [rcx]
0x1800a436f  lea     rax, [rsp+2A0h+var_280]
0x1800a4374  mov     rsi, r9
0x1800a4377  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800a437e  mov     rdi, r8
0x1800a4381  mov     [rbp+1A0h+var_40], 1
0x1800a4388  mov     r14, rdx
0x1800a438b  lea     r9, [rbp+1A0h+var_48]
0x1800a4392  xor     r15d, r15d
0x1800a4395  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x1800a439c  xor     r8d, r8d
0x1800a439f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800a43a4  mov     [rbp+1A0h+var_48], r15
0x1800a43ab  call    cs:__imp_SRCacheContext_Open
0x1800a43b1  lea     rcx, [rbp+1A0h+var_50]
0x1800a43b8  mov     ebx, eax
0x1800a43ba  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a43bf  test    ebx, ebx
0x1800a43c1  jns     short loc_1800A4415
0x1800a43c3  mov     rcx, [rbp+1A8h]; this
0x1800a43ca  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a43d1  mov     r9d, ebx; char *
0x1800a43d4  mov     edx, 18Ch; void *
0x1800a43d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a43de  mov     edx, 13Dh; void *
0x1800a43e3  mov     rcx, [rbp+1A8h]; this
0x1800a43ea  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a43f1  mov     r9d, ebx; char *
0x1800a43f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a43f9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a43fe  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a4403  test    rcx, rcx
0x1800a4406  jz      short loc_1800A440E
0x1800a4408  call    cs:__imp_SRCacheContext_Close
0x1800a440e  mov     eax, ebx
0x1800a4410  jmp     loc_1800A45AF
0x1800a4415  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800a441a  setnz   al
0x1800a441d  test    al, al
0x1800a441f  jnz     short loc_1800A442D
0x1800a4421  mov     ebx, 80670012h
0x1800a4426  mov     edx, 13Eh
0x1800a442b  jmp     short loc_1800A43E3
0x1800a442d  xor     edx, edx; Val
0x1800a442f  mov     [rsp+2A0h+var_270], r15
0x1800a4434  mov     r8d, 200h; Size
0x1800a443a  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800a443f  call    memset_0
0x1800a4444  mov     r9d, 10h
0x1800a444a  mov     [rbp+1A0h+var_68], r15
0x1800a4451  lea     rax, [rsp+2A0h+var_268]
0x1800a4456  mov     [rbp+1A0h+var_60], 100h
0x1800a4461  lea     rdx, [rbp+1A0h+var_50]
0x1800a4468  mov     [rbp+1A0h+var_58], rax
0x1800a446f  mov     rcx, r14
0x1800a4472  lea     r8d, [r9+1]
0x1800a4476  call    cs:__imp__o__ui64tow_s
0x1800a447c  test    eax, eax
0x1800a447e  jz      short loc_1800A44A2
0x1800a4480  mov     rcx, [rbp+1A8h]; this
0x1800a4487  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a448e  mov     ebx, 8000FFFFh
0x1800a4493  mov     edx, 166h; void *
0x1800a4498  mov     r9d, ebx; char *
0x1800a449b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a44a0  jmp     short loc_1800A44B9
0x1800a44a2  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800a44a9  lea     rcx, [rsp+2A0h+var_270]; this
0x1800a44ae  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800a44b3  mov     ebx, eax
0x1800a44b5  test    eax, eax
0x1800a44b7  jns     short loc_1800A44F2
0x1800a44b9  mov     edx, 141h; void *
0x1800a44be  mov     rcx, [rbp+1A8h]; this
0x1800a44c5  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a44cc  mov     r9d, ebx; char *
0x1800a44cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a44d4  mov     rcx, [rsp+2A0h+var_270]
0x1800a44d9  mov     [rsp+2A0h+var_270], r15
0x1800a44de  test    rcx, rcx
0x1800a44e1  jz      loc_1800A43F9
0x1800a44e7  call    cs:__imp_SRCache_Free
0x1800a44ed  jmp     loc_1800A43F9
0x1800a44f2  mov     rdx, [rbp+1A0h+var_58]
0x1800a44f9  lea     r9, [rbp+1A0h+var_48]
0x1800a4500  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a4505  xor     r8d, r8d
0x1800a4508  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1800a450f  mov     [rbp+1A0h+var_48], r15
0x1800a4516  mov     [rbp+1A0h+var_40], 1
0x1800a451d  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800a4523  lea     rcx, [rbp+1A0h+var_50]
0x1800a452a  mov     ebx, eax
0x1800a452c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a4531  test    ebx, ebx
0x1800a4533  jns     short loc_1800A455A
0x1800a4535  mov     rcx, [rbp+1A8h]; this
0x1800a453c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a4543  mov     r9d, ebx; char *
0x1800a4546  mov     edx, 1B0h; void *
0x1800a454b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4550  mov     edx, 142h
0x1800a4555  jmp     loc_1800A44BE
0x1800a455a  cmp     [rdi], r15
0x1800a455d  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x1800a4564  lea     rcx, [rsp+2A0h+var_280]; this
0x1800a4569  setnz   al
0x1800a456c  mov     [rsi], al
0x1800a456e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a4573  mov     ebx, eax
0x1800a4575  test    eax, eax
0x1800a4577  jns     short loc_1800A4583
0x1800a4579  mov     edx, 144h
0x1800a457e  jmp     loc_1800A44BE
0x1800a4583  mov     rcx, [rsp+2A0h+var_270]
0x1800a4588  mov     [rsp+2A0h+var_270], r15
0x1800a458d  test    rcx, rcx
0x1800a4590  jz      short loc_1800A4598
0x1800a4592  call    cs:__imp_SRCache_Free
0x1800a4598  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800a459d  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800a45a2  test    rcx, rcx
0x1800a45a5  jz      short loc_1800A45AD
0x1800a45a7  call    cs:__imp_SRCacheContext_Close
0x1800a45ad  xor     eax, eax
0x1800a45af  mov     rcx, [rbp+1A0h+var_28]
0x1800a45b6  xor     rcx, rsp; StackCookie
0x1800a45b9  call    __security_check_cookie
0x1800a45be  mov     rbx, [rsp+2A0h+arg_10]
0x1800a45c6  add     rsp, 280h
0x1800a45cd  pop     r15
0x1800a45cf  pop     r14
0x1800a45d1  pop     rdi
0x1800a45d2  pop     rsi
0x1800a45d3  pop     rbp
0x1800a45d4  retn
```
