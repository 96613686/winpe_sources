# ATL::CComClassFactory::LockServer(int)

- ea: `0x180008af0`
- end: `0x180008b19`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008af0`
- `0x180014010`

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
0x180008af0  sub     rsp, 28h
0x180008af4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008afb  mov     rax, [rcx]
0x180008afe  test    edx, edx
0x180008b00  jz      short loc_180008B08
0x180008b02  mov     rax, [rax+8]
0x180008b06  jmp     short loc_180008B0C
0x180008b08  mov     rax, [rax+10h]
0x180008b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b11  xor     eax, eax
0x180008b13  add     rsp, 28h
0x180008b17  retn
```
