# StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByExtension(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18037b388`
- end: `0x18037b6c4`
- name: `?OpenByExtension@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `828`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18020b38c`

## callees

- `0x1800432f0`
- `0x1800a0e00`
- `0x18020b35c`
- `0x180291fc8`
- `0x18037b388`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18037b535`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18037b535`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18037b5dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18037b5dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b681`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b5a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18037b681`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b3f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b495`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b4e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b696`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b3f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b495`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b4e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18037b696`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18037b438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18037b438`

## string_xrefs

- `0x18037b546`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18037b3cc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18037b472`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18037b4b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18037b584`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18037b640`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18037b457`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18037b5fb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18037b414`: `Protocol\Index\Extension`
- `0x18037b622`: `Protocol\Index\Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByExtension(
        StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x242,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)0x80070057LL,
      v22[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)v28 = v22;
  *(_QWORD *)v22 = 0;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_Open(v9, L"Protocol\\Index\\Extension", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
LABEL_8:
    v12 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v11);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v22 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v14 = *(_QWORD *)v22;
    *(_QWORD *)v22 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v13);
    return v6;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 256;
  v27 = v24;
  if ( (unsigned int)_o__ui64tow_s(a3, v28, 17) )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v22[0]);
LABEL_18:
    v15 = 588;
    goto LABEL_19;
  }
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
  if ( v10 < 0 )
    goto LABEL_18;
  *(_QWORD *)v28 = this;
  v29 = 0;
  v30 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v22, v27, 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v28);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v15 = 591;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    v16 = v23;
    v23 = 0;
    if ( v16 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v22,
          L"Protocol\\Index\\Extension");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v17,
      v22[0]);
    v19 = v23;
    v23 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_13;
  }
  v20 = v23;
  v23 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = *(_QWORD *)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18);
  return 0;
}

```

## disassembly

```asm
0x18037b388  mov     [rsp-8+arg_18], rbx
0x18037b38d  push    rbp
0x18037b38e  push    rsi
0x18037b38f  push    rdi
0x18037b390  push    r14
0x18037b392  push    r15
0x18037b394  lea     rbp, [rsp-180h]
0x18037b39c  sub     rsp, 280h
0x18037b3a3  mov     rax, cs:__security_cookie
0x18037b3aa  xor     rax, rsp
0x18037b3ad  mov     [rbp+1A0h+var_28], rax
0x18037b3b4  xor     r15d, r15d
0x18037b3b7  mov     r14, r8
0x18037b3ba  mov     rsi, rdx
0x18037b3bd  mov     rbx, rcx
0x18037b3c0  test    r8, r8
0x18037b3c3  jnz     short loc_18037B3EC
0x18037b3c5  mov     rcx, [rbp+1A8h]; this
0x18037b3cc  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b3d3  mov     ebx, 80070057h
0x18037b3d8  mov     edx, 242h; void *
0x18037b3dd  mov     r9d, ebx; char *
0x18037b3e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b3e5  mov     eax, ebx
0x18037b3e7  jmp     loc_18037B69E
0x18037b3ec  mov     rcx, [rcx]
0x18037b3ef  mov     [rbx], r15
0x18037b3f2  test    rcx, rcx
0x18037b3f5  jz      short loc_18037B3FD
0x18037b3f7  call    cs:__imp_SRCacheContext_Close
0x18037b3fd  mov     [rbx+8], r15d
0x18037b401  lea     rax, [rsp+2A0h+var_280]
0x18037b406  mov     [rbx+10h], r15
0x18037b40a  lea     r9, [rbp+1A0h+var_48]
0x18037b411  mov     rcx, [rsi]
0x18037b414  lea     rdx, aProtocolIndexE; "Protocol\\Index\\Extension"
0x18037b41b  xor     r8d, r8d
0x18037b41e  mov     qword ptr [rbp+1A0h+var_50], rax
0x18037b425  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18037b42a  mov     [rbp+1A0h+var_48], r15
0x18037b431  mov     [rbp+1A0h+var_40], 1
0x18037b438  call    cs:__imp_SRCacheContext_Open
0x18037b43e  lea     rcx, [rbp+1A0h+var_50]
0x18037b445  mov     edi, eax
0x18037b447  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18037b44c  test    edi, edi
0x18037b44e  jns     short loc_18037B4A2
0x18037b450  mov     rcx, [rbp+1A8h]; this
0x18037b457  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b45e  mov     r9d, edi; char *
0x18037b461  mov     edx, 18Ch; void *
0x18037b466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b46b  mov     rcx, [rbp+1A8h]; this
0x18037b472  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b479  mov     r9d, edi; char *
0x18037b47c  mov     edx, 248h; void *
0x18037b481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b486  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18037b48b  mov     qword ptr [rsp+2A0h+var_280], r15
0x18037b490  test    rcx, rcx
0x18037b493  jz      short loc_18037B49B
0x18037b495  call    cs:__imp_SRCacheContext_Close
0x18037b49b  mov     eax, edi
0x18037b49d  jmp     loc_18037B69E
0x18037b4a2  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18037b4a7  setnz   al
0x18037b4aa  test    al, al
0x18037b4ac  jnz     short loc_18037B4EC
0x18037b4ae  mov     rcx, [rbp+1A8h]; this
0x18037b4b5  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b4bc  mov     ebx, 80670012h
0x18037b4c1  mov     edx, 249h; void *
0x18037b4c6  mov     r9d, ebx; char *
0x18037b4c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b4ce  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18037b4d3  mov     qword ptr [rsp+2A0h+var_280], r15
0x18037b4d8  test    rcx, rcx
0x18037b4db  jz      loc_18037B3E5
0x18037b4e1  call    cs:__imp_SRCacheContext_Close
0x18037b4e7  jmp     loc_18037B3E5
0x18037b4ec  xor     edx, edx; Val
0x18037b4ee  mov     [rsp+2A0h+var_270], r15
0x18037b4f3  mov     r8d, 200h; Size
0x18037b4f9  lea     rcx, [rsp+2A0h+var_268]; void *
0x18037b4fe  call    memset_0
0x18037b503  mov     r9d, 10h
0x18037b509  mov     [rbp+1A0h+var_68], r15
0x18037b510  lea     rax, [rsp+2A0h+var_268]
0x18037b515  mov     [rbp+1A0h+var_60], 100h
0x18037b520  lea     rdx, [rbp+1A0h+var_50]
0x18037b527  mov     [rbp+1A0h+var_58], rax
0x18037b52e  mov     rcx, r14
0x18037b531  lea     r8d, [r9+1]
0x18037b535  call    cs:__imp__o__ui64tow_s
0x18037b53b  test    eax, eax
0x18037b53d  jz      short loc_18037B561
0x18037b53f  mov     rcx, [rbp+1A8h]; this
0x18037b546  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b54d  mov     edi, 8000FFFFh
0x18037b552  mov     edx, 166h; void *
0x18037b557  mov     r9d, edi; char *
0x18037b55a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b55f  jmp     short loc_18037B578
0x18037b561  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18037b568  lea     rcx, [rsp+2A0h+var_270]; this
0x18037b56d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18037b572  mov     edi, eax
0x18037b574  test    eax, eax
0x18037b576  jns     short loc_18037B5B1
0x18037b578  mov     edx, 24Ch; void *
0x18037b57d  mov     rcx, [rbp+1A8h]; this
0x18037b584  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b58b  mov     r9d, edi; char *
0x18037b58e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b593  mov     rcx, [rsp+2A0h+var_270]
0x18037b598  mov     [rsp+2A0h+var_270], r15
0x18037b59d  test    rcx, rcx
0x18037b5a0  jz      loc_18037B486
0x18037b5a6  call    cs:__imp_SRCache_Free
0x18037b5ac  jmp     loc_18037B486
0x18037b5b1  mov     rdx, [rbp+1A0h+var_58]
0x18037b5b8  lea     r9, [rbp+1A0h+var_48]
0x18037b5bf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18037b5c4  xor     r8d, r8d
0x18037b5c7  mov     qword ptr [rbp+1A0h+var_50], rbx
0x18037b5ce  mov     [rbp+1A0h+var_48], r15
0x18037b5d5  mov     [rbp+1A0h+var_40], 1
0x18037b5dc  call    cs:__imp_SRCacheContext_OpenSubContext
0x18037b5e2  lea     rcx, [rbp+1A0h+var_50]
0x18037b5e9  mov     edi, eax
0x18037b5eb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18037b5f0  test    edi, edi
0x18037b5f2  jns     short loc_18037B619
0x18037b5f4  mov     rcx, [rbp+1A8h]; this
0x18037b5fb  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b602  mov     r9d, edi; char *
0x18037b605  mov     edx, 1B0h; void *
0x18037b60a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b60f  mov     edx, 24Fh
0x18037b614  jmp     loc_18037B57D
0x18037b619  cmp     [rbx], r15
0x18037b61c  jz      short loc_18037B622
0x18037b61e  mov     [rbx+10h], rsi
0x18037b622  lea     rdx, aProtocolIndexE; "Protocol\\Index\\Extension"
0x18037b629  lea     rcx, [rsp+2A0h+var_280]; this
0x18037b62e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18037b633  mov     ebx, eax
0x18037b635  test    eax, eax
0x18037b637  jns     short loc_18037B672
0x18037b639  mov     rcx, [rbp+1A8h]; this
0x18037b640  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18037b647  mov     r9d, eax; char *
0x18037b64a  mov     edx, 255h; void *
0x18037b64f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037b654  mov     rcx, [rsp+2A0h+var_270]
0x18037b659  mov     [rsp+2A0h+var_270], r15
0x18037b65e  test    rcx, rcx
0x18037b661  jz      loc_18037B4CE
0x18037b667  call    cs:__imp_SRCache_Free
0x18037b66d  jmp     loc_18037B4CE
0x18037b672  mov     rcx, [rsp+2A0h+var_270]
0x18037b677  mov     [rsp+2A0h+var_270], r15
0x18037b67c  test    rcx, rcx
0x18037b67f  jz      short loc_18037B687
0x18037b681  call    cs:__imp_SRCache_Free
0x18037b687  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18037b68c  mov     qword ptr [rsp+2A0h+var_280], r15
0x18037b691  test    rcx, rcx
0x18037b694  jz      short loc_18037B69C
0x18037b696  call    cs:__imp_SRCacheContext_Close
0x18037b69c  xor     eax, eax
0x18037b69e  mov     rcx, [rbp+1A0h+var_28]
0x18037b6a5  xor     rcx, rsp; StackCookie
0x18037b6a8  call    __security_check_cookie
0x18037b6ad  mov     rbx, [rsp+2A0h+arg_18]
0x18037b6b5  add     rsp, 280h
0x18037b6bc  pop     r15
0x18037b6be  pop     r14
0x18037b6c0  pop     rdi
0x18037b6c1  pop     rsi
0x18037b6c2  pop     rbp
0x18037b6c3  retn
```
