# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14000b1d8`
- end: `0x14000b22f`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b560`
- `0x14000d138`

## callees

- `0x14000b1d8`

## pseudocode

```c
__int64 __fastcall wil_details_BuildFeatureStateCacheFromQueryResults(int a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v4; // edx
  int v5; // edx

  if ( a1 == -2147483614 || a1 == -1073741275 )
  {
    result = 0;
    *a3 = 0;
    goto LABEL_9;
  }
  result = 0;
  *a3 = 0;
  if ( !a1 )
  {
    result = *(_DWORD *)(a2 + 4) & 0xB0;
    v4 = result | (4 * (*(_DWORD *)(a2 + 4) & 0x40));
    goto LABEL_7;
  }
  if ( a1 != 279 )
  {
LABEL_9:
    v5 = 518;
    goto LABEL_10;
  }
  v4 = *(_DWORD *)(a2 + 4) & 0x80;
LABEL_7:
  v5 = (8 * v4) | 0x206;
LABEL_10:
  *(_DWORD *)a3 = v5;
  return result;
}

```

## disassembly

```asm
0x14000b1d8  cmp     ecx, 80000022h
0x14000b1de  jz      short loc_14000B221
0x14000b1e0  cmp     ecx, 0C0000225h
0x14000b1e6  jz      short loc_14000B221
0x14000b1e8  xor     eax, eax
0x14000b1ea  mov     [r8], rax
0x14000b1ed  test    ecx, ecx
0x14000b1ef  jz      short loc_14000B204
0x14000b1f1  cmp     ecx, 117h
0x14000b1f7  jnz     short loc_14000B226
0x14000b1f9  mov     edx, [rdx+4]
0x14000b1fc  and     edx, 80h
0x14000b202  jmp     short loc_14000B216
0x14000b204  mov     eax, [rdx+4]
0x14000b207  mov     edx, eax
0x14000b209  and     edx, 40h
0x14000b20c  and     eax, 0B0h
0x14000b211  shl     edx, 2
0x14000b214  or      edx, eax
0x14000b216  shl     edx, 3
0x14000b219  or      edx, 206h
0x14000b21f  jmp     short loc_14000B22B
0x14000b221  xor     eax, eax
0x14000b223  mov     [r8], rax
0x14000b226  mov     edx, 206h
0x14000b22b  mov     [r8], edx
0x14000b22e  retn
```
