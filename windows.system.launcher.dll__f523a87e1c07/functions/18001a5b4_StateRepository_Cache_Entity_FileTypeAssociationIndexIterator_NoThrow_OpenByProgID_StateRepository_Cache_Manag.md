# StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x18001a5b4`
- end: `0x18001aa75`
- name: `?OpenByProgID@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `1217`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017b70`

## callees

- `0x180010c04`
- `0x18001a5b4`
- `0x180032730`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008e5a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a7f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a8c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a5fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a659`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a805`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a88b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a5fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a659`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a805`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a88b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001a867`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001a867`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a979`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a979`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001a635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001a635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001a8ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001a8ae`

## string_xrefs

- `0x18001a7ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a98e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a7d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x18001a95a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x18001a909`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a92e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001aa4e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByProgID(
        StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  _BYTE *v11; // r10
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r15
  __int64 v15; // rbx
  const unsigned __int16 *i; // rax
  unsigned __int64 v17; // r14
  __int64 v18; // r9
  __int64 v19; // r8
  _WORD *v20; // rax
  __int64 v21; // rax
  _WORD *v22; // r8
  __int64 k; // rdx
  _WORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  _BYTE *v27; // rcx
  __int64 v28; // rcx
  __int64 v30; // rcx
  int v31; // eax
  _BYTE *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  void *v35; // rax
  void *v36; // r12
  _WORD *v37; // rcx
  unsigned __int64 j; // rdx
  int v39[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v40; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+30h] [rbp-D0h] BYREF
  char v42; // [rsp+38h] [rbp-C8h]
  _BYTE *v43; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v44[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+248h] [rbp+148h]
  __int64 v46; // [rsp+250h] [rbp+150h]
  void *Src; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v40 = v39;
  *(_QWORD *)v39 = 0;
  v41 = 0;
  v42 = 1;
  v8 = SRCacheContext_Open(v7, L"FileTypeAssociation\\Index\\ProgID", 0, &v41);
  if ( v42 )
  {
    v9 = *(_QWORD *)v40;
    *(_QWORD *)v40 = v41;
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
      v39[0]);
    v34 = 664;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)v8,
      v39[0]);
LABEL_35:
    v28 = *(_QWORD *)v39;
    *(_QWORD *)v39 = 0;
    if ( v28 )
      SRCacheContext_Close(v28);
    return v8;
  }
  v10 = *(_QWORD *)v39;
  if ( !*(_QWORD *)v39 )
  {
    v8 = -2140733422;
    v34 = 665;
    goto LABEL_56;
  }
  v43 = 0;
  memset_0(v44, 0, sizeof(v44));
  v11 = v44;
  v12 = 0;
  v45 = 0;
  v13 = 256;
  v46 = 256;
  Src = v44;
  if ( a3 )
  {
    v14 = 0;
    v15 = 0;
    for ( i = a3; *i; ++i )
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
    if ( v17 > 0x100 )
    {
      v35 = (void *)SRCache_AllocStringBuffer((unsigned int)v17);
      v36 = v35;
      if ( !v35 )
      {
        v8 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v39[0]);
        v25 = 310;
        goto LABEL_32;
      }
      memcpy_0(v35, Src, 2 * v46);
      wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
        &v43,
        v36);
      v11 = v43;
      v12 = v45;
      v13 = v15 + v14 + 1;
      Src = v43;
      v46 = v13;
    }
    if ( v15 )
    {
      v37 = &v11[2 * v12];
      for ( j = 0; j < v14; ++v37 )
      {
        if ( *a3 == 94 )
          *v37++ = 94;
        ++j;
        *v37 = *a3++;
      }
      *v37 = 0;
    }
    else
    {
      v18 = 2147483646;
      if ( (unsigned __int64)(v13 - 1) > 0x7FFFFFFE )
      {
        v8 = -2147024809;
LABEL_31:
        v25 = 313;
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v8,
          v39[0]);
        v26 = 668;
        goto LABEL_33;
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
      v8 = v19 == 0 ? 0x80070057 : 0;
      if ( v19 )
        v21 = v13 - v19;
      else
        v21 = 0;
      if ( !v19 )
        goto LABEL_31;
      v22 = &v11[2 * v21];
      for ( k = v13 - v21; k; --k )
      {
        if ( !v18 )
          break;
        if ( !*a3 )
          break;
        *v22++ = *a3++;
        --v18;
      }
      v24 = v22 - 1;
      v8 = k == 0 ? 0x8007007A : 0;
      if ( k )
        v24 = v22;
      *v24 = 0;
      if ( !k )
        goto LABEL_31;
    }
    v45 += v14;
    v10 = *(_QWORD *)v39;
    v11 = Src;
  }
  v40 = (int *)this;
  v41 = 0;
  v42 = 1;
  v8 = SRCacheContext_OpenSubContext(v10, v11, 0, &v41);
  if ( v42 )
  {
    v30 = *(_QWORD *)v40;
    *(_QWORD *)v40 = v41;
    if ( v30 )
      SRCacheContext_Close(v30);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v39[0]);
    v26 = 671;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)v8,
      v39[0]);
    v27 = v43;
    v43 = 0;
    if ( v27 )
      SRCache_Free(v27);
    goto LABEL_35;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v31 = SRCacheContext_AddToCache(*(_QWORD *)v39, L"FileTypeAssociation\\Index\\ProgID");
  v8 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v31,
      v39[0]);
    v26 = 677;
    goto LABEL_33;
  }
  v32 = v43;
  v43 = 0;
  if ( v32 )
    SRCache_Free(v32);
  v33 = *(_QWORD *)v39;
  *(_QWORD *)v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  return 0;
}

```

## disassembly

```asm
0x18001a5b4  mov     [rsp-8+arg_10], rbx
0x18001a5b9  push    rbp
0x18001a5ba  push    rsi
0x18001a5bb  push    rdi
0x18001a5bc  push    r12
0x18001a5be  push    r13
0x18001a5c0  push    r14
0x18001a5c2  push    r15
0x18001a5c4  lea     rbp, [rsp-170h]
0x18001a5cc  sub     rsp, 270h
0x18001a5d3  mov     rax, cs:__security_cookie
0x18001a5da  xor     rax, rsp
0x18001a5dd  mov     [rbp+1A0h+var_40], rax
0x18001a5e4  mov     rsi, rcx
0x18001a5e7  xor     r12d, r12d
0x18001a5ea  mov     rcx, [rcx]
0x18001a5ed  mov     rdi, r8
0x18001a5f0  mov     r13, rdx
0x18001a5f3  mov     [rsi], r12
0x18001a5f6  test    rcx, rcx
0x18001a5f9  jz      short loc_18001A601
0x18001a5fb  call    cs:__imp_SRCacheContext_Close
0x18001a601  mov     [rsi+8], r12d
0x18001a605  lea     rax, [rsp+2A0h+var_280]
0x18001a60a  mov     [rsi+10h], r12
0x18001a60e  lea     r9, [rsp+2A0h+var_270]
0x18001a613  mov     rcx, [r13+0]
0x18001a617  lea     rdx, aFiletypeassoci; "FileTypeAssociation\\Index\\ProgID"
0x18001a61e  xor     r8d, r8d
0x18001a621  mov     [rsp+2A0h+var_278], rax
0x18001a626  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x18001a62b  mov     [rsp+2A0h+var_270], r12
0x18001a630  mov     [rsp+2A0h+var_268], 1
0x18001a635  call    cs:__imp_SRCacheContext_Open
0x18001a63b  mov     ebx, eax
0x18001a63d  cmp     [rsp+2A0h+var_268], r12b
0x18001a642  jz      short loc_18001A65F
0x18001a644  mov     r8, [rsp+2A0h+var_278]
0x18001a649  mov     rdx, [rsp+2A0h+var_270]
0x18001a64e  mov     rcx, [r8]
0x18001a651  mov     [r8], rdx
0x18001a654  test    rcx, rcx
0x18001a657  jz      short loc_18001A65F
0x18001a659  call    cs:__imp_SRCacheContext_Close
0x18001a65f  test    ebx, ebx
0x18001a661  js      loc_18001A927
0x18001a667  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x18001a66c  test    rbx, rbx
0x18001a66f  setnz   al
0x18001a672  test    al, al
0x18001a674  jz      loc_18001A949
0x18001a67a  xor     edx, edx; Val
0x18001a67c  mov     [rsp+2A0h+var_260], r12
0x18001a681  mov     r8d, 200h; Size
0x18001a687  lea     rcx, [rsp+2A0h+var_258]; void *
0x18001a68c  call    memset_0
0x18001a691  lea     r10, [rsp+2A0h+var_258]
0x18001a696  mov     rcx, r12
0x18001a699  mov     [rbp+1A0h+var_58], rcx
0x18001a6a0  mov     edx, 100h
0x18001a6a5  mov     [rbp+1A0h+var_50], rdx
0x18001a6ac  mov     [rbp+1A0h+Src], r10
0x18001a6b3  test    rdi, rdi
0x18001a6b6  jz      loc_18001A84A
0x18001a6bc  mov     r15, r12
0x18001a6bf  mov     rbx, r12
0x18001a6c2  mov     rax, rdi
0x18001a6c5  mov     r8d, 5Eh ; '^'
0x18001a6cb  cmp     [rax], r12w
0x18001a6cf  jz      short loc_18001A6F1
0x18001a6d1  inc     r15
0x18001a6d4  cmp     r15, 7FFFFFFFh
0x18001a6db  jnb     loc_18001A8F3
0x18001a6e1  cmp     [rax], r8w
0x18001a6e5  jz      loc_18001A96E
0x18001a6eb  add     rax, 2
0x18001a6ef  jmp     short loc_18001A6CB
0x18001a6f1  lea     r14, [r15+1]
0x18001a6f5  add     r14, rbx
0x18001a6f8  cmp     r14, rdx
0x18001a6fb  ja      loc_18001A976
0x18001a701  test    rbx, rbx
0x18001a704  jnz     loc_18001AA0E
0x18001a70a  lea     rax, [rdx-1]
0x18001a70e  mov     r9d, 7FFFFFFEh
0x18001a714  cmp     rax, r9
0x18001a717  ja      loc_18001AA04
0x18001a71d  mov     r8, rdx
0x18001a720  mov     rax, r10
0x18001a723  cmp     [rax], r12w
0x18001a727  jz      short loc_18001A733
0x18001a729  add     rax, 2
0x18001a72d  sub     r8, 1
0x18001a731  jnz     short loc_18001A723
0x18001a733  mov     rax, r8
0x18001a736  mov     ebx, 80070057h
0x18001a73b  neg     rax
0x18001a73e  sbb     ecx, ecx
0x18001a740  not     ecx
0x18001a742  and     ebx, ecx
0x18001a744  test    r8, r8
0x18001a747  jz      loc_18001A8EB
0x18001a74d  mov     rax, rdx
0x18001a750  sub     rax, r8
0x18001a753  test    r8, r8
0x18001a756  jz      short loc_18001A7A8
0x18001a758  lea     r8, [r10+rax*2]
0x18001a75c  sub     rdx, rax
0x18001a75f  jz      short loc_18001A783
0x18001a761  test    r9, r9
0x18001a764  jz      short loc_18001A783
0x18001a766  movzx   eax, word ptr [rdi]
0x18001a769  test    ax, ax
0x18001a76c  jz      short loc_18001A783
0x18001a76e  mov     [r8], ax
0x18001a772  add     rdi, 2
0x18001a776  add     r8, 2
0x18001a77a  dec     r9
0x18001a77d  sub     rdx, 1
0x18001a781  jnz     short loc_18001A761
0x18001a783  mov     rax, rdx
0x18001a786  lea     rcx, [r8-2]
0x18001a78a  neg     rax
0x18001a78d  sbb     ebx, ebx
0x18001a78f  not     ebx
0x18001a791  and     ebx, 8007007Ah
0x18001a797  test    rdx, rdx
0x18001a79a  cmovnz  rcx, r8
0x18001a79e  mov     [rcx], r12w
0x18001a7a2  jnz     loc_18001A837
0x18001a7a8  mov     edx, 139h; void *
0x18001a7ad  lea     rdi, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a7b4  mov     rcx, [rbp+1A8h]; this
0x18001a7bb  mov     r9d, ebx; char *
0x18001a7be  mov     r8, rdi; unsigned int
0x18001a7c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7c6  mov     edx, 29Ch; void *
0x18001a7cb  mov     rcx, [rbp+1A8h]; this
0x18001a7d2  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a7d9  mov     r9d, ebx; char *
0x18001a7dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7e1  mov     rcx, [rsp+2A0h+var_260]
0x18001a7e6  mov     [rsp+2A0h+var_260], r12
0x18001a7eb  test    rcx, rcx
0x18001a7ee  jz      short loc_18001A7F6
0x18001a7f0  call    cs:__imp_SRCache_Free
0x18001a7f6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001a7fb  mov     qword ptr [rsp+2A0h+var_280], r12
0x18001a800  test    rcx, rcx
0x18001a803  jz      short loc_18001A80B
0x18001a805  call    cs:__imp_SRCacheContext_Close
0x18001a80b  mov     eax, ebx
0x18001a80d  mov     rcx, [rbp+1A0h+var_40]
0x18001a814  xor     rcx, rsp; StackCookie
0x18001a817  call    __security_check_cookie
0x18001a81c  mov     rbx, [rsp+2A0h+arg_10]
0x18001a824  add     rsp, 270h
0x18001a82b  pop     r15
0x18001a82d  pop     r14
0x18001a82f  pop     r13
0x18001a831  pop     r12
0x18001a833  pop     rdi
0x18001a834  pop     rsi
0x18001a835  pop     rbp
0x18001a836  retn
0x18001a837  add     [rbp+1A0h+var_58], r15
0x18001a83e  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x18001a843  mov     r10, [rbp+1A0h+Src]
0x18001a84a  lea     r9, [rsp+2A0h+var_270]
0x18001a84f  mov     [rsp+2A0h+var_278], rsi
0x18001a854  xor     r8d, r8d
0x18001a857  mov     [rsp+2A0h+var_270], r12
0x18001a85c  mov     rdx, r10
0x18001a85f  mov     [rsp+2A0h+var_268], 1
0x18001a864  mov     rcx, rbx
0x18001a867  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001a86d  mov     ebx, eax
0x18001a86f  cmp     [rsp+2A0h+var_268], r12b
0x18001a874  jz      short loc_18001A891
0x18001a876  mov     r8, [rsp+2A0h+var_278]
0x18001a87b  mov     rdx, [rsp+2A0h+var_270]
0x18001a880  mov     rcx, [r8]
0x18001a883  mov     [r8], rdx
0x18001a886  test    rcx, rcx
0x18001a889  jz      short loc_18001A891
0x18001a88b  call    cs:__imp_SRCacheContext_Close
0x18001a891  test    ebx, ebx
0x18001a893  js      loc_18001AA47
0x18001a899  cmp     [rsi], r12
0x18001a89c  jnz     loc_18001AA6C
0x18001a8a2  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001a8a7  lea     rdx, aFiletypeassoci; "FileTypeAssociation\\Index\\ProgID"
0x18001a8ae  call    cs:__imp_SRCacheContext_AddToCache
0x18001a8b4  mov     ebx, eax
0x18001a8b6  test    eax, eax
0x18001a8b8  js      short loc_18001A902
0x18001a8ba  mov     rcx, [rsp+2A0h+var_260]
0x18001a8bf  mov     [rsp+2A0h+var_260], r12
0x18001a8c4  test    rcx, rcx
0x18001a8c7  jz      short loc_18001A8CF
0x18001a8c9  call    cs:__imp_SRCache_Free
0x18001a8cf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001a8d4  mov     qword ptr [rsp+2A0h+var_280], r12
0x18001a8d9  test    rcx, rcx
0x18001a8dc  jz      short loc_18001A8E4
0x18001a8de  call    cs:__imp_SRCacheContext_Close
0x18001a8e4  xor     eax, eax
0x18001a8e6  jmp     loc_18001A80D
0x18001a8eb  mov     rax, r12
0x18001a8ee  jmp     loc_18001A753
0x18001a8f3  mov     ebx, 80070057h
0x18001a8f8  mov     edx, 135h
0x18001a8fd  jmp     loc_18001A7AD
0x18001a902  mov     rcx, [rbp+1A8h]; this
0x18001a909  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a910  mov     r9d, ebx; char *
0x18001a913  mov     edx, 1A6h; void *
0x18001a918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a91d  mov     edx, 2A5h
0x18001a922  jmp     loc_18001A7CB
0x18001a927  mov     rcx, [rbp+1A8h]; this
0x18001a92e  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a935  mov     r9d, ebx; char *
0x18001a938  mov     edx, 18Ch; void *
0x18001a93d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a942  mov     edx, 298h
0x18001a947  jmp     short loc_18001A953
0x18001a949  mov     ebx, 80670012h
0x18001a94e  mov     edx, 299h; void *
0x18001a953  mov     rcx, [rbp+1A8h]; this
0x18001a95a  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a961  mov     r9d, ebx; char *
0x18001a964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a969  jmp     loc_18001A7F6
0x18001a96e  inc     rbx
0x18001a971  jmp     loc_18001A6EB
0x18001a976  mov     ecx, r14d
0x18001a979  call    cs:__imp_SRCache_AllocStringBuffer
0x18001a97f  mov     r12, rax
0x18001a982  test    rax, rax
0x18001a985  jnz     short loc_18001A9B4
0x18001a987  mov     rcx, [rbp+1A8h]; this
0x18001a98e  lea     rdi, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a995  mov     ebx, 8007000Eh
0x18001a99a  mov     r8, rdi; unsigned int
0x18001a99d  mov     r9d, ebx; char *
0x18001a9a0  mov     edx, 193h; void *
0x18001a9a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9aa  mov     edx, 136h
0x18001a9af  jmp     loc_18001A7B4
0x18001a9b4  mov     r8, [rbp+1A0h+var_50]
0x18001a9bb  mov     rcx, r12; void *
0x18001a9be  mov     rdx, [rbp+1A0h+Src]; Src
0x18001a9c5  add     r8, r8; Size
0x18001a9c8  call    memcpy_0
0x18001a9cd  mov     rdx, r12
0x18001a9d0  lea     rcx, [rsp+2A0h+var_260]
0x18001a9d5  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x18001a9da  mov     r10, [rsp+2A0h+var_260]
0x18001a9df  xor     r12d, r12d
0x18001a9e2  mov     rcx, [rbp+1A0h+var_58]
0x18001a9e9  mov     rdx, r14
0x18001a9ec  mov     [rbp+1A0h+Src], r10
0x18001a9f3  mov     [rbp+1A0h+var_50], rdx
0x18001a9fa  lea     r8d, [r12+5Eh]
0x18001a9ff  jmp     loc_18001A701
0x18001aa04  mov     ebx, 80070057h
0x18001aa09  jmp     loc_18001A7A8
0x18001aa0e  lea     rcx, [r10+rcx*2]
0x18001aa12  mov     rdx, r12
0x18001aa15  test    r15, r15
0x18001aa18  jz      short loc_18001AA3E
0x18001aa1a  cmp     [rdi], r8w
0x18001aa1e  jnz     short loc_18001AA28
0x18001aa20  mov     [rcx], r8w
0x18001aa24  add     rcx, 2
0x18001aa28  movzx   eax, word ptr [rdi]
0x18001aa2b  inc     rdx
0x18001aa2e  mov     [rcx], ax
0x18001aa31  add     rdi, 2
0x18001aa35  add     rcx, 2
0x18001aa39  cmp     rdx, r15
0x18001aa3c  jb      short loc_18001AA1A
0x18001aa3e  mov     [rcx], r12w
0x18001aa42  jmp     loc_18001A837
0x18001aa47  mov     rcx, [rbp+1A8h]; this
0x18001aa4e  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001aa55  mov     r9d, ebx; char *
0x18001aa58  mov     edx, 1B0h; void *
0x18001aa5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa62  mov     edx, 29Fh
0x18001aa67  jmp     loc_18001A7CB
0x18001aa6c  mov     [rsi+10h], r13
0x18001aa70  jmp     loc_18001A8A2
```
