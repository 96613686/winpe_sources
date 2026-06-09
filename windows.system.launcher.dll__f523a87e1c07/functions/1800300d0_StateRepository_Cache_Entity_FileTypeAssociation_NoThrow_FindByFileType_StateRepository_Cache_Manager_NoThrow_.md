# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::FindByFileType(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow &)

- ea: `0x1800300d0`
- end: `0x180030631`
- name: `?FindByFileType@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAVFileTypeAssociationIndexIterator_NoThrow@234@@Z`
- size: `1377`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, struct StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010c30`

## callees

- `0x180010c04`
- `0x1800300d0`
- `0x180032730`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008e5a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003030b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003040e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030482`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800304ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003030b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003040e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030482`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800304ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030110`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003016e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030320`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800303cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030503`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030626`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030110`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003016e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030320`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800303cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030503`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030626`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800303ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800303ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18003055c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18003055c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003014a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003014a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800303f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800303f3`

## string_xrefs

- `0x1800302c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180030571`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800302e8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180030335`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x18003045f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800304c7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180030541`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180030444`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800304ac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030515`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::FindByFileType(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        struct StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *a3)
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
  _BYTE *v35; // rcx
  __int64 v36; // rdx
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
  v8 = SRCacheContext_Open(v7, L"FileTypeAssociation\\Index\\FileType", 0, &v43);
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
    v36 = 609;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)v8,
      v41[0]);
    goto LABEL_59;
  }
  v10 = *(_QWORD *)v41;
  if ( !*(_QWORD *)v41 )
  {
    v8 = -2140733422;
    v36 = 610;
    goto LABEL_63;
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
      v30 = SRCacheContext_AddToCache(*(_QWORD *)v41, L"FileTypeAssociation\\Index\\FileType");
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
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
        (const char *)v8,
        v41[0]);
      v33 = v45;
      v45 = 0;
      if ( v33 )
        SRCache_Free(v33);
      v34 = *(_QWORD *)v41;
      *(_QWORD *)v41 = 0;
      if ( v34 )
        goto LABEL_60;
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)v8,
      v41[0]);
    v35 = v45;
    v45 = 0;
    if ( v35 )
      SRCache_Free(v35);
LABEL_59:
    v34 = *(_QWORD *)v41;
    *(_QWORD *)v41 = 0;
    if ( v34 )
LABEL_60:
      SRCacheContext_Close(v34);
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
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
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
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
0x1800300d0  push    rbp
0x1800300d2  push    rsi
0x1800300d3  push    rdi
0x1800300d4  push    r13
0x1800300d6  push    r14
0x1800300d8  push    r15
0x1800300da  lea     rbp, [rsp-178h]
0x1800300e2  sub     rsp, 278h
0x1800300e9  mov     rax, cs:__security_cookie
0x1800300f0  xor     rax, rsp
0x1800300f3  mov     [rbp+1A0h+var_40], rax
0x1800300fa  xor     esi, esi
0x1800300fc  mov     r13, rcx
0x1800300ff  mov     rcx, [r8]
0x180030102  mov     r14, r8
0x180030105  mov     [r8], rsi
0x180030108  mov     r15, rdx
0x18003010b  test    rcx, rcx
0x18003010e  jz      short loc_180030116
0x180030110  call    cs:__imp_SRCacheContext_Close
0x180030116  mov     [r14+8], esi
0x18003011a  lea     rax, [rsp+2A0h+var_280]
0x18003011f  mov     [r14+10h], rsi
0x180030123  lea     r9, [rsp+2A0h+var_270]
0x180030128  mov     rcx, [r13+0]
0x18003012c  lea     rdx, aFiletypeassoci_2; "FileTypeAssociation\\Index\\FileType"
0x180030133  xor     r8d, r8d
0x180030136  mov     [rsp+2A0h+var_278], rax
0x18003013b  mov     qword ptr [rsp+2A0h+var_280], rsi; int
0x180030140  mov     [rsp+2A0h+var_270], rsi
0x180030145  mov     [rsp+2A0h+var_268], 1
0x18003014a  call    cs:__imp_SRCacheContext_Open
0x180030150  mov     edi, eax
0x180030152  cmp     [rsp+2A0h+var_268], sil
0x180030157  jz      short loc_180030174
0x180030159  mov     rdx, [rsp+2A0h+var_278]
0x18003015e  mov     rax, [rsp+2A0h+var_270]
0x180030163  mov     rcx, [rdx]
0x180030166  mov     [rdx], rax
0x180030169  test    rcx, rcx
0x18003016c  jz      short loc_180030174
0x18003016e  call    cs:__imp_SRCacheContext_Close
0x180030174  mov     [rsp+2A0h+arg_8], rbx
0x18003017c  mov     [rsp+2A0h+var_30], r12
0x180030184  test    edi, edi
0x180030186  js      loc_18003050E
0x18003018c  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180030191  test    rbx, rbx
0x180030194  setnz   al
0x180030197  test    al, al
0x180030199  jz      loc_180030530
0x18003019f  xor     edx, edx; Val
0x1800301a1  mov     [rsp+2A0h+var_260], rsi
0x1800301a6  mov     r8d, 200h; Size
0x1800301ac  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800301b1  call    memset_0
0x1800301b6  lea     r10, [rsp+2A0h+var_258]
0x1800301bb  mov     rdx, rsi
0x1800301be  mov     [rbp+1A0h+var_58], rdx
0x1800301c5  mov     r9d, 100h
0x1800301cb  mov     [rbp+1A0h+var_50], r9
0x1800301d2  mov     [rbp+1A0h+Src], r10
0x1800301d9  test    r15, r15
0x1800301dc  jz      loc_18003038E
0x1800301e2  mov     rbx, rsi
0x1800301e5  mov     r12, rsi
0x1800301e8  mov     rax, r15
0x1800301eb  nop     dword ptr [rax+rax+00h]
0x1800301f0  movzx   ecx, word ptr [rax]
0x1800301f3  test    cx, cx
0x1800301f6  jz      short loc_180030218
0x1800301f8  inc     rbx
0x1800301fb  cmp     rbx, 7FFFFFFFh
0x180030202  jnb     loc_18003042E
0x180030208  cmp     cx, 5Eh ; '^'
0x18003020c  jz      loc_180030552
0x180030212  add     rax, 2
0x180030216  jmp     short loc_1800301F0
0x180030218  lea     rdi, [rbx+1]
0x18003021c  add     rdi, r12
0x18003021f  cmp     rdi, r9
0x180030222  ja      loc_18003055A
0x180030228  test    r12, r12
0x18003022b  jnz     loc_1800305EB
0x180030231  lea     rax, [r9-1]
0x180030235  mov     r8d, 7FFFFFFEh
0x18003023b  cmp     rax, r8
0x18003023e  ja      loc_1800305E1
0x180030244  mov     rcx, r9
0x180030247  mov     rax, r10
0x18003024a  nop     word ptr [rax+rax+00h]
0x180030250  cmp     word ptr [rax], 0
0x180030254  jz      short loc_180030260
0x180030256  add     rax, 2
0x18003025a  sub     rcx, 1
0x18003025e  jnz     short loc_180030250
0x180030260  test    rcx, rcx
0x180030263  mov     edi, 80070057h
0x180030268  cmovnz  edi, esi
0x18003026b  jz      loc_18003049D
0x180030271  mov     rax, r9
0x180030274  sub     rax, rcx
0x180030277  test    rcx, rcx
0x18003027a  jz      short loc_1800302C3
0x18003027c  lea     rdx, [r10+rax*2]
0x180030280  sub     r9, rax
0x180030283  jz      short loc_1800302A7
0x180030285  test    r8, r8
0x180030288  jz      short loc_1800302A7
0x18003028a  movzx   eax, word ptr [r15]
0x18003028e  test    ax, ax
0x180030291  jz      short loc_1800302A7
0x180030293  mov     [rdx], ax
0x180030296  add     r15, 2
0x18003029a  add     rdx, 2
0x18003029e  dec     r8
0x1800302a1  sub     r9, 1
0x1800302a5  jnz     short loc_180030285
0x1800302a7  test    r9, r9
0x1800302aa  lea     rcx, [rdx-2]
0x1800302ae  mov     edi, 8007007Ah
0x1800302b3  cmovnz  rcx, rdx
0x1800302b7  cmovnz  edi, esi
0x1800302ba  mov     [rcx], si
0x1800302bd  jnz     loc_18003037B
0x1800302c3  mov     edx, 139h; void *
0x1800302c8  lea     rbx, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800302cf  mov     rcx, [rbp+1A8h]; this
0x1800302d6  mov     r9d, edi; char *
0x1800302d9  mov     r8, rbx; unsigned int
0x1800302dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302e1  mov     rcx, [rbp+1A8h]; this
0x1800302e8  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800302ef  mov     r9d, edi; char *
0x1800302f2  mov     edx, 265h; void *
0x1800302f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302fc  mov     rcx, [rsp+2A0h+var_260]
0x180030301  mov     [rsp+2A0h+var_260], rsi
0x180030306  test    rcx, rcx
0x180030309  jz      short loc_180030311
0x18003030b  call    cs:__imp_SRCache_Free
0x180030311  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180030316  mov     qword ptr [rsp+2A0h+var_280], rsi; int
0x18003031b  test    rcx, rcx
0x18003031e  jz      short loc_180030326
0x180030320  call    cs:__imp_SRCacheContext_Close
0x180030326  test    edi, edi
0x180030328  jns     loc_180030427
0x18003032e  mov     rcx, [rbp+1A8h]; this
0x180030335  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003033c  mov     r9d, edi; char *
0x18003033f  mov     edx, 335h; void *
0x180030344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030349  mov     eax, edi
0x18003034b  mov     r12, [rsp+2A0h+var_30]
0x180030353  mov     rbx, [rsp+2A0h+arg_8]
0x18003035b  mov     rcx, [rbp+1A0h+var_40]
0x180030362  xor     rcx, rsp; StackCookie
0x180030365  call    __security_check_cookie
0x18003036a  add     rsp, 278h
0x180030371  pop     r15
0x180030373  pop     r14
0x180030375  pop     r13
0x180030377  pop     rdi
0x180030378  pop     rsi
0x180030379  pop     rbp
0x18003037a  retn
0x18003037b  add     [rbp+1A0h+var_58], rbx
0x180030382  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180030387  mov     r10, [rbp+1A0h+Src]
0x18003038e  lea     r9, [rsp+2A0h+var_270]
0x180030393  mov     [rsp+2A0h+var_278], r14
0x180030398  xor     r8d, r8d
0x18003039b  mov     [rsp+2A0h+var_270], rsi
0x1800303a0  mov     rdx, r10
0x1800303a3  mov     [rsp+2A0h+var_268], 1
0x1800303a8  mov     rcx, rbx
0x1800303ab  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800303b1  cmp     [rsp+2A0h+var_268], 0
0x1800303b6  mov     edi, eax
0x1800303b8  jz      short loc_1800303D5
0x1800303ba  mov     rdx, [rsp+2A0h+var_278]
0x1800303bf  mov     rax, [rsp+2A0h+var_270]
0x1800303c4  mov     rcx, [rdx]
0x1800303c7  mov     [rdx], rax
0x1800303ca  test    rcx, rcx
0x1800303cd  jz      short loc_1800303D5
0x1800303cf  call    cs:__imp_SRCacheContext_Close
0x1800303d5  test    edi, edi
0x1800303d7  js      loc_1800304A5
0x1800303dd  cmp     qword ptr [r14], 0
0x1800303e1  jz      short loc_1800303E7
0x1800303e3  mov     [r14+10h], r13
0x1800303e7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800303ec  lea     rdx, aFiletypeassoci_2; "FileTypeAssociation\\Index\\FileType"
0x1800303f3  call    cs:__imp_SRCacheContext_AddToCache
0x1800303f9  mov     edi, eax
0x1800303fb  test    eax, eax
0x1800303fd  js      short loc_18003043D
0x1800303ff  mov     rcx, [rsp+2A0h+var_260]
0x180030404  mov     [rsp+2A0h+var_260], rsi
0x180030409  test    rcx, rcx
0x18003040c  jz      short loc_180030414
0x18003040e  call    cs:__imp_SRCache_Free
0x180030414  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180030419  mov     qword ptr [rsp+2A0h+var_280], rsi
0x18003041e  test    rcx, rcx
0x180030421  jnz     loc_180030626
0x180030427  xor     eax, eax
0x180030429  jmp     loc_18003034B
0x18003042e  mov     edi, 80070057h
0x180030433  mov     edx, 135h
0x180030438  jmp     loc_1800302C8
0x18003043d  mov     rcx, [rbp+1A8h]; this
0x180030444  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003044b  mov     r9d, edi; char *
0x18003044e  mov     edx, 1A6h; void *
0x180030453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030458  mov     rcx, [rbp+1A8h]; this
0x18003045f  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030466  mov     r9d, edi; char *
0x180030469  mov     edx, 26Eh; void *
0x18003046e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030473  mov     rcx, [rsp+2A0h+var_260]
0x180030478  mov     [rsp+2A0h+var_260], rsi
0x18003047d  test    rcx, rcx
0x180030480  jz      short loc_180030488
0x180030482  call    cs:__imp_SRCache_Free
0x180030488  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18003048d  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180030492  test    rcx, rcx
0x180030495  jz      loc_18003032E
0x18003049b  jmp     short loc_180030503
0x18003049d  mov     rax, rsi
0x1800304a0  jmp     loc_180030277
0x1800304a5  mov     rcx, [rbp+1A8h]; this
0x1800304ac  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800304b3  mov     r9d, edi; char *
0x1800304b6  mov     edx, 1B0h; void *
0x1800304bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304c0  mov     rcx, [rbp+1A8h]; this
0x1800304c7  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800304ce  mov     r9d, edi; char *
0x1800304d1  mov     edx, 268h; void *
0x1800304d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304db  mov     rcx, [rsp+2A0h+var_260]
0x1800304e0  mov     [rsp+2A0h+var_260], rsi
0x1800304e5  test    rcx, rcx
0x1800304e8  jz      short loc_1800304F0
0x1800304ea  call    cs:__imp_SRCache_Free
0x1800304f0  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800304f5  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1800304fa  test    rcx, rcx
0x1800304fd  jz      loc_18003032E
0x180030503  call    cs:__imp_SRCacheContext_Close
0x180030509  jmp     loc_18003032E
0x18003050e  mov     rcx, [rbp+1A8h]; this
0x180030515  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003051c  mov     r9d, edi; char *
0x18003051f  mov     edx, 18Ch; void *
0x180030524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030529  mov     edx, 261h
0x18003052e  jmp     short loc_18003053A
0x180030530  mov     edi, 80670012h
0x180030535  mov     edx, 262h; void *
0x18003053a  mov     rcx, [rbp+1A8h]; this
0x180030541  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030548  mov     r9d, edi; char *
0x18003054b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030550  jmp     short loc_1800304F0
0x180030552  inc     r12
0x180030555  jmp     loc_180030212
0x18003055a  mov     ecx, edi
0x18003055c  call    cs:__imp_SRCache_AllocStringBuffer
0x180030562  mov     rsi, rax
0x180030565  test    rax, rax
0x180030568  jnz     short loc_180030597
0x18003056a  mov     rcx, [rbp+1A8h]; this
0x180030571  lea     rbx, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030578  mov     edi, 8007000Eh
0x18003057d  mov     r8, rbx; unsigned int
0x180030580  mov     r9d, edi; char *
0x180030583  mov     edx, 193h; void *
0x180030588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003058d  mov     edx, 136h
0x180030592  jmp     loc_1800302CF
0x180030597  mov     r8, [rbp+1A0h+var_50]
0x18003059e  mov     rcx, rsi; void *
0x1800305a1  mov     rdx, [rbp+1A0h+Src]; Src
0x1800305a8  add     r8, r8; Size
0x1800305ab  call    memcpy_0
0x1800305b0  mov     rdx, rsi
0x1800305b3  lea     rcx, [rsp+2A0h+var_260]
0x1800305b8  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x1800305bd  mov     r10, [rsp+2A0h+var_260]
0x1800305c2  mov     r9, rdi
0x1800305c5  mov     rdx, [rbp+1A0h+var_58]
0x1800305cc  xor     esi, esi
0x1800305ce  mov     [rbp+1A0h+Src], r10
0x1800305d5  mov     [rbp+1A0h+var_50], rdi
  ... truncated ...
```
