# WinHvpDeletePartitionObject

- ea: `0x140007828`
- end: `0x140007866`
- name: `WinHvpDeletePartitionObject`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400024d0`
- `0x1400025e0`
- `0x1400026d0`
- `0x140002830`
- `0x14000b0f0`
- `0x14000bcd0`
- `0x14001f2d0`

## callees

- `0x140007828`
- `0x140008e70`
- `0x14000b040`

## pseudocode

```c
__int64 __fastcall WinHvpDeletePartitionObject(__int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 64);
  if ( v2 )
    WinHvpFreePoolWithTag(v2, 1316374615);
  if ( *(_QWORD *)(a1 + 88) )
    WinHvpDereferencePartitionData();
  return WinHvpFreePoolWithTag(a1, 1215711319);
}

```

## disassembly

```asm
0x140007828  push    rbx
0x14000782a  sub     rsp, 20h
0x14000782e  mov     rbx, rcx
0x140007831  mov     rcx, [rcx+40h]
0x140007835  test    rcx, rcx
0x140007838  jz      short loc_140007844
0x14000783a  mov     edx, 4E764857h
0x14000783f  call    WinHvpFreePoolWithTag
0x140007844  mov     rcx, [rbx+58h]
0x140007848  test    rcx, rcx
0x14000784b  jz      short loc_140007852
0x14000784d  call    WinHvpDereferencePartitionData
0x140007852  mov     edx, 48764857h
0x140007857  mov     rcx, rbx
0x14000785a  call    WinHvpFreePoolWithTag
0x14000785f  add     rsp, 20h
0x140007863  pop     rbx
0x140007864  retn
```
