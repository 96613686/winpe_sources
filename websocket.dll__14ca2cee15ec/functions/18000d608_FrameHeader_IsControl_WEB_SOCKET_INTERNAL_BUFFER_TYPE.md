# FrameHeader::IsControl(WEB_SOCKET_INTERNAL_BUFFER_TYPE)

- ea: `0x18000d608`
- end: `0x18000d641`
- name: `?IsControl@FrameHeader@@SAHW4WEB_SOCKET_INTERNAL_BUFFER_TYPE@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf54`
- `0x18000c19c`
- `0x18000c300`
- `0x18000c8f0`
- `0x18000d51c`

## callees

- `0x18000d608`

## pseudocode

```c
__int64 __fastcall FrameHeader::IsControl(int a1)
{
  unsigned int v1; // edx

  if ( a1 >= 0 )
    return ((unsigned __int8)__ROR2__((_WORD)a1 << 7, 8) >> 3) & 1;
  v1 = 1;
  if ( (unsigned int)(a1 + 2147483644) > 2 )
    return (unsigned int)(a1 + 0x40000000) <= 1;
  return v1;
}

```

## disassembly

```asm
0x18000d608  test    ecx, 80000000h
0x18000d60e  jbe     short loc_18000D62F
0x18000d610  lea     eax, [rcx+7FFFFFFCh]
0x18000d616  mov     edx, 1
0x18000d61b  cmp     eax, 2
0x18000d61e  jbe     short loc_18000D62C
0x18000d620  lea     eax, [rcx+40000000h]
0x18000d626  cmp     eax, edx
0x18000d628  jbe     short loc_18000D62C
0x18000d62a  xor     edx, edx
0x18000d62c  mov     eax, edx
0x18000d62e  retn
0x18000d62f  shl     cx, 7
0x18000d633  ror     cx, 8
0x18000d637  movzx   eax, cl
0x18000d63a  shr     eax, 3
0x18000d63d  and     eax, 1
0x18000d640  retn
```
