# MTX_AHUFF_WriteSymbolCost

- ea: `0x18000ed70`
- end: `0x18000edcc`
- name: `MTX_AHUFF_WriteSymbolCost`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007210`

## callees

- `0x18000ed70`
- `0x18001c9ec`

## pseudocode

```c
__int64 __fastcall MTX_AHUFF_WriteSymbolCost(__int64 *a1, __int16 a2)
{
  int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rdi

  v2 = 0;
  v3 = *a1;
  v4 = *(__int16 *)(a1[1] + 2LL * a2);
  if ( *(_WORD *)(*a1 + 12 * v4 + 6) != a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  do
  {
    ++v2;
    LOWORD(v4) = *(_WORD *)(v3 + 12LL * (__int16)v4);
  }
  while ( (_WORD)v4 != 1 );
  return (unsigned int)(v2 << 16);
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp+arg_0], rbx
0x18000ed75  mov     [rsp+arg_8], rsi
0x18000ed7a  push    rdi
0x18000ed7b  sub     rsp, 20h
0x18000ed7f  mov     rax, [rcx+8]
0x18000ed83  xor     ebx, ebx
0x18000ed85  mov     rsi, [rcx]
0x18000ed88  movsx   r8, dx
0x18000ed8c  movsx   rdi, word ptr [rax+r8*2]
0x18000ed91  lea     rcx, [rdi+rdi*2]
0x18000ed95  cmp     [rsi+rcx*4+6], dx
0x18000ed9a  jnz     short loc_18000EDC5
0x18000ed9c  movsx   rax, di
0x18000eda0  inc     ebx
0x18000eda2  lea     rcx, [rax+rax*2]
0x18000eda6  movzx   edi, word ptr [rsi+rcx*4]
0x18000edaa  cmp     di, 1
0x18000edae  jnz     short loc_18000ED9C
0x18000edb0  mov     rsi, [rsp+28h+arg_8]
0x18000edb5  shl     ebx, 10h
0x18000edb8  mov     eax, ebx
0x18000edba  mov     rbx, [rsp+28h+arg_0]
0x18000edbf  add     rsp, 20h
0x18000edc3  pop     rdi
0x18000edc4  retn
0x18000edc5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000edca  jmp     short loc_18000ED9C
```
