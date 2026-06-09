# UpdateDataPoint(ulong volatile *,ulong)

- ea: `0x18002184c`
- end: `0x18002187c`
- name: `?UpdateDataPoint@@YAXPECKK@Z`
- size: `48`
- prototype: `void __fastcall(volatile unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021884`

## callees

- `0x18002184c`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180021871`
- `ntdll!WinSqmIncrementDWORD` at `0x180021871`

## pseudocode

```c
void __fastcall UpdateDataPoint(volatile unsigned int *a1)
{
  signed __int32 v1; // r8d

  if ( ++*a1 >= 0x2710 )
  {
    v1 = *a1;
    if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)a1, 0, v1) )
      WinSqmIncrementDWORD(0);
  }
}

```

## disassembly

```asm
0x18002184c  sub     rsp, 28h
0x180021850  mov     eax, [rcx]
0x180021852  inc     eax
0x180021854  mov     [rcx], eax
0x180021856  mov     r8d, [rcx]
0x180021859  cmp     r8d, 2710h
0x180021860  jb      short loc_180021877
0x180021862  xor     r9d, r9d
0x180021865  mov     eax, r8d
0x180021868  lock cmpxchg [rcx], r9d
0x18002186d  jnz     short loc_180021877
0x18002186f  xor     ecx, ecx
0x180021871  call    cs:__imp_WinSqmIncrementDWORD
0x180021877  add     rsp, 28h
0x18002187b  retn
```
