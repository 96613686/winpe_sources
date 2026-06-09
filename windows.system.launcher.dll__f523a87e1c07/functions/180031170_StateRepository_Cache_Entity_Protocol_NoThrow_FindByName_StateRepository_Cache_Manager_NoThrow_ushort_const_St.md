# StateRepository::Cache::Entity::Protocol_NoThrow::FindByName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow &)

- ea: `0x180031170`
- end: `0x1800316cd`
- name: `?FindByName@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAVProtocolIndexIterator_NoThrow@234@@Z`
- size: `1373`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, struct StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014bd0`

## callees

- `0x180010c04`
- `0x180031170`
- `0x180032730`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008e5a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800313ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800314ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180031526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800315cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800313ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800314ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180031526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800315cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800311b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003120e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800313c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003146f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800314d9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031574`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800311b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003120e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800313c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003146f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800314d9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031574`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18003144b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18003144b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180031603`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180031603`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800311ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800311ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180031493`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180031493`

## string_xrefs

- `0x180031368`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180031618`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800314e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003158e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800315db`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180031388`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800313d5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x180031503`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x180031552`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800315a9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800311cc`: `Protocol\Index\Name`
- `0x18003148c`: `Protocol\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::FindByName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        struct StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rbx
  _BYTE *v11; // r10
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // rbx
  __int64 v15; // r12
  const unsigned __int16 *i; // rax
  unsigned __int64 v17; // rdi
  __int64 v18; // r8
  __int64 v19; // rcx
  _WORD *v20; // rax
  __int64 v21; // rax
  _WORD *v22; // rdx
  __int64 k; // r9
  _WORD *v24; // rcx
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  __int64 v27; // rcx
  __int64 v29; // rcx
  int v30; // eax
  _BYTE *v31; // rcx
  __int64 v32; // rcx
  _BYTE *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  _BYTE *v36; // rcx
  void *v37; // rax
  void *v38; // rsi
  _WORD *v39; // rcx
  unsigned __int64 j; // rdx
  int v41[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  char v44; // [rsp+38h] [rbp-C8h]
  _BYTE *v45; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v46[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+248h] [rbp+148h]
  __int64 v48; // [rsp+250h] [rbp+150h]
  void *Src; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a3;
  *(_QWORD *)a3 = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 2) = 0;
  v7 = *(_QWORD *)a1;
  v42 = v41;
  *(_QWORD *)v41 = 0;
  v43 = 0;
  v44 = 1;
  v8 = SRCacheContext_Open(v7, L"Protocol\\Index\\Name", 0, &v43);
  if ( v44 )
  {
    v9 = *(_QWORD *)v42;
    *(_QWORD *)v42 = v43;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v41[0]);
    v35 = 609;
    goto LABEL_57;
  }
  v10 = *(_QWORD *)v41;
  if ( !*(_QWORD *)v41 )
  {
    v8 = -2140733422;
    v35 = 610;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)v8,
      v41[0]);
    goto LABEL_58;
  }
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v11 = v46;
  v12 = 0;
  v47 = 0;
  v13 = 256;
  v48 = 256;
  Src = v46;
  if ( !a2 )
  {
LABEL_39:
    v42 = (int *)a3;
    v43 = 0;
    v44 = 1;
    v8 = SRCacheContext_OpenSubContext(v10, v11, 0, &v43);
    if ( v44 )
    {
      v29 = *(_QWORD *)v42;
      *(_QWORD *)v42 = v43;
      if ( v29 )
        SRCacheContext_Close(v29);
    }
    if ( (v8 & 0x80000000) == 0 )
    {
      if ( *(_QWORD *)a3 )
        *((_QWORD *)a3 + 2) = a1;
      v30 = SRCacheContext_AddToCache(*(_QWORD *)v41, L"Protocol\\Index\\Name");
      v8 = v30;
      if ( v30 >= 0 )
      {
        v31 = v45;
        v45 = 0;
        if ( v31 )
          SRCache_Free(v31);
        v32 = *(_QWORD *)v41;
        *(_QWORD *)v41 = 0;
        if ( v32 )
          SRCacheContext_Close(v32);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v30,
        v41[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
        (const char *)v8,
        v41[0]);
      v33 = v45;
      v45 = 0;
      if ( v33 )
        SRCache_Free(v33);
      v34 = *(_QWORD *)v41;
      *(_QWORD *)v41 = 0;
      if ( v34 )
        goto LABEL_59;
      goto LABEL_37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v41[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)v8,
      v41[0]);
    v36 = v45;
    v45 = 0;
    if ( v36 )
      SRCache_Free(v36);
LABEL_58:
    v34 = *(_QWORD *)v41;
    *(_QWORD *)v41 = 0;
    if ( v34 )
LABEL_59:
      SRCacheContext_Close(v34);
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)v8,
      v41[0]);
    return v8;
  }
  v14 = 0;
  v15 = 0;
  for ( i = a2; *i; ++i )
  {
    if ( ++v14 >= 0x7FFFFFFF )
    {
      v8 = -2147024809;
      v25 = 309;
      goto LABEL_32;
    }
    if ( *i == 94 )
      ++v15;
  }
  v17 = v15 + v14 + 1;
  if ( v17 <= 0x100 )
  {
LABEL_16:
    if ( v15 )
    {
      v39 = &v11[2 * v12];
      for ( j = 0; j < v14; ++v39 )
      {
        if ( *a2 == 94 )
          *v39++ = 94;
        ++j;
        *v39 = *a2++;
      }
      *v39 = 0;
    }
    else
    {
      v18 = 2147483646;
      if ( (unsigned __int64)(v13 - 1) > 0x7FFFFFFE )
      {
        v8 = -2147024809;
LABEL_31:
        v25 = 313;
        goto LABEL_32;
      }
      v19 = v13;
      v20 = v11;
      do
      {
        if ( !*v20 )
          break;
        ++v20;
        --v19;
      }
      while ( v19 );
      v8 = -2147024809;
      if ( v19 )
      {
        v8 = 0;
        v21 = v13 - v19;
      }
      else
      {
        v21 = 0;
      }
      if ( !v19 )
        goto LABEL_31;
      v22 = &v11[2 * v21];
      for ( k = v13 - v21; k; --k )
      {
        if ( !v18 )
          break;
        if ( !*a2 )
          break;
        *v22++ = *a2++;
        --v18;
      }
      v24 = v22 - 1;
      v8 = -2147024774;
      if ( k )
      {
        v24 = v22;
        v8 = 0;
      }
      *v24 = 0;
      if ( !k )
        goto LABEL_31;
    }
    v47 += v14;
    v10 = *(_QWORD *)v41;
    v11 = Src;
    goto LABEL_39;
  }
  v37 = (void *)SRCache_AllocStringBuffer((unsigned int)v17);
  v38 = v37;
  if ( v37 )
  {
    memcpy_0(v37, Src, 2 * v48);
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
      &v45,
      v38);
    v11 = v45;
    v13 = v15 + v14 + 1;
    v12 = v47;
    Src = v45;
    v48 = v13;
    goto LABEL_16;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v41[0]);
  v25 = 310;
LABEL_32:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)v8,
    v41[0]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x265,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
    (const char *)v8,
    v41[0]);
  v26 = v45;
  v45 = 0;
  if ( v26 )
    SRCache_Free(v26);
  v27 = *(_QWORD *)v41;
  *(_QWORD *)v41 = 0;
  if ( v27 )
    SRCacheContext_Close(v27);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_37;
  return 0;
}

```

## disassembly

```asm
0x180031170  push    rbp
0x180031172  push    rsi
0x180031173  push    rdi
0x180031174  push    r13
0x180031176  push    r14
0x180031178  push    r15
0x18003117a  lea     rbp, [rsp-178h]
0x180031182  sub     rsp, 278h
0x180031189  mov     rax, cs:__security_cookie
0x180031190  xor     rax, rsp
0x180031193  mov     [rbp+1A0h+var_40], rax
0x18003119a  xor     esi, esi
0x18003119c  mov     r13, rcx
0x18003119f  mov     rcx, [r8]
0x1800311a2  mov     r14, r8
0x1800311a5  mov     [r8], rsi
0x1800311a8  mov     r15, rdx
0x1800311ab  test    rcx, rcx
0x1800311ae  jz      short loc_1800311B6
0x1800311b0  call    cs:__imp_SRCacheContext_Close
0x1800311b6  mov     [r14+8], esi
0x1800311ba  lea     rax, [rsp+2A0h+var_280]
0x1800311bf  mov     [r14+10h], rsi
0x1800311c3  lea     r9, [rsp+2A0h+var_270]
0x1800311c8  mov     rcx, [r13+0]
0x1800311cc  lea     rdx, aProtocolIndexN; "Protocol\\Index\\Name"
0x1800311d3  xor     r8d, r8d
0x1800311d6  mov     [rsp+2A0h+var_278], rax
0x1800311db  mov     qword ptr [rsp+2A0h+var_280], rsi; int
0x1800311e0  mov     [rsp+2A0h+var_270], rsi
0x1800311e5  mov     [rsp+2A0h+var_268], 1
0x1800311ea  call    cs:__imp_SRCacheContext_Open
0x1800311f0  mov     edi, eax
0x1800311f2  cmp     [rsp+2A0h+var_268], sil
0x1800311f7  jz      short loc_180031214
0x1800311f9  mov     rdx, [rsp+2A0h+var_278]
0x1800311fe  mov     rax, [rsp+2A0h+var_270]
0x180031203  mov     rcx, [rdx]
0x180031206  mov     [rdx], rax
0x180031209  test    rcx, rcx
0x18003120c  jz      short loc_180031214
0x18003120e  call    cs:__imp_SRCacheContext_Close
0x180031214  mov     [rsp+2A0h+arg_8], rbx
0x18003121c  mov     [rsp+2A0h+var_30], r12
0x180031224  test    edi, edi
0x180031226  js      loc_1800315D4
0x18003122c  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180031231  test    rbx, rbx
0x180031234  setnz   al
0x180031237  test    al, al
0x180031239  jz      loc_180031541
0x18003123f  xor     edx, edx; Val
0x180031241  mov     [rsp+2A0h+var_260], rsi
0x180031246  mov     r8d, 200h; Size
0x18003124c  lea     rcx, [rsp+2A0h+var_258]; void *
0x180031251  call    memset_0
0x180031256  lea     r10, [rsp+2A0h+var_258]
0x18003125b  mov     rdx, rsi
0x18003125e  mov     [rbp+1A0h+var_58], rdx
0x180031265  mov     r9d, 100h
0x18003126b  mov     [rbp+1A0h+var_50], r9
0x180031272  mov     [rbp+1A0h+Src], r10
0x180031279  test    r15, r15
0x18003127c  jz      loc_18003142E
0x180031282  mov     rbx, rsi
0x180031285  mov     r12, rsi
0x180031288  mov     rax, r15
0x18003128b  nop     dword ptr [rax+rax+00h]
0x180031290  movzx   ecx, word ptr [rax]
0x180031293  test    cx, cx
0x180031296  jz      short loc_1800312B8
0x180031298  inc     rbx
0x18003129b  cmp     rbx, 7FFFFFFFh
0x1800312a2  jnb     loc_1800314CA
0x1800312a8  cmp     cx, 5Eh ; '^'
0x1800312ac  jz      loc_1800315F9
0x1800312b2  add     rax, 2
0x1800312b6  jmp     short loc_180031290
0x1800312b8  lea     rdi, [rbx+1]
0x1800312bc  add     rdi, r12
0x1800312bf  cmp     rdi, r9
0x1800312c2  ja      loc_180031601
0x1800312c8  test    r12, r12
0x1800312cb  jnz     loc_180031692
0x1800312d1  lea     rax, [r9-1]
0x1800312d5  mov     r8d, 7FFFFFFEh
0x1800312db  cmp     rax, r8
0x1800312de  ja      loc_180031688
0x1800312e4  mov     rcx, r9
0x1800312e7  mov     rax, r10
0x1800312ea  nop     word ptr [rax+rax+00h]
0x1800312f0  cmp     word ptr [rax], 0
0x1800312f4  jz      short loc_180031300
0x1800312f6  add     rax, 2
0x1800312fa  sub     rcx, 1
0x1800312fe  jnz     short loc_1800312F0
0x180031300  test    rcx, rcx
0x180031303  mov     edi, 80070057h
0x180031308  cmovnz  edi, esi
0x18003130b  jz      loc_18003157F
0x180031311  mov     rax, r9
0x180031314  sub     rax, rcx
0x180031317  test    rcx, rcx
0x18003131a  jz      short loc_180031363
0x18003131c  lea     rdx, [r10+rax*2]
0x180031320  sub     r9, rax
0x180031323  jz      short loc_180031347
0x180031325  test    r8, r8
0x180031328  jz      short loc_180031347
0x18003132a  movzx   eax, word ptr [r15]
0x18003132e  test    ax, ax
0x180031331  jz      short loc_180031347
0x180031333  mov     [rdx], ax
0x180031336  add     r15, 2
0x18003133a  add     rdx, 2
0x18003133e  dec     r8
0x180031341  sub     r9, 1
0x180031345  jnz     short loc_180031325
0x180031347  test    r9, r9
0x18003134a  lea     rcx, [rdx-2]
0x18003134e  mov     edi, 8007007Ah
0x180031353  cmovnz  rcx, rdx
0x180031357  cmovnz  edi, esi
0x18003135a  mov     [rcx], si
0x18003135d  jnz     loc_18003141B
0x180031363  mov     edx, 139h; void *
0x180031368  lea     rbx, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003136f  mov     rcx, [rbp+1A8h]; this
0x180031376  mov     r9d, edi; char *
0x180031379  mov     r8, rbx; unsigned int
0x18003137c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031381  mov     rcx, [rbp+1A8h]; this
0x180031388  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003138f  mov     r9d, edi; char *
0x180031392  mov     edx, 265h; void *
0x180031397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003139c  mov     rcx, [rsp+2A0h+var_260]
0x1800313a1  mov     [rsp+2A0h+var_260], rsi
0x1800313a6  test    rcx, rcx
0x1800313a9  jz      short loc_1800313B1
0x1800313ab  call    cs:__imp_SRCache_Free
0x1800313b1  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800313b6  mov     qword ptr [rsp+2A0h+var_280], rsi; int
0x1800313bb  test    rcx, rcx
0x1800313be  jz      short loc_1800313C6
0x1800313c0  call    cs:__imp_SRCacheContext_Close
0x1800313c6  test    edi, edi
0x1800313c8  jns     loc_1800314C3
0x1800313ce  mov     rcx, [rbp+1A8h]; this
0x1800313d5  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800313dc  mov     r9d, edi; char *
0x1800313df  mov     edx, 335h; void *
0x1800313e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313e9  mov     eax, edi
0x1800313eb  mov     r12, [rsp+2A0h+var_30]
0x1800313f3  mov     rbx, [rsp+2A0h+arg_8]
0x1800313fb  mov     rcx, [rbp+1A0h+var_40]
0x180031402  xor     rcx, rsp; StackCookie
0x180031405  call    __security_check_cookie
0x18003140a  add     rsp, 278h
0x180031411  pop     r15
0x180031413  pop     r14
0x180031415  pop     r13
0x180031417  pop     rdi
0x180031418  pop     rsi
0x180031419  pop     rbp
0x18003141a  retn
0x18003141b  add     [rbp+1A0h+var_58], rbx
0x180031422  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180031427  mov     r10, [rbp+1A0h+Src]
0x18003142e  lea     r9, [rsp+2A0h+var_270]
0x180031433  mov     [rsp+2A0h+var_278], r14
0x180031438  xor     r8d, r8d
0x18003143b  mov     [rsp+2A0h+var_270], rsi
0x180031440  mov     rdx, r10
0x180031443  mov     [rsp+2A0h+var_268], 1
0x180031448  mov     rcx, rbx
0x18003144b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180031451  cmp     [rsp+2A0h+var_268], 0
0x180031456  mov     edi, eax
0x180031458  jz      short loc_180031475
0x18003145a  mov     rdx, [rsp+2A0h+var_278]
0x18003145f  mov     rax, [rsp+2A0h+var_270]
0x180031464  mov     rcx, [rdx]
0x180031467  mov     [rdx], rax
0x18003146a  test    rcx, rcx
0x18003146d  jz      short loc_180031475
0x18003146f  call    cs:__imp_SRCacheContext_Close
0x180031475  test    edi, edi
0x180031477  js      loc_180031587
0x18003147d  cmp     qword ptr [r14], 0
0x180031481  jz      short loc_180031487
0x180031483  mov     [r14+10h], r13
0x180031487  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18003148c  lea     rdx, aProtocolIndexN; "Protocol\\Index\\Name"
0x180031493  call    cs:__imp_SRCacheContext_AddToCache
0x180031499  mov     edi, eax
0x18003149b  test    eax, eax
0x18003149d  js      short loc_1800314E1
0x18003149f  mov     rcx, [rsp+2A0h+var_260]
0x1800314a4  mov     [rsp+2A0h+var_260], rsi
0x1800314a9  test    rcx, rcx
0x1800314ac  jz      short loc_1800314B4
0x1800314ae  call    cs:__imp_SRCache_Free
0x1800314b4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800314b9  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1800314be  test    rcx, rcx
0x1800314c1  jnz     short loc_1800314D9
0x1800314c3  xor     eax, eax
0x1800314c5  jmp     loc_1800313EB
0x1800314ca  mov     edi, 80070057h
0x1800314cf  mov     edx, 135h
0x1800314d4  jmp     loc_180031368
0x1800314d9  call    cs:__imp_SRCacheContext_Close
0x1800314df  jmp     short loc_1800314C3
0x1800314e1  mov     rcx, [rbp+1A8h]; this
0x1800314e8  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800314ef  mov     r9d, edi; char *
0x1800314f2  mov     edx, 1A6h; void *
0x1800314f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800314fc  mov     rcx, [rbp+1A8h]; this
0x180031503  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003150a  mov     r9d, edi; char *
0x18003150d  mov     edx, 26Eh; void *
0x180031512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031517  mov     rcx, [rsp+2A0h+var_260]
0x18003151c  mov     [rsp+2A0h+var_260], rsi
0x180031521  test    rcx, rcx
0x180031524  jz      short loc_18003152C
0x180031526  call    cs:__imp_SRCache_Free
0x18003152c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180031531  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180031536  test    rcx, rcx
0x180031539  jz      loc_1800313CE
0x18003153f  jmp     short loc_180031574
0x180031541  mov     edi, 80670012h
0x180031546  mov     edx, 262h; void *
0x18003154b  mov     rcx, [rbp+1A8h]; this
0x180031552  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031559  mov     r9d, edi; char *
0x18003155c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031561  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180031566  mov     qword ptr [rsp+2A0h+var_280], rsi
0x18003156b  test    rcx, rcx
0x18003156e  jz      loc_1800313CE
0x180031574  call    cs:__imp_SRCacheContext_Close
0x18003157a  jmp     loc_1800313CE
0x18003157f  mov     rax, rsi
0x180031582  jmp     loc_180031317
0x180031587  mov     rcx, [rbp+1A8h]; this
0x18003158e  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031595  mov     r9d, edi; char *
0x180031598  mov     edx, 1B0h; void *
0x18003159d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315a2  mov     rcx, [rbp+1A8h]; this
0x1800315a9  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800315b0  mov     r9d, edi; char *
0x1800315b3  mov     edx, 268h; void *
0x1800315b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315bd  mov     rcx, [rsp+2A0h+var_260]
0x1800315c2  mov     [rsp+2A0h+var_260], rsi
0x1800315c7  test    rcx, rcx
0x1800315ca  jz      short loc_180031561
0x1800315cc  call    cs:__imp_SRCache_Free
0x1800315d2  jmp     short loc_180031561
0x1800315d4  mov     rcx, [rbp+1A8h]; this
0x1800315db  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800315e2  mov     r9d, edi; char *
0x1800315e5  mov     edx, 18Ch; void *
0x1800315ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315ef  mov     edx, 261h
0x1800315f4  jmp     loc_18003154B
0x1800315f9  inc     r12
0x1800315fc  jmp     loc_1800312B2
0x180031601  mov     ecx, edi
0x180031603  call    cs:__imp_SRCache_AllocStringBuffer
0x180031609  mov     rsi, rax
0x18003160c  test    rax, rax
0x18003160f  jnz     short loc_18003163E
0x180031611  mov     rcx, [rbp+1A8h]; this
0x180031618  lea     rbx, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003161f  mov     edi, 8007000Eh
0x180031624  mov     r8, rbx; unsigned int
0x180031627  mov     r9d, edi; char *
0x18003162a  mov     edx, 193h; void *
0x18003162f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031634  mov     edx, 136h
0x180031639  jmp     loc_18003136F
0x18003163e  mov     r8, [rbp+1A0h+var_50]
0x180031645  mov     rcx, rsi; void *
0x180031648  mov     rdx, [rbp+1A0h+Src]; Src
0x18003164f  add     r8, r8; Size
0x180031652  call    memcpy_0
0x180031657  mov     rdx, rsi
0x18003165a  lea     rcx, [rsp+2A0h+var_260]
0x18003165f  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x180031664  mov     r10, [rsp+2A0h+var_260]
0x180031669  mov     r9, rdi
0x18003166c  mov     rdx, [rbp+1A0h+var_58]
0x180031673  xor     esi, esi
  ... truncated ...
```
