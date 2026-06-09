# SmpCompleteSubSysStatusChange

- ea: `0x14000b8f0`
- end: `0x14000b929`
- name: `SmpCompleteSubSysStatusChange`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017f58`

## callees

- `0x14000b8f0`
- `0x140017ff0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x14000b918`

## pseudocode

```c
NTSTATUS __fastcall SmpCompleteSubSysStatusChange(__int64 a1)
{
  NTSTATUS result; // eax
  HANDLE *v2; // rcx

  result = a1;
  if ( *(_QWORD *)(a1 + 16) )
  {
    v2 = (HANDLE *)_InterlockedExchange64((volatile __int64 *)(a1 + 16), 0);
    if ( v2 )
    {
      if ( *(_DWORD *)v2 )
        return NtSetEvent(v2[1], 0);
      else
        return SmpDisposeSubSysSynch(v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b8f0  sub     rsp, 28h
0x14000b8f4  cmp     qword ptr [rcx+10h], 0
0x14000b8f9  mov     rax, rcx
0x14000b8fc  jz      short loc_14000B924
0x14000b8fe  xor     ecx, ecx
0x14000b900  xchg    rcx, [rax+10h]; BaseAddress
0x14000b904  test    rcx, rcx
0x14000b907  jz      short loc_14000B924
0x14000b909  cmp     dword ptr [rcx], 0
0x14000b90c  jbe     short loc_14000B91F
0x14000b90e  mov     rcx, [rcx+8]
0x14000b912  xor     edx, edx
0x14000b914  add     rsp, 28h
0x14000b918  jmp     cs:__imp_NtSetEvent
0x14000b91f  call    SmpDisposeSubSysSynch
0x14000b924  add     rsp, 28h
0x14000b928  retn
```
