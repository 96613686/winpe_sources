# SLInstallLicense

- ea: `0x180012a40`
- end: `0x180012b68`
- name: `SLInstallLicense`
- size: `296`
- prototype: `HRESULT __stdcall(HSLC hSLC, UINT cbLicenseBlob, const BYTE *pbLicenseBlob, SLID *pLicenseFileId)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180001760`
- `0x180001ec0`
- `0x180002bf0`
- `0x1800044dc`
- `0x18000469c`
- `0x180004f80`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f114`
- `0x180012a40`

## pseudocode

```c
HRESULT __stdcall SLInstallLicense(HSLC hSLC, UINT cbLicenseBlob, const BYTE *pbLicenseBlob, SLID *pLicenseFileId)
{
  __int64 v7; // rcx
  HRESULT v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v12[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  UINT v14; // [rsp+78h] [rbp+28h] BYREF

  v14 = cbLicenseBlob;
  v12[0] = (__int64)&v13 + 8;
  v12[1] = (__int64)&v13;
  v13 = 0;
  sub_180001EC0(&dword_180019A14, qword_18001E2D0);
  if ( !hSLC )
  {
    sub_180002BF0(&dword_180019EBC, &dword_18001E78C);
LABEL_3:
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_12:
    sub_180006844(v7);
    goto LABEL_13;
  }
  if ( !pbLicenseBlob || !pLicenseFileId )
    goto LABEL_3;
  v9 = sub_180004F80(v12, 1, &v14);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_11;
  v8 = sub_18000F114(v12, 2, v14, pbLicenseBlob);
  sub_180001760(qword_180019988, qword_18001E210);
  if ( v8 < 0 )
  {
    v7 = (unsigned int)v8;
    goto LABEL_12;
  }
  v9 = sub_1800044DC(v12, (__int64)hSLC, 0, 1, 1);
  v8 = v9;
  if ( v9 < 0 || (v9 = sub_18000469C(v12, v10, pLicenseFileId), v8 = v9, v9 < 0) )
  {
LABEL_11:
    v7 = (unsigned int)v9;
    goto LABEL_12;
  }
LABEL_13:
  sub_18000A8D0((unsigned int)v8);
  sub_180005208(v12);
  return v8;
}

```

## disassembly

```asm
0x180012a40  mov     [rsp-18h+arg_0], rbx
0x180012a45  mov     [rsp-18h+arg_10], rsi
0x180012a4a  mov     [rsp-18h+arg_8], edx
0x180012a4e  push    rbp
0x180012a4f  push    rdi
0x180012a50  push    r14
0x180012a52  mov     rbp, rsp
0x180012a55  sub     rsp, 50h
0x180012a59  lea     rax, [rbp+var_10+8]
0x180012a5d  mov     r14, rcx
0x180012a60  mov     [rbp+var_20], rax
0x180012a64  lea     rdx, qword_18001E2D0
0x180012a6b  lea     rax, [rbp+var_10]
0x180012a6f  xorps   xmm0, xmm0
0x180012a72  lea     rcx, dword_180019A14
0x180012a79  mov     [rbp+var_18], rax
0x180012a7d  mov     rdi, r9
0x180012a80  mov     rsi, r8
0x180012a83  movdqu  [rbp+var_10], xmm0
0x180012a88  call    sub_180001EC0
0x180012a8d  test    r14, r14
0x180012a90  jnz     short loc_180012AB1
0x180012a92  lea     rdx, dword_18001E78C
0x180012a99  lea     rcx, dword_180019EBC
0x180012aa0  call    sub_180002BF0
0x180012aa5  mov     ecx, 80070057h
0x180012aaa  mov     ebx, ecx
0x180012aac  jmp     loc_180012B3C
0x180012ab1  test    rsi, rsi
0x180012ab4  jz      short loc_180012AA5
0x180012ab6  test    rdi, rdi
0x180012ab9  jz      short loc_180012AA5
0x180012abb  lea     r8, [rbp+arg_8]
0x180012abf  mov     edx, 1
0x180012ac4  lea     rcx, [rbp+var_20]
0x180012ac8  call    sub_180004F80
0x180012acd  mov     ebx, eax
0x180012acf  test    eax, eax
0x180012ad1  js      short loc_180012B3A
0x180012ad3  mov     r8d, [rbp+arg_8]
0x180012ad7  lea     rcx, [rbp+var_20]
0x180012adb  mov     r9, rsi
0x180012ade  mov     edx, 2
0x180012ae3  call    sub_18000F114
0x180012ae8  lea     rdx, qword_18001E210
0x180012aef  mov     ebx, eax
0x180012af1  lea     rcx, qword_180019988
0x180012af8  call    sub_180001760
0x180012afd  test    ebx, ebx
0x180012aff  jns     short loc_180012B05
0x180012b01  mov     ecx, ebx
0x180012b03  jmp     short loc_180012B3C
0x180012b05  mov     r9d, 1
0x180012b0b  mov     [rsp+50h+var_30], 1
0x180012b13  xor     r8d, r8d
0x180012b16  lea     rcx, [rbp+var_20]
0x180012b1a  mov     rdx, r14
0x180012b1d  call    sub_1800044DC
0x180012b22  mov     ebx, eax
0x180012b24  test    eax, eax
0x180012b26  js      short loc_180012B3A
0x180012b28  mov     r8, rdi
0x180012b2b  lea     rcx, [rbp+var_20]
0x180012b2f  call    sub_18000469C
0x180012b34  mov     ebx, eax
0x180012b36  test    eax, eax
0x180012b38  jns     short loc_180012B41
0x180012b3a  mov     ecx, eax
0x180012b3c  call    sub_180006844
0x180012b41  mov     ecx, ebx
0x180012b43  call    sub_18000A8D0
0x180012b48  lea     rcx, [rbp+var_20]
0x180012b4c  call    sub_180005208
0x180012b51  lea     r11, [rsp+50h+var_s0]
0x180012b56  mov     eax, ebx
0x180012b58  mov     rbx, [r11+20h]
0x180012b5c  mov     rsi, [r11+30h]
0x180012b60  mov     rsp, r11
0x180012b63  pop     r14
0x180012b65  pop     rdi
0x180012b66  pop     rbp
0x180012b67  retn
```
