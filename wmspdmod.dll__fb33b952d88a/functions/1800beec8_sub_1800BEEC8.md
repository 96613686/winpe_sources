# sub_1800BEEC8

- ea: `0x1800beec8`
- end: `0x1800bef9f`
- name: `sub_1800BEEC8`
- size: `215`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1800bd86c`
- `0x1800be4a0`
- `0x1800befd8`
- `0x1800bf894`
- `0x1800bfbb8`
- `0x1800bfc74`
- `0x1800c169c`
- `0x1800c1f14`
- `0x1800c2bb0`
- `0x1800c3490`
- `0x1800c4360`

## callees

- `0x1800bd6b8`
- `0x1800beec8`
- `0x1800c4224`
- `0x1800c60f0`

## pseudocode

```c
__int64 __fastcall sub_1800BEEC8(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, void *a6, __int64 a7)
{
  __int64 v9; // rbp
  int v10; // eax
  void *v11; // rsi
  __int64 i; // rdi
  unsigned int v13; // ebx
  LPVOID lpMem[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v16; // [rsp+50h] [rbp-58h]

  lpMem[0] = a6;
  v16 = 0;
  v9 = *a5;
  lpMem[1] = (LPVOID)a5[3];
  v10 = sub_1800C4224(lpMem);
  v11 = lpMem[0];
  if ( v10 )
  {
    for ( i = 0; ; i += v9 )
    {
      v13 = 1;
      if ( i == v9 )
        break;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, void *, __int64))(a5[8] + 56))(
              a1 + 4 * i,
              a2 + 4 * i,
              a3 + 4 * i,
              a5,
              v11,
              a7) )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    v13 = 0;
  }
  if ( (_DWORD)v16 && v11 )
    sub_1800BD6B8(v11);
  return v13;
}

```

## disassembly

```asm
0x1800beec8  mov     r11, rsp
0x1800beecb  mov     [r11+8], rcx
0x1800beecf  push    rbx
0x1800beed0  push    rbp
0x1800beed1  push    rsi
0x1800beed2  push    rdi
0x1800beed3  push    r12
0x1800beed5  push    r13
0x1800beed7  push    r14
0x1800beed9  push    r15
0x1800beedb  sub     rsp, 68h
0x1800beedf  mov     r14, [rsp+0A8h+arg_20]
0x1800beee7  lea     rcx, [r11-68h]
0x1800beeeb  mov     rax, [rsp+0A8h+arg_28]
0x1800beef3  mov     r12, r8
0x1800beef6  mov     [r11-68h], rax
0x1800beefa  mov     r13, rdx
0x1800beefd  mov     qword ptr [r11-58h], 0
0x1800bef05  mov     rax, [r14+18h]
0x1800bef09  mov     rbp, [r14]
0x1800bef0c  mov     [r11-60h], rax
0x1800bef10  call    sub_1800C4224
0x1800bef15  mov     rsi, [rsp+0A8h+lpMem]
0x1800bef1a  test    eax, eax
0x1800bef1c  jz      short loc_1800BEF75
0x1800bef1e  mov     r15, [rsp+0A8h+arg_30]
0x1800bef26  xor     edi, edi
0x1800bef28  mov     ebx, 1
0x1800bef2d  cmp     rdi, rbp
0x1800bef30  jz      short loc_1800BEF77
0x1800bef32  test    ebx, ebx
0x1800bef34  jz      short loc_1800BEF75
0x1800bef36  mov     rax, [r14+40h]
0x1800bef3a  lea     rdx, ds:0[rdi*4]
0x1800bef42  mov     rcx, [rsp+0A8h+arg_0]
0x1800bef4a  lea     r8, [r12+rdi*4]
0x1800bef4e  add     rdx, r13
0x1800bef51  mov     [rsp+0A8h+var_80], r15
0x1800bef56  mov     r9, r14
0x1800bef59  mov     [rsp+0A8h+var_88], rsi
0x1800bef5e  mov     rax, [rax+38h]
0x1800bef62  lea     rcx, [rcx+rdi*4]
0x1800bef66  call    cs:__guard_dispatch_icall_fptr
0x1800bef6c  test    eax, eax
0x1800bef6e  jz      short loc_1800BEF75
0x1800bef70  add     rdi, rbp
0x1800bef73  jmp     short loc_1800BEF28
0x1800bef75  xor     ebx, ebx
0x1800bef77  cmp     dword ptr [rsp+0A8h+var_58], 0
0x1800bef7c  jz      short loc_1800BEF8B
0x1800bef7e  test    rsi, rsi
0x1800bef81  jz      short loc_1800BEF8B
0x1800bef83  mov     rcx, rsi; lpMem
0x1800bef86  call    sub_1800BD6B8
0x1800bef8b  mov     eax, ebx
0x1800bef8d  add     rsp, 68h
0x1800bef91  pop     r15
0x1800bef93  pop     r14
0x1800bef95  pop     r13
0x1800bef97  pop     r12
0x1800bef99  pop     rdi
0x1800bef9a  pop     rsi
0x1800bef9b  pop     rbp
0x1800bef9c  pop     rbx
0x1800bef9d  retn
```
