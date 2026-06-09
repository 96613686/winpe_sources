# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180078268`
- end: `0x1800784a5`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180070e58`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x180010c04`
- `0x180030640`
- `0x180078268`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800783c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078462`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800783c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078462`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078477`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180078477`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800783ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800783ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800782cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800782cb`

## string_xrefs

- `0x1800782e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18007840c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180078308`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18007839f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
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
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
    v9 = 392;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 395;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 396;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v12 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x180078268  mov     [rsp-8+arg_10], rbx
0x18007826d  push    rbp
0x18007826e  push    rsi
0x18007826f  push    rdi
0x180078270  push    r14
0x180078272  push    r15
0x180078274  lea     rbp, [rsp-170h]
0x18007827c  sub     rsp, 270h
0x180078283  mov     rax, cs:__security_cookie
0x18007828a  xor     rax, rsp
0x18007828d  mov     [rbp+190h+var_30], rax
0x180078294  mov     rcx, [rcx]
0x180078297  lea     rax, [rsp+290h+var_270]
0x18007829c  mov     rsi, r9
0x18007829f  mov     [rsp+290h+var_268], rax
0x1800782a4  mov     rdi, r8
0x1800782a7  mov     [rsp+290h+var_258], 1
0x1800782ac  mov     r14, rdx
0x1800782af  lea     r9, [rsp+290h+var_260]
0x1800782b4  xor     r15d, r15d
0x1800782b7  lea     rdx, aActivationData; "Activation\\Data"
0x1800782be  xor     r8d, r8d
0x1800782c1  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800782c6  mov     [rsp+290h+var_260], r15
0x1800782cb  call    cs:__imp_SRCacheContext_Open
0x1800782d1  lea     rcx, [rsp+290h+var_268]
0x1800782d6  mov     ebx, eax
0x1800782d8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800782dd  test    ebx, ebx
0x1800782df  jns     short loc_180078333
0x1800782e1  mov     rcx, [rbp+198h]; this
0x1800782e8  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800782ef  mov     r9d, ebx; char *
0x1800782f2  mov     edx, 18Ch; void *
0x1800782f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800782fc  mov     edx, 187h; void *
0x180078301  mov     rcx, [rbp+198h]; this
0x180078308  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007830f  mov     r9d, ebx; char *
0x180078312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078317  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007831c  mov     qword ptr [rsp+290h+var_270], r15
0x180078321  test    rcx, rcx
0x180078324  jz      short loc_18007832C
0x180078326  call    cs:__imp_SRCacheContext_Close
0x18007832c  mov     eax, ebx
0x18007832e  jmp     loc_18007847F
0x180078333  cmp     qword ptr [rsp+290h+var_270], r15
0x180078338  setnz   al
0x18007833b  test    al, al
0x18007833d  jnz     short loc_18007834B
0x18007833f  mov     ebx, 80670012h
0x180078344  mov     edx, 188h
0x180078349  jmp     short loc_180078301
0x18007834b  xor     edx, edx; Val
0x18007834d  mov     [rsp+290h+var_250], r15
0x180078352  mov     r8d, 200h; Size
0x180078358  lea     rcx, [rsp+290h+var_248]; void *
0x18007835d  call    memset_0
0x180078362  lea     rax, [rsp+290h+var_248]
0x180078367  mov     [rbp+190h+var_48], r15
0x18007836e  mov     rdx, r14; unsigned __int64
0x180078371  mov     [rbp+190h+var_38], rax
0x180078378  lea     rcx, [rsp+290h+var_250]; this
0x18007837d  mov     [rbp+190h+var_40], 100h
0x180078388  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18007838d  mov     ebx, eax
0x18007838f  test    eax, eax
0x180078391  jns     short loc_1800783CC
0x180078393  mov     edx, 18Bh; void *
0x180078398  mov     rcx, [rbp+198h]; this
0x18007839f  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800783a6  mov     r9d, ebx; char *
0x1800783a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800783ae  mov     rcx, [rsp+290h+var_250]
0x1800783b3  mov     [rsp+290h+var_250], r15
0x1800783b8  test    rcx, rcx
0x1800783bb  jz      loc_180078317
0x1800783c1  call    cs:__imp_SRCache_Free
0x1800783c7  jmp     loc_180078317
0x1800783cc  mov     rdx, [rbp+190h+var_38]
0x1800783d3  lea     r9, [rsp+290h+var_260]
0x1800783d8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800783dd  xor     r8d, r8d
0x1800783e0  mov     [rsp+290h+var_268], rdi
0x1800783e5  mov     [rsp+290h+var_260], r15
0x1800783ea  mov     [rsp+290h+var_258], 1
0x1800783ef  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800783f5  lea     rcx, [rsp+290h+var_268]
0x1800783fa  mov     ebx, eax
0x1800783fc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180078401  test    ebx, ebx
0x180078403  jns     short loc_18007842A
0x180078405  mov     rcx, [rbp+198h]; this
0x18007840c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078413  mov     r9d, ebx; char *
0x180078416  mov     edx, 1B0h; void *
0x18007841b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078420  mov     edx, 18Ch
0x180078425  jmp     loc_180078398
0x18007842a  cmp     [rdi], r15
0x18007842d  lea     rdx, aActivationData; "Activation\\Data"
0x180078434  lea     rcx, [rsp+290h+var_270]; this
0x180078439  setnz   al
0x18007843c  mov     [rsi], al
0x18007843e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180078443  mov     ebx, eax
0x180078445  test    eax, eax
0x180078447  jns     short loc_180078453
0x180078449  mov     edx, 18Eh
0x18007844e  jmp     loc_180078398
0x180078453  mov     rcx, [rsp+290h+var_250]
0x180078458  mov     [rsp+290h+var_250], r15
0x18007845d  test    rcx, rcx
0x180078460  jz      short loc_180078468
0x180078462  call    cs:__imp_SRCache_Free
0x180078468  mov     rcx, qword ptr [rsp+290h+var_270]
0x18007846d  mov     qword ptr [rsp+290h+var_270], r15
0x180078472  test    rcx, rcx
0x180078475  jz      short loc_18007847D
0x180078477  call    cs:__imp_SRCacheContext_Close
0x18007847d  xor     eax, eax
0x18007847f  mov     rcx, [rbp+190h+var_30]
0x180078486  xor     rcx, rsp; StackCookie
0x180078489  call    __security_check_cookie
0x18007848e  mov     rbx, [rsp+290h+arg_10]
0x180078496  add     rsp, 270h
0x18007849d  pop     r15
0x18007849f  pop     r14
0x1800784a1  pop     rdi
0x1800784a2  pop     rsi
0x1800784a3  pop     rbp
0x1800784a4  retn
```
