# DllRegisterServer

- ea: `0x180013790`
- end: `0x180013881`
- name: `DllRegisterServer`
- size: `241`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180010440`
- `0x1800109ec`
- `0x180013790`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *i; // rcx
  __int64 v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  v1 = qword_18001BDB8;
  if ( qword_18001BDB8 )
  {
    while ( *(_QWORD *)v1 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v1 + 8))(1);
      if ( result < 0 )
        return result;
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v3, 1);
      if ( result < 0 )
        return result;
      v1 += 72;
    }
  }
  v4 = (__int64 *)off_18001B630[0];
  for ( i = (__int64 *)off_18001B638; v4 < i; ++v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v6 + 8))(1);
      if ( result < 0 )
        return result;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
      if ( result < 0 )
        return result;
      i = (__int64 *)off_18001B638;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_18001B628, v0);
  if ( result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HINSTANCE))ATL::_pPerfRegFunc)(hInstance);
  }
  return result;
}

```

## disassembly

```asm
0x180013790  mov     [rsp+arg_0], rbx
0x180013795  push    rdi
0x180013796  sub     rsp, 20h
0x18001379a  mov     rbx, cs:qword_18001BDB8
0x1800137a1  test    rbx, rbx
0x1800137a4  jz      short loc_1800137EA
0x1800137a6  jmp     short loc_1800137E4
0x1800137a8  mov     rax, [rbx+8]
0x1800137ac  mov     ecx, 1
0x1800137b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137b6  test    eax, eax
0x1800137b8  js      loc_180013876
0x1800137be  mov     rax, [rbx+38h]
0x1800137c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137c7  mov     rcx, [rbx]; rguid
0x1800137ca  mov     r8d, 1; int
0x1800137d0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800137d3  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800137d8  test    eax, eax
0x1800137da  js      loc_180013876
0x1800137e0  add     rbx, 48h ; 'H'
0x1800137e4  cmp     qword ptr [rbx], 0
0x1800137e8  jnz     short loc_1800137A8
0x1800137ea  mov     rbx, cs:off_18001B630
0x1800137f1  xor     eax, eax
0x1800137f3  mov     rcx, cs:off_18001B638
0x1800137fa  cmp     rbx, rcx
0x1800137fd  jnb     short loc_18001384B
0x1800137ff  mov     rdi, [rbx]
0x180013802  test    rdi, rdi
0x180013805  jz      short loc_18001383E
0x180013807  mov     rax, [rdi+8]
0x18001380b  mov     ecx, 1
0x180013810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013815  test    eax, eax
0x180013817  js      short loc_180013876
0x180013819  mov     rax, [rdi+38h]
0x18001381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013822  mov     rcx, [rdi]; rguid
0x180013825  mov     r8d, 1; int
0x18001382b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001382e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013833  test    eax, eax
0x180013835  js      short loc_180013876
0x180013837  mov     rcx, cs:off_18001B638
0x18001383e  add     rbx, 8
0x180013842  cmp     rbx, rcx
0x180013845  jb      short loc_1800137FF
0x180013847  test    eax, eax
0x180013849  js      short loc_180013876
0x18001384b  mov     rcx, cs:off_18001B628; HINSTANCE
0x180013852  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180013857  test    eax, eax
0x180013859  js      short loc_180013876
0x18001385b  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180013862  test    rdx, rdx
0x180013865  jz      short loc_180013876
0x180013867  mov     rcx, cs:hInstance
0x18001386e  mov     rax, rdx
0x180013871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013876  mov     rbx, [rsp+28h+arg_0]
0x18001387b  add     rsp, 20h
0x18001387f  pop     rdi
0x180013880  retn
```
