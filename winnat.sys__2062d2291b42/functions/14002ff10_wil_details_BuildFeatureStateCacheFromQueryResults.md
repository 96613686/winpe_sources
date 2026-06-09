# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x14002ff10`
- end: `0x14002ff67`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400302a0`
- `0x140036494`

## callees

- `0x14002ff10`

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
0x14002ff10  cmp     ecx, 80000022h
0x14002ff16  jz      short loc_14002FF59
0x14002ff18  cmp     ecx, 0C0000225h
0x14002ff1e  jz      short loc_14002FF59
0x14002ff20  xor     eax, eax
0x14002ff22  mov     [r8], rax
0x14002ff25  test    ecx, ecx
0x14002ff27  jz      short loc_14002FF3C
0x14002ff29  cmp     ecx, 117h
0x14002ff2f  jnz     short loc_14002FF5E
0x14002ff31  mov     edx, [rdx+4]
0x14002ff34  and     edx, 80h
0x14002ff3a  jmp     short loc_14002FF4E
0x14002ff3c  mov     eax, [rdx+4]
0x14002ff3f  mov     edx, eax
0x14002ff41  and     edx, 40h
0x14002ff44  and     eax, 0B0h
0x14002ff49  shl     edx, 2
0x14002ff4c  or      edx, eax
0x14002ff4e  shl     edx, 3
0x14002ff51  or      edx, 206h
0x14002ff57  jmp     short loc_14002FF63
0x14002ff59  xor     eax, eax
0x14002ff5b  mov     [r8], rax
0x14002ff5e  mov     edx, 206h
0x14002ff63  mov     [r8], edx
0x14002ff66  retn
```
