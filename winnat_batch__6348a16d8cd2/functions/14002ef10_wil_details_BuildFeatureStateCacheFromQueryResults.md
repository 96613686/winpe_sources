# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14002ef10`
- end: `0x14002ef67`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002f240`
- `0x140035494`

## callees

- `0x14002ef10`

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
0x14002ef10  cmp     ecx, 80000022h
0x14002ef16  jz      short loc_14002EF59
0x14002ef18  cmp     ecx, 0C0000225h
0x14002ef1e  jz      short loc_14002EF59
0x14002ef20  xor     eax, eax
0x14002ef22  mov     [r8], rax
0x14002ef25  test    ecx, ecx
0x14002ef27  jz      short loc_14002EF3C
0x14002ef29  cmp     ecx, 117h
0x14002ef2f  jnz     short loc_14002EF5E
0x14002ef31  mov     edx, [rdx+4]
0x14002ef34  and     edx, 80h
0x14002ef3a  jmp     short loc_14002EF4E
0x14002ef3c  mov     eax, [rdx+4]
0x14002ef3f  mov     edx, eax
0x14002ef41  and     edx, 40h
0x14002ef44  and     eax, 0B0h
0x14002ef49  shl     edx, 2
0x14002ef4c  or      edx, eax
0x14002ef4e  shl     edx, 3
0x14002ef51  or      edx, 206h
0x14002ef57  jmp     short loc_14002EF63
0x14002ef59  xor     eax, eax
0x14002ef5b  mov     [r8], rax
0x14002ef5e  mov     edx, 206h
0x14002ef63  mov     [r8], edx
0x14002ef66  retn
```
