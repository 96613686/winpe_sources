# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14001390c`
- end: `0x140013963`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140013c40`
- `0x1400169e0`

## callees

- `0x14001390c`

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
0x14001390c  cmp     ecx, 80000022h
0x140013912  jz      short loc_140013955
0x140013914  cmp     ecx, 0C0000225h
0x14001391a  jz      short loc_140013955
0x14001391c  xor     eax, eax
0x14001391e  mov     [r8], rax
0x140013921  test    ecx, ecx
0x140013923  jz      short loc_140013938
0x140013925  cmp     ecx, 117h
0x14001392b  jnz     short loc_14001395A
0x14001392d  mov     edx, [rdx+4]
0x140013930  and     edx, 80h
0x140013936  jmp     short loc_14001394A
0x140013938  mov     eax, [rdx+4]
0x14001393b  mov     edx, eax
0x14001393d  and     edx, 40h
0x140013940  and     eax, 0B0h
0x140013945  shl     edx, 2
0x140013948  or      edx, eax
0x14001394a  shl     edx, 3
0x14001394d  or      edx, 206h
0x140013953  jmp     short loc_14001395F
0x140013955  xor     eax, eax
0x140013957  mov     [r8], rax
0x14001395a  mov     edx, 206h
0x14001395f  mov     [r8], edx
0x140013962  retn
```
