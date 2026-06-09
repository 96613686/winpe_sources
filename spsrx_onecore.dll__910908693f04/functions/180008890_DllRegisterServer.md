# DllRegisterServer

- ea: `0x180008890`
- end: `0x1800088ea`
- name: `DllRegisterServer`
- size: `90`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006598`
- `0x180007854`
- `0x180008890`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax

  v0 = qword_1800152F8;
  if ( qword_1800152F8 )
  {
    while ( *(_QWORD *)v0 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
      if ( result < 0 )
        return result;
      v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v2, 1);
      if ( result < 0 )
        return result;
      v0 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
}

```

## disassembly

```asm
0x180008890  push    rbx
0x180008892  sub     rsp, 20h
0x180008896  mov     rbx, cs:qword_1800152F8
0x18000889d  test    rbx, rbx
0x1800088a0  jz      short loc_1800088DE
0x1800088a2  jmp     short loc_1800088D8
0x1800088a4  mov     ecx, 1
0x1800088a9  mov     rax, [rbx+8]
0x1800088ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b2  test    eax, eax
0x1800088b4  js      short loc_1800088E4
0x1800088b6  mov     rax, [rbx+38h]
0x1800088ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088bf  mov     r8d, 1; int
0x1800088c5  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800088c8  mov     rcx, [rbx]; rguid
0x1800088cb  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800088d0  test    eax, eax
0x1800088d2  js      short loc_1800088E4
0x1800088d4  add     rbx, 48h ; 'H'
0x1800088d8  cmp     qword ptr [rbx], 0
0x1800088dc  jnz     short loc_1800088A4
0x1800088de  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x1800088e3  nop
0x1800088e4  add     rsp, 20h
0x1800088e8  pop     rbx
0x1800088e9  retn
```
