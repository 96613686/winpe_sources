# WinNatCopyTransportAddrToSockAddr

- ea: `0x14001a0c8`
- end: `0x14001a140`
- name: `WinNatCopyTransportAddrToSockAddr`
- size: `120`
- prototype: `void *__fastcall(__int16 *, __int16 *)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140004094`
- `0x140004648`
- `0x140004ed0`
- `0x1400052d0`
- `0x140008df0`
- `0x140009b04`
- `0x14000a9d0`
- `0x14000ae68`
- `0x14000b220`
- `0x14001a23c`
- `0x14001a658`
- `0x14001a7c0`
- `0x14001bce8`
- `0x14001ccc0`

## callees

- `0x14001f680`
- `0x14001f980`

## pseudocode

```c
void *__fastcall WinNatCopyTransportAddrToSockAddr(__int16 *a1, __int16 *a2)
{
  size_t v4; // r8
  __int16 v5; // r9
  __int64 v6; // rcx
  size_t v7; // r8

  v4 = 16;
  if ( *a2 != 2 )
    v4 = 28;
  memset(a2, 0, v4);
  v5 = *a1;
  v6 = 2;
  *a2 = *a1;
  v7 = 4;
  a2[1] = a1[1];
  if ( *a1 != 2 )
    v7 = 16;
  if ( v5 != 2 )
    v6 = 4;
  return memmove(&a2[v6], a1 + 2, v7);
}

```

## disassembly

```asm
0x14001a0c8  mov     [rsp+arg_0], rbx
0x14001a0cd  mov     [rsp+arg_8], rsi
0x14001a0d2  push    rdi
0x14001a0d3  sub     rsp, 20h
0x14001a0d7  cmp     word ptr [rdx], 2
0x14001a0db  mov     rdi, rdx
0x14001a0de  mov     esi, 10h
0x14001a0e3  mov     rbx, rcx
0x14001a0e6  mov     r8d, esi
0x14001a0e9  mov     rcx, rdi; void *
0x14001a0ec  lea     eax, [rsi+0Ch]
0x14001a0ef  cmovnz  r8d, eax; Size
0x14001a0f3  xor     edx, edx; Val
0x14001a0f5  call    memset
0x14001a0fa  movzx   r9d, word ptr [rbx]
0x14001a0fe  lea     ecx, [rsi-0Ch]
0x14001a101  mov     [rdi], r9w
0x14001a105  lea     rdx, [rbx+4]; Src
0x14001a109  movzx   eax, word ptr [rbx+2]
0x14001a10d  mov     r8d, ecx
0x14001a110  mov     [rdi+2], ax
0x14001a114  lea     eax, [rsi-8]
0x14001a117  cmp     word ptr [rbx], 2
0x14001a11b  cmovnz  r8d, esi; Size
0x14001a11f  cmp     r9w, 2
0x14001a124  cmovnz  ecx, eax
0x14001a127  add     rcx, rdi; void *
0x14001a12a  call    memmove
0x14001a12f  mov     rbx, [rsp+28h+arg_0]
0x14001a134  mov     rsi, [rsp+28h+arg_8]
0x14001a139  add     rsp, 20h
0x14001a13d  pop     rdi
0x14001a13e  retn
```
