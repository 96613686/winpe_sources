# ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)

- ea: `0x180007854`
- end: `0x1800078e3`
- name: `?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180006598`
- `0x180007854`
- `0x180010010`

## pseudocode

```c
__int64 ATL::CAtlModuleT<ATL::CComModule>::RegisterServer()
{
  __int64 result; // rax
  __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  __int64 v3; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax

  result = 0;
  v1 = (__int64 *)qword_1800153C0;
  v2 = qword_1800153C8;
  while ( (unsigned __int64)v1 < v2 )
  {
    v3 = *v1;
    if ( *v1 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
      if ( (int)result < 0 )
        return result;
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 1);
      if ( (int)result < 0 )
        return result;
      v2 = qword_1800153C8;
    }
    ++v1;
  }
  if ( ATL::_pPerfRegFunc )
    return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  return result;
}

```

## disassembly

```asm
0x180007854  mov     [rsp+arg_0], rbx
0x180007859  push    rdi
0x18000785a  sub     rsp, 20h
0x18000785e  xor     eax, eax
0x180007860  mov     rbx, cs:qword_1800153C0
0x180007867  mov     rcx, cs:qword_1800153C8
0x18000786e  jmp     short loc_1800078B3
0x180007870  mov     rdi, [rbx]
0x180007873  test    rdi, rdi
0x180007876  jz      short loc_1800078AF
0x180007878  mov     ecx, 1
0x18000787d  mov     rax, [rdi+8]
0x180007881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007886  test    eax, eax
0x180007888  js      short loc_1800078D8
0x18000788a  mov     rax, [rdi+38h]
0x18000788e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007893  mov     r8d, 1; int
0x180007899  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000789c  mov     rcx, [rdi]; rguid
0x18000789f  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800078a4  test    eax, eax
0x1800078a6  js      short loc_1800078D8
0x1800078a8  mov     rcx, cs:qword_1800153C8
0x1800078af  add     rbx, 8
0x1800078b3  cmp     rbx, rcx
0x1800078b6  jb      short loc_180007870
0x1800078b8  test    eax, eax
0x1800078ba  js      short loc_1800078D8
0x1800078bc  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800078c3  test    rdx, rdx
0x1800078c6  jz      short loc_1800078D8
0x1800078c8  mov     rcx, cs:hModule
0x1800078cf  mov     rax, rdx
0x1800078d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d7  nop
0x1800078d8  mov     rbx, [rsp+28h+arg_0]
0x1800078dd  add     rsp, 20h
0x1800078e1  pop     rdi
0x1800078e2  retn
```
