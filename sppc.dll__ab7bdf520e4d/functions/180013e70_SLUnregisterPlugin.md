# SLUnregisterPlugin

- ea: `0x180013e70`
- end: `0x180013f4a`
- name: `SLUnregisterPlugin`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1800021b0`
- `0x180002610`
- `0x1800028f0`
- `0x1800044dc`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f144`
- `0x180013e70`

## pseudocode

```c
__int64 __fastcall SLUnregisterPlugin(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v8[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+40h] [rbp-18h] BYREF

  v8[0] = (__int64)&v9 + 8;
  v9 = 0;
  sub_1800021B0(qword_180019E38, &dword_18001E6B4);
  v8[1] = (__int64)&v9;
  if ( !a1 )
  {
    sub_1800028F0(qword_180019F98, qword_18001E858);
LABEL_3:
    v4 = 2147942487LL;
    v5 = -2147024809;
LABEL_9:
    sub_180006844(v4);
    goto LABEL_10;
  }
  if ( !a2 )
  {
    sub_180002610(byte_180019E28, byte_18001E688);
    goto LABEL_3;
  }
  v6 = sub_18000F144(v8, 1, a2);
  v5 = v6;
  if ( v6 < 0 || (v6 = sub_1800044DC(v8, a1, 0x24u, 0, 1), v5 = v6, v6 < 0) )
  {
    v4 = (unsigned int)v6;
    goto LABEL_9;
  }
LABEL_10:
  sub_18000A8D0(v5);
  sub_180005208(v8);
  return v5;
}

```

## disassembly

```asm
0x180013e70  mov     [rsp+arg_0], rbx
0x180013e75  push    rdi
0x180013e76  sub     rsp, 50h
0x180013e7a  mov     rbx, rdx
0x180013e7d  lea     rax, [rsp+58h+var_10]
0x180013e82  mov     rdi, rcx
0x180013e85  mov     [rsp+58h+var_28], rax
0x180013e8a  xorps   xmm0, xmm0
0x180013e8d  lea     rdx, dword_18001E6B4
0x180013e94  lea     rcx, qword_180019E38
0x180013e9b  movdqu  xmmword ptr [rsp+40h], xmm0
0x180013ea1  call    sub_1800021B0
0x180013ea6  lea     rax, [rsp+58h+var_18]
0x180013eab  mov     [rsp+58h+var_20], rax
0x180013eb0  test    rdi, rdi
0x180013eb3  jnz     short loc_180013ED1
0x180013eb5  lea     rdx, qword_18001E858
0x180013ebc  lea     rcx, qword_180019F98
0x180013ec3  call    sub_1800028F0
0x180013ec8  mov     ecx, 80070057h
0x180013ecd  mov     ebx, ecx
0x180013ecf  jmp     short loc_180013F27
0x180013ed1  test    rbx, rbx
0x180013ed4  jnz     short loc_180013EEB
0x180013ed6  lea     rdx, byte_18001E688
0x180013edd  lea     rcx, byte_180019E28
0x180013ee4  call    sub_180002610
0x180013ee9  jmp     short loc_180013EC8
0x180013eeb  mov     r8, rbx
0x180013eee  lea     rcx, [rsp+58h+var_28]
0x180013ef3  mov     edx, 1
0x180013ef8  call    sub_18000F144
0x180013efd  mov     ebx, eax
0x180013eff  test    eax, eax
0x180013f01  js      short loc_180013F25
0x180013f03  xor     r9d, r9d
0x180013f06  mov     [rsp+58h+var_38], 1
0x180013f0e  mov     rdx, rdi
0x180013f11  lea     rcx, [rsp+58h+var_28]
0x180013f16  lea     r8d, [r9+24h]
0x180013f1a  call    sub_1800044DC
0x180013f1f  mov     ebx, eax
0x180013f21  test    eax, eax
0x180013f23  jns     short loc_180013F2C
0x180013f25  mov     ecx, eax
0x180013f27  call    sub_180006844
0x180013f2c  mov     ecx, ebx
0x180013f2e  call    sub_18000A8D0
0x180013f33  lea     rcx, [rsp+58h+var_28]
0x180013f38  call    sub_180005208
0x180013f3d  mov     eax, ebx
0x180013f3f  mov     rbx, [rsp+58h+arg_0]
0x180013f44  add     rsp, 50h
0x180013f48  pop     rdi
0x180013f49  retn
```
