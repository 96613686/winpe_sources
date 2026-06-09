# OncRpcCopyAddress

- ea: `0x140006720`
- end: `0x140006753`
- name: `OncRpcCopyAddress`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005dc8`
- `0x1400064cc`
- `0x140007394`
- `0x14000bb64`
- `0x14000d300`
- `0x14000e8e0`

## callees

- `0x140006720`

## pseudocode

```c
__int64 __fastcall OncRpcCopyAddress(_OWORD *a1, _OWORD *a2)
{
  __int64 result; // rax

  result = *(unsigned __int16 *)a2;
  if ( (_WORD)result == 2 )
  {
    *a1 = *a2;
  }
  else if ( (_WORD)result == 23 )
  {
    *a1 = *a2;
    *(_OWORD *)((char *)a1 + 12) = *(_OWORD *)((char *)a2 + 12);
  }
  else
  {
    *a1 = 0;
    *(_OWORD *)((char *)a1 + 12) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006720  movzx   eax, word ptr [rdx]
0x140006723  cmp     ax, 2
0x140006727  jz      short loc_14000674B
0x140006729  cmp     ax, 17h
0x14000672d  jz      short loc_14000673B
0x14000672f  xorps   xmm0, xmm0
0x140006732  movups  xmmword ptr [rcx], xmm0
0x140006735  movups  xmmword ptr [rcx+0Ch], xmm0
0x140006739  retn
0x14000673b  movups  xmm0, xmmword ptr [rdx]
0x14000673e  movups  xmmword ptr [rcx], xmm0
0x140006741  movups  xmm1, xmmword ptr [rdx+0Ch]
0x140006745  movups  xmmword ptr [rcx+0Ch], xmm1
0x140006749  retn
0x14000674b  movups  xmm0, xmmword ptr [rdx]
0x14000674e  movdqu  xmmword ptr [rcx], xmm0
0x140006752  retn
```
