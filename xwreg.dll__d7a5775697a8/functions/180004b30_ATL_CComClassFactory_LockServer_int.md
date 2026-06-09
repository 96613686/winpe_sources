# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004b30`
- end: `0x180004b58`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004b30`
- `0x180013010`

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
0x180004b30  sub     rsp, 28h
0x180004b34  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b3b  mov     rax, [rcx]
0x180004b3e  test    edx, edx
0x180004b40  jz      short loc_180004B48
0x180004b42  mov     rax, [rax+8]
0x180004b46  jmp     short loc_180004B4C
0x180004b48  mov     rax, [rax+10h]
0x180004b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b51  xor     eax, eax
0x180004b53  add     rsp, 28h
0x180004b57  retn
```
