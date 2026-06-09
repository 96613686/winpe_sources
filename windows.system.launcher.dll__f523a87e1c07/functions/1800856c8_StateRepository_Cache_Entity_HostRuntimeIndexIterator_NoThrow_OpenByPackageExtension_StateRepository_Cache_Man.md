# StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::OpenByPackageExtension(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1800856c8`
- end: `0x1800859ac`
- name: `?OpenByPackageExtension@HostRuntimeIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `740`
- prototype: `int(StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18007bbe8`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x1800856c8`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180085898`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008594f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180085969`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180085898`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008594f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180085969`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180085737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800857cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180085817`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008597e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180085737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800857cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180085817`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008597e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800858c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800858c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180085770`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180085770`

## string_xrefs

- `0x18008578d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800858e3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18008570c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800857a8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x1800857eb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x180085876`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x180085928`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-HostRuntime.hpp`
- `0x180085752`: `HostRuntime\Index\PackageExtension`
- `0x18008590a`: `HostRuntime\Index\PackageExtension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow::OpenByPackageExtension(
        StateRepository::Cache::Entity::HostRuntimeIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)0x80070057LL,
      v19[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v20 = v19;
  *(_QWORD *)v19 = 0;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_Open(v9, L"HostRuntime\\Index\\PackageExtension", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
LABEL_8:
    v11 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v19 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v12 = *(_QWORD *)v19;
    *(_QWORD *)v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
  if ( v10 < 0 )
  {
    v13 = 532;
    goto LABEL_17;
  }
  v20 = (int *)this;
  v21 = 0;
  v22 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v19, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v13 = 535;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v15 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v19,
          L"HostRuntime\\Index\\PackageExtension");
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v15,
      v19[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_13;
  }
  v17 = v23;
  v23 = 0;
  if ( v17 )
    SRCache_Free(v17);
  v18 = *(_QWORD *)v19;
  *(_QWORD *)v19 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x1800856c8  mov     [rsp-8+arg_18], rbx
0x1800856cd  push    rbp
0x1800856ce  push    rsi
0x1800856cf  push    rdi
0x1800856d0  push    r14
0x1800856d2  push    r15
0x1800856d4  lea     rbp, [rsp-170h]
0x1800856dc  sub     rsp, 270h
0x1800856e3  mov     rax, cs:__security_cookie
0x1800856ea  xor     rax, rsp
0x1800856ed  mov     [rbp+190h+var_30], rax
0x1800856f4  xor     r15d, r15d
0x1800856f7  mov     r14, r8
0x1800856fa  mov     rsi, rdx
0x1800856fd  mov     rbx, rcx
0x180085700  test    r8, r8
0x180085703  jnz     short loc_18008572C
0x180085705  mov     rcx, [rbp+198h]; this
0x18008570c  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x180085713  mov     ebx, 80070057h
0x180085718  mov     edx, 20Ah; void *
0x18008571d  mov     r9d, ebx; char *
0x180085720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085725  mov     eax, ebx
0x180085727  jmp     loc_180085986
0x18008572c  mov     rcx, [rcx]
0x18008572f  mov     [rbx], r15
0x180085732  test    rcx, rcx
0x180085735  jz      short loc_18008573D
0x180085737  call    cs:__imp_SRCacheContext_Close
0x18008573d  mov     [rbx+8], r15d
0x180085741  lea     rax, [rsp+290h+var_270]
0x180085746  mov     [rbx+10h], r15
0x18008574a  lea     r9, [rsp+290h+var_260]
0x18008574f  mov     rcx, [rsi]
0x180085752  lea     rdx, aHostruntimeInd; "HostRuntime\\Index\\PackageExtension"
0x180085759  xor     r8d, r8d
0x18008575c  mov     [rsp+290h+var_268], rax
0x180085761  mov     qword ptr [rsp+290h+var_270], r15; int
0x180085766  mov     [rsp+290h+var_260], r15
0x18008576b  mov     [rsp+290h+var_258], 1
0x180085770  call    cs:__imp_SRCacheContext_Open
0x180085776  lea     rcx, [rsp+290h+var_268]
0x18008577b  mov     edi, eax
0x18008577d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180085782  test    edi, edi
0x180085784  jns     short loc_1800857D8
0x180085786  mov     rcx, [rbp+198h]; this
0x18008578d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180085794  mov     r9d, edi; char *
0x180085797  mov     edx, 18Ch; void *
0x18008579c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857a1  mov     rcx, [rbp+198h]; this
0x1800857a8  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800857af  mov     r9d, edi; char *
0x1800857b2  mov     edx, 210h; void *
0x1800857b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857bc  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800857c1  mov     qword ptr [rsp+290h+var_270], r15
0x1800857c6  test    rcx, rcx
0x1800857c9  jz      short loc_1800857D1
0x1800857cb  call    cs:__imp_SRCacheContext_Close
0x1800857d1  mov     eax, edi
0x1800857d3  jmp     loc_180085986
0x1800857d8  cmp     qword ptr [rsp+290h+var_270], r15
0x1800857dd  setnz   al
0x1800857e0  test    al, al
0x1800857e2  jnz     short loc_180085822
0x1800857e4  mov     rcx, [rbp+198h]; this
0x1800857eb  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800857f2  mov     ebx, 80670012h
0x1800857f7  mov     edx, 211h; void *
0x1800857fc  mov     r9d, ebx; char *
0x1800857ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085804  mov     rcx, qword ptr [rsp+290h+var_270]
0x180085809  mov     qword ptr [rsp+290h+var_270], r15
0x18008580e  test    rcx, rcx
0x180085811  jz      loc_180085725
0x180085817  call    cs:__imp_SRCacheContext_Close
0x18008581d  jmp     loc_180085725
0x180085822  xor     edx, edx; Val
0x180085824  mov     [rsp+290h+var_250], r15
0x180085829  mov     r8d, 200h; Size
0x18008582f  lea     rcx, [rsp+290h+var_248]; void *
0x180085834  call    memset_0
0x180085839  lea     rax, [rsp+290h+var_248]
0x18008583e  mov     [rbp+190h+var_48], r15
0x180085845  mov     rdx, r14; unsigned __int64
0x180085848  mov     [rbp+190h+var_38], rax
0x18008584f  lea     rcx, [rsp+290h+var_250]; this
0x180085854  mov     [rbp+190h+var_40], 100h
0x18008585f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180085864  mov     edi, eax
0x180085866  test    eax, eax
0x180085868  jns     short loc_1800858A3
0x18008586a  mov     edx, 214h; void *
0x18008586f  mov     rcx, [rbp+198h]; this
0x180085876  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008587d  mov     r9d, edi; char *
0x180085880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085885  mov     rcx, [rsp+290h+var_250]
0x18008588a  mov     [rsp+290h+var_250], r15
0x18008588f  test    rcx, rcx
0x180085892  jz      loc_1800857BC
0x180085898  call    cs:__imp_SRCache_Free
0x18008589e  jmp     loc_1800857BC
0x1800858a3  mov     rdx, [rbp+190h+var_38]
0x1800858aa  lea     r9, [rsp+290h+var_260]
0x1800858af  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800858b4  xor     r8d, r8d
0x1800858b7  mov     [rsp+290h+var_268], rbx
0x1800858bc  mov     [rsp+290h+var_260], r15
0x1800858c1  mov     [rsp+290h+var_258], 1
0x1800858c6  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800858cc  lea     rcx, [rsp+290h+var_268]
0x1800858d1  mov     edi, eax
0x1800858d3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800858d8  test    edi, edi
0x1800858da  jns     short loc_180085901
0x1800858dc  mov     rcx, [rbp+198h]; this
0x1800858e3  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800858ea  mov     r9d, edi; char *
0x1800858ed  mov     edx, 1B0h; void *
0x1800858f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800858f7  mov     edx, 217h
0x1800858fc  jmp     loc_18008586F
0x180085901  cmp     [rbx], r15
0x180085904  jz      short loc_18008590A
0x180085906  mov     [rbx+10h], rsi
0x18008590a  lea     rdx, aHostruntimeInd; "HostRuntime\\Index\\PackageExtension"
0x180085911  lea     rcx, [rsp+290h+var_270]; this
0x180085916  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008591b  mov     ebx, eax
0x18008591d  test    eax, eax
0x18008591f  jns     short loc_18008595A
0x180085921  mov     rcx, [rbp+198h]; this
0x180085928  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008592f  mov     r9d, eax; char *
0x180085932  mov     edx, 21Dh; void *
0x180085937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008593c  mov     rcx, [rsp+290h+var_250]
0x180085941  mov     [rsp+290h+var_250], r15
0x180085946  test    rcx, rcx
0x180085949  jz      loc_180085804
0x18008594f  call    cs:__imp_SRCache_Free
0x180085955  jmp     loc_180085804
0x18008595a  mov     rcx, [rsp+290h+var_250]
0x18008595f  mov     [rsp+290h+var_250], r15
0x180085964  test    rcx, rcx
0x180085967  jz      short loc_18008596F
0x180085969  call    cs:__imp_SRCache_Free
0x18008596f  mov     rcx, qword ptr [rsp+290h+var_270]
0x180085974  mov     qword ptr [rsp+290h+var_270], r15
0x180085979  test    rcx, rcx
0x18008597c  jz      short loc_180085984
0x18008597e  call    cs:__imp_SRCacheContext_Close
0x180085984  xor     eax, eax
0x180085986  mov     rcx, [rbp+190h+var_30]
0x18008598d  xor     rcx, rsp; StackCookie
0x180085990  call    __security_check_cookie
0x180085995  mov     rbx, [rsp+290h+arg_18]
0x18008599d  add     rsp, 270h
0x1800859a4  pop     r15
0x1800859a6  pop     r14
0x1800859a8  pop     rdi
0x1800859a9  pop     rsi
0x1800859aa  pop     rbp
0x1800859ab  retn
```
