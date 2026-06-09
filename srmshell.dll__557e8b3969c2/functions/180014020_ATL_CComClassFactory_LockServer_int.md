# ATL::CComClassFactory::LockServer(int)

- ea: `0x180014020`
- end: `0x180014048`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014020`
- `0x180020010`

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
0x180014020  sub     rsp, 28h
0x180014024  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001402b  mov     rax, [rcx]
0x18001402e  test    edx, edx
0x180014030  jz      short loc_180014038
0x180014032  mov     rax, [rax+8]
0x180014036  jmp     short loc_18001403C
0x180014038  mov     rax, [rax+10h]
0x18001403c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014041  xor     eax, eax
0x180014043  add     rsp, 28h
0x180014047  retn
```
