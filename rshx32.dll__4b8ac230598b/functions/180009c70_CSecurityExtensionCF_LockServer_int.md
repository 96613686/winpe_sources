# CSecurityExtensionCF::LockServer(int)

- ea: `0x180009c70`
- end: `0x180009c89`
- name: `?LockServer@CSecurityExtensionCF@@UEAAJH@Z`
- size: `25`
- prototype: `__int64 __fastcall(CSecurityExtensionCF *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009c70`

## pseudocode

```c
__int64 __fastcall CSecurityExtensionCF::LockServer(CSecurityExtensionCF *this, int a2)
{
  int v2; // eax

  if ( a2 )
    v2 = g_cServerLocks + 1;
  else
    v2 = g_cServerLocks - 1;
  g_cServerLocks = v2;
  return 0;
}

```

## disassembly

```asm
0x180009c70  mov     eax, cs:?g_cServerLocks@@3JA; long g_cServerLocks
0x180009c76  test    edx, edx
0x180009c78  jz      short loc_180009C7E
0x180009c7a  inc     eax
0x180009c7c  jmp     short loc_180009C80
0x180009c7e  dec     eax
0x180009c80  mov     cs:?g_cServerLocks@@3JA, eax; long g_cServerLocks
0x180009c86  xor     eax, eax
0x180009c88  retn
```
