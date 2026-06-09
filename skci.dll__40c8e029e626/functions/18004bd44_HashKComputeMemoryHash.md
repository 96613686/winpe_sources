# HashKComputeMemoryHash

- ea: `0x18004bd44`
- end: `0x18004be05`
- name: `HashKComputeMemoryHash`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800468f8`

## callees

- `0x180033950`
- `0x180033980`
- `0x18004bd44`
- `0x18004c0c8`
- `0x18004c134`
- `0x18004c1ac`

## pseudocode

```c
__int64 __fastcall HashKComputeMemoryHash(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  unsigned __int64 v8; // rbx
  unsigned int v9; // edi
  int v10; // [rsp+20h] [rbp-118h] BYREF
  _BYTE v11[236]; // [rsp+24h] [rbp-114h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v10 = a1;
  result = HashpInitHash(&v10, 0);
  if ( (int)result >= 0 )
  {
    v8 = 4096;
    do
    {
      v9 = -1;
      if ( v8 <= 0xFFFFFFFF )
        v9 = v8;
      HashpHashBytes(&v10, a2, v9);
      a2 += v9;
      v8 -= v9;
    }
    while ( v8 );
    HashpFinalizeHash(&v10, a5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004bd44  mov     [rsp+arg_10], rbx
0x18004bd49  mov     [rsp+arg_18], rbp
0x18004bd4e  push    rsi
0x18004bd4f  push    rdi
0x18004bd50  push    r14
0x18004bd52  sub     rsp, 120h
0x18004bd59  mov     rax, cs:__security_cookie
0x18004bd60  xor     rax, rsp
0x18004bd63  mov     [rsp+138h+var_28], rax
0x18004bd6b  mov     rbp, [rsp+138h+arg_20]
0x18004bd73  mov     rsi, rdx
0x18004bd76  mov     ebx, ecx
0x18004bd78  xor     edx, edx; Val
0x18004bd7a  lea     rcx, [rsp+138h+var_114]; void *
0x18004bd7f  mov     r8d, 0ECh; Size
0x18004bd85  call    memset_0
0x18004bd8a  xor     edx, edx
0x18004bd8c  mov     [rsp+138h+var_118], ebx
0x18004bd90  lea     rcx, [rsp+138h+var_118]
0x18004bd95  call    HashpInitHash
0x18004bd9a  test    eax, eax
0x18004bd9c  js      short loc_18004BDDC
0x18004bd9e  mov     ebx, 1000h
0x18004bda3  mov     r14d, 0FFFFFFFFh
0x18004bda9  mov     edi, r14d
0x18004bdac  cmp     rbx, r14
0x18004bdaf  ja      short loc_18004BDB3
0x18004bdb1  mov     edi, ebx
0x18004bdb3  mov     r8d, edi
0x18004bdb6  lea     rcx, [rsp+138h+var_118]
0x18004bdbb  mov     rdx, rsi
0x18004bdbe  call    HashpHashBytes
0x18004bdc3  mov     eax, edi
0x18004bdc5  add     rsi, rax
0x18004bdc8  sub     rbx, rax
0x18004bdcb  jnz     short loc_18004BDA9
0x18004bdcd  mov     rdx, rbp
0x18004bdd0  lea     rcx, [rsp+138h+var_118]
0x18004bdd5  call    HashpFinalizeHash
0x18004bdda  xor     eax, eax
0x18004bddc  mov     rcx, [rsp+138h+var_28]
0x18004bde4  xor     rcx, rsp; StackCookie
0x18004bde7  call    __security_check_cookie
0x18004bdec  lea     r11, [rsp+138h+var_18]
0x18004bdf4  mov     rbx, [r11+30h]
0x18004bdf8  mov     rbp, [r11+38h]
0x18004bdfc  mov     rsp, r11
0x18004bdff  pop     r14
0x18004be01  pop     rdi
0x18004be02  pop     rsi
0x18004be03  retn
```
