# ATL::CComClassFactory::LockServer(int)

- ea: `0x140004ee0`
- end: `0x140004f08`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004ee0`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  __int64 v2; // rax
  void (*v3)(void); // rax

  v2 = *(_QWORD *)ATL::_pAtlModule;
  if ( a2 )
    v3 = *(void (**)(void))(v2 + 8);
  else
    v3 = *(void (**)(void))(v2 + 16);
  v3();
  return 0;
}

```

## disassembly

```asm
0x140004ee0  sub     rsp, 28h
0x140004ee4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004eeb  mov     rax, [rcx]
0x140004eee  test    edx, edx
0x140004ef0  jz      short loc_140004EF8
0x140004ef2  mov     rax, [rax+8]
0x140004ef6  jmp     short loc_140004EFC
0x140004ef8  mov     rax, [rax+10h]
0x140004efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f01  xor     eax, eax
0x140004f03  add     rsp, 28h
0x140004f07  retn
```
