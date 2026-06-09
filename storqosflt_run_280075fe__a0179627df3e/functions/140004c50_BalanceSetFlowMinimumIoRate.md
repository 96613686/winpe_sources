# BalanceSetFlowMinimumIoRate

- ea: `0x140004c50`
- end: `0x140004c82`
- name: `BalanceSetFlowMinimumIoRate`
- size: `50`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002620`
- `0x140004be4`
- `0x140005de4`
- `0x140007344`

## callees

- `0x140004c50`

## pseudocode

```c
__int64 __fastcall BalanceSetFlowMinimumIoRate(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax

  if ( a1[56] )
  {
    if ( !a2 )
    {
      result = *a1;
      _InterlockedDecrement((volatile signed __int32 *)(*a1 + 920LL));
    }
  }
  else if ( a2 )
  {
    result = *a1;
    _InterlockedIncrement((volatile signed __int32 *)(*a1 + 920LL));
  }
  a1[56] = a2;
  return result;
}

```

## disassembly

```asm
0x140004c50  cmp     qword ptr [rcx+1C0h], 0
0x140004c58  jbe     short loc_140004C6B
0x140004c5a  test    rdx, rdx
0x140004c5d  jnz     short loc_140004C7A
0x140004c5f  mov     rax, [rcx]
0x140004c62  lock dec dword ptr [rax+398h]
0x140004c69  jmp     short loc_140004C7A
0x140004c6b  test    rdx, rdx
0x140004c6e  jz      short loc_140004C7A
0x140004c70  mov     rax, [rcx]
0x140004c73  lock inc dword ptr [rax+398h]
0x140004c7a  mov     [rcx+1C0h], rdx
0x140004c81  retn
```
