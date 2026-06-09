# INETADDR_SETSOCKADDR

- ea: `0x14000d678`
- end: `0x14000d729`
- name: `INETADDR_SETSOCKADDR`
- size: `177`
- prototype: `__int64 __fastcall(__int16, __int64, IN6_ADDR *, int, __int16)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x14001448c`
- `0x1400306d8`
- `0x1400308ac`
- `0x1400310f8`
- `0x1400314d4`
- `0x1400315a0`
- `0x1400320a8`
- `0x1400321a4`

## callees

- `0x14000d678`
- `0x14000d730`
- `0x1400138a0`

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
0x14000d678  mov     [rsp+arg_0], rbx
0x14000d67d  push    rdi
0x14000d67e  sub     rsp, 20h
0x14000d682  mov     eax, 17h
0x14000d687  lea     rdi, [rdx+8]
0x14000d68b  mov     r11d, r9d
0x14000d68e  mov     rbx, rdx
0x14000d691  cmp     cx, ax
0x14000d694  jnz     short loc_14000D704
0x14000d696  mov     [rdx], ax
0x14000d699  movzx   eax, [rsp+28h+arg_20]
0x14000d69e  mov     [rdx+2], ax
0x14000d6a2  mov     dword ptr [rdx+4], 0
0x14000d6a9  movups  xmm0, xmmword ptr [r8]
0x14000d6ad  mov     [rdx+18h], r9d
0x14000d6b1  movdqu  xmmword ptr [rdi], xmm0
0x14000d6b5  cmp     byte ptr [rdi], 0FFh
0x14000d6b8  jnz     short loc_14000D6C5
0x14000d6ba  movzx   r8d, byte ptr [rdi+1]
0x14000d6bf  and     r8d, 0Fh
0x14000d6c3  jmp     short loc_14000D6D0
0x14000d6c5  mov     rcx, rdi; a
0x14000d6c8  call    Ipv6UnicastAddressScope
0x14000d6cd  mov     r8d, eax
0x14000d6d0  mov     rcx, rdi; a
0x14000d6d3  call    IN6_IS_ADDR_LOOPBACK
0x14000d6d8  test    al, al
0x14000d6da  jnz     short loc_14000D6E2
0x14000d6dc  cmp     r8d, 0Eh
0x14000d6e0  jnz     short loc_14000D6EC
0x14000d6e2  mov     dword ptr [rbx+18h], 0
0x14000d6e9  xor     r11d, r11d
0x14000d6ec  mov     eax, r11d
0x14000d6ef  shr     eax, 1Ch
0x14000d6f2  cmp     eax, r8d
0x14000d6f5  jnz     short loc_14000D71D
0x14000d6f7  and     r11d, 0FFFFFFFh
0x14000d6fe  mov     [rbx+18h], r11d
0x14000d702  jmp     short loc_14000D71D
0x14000d704  mov     ecx, [r8]
0x14000d707  movzx   eax, [rsp+28h+arg_20]
0x14000d70c  mov     [rdx+2], ax
0x14000d710  xor     eax, eax
0x14000d712  mov     word ptr [rdx], 2
0x14000d717  mov     [rdx+4], ecx
0x14000d71a  mov     [rdi], rax
0x14000d71d  mov     rbx, [rsp+28h+arg_0]
0x14000d722  add     rsp, 20h
0x14000d726  pop     rdi
0x14000d727  retn
```
