# u8_ipps_createTabDftDir_32f

- ea: `0x180059a60`
- end: `0x180059aee`
- name: `u8_ipps_createTabDftDir_32f`
- size: `142`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d830`
- `0x18001da40`
- `0x18001e5c0`
- `0x18001e7d0`
- `0x18005b08c`

## callees

- `0x18001f910`
- `0x180059a60`

## pseudocode

```c
__int64 __fastcall u8_ipps_createTabDftDir_32f(unsigned int a1, __int64 *a2, int a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  int v7; // r9d
  __int64 v8; // r10
  __int64 v9; // rdi
  _DWORD *v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax

  v3 = a1;
  result = px_ippsMalloc_8u(16 * a1);
  v7 = 0;
  v8 = result;
  if ( result )
  {
    v9 = 0;
    v10 = (_DWORD *)(result + 8LL * (int)v3);
    if ( (int)v3 > 0 )
    {
      do
      {
        v11 = *a2;
        a2 += a3 / (int)v3;
        *(_QWORD *)(v8 + 8 * v9++) = v11;
      }
      while ( v9 < (int)v3 );
      v12 = v3;
      do
      {
        *v10 = v7;
        v10[(int)v3] = v7;
        v7 += 2;
        ++v10;
        --v12;
      }
      while ( v12 );
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180059a60  mov     [rsp+arg_0], rbx
0x180059a65  mov     [rsp+arg_8], rbp
0x180059a6a  mov     [rsp+arg_10], rsi
0x180059a6f  push    rdi
0x180059a70  sub     rsp, 20h
0x180059a74  mov     ebx, ecx
0x180059a76  shl     ecx, 4
0x180059a79  mov     ebp, r8d
0x180059a7c  mov     rsi, rdx
0x180059a7f  call    px_ippsMalloc_8u
0x180059a84  xor     r9d, r9d
0x180059a87  mov     r10, rax
0x180059a8a  test    rax, rax
0x180059a8d  jz      short loc_180059AD9
0x180059a8f  movsxd  r11, ebx
0x180059a92  mov     rdi, r9
0x180059a95  lea     r8, [rax+r11*8]
0x180059a99  test    ebx, ebx
0x180059a9b  jle     short loc_180059AD6
0x180059a9d  mov     eax, ebp
0x180059a9f  cdq
0x180059aa0  idiv    ebx
0x180059aa2  movsxd  rcx, eax
0x180059aa5  shl     rcx, 3
0x180059aa9  mov     rax, [rsi]
0x180059aac  add     rsi, rcx
0x180059aaf  mov     [r10+rdi*8], rax
0x180059ab3  inc     rdi
0x180059ab6  cmp     rdi, r11
0x180059ab9  jl      short loc_180059AA9
0x180059abb  test    ebx, ebx
0x180059abd  jle     short loc_180059AD6
0x180059abf  mov     rax, rbx
0x180059ac2  mov     [r8], r9d
0x180059ac5  mov     [r8+r11*4], r9d
0x180059ac9  add     r9d, 2
0x180059acd  lea     r8, [r8+4]
0x180059ad1  dec     rax
0x180059ad4  jnz     short loc_180059AC2
0x180059ad6  mov     rax, r10
0x180059ad9  mov     rbx, [rsp+28h+arg_0]
0x180059ade  mov     rbp, [rsp+28h+arg_8]
0x180059ae3  mov     rsi, [rsp+28h+arg_10]
0x180059ae8  add     rsp, 20h
0x180059aec  pop     rdi
0x180059aed  retn
```
