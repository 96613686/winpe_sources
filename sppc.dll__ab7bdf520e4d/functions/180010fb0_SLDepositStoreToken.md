# SLDepositStoreToken

- ea: `0x180010fb0`
- end: `0x1800110a8`
- name: `SLDepositStoreToken`
- size: `248`
- prototype: `HRESULT __stdcall(HSLC hSLC, UINT cbValue, const BYTE *pbValue)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001430`
- `0x180002bf0`
- `0x180003410`
- `0x1800044dc`
- `0x180004f80`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f114`
- `0x180010fb0`

## pseudocode

```c
HRESULT __stdcall SLDepositStoreToken(HSLC hSLC, UINT cbValue, const BYTE *pbValue)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v9[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF
  UINT v11; // [rsp+88h] [rbp+30h] BYREF

  v11 = cbValue;
  v9[0] = (__int64)&v10 + 8;
  v9[1] = (__int64)&v10;
  v10 = 0;
  if ( !hSLC )
  {
    sub_180003410(byte_180019420, &dword_18001EAAC);
LABEL_3:
    v5 = 2147942487LL;
    v6 = -2147024809;
LABEL_11:
    sub_180006844(v5);
    goto LABEL_12;
  }
  if ( !cbValue )
  {
    sub_180001430(byte_1800197E8, qword_18001ED00);
    goto LABEL_3;
  }
  if ( !pbValue )
    goto LABEL_3;
  v7 = sub_180004F80(v9, 1, &v11);
  v6 = v7;
  if ( v7 < 0
    || (v7 = sub_18000F114(v9, 2, v11, pbValue), v6 = v7, v7 < 0)
    || (v7 = sub_1800044DC(v9, (__int64)hSLC, 0x32u, 1, 1), v6 = v7, v7 < 0) )
  {
    v5 = (unsigned int)v7;
    goto LABEL_11;
  }
LABEL_12:
  sub_18000A8D0(v6);
  sub_180002BF0(qword_180019D58, qword_18001E588);
  sub_180005208(v9);
  return v6;
}

```

## disassembly

```asm
0x180010fb0  mov     [rsp-20h+arg_8], edx
0x180010fb4  push    rbp
0x180010fb5  push    rbx
0x180010fb6  push    rsi
0x180010fb7  push    rdi
0x180010fb8  mov     rbp, rsp
0x180010fbb  sub     rsp, 58h
0x180010fbf  lea     rax, [rbp+var_18+8]
0x180010fc3  xorps   xmm0, xmm0
0x180010fc6  mov     [rbp+var_28], rax
0x180010fca  lea     rax, [rbp+var_18]
0x180010fce  mov     [rbp+var_20], rax
0x180010fd2  mov     rdi, r8
0x180010fd5  mov     rsi, rcx
0x180010fd8  movdqu  [rbp+var_18], xmm0
0x180010fdd  test    rcx, rcx
0x180010fe0  jnz     short loc_180010FFE
0x180010fe2  lea     rdx, dword_18001EAAC
0x180010fe9  lea     rcx, byte_180019420
0x180010ff0  call    sub_180003410
0x180010ff5  mov     ecx, 80070057h
0x180010ffa  mov     ebx, ecx
0x180010ffc  jmp     short loc_180011075
0x180010ffe  test    edx, edx
0x180011000  jnz     short loc_180011017
0x180011002  lea     rdx, qword_18001ED00
0x180011009  lea     rcx, byte_1800197E8
0x180011010  call    sub_180001430
0x180011015  jmp     short loc_180010FF5
0x180011017  test    rdi, rdi
0x18001101a  jz      short loc_180010FF5
0x18001101c  lea     r8, [rbp+arg_8]
0x180011020  mov     edx, 1
0x180011025  lea     rcx, [rbp+var_28]
0x180011029  call    sub_180004F80
0x18001102e  mov     ebx, eax
0x180011030  test    eax, eax
0x180011032  js      short loc_180011073
0x180011034  mov     r8d, [rbp+arg_8]
0x180011038  lea     rcx, [rbp+var_28]
0x18001103c  mov     r9, rdi
0x18001103f  mov     edx, 2
0x180011044  call    sub_18000F114
0x180011049  mov     ebx, eax
0x18001104b  test    eax, eax
0x18001104d  js      short loc_180011073
0x18001104f  mov     r9d, 1
0x180011055  mov     [rsp+58h+var_38], 1
0x18001105d  mov     rdx, rsi
0x180011060  lea     rcx, [rbp+var_28]
0x180011064  lea     r8d, [r9+31h]
0x180011068  call    sub_1800044DC
0x18001106d  mov     ebx, eax
0x18001106f  test    eax, eax
0x180011071  jns     short loc_18001107A
0x180011073  mov     ecx, eax
0x180011075  call    sub_180006844
0x18001107a  mov     ecx, ebx
0x18001107c  call    sub_18000A8D0
0x180011081  lea     rdx, qword_18001E588
0x180011088  lea     rcx, qword_180019D58
0x18001108f  call    sub_180002BF0
0x180011094  lea     rcx, [rbp+var_28]
0x180011098  call    sub_180005208
0x18001109d  mov     eax, ebx
0x18001109f  add     rsp, 58h
0x1800110a3  pop     rdi
0x1800110a4  pop     rsi
0x1800110a5  pop     rbx
0x1800110a6  pop     rbp
0x1800110a7  retn
```
