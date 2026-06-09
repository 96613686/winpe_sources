# ChReferenceChannelInternal

- ea: `0x14001016c`
- end: `0x1400101b9`
- name: `ChReferenceChannelInternal`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e30`
- `0x140003dd0`
- `0x140004a70`
- `0x14000566c`
- `0x140007430`
- `0x140009798`
- `0x140009cf0`
- `0x140010834`
- `0x1400112f8`

## callees

- `0x14001016c`

## pseudocode

```c
__int64 __fastcall ChReferenceChannelInternal(__int64 a1, int a2, __int16 a3)
{
  __int64 v3; // rax
  __int64 result; // rax

  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1280), 1u) & 0x1F;
  *(_BYTE *)(a1 + 8 * v3 + 1284) = 1;
  *(_WORD *)(a1 + 8 * v3 + 1286) = a3;
  *(_DWORD *)(a1 + 8 * v3 + 1288) = a2;
  result = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 240));
  if ( result <= 1 )
    __fastfail(0xEu);
  return result;
}

```

## disassembly

```asm
0x14001016c  mov     r9d, 1
0x140010172  mov     eax, r9d
0x140010175  lock xadd [rcx+500h], eax
0x14001017d  add     eax, r9d
0x140010180  sub     eax, r9d
0x140010183  and     eax, 1Fh
0x140010186  mov     [rcx+rax*8+504h], r9b
0x14001018e  mov     [rcx+rax*8+506h], r8w
0x140010197  mov     [rcx+rax*8+508h], edx
0x14001019e  mov     eax, r9d
0x1400101a1  lock xadd [rcx+0F0h], rax
0x1400101aa  add     rax, r9
0x1400101ad  cmp     rax, r9
0x1400101b0  jg      short locret_1400101B8
0x1400101b2  lea     ecx, [r9+0Dh]
0x1400101b6  int     29h; Win8: RtlFailFast(ecx)
0x1400101b8  retn
```
