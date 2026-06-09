# CCritSectWithResource<CCurrentThreads<20>>::_Cleanup(void)

- ea: `0x18001817c`
- end: `0x1800181a5`
- name: `?_Cleanup@?$CCritSectWithResource@V?$CCurrentThreads@$0BE@@@@@AEAAXXZ`
- size: `41`
- prototype: `void __fastcall(__int64)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180018110`
- `0x18001c04c`
- `0x18001c0f0`
- `0x18001c1b0`
- `0x18001d3c0`
- `0x180024aa0`
- `0x180024c60`
- `0x180024e58`
- `0x1800253f0`
- `0x180026e58`
- `0x180027230`
- `0x180027d28`
- `0x1800296b0`
- `0x18002bcd4`
- `0x18002ee50`
- `0x18002f904`

## callees

- `0x18001817c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001819a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001819a`

## pseudocode

```c
void __fastcall CCritSectWithResource<CCurrentThreads<20>>::_Cleanup(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 48) )
  {
    *(_DWORD *)(a1 + 48) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((a1 + 8) & -(__int64)(a1 != 0)));
  }
}

```

## disassembly

```asm
0x18001817c  sub     rsp, 28h
0x180018180  cmp     dword ptr [rcx+30h], 0
0x180018184  jz      short loc_1800181A0
0x180018186  mov     dword ptr [rcx+30h], 0
0x18001818d  lea     rax, [rcx+8]
0x180018191  neg     rcx
0x180018194  sbb     rcx, rcx
0x180018197  and     rcx, rax; lpCriticalSection
0x18001819a  call    cs:__imp_DeleteCriticalSection
0x1800181a0  add     rsp, 28h
0x1800181a4  retn
```
