# _tlgCreate1Sz_wchar_t

- ea: `0x140001010`
- end: `0x14000105c`
- name: `_tlgCreate1Sz_wchar_t`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002cb0`
- `0x140006cbc`
- `0x1400086f8`

## callees

- `0x140001010`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    while ( *(_WORD *)(a2 + 2 * v2++ + 2) != 0 )
      ;
    result = (unsigned int)(2 * v2 + 2);
    *(_QWORD *)a1 = a2;
    *(_QWORD *)(a1 + 8) = (unsigned int)result;
  }
  else
  {
    *(_DWORD *)(a1 + 12) = 0;
    result = 2;
    *(_QWORD *)a1 = "";
    *(_DWORD *)(a1 + 8) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x140001010  test    rdx, rdx
0x140001013  jz      short loc_140001042
0x140001015  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000101c  nop     dword ptr [rax+00h]
0x140001020  cmp     word ptr [rdx+rax*2+2], 0
0x140001026  lea     rax, [rax+1]
0x14000102a  jnz     short loc_140001020
0x14000102c  lea     eax, ds:2[rax*2]
0x140001033  mov     [rcx], rdx
0x140001036  mov     [rcx+8], eax
0x140001039  mov     dword ptr [rcx+0Ch], 0
0x140001040  retn
0x140001042  lea     rdx, aNourlmimefilte+10h; ""
0x140001049  mov     dword ptr [rcx+0Ch], 0
0x140001050  mov     eax, 2
0x140001055  mov     [rcx], rdx
0x140001058  mov     [rcx+8], eax
0x14000105b  retn
```
