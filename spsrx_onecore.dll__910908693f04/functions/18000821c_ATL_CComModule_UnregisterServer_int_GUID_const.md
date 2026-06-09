# ATL::CComModule::UnregisterServer(int,_GUID const *)

- ea: `0x18000821c`
- end: `0x1800082e0`
- name: `?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800088f0`

## callees

- `0x180006598`
- `0x18000821c`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ATL::CComModule::UnregisterServer(ATL::CComModule *this, __int64 a2, const struct _GUID *a3)
{
  __int64 v3; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax
  int result; // eax
  __int64 *v6; // rbx
  unsigned __int64 v7; // rcx
  __int64 v8; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v9; // rax

  v3 = qword_1800152F8;
  if ( qword_1800152F8 )
  {
    while ( *(_QWORD *)v3 )
    {
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 0);
      if ( result < 0 )
        return result;
      result = (*(__int64 (__fastcall **)(_QWORD))(v3 + 8))(0);
      if ( result < 0 )
        return result;
      v3 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
  {
    result = 0;
    v6 = (__int64 *)qword_1800153C0;
    v7 = qword_1800153C8;
    while ( (unsigned __int64)v6 < v7 )
    {
      v8 = *v6;
      if ( *v6 )
      {
        v9 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v8 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v8, v9, 0);
        if ( result < 0 )
          return result;
        result = (*(__int64 (__fastcall **)(_QWORD))(v8 + 8))(0);
        if ( result < 0 )
          return result;
        v7 = qword_1800153C8;
      }
      ++v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000821c  mov     [rsp+arg_0], rbx
0x180008221  push    rdi
0x180008222  sub     rsp, 20h
0x180008226  mov     rbx, cs:qword_1800152F8
0x18000822d  test    rbx, rbx
0x180008230  jz      short loc_18000826C
0x180008232  jmp     short loc_180008266
0x180008234  mov     rax, [rbx+38h]
0x180008238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823d  xor     r8d, r8d; int
0x180008240  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180008243  mov     rcx, [rbx]; rguid
0x180008246  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000824b  test    eax, eax
0x18000824d  js      loc_1800082D5
0x180008253  xor     ecx, ecx
0x180008255  mov     rax, [rbx+8]
0x180008259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825e  test    eax, eax
0x180008260  js      short loc_1800082D5
0x180008262  add     rbx, 48h ; 'H'
0x180008266  cmp     qword ptr [rbx], 0
0x18000826a  jnz     short loc_180008234
0x18000826c  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180008273  test    rax, rax
0x180008276  jz      short loc_180008281
0x180008278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827d  test    eax, eax
0x18000827f  js      short loc_1800082D5
0x180008281  xor     eax, eax
0x180008283  mov     rbx, cs:qword_1800153C0
0x18000828a  mov     rcx, cs:qword_1800153C8
0x180008291  jmp     short loc_1800082D0
0x180008293  mov     rdi, [rbx]
0x180008296  test    rdi, rdi
0x180008299  jz      short loc_1800082CC
0x18000829b  mov     rax, [rdi+38h]
0x18000829f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a4  xor     r8d, r8d; int
0x1800082a7  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800082aa  mov     rcx, [rdi]; rguid
0x1800082ad  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800082b2  test    eax, eax
0x1800082b4  js      short loc_1800082D5
0x1800082b6  xor     ecx, ecx
0x1800082b8  mov     rax, [rdi+8]
0x1800082bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c1  test    eax, eax
0x1800082c3  js      short loc_1800082D5
0x1800082c5  mov     rcx, cs:qword_1800153C8
0x1800082cc  add     rbx, 8
0x1800082d0  cmp     rbx, rcx
0x1800082d3  jb      short loc_180008293
0x1800082d5  mov     rbx, [rsp+28h+arg_0]
0x1800082da  add     rsp, 20h
0x1800082de  pop     rdi
0x1800082df  retn
```
