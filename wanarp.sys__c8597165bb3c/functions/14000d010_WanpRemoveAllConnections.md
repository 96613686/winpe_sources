# WanpRemoveAllConnections

- ea: `0x14000d010`
- end: `0x14000d088`
- name: `WanpRemoveAllConnections`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140019b00`

## callees

- `0x14000d010`
- `0x14000f834`

## pseudocode

```c
PVOID __fastcall WanpRemoveAllConnections(char a1)
{
  unsigned int i; // ebx
  __int64 v3; // rsi
  PVOID result; // rax
  __int64 v5; // rcx

  for ( i = 1; i < g_ulConnTableSize; ++i )
  {
    v3 = 8LL * i;
    result = g_puipConnTable;
    v5 = *(_QWORD *)((char *)g_puipConnTable + v3);
    if ( v5 && *(_DWORD *)(v5 + 100) != 3 && *(_BYTE *)(v5 + 4) == a1 )
    {
      WanpLinkDownIndication(0, i);
      result = g_puipConnTable;
      *(_QWORD *)((char *)g_puipConnTable + v3) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d010  mov     [rsp+arg_8], rbx
0x14000d015  push    rdi
0x14000d016  sub     rsp, 20h
0x14000d01a  mov     ebx, 1
0x14000d01f  movzx   edi, cl
0x14000d022  cmp     cs:g_ulConnTableSize, ebx
0x14000d028  jbe     short loc_14000D07C
0x14000d02a  mov     [rsp+28h+arg_0], rsi
0x14000d02f  mov     eax, ebx
0x14000d031  lea     rsi, ds:0[rax*8]
0x14000d039  mov     rax, cs:g_puipConnTable
0x14000d040  mov     rcx, [rsi+rax]
0x14000d044  test    rcx, rcx
0x14000d047  jz      short loc_14000D06D
0x14000d049  cmp     dword ptr [rcx+64h], 3
0x14000d04d  jz      short loc_14000D06D
0x14000d04f  cmp     [rcx+4], dil
0x14000d053  jnz     short loc_14000D06D
0x14000d055  mov     edx, ebx
0x14000d057  xor     ecx, ecx
0x14000d059  call    WanpLinkDownIndication
0x14000d05e  mov     rax, cs:g_puipConnTable
0x14000d065  mov     qword ptr [rsi+rax], 0
0x14000d06d  inc     ebx
0x14000d06f  cmp     ebx, cs:g_ulConnTableSize
0x14000d075  jb      short loc_14000D02F
0x14000d077  mov     rsi, [rsp+28h+arg_0]
0x14000d07c  mov     rbx, [rsp+28h+arg_8]
0x14000d081  add     rsp, 20h
0x14000d085  pop     rdi
0x14000d086  retn
```
