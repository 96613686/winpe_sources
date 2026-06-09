# MinCryptDecodeHashAlgorithmIdentifier

- ea: `0x180014614`
- end: `0x180014662`
- name: `MinCryptDecodeHashAlgorithmIdentifier`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800150c0`
- `0x180015360`
- `0x180015624`
- `0x18001618c`
- `0x180016f2c`
- `0x1800458d8`
- `0x180045a08`

## callees

- `0x180014614`
- `0x180014668`
- `0x180033980`
- `0x18004c8d4`

## pseudocode

```c
__int64 __fastcall MinCryptDecodeHashAlgorithmIdentifier(__int64 a1)
{
  _BYTE v2[32]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v3[8]; // [rsp+40h] [rbp-38h] BYREF

  if ( (int)MinAsn1ParseAlgorithmIdentifier(a1, v2) >= 0 )
    return MinCryptDecodeOid((__int64)&qword_180053820, 0x17u, v3);
  else
    return 0;
}

```

## disassembly

```asm
0x180014614  sub     rsp, 78h
0x180014618  mov     rax, cs:__security_cookie
0x18001461f  xor     rax, rsp
0x180014622  mov     [rsp+78h+var_18], rax
0x180014627  lea     rdx, [rsp+78h+var_58]
0x18001462c  call    MinAsn1ParseAlgorithmIdentifier
0x180014631  test    eax, eax
0x180014633  jns     short loc_180014639
0x180014635  xor     eax, eax
0x180014637  jmp     short loc_18001464F
0x180014639  lea     r8, [rsp+78h+var_38]
0x18001463e  mov     edx, 17h
0x180014643  lea     rcx, qword_180053820
0x18001464a  call    MinCryptDecodeOid
0x18001464f  mov     rcx, [rsp+78h+var_18]
0x180014654  xor     rcx, rsp; StackCookie
0x180014657  call    __security_check_cookie
0x18001465c  add     rsp, 78h
0x180014660  retn
```
