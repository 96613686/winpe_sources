# ClassifyGuid

- ea: `0x180001940`
- end: `0x1800019a9`
- name: `ClassifyGuid`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001220`
- `0x180001490`
- `0x1800093c0`
- `0x180009a90`
- `0x180009be0`

## callees

- `0x180001940`

## pseudocode

```c
__int64 __fastcall ClassifyGuid(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 result; // rax
  __int64 v4; // rdx

  v1 = *a1 - *(_QWORD *)&OID_VBSSIP.Data1;
  if ( *a1 == *(_QWORD *)&OID_VBSSIP.Data1 )
    v1 = a1[1] - *(_QWORD *)OID_VBSSIP.Data4;
  if ( !v1 )
    return 1;
  v2 = *a1 - *(_QWORD *)&OID_JSSIP.Data1;
  if ( *a1 == *(_QWORD *)&OID_JSSIP.Data1 )
    v2 = a1[1] - *(_QWORD *)OID_JSSIP.Data4;
  if ( !v2 )
    return 2;
  v4 = *a1 - *(_QWORD *)&OID_WSFSIP.Data1;
  if ( *a1 == *(_QWORD *)&OID_WSFSIP.Data1 )
    v4 = a1[1] - *(_QWORD *)OID_WSFSIP.Data4;
  result = 0;
  if ( !v4 )
    return 3;
  return result;
}

```

## disassembly

```asm
0x180001940  mov     rax, [rcx]
0x180001943  sub     rax, qword ptr cs:OID_VBSSIP.Data1
0x18000194a  jnz     short loc_180001957
0x18000194c  mov     rax, [rcx+8]
0x180001950  sub     rax, qword ptr cs:OID_VBSSIP.Data4
0x180001957  test    rax, rax
0x18000195a  jz      short loc_1800019A3
0x18000195c  mov     rax, [rcx]
0x18000195f  sub     rax, qword ptr cs:OID_JSSIP.Data1
0x180001966  jnz     short loc_180001973
0x180001968  mov     rax, [rcx+8]
0x18000196c  sub     rax, qword ptr cs:OID_JSSIP.Data4
0x180001973  test    rax, rax
0x180001976  jnz     short loc_18000197E
0x180001978  mov     eax, 2
0x18000197d  retn
0x18000197e  mov     rdx, [rcx]
0x180001981  sub     rdx, qword ptr cs:OID_WSFSIP.Data1
0x180001988  jnz     short loc_180001995
0x18000198a  mov     rdx, [rcx+8]
0x18000198e  sub     rdx, qword ptr cs:OID_WSFSIP.Data4
0x180001995  xor     eax, eax
0x180001997  mov     ecx, 3
0x18000199c  test    rdx, rdx
0x18000199f  cmovz   eax, ecx
0x1800019a2  retn
0x1800019a3  mov     eax, 1
0x1800019a8  retn
```
