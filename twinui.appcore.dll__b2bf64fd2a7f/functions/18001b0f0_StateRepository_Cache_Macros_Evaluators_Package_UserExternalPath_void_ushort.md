# StateRepository::Cache::Macros::Evaluators::Package::UserExternalPath(void *,ushort * *)

- ea: `0x18001b0f0`
- end: `0x18001b233`
- name: `?UserExternalPath@Package@Evaluators@Macros@Cache@StateRepository@@YAJPEAXPEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(StateRepository::Cache::Macros::Evaluators::Package *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800373d0`

## callees

- `0x18001b0f0`
- `0x18001cc38`
- `0x180037d54`
- `0x180039b88`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18001b1f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18001b1f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b1da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b216`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b1da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b216`

## string_xrefs

- `0x18001b11b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x18001b14d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x18001b1b6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Macros::Evaluators::Package::UserExternalPath(
        StateRepository::Cache::Macros::Evaluators::Package *this,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // r14
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-30h]
  int v16[4]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v17; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  *a2 = 0;
  if ( !this )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)0x80070057LL,
      v15);
    return v4;
  }
  v6 = *(_QWORD *)this;
  v7 = StateRepository::Cache::Macros::MacroExpandData_NoThrow::ResolvePackage(this);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = *((_QWORD *)this + 2);
    if ( v9 )
    {
      v10 = *((_QWORD *)this + 1);
      *(_OWORD *)v16 = 0;
      v17 = 0;
      v4 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(v6, v10, v9);
      if ( (v4 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
          (const char *)v4,
          (int)v16);
        v13 = *((_QWORD *)&v17 + 1);
        *((_QWORD *)&v17 + 1) = 0;
        if ( v13 )
          SRCache_Free(v13, v12);
        return v4;
      }
      v14 = *((_QWORD *)&v17 + 1);
      *((_QWORD *)&v17 + 1) = 0;
      if ( v14 )
        SRCache_Free(v14, v11);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)(unsigned int)v7,
      v15);
    return v8;
  }
}

```

## disassembly

```asm
0x18001b0f0  mov     [rsp-18h+arg_8], rbx
0x18001b0f5  mov     [rsp-18h+arg_10], rsi
0x18001b0fa  push    rbp
0x18001b0fb  push    rdi
0x18001b0fc  push    r14
0x18001b0fe  mov     rbp, rsp
0x18001b101  sub     rsp, 50h
0x18001b105  mov     qword ptr [rdx], 0
0x18001b10c  mov     rsi, rdx
0x18001b10f  mov     rbx, rcx
0x18001b112  test    rcx, rcx
0x18001b115  jnz     short loc_18001B13B
0x18001b117  mov     rcx, [rbp+18h]; this
0x18001b11b  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b122  mov     ebx, 80070057h
0x18001b127  mov     edx, 64h ; 'd'; void *
0x18001b12c  mov     r9d, ebx; char *
0x18001b12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b134  mov     eax, ebx
0x18001b136  jmp     loc_18001B21E
0x18001b13b  mov     r14, [rcx]
0x18001b13e  call    ?ResolvePackage@MacroExpandData_NoThrow@Macros@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Macros::MacroExpandData_NoThrow::ResolvePackage(void)
0x18001b143  mov     edi, eax
0x18001b145  test    eax, eax
0x18001b147  jns     short loc_18001B168
0x18001b149  mov     rcx, [rbp+18h]; this
0x18001b14d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b154  mov     r9d, eax; char *
0x18001b157  mov     edx, 69h ; 'i'; void *
0x18001b15c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b161  mov     eax, edi
0x18001b163  jmp     loc_18001B21E
0x18001b168  mov     r8, [rbx+10h]
0x18001b16c  test    r8, r8
0x18001b16f  jz      loc_18001B21C
0x18001b175  mov     rdx, [rbx+8]
0x18001b179  lea     rax, [rbp+arg_0]
0x18001b17d  mov     [rsp+50h+var_28], rax
0x18001b182  xorps   xmm0, xmm0
0x18001b185  lea     rax, [rbp+var_20]
0x18001b189  mov     [rbp+arg_0], 0
0x18001b18d  xorps   xmm1, xmm1
0x18001b190  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001b195  mov     rcx, r14
0x18001b198  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001b19d  movdqu  [rbp+var_10], xmm1
0x18001b1a2  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18001b1a7  mov     ebx, eax
0x18001b1a9  test    eax, eax
0x18001b1ab  jns     short loc_18001B1E5
0x18001b1ad  mov     edx, 70h ; 'p'; void *
0x18001b1b2  mov     rcx, [rbp+18h]; this
0x18001b1b6  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b1bd  mov     r9d, ebx; char *
0x18001b1c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1c5  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b1c9  mov     qword ptr [rbp+var_10+8], 0
0x18001b1d1  test    rcx, rcx
0x18001b1d4  jz      loc_18001B134
0x18001b1da  call    cs:__imp_SRCache_Free
0x18001b1e0  jmp     loc_18001B134
0x18001b1e5  cmp     [rbp+arg_0], 0
0x18001b1e9  jz      short loc_18001B205
0x18001b1eb  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b1ef  mov     rdx, rsi
0x18001b1f2  call    cs:__imp_SRCache_DuplicateString
0x18001b1f8  mov     ebx, eax
0x18001b1fa  test    eax, eax
0x18001b1fc  jns     short loc_18001B205
0x18001b1fe  mov     edx, 73h ; 's'
0x18001b203  jmp     short loc_18001B1B2
0x18001b205  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b209  mov     qword ptr [rbp+var_10+8], 0
0x18001b211  test    rcx, rcx
0x18001b214  jz      short loc_18001B21C
0x18001b216  call    cs:__imp_SRCache_Free
0x18001b21c  xor     eax, eax
0x18001b21e  lea     r11, [rsp+50h+var_s0]
0x18001b223  mov     rbx, [r11+28h]
0x18001b227  mov     rsi, [r11+30h]
0x18001b22b  mov     rsp, r11
0x18001b22e  pop     r14
0x18001b230  pop     rdi
0x18001b231  pop     rbp
0x18001b232  retn
```
