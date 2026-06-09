# ATL::CComClassFactory::LockServer(int)

- ea: `0x180002f10`
- end: `0x180002f27`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f10`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_18000A288);
  else
    _InterlockedDecrement(&dword_18000A288);
  return 0;
}

```

## disassembly

```asm
0x180002f10  test    edx, edx
0x180002f12  jz      short loc_180002F1D
0x180002f14  lock inc cs:dword_18000A288
0x180002f1b  jmp     short loc_180002F24
0x180002f1d  lock dec cs:dword_18000A288
0x180002f24  xor     eax, eax
0x180002f26  retn
```
