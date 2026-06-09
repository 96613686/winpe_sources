# CreateInstance

- ea: `0x180082a50`
- end: `0x180082afa`
- name: `CreateInstance`
- size: `170`
- prototype: `__int64 __fastcall(void *Buf2, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800825a0`
- `0x180082a50`
- `0x1800c6084`

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
  result = ((__int64 (__fastcall *)(_QWORD *, __int64, __int64, _QWORD *))sub_1800825A0)(v10, a2, a3, a4);
  _InterlockedDecrement(&dword_18011B848);
  return result;
}

```

## disassembly

```asm
0x180082a50  push    rbx
0x180082a52  push    rbp
0x180082a53  push    rsi
0x180082a54  push    rdi
0x180082a55  push    r14
0x180082a57  push    r15
0x180082a59  sub     rsp, 48h
0x180082a5d  mov     rdi, r9
0x180082a60  mov     rbp, r8
0x180082a63  mov     r14, rdx
0x180082a66  mov     r15, rcx
0x180082a69  test    r9, r9
0x180082a6c  jnz     short loc_180082A75
0x180082a6e  mov     eax, 80004003h
0x180082a73  jmp     short loc_180082AEC
0x180082a75  mov     qword ptr [r9], 0
0x180082a7c  xor     ebx, ebx
0x180082a7e  lea     rcx, off_18010C940
0x180082a85  movsxd  rsi, ebx
0x180082a88  shl     rsi, 4
0x180082a8c  mov     r8d, 10h; Size
0x180082a92  add     rsi, rcx
0x180082a95  mov     rdx, r15; Buf2
0x180082a98  mov     rcx, [rsi]; Buf1
0x180082a9b  call    memcmp
0x180082aa0  test    eax, eax
0x180082aa2  jz      short loc_180082AB2
0x180082aa4  inc     ebx
0x180082aa6  cmp     ebx, 1
0x180082aa9  jl      short loc_180082A7E
0x180082aab  mov     eax, 80040111h
0x180082ab0  jmp     short loc_180082AEC
0x180082ab2  lock inc cs:dword_18011B848
0x180082ab9  lea     rax, off_1800C9878
0x180082ac0  mov     [rsp+78h+var_50], rsi
0x180082ac5  mov     r9, rdi
0x180082ac8  mov     [rsp+78h+var_58], rax
0x180082acd  mov     r8, rbp
0x180082ad0  mov     [rsp+78h+var_48], 0
0x180082ad8  mov     rdx, r14
0x180082adb  lea     rcx, [rsp+78h+var_58]
0x180082ae0  call    sub_1800825A0
0x180082ae5  lock dec cs:dword_18011B848
0x180082aec  add     rsp, 48h
0x180082af0  pop     r15
0x180082af2  pop     r14
0x180082af4  pop     rdi
0x180082af5  pop     rsi
0x180082af6  pop     rbp
0x180082af7  pop     rbx
0x180082af8  retn
```
