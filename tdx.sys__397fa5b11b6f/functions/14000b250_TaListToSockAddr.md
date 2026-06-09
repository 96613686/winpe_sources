# TaListToSockAddr

- ea: `0x14000b250`
- end: `0x14000b324`
- name: `TaListToSockAddr`
- size: `212`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140004df4`
- `0x140006608`
- `0x140011cb4`

## callees

- `0x14000b250`
- `0x14000ca98`
- `0x140018600`

## pseudocode

```c
void *__fastcall TaListToSockAddr(__int64 a1, char a2, char *a3)
{
  _WORD *v5; // rdx
  size_t v6; // r8
  void *result; // rax
  __int16 v8; // ax
  unsigned int v9; // r8d
  _BYTE *v10; // r9
  __int64 v11; // r10
  SCOPE_LEVEL v12; // r11d

  v5 = (_WORD *)(a1 + 6);
  if ( a2 && *v5 == 2 )
  {
    v8 = *(_WORD *)(a1 + 8);
    *(_WORD *)a3 = 23;
    *((_WORD *)a3 + 1) = v8;
    *((_DWORD *)a3 + 1) = 0;
    *(IN6_ADDR *)(a3 + 8) = in6addr_v4mappedprefix;
    a3[20] = *(_BYTE *)(a1 + 10);
    a3[21] = *(_BYTE *)(a1 + 11);
    a3[22] = *(_BYTE *)(a1 + 12);
    a3[23] = *(_BYTE *)(a1 + 13);
    *((SCOPE_ID *)a3 + 6) = scopeid_unspecified;
    v12 = Ipv4AddressScope((const UCHAR *)(a1 + 10));
    if ( v12 == ScopeLevelGlobal || *v10 == 127 )
    {
      *(_DWORD *)(v11 + 24) = 0;
      v9 = 0;
    }
    result = (void *)(v9 >> 28);
    if ( (_DWORD)result == v12 )
      *(_DWORD *)(v11 + 24) = v9 & 0xFFFFFFF;
  }
  else
  {
    v6 = 16;
    if ( *v5 != 2 )
      v6 = 28;
    return memmove(a3, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000b250  sub     rsp, 28h
0x14000b254  movzx   eax, dl
0x14000b257  mov     r10, r8
0x14000b25a  lea     rdx, [rcx+6]; Src
0x14000b25e  test    al, al
0x14000b260  jnz     short loc_14000B283
0x14000b262  cmp     word ptr [rdx], 2
0x14000b266  mov     eax, 1Ch
0x14000b26b  mov     r8d, 10h
0x14000b271  mov     rcx, r10; void *
0x14000b274  cmovnz  r8d, eax; Size
0x14000b278  call    memmove
0x14000b27d  add     rsp, 28h
0x14000b281  retn
0x14000b283  cmp     word ptr [rdx], 2
0x14000b287  jnz     short loc_14000B262
0x14000b289  movzx   eax, word ptr [rcx+8]
0x14000b28d  lea     r9, [rcx+0Ah]
0x14000b291  movups  xmm0, xmmword ptr cs:in6addr_v4mappedprefix.u
0x14000b298  mov     word ptr [r8], 17h
0x14000b29e  mov     rcx, r9; Address
0x14000b2a1  mov     [r8+2], ax
0x14000b2a6  mov     [rsp+28h+var_8], rbx
0x14000b2ab  xor     ebx, ebx
0x14000b2ad  mov     [r8+4], ebx
0x14000b2b1  movups  xmmword ptr [r8+8], xmm0
0x14000b2b6  movzx   eax, byte ptr [r9]
0x14000b2ba  mov     [r8+14h], al
0x14000b2be  movzx   eax, byte ptr [r9+1]
0x14000b2c3  mov     [r8+15h], al
0x14000b2c7  movzx   eax, byte ptr [r9+2]
0x14000b2cc  mov     [r8+16h], al
0x14000b2d0  movzx   eax, byte ptr [r9+3]
0x14000b2d5  mov     [r8+17h], al
0x14000b2d9  mov     r8d, dword ptr cs:scopeid_unspecified
0x14000b2e0  mov     [r10+18h], r8d
0x14000b2e4  call    Ipv4AddressScope
0x14000b2e9  mov     r11d, eax
0x14000b2ec  cmp     eax, 0Eh
0x14000b2ef  jnz     short loc_14000B31C
0x14000b2f1  mov     [r10+18h], ebx
0x14000b2f5  mov     r8d, ebx
0x14000b2f8  mov     rbx, [rsp+28h+var_8]
0x14000b2fd  mov     eax, r8d
0x14000b300  shr     eax, 1Ch
0x14000b303  cmp     eax, r11d
0x14000b306  jnz     loc_14000B27D
0x14000b30c  and     r8d, 0FFFFFFFh
0x14000b313  mov     [r10+18h], r8d
0x14000b317  jmp     loc_14000B27D
0x14000b31c  cmp     byte ptr [r9], 7Fh
0x14000b320  jz      short loc_14000B2F1
0x14000b322  jmp     short loc_14000B2F8
```
