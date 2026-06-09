# CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::LockServer(int)

- ea: `0x18001cd90`
- end: `0x18001cda7`
- name: `?LockServer@?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJH@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001cd90`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::LockServer(
        __int64 a1,
        int a2)
{
  if ( a2 )
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  else
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  return 0;
}

```

## disassembly

```asm
0x18001cd90  test    edx, edx
0x18001cd92  jz      short loc_18001CD9D
0x18001cd94  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001cd9b  jmp     short loc_18001CDA4
0x18001cd9d  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001cda4  xor     eax, eax
0x18001cda6  retn
```
