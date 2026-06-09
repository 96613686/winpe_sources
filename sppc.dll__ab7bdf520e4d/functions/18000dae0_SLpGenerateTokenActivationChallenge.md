# SLpGenerateTokenActivationChallenge

- ea: `0x18000dae0`
- end: `0x18000dc5f`
- name: `SLpGenerateTokenActivationChallenge`
- size: `383`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180001430`
- `0x180002610`
- `0x180003410`
- `0x1800044dc`
- `0x180004660`
- `0x180004f44`
- `0x180005208`
- `0x18000532c`
- `0x180006844`
- `0x180008a40`
- `0x18000a8d0`
- `0x18000dae0`

## pseudocode

```c
__int64 __fastcall SLpGenerateTokenActivationChallenge(__int64 a1, __int64 a2, unsigned int *a3, _QWORD *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v16; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+20h] BYREF

  v15[0] = (__int64)&v16 + 8;
  v15[1] = (__int64)&v16;
  v16 = 0;
  sub_180002610(byte_180018778, byte_18001E948);
  v17 = 0;
  v14 = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    v9 = -2147024809;
    sub_180006844(2147942487LL);
    sub_180003410(byte_180019EF8, &dword_18001E7FC);
    goto LABEL_15;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    sub_180006844(2147942487LL);
    sub_180001430(byte_18001A4D0, byte_18001E410);
    goto LABEL_15;
  }
  if ( a4 )
  {
    v10 = sub_180004F44(v15, 1, a2);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v10 = sub_1800044DC(v15, a1, 0x2Du, 1, 1);
      v9 = v10;
      if ( v10 >= 0 )
      {
        v10 = sub_180004660(v15, 1, &v17);
        v9 = v10;
        if ( v10 >= 0 )
        {
          v11 = v17;
          v10 = sub_180008A40(v15, 2, v17, &v14);
          v9 = v10;
          if ( v10 >= 0 )
          {
            v12 = v14;
            *a3 = v11;
            *a4 = v12;
            v14 = 0;
            goto LABEL_15;
          }
        }
      }
    }
    v8 = (unsigned int)v10;
  }
  else
  {
LABEL_2:
    v8 = 2147942487LL;
    v9 = -2147024809;
  }
  sub_180006844(v8);
LABEL_15:
  sub_18000A8D0(v9);
  sub_18000532C(&v14);
  sub_180005208(v15);
  return v9;
}

```

## disassembly

```asm
0x18000dae0  mov     [rsp-18h+arg_8], rbx
0x18000dae5  mov     [rsp-18h+arg_10], rsi
0x18000daea  push    rbp
0x18000daeb  push    rdi
0x18000daec  push    r14
0x18000daee  mov     rbp, rsp
0x18000daf1  sub     rsp, 60h
0x18000daf5  lea     rax, [rbp+var_18+8]
0x18000daf9  mov     rbx, rdx
0x18000dafc  mov     [rbp+var_28], rax
0x18000db00  lea     rdx, byte_18001E948
0x18000db07  lea     rax, [rbp+var_18]
0x18000db0b  mov     rdi, rcx
0x18000db0e  xorps   xmm0, xmm0
0x18000db11  mov     [rbp+var_20], rax
0x18000db15  lea     rcx, byte_180018778
0x18000db1c  mov     rsi, r9
0x18000db1f  mov     r14, r8
0x18000db22  movdqu  [rbp+var_18], xmm0
0x18000db27  call    sub_180002610
0x18000db2c  mov     [rbp+arg_0], 0
0x18000db33  mov     [rbp+var_30], 0
0x18000db3b  test    rdi, rdi
0x18000db3e  jnz     short loc_18000DB51
0x18000db40  mov     ecx, 80070057h
0x18000db45  mov     ebx, ecx
0x18000db47  call    sub_180006844
0x18000db4c  jmp     loc_18000DC2F
0x18000db51  test    rbx, rbx
0x18000db54  jnz     short loc_18000DB7A
0x18000db56  mov     ecx, 80070057h
0x18000db5b  mov     ebx, ecx
0x18000db5d  call    sub_180006844
0x18000db62  lea     rdx, dword_18001E7FC
0x18000db69  lea     rcx, byte_180019EF8
0x18000db70  call    sub_180003410
0x18000db75  jmp     loc_18000DC2F
0x18000db7a  test    r14, r14
0x18000db7d  jnz     short loc_18000DBA3
0x18000db7f  mov     ecx, 80070057h
0x18000db84  mov     ebx, ecx
0x18000db86  call    sub_180006844
0x18000db8b  lea     rdx, byte_18001E410
0x18000db92  lea     rcx, byte_18001A4D0
0x18000db99  call    sub_180001430
0x18000db9e  jmp     loc_18000DC2F
0x18000dba3  test    rsi, rsi
0x18000dba6  jz      short loc_18000DB40
0x18000dba8  mov     r8, rbx
0x18000dbab  lea     rcx, [rbp+var_28]
0x18000dbaf  mov     edx, 1
0x18000dbb4  call    sub_180004F44
0x18000dbb9  mov     ebx, eax
0x18000dbbb  test    eax, eax
0x18000dbbd  jns     short loc_18000DBC3
0x18000dbbf  mov     ecx, eax
0x18000dbc1  jmp     short loc_18000DB47
0x18000dbc3  mov     r9d, 1
0x18000dbc9  mov     [rsp+60h+var_40], 1
0x18000dbd1  mov     rdx, rdi
0x18000dbd4  lea     rcx, [rbp+var_28]
0x18000dbd8  lea     r8d, [r9+2Ch]
0x18000dbdc  call    sub_1800044DC
0x18000dbe1  mov     ebx, eax
0x18000dbe3  test    eax, eax
0x18000dbe5  js      short loc_18000DBBF
0x18000dbe7  lea     r8, [rbp+arg_0]
0x18000dbeb  mov     edx, 1
0x18000dbf0  lea     rcx, [rbp+var_28]
0x18000dbf4  call    sub_180004660
0x18000dbf9  mov     ebx, eax
0x18000dbfb  test    eax, eax
0x18000dbfd  js      short loc_18000DBBF
0x18000dbff  mov     edi, [rbp+arg_0]
0x18000dc02  lea     r9, [rbp+var_30]
0x18000dc06  mov     r8d, edi
0x18000dc09  lea     rcx, [rbp+var_28]
0x18000dc0d  mov     edx, 2
0x18000dc12  call    sub_180008A40
0x18000dc17  mov     ebx, eax
0x18000dc19  test    eax, eax
0x18000dc1b  js      short loc_18000DBBF
0x18000dc1d  mov     rax, [rbp+var_30]
0x18000dc21  mov     [r14], edi
0x18000dc24  mov     [rsi], rax
0x18000dc27  mov     [rbp+var_30], 0
0x18000dc2f  mov     ecx, ebx
0x18000dc31  call    sub_18000A8D0
0x18000dc36  lea     rcx, [rbp+var_30]
0x18000dc3a  call    sub_18000532C
0x18000dc3f  lea     rcx, [rbp+var_28]
0x18000dc43  call    sub_180005208
0x18000dc48  lea     r11, [rsp+60h+var_s0]
0x18000dc4d  mov     eax, ebx
0x18000dc4f  mov     rbx, [r11+28h]
0x18000dc53  mov     rsi, [r11+30h]
0x18000dc57  mov     rsp, r11
0x18000dc5a  pop     r14
0x18000dc5c  pop     rdi
0x18000dc5d  pop     rbp
0x18000dc5e  retn
```
