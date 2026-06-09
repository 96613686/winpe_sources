# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14001dbfc`
- end: `0x14001dc53`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001df80`
- `0x140020378`

## callees

- `0x14001dbfc`

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
0x14001dbfc  cmp     ecx, 80000022h
0x14001dc02  jz      short loc_14001DC45
0x14001dc04  cmp     ecx, 0C0000225h
0x14001dc0a  jz      short loc_14001DC45
0x14001dc0c  xor     eax, eax
0x14001dc0e  mov     [r8], rax
0x14001dc11  test    ecx, ecx
0x14001dc13  jz      short loc_14001DC28
0x14001dc15  cmp     ecx, 117h
0x14001dc1b  jnz     short loc_14001DC4A
0x14001dc1d  mov     edx, [rdx+4]
0x14001dc20  and     edx, 80h
0x14001dc26  jmp     short loc_14001DC3A
0x14001dc28  mov     eax, [rdx+4]
0x14001dc2b  mov     edx, eax
0x14001dc2d  and     edx, 40h
0x14001dc30  and     eax, 0B0h
0x14001dc35  shl     edx, 2
0x14001dc38  or      edx, eax
0x14001dc3a  shl     edx, 3
0x14001dc3d  or      edx, 206h
0x14001dc43  jmp     short loc_14001DC4F
0x14001dc45  xor     eax, eax
0x14001dc47  mov     [r8], rax
0x14001dc4a  mov     edx, 206h
0x14001dc4f  mov     [r8], edx
0x14001dc52  retn
```
