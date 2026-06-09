# I_MinCryptGetPlatformManifestBinaryIDAttribute

- ea: `0x180014ec4`
- end: `0x180014f58`
- name: `I_MinCryptGetPlatformManifestBinaryIDAttribute`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015624`

## callees

- `0x180014ae0`
- `0x180014ec4`
- `0x18004d178`
- `0x18004dd2c`

## pseudocode

```c
__int64 __fastcall I_MinCryptGetPlatformManifestBinaryIDAttribute(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  __int128 v6; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+18h] BYREF
  int v8; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+58h] [rbp+28h] BYREF

  v2 = *(_QWORD *)(a2 + 16);
  v9 = 0;
  v7 = 0;
  *(_OWORD *)(v2 + 72) = 0;
  *(_OWORD *)(v2 + 88) = 0;
  v6 = 0;
  if ( (unsigned __int8)MinAsn1ParseSingleAttributeValue(&qword_180052418, a1, 4, &v6)
    && (int)MinAsn1ExtractContent(*((_QWORD *)&v6 + 1), (unsigned int)v6, &v7, &v9) >= 0 )
  {
    v4 = *(_QWORD *)(a2 + 16) + 72LL;
    v8 = 32;
    I_Base64Decode(v9, v7, v4, &v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180014ec4  mov     [rsp-8+arg_0], rbx
0x180014ec9  push    rbp
0x180014eca  mov     rbp, rsp
0x180014ecd  sub     rsp, 30h
0x180014ed1  mov     rax, [rdx+10h]
0x180014ed5  lea     r9, [rbp+var_10]
0x180014ed9  xorps   xmm0, xmm0
0x180014edc  mov     [rbp+arg_18], 0
0x180014ee4  mov     rbx, rdx
0x180014ee7  mov     [rbp+arg_8], 0
0x180014eee  mov     rdx, rcx
0x180014ef1  mov     r8d, 4
0x180014ef7  movups  xmmword ptr [rax+48h], xmm0
0x180014efb  lea     rcx, qword_180052418
0x180014f02  movups  xmmword ptr [rax+58h], xmm0
0x180014f06  movups  [rbp+var_10], xmm0
0x180014f0a  call    MinAsn1ParseSingleAttributeValue
0x180014f0f  test    al, al
0x180014f11  jz      short loc_180014F4A
0x180014f13  mov     edx, dword ptr [rbp+var_10]
0x180014f16  lea     r9, [rbp+arg_18]
0x180014f1a  mov     rcx, qword ptr [rbp+var_10+8]
0x180014f1e  lea     r8, [rbp+arg_8]
0x180014f22  call    MinAsn1ExtractContent
0x180014f27  test    eax, eax
0x180014f29  js      short loc_180014F4A
0x180014f2b  mov     r8, [rbx+10h]
0x180014f2f  lea     r9, [rbp+arg_10]
0x180014f33  mov     edx, [rbp+arg_8]
0x180014f36  add     r8, 48h ; 'H'
0x180014f3a  mov     rcx, [rbp+arg_18]
0x180014f3e  mov     [rbp+arg_10], 20h ; ' '
0x180014f45  call    I_Base64Decode
0x180014f4a  mov     rbx, [rsp+30h+arg_0]
0x180014f4f  xor     eax, eax
0x180014f51  add     rsp, 30h
0x180014f55  pop     rbp
0x180014f56  retn
```
