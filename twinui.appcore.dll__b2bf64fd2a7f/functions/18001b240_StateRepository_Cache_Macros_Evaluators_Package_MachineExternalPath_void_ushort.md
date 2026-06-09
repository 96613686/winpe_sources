# StateRepository::Cache::Macros::Evaluators::Package::MachineExternalPath(void *,ushort * *)

- ea: `0x18001b240`
- end: `0x18001b381`
- name: `?MachineExternalPath@Package@Evaluators@Macros@Cache@StateRepository@@YAJPEAXPEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(StateRepository::Cache::Macros::Evaluators::Package *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800373d0`

## callees

- `0x18001b240`
- `0x18001cc38`
- `0x180037d54`
- `0x180039b88`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18001b340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_DuplicateString` at `0x18001b340`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b328`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b328`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b364`

## string_xrefs

- `0x18001b26b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x18001b29d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`
- `0x18001b304`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Macros-Evaluators.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Macros::Evaluators::Package::MachineExternalPath(
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
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  int v15[4]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  *a2 = 0;
  if ( !this )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)0x80070057LL,
      v14);
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
      *(_OWORD *)v15 = 0;
      v16 = 0;
      v4 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(v6, 0, v9);
      if ( (v4 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
          (const char *)v4,
          (int)v15);
        v12 = *((_QWORD *)&v16 + 1);
        *((_QWORD *)&v16 + 1) = 0;
        if ( v12 )
          SRCache_Free(v12, v11);
        return v4;
      }
      v13 = *((_QWORD *)&v16 + 1);
      *((_QWORD *)&v16 + 1) = 0;
      if ( v13 )
        SRCache_Free(v13, v10);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Macros-Evaluators.hpp",
      (const char *)(unsigned int)v7,
      v14);
    return v8;
  }
}

```

## disassembly

```asm
0x18001b240  mov     [rsp-18h+arg_8], rbx
0x18001b245  mov     [rsp-18h+arg_10], rsi
0x18001b24a  push    rbp
0x18001b24b  push    rdi
0x18001b24c  push    r14
0x18001b24e  mov     rbp, rsp
0x18001b251  sub     rsp, 50h
0x18001b255  mov     qword ptr [rdx], 0
0x18001b25c  mov     rsi, rdx
0x18001b25f  mov     rbx, rcx
0x18001b262  test    rcx, rcx
0x18001b265  jnz     short loc_18001B28B
0x18001b267  mov     rcx, [rbp+18h]; this
0x18001b26b  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b272  mov     ebx, 80070057h
0x18001b277  mov     edx, 7Fh; void *
0x18001b27c  mov     r9d, ebx; char *
0x18001b27f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b284  mov     eax, ebx
0x18001b286  jmp     loc_18001B36C
0x18001b28b  mov     r14, [rcx]
0x18001b28e  call    ?ResolvePackage@MacroExpandData_NoThrow@Macros@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Macros::MacroExpandData_NoThrow::ResolvePackage(void)
0x18001b293  mov     edi, eax
0x18001b295  test    eax, eax
0x18001b297  jns     short loc_18001B2B8
0x18001b299  mov     rcx, [rbp+18h]; this
0x18001b29d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b2a4  mov     r9d, eax; char *
0x18001b2a7  mov     edx, 84h; void *
0x18001b2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b2b1  mov     eax, edi
0x18001b2b3  jmp     loc_18001B36C
0x18001b2b8  mov     r8, [rbx+10h]
0x18001b2bc  test    r8, r8
0x18001b2bf  jz      loc_18001B36A
0x18001b2c5  lea     rax, [rbp+arg_0]
0x18001b2c9  mov     [rbp+arg_0], 0
0x18001b2cd  mov     [rsp+50h+var_28], rax
0x18001b2d2  xorps   xmm0, xmm0
0x18001b2d5  lea     rax, [rbp+var_20]
0x18001b2d9  xorps   xmm1, xmm1
0x18001b2dc  xor     edx, edx
0x18001b2de  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001b2e3  mov     rcx, r14
0x18001b2e6  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001b2eb  movdqu  [rbp+var_10], xmm1
0x18001b2f0  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18001b2f5  mov     ebx, eax
0x18001b2f7  test    eax, eax
0x18001b2f9  jns     short loc_18001B333
0x18001b2fb  mov     edx, 8Bh; void *
0x18001b300  mov     rcx, [rbp+18h]; this
0x18001b304  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b30b  mov     r9d, ebx; char *
0x18001b30e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b313  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b317  mov     qword ptr [rbp+var_10+8], 0
0x18001b31f  test    rcx, rcx
0x18001b322  jz      loc_18001B284
0x18001b328  call    cs:__imp_SRCache_Free
0x18001b32e  jmp     loc_18001B284
0x18001b333  cmp     [rbp+arg_0], 0
0x18001b337  jz      short loc_18001B353
0x18001b339  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b33d  mov     rdx, rsi
0x18001b340  call    cs:__imp_SRCache_DuplicateString
0x18001b346  mov     ebx, eax
0x18001b348  test    eax, eax
0x18001b34a  jns     short loc_18001B353
0x18001b34c  mov     edx, 8Eh
0x18001b351  jmp     short loc_18001B300
0x18001b353  mov     rcx, qword ptr [rbp+var_10+8]
0x18001b357  mov     qword ptr [rbp+var_10+8], 0
0x18001b35f  test    rcx, rcx
0x18001b362  jz      short loc_18001B36A
0x18001b364  call    cs:__imp_SRCache_Free
0x18001b36a  xor     eax, eax
0x18001b36c  lea     r11, [rsp+50h+var_s0]
0x18001b371  mov     rbx, [r11+28h]
0x18001b375  mov     rsi, [r11+30h]
0x18001b379  mov     rsp, r11
0x18001b37c  pop     r14
0x18001b37e  pop     rdi
0x18001b37f  pop     rbp
0x18001b380  retn
```
