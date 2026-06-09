# CreateInstance

- ea: `0x180038c10`
- end: `0x180038ca9`
- name: `CreateInstance`
- size: `153`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800386fc`
- `0x180038760`
- `0x180038c10`
- `0x18009328c`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  int i; // ebx
  const void **v10; // rsi
  _BYTE v11[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v10 = (const void **)((char *)&off_1800E0000 + 16 * i);
    if ( !memcmp(*v10, Buf2, 0x10u) )
    {
      sub_1800386FC(v11, v10);
      result = sub_180038760(v11, a2, a3, a4);
      _InterlockedDecrement(&dword_1800E1F80);
      return result;
    }
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x180038c10  push    rbx
0x180038c12  push    rbp
0x180038c13  push    rsi
0x180038c14  push    rdi
0x180038c15  push    r14
0x180038c17  push    r15
0x180038c19  sub     rsp, 48h
0x180038c1d  mov     rdi, r9
0x180038c20  mov     rbp, r8
0x180038c23  mov     r14, rdx
0x180038c26  mov     r15, rcx
0x180038c29  test    r9, r9
0x180038c2c  jnz     short loc_180038C35
0x180038c2e  mov     eax, 80004003h
0x180038c33  jmp     short loc_180038C9B
0x180038c35  mov     qword ptr [r9], 0
0x180038c3c  xor     ebx, ebx
0x180038c3e  cmp     ebx, 2
0x180038c41  jge     short loc_180038C96
0x180038c43  lea     rcx, off_1800E0000
0x180038c4a  movsxd  rsi, ebx
0x180038c4d  shl     rsi, 4
0x180038c51  mov     r8d, 10h; Size
0x180038c57  add     rsi, rcx
0x180038c5a  mov     rdx, r15; Buf2
0x180038c5d  mov     rcx, [rsi]; Buf1
0x180038c60  call    memcmp
0x180038c65  test    eax, eax
0x180038c67  jz      short loc_180038C6D
0x180038c69  inc     ebx
0x180038c6b  jmp     short loc_180038C3E
0x180038c6d  mov     rdx, rsi
0x180038c70  lea     rcx, [rsp+78h+var_58]
0x180038c75  call    sub_1800386FC
0x180038c7a  mov     r9, rdi
0x180038c7d  lea     rcx, [rsp+78h+var_58]
0x180038c82  mov     r8, rbp
0x180038c85  mov     rdx, r14
0x180038c88  call    sub_180038760
0x180038c8d  lock dec cs:dword_1800E1F80
0x180038c94  jmp     short loc_180038C9B
0x180038c96  mov     eax, 80040111h
0x180038c9b  add     rsp, 48h
0x180038c9f  pop     r15
0x180038ca1  pop     r14
0x180038ca3  pop     rdi
0x180038ca4  pop     rsi
0x180038ca5  pop     rbp
0x180038ca6  pop     rbx
0x180038ca7  retn
```
