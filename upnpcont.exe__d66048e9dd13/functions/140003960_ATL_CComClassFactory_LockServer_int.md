# ATL::CComClassFactory::LockServer(int)

- ea: `0x140003960`
- end: `0x140003988`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003960`
- `0x140007010`

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
0x140003960  sub     rsp, 28h
0x140003964  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000396b  mov     rax, [rcx]
0x14000396e  test    edx, edx
0x140003970  jz      short loc_140003978
0x140003972  mov     rax, [rax+8]
0x140003976  jmp     short loc_14000397C
0x140003978  mov     rax, [rax+10h]
0x14000397c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003981  xor     eax, eax
0x140003983  add     rsp, 28h
0x140003987  retn
```
