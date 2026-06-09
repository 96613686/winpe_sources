# StateRepository::Cache::Macros::Evaluators::Package::CurrentDirectoryPath(void *,ushort * *)

- ea: `0x180037230`
- end: `0x1800373be`
- name: `?CurrentDirectoryPath@Package@Evaluators@Macros@Cache@StateRepository@@YAJPEAXPEAPEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(StateRepository::Cache::Macros::Evaluators::Package *__hidden this, void *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800088c0`
- `0x180015040`
- `0x18001b008`
- `0x18001cc38`
- `0x180036960`
- `0x180037230`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x1800372d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18003737a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x1800372d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18003737a`

## string_xrefs

- `0x180037252`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x1800372ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x18003738f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Macros::Evaluators::Package::CurrentDirectoryPath(
        StateRepository::Cache::Macros::Evaluators::Package *this,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  __int64 *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-39h]
  int v14; // [rsp+20h] [rbp-39h]
  __int128 v15; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+40h] [rbp-19h]
  __int64 v17; // [rsp+48h] [rbp-11h]
  __int128 v18; // [rsp+50h] [rbp-9h]
  __int128 v19; // [rsp+60h] [rbp+7h]
  __int128 v20; // [rsp+70h] [rbp+17h]
  __int128 v21; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v23; // [rsp+C0h] [rbp+67h] BYREF

  *a2 = 0;
  if ( !this )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)0x80070057LL,
      v13);
    return v4;
  }
  v6 = *((_QWORD *)this + 5);
  v7 = *(__int64 **)this;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    *(_QWORD *)&v20 = 0;
    DWORD2(v20) = 0;
    LOBYTE(v23) = 0;
    v8 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(v7, v6, a3, &v15);
    v4 = v8;
    if ( v8 >= 0 )
    {
      if ( !(_BYTE)v23 || (v8 = SRCache_DuplicateString(*((_QWORD *)&v19 + 1), a2), v4 = v8, v8 >= 0) )
      {
        v4 = 0;
        goto LABEL_12;
      }
      v9 = 58;
    }
    else
    {
      v9 = 55;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)(unsigned int)v8,
      (int)&v23);
LABEL_12:
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v15);
    return v4;
  }
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v16 = 0;
    v15 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    LOBYTE(v23) = 0;
    v11 = StateRepository::Cache::Entity::Application_NoThrow::Get(v7, v10, 256, (__int64)&v15, (bool *)&v23);
    v4 = v11;
    if ( v11 >= 0 )
    {
      if ( !(_BYTE)v23 || (v11 = SRCache_DuplicateString(v20, a2), v4 = v11, v11 >= 0) )
      {
        v4 = 0;
        goto LABEL_21;
      }
      v12 = 72;
    }
    else
    {
      v12 = 69;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)(unsigned int)v11,
      v14);
LABEL_21:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v15);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180037230  push    rbp
0x180037232  push    rbx
0x180037233  push    rsi
0x180037234  push    rdi
0x180037235  lea     rbp, [rsp-3Fh]
0x18003723a  sub     rsp, 98h
0x180037241  xor     esi, esi
0x180037243  mov     rdi, rdx
0x180037246  mov     [rdx], rsi
0x180037249  test    rcx, rcx
0x18003724c  jnz     short loc_180037270
0x18003724e  mov     rcx, [rbp+5Fh]; this
0x180037252  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037259  mov     ebx, 80070057h
0x18003725e  lea     edx, [rsi+2Ch]; void *
0x180037261  mov     r9d, ebx; char *
0x180037264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037269  mov     eax, ebx
0x18003726b  jmp     loc_1800373B2
0x180037270  mov     rdx, [rcx+28h]
0x180037274  mov     rax, [rcx]
0x180037277  test    rdx, rdx
0x18003727a  jz      loc_18003730D
0x180037280  xorps   xmm0, xmm0
0x180037283  mov     [rbp+57h+var_70], rsi
0x180037287  lea     rcx, [rbp+57h+arg_0]
0x18003728b  movdqa  [rbp+57h+var_80], xmm0
0x180037290  mov     qword ptr [rsp+0B0h+var_90], rcx; int
0x180037295  lea     r9, [rbp+57h+var_80]
0x180037299  xorps   xmm1, xmm1
0x18003729c  mov     [rbp+57h+var_68], rsi
0x1800372a0  mov     rcx, rax
0x1800372a3  movdqa  [rbp+57h+var_60], xmm0
0x1800372a8  movdqa  [rbp+57h+var_50], xmm1
0x1800372ad  mov     qword ptr [rbp+57h+var_40], rsi
0x1800372b1  mov     dword ptr [rbp+57h+var_40+8], esi
0x1800372b4  mov     byte ptr [rbp+57h+arg_0], sil
0x1800372b8  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800372bd  mov     ebx, eax
0x1800372bf  test    eax, eax
0x1800372c1  jns     short loc_1800372CA
0x1800372c3  mov     edx, 37h ; '7'
0x1800372c8  jmp     short loc_1800372E8
0x1800372ca  cmp     byte ptr [rbp+57h+arg_0], sil
0x1800372ce  jz      short loc_1800372FD
0x1800372d0  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x1800372d4  mov     rdx, rdi
0x1800372d7  call    cs:__imp_SRCache_DuplicateString
0x1800372dd  mov     ebx, eax
0x1800372df  test    eax, eax
0x1800372e1  jns     short loc_1800372FD
0x1800372e3  mov     edx, 3Ah ; ':'; void *
0x1800372e8  mov     rcx, [rbp+5Fh]; this
0x1800372ec  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800372f3  mov     r9d, eax; char *
0x1800372f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800372fb  jmp     short loc_1800372FF
0x1800372fd  mov     ebx, esi
0x1800372ff  lea     rcx, [rbp+57h+var_80]; this
0x180037303  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180037308  jmp     loc_180037269
0x18003730d  mov     rdx, [rcx+18h]
0x180037311  test    rdx, rdx
0x180037314  jz      loc_1800373B0
0x18003731a  xorps   xmm0, xmm0
0x18003731d  mov     [rbp+57h+var_70], rsi
0x180037321  xorps   xmm1, xmm1
0x180037324  movdqa  [rbp+57h+var_80], xmm0
0x180037329  lea     rcx, [rbp+57h+arg_0]
0x18003732d  mov     [rbp+57h+var_68], rsi
0x180037331  mov     qword ptr [rsp+0B0h+var_90], rcx; int
0x180037336  lea     r9, [rbp+57h+var_80]
0x18003733a  mov     rcx, rax
0x18003733d  movdqa  [rbp+57h+var_60], xmm0
0x180037342  mov     r8d, 100h
0x180037348  movdqa  [rbp+57h+var_50], xmm1
0x18003734d  movdqa  [rbp+57h+var_40], xmm0
0x180037352  movdqa  [rbp+57h+var_30], xmm1
0x180037357  mov     byte ptr [rbp+57h+arg_0], sil
0x18003735b  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180037360  mov     ebx, eax
0x180037362  test    eax, eax
0x180037364  jns     short loc_18003736D
0x180037366  mov     edx, 45h ; 'E'
0x18003736b  jmp     short loc_18003738B
0x18003736d  cmp     byte ptr [rbp+57h+arg_0], sil
0x180037371  jz      short loc_1800373A0
0x180037373  mov     rcx, qword ptr [rbp+57h+var_40]
0x180037377  mov     rdx, rdi
0x18003737a  call    cs:__imp_SRCache_DuplicateString
0x180037380  mov     ebx, eax
0x180037382  test    eax, eax
0x180037384  jns     short loc_1800373A0
0x180037386  mov     edx, 48h ; 'H'; void *
0x18003738b  mov     rcx, [rbp+5Fh]; this
0x18003738f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037396  mov     r9d, eax; char *
0x180037399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003739e  jmp     short loc_1800373A2
0x1800373a0  mov     ebx, esi
0x1800373a2  lea     rcx, [rbp+57h+var_80]; this
0x1800373a6  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800373ab  jmp     loc_180037269
0x1800373b0  xor     eax, eax
0x1800373b2  add     rsp, 98h
0x1800373b9  pop     rdi
0x1800373ba  pop     rsi
0x1800373bb  pop     rbx
0x1800373bc  pop     rbp
0x1800373bd  retn
```
