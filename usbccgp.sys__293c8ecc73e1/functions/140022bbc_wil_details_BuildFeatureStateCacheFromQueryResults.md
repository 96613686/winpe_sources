# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140022bbc`
- end: `0x140022c13`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140022de0`
- `0x14002f328`

## callees

- `0x140022bbc`

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
0x140022bbc  cmp     ecx, 80000022h
0x140022bc2  jz      short loc_140022C05
0x140022bc4  cmp     ecx, 0C0000225h
0x140022bca  jz      short loc_140022C05
0x140022bcc  xor     eax, eax
0x140022bce  mov     [r8], rax
0x140022bd1  test    ecx, ecx
0x140022bd3  jz      short loc_140022BE8
0x140022bd5  cmp     ecx, 117h
0x140022bdb  jnz     short loc_140022C0A
0x140022bdd  mov     edx, [rdx+4]
0x140022be0  and     edx, 80h
0x140022be6  jmp     short loc_140022BFA
0x140022be8  mov     eax, [rdx+4]
0x140022beb  mov     edx, eax
0x140022bed  and     edx, 40h
0x140022bf0  and     eax, 0B0h
0x140022bf5  shl     edx, 2
0x140022bf8  or      edx, eax
0x140022bfa  shl     edx, 3
0x140022bfd  or      edx, 206h
0x140022c03  jmp     short loc_140022C0F
0x140022c05  xor     eax, eax
0x140022c07  mov     [r8], rax
0x140022c0a  mov     edx, 206h
0x140022c0f  mov     [r8], edx
0x140022c12  retn
```
