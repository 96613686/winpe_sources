# _tlgCreate1Sz_wchar_t

- ea: `0x18000bfcc`
- end: `0x18000c002`
- name: `_tlgCreate1Sz_wchar_t`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d080`
- `0x18000d2f4`

## callees

- `0x18000bfcc`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( *((_WORD *)a2 + v2) );
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &qword_18001E9A0;
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
0x18000bfcc  xor     r8d, r8d
0x18000bfcf  test    rdx, rdx
0x18000bfd2  jz      short loc_18000BFF4
0x18000bfd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bfd8  inc     rax
0x18000bfdb  cmp     [rdx+rax*2], r8w
0x18000bfe0  jnz     short loc_18000BFD8
0x18000bfe2  lea     eax, ds:2[rax*2]
0x18000bfe9  mov     [rcx], rdx
0x18000bfec  mov     [rcx+8], eax
0x18000bfef  mov     [rcx+0Ch], r8d
0x18000bff3  retn
0x18000bff4  lea     rdx, qword_18001E9A0
0x18000bffb  mov     eax, 2
0x18000c000  jmp     short loc_18000BFE9
```
