# ATL::CComClassFactory::LockServer(int)

- ea: `0x14000b080`
- end: `0x14000b09d`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b080`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_1400153D8);
  else
    CExeModule::Unlock(this);
  return 0;
}

```

## disassembly

```asm
0x14000b080  sub     rsp, 28h
0x14000b084  test    edx, edx
0x14000b086  jz      short loc_14000B091
0x14000b088  lock inc cs:dword_1400153D8
0x14000b08f  jmp     short loc_14000B096
0x14000b091  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000b096  xor     eax, eax
0x14000b098  add     rsp, 28h
0x14000b09c  retn
```
