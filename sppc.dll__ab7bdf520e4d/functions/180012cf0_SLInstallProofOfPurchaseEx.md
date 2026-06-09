# SLInstallProofOfPurchaseEx

- ea: `0x180012cf0`
- end: `0x180012eaf`
- name: `SLInstallProofOfPurchaseEx`
- size: `447`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pApplicationId, const SLID *pProductSkuId, PCWSTR pwszPKeyAlgorithm, PCWSTR pwszPKeyString, UINT cbPKeySpecificData, PBYTE pbPKeySpecificData, SLID *pPkeyId)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x180001760`
- `0x180001a90`
- `0x180001ec0`
- `0x1800044dc`
- `0x18000469c`
- `0x180004f44`
- `0x180004f80`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f114`
- `0x18000f144`
- `0x180012cf0`

## pseudocode

```c
HRESULT __stdcall SLInstallProofOfPurchaseEx(
        HSLC hSLC,
        const SLID *pApplicationId,
        const SLID *pProductSkuId,
        PCWSTR pwszPKeyAlgorithm,
        PCWSTR pwszPKeyString,
        UINT cbPKeySpecificData,
        PBYTE pbPKeySpecificData,
        SLID *pPkeyId)
{
  __int64 v11; // rcx
  HRESULT v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v18[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v19; // [rsp+40h] [rbp-18h] BYREF

  v18[0] = (__int64)&v19 + 8;
  v18[1] = (__int64)&v19;
  v19 = 0;
  if ( !hSLC || !pApplicationId || !pwszPKeyAlgorithm || !pwszPKeyString || !pPkeyId )
    goto LABEL_2;
  v12 = sub_18000F144(v18, 1, pwszPKeyAlgorithm);
  sub_180001A90(qword_1800191A8, byte_18001E878);
  if ( v12 >= 0 )
  {
    v13 = sub_18000F144(v18, 2, pwszPKeyString);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_22;
    v13 = sub_180004F80(v18, 3, &cbPKeySpecificData);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_22;
    if ( !cbPKeySpecificData )
    {
      v14 = 4;
      goto LABEL_16;
    }
    if ( pbPKeySpecificData )
    {
      v13 = sub_18000F114(v18, 4, cbPKeySpecificData, pbPKeySpecificData);
      v12 = v13;
      if ( v13 >= 0 )
      {
        v14 = 5;
LABEL_16:
        v13 = sub_180004F44(v18, v14, pApplicationId);
        v12 = v13;
        if ( v13 >= 0 )
        {
          if ( !pProductSkuId || (v13 = sub_180004F44(v18, v14 + 1, pProductSkuId), v12 = v13, v13 >= 0) )
          {
            v15 = sub_1800044DC(v18, (__int64)hSLC, 0x2Bu, 1, 1);
            v12 = v15;
            if ( v15 < 0 )
            {
              sub_180006844((unsigned int)v15);
              sub_180001760(&dword_18001861C, &dword_18001E7EC);
              goto LABEL_24;
            }
            v13 = sub_18000469C(v18, v16, pPkeyId);
            v12 = v13;
            if ( v13 >= 0 )
              goto LABEL_24;
          }
        }
      }
LABEL_22:
      v11 = (unsigned int)v13;
      goto LABEL_23;
    }
LABEL_2:
    v11 = 2147942487LL;
    v12 = -2147024809;
LABEL_23:
    sub_180006844(v11);
    goto LABEL_24;
  }
  sub_180006844((unsigned int)v12);
  sub_180001EC0(qword_180019BA8, &dword_18001E2AC);
LABEL_24:
  sub_18000A8D0((unsigned int)v12);
  sub_180005208(v18);
  return v12;
}

```

## disassembly

```asm
0x180012cf0  push    rbp
0x180012cf2  push    rbx
0x180012cf3  push    rdi
0x180012cf4  push    r12
0x180012cf6  push    r14
0x180012cf8  push    r15
0x180012cfa  mov     rbp, rsp
0x180012cfd  sub     rsp, 58h
0x180012d01  lea     rax, [rbp+var_18+8]
0x180012d05  xorps   xmm0, xmm0
0x180012d08  mov     [rbp+var_28], rax
0x180012d0c  lea     rax, [rbp+var_18]
0x180012d10  mov     [rbp+var_20], rax
0x180012d14  mov     r15, r8
0x180012d17  mov     r14, rdx
0x180012d1a  mov     r12, rcx
0x180012d1d  movdqu  [rbp+var_18], xmm0
0x180012d22  test    rcx, rcx
0x180012d25  jnz     short loc_180012D33
0x180012d27  mov     ecx, 80070057h
0x180012d2c  mov     ebx, ecx
0x180012d2e  jmp     loc_180012E8A
0x180012d33  test    r14, r14
0x180012d36  jz      short loc_180012D27
0x180012d38  test    r9, r9
0x180012d3b  jz      short loc_180012D27
0x180012d3d  mov     rdi, [rbp+pwszPKeyString]
0x180012d41  test    rdi, rdi
0x180012d44  jz      short loc_180012D27
0x180012d46  cmp     [rbp+pPkeyId], 0
0x180012d4b  jz      short loc_180012D27
0x180012d4d  mov     r8, r9
0x180012d50  lea     rcx, [rbp+var_28]
0x180012d54  mov     edx, 1
0x180012d59  call    sub_18000F144
0x180012d5e  lea     rdx, byte_18001E878
0x180012d65  mov     ebx, eax
0x180012d67  lea     rcx, qword_1800191A8
0x180012d6e  call    sub_180001A90
0x180012d73  test    ebx, ebx
0x180012d75  jns     short loc_180012D96
0x180012d77  mov     ecx, ebx
0x180012d79  call    sub_180006844
0x180012d7e  lea     rdx, dword_18001E2AC
0x180012d85  lea     rcx, qword_180019BA8
0x180012d8c  call    sub_180001EC0
0x180012d91  jmp     loc_180012E8F
0x180012d96  mov     r8, rdi
0x180012d99  lea     rcx, [rbp+var_28]
0x180012d9d  mov     edx, 2
0x180012da2  call    sub_18000F144
0x180012da7  mov     ebx, eax
0x180012da9  test    eax, eax
0x180012dab  js      loc_180012E88
0x180012db1  lea     r8, [rbp+cbPKeySpecificData]
0x180012db5  mov     edx, 3
0x180012dba  lea     rcx, [rbp+var_28]
0x180012dbe  call    sub_180004F80
0x180012dc3  mov     ebx, eax
0x180012dc5  test    eax, eax
0x180012dc7  js      loc_180012E88
0x180012dcd  mov     r8d, [rbp+cbPKeySpecificData]
0x180012dd1  test    r8d, r8d
0x180012dd4  jz      short loc_180012E02
0x180012dd6  mov     r9, [rbp+pbPKeySpecificData]
0x180012dda  test    r9, r9
0x180012ddd  jz      loc_180012D27
0x180012de3  mov     edx, 4
0x180012de8  lea     rcx, [rbp+var_28]
0x180012dec  call    sub_18000F114
0x180012df1  mov     ebx, eax
0x180012df3  test    eax, eax
0x180012df5  js      loc_180012E88
0x180012dfb  mov     edi, 5
0x180012e00  jmp     short loc_180012E07
0x180012e02  mov     edi, 4
0x180012e07  mov     r8, r14
0x180012e0a  lea     rcx, [rbp+var_28]
0x180012e0e  mov     edx, edi
0x180012e10  call    sub_180004F44
0x180012e15  mov     ebx, eax
0x180012e17  test    eax, eax
0x180012e19  js      short loc_180012E88
0x180012e1b  test    r15, r15
0x180012e1e  jz      short loc_180012E35
0x180012e20  lea     edx, [rdi+1]
0x180012e23  mov     r8, r15
0x180012e26  lea     rcx, [rbp+var_28]
0x180012e2a  call    sub_180004F44
0x180012e2f  mov     ebx, eax
0x180012e31  test    eax, eax
0x180012e33  js      short loc_180012E88
0x180012e35  mov     r9d, 1
0x180012e3b  mov     [rsp+58h+var_38], 1
0x180012e43  mov     rdx, r12
0x180012e46  lea     rcx, [rbp+var_28]
0x180012e4a  lea     r8d, [r9+2Ah]
0x180012e4e  call    sub_1800044DC
0x180012e53  mov     ebx, eax
0x180012e55  test    eax, eax
0x180012e57  jns     short loc_180012E75
0x180012e59  mov     ecx, eax
0x180012e5b  call    sub_180006844
0x180012e60  lea     rdx, dword_18001E7EC
0x180012e67  lea     rcx, dword_18001861C
0x180012e6e  call    sub_180001760
0x180012e73  jmp     short loc_180012E8F
0x180012e75  mov     r8, [rbp+pPkeyId]
0x180012e79  lea     rcx, [rbp+var_28]
0x180012e7d  call    sub_18000469C
0x180012e82  mov     ebx, eax
0x180012e84  test    eax, eax
0x180012e86  jns     short loc_180012E8F
0x180012e88  mov     ecx, eax
0x180012e8a  call    sub_180006844
0x180012e8f  mov     ecx, ebx
0x180012e91  call    sub_18000A8D0
0x180012e96  lea     rcx, [rbp+var_28]
0x180012e9a  call    sub_180005208
0x180012e9f  mov     eax, ebx
0x180012ea1  add     rsp, 58h
0x180012ea5  pop     r15
0x180012ea7  pop     r14
0x180012ea9  pop     r12
0x180012eab  pop     rdi
0x180012eac  pop     rbx
0x180012ead  pop     rbp
0x180012eae  retn
```
