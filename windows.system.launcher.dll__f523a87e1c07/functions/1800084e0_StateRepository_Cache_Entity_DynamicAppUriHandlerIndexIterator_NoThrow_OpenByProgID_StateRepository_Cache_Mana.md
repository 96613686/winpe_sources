# StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x1800084e0`
- end: `0x1800089a1`
- name: `?OpenByProgID@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `1217`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006280`
- `0x180008d70`

## callees

- `0x1800084e0`
- `0x180010c04`
- `0x180032730`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008e5a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000881f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000881f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008527`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008585`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008753`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800087e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008834`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008527`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008585`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008753`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800087e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180008834`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800087bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800087bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800088a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800088a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008561`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180008561`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180008804`

## string_xrefs

- `0x180008543`: `DynamicAppUriHandler\Index\ProgID`
- `0x1800087fd`: `DynamicAppUriHandler\Index\ProgID`
- `0x1800086fe`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x180008735`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x1800086d9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800088ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008857`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000887c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000897a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByProgID(
        StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *this,
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
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v31; // rcx
  int v32; // eax
  _BYTE *v33; // rcx
  __int64 v34; // rcx
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
  v8 = SRCacheContext_Open(v7, L"DynamicAppUriHandler\\Index\\ProgID", 0, &v41);
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
    v28 = 753;
    goto LABEL_36;
  }
  v10 = *(_QWORD *)v39;
  if ( !*(_QWORD *)v39 )
  {
    v8 = -2140733422;
    v28 = 754;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)v8,
      v39[0]);
LABEL_37:
    v29 = *(_QWORD *)v39;
    *(_QWORD *)v39 = 0;
    if ( v29 )
      SRCacheContext_Close(v29);
    return v8;
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
        v26 = 757;
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
    v31 = *(_QWORD *)v40;
    *(_QWORD *)v40 = v41;
    if ( v31 )
      SRCacheContext_Close(v31);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v39[0]);
    v26 = 760;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)v8,
      v39[0]);
    v27 = v43;
    v43 = 0;
    if ( v27 )
      SRCache_Free(v27);
    goto LABEL_37;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v32 = SRCacheContext_AddToCache(*(_QWORD *)v39, L"DynamicAppUriHandler\\Index\\ProgID");
  v8 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v32,
      v39[0]);
    v26 = 766;
    goto LABEL_33;
  }
  v33 = v43;
  v43 = 0;
  if ( v33 )
    SRCache_Free(v33);
  v34 = *(_QWORD *)v39;
  *(_QWORD *)v39 = 0;
  if ( v34 )
    SRCacheContext_Close(v34);
  return 0;
}

```

## disassembly

```asm
0x1800084e0  mov     [rsp-8+arg_10], rbx
0x1800084e5  push    rbp
0x1800084e6  push    rsi
0x1800084e7  push    rdi
0x1800084e8  push    r12
0x1800084ea  push    r13
0x1800084ec  push    r14
0x1800084ee  push    r15
0x1800084f0  lea     rbp, [rsp-170h]
0x1800084f8  sub     rsp, 270h
0x1800084ff  mov     rax, cs:__security_cookie
0x180008506  xor     rax, rsp
0x180008509  mov     [rbp+1A0h+var_40], rax
0x180008510  mov     rsi, rcx
0x180008513  xor     r12d, r12d
0x180008516  mov     rcx, [rcx]
0x180008519  mov     rdi, r8
0x18000851c  mov     r13, rdx
0x18000851f  mov     [rsi], r12
0x180008522  test    rcx, rcx
0x180008525  jz      short loc_18000852D
0x180008527  call    cs:__imp_SRCacheContext_Close
0x18000852d  mov     [rsi+8], r12d
0x180008531  lea     rax, [rsp+2A0h+var_280]
0x180008536  mov     [rsi+10h], r12
0x18000853a  lea     r9, [rsp+2A0h+var_270]
0x18000853f  mov     rcx, [r13+0]
0x180008543  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandler\\Index\\ProgID"
0x18000854a  xor     r8d, r8d
0x18000854d  mov     [rsp+2A0h+var_278], rax
0x180008552  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x180008557  mov     [rsp+2A0h+var_270], r12
0x18000855c  mov     [rsp+2A0h+var_268], 1
0x180008561  call    cs:__imp_SRCacheContext_Open
0x180008567  mov     ebx, eax
0x180008569  cmp     [rsp+2A0h+var_268], r12b
0x18000856e  jz      short loc_18000858B
0x180008570  mov     r8, [rsp+2A0h+var_278]
0x180008575  mov     rdx, [rsp+2A0h+var_270]
0x18000857a  mov     rcx, [r8]
0x18000857d  mov     [r8], rdx
0x180008580  test    rcx, rcx
0x180008583  jz      short loc_18000858B
0x180008585  call    cs:__imp_SRCacheContext_Close
0x18000858b  test    ebx, ebx
0x18000858d  js      loc_180008875
0x180008593  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180008598  test    rbx, rbx
0x18000859b  setnz   al
0x18000859e  test    al, al
0x1800085a0  jz      loc_180008724
0x1800085a6  xor     edx, edx; Val
0x1800085a8  mov     [rsp+2A0h+var_260], r12
0x1800085ad  mov     r8d, 200h; Size
0x1800085b3  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800085b8  call    memset_0
0x1800085bd  lea     r10, [rsp+2A0h+var_258]
0x1800085c2  mov     rcx, r12
0x1800085c5  mov     [rbp+1A0h+var_58], rcx
0x1800085cc  mov     edx, 100h
0x1800085d1  mov     [rbp+1A0h+var_50], rdx
0x1800085d8  mov     [rbp+1A0h+Src], r10
0x1800085df  test    rdi, rdi
0x1800085e2  jz      loc_1800087A0
0x1800085e8  mov     r15, r12
0x1800085eb  mov     rbx, r12
0x1800085ee  mov     rax, rdi
0x1800085f1  mov     r8d, 5Eh ; '^'
0x1800085f7  cmp     [rax], r12w
0x1800085fb  jz      short loc_18000861D
0x1800085fd  inc     r15
0x180008600  cmp     r15, 7FFFFFFFh
0x180008607  jnb     loc_180008841
0x18000860d  cmp     [rax], r8w
0x180008611  jz      loc_18000889A
0x180008617  add     rax, 2
0x18000861b  jmp     short loc_1800085F7
0x18000861d  lea     r14, [r15+1]
0x180008621  add     r14, rbx
0x180008624  cmp     r14, rdx
0x180008627  ja      loc_1800088A2
0x18000862d  test    rbx, rbx
0x180008630  jnz     loc_18000893A
0x180008636  lea     rax, [rdx-1]
0x18000863a  mov     r9d, 7FFFFFFEh
0x180008640  cmp     rax, r9
0x180008643  ja      loc_180008930
0x180008649  mov     r8, rdx
0x18000864c  mov     rax, r10
0x18000864f  cmp     [rax], r12w
0x180008653  jz      short loc_18000865F
0x180008655  add     rax, 2
0x180008659  sub     r8, 1
0x18000865d  jnz     short loc_18000864F
0x18000865f  mov     rax, r8
0x180008662  mov     ebx, 80070057h
0x180008667  neg     rax
0x18000866a  sbb     ecx, ecx
0x18000866c  not     ecx
0x18000866e  and     ebx, ecx
0x180008670  test    r8, r8
0x180008673  jz      loc_180008785
0x180008679  mov     rax, rdx
0x18000867c  sub     rax, r8
0x18000867f  test    r8, r8
0x180008682  jz      short loc_1800086D4
0x180008684  lea     r8, [r10+rax*2]
0x180008688  sub     rdx, rax
0x18000868b  jz      short loc_1800086AF
0x18000868d  test    r9, r9
0x180008690  jz      short loc_1800086AF
0x180008692  movzx   eax, word ptr [rdi]
0x180008695  test    ax, ax
0x180008698  jz      short loc_1800086AF
0x18000869a  mov     [r8], ax
0x18000869e  add     rdi, 2
0x1800086a2  add     r8, 2
0x1800086a6  dec     r9
0x1800086a9  sub     rdx, 1
0x1800086ad  jnz     short loc_18000868D
0x1800086af  mov     rax, rdx
0x1800086b2  lea     rcx, [r8-2]
0x1800086b6  neg     rax
0x1800086b9  sbb     ebx, ebx
0x1800086bb  not     ebx
0x1800086bd  and     ebx, 8007007Ah
0x1800086c3  test    rdx, rdx
0x1800086c6  cmovnz  rcx, r8
0x1800086ca  mov     [rcx], r12w
0x1800086ce  jnz     loc_18000878D
0x1800086d4  mov     edx, 139h; void *
0x1800086d9  lea     rdi, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800086e0  mov     rcx, [rbp+1A8h]; this
0x1800086e7  mov     r9d, ebx; char *
0x1800086ea  mov     r8, rdi; unsigned int
0x1800086ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086f2  mov     edx, 2F5h; void *
0x1800086f7  mov     rcx, [rbp+1A8h]; this
0x1800086fe  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008705  mov     r9d, ebx; char *
0x180008708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000870d  mov     rcx, [rsp+2A0h+var_260]
0x180008712  mov     [rsp+2A0h+var_260], r12
0x180008717  test    rcx, rcx
0x18000871a  jz      short loc_180008744
0x18000871c  call    cs:__imp_SRCache_Free
0x180008722  jmp     short loc_180008744
0x180008724  mov     ebx, 80670012h
0x180008729  mov     edx, 2F2h; void *
0x18000872e  mov     rcx, [rbp+1A8h]; this
0x180008735  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000873c  mov     r9d, ebx; char *
0x18000873f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008744  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180008749  mov     qword ptr [rsp+2A0h+var_280], r12
0x18000874e  test    rcx, rcx
0x180008751  jz      short loc_180008759
0x180008753  call    cs:__imp_SRCacheContext_Close
0x180008759  mov     eax, ebx
0x18000875b  mov     rcx, [rbp+1A0h+var_40]
0x180008762  xor     rcx, rsp; StackCookie
0x180008765  call    __security_check_cookie
0x18000876a  mov     rbx, [rsp+2A0h+arg_10]
0x180008772  add     rsp, 270h
0x180008779  pop     r15
0x18000877b  pop     r14
0x18000877d  pop     r13
0x18000877f  pop     r12
0x180008781  pop     rdi
0x180008782  pop     rsi
0x180008783  pop     rbp
0x180008784  retn
0x180008785  mov     rax, r12
0x180008788  jmp     loc_18000867F
0x18000878d  add     [rbp+1A0h+var_58], r15
0x180008794  mov     rbx, qword ptr [rsp+2A0h+var_280]
0x180008799  mov     r10, [rbp+1A0h+Src]
0x1800087a0  lea     r9, [rsp+2A0h+var_270]
0x1800087a5  mov     [rsp+2A0h+var_278], rsi
0x1800087aa  xor     r8d, r8d
0x1800087ad  mov     [rsp+2A0h+var_270], r12
0x1800087b2  mov     rdx, r10
0x1800087b5  mov     [rsp+2A0h+var_268], 1
0x1800087ba  mov     rcx, rbx
0x1800087bd  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800087c3  mov     ebx, eax
0x1800087c5  cmp     [rsp+2A0h+var_268], r12b
0x1800087ca  jz      short loc_1800087E7
0x1800087cc  mov     r8, [rsp+2A0h+var_278]
0x1800087d1  mov     rdx, [rsp+2A0h+var_270]
0x1800087d6  mov     rcx, [r8]
0x1800087d9  mov     [r8], rdx
0x1800087dc  test    rcx, rcx
0x1800087df  jz      short loc_1800087E7
0x1800087e1  call    cs:__imp_SRCacheContext_Close
0x1800087e7  test    ebx, ebx
0x1800087e9  js      loc_180008973
0x1800087ef  cmp     [rsi], r12
0x1800087f2  jnz     loc_180008998
0x1800087f8  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800087fd  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandler\\Index\\ProgID"
0x180008804  call    cs:__imp_SRCacheContext_AddToCache
0x18000880a  mov     ebx, eax
0x18000880c  test    eax, eax
0x18000880e  js      short loc_180008850
0x180008810  mov     rcx, [rsp+2A0h+var_260]
0x180008815  mov     [rsp+2A0h+var_260], r12
0x18000881a  test    rcx, rcx
0x18000881d  jz      short loc_180008825
0x18000881f  call    cs:__imp_SRCache_Free
0x180008825  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000882a  mov     qword ptr [rsp+2A0h+var_280], r12
0x18000882f  test    rcx, rcx
0x180008832  jz      short loc_18000883A
0x180008834  call    cs:__imp_SRCacheContext_Close
0x18000883a  xor     eax, eax
0x18000883c  jmp     loc_18000875B
0x180008841  mov     ebx, 80070057h
0x180008846  mov     edx, 135h
0x18000884b  jmp     loc_1800086D9
0x180008850  mov     rcx, [rbp+1A8h]; this
0x180008857  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000885e  mov     r9d, ebx; char *
0x180008861  mov     edx, 1A6h; void *
0x180008866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000886b  mov     edx, 2FEh
0x180008870  jmp     loc_1800086F7
0x180008875  mov     rcx, [rbp+1A8h]; this
0x18000887c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008883  mov     r9d, ebx; char *
0x180008886  mov     edx, 18Ch; void *
0x18000888b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008890  mov     edx, 2F1h
0x180008895  jmp     loc_18000872E
0x18000889a  inc     rbx
0x18000889d  jmp     loc_180008617
0x1800088a2  mov     ecx, r14d
0x1800088a5  call    cs:__imp_SRCache_AllocStringBuffer
0x1800088ab  mov     r12, rax
0x1800088ae  test    rax, rax
0x1800088b1  jnz     short loc_1800088E0
0x1800088b3  mov     rcx, [rbp+1A8h]; this
0x1800088ba  lea     rdi, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800088c1  mov     ebx, 8007000Eh
0x1800088c6  mov     r8, rdi; unsigned int
0x1800088c9  mov     r9d, ebx; char *
0x1800088cc  mov     edx, 193h; void *
0x1800088d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088d6  mov     edx, 136h
0x1800088db  jmp     loc_1800086E0
0x1800088e0  mov     r8, [rbp+1A0h+var_50]
0x1800088e7  mov     rcx, r12; void *
0x1800088ea  mov     rdx, [rbp+1A0h+Src]; Src
0x1800088f1  add     r8, r8; Size
0x1800088f4  call    memcpy_0
0x1800088f9  mov     rdx, r12
0x1800088fc  lea     rcx, [rsp+2A0h+var_260]
0x180008901  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x180008906  mov     r10, [rsp+2A0h+var_260]
0x18000890b  xor     r12d, r12d
0x18000890e  mov     rcx, [rbp+1A0h+var_58]
0x180008915  mov     rdx, r14
0x180008918  mov     [rbp+1A0h+Src], r10
0x18000891f  mov     [rbp+1A0h+var_50], rdx
0x180008926  lea     r8d, [r12+5Eh]
0x18000892b  jmp     loc_18000862D
0x180008930  mov     ebx, 80070057h
0x180008935  jmp     loc_1800086D4
0x18000893a  lea     rcx, [r10+rcx*2]
0x18000893e  mov     rdx, r12
0x180008941  test    r15, r15
0x180008944  jz      short loc_18000896A
0x180008946  cmp     [rdi], r8w
0x18000894a  jnz     short loc_180008954
0x18000894c  mov     [rcx], r8w
0x180008950  add     rcx, 2
0x180008954  movzx   eax, word ptr [rdi]
0x180008957  inc     rdx
0x18000895a  mov     [rcx], ax
0x18000895d  add     rdi, 2
0x180008961  add     rcx, 2
0x180008965  cmp     rdx, r15
0x180008968  jb      short loc_180008946
0x18000896a  mov     [rcx], r12w
0x18000896e  jmp     loc_18000878D
0x180008973  mov     rcx, [rbp+1A8h]; this
0x18000897a  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008981  mov     r9d, ebx; char *
0x180008984  mov     edx, 1B0h; void *
0x180008989  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000898e  mov     edx, 2F8h
0x180008993  jmp     loc_1800086F7
0x180008998  mov     [rsi+10h], r13
0x18000899c  jmp     loc_1800087F8
```
