# StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x18000d2f4`
- end: `0x18000d605`
- name: `?OpenByProgID@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `785`
- prototype: `int(StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c350`
- `0x18000c398`

## callees

- `0x18000d2f4`
- `0x1800103b0`
- `0x180010c04`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d558`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d558`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d394`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d445`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d49c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d56d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d394`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d445`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d49c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000d56d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000d421`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000d421`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000d370`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000d370`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000d468`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000d468`

## string_xrefs

- `0x18000d352`: `Protocol\Index\ProgID`
- `0x18000d461`: `Protocol\Index\ProgID`
- `0x18000d51a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000d581`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000d5de`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000d4d6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000d535`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000d59c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000d5bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByProgID(
        StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_Open(v7, L"Protocol\\Index\\ProgID", 0, &v23);
  if ( v24 )
  {
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
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
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x298,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    if ( !*(_QWORD *)v21 )
    {
      v12 = -2140733422;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
        (const char *)0x80670012LL,
        0);
LABEL_29:
      v20 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      if ( v20 )
        SRCacheContext_Close(v20);
      return v12;
    }
    v25 = 0;
    memset_0(v26, 0, sizeof(v26));
    v27 = 0;
    v29 = v26;
    v28 = 256;
    v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
    if ( v8 < 0 )
    {
      v16 = 668;
    }
    else
    {
      v22 = (int *)this;
      v23 = 0;
      v24 = 1;
      v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
      if ( v24 )
      {
        v10 = *(_QWORD *)v22;
        *(_QWORD *)v22 = v23;
        if ( v10 )
          SRCacheContext_Close(v10);
      }
      if ( v8 >= 0 )
      {
        if ( *(_QWORD *)this )
          *((_QWORD *)this + 2) = a2;
        v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Protocol\\Index\\ProgID");
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = v25;
          v25 = 0;
          if ( v13 )
            SRCache_Free(v13);
          v14 = *(_QWORD *)v21;
          *(_QWORD *)v21 = 0;
          if ( v14 )
            SRCacheContext_Close(v14);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v11,
          v21[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A5,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
          (const char *)v12,
          v21[0]);
        v19 = v25;
        v25 = 0;
        if ( v19 )
          SRCache_Free(v19);
        goto LABEL_29;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v21[0]);
      v16 = 671;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    v17 = v25;
    v25 = 0;
    if ( v17 )
      SRCache_Free(v17);
  }
  v18 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d2f4  mov     [rsp-8+arg_18], rbx
0x18000d2f9  push    rbp
0x18000d2fa  push    rsi
0x18000d2fb  push    rdi
0x18000d2fc  push    r14
0x18000d2fe  push    r15
0x18000d300  lea     rbp, [rsp-170h]
0x18000d308  sub     rsp, 270h
0x18000d30f  mov     rax, cs:__security_cookie
0x18000d316  xor     rax, rsp
0x18000d319  mov     [rbp+190h+var_30], rax
0x18000d320  mov     rbx, rcx
0x18000d323  xor     r15d, r15d
0x18000d326  mov     rcx, [rcx]
0x18000d329  mov     r14, r8
0x18000d32c  mov     rsi, rdx
0x18000d32f  mov     [rbx], r15
0x18000d332  test    rcx, rcx
0x18000d335  jz      short loc_18000D33D
0x18000d337  call    cs:__imp_SRCacheContext_Close
0x18000d33d  mov     [rbx+8], r15d
0x18000d341  lea     rax, [rsp+290h+var_270]
0x18000d346  mov     [rbx+10h], r15
0x18000d34a  lea     r9, [rsp+290h+var_260]
0x18000d34f  mov     rcx, [rsi]
0x18000d352  lea     rdx, aProtocolIndexP; "Protocol\\Index\\ProgID"
0x18000d359  xor     r8d, r8d
0x18000d35c  mov     [rsp+290h+var_268], rax
0x18000d361  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000d366  mov     [rsp+290h+var_260], r15
0x18000d36b  mov     [rsp+290h+var_258], 1
0x18000d370  call    cs:__imp_SRCacheContext_Open
0x18000d376  mov     edi, eax
0x18000d378  cmp     [rsp+290h+var_258], r15b
0x18000d37d  jz      short loc_18000D39A
0x18000d37f  mov     r8, [rsp+290h+var_268]
0x18000d384  mov     rdx, [rsp+290h+var_260]
0x18000d389  mov     rcx, [r8]
0x18000d38c  mov     [r8], rdx
0x18000d38f  test    rcx, rcx
0x18000d392  jz      short loc_18000D39A
0x18000d394  call    cs:__imp_SRCacheContext_Close
0x18000d39a  test    edi, edi
0x18000d39c  js      loc_18000D57A
0x18000d3a2  cmp     qword ptr [rsp+290h+var_270], r15
0x18000d3a7  setnz   al
0x18000d3aa  test    al, al
0x18000d3ac  jz      loc_18000D5B5
0x18000d3b2  xor     edx, edx; Val
0x18000d3b4  mov     [rsp+290h+var_250], r15
0x18000d3b9  mov     r8d, 200h; Size
0x18000d3bf  lea     rcx, [rsp+290h+var_248]; void *
0x18000d3c4  call    memset_0
0x18000d3c9  lea     rax, [rsp+290h+var_248]
0x18000d3ce  mov     [rbp+190h+var_48], r15
0x18000d3d5  mov     rdx, r14; unsigned __int16 *
0x18000d3d8  mov     [rbp+190h+var_38], rax
0x18000d3df  lea     rcx, [rsp+290h+var_250]; this
0x18000d3e4  mov     [rbp+190h+var_40], 100h
0x18000d3ef  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000d3f4  mov     edi, eax
0x18000d3f6  test    eax, eax
0x18000d3f8  js      loc_18000D4CA
0x18000d3fe  mov     rdx, [rbp+190h+var_38]
0x18000d405  lea     r9, [rsp+290h+var_260]
0x18000d40a  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000d40f  xor     r8d, r8d
0x18000d412  mov     [rsp+290h+var_268], rbx
0x18000d417  mov     [rsp+290h+var_260], r15
0x18000d41c  mov     [rsp+290h+var_258], 1
0x18000d421  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000d427  mov     edi, eax
0x18000d429  cmp     [rsp+290h+var_258], r15b
0x18000d42e  jz      short loc_18000D44B
0x18000d430  mov     r8, [rsp+290h+var_268]
0x18000d435  mov     rdx, [rsp+290h+var_260]
0x18000d43a  mov     rcx, [r8]
0x18000d43d  mov     [r8], rdx
0x18000d440  test    rcx, rcx
0x18000d443  jz      short loc_18000D44B
0x18000d445  call    cs:__imp_SRCacheContext_Close
0x18000d44b  test    edi, edi
0x18000d44d  js      loc_18000D5D7
0x18000d453  cmp     [rbx], r15
0x18000d456  jnz     loc_18000D5FC
0x18000d45c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000d461  lea     rdx, aProtocolIndexP; "Protocol\\Index\\ProgID"
0x18000d468  call    cs:__imp_SRCacheContext_AddToCache
0x18000d46e  mov     ebx, eax
0x18000d470  test    eax, eax
0x18000d472  js      loc_18000D513
0x18000d478  mov     rcx, [rsp+290h+var_250]
0x18000d47d  mov     [rsp+290h+var_250], r15
0x18000d482  test    rcx, rcx
0x18000d485  jz      short loc_18000D48D
0x18000d487  call    cs:__imp_SRCache_Free
0x18000d48d  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000d492  mov     qword ptr [rsp+290h+var_270], r15
0x18000d497  test    rcx, rcx
0x18000d49a  jz      short loc_18000D4A2
0x18000d49c  call    cs:__imp_SRCacheContext_Close
0x18000d4a2  xor     eax, eax
0x18000d4a4  mov     rcx, [rbp+190h+var_30]
0x18000d4ab  xor     rcx, rsp; StackCookie
0x18000d4ae  call    __security_check_cookie
0x18000d4b3  mov     rbx, [rsp+290h+arg_18]
0x18000d4bb  add     rsp, 270h
0x18000d4c2  pop     r15
0x18000d4c4  pop     r14
0x18000d4c6  pop     rdi
0x18000d4c7  pop     rsi
0x18000d4c8  pop     rbp
0x18000d4c9  retn
0x18000d4ca  mov     edx, 29Ch; void *
0x18000d4cf  mov     rcx, [rbp+198h]; this
0x18000d4d6  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d4dd  mov     r9d, edi; char *
0x18000d4e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4e5  mov     rcx, [rsp+290h+var_250]
0x18000d4ea  mov     [rsp+290h+var_250], r15
0x18000d4ef  test    rcx, rcx
0x18000d4f2  jz      short loc_18000D4FA
0x18000d4f4  call    cs:__imp_SRCache_Free
0x18000d4fa  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000d4ff  mov     qword ptr [rsp+290h+var_270], r15
0x18000d504  test    rcx, rcx
0x18000d507  jz      short loc_18000D50F
0x18000d509  call    cs:__imp_SRCacheContext_Close
0x18000d50f  mov     eax, edi
0x18000d511  jmp     short loc_18000D4A4
0x18000d513  mov     rcx, [rbp+198h]; this
0x18000d51a  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d521  mov     r9d, ebx; char *
0x18000d524  mov     edx, 1A6h; void *
0x18000d529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d52e  mov     rcx, [rbp+198h]; this
0x18000d535  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d53c  mov     r9d, ebx; char *
0x18000d53f  mov     edx, 2A5h; void *
0x18000d544  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d549  mov     rcx, [rsp+290h+var_250]
0x18000d54e  mov     [rsp+290h+var_250], r15
0x18000d553  test    rcx, rcx
0x18000d556  jz      short loc_18000D55E
0x18000d558  call    cs:__imp_SRCache_Free
0x18000d55e  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000d563  mov     qword ptr [rsp+290h+var_270], r15
0x18000d568  test    rcx, rcx
0x18000d56b  jz      short loc_18000D573
0x18000d56d  call    cs:__imp_SRCacheContext_Close
0x18000d573  mov     eax, ebx
0x18000d575  jmp     loc_18000D4A4
0x18000d57a  mov     rcx, [rbp+198h]; this
0x18000d581  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d588  mov     r9d, edi; char *
0x18000d58b  mov     edx, 18Ch; void *
0x18000d590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d595  mov     rcx, [rbp+198h]; this
0x18000d59c  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d5a3  mov     r9d, edi; char *
0x18000d5a6  mov     edx, 298h; void *
0x18000d5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5b0  jmp     loc_18000D4FA
0x18000d5b5  mov     rcx, [rbp+198h]; this
0x18000d5bc  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d5c3  mov     ebx, 80670012h
0x18000d5c8  mov     edx, 299h; void *
0x18000d5cd  mov     r9d, ebx; char *
0x18000d5d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5d5  jmp     short loc_18000D55E
0x18000d5d7  mov     rcx, [rbp+198h]; this
0x18000d5de  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d5e5  mov     r9d, edi; char *
0x18000d5e8  mov     edx, 1B0h; void *
0x18000d5ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5f2  mov     edx, 29Fh
0x18000d5f7  jmp     loc_18000D4CF
0x18000d5fc  mov     [rbx+10h], rsi
0x18000d600  jmp     loc_18000D45C
```
