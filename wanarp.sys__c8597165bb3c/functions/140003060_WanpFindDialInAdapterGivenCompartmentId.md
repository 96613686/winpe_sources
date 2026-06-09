# WanpFindDialInAdapterGivenCompartmentId

- ea: `0x140003060`
- end: `0x140003089`
- name: `WanpFindDialInAdapterGivenCompartmentId`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000df30`
- `0x14000fdc4`
- `0x1400124bc`

## callees

- `0x140003060`

## pseudocode

```c
__int64 __fastcall WanpFindDialInAdapterGivenCompartmentId(int a1)
{
  __int64 i; // rax

  for ( i = g_leDialInAdapterList; (__int64 *)i != &g_leDialInAdapterList; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 336) == a1 )
      return i - 32;
  }
  return 0;
}

```

## disassembly

```asm
0x140003060  mov     rax, cs:g_leDialInAdapterList
0x140003067  lea     rdx, g_leDialInAdapterList
0x14000306e  cmp     rax, rdx
0x140003071  jz      short loc_140003086
0x140003073  cmp     [rax+150h], ecx
0x140003079  jz      short loc_140003080
0x14000307b  mov     rax, [rax]
0x14000307e  jmp     short loc_140003067
0x140003080  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003084  retn
0x140003086  xor     eax, eax
0x140003088  retn
```
