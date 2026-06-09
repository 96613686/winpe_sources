# MinAsn1FindExtensionMatchingValue

- ea: `0x18004e128`
- end: `0x18004e1ec`
- name: `MinAsn1FindExtensionMatchingValue`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180045408`

## callees

- `0x18003391a`
- `0x180033980`
- `0x18004cc70`
- `0x18004e128`

## pseudocode

```c
char __fastcall MinAsn1FindExtensionMatchingValue(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rbx
  __int64 v4; // r8
  __int64 v5; // rcx
  unsigned int v7[4]; // [rsp+20h] [rbp-528h] BYREF
  _BYTE v8[72]; // [rsp+30h] [rbp-518h] BYREF
  _OWORD Buf2[75]; // [rsp+78h] [rbp-4D0h]

  v7[0] = 16;
  if ( (int)MinAsn1ParseExtensions(a3, v7, v8) > 0 )
  {
    for ( i = 0; (unsigned int)i < v7[0]; i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)&v8[80 * i + 32] == 10 )
      {
        v4 = *(_QWORD *)&v8[80 * i + 40];
        v5 = 0xC3782010401062BLL - *(_QWORD *)v4;
        if ( *(_QWORD *)v4 == 0xC3782010401062BLL )
          v5 = LOWORD(qword_180037460[1]) - (unsigned __int64)*(unsigned __int16 *)(v4 + 8);
        if ( !v5 && *(_DWORD *)&v8[80 * i + 64] == 31 && !memcmp_0(qword_180037658, *(const void **)&Buf2[5 * i], 0x1Fu) )
          return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004e128  mov     [rsp+arg_0], rbx
0x18004e12d  push    rdi
0x18004e12e  sub     rsp, 540h
0x18004e135  mov     rax, cs:__security_cookie
0x18004e13c  xor     rax, rsp
0x18004e13f  mov     [rsp+548h+var_18], rax
0x18004e147  mov     rdi, cs:off_180035988
0x18004e14e  lea     rdx, [rsp+548h+var_528]
0x18004e153  mov     rcx, r8
0x18004e156  mov     [rsp+548h+var_528], 10h
0x18004e15e  lea     r8, [rsp+548h+var_518]
0x18004e163  call    MinAsn1ParseExtensions
0x18004e168  test    eax, eax
0x18004e16a  jle     short loc_18004E1C8
0x18004e16c  xor     ebx, ebx
0x18004e16e  cmp     ebx, [rsp+548h+var_528]
0x18004e172  jnb     short loc_18004E1C8
0x18004e174  lea     rdx, [rbx+rbx*4]
0x18004e178  add     rdx, rdx
0x18004e17b  cmp     [rsp+rdx*8+548h+var_4F8], 0Ah
0x18004e180  jnz     short loc_18004E1C0
0x18004e182  mov     r8, [rsp+rdx*8+548h+var_4F0]
0x18004e187  mov     rcx, [rdi]
0x18004e18a  sub     rcx, [r8]
0x18004e18d  jnz     short loc_18004E19B
0x18004e18f  movzx   ecx, word ptr [rdi+8]
0x18004e193  movzx   eax, word ptr [r8+8]
0x18004e198  sub     rcx, rax
0x18004e19b  test    rcx, rcx
0x18004e19e  jnz     short loc_18004E1C0
0x18004e1a0  cmp     [rsp+rdx*8+548h+var_4D8], 1Fh
0x18004e1a5  jnz     short loc_18004E1C0
0x18004e1a7  mov     rdx, [rsp+rdx*8+548h+Buf2]; Buf2
0x18004e1ac  lea     r8d, [rcx+1Fh]; Size
0x18004e1b0  mov     rcx, cs:Buf1; Buf1
0x18004e1b7  call    memcmp_0
0x18004e1bc  test    eax, eax
0x18004e1be  jz      short loc_18004E1C4
0x18004e1c0  inc     ebx
0x18004e1c2  jmp     short loc_18004E16E
0x18004e1c4  mov     al, 1
0x18004e1c6  jmp     short loc_18004E1CA
0x18004e1c8  xor     al, al
0x18004e1ca  mov     rcx, [rsp+548h+var_18]
0x18004e1d2  xor     rcx, rsp; StackCookie
0x18004e1d5  call    __security_check_cookie
0x18004e1da  mov     rbx, [rsp+548h+arg_0]
0x18004e1e2  add     rsp, 540h
0x18004e1e9  pop     rdi
0x18004e1ea  retn
```
