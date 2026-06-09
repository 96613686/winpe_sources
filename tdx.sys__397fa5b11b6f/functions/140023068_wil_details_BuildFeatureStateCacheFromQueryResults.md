# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140023068`
- end: `0x1400230bf`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400233f0`
- `0x140024138`

## callees

- `0x140023068`

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
0x140023068  cmp     ecx, 80000022h
0x14002306e  jz      short loc_1400230B1
0x140023070  cmp     ecx, 0C0000225h
0x140023076  jz      short loc_1400230B1
0x140023078  xor     eax, eax
0x14002307a  mov     [r8], rax
0x14002307d  test    ecx, ecx
0x14002307f  jz      short loc_140023094
0x140023081  cmp     ecx, 117h
0x140023087  jnz     short loc_1400230B6
0x140023089  mov     edx, [rdx+4]
0x14002308c  and     edx, 80h
0x140023092  jmp     short loc_1400230A6
0x140023094  mov     eax, [rdx+4]
0x140023097  mov     edx, eax
0x140023099  and     edx, 40h
0x14002309c  and     eax, 0B0h
0x1400230a1  shl     edx, 2
0x1400230a4  or      edx, eax
0x1400230a6  shl     edx, 3
0x1400230a9  or      edx, 206h
0x1400230af  jmp     short loc_1400230BB
0x1400230b1  xor     eax, eax
0x1400230b3  mov     [r8], rax
0x1400230b6  mov     edx, 206h
0x1400230bb  mov     [r8], edx
0x1400230be  retn
```
