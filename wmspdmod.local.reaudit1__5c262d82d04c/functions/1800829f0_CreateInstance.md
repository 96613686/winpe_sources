# CreateInstance

- ea: `0x1800829f0`
- end: `0x180082a9a`
- name: `CreateInstance`
- size: `170`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180082540`
- `0x1800829f0`
- `0x1800c6024`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  int v9; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-58h] BYREF
  int v11; // [rsp+30h] [rbp-48h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v9 = 0;
  while ( memcmp(*((const void **)&off_18010C940 + 2 * v9), Buf2, 0x10u) )
  {
    if ( ++v9 >= 1 )
      return 2147746065LL;
  }
  _InterlockedIncrement(&dword_18011B848);
  v10[1] = (char *)&off_18010C940 + 16 * v9;
  v10[0] = off_1800C9878;
  v11 = 0;
  result = ((__int64 (__fastcall *)(_QWORD *, __int64, __int64, _QWORD *))sub_180082540)(v10, a2, a3, a4);
  _InterlockedDecrement(&dword_18011B848);
  return result;
}

```

## disassembly

```asm
0x1800829f0  push    rbx
0x1800829f2  push    rbp
0x1800829f3  push    rsi
0x1800829f4  push    rdi
0x1800829f5  push    r14
0x1800829f7  push    r15
0x1800829f9  sub     rsp, 48h
0x1800829fd  mov     rdi, r9
0x180082a00  mov     rbp, r8
0x180082a03  mov     r14, rdx
0x180082a06  mov     r15, rcx
0x180082a09  test    r9, r9
0x180082a0c  jnz     short loc_180082A15
0x180082a0e  mov     eax, 80004003h
0x180082a13  jmp     short loc_180082A8C
0x180082a15  mov     qword ptr [r9], 0
0x180082a1c  xor     ebx, ebx
0x180082a1e  lea     rcx, off_18010C940
0x180082a25  movsxd  rsi, ebx
0x180082a28  shl     rsi, 4
0x180082a2c  mov     r8d, 10h; Size
0x180082a32  add     rsi, rcx
0x180082a35  mov     rdx, r15; Buf2
0x180082a38  mov     rcx, [rsi]; Buf1
0x180082a3b  call    memcmp
0x180082a40  test    eax, eax
0x180082a42  jz      short loc_180082A52
0x180082a44  inc     ebx
0x180082a46  cmp     ebx, 1
0x180082a49  jl      short loc_180082A1E
0x180082a4b  mov     eax, 80040111h
0x180082a50  jmp     short loc_180082A8C
0x180082a52  lock inc cs:dword_18011B848
0x180082a59  lea     rax, off_1800C9878
0x180082a60  mov     [rsp+78h+var_50], rsi
0x180082a65  mov     r9, rdi
0x180082a68  mov     [rsp+78h+var_58], rax
0x180082a6d  mov     r8, rbp
0x180082a70  mov     [rsp+78h+var_48], 0
0x180082a78  mov     rdx, r14
0x180082a7b  lea     rcx, [rsp+78h+var_58]
0x180082a80  call    sub_180082540
0x180082a85  lock dec cs:dword_18011B848
0x180082a8c  add     rsp, 48h
0x180082a90  pop     r15
0x180082a92  pop     r14
0x180082a94  pop     rdi
0x180082a95  pop     rsi
0x180082a96  pop     rbp
0x180082a97  pop     rbx
0x180082a98  retn
```
