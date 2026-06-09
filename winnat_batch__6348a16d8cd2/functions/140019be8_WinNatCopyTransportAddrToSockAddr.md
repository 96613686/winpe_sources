# WinNatCopyTransportAddrToSockAddr

- ea: `0x140019be8`
- end: `0x140019c60`
- name: `WinNatCopyTransportAddrToSockAddr`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
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
- `0x140019d5c`
- `0x14001a178`
- `0x14001a2e0`
- `0x14001b808`
- `0x14001c7e0`

## callees

- `0x14001f140`
- `0x14001f440`

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
0x140019be8  mov     [rsp+arg_0], rbx
0x140019bed  mov     [rsp+arg_8], rsi
0x140019bf2  push    rdi
0x140019bf3  sub     rsp, 20h
0x140019bf7  cmp     word ptr [rdx], 2
0x140019bfb  mov     rdi, rdx
0x140019bfe  mov     esi, 10h
0x140019c03  mov     rbx, rcx
0x140019c06  mov     r8d, esi
0x140019c09  mov     rcx, rdi; void *
0x140019c0c  lea     eax, [rsi+0Ch]
0x140019c0f  cmovnz  r8d, eax; Size
0x140019c13  xor     edx, edx; Val
0x140019c15  call    memset
0x140019c1a  movzx   r9d, word ptr [rbx]
0x140019c1e  lea     ecx, [rsi-0Ch]
0x140019c21  mov     [rdi], r9w
0x140019c25  lea     rdx, [rbx+4]; Src
0x140019c29  movzx   eax, word ptr [rbx+2]
0x140019c2d  mov     r8d, ecx
0x140019c30  mov     [rdi+2], ax
0x140019c34  lea     eax, [rsi-8]
0x140019c37  cmp     word ptr [rbx], 2
0x140019c3b  cmovnz  r8d, esi; Size
0x140019c3f  cmp     r9w, 2
0x140019c44  cmovnz  ecx, eax
0x140019c47  add     rcx, rdi; void *
0x140019c4a  call    memmove
0x140019c4f  mov     rbx, [rsp+28h+arg_0]
0x140019c54  mov     rsi, [rsp+28h+arg_8]
0x140019c59  add     rsp, 20h
0x140019c5d  pop     rdi
0x140019c5e  retn
```
