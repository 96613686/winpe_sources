# SLpGetTokenActivationGrantInfo

- ea: `0x18000e390`
- end: `0x18000e567`
- name: `SLpGetTokenActivationGrantInfo`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, _QWORD *, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800021b0`
- `0x1800028f0`
- `0x180003030`
- `0x1800044dc`
- `0x180004660`
- `0x180004f44`
- `0x180005208`
- `0x18000532c`
- `0x180006844`
- `0x180008a40`
- `0x18000a8d0`
- `0x18000e390`

## pseudocode

```c
__int64 __fastcall SLpGetTokenActivationGrantInfo(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        _QWORD *a4,
        unsigned int *a5,
        _QWORD *a6)
{
  int v9; // ebx
  __int64 v10; // rcx
  unsigned int *v11; // rdi
  _QWORD *v12; // rsi
  int v13; // eax
  unsigned int v14; // r13d
  unsigned int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v19; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  __int64 v21; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22[2]; // [rsp+48h] [rbp-30h] BYREF
  _OWORD v23[2]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+C0h] [rbp+48h] BYREF

  v22[0] = (__int64)v23 + 8;
  v22[1] = (__int64)v23;
  v24 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v23[0] = 0;
  if ( a1 && a2 )
  {
    if ( !a3 )
    {
      v9 = -2147024809;
      sub_1800021B0(qword_180018838, qword_18001EA60);
      goto LABEL_3;
    }
    if ( a4 )
    {
      v11 = a5;
      if ( a5 )
      {
        v12 = a6;
        if ( a6 )
        {
          v13 = sub_180004F44(v22, 1, a2);
          v9 = v13;
          if ( v13 < 0 )
          {
LABEL_12:
            v10 = (unsigned int)v13;
            goto LABEL_4;
          }
          v9 = sub_1800044DC(v22, a1, 0x2Cu, 1, 1);
          sub_1800028F0(byte_1800194E8, qword_18001EB50);
          if ( v9 >= 0 )
          {
            v13 = sub_180004660(v22, 1, &v24);
            v9 = v13;
            if ( v13 < 0 )
              goto LABEL_12;
            v14 = v24;
            v9 = sub_180008A40(v22, 2, v24, &v21);
            sub_180003030(&dword_180019EB4, byte_18001E778);
            if ( v9 >= 0 )
            {
              v13 = sub_180004660(v22, 3, &v19);
              v9 = v13;
              if ( v13 >= 0 )
              {
                v15 = v19;
                v13 = sub_180008A40(v22, 4, v19, &v20);
                v9 = v13;
                if ( v13 >= 0 )
                {
                  v16 = v21;
                  *a3 = v14;
                  *a4 = v16;
                  v17 = v20;
                  *v11 = v15;
                  *v12 = v17;
                  v21 = 0;
                  v20 = 0;
                  goto LABEL_20;
                }
              }
              goto LABEL_12;
            }
          }
          v10 = (unsigned int)v9;
          goto LABEL_4;
        }
      }
    }
  }
  v9 = -2147024809;
LABEL_3:
  v10 = 2147942487LL;
LABEL_4:
  sub_180006844(v10);
LABEL_20:
  sub_18000A8D0((unsigned int)v9);
  sub_18000532C(&v20);
  sub_18000532C(&v21);
  sub_180005208(v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e390  push    rbp
0x18000e392  push    rbx
0x18000e393  push    rsi
0x18000e394  push    rdi
0x18000e395  push    r12
0x18000e397  push    r13
0x18000e399  push    r14
0x18000e39b  push    r15
0x18000e39d  mov     rbp, rsp
0x18000e3a0  sub     rsp, 78h
0x18000e3a4  xor     r13d, r13d
0x18000e3a7  lea     rax, [rbp+var_20+8]
0x18000e3ab  mov     [rbp+var_30], rax
0x18000e3af  lea     rax, [rbp+var_20]
0x18000e3b3  mov     [rbp+var_28], rax
0x18000e3b7  xorps   xmm0, xmm0
0x18000e3ba  mov     [rbp+arg_0], r13d
0x18000e3be  mov     r15, r9
0x18000e3c1  mov     [rbp+var_38], r13
0x18000e3c5  mov     r12, r8
0x18000e3c8  mov     [rbp+var_48], r13d
0x18000e3cc  mov     r14, rcx
0x18000e3cf  mov     [rbp+var_40], r13
0x18000e3d3  movdqu  [rbp+var_20], xmm0
0x18000e3d8  test    rcx, rcx
0x18000e3db  jnz     short loc_18000E3F0
0x18000e3dd  mov     edi, 80070057h
0x18000e3e2  mov     ebx, edi
0x18000e3e4  mov     ecx, edi
0x18000e3e6  call    sub_180006844
0x18000e3eb  jmp     loc_18000E532
0x18000e3f0  test    rdx, rdx
0x18000e3f3  jz      short loc_18000E3DD
0x18000e3f5  test    r12, r12
0x18000e3f8  jnz     short loc_18000E416
0x18000e3fa  mov     edi, 80070057h
0x18000e3ff  lea     rdx, qword_18001EA60
0x18000e406  lea     rcx, qword_180018838
0x18000e40d  mov     ebx, edi
0x18000e40f  call    sub_1800021B0
0x18000e414  jmp     short loc_18000E3E4
0x18000e416  test    r15, r15
0x18000e419  jz      short loc_18000E3DD
0x18000e41b  mov     rdi, [rbp+arg_20]
0x18000e41f  test    rdi, rdi
0x18000e422  jz      short loc_18000E3DD
0x18000e424  mov     rsi, [rbp+arg_28]
0x18000e428  test    rsi, rsi
0x18000e42b  jz      short loc_18000E3DD
0x18000e42d  mov     r8, rdx
0x18000e430  lea     rcx, [rbp+var_30]
0x18000e434  mov     edx, 1
0x18000e439  call    sub_180004F44
0x18000e43e  mov     ebx, eax
0x18000e440  test    eax, eax
0x18000e442  jns     short loc_18000E448
0x18000e444  mov     ecx, eax
0x18000e446  jmp     short loc_18000E3E6
0x18000e448  mov     eax, 1
0x18000e44d  lea     rcx, [rbp+var_30]
0x18000e451  mov     r9d, eax
0x18000e454  mov     [rsp+78h+var_58], eax
0x18000e458  mov     rdx, r14
0x18000e45b  lea     r8d, [rax+2Bh]
0x18000e45f  call    sub_1800044DC
0x18000e464  lea     rdx, qword_18001EB50
0x18000e46b  mov     ebx, eax
0x18000e46d  lea     rcx, byte_1800194E8
0x18000e474  call    sub_1800028F0
0x18000e479  test    ebx, ebx
0x18000e47b  jns     short loc_18000E484
0x18000e47d  mov     ecx, ebx
0x18000e47f  jmp     loc_18000E3E6
0x18000e484  lea     r8, [rbp+arg_0]
0x18000e488  mov     edx, 1
0x18000e48d  lea     rcx, [rbp+var_30]
0x18000e491  call    sub_180004660
0x18000e496  mov     ebx, eax
0x18000e498  test    eax, eax
0x18000e49a  js      short loc_18000E444
0x18000e49c  mov     r13d, [rbp+arg_0]
0x18000e4a0  lea     r9, [rbp+var_38]
0x18000e4a4  mov     r8d, r13d
0x18000e4a7  lea     rcx, [rbp+var_30]
0x18000e4ab  mov     edx, 2
0x18000e4b0  call    sub_180008A40
0x18000e4b5  lea     rdx, byte_18001E778
0x18000e4bc  mov     ebx, eax
0x18000e4be  lea     rcx, dword_180019EB4
0x18000e4c5  call    sub_180003030
0x18000e4ca  test    ebx, ebx
0x18000e4cc  js      short loc_18000E47D
0x18000e4ce  lea     r8, [rbp+var_48]
0x18000e4d2  mov     edx, 3
0x18000e4d7  lea     rcx, [rbp+var_30]
0x18000e4db  call    sub_180004660
0x18000e4e0  mov     ebx, eax
0x18000e4e2  test    eax, eax
0x18000e4e4  js      loc_18000E444
0x18000e4ea  mov     r14d, [rbp+var_48]
0x18000e4ee  lea     r9, [rbp+var_40]
0x18000e4f2  mov     r8d, r14d
0x18000e4f5  lea     rcx, [rbp+var_30]
0x18000e4f9  mov     edx, 4
0x18000e4fe  call    sub_180008A40
0x18000e503  mov     ebx, eax
0x18000e505  test    eax, eax
0x18000e507  js      loc_18000E444
0x18000e50d  mov     rax, [rbp+var_38]
0x18000e511  mov     [r12], r13d
0x18000e515  mov     [r15], rax
0x18000e518  mov     rax, [rbp+var_40]
0x18000e51c  mov     [rdi], r14d
0x18000e51f  mov     [rsi], rax
0x18000e522  mov     [rbp+var_38], 0
0x18000e52a  mov     [rbp+var_40], 0
0x18000e532  mov     ecx, ebx
0x18000e534  call    sub_18000A8D0
0x18000e539  lea     rcx, [rbp+var_40]
0x18000e53d  call    sub_18000532C
0x18000e542  lea     rcx, [rbp+var_38]
0x18000e546  call    sub_18000532C
0x18000e54b  lea     rcx, [rbp+var_30]
0x18000e54f  call    sub_180005208
0x18000e554  mov     eax, ebx
0x18000e556  add     rsp, 78h
0x18000e55a  pop     r15
0x18000e55c  pop     r14
0x18000e55e  pop     r13
0x18000e560  pop     r12
0x18000e562  pop     rdi
0x18000e563  pop     rsi
0x18000e564  pop     rbx
0x18000e565  pop     rbp
0x18000e566  retn
```
