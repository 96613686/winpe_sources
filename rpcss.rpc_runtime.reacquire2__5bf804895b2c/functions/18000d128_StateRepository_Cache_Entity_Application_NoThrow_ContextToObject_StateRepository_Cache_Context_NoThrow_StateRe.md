# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x18000d128`
- end: `0x18000d526`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009979c`

## callees

- `0x18000d128`
- `0x18000d52c`
- `0x18000d574`
- `0x1800210f8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d468`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d498`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d515`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d468`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d498`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d4fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d515`

## string_xrefs

- `0x18000d2ed`: `CurrentDirectoryPath`
- `0x18000d41d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000d43b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // esi
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rcx
  int v15; // edi
  unsigned __int16 *v16; // rcx
  __int64 v18; // rdx
  unsigned __int16 **v19; // [rsp+20h] [rbp-28h]
  unsigned __int16 **v20; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v21; // [rsp+28h] [rbp-20h] BYREF
  char v22; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Package", (unsigned int *)(a2 + 8));
  if ( Field < 0 )
  {
    v18 = 1159;
    goto LABEL_39;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Index", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v18 = 1163;
    goto LABEL_39;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  if ( Field < 0 )
  {
    v18 = 1167;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 24);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageRelativeApplicationId", &v21);
  if ( v22 )
  {
    v8 = *v19;
    *v19 = v21;
    if ( v8 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1171;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 32);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ApplicationUserModelId", &v21);
  if ( v22 )
  {
    v9 = *v19;
    *v19 = v21;
    if ( v9 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1175;
    goto LABEL_39;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 40));
  if ( Field < 0 )
  {
    v18 = 1179;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)Field,
      (int)v19);
    return (unsigned int)Field;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 48);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v21);
  if ( v22 )
  {
    v10 = *v19;
    *v19 = v21;
    if ( v10 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1183;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 56);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v21);
  if ( v22 )
  {
    v11 = *v19;
    *v19 = v21;
    if ( v11 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1187;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 64);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v21);
  if ( v22 )
  {
    v12 = *v19;
    *v19 = v21;
    if ( v12 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1191;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 72);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Executable", &v21);
  if ( v22 )
  {
    v13 = *v19;
    *v19 = v21;
    if ( v13 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1195;
    goto LABEL_39;
  }
  v21 = 0;
  v19 = (unsigned __int16 **)(a2 + 80);
  v22 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v21);
  if ( v22 )
  {
    v14 = *v19;
    *v19 = v21;
    if ( v14 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v18 = 1199;
    goto LABEL_39;
  }
  v21 = 0;
  v20 = (unsigned __int16 **)(a2 + 88);
  v22 = 1;
  v15 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"StartPage", &v21);
  if ( v22 )
  {
    v16 = *v20;
    *v20 = v21;
    if ( v16 )
      SRCache_Free();
  }
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      (int)v20);
    return (unsigned int)v15;
  }
  else
  {
    *(_QWORD *)a2 = a4;
    return 0;
  }
}

```

## disassembly

```asm
0x18000d128  push    rbp
0x18000d12a  push    rbx
0x18000d12b  push    rsi
0x18000d12c  push    rdi
0x18000d12d  push    r14
0x18000d12f  push    r15
0x18000d131  mov     rbp, rsp
0x18000d134  sub     rsp, 48h
0x18000d138  mov     rbx, rdx
0x18000d13b  lea     r8, [rdx+8]; unsigned int *
0x18000d13f  lea     rdx, aPackage; "Package"
0x18000d146  mov     r14, r9
0x18000d149  mov     rdi, rcx
0x18000d14c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18000d151  xor     r15d, r15d
0x18000d154  mov     esi, eax
0x18000d156  test    eax, eax
0x18000d158  js      loc_18000D45A
0x18000d15e  lea     r8, [rbx+10h]; unsigned int *
0x18000d162  mov     rcx, rdi; this
0x18000d165  lea     rdx, aIndex; "Index"
0x18000d16c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18000d171  mov     esi, eax
0x18000d173  test    eax, eax
0x18000d175  js      loc_18000D430
0x18000d17b  lea     r8, [rbx+14h]; unsigned int *
0x18000d17f  mov     rcx, rdi; this
0x18000d182  lea     rdx, aFlags; "Flags"
0x18000d189  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18000d18e  mov     esi, eax
0x18000d190  test    eax, eax
0x18000d192  js      loc_18000D461
0x18000d198  lea     rax, [rbx+18h]
0x18000d19c  mov     [rbp+var_20], r15
0x18000d1a0  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d1a4  mov     [rbp+var_28], rax
0x18000d1a8  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x18000d1af  mov     [rbp+var_18], 1
0x18000d1b3  mov     rcx, rdi; this
0x18000d1b6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d1bb  mov     esi, eax
0x18000d1bd  cmp     [rbp+var_18], r15b
0x18000d1c1  jz      short loc_18000D1DA
0x18000d1c3  mov     r8, [rbp+var_28]
0x18000d1c7  mov     rdx, [rbp+var_20]
0x18000d1cb  mov     rcx, [r8]
0x18000d1ce  mov     [r8], rdx
0x18000d1d1  test    rcx, rcx
0x18000d1d4  jnz     loc_18000D468
0x18000d1da  test    esi, esi
0x18000d1dc  js      loc_18000D479
0x18000d1e2  lea     rax, [rbx+20h]
0x18000d1e6  mov     [rbp+var_20], r15
0x18000d1ea  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d1ee  mov     [rbp+var_28], rax
0x18000d1f2  lea     rdx, aApplicationuse; "ApplicationUserModelId"
0x18000d1f9  mov     [rbp+var_18], 1
0x18000d1fd  mov     rcx, rdi; this
0x18000d200  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d205  mov     esi, eax
0x18000d207  cmp     [rbp+var_18], r15b
0x18000d20b  jz      short loc_18000D224
0x18000d20d  mov     r8, [rbp+var_28]
0x18000d211  mov     rdx, [rbp+var_20]
0x18000d215  mov     rcx, [r8]
0x18000d218  mov     [r8], rdx
0x18000d21b  test    rcx, rcx
0x18000d21e  jnz     loc_18000D480
0x18000d224  test    esi, esi
0x18000d226  js      loc_18000D491
0x18000d22c  lea     r8, [rbx+28h]; unsigned int *
0x18000d230  mov     rcx, rdi; this
0x18000d233  lea     rdx, aActivation; "Activation"
0x18000d23a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18000d23f  mov     esi, eax
0x18000d241  test    eax, eax
0x18000d243  js      loc_18000D414
0x18000d249  lea     rax, [rbx+30h]
0x18000d24d  mov     [rbp+var_20], r15
0x18000d251  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d255  mov     [rbp+var_28], rax
0x18000d259  lea     rdx, aHostid; "HostId"
0x18000d260  mov     [rbp+var_18], 1
0x18000d264  mov     rcx, rdi; this
0x18000d267  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d26c  mov     esi, eax
0x18000d26e  cmp     [rbp+var_18], r15b
0x18000d272  jz      short loc_18000D28B
0x18000d274  mov     r8, [rbp+var_28]
0x18000d278  mov     rdx, [rbp+var_20]
0x18000d27c  mov     rcx, [r8]
0x18000d27f  mov     [r8], rdx
0x18000d282  test    rcx, rcx
0x18000d285  jnz     loc_18000D498
0x18000d28b  test    esi, esi
0x18000d28d  js      loc_18000D4A9
0x18000d293  lea     rax, [rbx+38h]
0x18000d297  mov     [rbp+var_20], r15
0x18000d29b  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d29f  mov     [rbp+var_28], rax
0x18000d2a3  lea     rdx, aParameters; "Parameters"
0x18000d2aa  mov     [rbp+var_18], 1
0x18000d2ae  mov     rcx, rdi; this
0x18000d2b1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d2b6  mov     esi, eax
0x18000d2b8  cmp     [rbp+var_18], r15b
0x18000d2bc  jz      short loc_18000D2D5
0x18000d2be  mov     r8, [rbp+var_28]
0x18000d2c2  mov     rdx, [rbp+var_20]
0x18000d2c6  mov     rcx, [r8]
0x18000d2c9  mov     [r8], rdx
0x18000d2cc  test    rcx, rcx
0x18000d2cf  jnz     loc_18000D4B3
0x18000d2d5  test    esi, esi
0x18000d2d7  js      loc_18000D4C4
0x18000d2dd  lea     rax, [rbx+40h]
0x18000d2e1  mov     [rbp+var_20], r15
0x18000d2e5  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d2e9  mov     [rbp+var_28], rax
0x18000d2ed  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x18000d2f4  mov     [rbp+var_18], 1
0x18000d2f8  mov     rcx, rdi; this
0x18000d2fb  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d300  mov     esi, eax
0x18000d302  cmp     [rbp+var_18], r15b
0x18000d306  jz      short loc_18000D31F
0x18000d308  mov     r8, [rbp+var_28]
0x18000d30c  mov     rdx, [rbp+var_20]
0x18000d310  mov     rcx, [r8]
0x18000d313  mov     [r8], rdx
0x18000d316  test    rcx, rcx
0x18000d319  jnz     loc_18000D4CE
0x18000d31f  test    esi, esi
0x18000d321  js      loc_18000D4DF
0x18000d327  lea     rax, [rbx+48h]
0x18000d32b  mov     [rbp+var_20], r15
0x18000d32f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d333  mov     [rbp+var_28], rax
0x18000d337  lea     rdx, aExecutable; "Executable"
0x18000d33e  mov     [rbp+var_18], 1
0x18000d342  mov     rcx, rdi; this
0x18000d345  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d34a  mov     esi, eax
0x18000d34c  cmp     [rbp+var_18], r15b
0x18000d350  jz      short loc_18000D369
0x18000d352  mov     r8, [rbp+var_28]
0x18000d356  mov     rdx, [rbp+var_20]
0x18000d35a  mov     rcx, [r8]
0x18000d35d  mov     [r8], rdx
0x18000d360  test    rcx, rcx
0x18000d363  jnz     loc_18000D4E9
0x18000d369  test    esi, esi
0x18000d36b  js      loc_18000D453
0x18000d371  lea     rax, [rbx+50h]
0x18000d375  mov     [rbp+var_20], r15
0x18000d379  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d37d  mov     [rbp+var_28], rax
0x18000d381  lea     rdx, aEntrypoint; "Entrypoint"
0x18000d388  mov     [rbp+var_18], 1
0x18000d38c  mov     rcx, rdi; this
0x18000d38f  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d394  mov     esi, eax
0x18000d396  cmp     [rbp+var_18], r15b
0x18000d39a  jz      short loc_18000D3B3
0x18000d39c  mov     r8, [rbp+var_28]
0x18000d3a0  mov     rdx, [rbp+var_20]
0x18000d3a4  mov     rcx, [r8]
0x18000d3a7  mov     [r8], rdx
0x18000d3aa  test    rcx, rcx
0x18000d3ad  jnz     loc_18000D4FA
0x18000d3b3  test    esi, esi
0x18000d3b5  js      loc_18000D50B
0x18000d3bb  lea     rax, [rbx+58h]
0x18000d3bf  mov     [rbp+var_20], r15
0x18000d3c3  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000d3c7  mov     [rbp+var_28], rax
0x18000d3cb  lea     rdx, aStartpage; "StartPage"
0x18000d3d2  mov     [rbp+var_18], 1
0x18000d3d6  mov     rcx, rdi; this
0x18000d3d9  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000d3de  mov     edi, eax
0x18000d3e0  cmp     [rbp+var_18], r15b
0x18000d3e4  jz      short loc_18000D3FD
0x18000d3e6  mov     r8, [rbp+var_28]
0x18000d3ea  mov     rdx, [rbp+var_20]
0x18000d3ee  mov     rcx, [r8]
0x18000d3f1  mov     [r8], rdx
0x18000d3f4  test    rcx, rcx
0x18000d3f7  jnz     loc_18000D515
0x18000d3fd  test    edi, edi
0x18000d3ff  js      short loc_18000D437
0x18000d401  mov     [rbx], r14
0x18000d404  xor     eax, eax
0x18000d406  add     rsp, 48h
0x18000d40a  pop     r15
0x18000d40c  pop     r14
0x18000d40e  pop     rdi
0x18000d40f  pop     rsi
0x18000d410  pop     rbx
0x18000d411  pop     rbp
0x18000d412  retn
0x18000d414  mov     edx, 49Bh; void *
0x18000d419  mov     rcx, [rbp+30h]; this
0x18000d41d  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d424  mov     r9d, esi; char *
0x18000d427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d42c  mov     eax, esi
0x18000d42e  jmp     short loc_18000D406
0x18000d430  mov     edx, 48Bh
0x18000d435  jmp     short loc_18000D419
0x18000d437  mov     rcx, [rbp+30h]; this
0x18000d43b  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d442  mov     r9d, edi; char *
0x18000d445  mov     edx, 4B3h; void *
0x18000d44a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d44f  mov     eax, edi
0x18000d451  jmp     short loc_18000D406
0x18000d453  mov     edx, 4ABh
0x18000d458  jmp     short loc_18000D419
0x18000d45a  mov     edx, 487h
0x18000d45f  jmp     short loc_18000D419
0x18000d461  mov     edx, 48Fh
0x18000d466  jmp     short loc_18000D419
0x18000d468  call    cs:__imp_SRCache_Free
0x18000d46f  nop     dword ptr [rax+rax+00h]
0x18000d474  jmp     loc_18000D1DA
0x18000d479  mov     edx, 493h
0x18000d47e  jmp     short loc_18000D419
0x18000d480  call    cs:__imp_SRCache_Free
0x18000d487  nop     dword ptr [rax+rax+00h]
0x18000d48c  jmp     loc_18000D224
0x18000d491  mov     edx, 497h
0x18000d496  jmp     short loc_18000D419
0x18000d498  call    cs:__imp_SRCache_Free
0x18000d49f  nop     dword ptr [rax+rax+00h]
0x18000d4a4  jmp     loc_18000D28B
0x18000d4a9  mov     edx, 49Fh
0x18000d4ae  jmp     loc_18000D419
0x18000d4b3  call    cs:__imp_SRCache_Free
0x18000d4ba  nop     dword ptr [rax+rax+00h]
0x18000d4bf  jmp     loc_18000D2D5
0x18000d4c4  mov     edx, 4A3h
0x18000d4c9  jmp     loc_18000D419
0x18000d4ce  call    cs:__imp_SRCache_Free
0x18000d4d5  nop     dword ptr [rax+rax+00h]
0x18000d4da  jmp     loc_18000D31F
0x18000d4df  mov     edx, 4A7h
0x18000d4e4  jmp     loc_18000D419
0x18000d4e9  call    cs:__imp_SRCache_Free
0x18000d4f0  nop     dword ptr [rax+rax+00h]
0x18000d4f5  jmp     loc_18000D369
0x18000d4fa  call    cs:__imp_SRCache_Free
0x18000d501  nop     dword ptr [rax+rax+00h]
0x18000d506  jmp     loc_18000D3B3
0x18000d50b  mov     edx, 4AFh
0x18000d510  jmp     loc_18000D419
0x18000d515  call    cs:__imp_SRCache_Free
0x18000d51c  nop     dword ptr [rax+rax+00h]
0x18000d521  jmp     loc_18000D3FD
```
