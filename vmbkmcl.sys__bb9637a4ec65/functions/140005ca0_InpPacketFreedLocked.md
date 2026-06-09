# InpPacketFreedLocked

- ea: `0x140005ca0`
- end: `0x140005ce2`
- name: `InpPacketFreedLocked`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f9c`
- `0x1400086b0`
- `0x1400089a8`
- `0x140008c7c`

## callees

- `0x140005ca0`
- `0x140005cf0`

## pseudocode

```c
char __fastcall InpPacketFreedLocked(__int64 a1, unsigned int a2)
{
  unsigned int v2; // eax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 1144));
  *(_QWORD *)(a1 + 1168) += a2;
  v2 = *(_DWORD *)(a1 + 1096) - 1;
  if ( *(_DWORD *)(a1 + 1096) == 1 )
  {
    *(_BYTE *)(a1 + 1120) |= 2u;
  }
  else
  {
    v2 = *(_DWORD *)(a1 + 1096) - 5;
    if ( v2 <= 1 )
      LOBYTE(v2) = InpPrepareToQueueWorkerLocked(a1, 0, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x140005ca0  sub     rsp, 28h
0x140005ca4  lock inc dword ptr [rcx+478h]
0x140005cab  mov     eax, edx
0x140005cad  add     [rcx+490h], rax
0x140005cb4  mov     eax, [rcx+448h]
0x140005cba  sub     eax, 1
0x140005cbd  jz      short loc_140005CD5
0x140005cbf  sub     eax, 4
0x140005cc2  jz      short loc_140005CC9
0x140005cc4  cmp     eax, 1
0x140005cc7  jnz     short loc_140005CDC
0x140005cc9  xor     r8d, r8d
0x140005ccc  xor     edx, edx
0x140005cce  call    InpPrepareToQueueWorkerLocked
0x140005cd3  jmp     short loc_140005CDC
0x140005cd5  or      byte ptr [rcx+460h], 2
0x140005cdc  add     rsp, 28h
0x140005ce0  retn
```
