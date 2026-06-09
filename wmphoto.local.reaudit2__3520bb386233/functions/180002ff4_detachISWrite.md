# detachISWrite

- ea: `0x180002ff4`
- end: `0x180003048`
- name: `detachISWrite`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a50`
- `0x180007400`

## callees

- `0x180002ff4`
- `0x180003108`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall detachISWrite(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( (*(_DWORD *)(a2 + 8) & 7) != 0 )
    return 0xFFFFFFFFLL;
  result = writeIS(a1, a2);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64))(*(_QWORD *)(a2 + 32) + 72LL))(
               *(_QWORD *)(a2 + 32),
               *(_QWORD *)(a2 + 16),
               *(_QWORD *)(a2 + 24) + ((unsigned __int64)*(unsigned int *)(a2 + 8) >> 3) - *(_QWORD *)(a2 + 16));
    if ( (int)result >= 0 )
      *(_QWORD *)(a2 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002ff4  push    rbx
0x180002ff6  sub     rsp, 20h
0x180002ffa  mov     eax, [rdx+8]
0x180002ffd  mov     rbx, rdx
0x180003000  test    al, 7
0x180003002  jnz     short loc_180003043
0x180003004  call    writeIS
0x180003009  test    eax, eax
0x18000300b  js      short loc_18000303C
0x18000300d  mov     rax, [rbx+20h]
0x180003011  mov     r8d, [rbx+8]
0x180003015  mov     rcx, rax
0x180003018  mov     rdx, [rbx+10h]
0x18000301c  shr     r8, 3
0x180003020  add     r8, [rbx+18h]
0x180003024  mov     rax, [rax+48h]
0x180003028  sub     r8, rdx
0x18000302b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003030  test    eax, eax
0x180003032  js      short loc_18000303C
0x180003034  mov     qword ptr [rbx+20h], 0
0x18000303c  add     rsp, 20h
0x180003040  pop     rbx
0x180003041  retn
0x180003043  or      eax, 0FFFFFFFFh
0x180003046  jmp     short loc_18000303C
```
