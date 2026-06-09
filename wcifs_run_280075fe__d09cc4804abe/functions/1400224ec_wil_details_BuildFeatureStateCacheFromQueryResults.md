# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1400224ec`
- end: `0x140022543`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140022820`
- `0x140036170`

## callees

- `0x1400224ec`

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
0x1400224ec  cmp     ecx, 80000022h
0x1400224f2  jz      short loc_140022535
0x1400224f4  cmp     ecx, 0C0000225h
0x1400224fa  jz      short loc_140022535
0x1400224fc  xor     eax, eax
0x1400224fe  mov     [r8], rax
0x140022501  test    ecx, ecx
0x140022503  jz      short loc_140022518
0x140022505  cmp     ecx, 117h
0x14002250b  jnz     short loc_14002253A
0x14002250d  mov     edx, [rdx+4]
0x140022510  and     edx, 80h
0x140022516  jmp     short loc_14002252A
0x140022518  mov     eax, [rdx+4]
0x14002251b  mov     edx, eax
0x14002251d  and     edx, 40h
0x140022520  and     eax, 0B0h
0x140022525  shl     edx, 2
0x140022528  or      edx, eax
0x14002252a  shl     edx, 3
0x14002252d  or      edx, 206h
0x140022533  jmp     short loc_14002253F
0x140022535  xor     eax, eax
0x140022537  mov     [r8], rax
0x14002253a  mov     edx, 206h
0x14002253f  mov     [r8], edx
0x140022542  retn
```
