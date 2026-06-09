# ATL::CComClassFactory::LockServer(int)

- ea: `0x180003a40`
- end: `0x180003a69`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003a40`
- `0x18000d010`

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
0x180003a40  sub     rsp, 28h
0x180003a44  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003a4b  mov     rax, [rcx]
0x180003a4e  test    edx, edx
0x180003a50  jz      short loc_180003A58
0x180003a52  mov     rax, [rax+8]
0x180003a56  jmp     short loc_180003A5C
0x180003a58  mov     rax, [rax+10h]
0x180003a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a61  xor     eax, eax
0x180003a63  add     rsp, 28h
0x180003a67  retn
```
