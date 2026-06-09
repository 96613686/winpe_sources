# wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort,std::allocator<ushort>>,std::allocator<std::vector<ushort,std::allocator<ushort>>>> *),std::vector<std::vector<ushort,std::allocator<ushort>>,std::allocator<std::vector<ushort,std::allocator<ushort>>>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort,std::allocator<ushort>>,std::allocator<std::vector<ushort,std::allocator<ushort>>>> *),std::vector<std::vector<ushort,std::allocator<ushort>>,std::allocator<std::vector<ushort,std::allocator<ushort>>>> *>(void)

- ea: `0x180002510`
- end: `0x18000252f`
- name: `??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cb0`
- `0x180002f14`
- `0x1800042d0`
- `0x180004760`
- `0x180009170`
- `0x180009a10`
- `0x18000ada0`
- `0x18000c724`
- `0x18000cd50`
- `0x18000d03c`
- `0x18000e2f8`
- `0x18000f7b0`
- `0x180012f20`
- `0x18001483c`
- `0x1800165c0`
- `0x18001718c`
- `0x18001ab58`
- `0x18001b238`
- `0x18001b2ac`
- `0x18001b734`
- `0x18001bdac`
- `0x18001c750`
- `0x18001d2c4`
- `0x18002036a`
- `0x18002037c`
- `0x18002038e`
- `0x180020626`
- `0x1800206fe`
- `0x1800210dd`
- `0x180021113`
- `0x18002138f`
- `0x18002147e`
- `0x1800214b4`
- `0x1800215aa`
- `0x1800215ce`
- `0x18002167c`
- `0x1800217fc`
- `0x180021820`
- `0x1800221b2`
- `0x18002236a`
- `0x1800224ba`
- `0x18002267d`
- `0x18002268f`
- `0x1800226fb`
- `0x18002274b`

## callees

- `0x180002510`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(
        __int64 a1)
{
  __int64 result; // rax

  result = a1;
  if ( !*(_BYTE *)a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x180002510  sub     rsp, 28h
0x180002514  mov     rax, rcx
0x180002517  cmp     byte ptr [rcx], 0
0x18000251a  jnz     short loc_18000252A
0x18000251c  mov     rcx, [rcx+10h]
0x180002520  mov     rax, [rax+8]
0x180002524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002529  nop
0x18000252a  add     rsp, 28h
0x18000252e  retn
```
