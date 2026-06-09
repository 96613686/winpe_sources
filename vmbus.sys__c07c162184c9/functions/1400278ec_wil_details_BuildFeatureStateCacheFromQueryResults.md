# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1400278ec`
- end: `0x140027943`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140027c70`
- `0x140030320`

## callees

- `0x1400278ec`

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
0x1400278ec  cmp     ecx, 80000022h
0x1400278f2  jz      short loc_140027935
0x1400278f4  cmp     ecx, 0C0000225h
0x1400278fa  jz      short loc_140027935
0x1400278fc  xor     eax, eax
0x1400278fe  mov     [r8], rax
0x140027901  test    ecx, ecx
0x140027903  jz      short loc_140027918
0x140027905  cmp     ecx, 117h
0x14002790b  jnz     short loc_14002793A
0x14002790d  mov     edx, [rdx+4]
0x140027910  and     edx, 80h
0x140027916  jmp     short loc_14002792A
0x140027918  mov     eax, [rdx+4]
0x14002791b  mov     edx, eax
0x14002791d  and     edx, 40h
0x140027920  and     eax, 0B0h
0x140027925  shl     edx, 2
0x140027928  or      edx, eax
0x14002792a  shl     edx, 3
0x14002792d  or      edx, 206h
0x140027933  jmp     short loc_14002793F
0x140027935  xor     eax, eax
0x140027937  mov     [r8], rax
0x14002793a  mov     edx, 206h
0x14002793f  mov     [r8], edx
0x140027942  retn
```
