# MinCryptQueryHashAlgorithmFromSignature

- ea: `0x18001618c`
- end: `0x1800162ac`
- name: `MinCryptQueryHashAlgorithmFromSignature`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180014d74`
- `0x180015f14`

## callees

- `0x180014614`
- `0x18001618c`
- `0x180033980`
- `0x18004cd54`
- `0x18004cffc`
- `0x18004e1f4`
- `0x18004e328`

## pseudocode

```c
__int64 __fastcall MinCryptQueryHashAlgorithmFromSignature(unsigned int *a1, _DWORD *a2, _DWORD *a3, _OWORD *a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int128 v13; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  _BYTE v17[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int128 v21; // [rsp+150h] [rbp+50h]

  v6 = *a1;
  v7 = *((_QWORD *)a1 + 1);
  v9 = -1073740760;
  v13 = 0;
  if ( (int)MinAsn1ParseSignedData(v7, v6, v14) >= 0 && v15 == 9 )
  {
    v10 = 0x7010DF78648862ALL - *(_QWORD *)v16;
    if ( *(_QWORD *)v16 == 0x7010DF78648862ALL )
      v10 = 2LL - *(unsigned __int8 *)(v16 + 8);
    if ( !v10 && v19 == 10 )
    {
      v11 = 0x23782010401062BLL - *(_QWORD *)v20;
      if ( *(_QWORD *)v20 == 0x23782010401062BLL )
        v11 = 1025LL - *(unsigned __int16 *)(v20 + 8);
      if ( !v11 )
      {
        if ( a4 )
          *a4 = v21;
        if ( (int)MinAsn1SignedDataGetContent(v14, &v13) > 0 && (int)MinAsn1ParseIndirectData(&v13, v14) >= 0 )
        {
          *a2 = MinCryptDecodeHashAlgorithmIdentifier(v18);
          if ( a3 )
            *a3 = (unsigned __int8)MinAsn1FindPageHashesAttribute(v17, 0);
          return 0;
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001618c  push    rbp
0x18001618e  push    rbx
0x18001618f  push    rsi
0x180016190  push    rdi
0x180016191  push    r14
0x180016193  lea     rbp, [rsp-70h]
0x180016198  sub     rsp, 170h
0x18001619f  mov     rax, cs:__security_cookie
0x1800161a6  xor     rax, rsp
0x1800161a9  mov     [rbp+90h+var_30], rax
0x1800161ad  mov     r14, rdx
0x1800161b0  mov     rsi, r8
0x1800161b3  mov     edx, [rcx]
0x1800161b5  lea     r8, [rsp+190h+var_160]
0x1800161ba  mov     rcx, [rcx+8]
0x1800161be  xorps   xmm0, xmm0
0x1800161c1  mov     rdi, r9
0x1800161c4  mov     ebx, 0C0000428h
0x1800161c9  movups  [rsp+190h+var_170], xmm0
0x1800161ce  call    MinAsn1ParseSignedData
0x1800161d3  test    eax, eax
0x1800161d5  js      loc_18001628F
0x1800161db  cmp     [rsp+190h+var_140], 9
0x1800161e0  jnz     loc_18001628F
0x1800161e6  mov     rdx, [rsp+190h+var_138]
0x1800161eb  mov     rcx, cs:qword_180052018
0x1800161f2  sub     rcx, [rdx]
0x1800161f5  jnz     short loc_180016205
0x1800161f7  movzx   ecx, cs:byte_180052020
0x1800161fe  movzx   eax, byte ptr [rdx+8]
0x180016202  sub     rcx, rax
0x180016205  test    rcx, rcx
0x180016208  jnz     loc_18001628F
0x18001620e  cmp     [rbp+90h+var_110], 0Ah
0x180016212  jnz     short loc_18001628F
0x180016214  mov     rdx, [rbp+90h+var_108]
0x180016218  mov     rcx, cs:qword_1800521E8
0x18001621f  sub     rcx, [rdx]
0x180016222  jnz     short loc_180016232
0x180016224  movzx   ecx, cs:word_1800521F0
0x18001622b  movzx   eax, word ptr [rdx+8]
0x18001622f  sub     rcx, rax
0x180016232  test    rcx, rcx
0x180016235  jnz     short loc_18001628F
0x180016237  test    rdi, rdi
0x18001623a  jz      short loc_180016244
0x18001623c  movaps  xmm0, [rbp+90h+var_40]
0x180016240  movdqu  xmmword ptr [rdi], xmm0
0x180016244  lea     rdx, [rsp+190h+var_170]
0x180016249  lea     rcx, [rsp+190h+var_160]
0x18001624e  call    MinAsn1SignedDataGetContent
0x180016253  test    eax, eax
0x180016255  jle     short loc_18001628F
0x180016257  lea     rdx, [rsp+190h+var_160]
0x18001625c  lea     rcx, [rsp+190h+var_170]
0x180016261  call    MinAsn1ParseIndirectData
0x180016266  test    eax, eax
0x180016268  js      short loc_18001628F
0x18001626a  lea     rcx, [rsp+190h+var_120]
0x18001626f  call    MinCryptDecodeHashAlgorithmIdentifier
0x180016274  mov     [r14], eax
0x180016277  test    rsi, rsi
0x18001627a  jz      short loc_18001628D
0x18001627c  xor     edx, edx
0x18001627e  lea     rcx, [rsp+190h+var_130]
0x180016283  call    MinAsn1FindPageHashesAttribute
0x180016288  movzx   eax, al
0x18001628b  mov     [rsi], eax
0x18001628d  xor     ebx, ebx
0x18001628f  mov     eax, ebx
0x180016291  mov     rcx, [rbp+90h+var_30]
0x180016295  xor     rcx, rsp; StackCookie
0x180016298  call    __security_check_cookie
0x18001629d  add     rsp, 170h
0x1800162a4  pop     r14
0x1800162a6  pop     rdi
0x1800162a7  pop     rsi
0x1800162a8  pop     rbx
0x1800162a9  pop     rbp
0x1800162aa  retn
```
