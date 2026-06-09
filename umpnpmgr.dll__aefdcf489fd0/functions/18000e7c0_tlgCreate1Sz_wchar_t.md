# _tlgCreate1Sz_wchar_t

- ea: `0x18000e7c0`
- end: `0x18000e7ff`
- name: `_tlgCreate1Sz_wchar_t`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001002c`

## callees

- `0x18000e7c0`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    while ( *((_WORD *)a2 + ++v2) != 0 )
      ;
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &qword_18001C3B0;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e7c0  test    rdx, rdx
0x18000e7c3  jz      short loc_18000E7F1
0x18000e7c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e7cc  nop     dword ptr [rax+00h]
0x18000e7d0  cmp     word ptr [rdx+rax*2+2], 0
0x18000e7d6  lea     rax, [rax+1]
0x18000e7da  jnz     short loc_18000E7D0
0x18000e7dc  lea     eax, ds:2[rax*2]
0x18000e7e3  mov     [rcx], rdx
0x18000e7e6  mov     [rcx+8], eax
0x18000e7e9  mov     dword ptr [rcx+0Ch], 0
0x18000e7f0  retn
0x18000e7f1  lea     rdx, qword_18001C3B0
0x18000e7f8  mov     eax, 2
0x18000e7fd  jmp     short loc_18000E7E3
```
