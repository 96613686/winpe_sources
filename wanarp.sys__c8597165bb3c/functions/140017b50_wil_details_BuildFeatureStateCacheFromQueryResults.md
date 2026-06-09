# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x140017b50`
- end: `0x140017ba7`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140017ee0`
- `0x14001a91c`

## callees

- `0x140017b50`

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
0x140017b50  cmp     ecx, 80000022h
0x140017b56  jz      short loc_140017B99
0x140017b58  cmp     ecx, 0C0000225h
0x140017b5e  jz      short loc_140017B99
0x140017b60  xor     eax, eax
0x140017b62  mov     [r8], rax
0x140017b65  test    ecx, ecx
0x140017b67  jz      short loc_140017B7C
0x140017b69  cmp     ecx, 117h
0x140017b6f  jnz     short loc_140017B9E
0x140017b71  mov     edx, [rdx+4]
0x140017b74  and     edx, 80h
0x140017b7a  jmp     short loc_140017B8E
0x140017b7c  mov     eax, [rdx+4]
0x140017b7f  mov     edx, eax
0x140017b81  and     edx, 40h
0x140017b84  and     eax, 0B0h
0x140017b89  shl     edx, 2
0x140017b8c  or      edx, eax
0x140017b8e  shl     edx, 3
0x140017b91  or      edx, 206h
0x140017b97  jmp     short loc_140017BA3
0x140017b99  xor     eax, eax
0x140017b9b  mov     [r8], rax
0x140017b9e  mov     edx, 206h
0x140017ba3  mov     [r8], edx
0x140017ba6  retn
```
