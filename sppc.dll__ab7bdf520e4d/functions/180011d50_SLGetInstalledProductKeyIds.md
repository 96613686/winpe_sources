# SLGetInstalledProductKeyIds

- ea: `0x180011d50`
- end: `0x180011ee9`
- name: `SLGetInstalledProductKeyIds`
- size: `409`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, UINT *pnProductKeyIds, SLID **ppProductKeyIds)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180001430`
- `0x1800021b0`
- `0x180002610`
- `0x1800044dc`
- `0x180004660`
- `0x180004f44`
- `0x180005208`
- `0x18000532c`
- `0x180006844`
- `0x180008a40`
- `0x18000a8d0`
- `0x180011d50`

## pseudocode

```c
HRESULT __stdcall SLGetInstalledProductKeyIds(
        HSLC hSLC,
        const SLID *pProductSkuId,
        UINT *pnProductKeyIds,
        SLID **ppProductKeyIds)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  UINT v10; // esi
  unsigned int v11; // edi
  SLID *v12; // rax
  SLID *v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15[2]; // [rsp+38h] [rbp-30h] BYREF
  _OWORD v16[2]; // [rsp+48h] [rbp-20h] BYREF
  UINT v17; // [rsp+A0h] [rbp+38h] BYREF

  v17 = 0;
  v15[0] = (__int64)v16 + 8;
  v15[1] = (__int64)v16;
  v14 = 0;
  v16[0] = 0;
  if ( hSLC )
  {
    if ( !pProductSkuId )
    {
      v7 = -2147024809;
      sub_180002610(qword_180018D88, qword_18001E240);
      goto LABEL_3;
    }
    if ( !pnProductKeyIds )
    {
      v7 = -2147024809;
      sub_1800021B0(qword_180019B28, qword_18001E388);
      goto LABEL_3;
    }
    if ( ppProductKeyIds )
    {
      v9 = sub_180004F44(v15, 1, pProductSkuId);
      v7 = v9;
      if ( v9 < 0
        || (v9 = sub_1800044DC(v15, (__int64)hSLC, 0x21u, 1, 1), v7 = v9, v9 < 0)
        || (v9 = sub_180004660(v15, 1, &v17), v7 = v9, v9 < 0) )
      {
LABEL_11:
        v8 = (unsigned int)v9;
        goto LABEL_4;
      }
      v10 = v17;
      if ( v17 )
      {
        v11 = 16 * v17;
        if ( 16 * v17 / v17 != 16 )
        {
          v11 = 0;
          v7 = -2147024362;
          sub_180001430(&dword_18001877C, &dword_18001E94C);
          sub_180006844(2147942934LL);
          goto LABEL_17;
        }
      }
      else
      {
        v11 = 0;
      }
      v7 = 0;
LABEL_17:
      sub_18000A8D0(v7);
      if ( (v7 & 0x80000000) != 0 )
      {
        v8 = v7;
        goto LABEL_4;
      }
      v9 = sub_180008A40(v15, 2, v11, &v14);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v12 = v14;
        *pnProductKeyIds = v10;
        *ppProductKeyIds = v12;
        v14 = 0;
        goto LABEL_23;
      }
      goto LABEL_11;
    }
  }
  v7 = -2147024809;
LABEL_3:
  v8 = 2147942487LL;
LABEL_4:
  sub_180006844(v8);
LABEL_23:
  sub_18000A8D0(v7);
  sub_180005208(v15);
  sub_18000532C(&v14);
  return v7;
}

```

## disassembly

```asm
0x180011d50  push    rbp
0x180011d52  push    rbx
0x180011d53  push    rsi
0x180011d54  push    rdi
0x180011d55  push    r14
0x180011d57  push    r15
0x180011d59  mov     rbp, rsp
0x180011d5c  sub     rsp, 68h
0x180011d60  mov     [rbp+arg_0], 0
0x180011d67  lea     rax, [rbp+var_20+8]
0x180011d6b  mov     [rbp+var_30], rax
0x180011d6f  lea     rax, [rbp+var_20]
0x180011d73  mov     [rbp+var_28], rax
0x180011d77  xorps   xmm0, xmm0
0x180011d7a  mov     [rbp+var_38], 0
0x180011d82  mov     r14, r9
0x180011d85  mov     r15, r8
0x180011d88  mov     rdi, rcx
0x180011d8b  movdqu  [rbp+var_20], xmm0
0x180011d90  test    rcx, rcx
0x180011d93  jnz     short loc_180011DA8
0x180011d95  mov     edi, 80070057h
0x180011d9a  mov     ebx, edi
0x180011d9c  mov     ecx, edi
0x180011d9e  call    sub_180006844
0x180011da3  jmp     loc_180011EC1
0x180011da8  test    rdx, rdx
0x180011dab  jnz     short loc_180011DC9
0x180011dad  mov     edi, 80070057h
0x180011db2  lea     rdx, qword_18001E240
0x180011db9  lea     rcx, qword_180018D88
0x180011dc0  mov     ebx, edi
0x180011dc2  call    sub_180002610
0x180011dc7  jmp     short loc_180011D9C
0x180011dc9  test    r15, r15
0x180011dcc  jnz     short loc_180011DEA
0x180011dce  mov     edi, 80070057h
0x180011dd3  lea     rdx, qword_18001E388
0x180011dda  lea     rcx, qword_180019B28
0x180011de1  mov     ebx, edi
0x180011de3  call    sub_1800021B0
0x180011de8  jmp     short loc_180011D9C
0x180011dea  test    r14, r14
0x180011ded  jz      short loc_180011D95
0x180011def  mov     r8, rdx
0x180011df2  lea     rcx, [rbp+var_30]
0x180011df6  mov     esi, 1
0x180011dfb  mov     edx, esi
0x180011dfd  call    sub_180004F44
0x180011e02  mov     ebx, eax
0x180011e04  test    eax, eax
0x180011e06  jns     short loc_180011E0C
0x180011e08  mov     ecx, eax
0x180011e0a  jmp     short loc_180011D9E
0x180011e0c  mov     r9d, esi
0x180011e0f  mov     [rsp+68h+var_48], esi
0x180011e13  mov     r8d, 21h ; '!'
0x180011e19  lea     rcx, [rbp+var_30]
0x180011e1d  mov     rdx, rdi
0x180011e20  call    sub_1800044DC
0x180011e25  mov     ebx, eax
0x180011e27  test    eax, eax
0x180011e29  js      short loc_180011E08
0x180011e2b  lea     r8, [rbp+arg_0]
0x180011e2f  mov     edx, esi
0x180011e31  lea     rcx, [rbp+var_30]
0x180011e35  call    sub_180004660
0x180011e3a  mov     ebx, eax
0x180011e3c  test    eax, eax
0x180011e3e  js      short loc_180011E08
0x180011e40  mov     esi, [rbp+arg_0]
0x180011e43  test    esi, esi
0x180011e45  jnz     short loc_180011E5D
0x180011e47  xor     edi, edi
0x180011e49  xor     ebx, ebx
0x180011e4b  mov     ecx, ebx
0x180011e4d  call    sub_18000A8D0
0x180011e52  test    ebx, ebx
0x180011e54  jns     short loc_180011E90
0x180011e56  mov     ecx, ebx
0x180011e58  jmp     loc_180011D9E
0x180011e5d  xor     edx, edx
0x180011e5f  mov     edi, esi
0x180011e61  shl     edi, 4
0x180011e64  mov     eax, edi
0x180011e66  div     esi
0x180011e68  cmp     eax, 10h
0x180011e6b  jz      short loc_180011E49
0x180011e6d  lea     rdx, dword_18001E94C
0x180011e74  xor     edi, edi
0x180011e76  lea     rcx, dword_18001877C
0x180011e7d  mov     ebx, 80070216h
0x180011e82  call    sub_180001430
0x180011e87  mov     ecx, ebx
0x180011e89  call    sub_180006844
0x180011e8e  jmp     short loc_180011E4B
0x180011e90  lea     r9, [rbp+var_38]
0x180011e94  mov     r8d, edi
0x180011e97  mov     edx, 2
0x180011e9c  lea     rcx, [rbp+var_30]
0x180011ea0  call    sub_180008A40
0x180011ea5  mov     ebx, eax
0x180011ea7  test    eax, eax
0x180011ea9  js      loc_180011E08
0x180011eaf  mov     rax, [rbp+var_38]
0x180011eb3  mov     [r15], esi
0x180011eb6  mov     [r14], rax
0x180011eb9  mov     [rbp+var_38], 0
0x180011ec1  mov     ecx, ebx
0x180011ec3  call    sub_18000A8D0
0x180011ec8  lea     rcx, [rbp+var_30]
0x180011ecc  call    sub_180005208
0x180011ed1  lea     rcx, [rbp+var_38]
0x180011ed5  call    sub_18000532C
0x180011eda  mov     eax, ebx
0x180011edc  add     rsp, 68h
0x180011ee0  pop     r15
0x180011ee2  pop     r14
0x180011ee4  pop     rdi
0x180011ee5  pop     rsi
0x180011ee6  pop     rbx
0x180011ee7  pop     rbp
0x180011ee8  retn
```
