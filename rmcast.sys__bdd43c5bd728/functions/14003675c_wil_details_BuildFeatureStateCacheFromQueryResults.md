# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14003675c`
- end: `0x1400367b3`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140036ae0`
- `0x14003a2fc`

## callees

- `0x14003675c`

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
0x14003675c  cmp     ecx, 80000022h
0x140036762  jz      short loc_1400367A5
0x140036764  cmp     ecx, 0C0000225h
0x14003676a  jz      short loc_1400367A5
0x14003676c  xor     eax, eax
0x14003676e  mov     [r8], rax
0x140036771  test    ecx, ecx
0x140036773  jz      short loc_140036788
0x140036775  cmp     ecx, 117h
0x14003677b  jnz     short loc_1400367AA
0x14003677d  mov     edx, [rdx+4]
0x140036780  and     edx, 80h
0x140036786  jmp     short loc_14003679A
0x140036788  mov     eax, [rdx+4]
0x14003678b  mov     edx, eax
0x14003678d  and     edx, 40h
0x140036790  and     eax, 0B0h
0x140036795  shl     edx, 2
0x140036798  or      edx, eax
0x14003679a  shl     edx, 3
0x14003679d  or      edx, 206h
0x1400367a3  jmp     short loc_1400367AF
0x1400367a5  xor     eax, eax
0x1400367a7  mov     [r8], rax
0x1400367aa  mov     edx, 206h
0x1400367af  mov     [r8], edx
0x1400367b2  retn
```
