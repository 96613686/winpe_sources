# MinCryptIsKeyPresent

- ea: `0x1800181e4`
- end: `0x1800182bd`
- name: `MinCryptIsKeyPresent`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016f2c`

## callees

- `0x1800181e4`
- `0x180033980`
- `0x18004cf24`
- `0x18004cf6c`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180018277`
- `securekernel!RtlCompareMemory` at `0x180018277`

## pseudocode

```c
__int64 __fastcall MinCryptIsKeyPresent(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // esi
  unsigned int v6; // edi
  char *v7; // rbp
  _BYTE v9[32]; // [rsp+20h] [rbp-B8h] BYREF
  SIZE_T Length; // [rsp+40h] [rbp-98h]
  void *Source1; // [rsp+48h] [rbp-90h]
  _BYTE v12[48]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v13[16]; // [rsp+90h] [rbp-48h] BYREF

  v5 = 0;
  if ( (int)MinAsn1ParsePublicKeyInfo(a1, v12) < 0 || (int)MinAsn1ParseRSAPublicKey(v13, v9) < 0 )
    return 0;
  v6 = Length;
  v7 = (char *)Source1;
  if ( (unsigned int)Length <= 1 )
  {
LABEL_6:
    if ( !v6 )
      return 0;
    goto LABEL_7;
  }
  if ( !*(_BYTE *)Source1 )
  {
    v7 = (char *)Source1 + 1;
    v6 = Length - 1;
    goto LABEL_6;
  }
LABEL_7:
  if ( v6 <= 0x200 )
  {
    while ( v5 < a3 )
    {
      if ( v6 == *(_DWORD *)(a2 + 16LL * v5) && RtlCompareMemory(v7, *(const void **)(a2 + 16LL * v5 + 8), v6) == v6 )
        return 1;
      ++v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800181e4  mov     [rsp+arg_10], rbx
0x1800181e9  push    rbp
0x1800181ea  push    rsi
0x1800181eb  push    rdi
0x1800181ec  push    r14
0x1800181ee  push    r15
0x1800181f0  sub     rsp, 0B0h
0x1800181f7  mov     rax, cs:__security_cookie
0x1800181fe  xor     rax, rsp
0x180018201  mov     [rsp+0D8h+var_38], rax
0x180018209  mov     r14, rdx
0x18001820c  mov     r15d, r8d
0x18001820f  lea     rdx, [rsp+0D8h+var_78]
0x180018214  call    MinAsn1ParsePublicKeyInfo
0x180018219  xor     esi, esi
0x18001821b  test    eax, eax
0x18001821d  js      short loc_180018293
0x18001821f  lea     rdx, [rsp+0D8h+var_B8]
0x180018224  lea     rcx, [rsp+0D8h+var_48]
0x18001822c  call    MinAsn1ParseRSAPublicKey
0x180018231  test    eax, eax
0x180018233  js      short loc_180018293
0x180018235  mov     edi, dword ptr [rsp+0D8h+Length]
0x180018239  mov     rbp, [rsp+0D8h+Source1]
0x18001823e  cmp     edi, 1
0x180018241  jbe     short loc_18001824E
0x180018243  cmp     [rbp+0], sil
0x180018247  jnz     short loc_180018252
0x180018249  inc     rbp
0x18001824c  dec     edi
0x18001824e  test    edi, edi
0x180018250  jz      short loc_180018293
0x180018252  cmp     edi, 200h
0x180018258  ja      short loc_180018293
0x18001825a  cmp     esi, r15d
0x18001825d  jnb     short loc_180018293
0x18001825f  mov     edx, esi
0x180018261  add     rdx, rdx
0x180018264  cmp     edi, [r14+rdx*8]
0x180018268  jnz     short loc_180018288
0x18001826a  mov     rdx, [r14+rdx*8+8]; Source2
0x18001826f  mov     rcx, rbp; Source1
0x180018272  mov     r8d, edi; Length
0x180018275  mov     ebx, edi
0x180018277  call    cs:__imp_RtlCompareMemory
0x18001827e  nop     dword ptr [rax+rax+00h]
0x180018283  cmp     rax, rbx
0x180018286  jz      short loc_18001828C
0x180018288  inc     esi
0x18001828a  jmp     short loc_18001825A
0x18001828c  mov     eax, 1
0x180018291  jmp     short loc_180018295
0x180018293  xor     eax, eax
0x180018295  mov     rcx, [rsp+0D8h+var_38]
0x18001829d  xor     rcx, rsp; StackCookie
0x1800182a0  call    __security_check_cookie
0x1800182a5  mov     rbx, [rsp+0D8h+arg_10]
0x1800182ad  add     rsp, 0B0h
0x1800182b4  pop     r15
0x1800182b6  pop     r14
0x1800182b8  pop     rdi
0x1800182b9  pop     rsi
0x1800182ba  pop     rbp
0x1800182bb  retn
```
