# CreateInstance

- ea: `0x180038c50`
- end: `0x180038ce9`
- name: `CreateInstance`
- size: `153`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18003873c`
- `0x1800387a0`
- `0x180038c50`
- `0x1800932cc`

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
      sub_18003873C(v11, v10);
      result = sub_1800387A0(v11, a2, a3, a4);
      _InterlockedDecrement(&dword_1800E1F80);
      return result;
    }
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x180038c50  push    rbx
0x180038c52  push    rbp
0x180038c53  push    rsi
0x180038c54  push    rdi
0x180038c55  push    r14
0x180038c57  push    r15
0x180038c59  sub     rsp, 48h
0x180038c5d  mov     rdi, r9
0x180038c60  mov     rbp, r8
0x180038c63  mov     r14, rdx
0x180038c66  mov     r15, rcx
0x180038c69  test    r9, r9
0x180038c6c  jnz     short loc_180038C75
0x180038c6e  mov     eax, 80004003h
0x180038c73  jmp     short loc_180038CDB
0x180038c75  mov     qword ptr [r9], 0
0x180038c7c  xor     ebx, ebx
0x180038c7e  cmp     ebx, 2
0x180038c81  jge     short loc_180038CD6
0x180038c83  lea     rcx, off_1800E0000
0x180038c8a  movsxd  rsi, ebx
0x180038c8d  shl     rsi, 4
0x180038c91  mov     r8d, 10h; Size
0x180038c97  add     rsi, rcx
0x180038c9a  mov     rdx, r15; Buf2
0x180038c9d  mov     rcx, [rsi]; Buf1
0x180038ca0  call    memcmp
0x180038ca5  test    eax, eax
0x180038ca7  jz      short loc_180038CAD
0x180038ca9  inc     ebx
0x180038cab  jmp     short loc_180038C7E
0x180038cad  mov     rdx, rsi
0x180038cb0  lea     rcx, [rsp+78h+var_58]
0x180038cb5  call    sub_18003873C
0x180038cba  mov     r9, rdi
0x180038cbd  lea     rcx, [rsp+78h+var_58]
0x180038cc2  mov     r8, rbp
0x180038cc5  mov     rdx, r14
0x180038cc8  call    sub_1800387A0
0x180038ccd  lock dec cs:dword_1800E1F80
0x180038cd4  jmp     short loc_180038CDB
0x180038cd6  mov     eax, 80040111h
0x180038cdb  add     rsp, 48h
0x180038cdf  pop     r15
0x180038ce1  pop     r14
0x180038ce3  pop     rdi
0x180038ce4  pop     rsi
0x180038ce5  pop     rbp
0x180038ce6  pop     rbx
0x180038ce7  retn
```
