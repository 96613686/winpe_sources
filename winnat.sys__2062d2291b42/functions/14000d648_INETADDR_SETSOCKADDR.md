# INETADDR_SETSOCKADDR

- ea: `0x14000d648`
- end: `0x14000d6f9`
- name: `INETADDR_SETSOCKADDR`
- size: `177`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140014dcc`
- `0x140031808`
- `0x1400319dc`
- `0x140032228`
- `0x140032604`
- `0x1400326d0`
- `0x1400331d8`
- `0x1400332d4`

## callees

- `0x14000d648`
- `0x14000d700`
- `0x1400141e0`

## pseudocode

```c
__int64 __fastcall INETADDR_SETSOCKADDR(__int16 a1, __int64 a2, IN6_ADDR *a3, int a4, __int16 a5)
{
  IN6_ADDR *v5; // rdi
  IN6_ADDR v7; // xmm0
  int v8; // r8d
  unsigned int v9; // r11d
  __int64 result; // rax
  int v11; // ecx

  v5 = (IN6_ADDR *)(a2 + 8);
  if ( a1 == 23 )
  {
    *(_WORD *)a2 = 23;
    *(_WORD *)(a2 + 2) = a5;
    *(_DWORD *)(a2 + 4) = 0;
    v7 = *a3;
    *(_DWORD *)(a2 + 24) = a4;
    *v5 = v7;
    if ( v5->u.Byte[0] != 0xFF )
      Ipv6UnicastAddressScope((IN6_ADDR *)(a2 + 8));
    if ( IN6_IS_ADDR_LOOPBACK(v5) || v8 == 14 )
    {
      *(_DWORD *)(a2 + 24) = 0;
      v9 = 0;
    }
    result = v9 >> 28;
    if ( (_DWORD)result == v8 )
      *(_DWORD *)(a2 + 24) = v9 & 0xFFFFFFF;
  }
  else
  {
    v11 = *(_DWORD *)a3->u.Byte;
    *(_WORD *)(a2 + 2) = a5;
    result = 0;
    *(_WORD *)a2 = 2;
    *(_DWORD *)(a2 + 4) = v11;
    *(_QWORD *)v5->u.Byte = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d648  mov     [rsp+arg_0], rbx
0x14000d64d  push    rdi
0x14000d64e  sub     rsp, 20h
0x14000d652  mov     eax, 17h
0x14000d657  lea     rdi, [rdx+8]
0x14000d65b  mov     r11d, r9d
0x14000d65e  mov     rbx, rdx
0x14000d661  cmp     cx, ax
0x14000d664  jnz     short loc_14000D6D4
0x14000d666  mov     [rdx], ax
0x14000d669  movzx   eax, [rsp+28h+arg_20]
0x14000d66e  mov     [rdx+2], ax
0x14000d672  mov     dword ptr [rdx+4], 0
0x14000d679  movups  xmm0, xmmword ptr [r8]
0x14000d67d  mov     [rdx+18h], r9d
0x14000d681  movdqu  xmmword ptr [rdi], xmm0
0x14000d685  cmp     byte ptr [rdi], 0FFh
0x14000d688  jnz     short loc_14000D695
0x14000d68a  movzx   r8d, byte ptr [rdi+1]
0x14000d68f  and     r8d, 0Fh
0x14000d693  jmp     short loc_14000D6A0
0x14000d695  mov     rcx, rdi; a
0x14000d698  call    Ipv6UnicastAddressScope
0x14000d69d  mov     r8d, eax
0x14000d6a0  mov     rcx, rdi; a
0x14000d6a3  call    IN6_IS_ADDR_LOOPBACK
0x14000d6a8  test    al, al
0x14000d6aa  jnz     short loc_14000D6B2
0x14000d6ac  cmp     r8d, 0Eh
0x14000d6b0  jnz     short loc_14000D6BC
0x14000d6b2  mov     dword ptr [rbx+18h], 0
0x14000d6b9  xor     r11d, r11d
0x14000d6bc  mov     eax, r11d
0x14000d6bf  shr     eax, 1Ch
0x14000d6c2  cmp     eax, r8d
0x14000d6c5  jnz     short loc_14000D6ED
0x14000d6c7  and     r11d, 0FFFFFFFh
0x14000d6ce  mov     [rbx+18h], r11d
0x14000d6d2  jmp     short loc_14000D6ED
0x14000d6d4  mov     ecx, [r8]
0x14000d6d7  movzx   eax, [rsp+28h+arg_20]
0x14000d6dc  mov     [rdx+2], ax
0x14000d6e0  xor     eax, eax
0x14000d6e2  mov     word ptr [rdx], 2
0x14000d6e7  mov     [rdx+4], ecx
0x14000d6ea  mov     [rdi], rax
0x14000d6ed  mov     rbx, [rsp+28h+arg_0]
0x14000d6f2  add     rsp, 20h
0x14000d6f6  pop     rdi
0x14000d6f7  retn
```
