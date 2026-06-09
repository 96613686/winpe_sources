# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x18001f3d4`
- end: `0x18001f7a1`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180094190`

## callees

- `0x18001f3d4`
- `0x18001f7a8`
- `0x18001f7e8`
- `0x18002ba28`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f713`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f725`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f74c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f776`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f781`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f796`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f713`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f725`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f74c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f776`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f781`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001f796`

## string_xrefs

- `0x18001f599`: `CurrentDirectoryPath`
- `0x18001f6c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18001f6e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

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
0x18001f3d4  push    rbp
0x18001f3d6  push    rbx
0x18001f3d7  push    rsi
0x18001f3d8  push    rdi
0x18001f3d9  push    r14
0x18001f3db  push    r15
0x18001f3dd  mov     rbp, rsp
0x18001f3e0  sub     rsp, 48h
0x18001f3e4  mov     rbx, rdx
0x18001f3e7  lea     r8, [rdx+8]; unsigned int *
0x18001f3eb  lea     rdx, aPackage; "Package"
0x18001f3f2  mov     r14, r9
0x18001f3f5  mov     rdi, rcx
0x18001f3f8  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001f3fd  xor     r15d, r15d
0x18001f400  mov     esi, eax
0x18001f402  test    eax, eax
0x18001f404  js      loc_18001F705
0x18001f40a  lea     r8, [rbx+10h]; unsigned int *
0x18001f40e  mov     rcx, rdi; this
0x18001f411  lea     rdx, aIndex; "Index"
0x18001f418  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001f41d  mov     esi, eax
0x18001f41f  test    eax, eax
0x18001f421  js      loc_18001F6DB
0x18001f427  lea     r8, [rbx+14h]; unsigned int *
0x18001f42b  mov     rcx, rdi; this
0x18001f42e  lea     rdx, aFlags; "Flags"
0x18001f435  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001f43a  mov     esi, eax
0x18001f43c  test    eax, eax
0x18001f43e  js      loc_18001F70C
0x18001f444  lea     rax, [rbx+18h]
0x18001f448  mov     [rbp+var_20], r15
0x18001f44c  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f450  mov     [rbp+var_28], rax
0x18001f454  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x18001f45b  mov     [rbp+var_18], 1
0x18001f45f  mov     rcx, rdi; this
0x18001f462  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f467  mov     esi, eax
0x18001f469  cmp     [rbp+var_18], r15b
0x18001f46d  jz      short loc_18001F486
0x18001f46f  mov     r8, [rbp+var_28]
0x18001f473  mov     rdx, [rbp+var_20]
0x18001f477  mov     rcx, [r8]
0x18001f47a  mov     [r8], rdx
0x18001f47d  test    rcx, rcx
0x18001f480  jnz     loc_18001F713
0x18001f486  test    esi, esi
0x18001f488  js      loc_18001F71E
0x18001f48e  lea     rax, [rbx+20h]
0x18001f492  mov     [rbp+var_20], r15
0x18001f496  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f49a  mov     [rbp+var_28], rax
0x18001f49e  lea     rdx, aApplicationuse; "ApplicationUserModelId"
0x18001f4a5  mov     [rbp+var_18], 1
0x18001f4a9  mov     rcx, rdi; this
0x18001f4ac  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f4b1  mov     esi, eax
0x18001f4b3  cmp     [rbp+var_18], r15b
0x18001f4b7  jz      short loc_18001F4D0
0x18001f4b9  mov     r8, [rbp+var_28]
0x18001f4bd  mov     rdx, [rbp+var_20]
0x18001f4c1  mov     rcx, [r8]
0x18001f4c4  mov     [r8], rdx
0x18001f4c7  test    rcx, rcx
0x18001f4ca  jnz     loc_18001F725
0x18001f4d0  test    esi, esi
0x18001f4d2  js      loc_18001F730
0x18001f4d8  lea     r8, [rbx+28h]; unsigned int *
0x18001f4dc  mov     rcx, rdi; this
0x18001f4df  lea     rdx, aActivation; "Activation"
0x18001f4e6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001f4eb  mov     esi, eax
0x18001f4ed  test    eax, eax
0x18001f4ef  js      loc_18001F6BF
0x18001f4f5  lea     rax, [rbx+30h]
0x18001f4f9  mov     [rbp+var_20], r15
0x18001f4fd  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f501  mov     [rbp+var_28], rax
0x18001f505  lea     rdx, aHostid; "HostId"
0x18001f50c  mov     [rbp+var_18], 1
0x18001f510  mov     rcx, rdi; this
0x18001f513  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f518  mov     esi, eax
0x18001f51a  cmp     [rbp+var_18], r15b
0x18001f51e  jz      short loc_18001F537
0x18001f520  mov     r8, [rbp+var_28]
0x18001f524  mov     rdx, [rbp+var_20]
0x18001f528  mov     rcx, [r8]
0x18001f52b  mov     [r8], rdx
0x18001f52e  test    rcx, rcx
0x18001f531  jnz     loc_18001F737
0x18001f537  test    esi, esi
0x18001f539  js      loc_18001F742
0x18001f53f  lea     rax, [rbx+38h]
0x18001f543  mov     [rbp+var_20], r15
0x18001f547  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f54b  mov     [rbp+var_28], rax
0x18001f54f  lea     rdx, aParameters; "Parameters"
0x18001f556  mov     [rbp+var_18], 1
0x18001f55a  mov     rcx, rdi; this
0x18001f55d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f562  mov     esi, eax
0x18001f564  cmp     [rbp+var_18], r15b
0x18001f568  jz      short loc_18001F581
0x18001f56a  mov     r8, [rbp+var_28]
0x18001f56e  mov     rdx, [rbp+var_20]
0x18001f572  mov     rcx, [r8]
0x18001f575  mov     [r8], rdx
0x18001f578  test    rcx, rcx
0x18001f57b  jnz     loc_18001F74C
0x18001f581  test    esi, esi
0x18001f583  js      loc_18001F757
0x18001f589  lea     rax, [rbx+40h]
0x18001f58d  mov     [rbp+var_20], r15
0x18001f591  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f595  mov     [rbp+var_28], rax
0x18001f599  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x18001f5a0  mov     [rbp+var_18], 1
0x18001f5a4  mov     rcx, rdi; this
0x18001f5a7  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f5ac  mov     esi, eax
0x18001f5ae  cmp     [rbp+var_18], r15b
0x18001f5b2  jz      short loc_18001F5CB
0x18001f5b4  mov     r8, [rbp+var_28]
0x18001f5b8  mov     rdx, [rbp+var_20]
0x18001f5bc  mov     rcx, [r8]
0x18001f5bf  mov     [r8], rdx
0x18001f5c2  test    rcx, rcx
0x18001f5c5  jnz     loc_18001F761
0x18001f5cb  test    esi, esi
0x18001f5cd  js      loc_18001F76C
0x18001f5d3  lea     rax, [rbx+48h]
0x18001f5d7  mov     [rbp+var_20], r15
0x18001f5db  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f5df  mov     [rbp+var_28], rax
0x18001f5e3  lea     rdx, aExecutable; "Executable"
0x18001f5ea  mov     [rbp+var_18], 1
0x18001f5ee  mov     rcx, rdi; this
0x18001f5f1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f5f6  mov     esi, eax
0x18001f5f8  cmp     [rbp+var_18], r15b
0x18001f5fc  jz      short loc_18001F615
0x18001f5fe  mov     r8, [rbp+var_28]
0x18001f602  mov     rdx, [rbp+var_20]
0x18001f606  mov     rcx, [r8]
0x18001f609  mov     [r8], rdx
0x18001f60c  test    rcx, rcx
0x18001f60f  jnz     loc_18001F776
0x18001f615  test    esi, esi
0x18001f617  js      loc_18001F6FE
0x18001f61d  lea     rax, [rbx+50h]
0x18001f621  mov     [rbp+var_20], r15
0x18001f625  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f629  mov     [rbp+var_28], rax
0x18001f62d  lea     rdx, aEntrypoint; "Entrypoint"
0x18001f634  mov     [rbp+var_18], 1
0x18001f638  mov     rcx, rdi; this
0x18001f63b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f640  mov     esi, eax
0x18001f642  cmp     [rbp+var_18], r15b
0x18001f646  jz      short loc_18001F65F
0x18001f648  mov     r8, [rbp+var_28]
0x18001f64c  mov     rdx, [rbp+var_20]
0x18001f650  mov     rcx, [r8]
0x18001f653  mov     [r8], rdx
0x18001f656  test    rcx, rcx
0x18001f659  jnz     loc_18001F781
0x18001f65f  test    esi, esi
0x18001f661  js      loc_18001F78C
0x18001f667  lea     rax, [rbx+58h]
0x18001f66b  mov     [rbp+var_20], r15
0x18001f66f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18001f673  mov     [rbp+var_28], rax
0x18001f677  lea     rdx, aStartpage; "StartPage"
0x18001f67e  mov     [rbp+var_18], 1
0x18001f682  mov     rcx, rdi; this
0x18001f685  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001f68a  mov     edi, eax
0x18001f68c  cmp     [rbp+var_18], r15b
0x18001f690  jz      short loc_18001F6A9
0x18001f692  mov     r8, [rbp+var_28]
0x18001f696  mov     rdx, [rbp+var_20]
0x18001f69a  mov     rcx, [r8]
0x18001f69d  mov     [r8], rdx
0x18001f6a0  test    rcx, rcx
0x18001f6a3  jnz     loc_18001F796
0x18001f6a9  test    edi, edi
0x18001f6ab  js      short loc_18001F6E2
0x18001f6ad  mov     [rbx], r14
0x18001f6b0  xor     eax, eax
0x18001f6b2  add     rsp, 48h
0x18001f6b6  pop     r15
0x18001f6b8  pop     r14
0x18001f6ba  pop     rdi
0x18001f6bb  pop     rsi
0x18001f6bc  pop     rbx
0x18001f6bd  pop     rbp
0x18001f6be  retn
0x18001f6bf  mov     edx, 49Bh; void *
0x18001f6c4  mov     rcx, [rbp+30h]; this
0x18001f6c8  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f6cf  mov     r9d, esi; char *
0x18001f6d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6d7  mov     eax, esi
0x18001f6d9  jmp     short loc_18001F6B2
0x18001f6db  mov     edx, 48Bh
0x18001f6e0  jmp     short loc_18001F6C4
0x18001f6e2  mov     rcx, [rbp+30h]; this
0x18001f6e6  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001f6ed  mov     r9d, edi; char *
0x18001f6f0  mov     edx, 4B3h; void *
0x18001f6f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6fa  mov     eax, edi
0x18001f6fc  jmp     short loc_18001F6B2
0x18001f6fe  mov     edx, 4ABh
0x18001f703  jmp     short loc_18001F6C4
0x18001f705  mov     edx, 487h
0x18001f70a  jmp     short loc_18001F6C4
0x18001f70c  mov     edx, 48Fh
0x18001f711  jmp     short loc_18001F6C4
0x18001f713  call    cs:__imp_SRCache_Free
0x18001f719  jmp     loc_18001F486
0x18001f71e  mov     edx, 493h
0x18001f723  jmp     short loc_18001F6C4
0x18001f725  call    cs:__imp_SRCache_Free
0x18001f72b  jmp     loc_18001F4D0
0x18001f730  mov     edx, 497h
0x18001f735  jmp     short loc_18001F6C4
0x18001f737  call    cs:__imp_SRCache_Free
0x18001f73d  jmp     loc_18001F537
0x18001f742  mov     edx, 49Fh
0x18001f747  jmp     loc_18001F6C4
0x18001f74c  call    cs:__imp_SRCache_Free
0x18001f752  jmp     loc_18001F581
0x18001f757  mov     edx, 4A3h
0x18001f75c  jmp     loc_18001F6C4
0x18001f761  call    cs:__imp_SRCache_Free
0x18001f767  jmp     loc_18001F5CB
0x18001f76c  mov     edx, 4A7h
0x18001f771  jmp     loc_18001F6C4
0x18001f776  call    cs:__imp_SRCache_Free
0x18001f77c  jmp     loc_18001F615
0x18001f781  call    cs:__imp_SRCache_Free
0x18001f787  jmp     loc_18001F65F
0x18001f78c  mov     edx, 4AFh
0x18001f791  jmp     loc_18001F6C4
0x18001f796  call    cs:__imp_SRCache_Free
0x18001f79c  jmp     loc_18001F6A9
```
