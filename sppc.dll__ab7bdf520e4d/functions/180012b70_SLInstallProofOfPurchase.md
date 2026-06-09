# SLInstallProofOfPurchase

- ea: `0x180012b70`
- end: `0x180012ce6`
- name: `SLInstallProofOfPurchase`
- size: `374`
- prototype: `HRESULT __stdcall(HSLC hSLC, PCWSTR pwszPKeyAlgorithm, PCWSTR pwszPKeyString, UINT cbPKeySpecificData, PBYTE pbPKeySpecificData, SLID *pPkeyId)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800021b0`
- `0x1800028f0`
- `0x180003030`
- `0x1800044dc`
- `0x18000469c`
- `0x180004f80`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f114`
- `0x18000f144`
- `0x180012b70`

## pseudocode

```c
HRESULT __stdcall SLInstallProofOfPurchase(
        HSLC hSLC,
        PCWSTR pwszPKeyAlgorithm,
        PCWSTR pwszPKeyString,
        UINT cbPKeySpecificData,
        PBYTE pbPKeySpecificData,
        SLID *pPkeyId)
{
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v15[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v16; // [rsp+40h] [rbp-18h] BYREF
  UINT v17; // [rsp+98h] [rbp+40h] BYREF

  v17 = cbPKeySpecificData;
  v15[0] = (__int64)&v16 + 8;
  v15[1] = (__int64)&v16;
  v16 = 0;
  if ( !hSLC )
  {
    v9 = -2147024809;
    sub_180006844(2147942487LL);
    sub_1800028F0(byte_180018A28, &dword_18001EBF4);
    goto LABEL_18;
  }
  if ( !pwszPKeyAlgorithm )
    goto LABEL_4;
  sub_180003030(&dword_18001A364, &dword_18001ED44);
  if ( !pwszPKeyString || !pPkeyId )
    goto LABEL_4;
  v11 = sub_18000F144(v15, 1, pwszPKeyAlgorithm);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_16;
  v12 = sub_18000F144(v15, 2, pwszPKeyString);
  v9 = v12;
  if ( v12 < 0 )
  {
    sub_180006844((unsigned int)v12);
    sub_1800021B0(&dword_180018734, byte_18001E8F8);
    goto LABEL_18;
  }
  v11 = sub_180004F80(v15, 3, &v17);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_16;
  if ( !v17 )
    goto LABEL_14;
  if ( !pbPKeySpecificData )
  {
LABEL_4:
    v10 = 2147942487LL;
    v9 = -2147024809;
LABEL_17:
    sub_180006844(v10);
    goto LABEL_18;
  }
  v11 = sub_18000F114(v15, 4, v17, pbPKeySpecificData);
  v9 = v11;
  if ( v11 < 0 )
  {
LABEL_16:
    v10 = (unsigned int)v11;
    goto LABEL_17;
  }
LABEL_14:
  v11 = sub_1800044DC(v15, (__int64)hSLC, 2u, 1, 1);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_16;
  v11 = sub_18000469C(v15, v13, pPkeyId);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_16;
LABEL_18:
  sub_18000A8D0(v9);
  sub_180005208(v15);
  return v9;
}

```

## disassembly

```asm
0x180012b70  mov     [rsp-20h+arg_18], r9d
0x180012b75  push    rbp
0x180012b76  push    rbx
0x180012b77  push    rsi
0x180012b78  push    r14
0x180012b7a  mov     rbp, rsp
0x180012b7d  sub     rsp, 58h
0x180012b81  lea     rax, [rbp+var_18+8]
0x180012b85  xorps   xmm0, xmm0
0x180012b88  mov     [rbp+var_28], rax
0x180012b8c  lea     rax, [rbp+var_18]
0x180012b90  mov     [rbp+var_20], rax
0x180012b94  mov     rsi, r8
0x180012b97  mov     rbx, rdx
0x180012b9a  mov     r14, rcx
0x180012b9d  movdqu  [rbp+var_18], xmm0
0x180012ba2  test    rcx, rcx
0x180012ba5  jnz     short loc_180012BCB
0x180012ba7  mov     ecx, 80070057h
0x180012bac  mov     ebx, ecx
0x180012bae  call    sub_180006844
0x180012bb3  lea     rdx, dword_18001EBF4
0x180012bba  lea     rcx, byte_180018A28
0x180012bc1  call    sub_1800028F0
0x180012bc6  jmp     loc_180012CCA
0x180012bcb  test    rbx, rbx
0x180012bce  jnz     short loc_180012BDC
0x180012bd0  mov     ecx, 80070057h
0x180012bd5  mov     ebx, ecx
0x180012bd7  jmp     loc_180012CC5
0x180012bdc  lea     rdx, dword_18001ED44
0x180012be3  lea     rcx, dword_18001A364
0x180012bea  call    sub_180003030
0x180012bef  test    rsi, rsi
0x180012bf2  jz      short loc_180012BD0
0x180012bf4  cmp     [rbp+pPkeyId], 0
0x180012bf9  jz      short loc_180012BD0
0x180012bfb  mov     r8, rbx
0x180012bfe  lea     rcx, [rbp+var_28]
0x180012c02  mov     edx, 1
0x180012c07  call    sub_18000F144
0x180012c0c  mov     ebx, eax
0x180012c0e  test    eax, eax
0x180012c10  js      loc_180012CC3
0x180012c16  mov     r8, rsi
0x180012c19  lea     rcx, [rbp+var_28]
0x180012c1d  mov     esi, 2
0x180012c22  mov     edx, esi
0x180012c24  call    sub_18000F144
0x180012c29  mov     ebx, eax
0x180012c2b  test    eax, eax
0x180012c2d  jns     short loc_180012C4B
0x180012c2f  mov     ecx, eax
0x180012c31  call    sub_180006844
0x180012c36  lea     rdx, byte_18001E8F8
0x180012c3d  lea     rcx, dword_180018734
0x180012c44  call    sub_1800021B0
0x180012c49  jmp     short loc_180012CCA
0x180012c4b  lea     r8, [rbp+arg_18]
0x180012c4f  mov     edx, 3
0x180012c54  lea     rcx, [rbp+var_28]
0x180012c58  call    sub_180004F80
0x180012c5d  mov     ebx, eax
0x180012c5f  test    eax, eax
0x180012c61  js      short loc_180012CC3
0x180012c63  mov     r8d, [rbp+arg_18]
0x180012c67  test    r8d, r8d
0x180012c6a  jz      short loc_180012C8D
0x180012c6c  mov     r9, [rbp+pbPKeySpecificData]
0x180012c70  test    r9, r9
0x180012c73  jz      loc_180012BD0
0x180012c79  mov     edx, 4
0x180012c7e  lea     rcx, [rbp+var_28]
0x180012c82  call    sub_18000F114
0x180012c87  mov     ebx, eax
0x180012c89  test    eax, eax
0x180012c8b  js      short loc_180012CC3
0x180012c8d  mov     r9d, 1
0x180012c93  mov     [rsp+58h+var_38], 1
0x180012c9b  mov     r8d, esi
0x180012c9e  lea     rcx, [rbp+var_28]
0x180012ca2  mov     rdx, r14
0x180012ca5  call    sub_1800044DC
0x180012caa  mov     ebx, eax
0x180012cac  test    eax, eax
0x180012cae  js      short loc_180012CC3
0x180012cb0  mov     r8, [rbp+pPkeyId]
0x180012cb4  lea     rcx, [rbp+var_28]
0x180012cb8  call    sub_18000469C
0x180012cbd  mov     ebx, eax
0x180012cbf  test    eax, eax
0x180012cc1  jns     short loc_180012CCA
0x180012cc3  mov     ecx, eax
0x180012cc5  call    sub_180006844
0x180012cca  mov     ecx, ebx
0x180012ccc  call    sub_18000A8D0
0x180012cd1  lea     rcx, [rbp+var_28]
0x180012cd5  call    sub_180005208
0x180012cda  mov     eax, ebx
0x180012cdc  add     rsp, 58h
0x180012ce0  pop     r14
0x180012ce2  pop     rsi
0x180012ce3  pop     rbx
0x180012ce4  pop     rbp
0x180012ce5  retn
```
