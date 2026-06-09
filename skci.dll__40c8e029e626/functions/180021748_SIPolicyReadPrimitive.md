# SIPolicyReadPrimitive

- ea: `0x180021748`
- end: `0x1800217a7`
- name: `SIPolicyReadPrimitive`
- size: `95`
- prototype: `__int64 __fastcall(__int64 *, size_t, void *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e674`
- `0x18001ef1c`
- `0x18001f230`
- `0x18001f960`
- `0x18001fb08`
- `0x18001fd18`
- `0x18001fd8c`
- `0x18002165c`
- `0x1800217b0`
- `0x1800217d0`
- `0x18002189c`

## callees

- `0x180021748`
- `0x18003392c`

## pseudocode

```c
__int64 __fastcall SIPolicyReadPrimitive(__int64 *a1, size_t a2, void *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rcx

  v3 = a1[2];
  v5 = *a1;
  if ( a1[1] - v5 - v3 < a2 )
    return 3236495363LL;
  memcpy_0(a3, (const void *)(v5 + v3), a2);
  a1[2] = v3 + a2;
  return 0;
}

```

## disassembly

```asm
0x180021748  mov     [rsp+arg_0], rbx
0x18002174d  mov     [rsp+arg_8], rsi
0x180021752  push    rdi
0x180021753  sub     rsp, 20h
0x180021757  mov     rsi, [rcx+10h]
0x18002175b  mov     rbx, rcx
0x18002175e  mov     rcx, [rcx]
0x180021761  mov     r9, r8
0x180021764  mov     rdi, rdx
0x180021767  mov     rax, [rbx+8]
0x18002176b  sub     rax, rcx
0x18002176e  sub     rax, rsi
0x180021771  cmp     rax, rdx
0x180021774  jnb     short loc_18002177D
0x180021776  mov     eax, 0C0E90003h
0x18002177b  jmp     short loc_180021796
0x18002177d  lea     rdx, [rcx+rsi]; Src
0x180021781  mov     r8, rdi; MaxCount
0x180021784  mov     rcx, r9; void *
0x180021787  call    memcpy_0
0x18002178c  lea     rax, [rsi+rdi]
0x180021790  mov     [rbx+10h], rax
0x180021794  xor     eax, eax
0x180021796  mov     rbx, [rsp+28h+arg_0]
0x18002179b  mov     rsi, [rsp+28h+arg_8]
0x1800217a0  add     rsp, 20h
0x1800217a4  pop     rdi
0x1800217a5  retn
```
