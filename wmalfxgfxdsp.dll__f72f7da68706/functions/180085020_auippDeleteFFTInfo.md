# auippDeleteFFTInfo

- ea: `0x180085020`
- end: `0x180085080`
- name: `auippDeleteFFTInfo`
- size: `96`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c774`

## callees

- `0x1800124f8`
- `0x180016ed0`
- `0x180085020`

## pseudocode

```c
void __fastcall auippDeleteFFTInfo(_DWORD *Block)
{
  int v2; // edi
  int v3; // esi

  if ( Block )
  {
    if ( *((_QWORD *)Block + 1) )
    {
      v2 = 0;
      v3 = Block[1] - *Block + 1;
      if ( v3 > 0 )
      {
        do
        {
          if ( *(_QWORD *)(32LL * (unsigned int)v2 + *((_QWORD *)Block + 1)) )
            ippsFFTFree_C_32fc();
          ++v2;
        }
        while ( v2 < v3 );
      }
    }
  }
  prvDeleteFFTInfo((void **)Block);
}

```

## disassembly

```asm
0x180085020  mov     [rsp+arg_0], rbx
0x180085025  mov     [rsp+arg_8], rsi
0x18008502a  push    rdi
0x18008502b  sub     rsp, 20h
0x18008502f  mov     rbx, rcx
0x180085032  test    rcx, rcx
0x180085035  jz      short loc_180085069
0x180085037  cmp     qword ptr [rcx+8], 0
0x18008503c  jz      short loc_180085069
0x18008503e  mov     esi, [rcx+4]
0x180085041  xor     edi, edi
0x180085043  sub     esi, [rcx]
0x180085045  inc     esi
0x180085047  test    esi, esi
0x180085049  jle     short loc_180085069
0x18008504b  mov     rax, [rbx+8]
0x18008504f  mov     ecx, edi
0x180085051  shl     rcx, 5
0x180085055  mov     rcx, [rcx+rax]
0x180085059  test    rcx, rcx
0x18008505c  jz      short loc_180085063
0x18008505e  call    ippsFFTFree_C_32fc
0x180085063  inc     edi
0x180085065  cmp     edi, esi
0x180085067  jl      short loc_18008504B
0x180085069  mov     rcx, rbx; Block
0x18008506c  mov     rbx, [rsp+28h+arg_0]
0x180085071  mov     rsi, [rsp+28h+arg_8]
0x180085076  add     rsp, 20h
0x18008507a  pop     rdi
0x18008507b  jmp     prvDeleteFFTInfo
```
