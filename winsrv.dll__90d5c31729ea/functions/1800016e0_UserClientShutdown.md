# UserClientShutdown

- ea: `0x1800016e0`
- end: `0x18000172d`
- name: `UserClientShutdown`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800016e0`

## pseudocode

```c
__int64 __fastcall UserClientShutdown(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned __int64 v3; // r9

  v3 = a3;
  if ( a3 )
  {
    if ( ((unsigned __int8)a2 & 4) != 0 )
    {
      *a2 = 1;
      v3 = a3 - 1LL;
      if ( a3 == 1 )
        return 0;
      ++a2;
    }
    memset64(a2, 0x100000001uLL, v3 >> 1);
    if ( (v3 & 1) != 0 )
      a2[v3 - 1] = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp+arg_0], rdi
0x1800016e5  mov     r9d, r8d
0x1800016e8  test    r8d, r8d
0x1800016eb  jz      short loc_180001724
0x1800016ed  mov     r8d, 1
0x1800016f3  test    dl, 4
0x1800016f6  jz      short loc_180001704
0x1800016f8  mov     [rdx], r8d
0x1800016fb  sub     r9, r8
0x1800016fe  jz      short loc_180001724
0x180001700  add     rdx, 4
0x180001704  mov     rcx, r9
0x180001707  mov     rax, 100000001h
0x180001711  shr     rcx, 1
0x180001714  mov     rdi, rdx
0x180001717  rep stosq
0x18000171a  test    r8b, r9b
0x18000171d  jz      short loc_180001724
0x18000171f  mov     [rdx+r9*4-4], r8d
0x180001724  mov     rdi, [rsp+arg_0]
0x180001729  xor     eax, eax
0x18000172b  retn
```
