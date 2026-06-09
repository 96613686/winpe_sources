# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000a38c`
- end: `0x18000a7f6`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `1130`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800093ec`

## callees

- `0x18000a334`
- `0x18000a38c`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x18002e495`
- `0x180036d30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a4d4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a4d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a3f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a3f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a417`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a746`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a7c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a417`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a746`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a7c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a5b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a6b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a7af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a5b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a6b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a7af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000a554`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000a554`

## string_xrefs

- `0x18000a448`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000a690`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000a428`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a757`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000a569`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000a66b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  HRESULT v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned __int64 v15; // rsi
  wchar_t *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rcx
  size_t *v19; // rdx
  unsigned __int64 v20; // r14
  char *v21; // rax
  char *v22; // rdi
  char *v23; // rcx
  size_t *v24; // r8
  _WORD *v25; // rax
  signed __int64 v26; // rax
  __int64 v27; // rdx
  char *v28; // rcx
  char *v29; // rcx
  unsigned __int64 v30; // r8
  wchar_t *i; // rdx
  __int64 v32; // rcx
  char *v33; // rcx
  __int64 v34; // rcx
  int cchToCopy; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  struct StateRepository::Cache::Context_NoThrow *v37; // [rsp+38h] [rbp-C8h]
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  char v39; // [rsp+48h] [rbp-B8h]
  char *v40; // [rsp+50h] [rbp-B0h]
  _BYTE v41[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+258h] [rbp+158h]
  unsigned __int64 v43; // [rsp+260h] [rbp+160h]
  void *Src; // [rsp+268h] [rbp+168h]
  wchar_t pszSrc[20]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = *(_QWORD *)a1;
  v37 = (struct StateRepository::Cache::Context_NoThrow *)&v36;
  v39 = 1;
  v36 = 0;
  v38 = 0;
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v38);
  if ( v39 )
  {
    v9 = *(_QWORD *)v37;
    *(_QWORD *)v37 = v38;
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
      cchToCopy);
    v10 = 433;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      cchToCopy);
LABEL_7:
    v11 = v36;
    v36 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v8;
  }
  if ( !v36 )
  {
    v8 = -2140733422;
    v10 = 434;
    goto LABEL_6;
  }
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v42 = 0;
  v43 = 256;
  Src = v41;
  if ( (unsigned int)_o__ui64tow_s(a2, pszSrc, 17) )
  {
    v8 = -2147418113;
    v14 = 358;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v8,
      cchToCopy);
    v27 = 437;
    goto LABEL_42;
  }
  v15 = 0;
  v16 = pszSrc;
  v17 = 0;
  while ( *v16 )
  {
    if ( ++v15 >= 0x7FFFFFFF )
    {
      v8 = -2147024809;
      v14 = 309;
      goto LABEL_41;
    }
    if ( *v16 == 94 )
      ++v17;
    ++v16;
  }
  v18 = v42;
  v19 = (size_t *)v43;
  v20 = v15 + v17 + v42 + 1;
  if ( v20 <= v43 )
  {
    v22 = (char *)Src;
  }
  else
  {
    v21 = (char *)SRCache_AllocStringBuffer((unsigned int)v20, v43, v13, 94);
    v22 = v21;
    if ( !v21 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        cchToCopy);
      v14 = 310;
      goto LABEL_41;
    }
    memcpy_0(v21, Src, 2 * v43);
    v23 = v40;
    v40 = v22;
    if ( v23 )
    {
      SRCache_Free();
      v22 = v40;
    }
    v18 = v42;
    v19 = (size_t *)v20;
    v43 = v20;
    Src = v22;
  }
  if ( v17 )
  {
    v29 = &v22[2 * v18];
    v30 = 0;
    for ( i = pszSrc; v30 < v15; v29 += 2 )
    {
      if ( *i == 94 )
      {
        *(_WORD *)v29 = 94;
        v29 += 2;
      }
      ++v30;
      *(_WORD *)v29 = *i++;
    }
    *(_WORD *)v29 = 0;
  }
  else
  {
    if ( (unsigned __int64)v19 - 1 > 0x7FFFFFFE )
    {
      v8 = -2147024809;
LABEL_40:
      v14 = 313;
      goto LABEL_41;
    }
    v24 = v19;
    v25 = v22;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      v24 = (size_t *)((char *)v24 - 1);
    }
    while ( v24 );
    v8 = v24 == 0 ? 0x80070057 : 0;
    if ( v24 )
      v26 = (char *)v19 - (char *)v24;
    else
      v26 = 0;
    if ( !v24 )
      goto LABEL_40;
    v8 = StringCopyWorkerW((STRSAFE_LPWSTR)&v22[2 * v26], (size_t)v19 - v26, v24, pszSrc, 0x7FFFFFFEu);
    if ( v8 < 0 )
      goto LABEL_40;
  }
  v42 += v15;
  v37 = a3;
  v38 = 0;
  v39 = 1;
  v8 = SRCacheContext_OpenSubContext(v36, Src, 0, &v38);
  if ( v39 )
  {
    v32 = *(_QWORD *)v37;
    *(_QWORD *)v37 = v38;
    if ( v32 )
      SRCacheContext_Close(v32);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      cchToCopy);
    v27 = 438;
    goto LABEL_42;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v36,
         L"Application\\Data");
  if ( v8 < 0 )
  {
    v27 = 440;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      cchToCopy);
    v28 = v40;
    v40 = 0;
    if ( v28 )
      SRCache_Free();
    goto LABEL_7;
  }
  v33 = v40;
  v40 = 0;
  if ( v33 )
    SRCache_Free();
  v34 = v36;
  v36 = 0;
  if ( v34 )
    SRCacheContext_Close(v34);
  return 0;
}

```

## disassembly

```asm
0x18000a38c  mov     [rsp-8+arg_10], rbx
0x18000a391  push    rbp
0x18000a392  push    rsi
0x18000a393  push    rdi
0x18000a394  push    r12
0x18000a396  push    r13
0x18000a398  push    r14
0x18000a39a  push    r15
0x18000a39c  lea     rbp, [rsp-1A0h]
0x18000a3a4  sub     rsp, 2A0h
0x18000a3ab  mov     rax, cs:__security_cookie
0x18000a3b2  xor     rax, rsp
0x18000a3b5  mov     [rbp+1D0h+var_38], rax
0x18000a3bc  mov     rcx, [rcx]
0x18000a3bf  lea     rax, [rsp+2D0h+var_2A0]
0x18000a3c4  mov     r12, r9
0x18000a3c7  mov     [rsp+2D0h+var_298], rax
0x18000a3cc  mov     r15, r8
0x18000a3cf  mov     [rsp+2D0h+var_288], 1
0x18000a3d4  mov     rdi, rdx
0x18000a3d7  lea     r9, [rsp+2D0h+var_290]
0x18000a3dc  xor     r13d, r13d
0x18000a3df  lea     rdx, aApplicationDat; "Application\\Data"
0x18000a3e6  xor     r8d, r8d
0x18000a3e9  mov     [rsp+2D0h+var_2A0], r13
0x18000a3ee  mov     [rsp+2D0h+var_290], r13
0x18000a3f3  call    cs:__imp_SRCacheContext_Open
0x18000a3f9  mov     ebx, eax
0x18000a3fb  cmp     [rsp+2D0h+var_288], r13b
0x18000a400  jz      short loc_18000A41D
0x18000a402  mov     r8, [rsp+2D0h+var_298]
0x18000a407  mov     rdx, [rsp+2D0h+var_290]
0x18000a40c  mov     rcx, [r8]
0x18000a40f  mov     [r8], rdx
0x18000a412  test    rcx, rcx
0x18000a415  jz      short loc_18000A41D
0x18000a417  call    cs:__imp_SRCacheContext_Close
0x18000a41d  test    ebx, ebx
0x18000a41f  jns     short loc_18000A473
0x18000a421  mov     rcx, [rbp+1D8h]; this
0x18000a428  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a42f  mov     r9d, ebx; char *
0x18000a432  mov     edx, 18Ch; void *
0x18000a437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a43c  mov     edx, 1B1h; void *
0x18000a441  mov     rcx, [rbp+1D8h]; this
0x18000a448  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a44f  mov     r9d, ebx; char *
0x18000a452  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a457  mov     rcx, [rsp+2D0h+var_2A0]
0x18000a45c  mov     [rsp+2D0h+var_2A0], r13
0x18000a461  test    rcx, rcx
0x18000a464  jz      short loc_18000A46C
0x18000a466  call    cs:__imp_SRCacheContext_Close
0x18000a46c  mov     eax, ebx
0x18000a46e  jmp     loc_18000A7CC
0x18000a473  cmp     [rsp+2D0h+var_2A0], r13
0x18000a478  setnz   al
0x18000a47b  test    al, al
0x18000a47d  jnz     short loc_18000A48B
0x18000a47f  mov     ebx, 80670012h
0x18000a484  mov     edx, 1B2h
0x18000a489  jmp     short loc_18000A441
0x18000a48b  xor     edx, edx; Val
0x18000a48d  mov     [rsp+2D0h+var_280], r13
0x18000a492  mov     r8d, 200h; Size
0x18000a498  lea     rcx, [rsp+2D0h+var_278]; void *
0x18000a49d  call    memset_0
0x18000a4a2  mov     r9d, 10h
0x18000a4a8  mov     [rbp+1D0h+var_78], r13
0x18000a4af  lea     rax, [rsp+2D0h+var_278]
0x18000a4b4  mov     [rbp+1D0h+var_70], 100h
0x18000a4bf  lea     rdx, [rbp+1D0h+pszSrc]
0x18000a4c6  mov     [rbp+1D0h+Src], rax
0x18000a4cd  mov     rcx, rdi
0x18000a4d0  lea     r8d, [r9+1]
0x18000a4d4  call    cs:__imp__o__ui64tow_s
0x18000a4da  test    eax, eax
0x18000a4dc  jz      short loc_18000A4ED
0x18000a4de  mov     ebx, 8000FFFFh
0x18000a4e3  mov     edx, 166h
0x18000a4e8  jmp     loc_18000A66B
0x18000a4ed  mov     rsi, r13
0x18000a4f0  lea     rax, [rbp+1D0h+pszSrc]
0x18000a4f7  mov     rbx, r13
0x18000a4fa  mov     r9d, 5Eh ; '^'
0x18000a500  cmp     [rax], r13w
0x18000a504  jz      short loc_18000A530
0x18000a506  inc     rsi
0x18000a509  cmp     rsi, 7FFFFFFFh
0x18000a510  jnb     short loc_18000A521
0x18000a512  cmp     [rax], r9w
0x18000a516  jnz     short loc_18000A51B
0x18000a518  inc     rbx
0x18000a51b  add     rax, 2
0x18000a51f  jmp     short loc_18000A500
0x18000a521  mov     ebx, 80070057h
0x18000a526  mov     edx, 135h
0x18000a52b  jmp     loc_18000A66B
0x18000a530  mov     rcx, [rbp+1D0h+var_78]
0x18000a537  mov     rdx, [rbp+1D0h+var_70]
0x18000a53e  lea     r14, [rcx+1]
0x18000a542  add     r14, rbx
0x18000a545  add     r14, rsi
0x18000a548  cmp     r14, rdx
0x18000a54b  jbe     loc_18000A5E2
0x18000a551  mov     ecx, r14d
0x18000a554  call    cs:__imp_SRCache_AllocStringBuffer
0x18000a55a  mov     rdi, rax
0x18000a55d  test    rax, rax
0x18000a560  jnz     short loc_18000A58F
0x18000a562  mov     rcx, [rbp+1D8h]; this
0x18000a569  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a570  mov     ebx, 8007000Eh
0x18000a575  mov     r8, rdi; unsigned int
0x18000a578  mov     r9d, ebx; char *
0x18000a57b  mov     edx, 193h; void *
0x18000a580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a585  mov     edx, 136h
0x18000a58a  jmp     loc_18000A672
0x18000a58f  mov     r8, [rbp+1D0h+var_70]
0x18000a596  mov     rcx, rdi; void *
0x18000a599  mov     rdx, [rbp+1D0h+Src]; Src
0x18000a5a0  add     r8, r8; Size
0x18000a5a3  call    memcpy_0
0x18000a5a8  mov     rcx, [rsp+2D0h+var_280]
0x18000a5ad  mov     [rsp+2D0h+var_280], rdi
0x18000a5b2  test    rcx, rcx
0x18000a5b5  jz      short loc_18000A5C2
0x18000a5b7  call    cs:__imp_SRCache_Free
0x18000a5bd  mov     rdi, [rsp+2D0h+var_280]
0x18000a5c2  mov     rcx, [rbp+1D0h+var_78]
0x18000a5c9  mov     rdx, r14
0x18000a5cc  mov     [rbp+1D0h+var_70], rdx
0x18000a5d3  mov     r9d, 5Eh ; '^'
0x18000a5d9  mov     [rbp+1D0h+Src], rdi
0x18000a5e0  jmp     short loc_18000A5E9
0x18000a5e2  mov     rdi, [rbp+1D0h+Src]
0x18000a5e9  test    rbx, rbx
0x18000a5ec  jnz     loc_18000A6BD
0x18000a5f2  lea     rax, [rdx-1]
0x18000a5f6  mov     r9d, 7FFFFFFEh
0x18000a5fc  cmp     rax, r9
0x18000a5ff  ja      short loc_18000A661
0x18000a601  mov     r8, rdx
0x18000a604  mov     rax, rdi
0x18000a607  cmp     [rax], r13w
0x18000a60b  jz      short loc_18000A617
0x18000a60d  add     rax, 2
0x18000a611  sub     r8, 1; pcchNewDestLength
0x18000a615  jnz     short loc_18000A607
0x18000a617  mov     rax, r8
0x18000a61a  mov     ebx, 80070057h
0x18000a61f  neg     rax
0x18000a622  sbb     ecx, ecx
0x18000a624  not     ecx
0x18000a626  and     ebx, ecx
0x18000a628  test    r8, r8
0x18000a62b  jz      short loc_18000A635
0x18000a62d  mov     rax, rdx
0x18000a630  sub     rax, r8
0x18000a633  jmp     short loc_18000A638
0x18000a635  mov     rax, r13
0x18000a638  test    r8, r8
0x18000a63b  jz      short loc_18000A666
0x18000a63d  mov     qword ptr [rsp+2D0h+cchToCopy], r9; cchToCopy
0x18000a642  lea     rcx, [rdi+rax*2]; pszDest
0x18000a646  lea     r9, [rbp+1D0h+pszSrc]; pszSrc
0x18000a64d  sub     rdx, rax; cchDest
0x18000a650  call    StringCopyWorkerW
0x18000a655  mov     ebx, eax
0x18000a657  test    eax, eax
0x18000a659  jns     loc_18000A6F8
0x18000a65f  jmp     short loc_18000A666
0x18000a661  mov     ebx, 80070057h
0x18000a666  mov     edx, 139h; void *
0x18000a66b  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a672  mov     rcx, [rbp+1D8h]; this
0x18000a679  mov     r9d, ebx; char *
0x18000a67c  mov     r8, rdi; unsigned int
0x18000a67f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a684  mov     edx, 1B5h; void *
0x18000a689  mov     rcx, [rbp+1D8h]; this
0x18000a690  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a697  mov     r9d, ebx; char *
0x18000a69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a69f  mov     rcx, [rsp+2D0h+var_280]
0x18000a6a4  mov     [rsp+2D0h+var_280], r13
0x18000a6a9  test    rcx, rcx
0x18000a6ac  jz      loc_18000A457
0x18000a6b2  call    cs:__imp_SRCache_Free
0x18000a6b8  jmp     loc_18000A457
0x18000a6bd  lea     rcx, [rdi+rcx*2]
0x18000a6c1  mov     r8, r13
0x18000a6c4  lea     rdx, [rbp+1D0h+pszSrc]
0x18000a6cb  test    rsi, rsi
0x18000a6ce  jz      short loc_18000A6F4
0x18000a6d0  cmp     [rdx], r9w
0x18000a6d4  jnz     short loc_18000A6DE
0x18000a6d6  mov     [rcx], r9w
0x18000a6da  add     rcx, 2
0x18000a6de  movzx   eax, word ptr [rdx]
0x18000a6e1  inc     r8
0x18000a6e4  mov     [rcx], ax
0x18000a6e7  add     rdx, 2
0x18000a6eb  add     rcx, 2
0x18000a6ef  cmp     r8, rsi
0x18000a6f2  jb      short loc_18000A6D0
0x18000a6f4  mov     [rcx], r13w
0x18000a6f8  mov     rdx, [rbp+1D0h+Src]
0x18000a6ff  lea     r9, [rsp+2D0h+var_290]
0x18000a704  mov     rcx, [rsp+2D0h+var_2A0]
0x18000a709  xor     r8d, r8d
0x18000a70c  add     [rbp+1D0h+var_78], rsi
0x18000a713  mov     [rsp+2D0h+var_298], r15
0x18000a718  mov     [rsp+2D0h+var_290], r13
0x18000a71d  mov     [rsp+2D0h+var_288], 1
0x18000a722  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000a728  mov     ebx, eax
0x18000a72a  cmp     [rsp+2D0h+var_288], r13b
0x18000a72f  jz      short loc_18000A74C
0x18000a731  mov     r8, [rsp+2D0h+var_298]
0x18000a736  mov     rdx, [rsp+2D0h+var_290]
0x18000a73b  mov     rcx, [r8]
0x18000a73e  mov     [r8], rdx
0x18000a741  test    rcx, rcx
0x18000a744  jz      short loc_18000A74C
0x18000a746  call    cs:__imp_SRCacheContext_Close
0x18000a74c  test    ebx, ebx
0x18000a74e  jns     short loc_18000A775
0x18000a750  mov     rcx, [rbp+1D8h]; this
0x18000a757  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a75e  mov     r9d, ebx; char *
0x18000a761  mov     edx, 1B0h; void *
0x18000a766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a76b  mov     edx, 1B6h
0x18000a770  jmp     loc_18000A689
0x18000a775  cmp     [r15], r13
0x18000a778  lea     rdx, aApplicationDat; "Application\\Data"
0x18000a77f  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18000a784  setnz   al
0x18000a787  mov     [r12], al
0x18000a78b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000a790  mov     ebx, eax
0x18000a792  test    eax, eax
0x18000a794  jns     short loc_18000A7A0
0x18000a796  mov     edx, 1B8h
0x18000a79b  jmp     loc_18000A689
0x18000a7a0  mov     rcx, [rsp+2D0h+var_280]
0x18000a7a5  mov     [rsp+2D0h+var_280], r13
0x18000a7aa  test    rcx, rcx
0x18000a7ad  jz      short loc_18000A7B5
0x18000a7af  call    cs:__imp_SRCache_Free
0x18000a7b5  mov     rcx, [rsp+2D0h+var_2A0]
0x18000a7ba  mov     [rsp+2D0h+var_2A0], r13
0x18000a7bf  test    rcx, rcx
0x18000a7c2  jz      short loc_18000A7CA
0x18000a7c4  call    cs:__imp_SRCacheContext_Close
0x18000a7ca  xor     eax, eax
0x18000a7cc  mov     rcx, [rbp+1D0h+var_38]
0x18000a7d3  xor     rcx, rsp; StackCookie
0x18000a7d6  call    __security_check_cookie
0x18000a7db  mov     rbx, [rsp+2D0h+arg_10]
0x18000a7e3  add     rsp, 2A0h
0x18000a7ea  pop     r15
0x18000a7ec  pop     r14
0x18000a7ee  pop     r13
0x18000a7f0  pop     r12
0x18000a7f2  pop     rdi
0x18000a7f3  pop     rsi
0x18000a7f4  pop     rbp
0x18000a7f5  retn
```
